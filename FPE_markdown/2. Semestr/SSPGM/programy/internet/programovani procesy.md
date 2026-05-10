---
title: "programovani procesy.html"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/programy/internet/programovani procesy.html"
date: 2009-05-03
type: HTML
---

# Unix Process API {#unix-process-api align="center"}

## Contents

[Process creation](#Process%20creation)\
[fork](#fork)\
[exec](#exec)\
[Example:](#Example:)\
[Process suspension](#Process%20suspension)\
[Process removal](#Process%20removal)\
[Process environment](#Process%20environment)\
[Information sharing](#Information%20sharing)\
[X Windows and Processes](#X%20Windows%20and%20Processes)\

::: {section=""}
## [Process creation]{#Process creation}

The Unix API allows creation of asynchronous processes where each
process has a parent. Each process has a process ID (a number) that can
be used to tell them apart. This PID is shown in the user-level command
\`\`ps\'\'. Because the parent process can resume execution before a
child terminates, the parent can continue to create processes. The
children can also create processes\
![fork](programovani%20procesy_soubory/pid_fork.gif){tppabs="http://jan.netcomp.monash.edu.au/ssw/processes/pid_fork.gif"}\
This creates a tree of processes.\
![tree](programovani%20procesy_soubory/pid_tree1.gif){tppabs="http://jan.netcomp.monash.edu.au/ssw/processes/pid_tree1.gif"}\
or\
![tree](programovani%20procesy_soubory/pid_tree2.gif){tppabs="http://jan.netcomp.monash.edu.au/ssw/processes/pid_tree2.gif"}

## [fork]{#fork}

The function call to do this is

    #include <sys/types.h>
    pid_t fork(void)

This splits the current process into two almost identical copies. A copy
is made of the user and system stacks, of the allocated data space and
of the registers. The major difference is that one has the PID of the
parent, the other has a new PID. The fork returns a value that is a PID.
The PID is zero if you are the child, or the PID of the child if you are
the parent.\
**Example:** This creates one child:

    #include <stdio.h>
    #include <sys/types.h>

    int main(void)
    { pid_t pid;

      pid = fork();
      if (pid == -1) {
        fprintf(stderr, 
               "fork failed\n");
        exit(1);
      }
      if (pid == 0) {
        printf("I'm the child\n");
        exit(0);
      }
      if (pid > 0) {
        printf("I'm the parent \
    with child %d\n", pid);
        exit(0);
      }
    }

What order are these two messages printed in? The child and the parent
can call any functions in the program, and execute as independent
processes with the same program code. There is (at present) no
communication between them.

## [exec]{#exec}

It is common to want to *replace* one of these processes so that it uses
a different *program.* For example, suppose the process creates a file
that it wants printed. In Unix it cannot print it itself, because it
does not have access to the line printer device. The program \`\`lpr\'\'
must be used. One way is

    system("lpr myfile");

This runs synchronously, so until the line printer program terminates
the calling program suspends. Printing an empty file takes about 150
milliseconds. A preferable way may be to fork a new process and let the
parent continue with the main piece of work, while the child prints the
file asynchronously. This is possible, but cruddy:

    if (fork() == 0)
      system("lpr myfile");
    else { /* parent */ }

It creates a child process that does nothing but wait for \`\`system\'\'
to finish. Better is to replace the child with the \`\`lpr\'\' program.
This is the job of the \`\`exec\'\' functions

    int execlp(char *file,
               char *arg0,
               char *arg1,
               ....
               char *argn,
               (char *) 0);

The \`\`file\'\' argument is the name of the program to execute. This
uses the PATH environment variable to find the file (like shell commands
do). \`\`arg0\'\' is often the same as \`\`file\'\'. This is used as the
name of the process, as reported by \`\`ps\'\'. \`\`arg1\'\' to
\`\`argn\'\' are the arguments to the command. This must be terminated
by a NULL pointer to show the end of the list. In normal operation
\`\`exec\'\' never returns. If if fails, it returns -1.

## [Example:]{#Example:}

Fork and use exec to print a file

    if (fork() == 0)
      if (execlp("lpr",
                 "lpr",
                 "myfile", 
                 (char *) 0) == -1)
        fprintf(stderr,
                "exec failed\n");
    else { /* parent */ }

or more simply

    if (fork() == 0)
    {
      execlp("lpr",
             "lpr",
             "myfile", 
             (char *) 0);
      fprintf(stderr,
              "exec failed\n");
    }
    else { /* parent */ }

Here is a simple example:

    #include <;stdio.h>
    #include <stdlib.h>
    #include <sys/wait.h>
    #include <sys/types.h>

    int main(int argc, char *argv[])
    {
      pid_t pid;

      if ((pid = fork()) < 0)
      {
        fprintf(stderr,
            "fork failed\n");
        exit(1);
      }

      if (pid == 0)
      {
        execlp("echo",
           "echo",
           "Hello from",
           "the child",
           (char *) NULL);
        fprintf(stderr, 
               "execl failed\n");
        exit(2);
      }

      printf("parent carries on\n");
      exit(0);
    }

(What happens if the `exit(2)` is removed and the `execlp ` fails? Why?)

## [Process suspension]{#Process suspension}

### wait

Suppose the file was a temporary file. After printing, it should be
deleted. The child cannot delete it, because after the \`\`exec\'\' it
no longer exists. The parent cannot directly delete it because the
\`\`lpr\'\' program may still be accessing it. (Actually, an option on
lpr allows removal after printing - ignore this.) When \`\`lpr\'\'
terminates, the parent can remove the file. So the parent has to be able
to decide when a child has finished.

    #include <sys/types.h>
    #include <sys/wait.h>
    pid_t wait(int *status)

This waits for a process to terminate and returns the PID of one that
did. It also returns status information.

    if ((pid = fork()) == 0)
      if (execlp("lpr",
                 "lpr",
                 "myfile", 
                 (char *) 0) == -1)
        fprintf(stderr,
                "exec failed\n");
    else {
      /* do lots of things while
         the printing takes place
       */

      /* now remove the file */
      while (wait(NULL) != pid)
        ;
      unlink("myfile");

      /* and do lots more things */
    }

### sleep

A process may suspend for a period of time using the sleep command

    unsigned int sleep(seconds)

    #include <stdio.h>
    #include <stdlib.h>
    #include <sys/wait.h>
    #include <sys/types.h>

    int main(int argc, char *argv[])
    {
      pid_t pid;

      if ((pid = fork()) == 0)
      { /* child */
        printf("sleeping...\n");
        sleep(5);
        printf("waking ... and exiting\n");
      } else {
        if (pid > 0)
        {
          printf("waiting for child\n");
          wait(NULL);
          printf("child woke up\n");
        }
      }
    }

## [Process removal]{#Process removal}

### exit

When a process executes the \`\`exit\'\' command it terminates.

### kill

One process can send simple messages to another using the \`\`kill\'\'
command

    #include <sys/types.h>
    #include <signal.h>
    int kill( pid_t pid, int sig);

The process to which the signal is sent must have the same uid or be a
\`\`super user\'\' process. The signal is often SIGINT or SIGKILL.

    if (pid = (fork() == 0))
      ...
    else {
      /* let the child run for
         10 seconds max
       */
      sleep(10);
      kill(pid, SIGINT);
    }

### signal

A process can catch certain signals by installing a signal handler which
is a function invoked when the signal arrives.

    #include <stdio.h>
    #include <stdlib.h>
    #include <signal.h>
    #include <sys/types.h>

    void int_handler(int sig)
    {
      printf("Ouch - shot in the ...\n");
      exit(2);
    }

    int main(int argc, char *argv[])
    {
      pid_t pid;

      if ((pid = fork()) < 0)
      {
        fprintf(stderr,
            "fork failed\n");
        exit(1);
      }

      if (pid == 0)
      {
        signal(SIGINT, int_handler);
        while (1)
          printf("Running amok!!!\n");
      }

      sleep(3);
      kill(pid, SIGINT);
      exit(0);
    }

## [Process environment]{#Process environment}

A process has an entry in a table of processes. This table contains all
sorts of information (see \`\`internals\'\' lecture) including user ID,
current directory, etc. A set of function calls allows access to much of
this information:

### Process ID

    #include <:sys/types.h>
    pid_t getpid(void);

### User ID

    #include 
    uid_t getuid(void);

### User name

    char *getlogin(void);

### Current directory

    char *getcwd(char *dir,
                 int size);

**Example:** Who is running this program?

    #include <streamio.h>

    int main(void)
    { char *login;

      if ((login = getlogin())
              != NULL)
        cout << login << endl;
    }

## [Information sharing]{#Information sharing}

::: subsection
When a new process is created from a parent, some information is new,
some is copied and some id shared:

-   the user and system stacks are copied
-   the heap memory is copied (in a VM system the copies are delayed
    till writes take place)
-   the process id is new
-   the file descriptor table is shared

Other facets of process information follow this:

-   The accounting and usage statistics are new
-   the user id and group id are shared
-   the resource limits are shared
:::

## [X Windows and Processes]{#X Windows and Processes}

::: subsection
Process state does not include any information about X Windows - X is
treated just like any other application. Creating an X process is no
different to other applications. However, there are these cases:

-   To run an X application as a process, just use `exec()` as normal

        exec("xclock", "xclock", NULL)

-   To run a character application from within an `xterm`, use `exec()`
    as usual

        exec("pico", "pico", NULL)

-   To run a character application within a new `xterm` use the -e
    option `xterm -e pico`:

        exec("xterm", "xterm", "-e", "pico", NULL)
:::
:::

[![Home](programovani%20procesy_soubory/home.gif){tppabs="http://jan.netcomp.monash.edu.au/images/home.gif"}
Systems Software
Home](http://dce.felk.cvut.cz/por/os_api/index.htm){tppabs="http://jan.netcomp.monash.edu.au/ssw/"}

------------------------------------------------------------------------

[Jan Newmarch (http://jan.netcomp.monash.edu.au)
\<jan.newmarch@infotech.monash.edu.au\>](javascript:if(confirm('http://jan.netcomp.monash.edu.au/%20%20\n\nThis%20file%20was%20not%20retrieved%20by%20Teleport%20Pro,%20because%20it%20is%20addressed%20on%20a%20domain%20or%20path%20outside%20the%20boundaries%20set%20for%20its%20Starting%20Address.%20%20\n\nDo%20you%20want%20to%20open%20it%20from%20the%20server?'))window.location='http://jan.netcomp.monash.edu.au/'){tppabs="http://jan.netcomp.monash.edu.au/"}

\
Copyright © Jan Newmarch\
Last modified: Wed Nov 19 18:44:59 EST 1997
