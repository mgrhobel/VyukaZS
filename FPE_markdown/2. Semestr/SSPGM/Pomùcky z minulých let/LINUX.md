---
title: "LINUX.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/Pomùcky z minulých let/LINUX.doc"
date: 2005-09-19
type: DOC
---

# LINUX, SSPGM {#linux-sspgm .western}

\

Zdroje, literatura:

\

[[[http://www.doc.ic.ac.uk/\~wjk/UnixIntro/]{lang="de-DE"}](http://www.doc.ic.ac.uk/~wjk/UnixIntro/)]{.underline}

[[[http://www.skocovsky.cz]{lang="de-DE"}](http://www.skocovsky.cz/)]{.underline}

Operační system Unix a jazyk C

\

\

[[[http://iris.pef.zcu.cz/\~toman/SSPGM]{lang="en-US"}](http://iris.pef.zcu.cz/~toman/SSPGM)]{.underline}

\

[Maurice J. Bach: Principy ]{lang="en-US"}operačního systému Unix

\

1.  Lecture One

\

1.  1.  Objectives

This lecture covers:

-   The concept of an operating system.

-   The internal architecture of an operating system.

-   The evolution of the UNIX operating system into two broad schools
    (BSD and SYSV) and the development of Linux, a popular open source
    operating system.

-   The architecture of the Linux operating system in more detail.

-   How to log into (and out of) UNIX and change your password.

-   The general format of UNIX commands.

\

1.  2.  What is an operating systém

An operating system (OS) is a resource manager. It takes the form of a
set of software routines that allow users and application programs to
access system resources (e.g. the CPU, memory, disks, modems, printers
network cards etc.) in a **safe,** **efficient** and **abstract** way.

For example, an OS ensures **safe** access to a printer by allowing only
one application program to send data directly to the printer at any one
time. An OS encourages **efficient** use of the CPU by suspending
programs that are waiting for I/O operations to complete to make way for
programs that can use the CPU more productively. An OS also provides
convenient **abstractions** (such as files rather than disk locations)
which isolate application programmers and users from the details of the
underlying hardware.

![](LINUX_html_66776700.png){#opsys align="bottom" width="523"
height="461" border="0"}\
*Fig. 1.1:  General operating system architecture*

Fig. 1.1 presents the architecture of a typical operating system and
shows how an OS succeeds in presenting users and application programs
with a uniform interface without regard to the details of the underlying
hardware. We see that:

-   The operating system **kernel** is in direct control of the
    underlying hardware. The kernel provides low-level device, memory
    and processor management functions (e.g. dealing with interrupts
    from hardware devices, sharing the processor among multiple
    programs, allocating memory for programs etc.)

-   Basic hardware-independent kernel services are exposed to
    higher-level programs through a library of **system calls** (e.g.
    services to create a file, begin execution of a program, or open a
    logical network connection to another computer).

-   **Application programs** (e.g. word processors, spreadsheets) and
    **system utility programs** (simple but useful application programs
    that come with the operating system, e.g. programs which find text
    inside a group of files) make use of system calls. Applications and
    system utilities are launched using a **shell** (a textual command
    line interface) or a **graphical user interface** that provides
    direct user interaction.

Operating systems (and different flavours of the same operating system)
can be distinguished from one another by the system calls, system
utilities and user interface they provide, as well as by the resource
scheduling policies implemented by the kernel.

1.  3.  Brief history of Unix

\

UNIX has been a popular OS for more than two decades because of its
multi-user, multi-tasking environment, stability, portability and
powerful networking capabilities. What follows here is a simplified
history of how UNIX has developed (to get an idea for how complicated
things really are, see the web site
[<http://www.levenez.com/unix/>]{.underline}).

![](LINUX_html_943af9df.png){#familytree align="bottom" width="529"
height="613" border="0"}\
*Fig. 1.2: Simplified UNIX FamilyTree*

In the late 1960s, researchers from General Electric, MIT and Bell Labs
launched a joint project to develop an ambitious multi-user,
multi-tasking OS for mainframe computers known as MULTICS (Multiplexed
Information and Computing System). MULTICS failed (for [[some MULTICS
enthusiasts](http://www.multicians.org/myths.html#fail69)]{.underline}
\"failed\" is perhaps too strong a word to use here), but it did inspire
Ken Thompson, who was a researcher at Bell Labs, to have a go at writing
a simpler operating system himself. He wrote a simpler version of
MULTICS on a PDP7 in assembler and called his attempt UNICS (Uniplexed
Information and Computing System). Because memory and CPU power were at
a premium in those days, UNICS (eventually shortened to UNIX) used short
commands to minimize the space needed to store them and the time needed
to decode them - hence the tradition of short UNIX commands we use
today, e.g. ls, cp, rm, mv etc.

Ken Thompson then teamed up with Dennis Ritchie, the author of the first
C compiler in 1973. They rewrote the UNIX kernel in C - this was a big
step forwards in terms of the system\'s portability - and released the
Fifth Edition of UNIX to universities in 1974. The Seventh Edition,
released in 1978, marked a split in UNIX development into two main
branches: SYSV (System 5) and BSD (Berkeley Software Distribution). BSD
arose from the University of California at Berkeley where Ken Thompson
spent a sabbatical year. Its development was continued by students at
Berkeley and other research institutions. SYSV was developed by AT&T and
other commercial companies. UNIX flavours based on SYSV have
traditionally been more conservative, but better supported than
BSD-based flavours.

The latest incarnations of SYSV (SVR4 or System 5 Release 4) and BSD
Unix are actually very similar. Some minor differences are to be found
in  file system structure, system utility names and options and system
call libraries as shown in Fig 1.3.\
 

+-----------------------------------------------------------------------+
|   [**Feature**]{.underline}**          ** [**Typical                  |
| SYSV**]{.underline}**           ** [**Typical BSD**]{.underline}\     |
|   kernel name       /unix                   /vmunix\                  |
|   boot init         /etc/rc.d directories   /etc/rc.\* files\         |
|   mounted FS        /etc/mnttab             /etc/mtab\                |
|   default shell     sh, ksh                 csh, tcsh\                |
|   FS block size     512 bytes-\>2K           4K-\>8K\                 |
|   print subsystem   lp, lpstat, cancel      lpr, lpq, lprm\           |
|   echo command      echo \"\\c\"               echo -n\               |
|    (no new line)\                                                     |
|   ps command        ps -fae                 ps -aux\                  |
|   multiple wait     poll                    select\                   |
|     syscalls\                                                         |
|   memory access     memset, memcpy          bzero, bcopy\             |
|     syscalls                                                          |
+-----------------------------------------------------------------------+

*Fig. 1.3: Differences between SYSV and BSD*

Linux is a free open source UNIX OS for PCs that was originally
developed in 1991 by Linus Torvalds, a Finnish undergraduate student.
Linux is neither pure SYSV or pure BSD. Instead, incorporates some
features from each (e.g. SYSV-style startup files but BSD-style file
system layout) and aims to conform with a set of IEEE standards called
POSIX (Portable Operating System Interface). To maximise code
portability, it typically supports SYSV, BSD and POSIX system calls
(e.g. poll, select, memset, memcpy, bzero and bcopy are all supported).

The open source nature of Linux means that the source code for the Linux
kernel is freely available so that anyone can add features and correct
deficiencies. This approach has been very successful and what started as
one person\'s project has now turned into a collaboration of hundreds of
volunteer developers from around the globe. The open source approach has
not just successfully been applied to kernel code, but also to
application programs for Linux (see e.g.
[[http://www.freshmeat.net](http://www.freshmeat.net/)]{.underline}).

As Linux has become more popular, several different development streams
or distributions have emerged, e.g. Redhat, Slackware, Mandrake, Debian,
and Caldera. A distribution comprises a prepackaged kernel, system
utilities, GUI interfaces and application programs.

Redhat is the most popular distribution because it has been ported to a
large number of hardware platforms (including Intel, Alpha, and SPARC),
it is easy to use and install and it comes with a comprehensive set of
utilities and applications including the X Windows graphics system,
GNOME and KDE GUI environments, and the StarOffice suite (an open source
MS-Office clone for Linux).

1.  4.  Architecture of the Unix Operating Systém

\

Linux has all of the components of a typical OS (at this point you might
like to refer back to Fig 1.1):

-   **Kernel**\
    The Linux kernel includes device driver support for a large number
    of PC hardware devices (graphics cards, network cards, hard disks
    etc.), advanced processor and memory management features, and
    support for many different types of filesystems (including DOS
    floppies and the ISO9660 standard for CDROMs). In terms of the
    services that it provides to application programs and system
    utilities, the kernel implements most BSD and SYSV system calls, as
    well as the system calls described in the POSIX.1 specification.

The kernel (in raw binary form that is loaded directly into memory at
system startup time) is typically found in the file /boot/vmlinuz, while
the source files can usually be found in /usr/src/linux.The latest
version of the Linux kernel sources can be downloaded from
[[http://www.kernel.org](http://www.kernel.org/)]{.underline}.\
 

-   **Shells and GUIs**\
    Linux supports two forms of command input: through textual command
    line shells similar to those found on most UNIX systems (e.g. sh -
    the Bourne shell, bash - the Bourne again shell and csh - the C
    shell) and through graphical interfaces (GUIs) such as the KDE and
    GNOME window managers. If you are connecting remotely to a server
    your access will typically be through a command line shell.\
     

-   **System Utilities**\
    Virtually every system utility that you would expect to find on
    standard implementations of UNIX (including every system utility
    described in the POSIX.2 specification) has been ported to Linux.
    This includes commands such as ls, cp, grep, awk, sed, bc, wc, more,
    and so on. These system utilities are designed to be powerful tools
    that do a single task extremely well (e.g. grep finds text inside
    files while wc counts the number of words, lines and bytes inside a
    file). Users can often solve problems by interconnecting these tools
    instead of writing a large monolithic application program.

Like other UNIX flavours, Linux\'s system utilities also include server
programs called **daemons** which provide remote network and
administration services (e.g. telnetd and sshd provide remote login
facilities, lpd provides printing services, httpd serves web pages,
crond runs regular system administration tasks automatically). A daemon
(probably derived from the Latin word which refers to a beneficient
spirit who watches over someone, or perhaps short for \"Disk And
Execution MONitor\") is usually spawned automatically at system startup
and spends most of its time lying dormant (lurking?) waiting for some
event to occur.\
 

-   **Application programs**\
    Linux distributions typically come with several useful application
    programs as standard. Examples include the emacs editor, xv (an
    image viewer), gcc (a C compiler), g++ (a C++ compiler), xfig (a
    drawing package), latex (a powerful typesetting language) and
    soffice (StarOffice, which is an MS-Office style clone that can read
    and write Word, Excel and PowerPoint files).

Redhat Linux also comes with rpm, the Redhat Package Manager which makes
it easy to install and uninstall application programs.

1.  5.  Logging into and out Unix OS

\

**Text-based (TTY) terminals**:

When you connect to a UNIX computer remotely (using telnet) or when you
log in locally using a text-only terminal, you will see the prompt:

    login:

At this prompt, type in your usename and press the
enter/return/![](LINUX_html_8d1f4a31.png){#enter align="bottom"
width="27" height="15" border="0"} key. Remember that UNIX is case
sensitive (i.e. Will, WILL and will are all different logins). You
should then be prompted for your password:

    login: will\
    password:

Type your password in at the prompt and press the
enter/return/![](LINUX_html_8d1f4a31.png){#Image1 align="bottom"
width="27" height="15" border="0"} key. Note that your password will not
be displayed on the screen as you type it in.

If you mistype your username or password you will get an appropriate
message from the computer and you will be presented with the login:
prompt again. Otherwise you should be presented with a shell prompt
which looks something like this:

    \$

To log out of a text-based UNIX shell, type \"exit\" at the shell prompt
(or if that doesn\'t work try \"logout\"; if that doesn\'t work press
ctrl-d).

**Graphical terminals:**

If you\'re logging into a UNIX computer locally, or if you are using a
remote login facility that supports graphics, you might instead be
presented with a graphical prompt with login and password fields. Enter
your user name and password in the same way as above (N.B. you may need
to press the TAB key to move between fields).

Once you are logged in, you should be presented with a graphical window
manager that looks similar to the Microsoft Windows interface. To bring
up a window containing a shell prompt look for menus or icons which
mention the words \"shell\", \"xterm\", \"console\" or \"terminal
emulator\".

To log out of a graphical window manager, look for menu options similar
to \"Log out\" or \"Exit\".

1.  6.  Changing Your password

\

One of the things you should do when you log in for the first time is to
change your password.

The UNIX command to change your password is passwd:

      \$ passwd![](LINUX_html_8d1f4a31.png){#Image2 align="bottom"
width="27" height="15" border="0"}

The system will prompt you for your old password, then for your new
password. To eliminate any possible typing errors you have made in your
new password, it will ask you to reconfirm your new password.

Remember the following points when choosing your password:

-   -   Avoid characters which might not appear on all keyboards, e.g.
        \'£\'.

    -   The weakest link in most computer security is user passwords so
        keep your password a secret, don\'t write it down and don\'t
        tell it to anyone else. Also avoid dictionary words or words
        related to your personal details (e.g. your boyfriend or
        girlfriend\'s name or your login).

    -   Make it at least 7 or 8 characters long and try to use a mix of
        letters, numbers and punctuation.

1.  7.  General fomat of Unix command

\

A UNIX command line consists of the name of a UNIX command (actually the
\"command\" is the name of a built-in shell command, a system utility or
an application program) followed by its \"arguments\" (options and the
target filenames and/or expressions). The general syntax for a UNIX
command is

    \$ command -options targets![](LINUX_html_8d1f4a31.png){#Image3
align="bottom" width="27" height="15" border="0"}

Here command can be though of as a verb, options as an adverb and
targets as the direct objects of the verb. In the case that the user
wishes to specify several options, these need not always be listed
separately (the options can sometimes be listed altogether after a
single dash).

Excersise:

Cv1.txt

\

Cviceni SSPGM 1. tyden

\

1\. Nastavte si uzivatelske prostredi - PATH, PS1 \...

\

2\. Nastavte si uzivatelske konto (chfn \...)

\

3\. Vytvorte si adresar bin, nastavte na nej cestu,

vytvorte skript \<l\> pro standardne pouzivany vypis (ls)

\

4\. Seznamte se s napovedou - man, apropos, whatis

\

5\. Vyzkousejte a seznamte se s prikazy

ps

pwd, cd, mkdir, rmdir, touch, cp, rm, mv, more, echo \...

vi, ed, joe, mc

ln

grep, egrep, fgrep

who, w, date, time, wc

\

6\. Seznamte se a vyzkousejte ruzne shelly dash (default), csh, sh, tcsh

\

7\. Seznamte se a vyzkousejte utilitu find, vyhledejte pomoci ni

prikaz \<traceroute\> a adresar dejte do vyhledavaci cesty (PATH)

\

\

\

1.  Log on a Linux machine or connect to one from a Windows machine
    (e.g. click on the Exceed icon and then use putty to connect to the
    server kiwi. Enter your login (user name) and password at relevant
    prompts.

2.  Enter these commands at the UNIX prompt, and try to interpret the
    output. Ask questions and don\'t be afraid to experiment (as a
    normal user you cannot do much harm):

    -   echo hello world![](LINUX_html_8d1f4a31.png){#Image4
        align="bottom" width="27" height="15" border="0"}

    -   passwd![](LINUX_html_8d1f4a31.png){#Image5 align="bottom"
        width="27" height="15" border="0"}

    -   date![](LINUX_html_8d1f4a31.png){#Image6 align="bottom"
        width="27" height="15" border="0"}

    -   hostname![](LINUX_html_8d1f4a31.png){#Image7 align="bottom"
        width="27" height="15" border="0"}

    -   arch![](LINUX_html_8d1f4a31.png){#Image8 align="bottom"
        width="27" height="15" border="0"}

    -   uname -a![](LINUX_html_8d1f4a31.png){#Image9 align="bottom"
        width="27" height="15" border="0"}

    -   dmesg \| more![](LINUX_html_8d1f4a31.png){#Image10
        align="bottom" width="27" height="15" border="0"} (you may need
        to press q to quit)

    -   uptime![](LINUX_html_8d1f4a31.png){#Image11 align="bottom"
        width="27" height="15" border="0"}

    -   who am i![](LINUX_html_8d1f4a31.png){#Image12 align="bottom"
        width="27" height="15" border="0"}

    -   who![](LINUX_html_8d1f4a31.png){#Image13 align="bottom"
        width="27" height="15" border="0"}

    -   id![](LINUX_html_8d1f4a31.png){#Image14 align="bottom"
        width="27" height="15" border="0"}

    -   last![](LINUX_html_8d1f4a31.png){#Image15 align="bottom"
        width="27" height="15" border="0"}

    -   finger![](LINUX_html_8d1f4a31.png){#Image16 align="bottom"
        width="27" height="15" border="0"}

    -   w![](LINUX_html_8d1f4a31.png){#Image17 align="bottom" width="27"
        height="15" border="0"}

    -   top![](LINUX_html_8d1f4a31.png){#Image18 align="bottom"
        width="27" height="15" border="0"} (you may need to press q to
        quit)

    -   echo \$SHELL![](LINUX_html_8d1f4a31.png){#Image19 align="bottom"
        width="27" height="15" border="0"}

    -   echo
        {con,pre}{sent,fer}{s,ed}![](LINUX_html_8d1f4a31.png){#Image20
        align="bottom" width="27" height="15" border="0"}

    -   man \"automatic door\"![](LINUX_html_8d1f4a31.png){#Image21
        align="bottom" width="27" height="15" border="0"}

    -   man ls![](LINUX_html_8d1f4a31.png){#Image22 align="bottom"
        width="27" height="15" border="0"} (you may need to press q to
        quit)

    -   man who![](LINUX_html_8d1f4a31.png){#Image23 align="bottom"
        width="27" height="15" border="0"} (you may need to press q to
        quit)

    -   who can tell me why i got
        divorced![](LINUX_html_8d1f4a31.png){#Image24 align="bottom"
        width="27" height="15" border="0"}

    -   lost![](LINUX_html_8d1f4a31.png){#Image25 align="bottom"
        width="27" height="15" border="0"}

    -   clear![](LINUX_html_8d1f4a31.png){#Image26 align="bottom"
        width="27" height="15" border="0"}

    -   cal 2000![](LINUX_html_8d1f4a31.png){#Image27 align="bottom"
        width="27" height="15" border="0"}

    -   cal 9 1752![](LINUX_html_8d1f4a31.png){#Image28 align="bottom"
        width="27" height="15" border="0"} (do you notice anything
        unusual?)

    -   bc -l![](LINUX_html_8d1f4a31.png){#Image29 align="bottom"
        width="27" height="15" border="0"} (type
        quit![](LINUX_html_8d1f4a31.png){#Image30 align="bottom"
        width="27" height="15" border="0"} or press Ctrl-d to quit)

    -   echo 5+4 \| bc -l![](LINUX_html_8d1f4a31.png){#Image31
        align="bottom" width="27" height="15" border="0"}

    -   yes please![](LINUX_html_8d1f4a31.png){#Image32 align="bottom"
        width="27" height="15" border="0"} (you may need to press Ctrl-c
        to quit)

    -   time sleep 5![](LINUX_html_8d1f4a31.png){#Image33 align="bottom"
        width="27" height="15" border="0"}

    -   history![](LINUX_html_8d1f4a31.png){#Image34 align="bottom"
        width="27" height="15" border="0"}

```{=html}
<!-- -->
```
2.  Lecture Two

\

1.  1.  Objectives

This lecture covers:

 The UNIX filesystem and directory structure.

 File and directory handling commands.

 How to make symbolic and hard links.

 How wildcard filename expansion works.

 What argument quoting is and when it should be used.

1.  2.  Unix Filesystem

The UNIX operating system is built around the concept of a filesystem
which is used to store all of the information that constitutes the
long-term state of the system. This state includes the operating system
kernel itself, the executable files for the commands supported by the
operating system, configuration information, temporary workfiles, user
data, and various special files that are used to give controlled access
to system hardware and operating system functions.

Every item stored in a UNIX filesystem belongs to one of four types:

1.  **Ordinary files**\
    Ordinary files can contain text, data, or program information. Files
    cannot contain other files or directories. Unlike other operating
    systems, UNIX filenames are not broken into a name part and an
    extension part (although extensions are still frequently used as a
    means to classify files). Instead they can contain any keyboard
    character except for \'/\' and be up to 256 characters long (note
    however that characters such as \*,?,# and & have special meaning in
    most shells and should not therefore be used in filenames). Putting
    spaces in filenames also makes them difficult to manipulate - rather
    use the underscore \'\_\'.

2.  **Directories**\
    Directories are containers or folders that hold files, and other
    directories.

3.  **Devices**\
    To provide applications with easy access to hardware devices, UNIX
    allows them to be used in much the same way as ordinary files. There
    are two types of devices in UNIX - **block-oriented** devices which
    transfer data in blocks (e.g. hard disks) and **character-oriented**
    devices that transfer data on a byte-by-byte basis (e.g. modems and
    dumb terminals).

4.  **Links**\
    A link is a pointer to another file. There are two types of links -
    a **hard link** to a file is indistinguishable from the file itself.
    A **soft link** (or symbolic link) provides an indirect pointer or
    shortcut to a file. A soft link is implemented as a directory file
    entry containing a pathname.

```{=html}
<!-- -->
```
1.  3.  Typical Unix Directory structure

The UNIX filesystem is laid out as a hierarchical tree structure which
is anchored at a special top-level directory known as the root
(designated by a slash \'/\'). Because of the tree structure, a
directory can have many child directories, but only one parent
directory. Fig. 2.1 illustrates this layout.

![](LINUX_html_34d7e84c.png){#dirtree align="bottom" width="573"
height="383" border="0"}\
*Fig. 2.1: Part of a typical UNIX filesystem tree*

To specify a location in the directory hierarchy, we must specify a path
through the tree. The path to a location can be defined by an absolute
path from the root /, or as a relative path from the current working
directory. To specify a path, each directory along the route from the
source to the destination must be included in the path, with each
directory in the sequence being separated by a slash. To help with the
specification of relative paths, UNIX provides the shorthand \".\" for
the current directory and \"..\" for the parent directory. For example,
the absolute path to the directory \"play\" is /home/will/play, while
the relative path to this directory from \"zeb\" is ../will/play.

Fig. 2.2 shows some typical directories you will find on UNIX systems
and briefly describes their contents. Note that these although these
subdirectories appear as part of a seamless logical filesystem, they do
not need be present on the same hard disk device; some may even be
located on a remote machine and accessed across a network.\
 

+----------+-----------------------------------------------------------+
| [**      | [**Typical Contents**]{.underline}                        |
| Director |                                                           |
| y**]{.un |                                                           |
| derline} |                                                           |
+----------+-----------------------------------------------------------+
| /        | The \"root\" directory                                    |
+----------+-----------------------------------------------------------+
| /bin     | Essential low-level system utilities                      |
+----------+-----------------------------------------------------------+
| /usr/bin | Higher-level system utilities and application programs    |
+----------+-----------------------------------------------------------+
| /sbin    | Superuser system utilities (for performing system         |
|          | administration tasks)                                     |
+----------+-----------------------------------------------------------+
| /lib     | Program libraries (collections of system calls that can   |
|          | be included in programs by a compiler) for low-level      |
|          | system utilities                                          |
+----------+-----------------------------------------------------------+
| /usr/lib | Program libraries for higher-level user programs          |
+----------+-----------------------------------------------------------+
| /tmp     | Temporary file storage space (can be used by any user)    |
+----------+-----------------------------------------------------------+
| /home or | User home directories containing personal file space for  |
| /homes   | each user. Each directory is named after the login of the |
|          | user.                                                     |
+----------+-----------------------------------------------------------+
| /etc     | UNIX system configuration and information files           |
+----------+-----------------------------------------------------------+
| /dev     | Hardware devices                                          |
+----------+-----------------------------------------------------------+
| /proc    | A pseudo-filesystem which is used as an interface to the  |
|          | kernel.  Includes a sub-directory for each active program |
|          | (or process).                                             |
+----------+-----------------------------------------------------------+

*Fig. 2.2: Typical UNIX directories*

When you log into UNIX, your current working directory is your user home
directory. You can refer to your home directory at any time as \"\~\"
and the home directory of other users as \"\~\<login\>\". So \~will/play
is another way for user jane to specify an absolute path to the
directory /homes/will/play. User will may refer to the directory as
\~/play.

1.  4.  Directory and File Handling commnands

This section describes some of the more important directory and file
handling commands.

-   pwd (print \[current\] working directory)

pwd displays the full absolute path to the your current location in the
filesystem. So

    \$ pwd![](LINUX_html_8d1f4a31.png){#Image35 align="bottom"
width="27" height="15" border="0"}\
    /usr/bin

implies that /usr/bin is the current working directory.\
 

-   ls (list directory)

ls lists the contents of a directory. If no target directory is given,
then the contents of the current working directory are displayed. So, if
the current working directory is /,

    \$ ls![](LINUX_html_8d1f4a31.png){#Image36 align="bottom" width="27"
height="15" border="0"}\
    bin   dev  home  mnt   share  usr  var\
    boot  etc  lib   proc  sbin   tmp  vol

Actually, ls doesn\'t show you *all* the entries in a directory - files
and directories that begin with a dot (.) are hidden (this includes the
directories \'.\' and \'..\' which are always present). The reason for
this is that files that begin with a . usually contain important
configuration information and should not be changed under normal
circumstances. If you want to see all files, ls supports the -a option:

    \$ ls -a![](LINUX_html_8d1f4a31.png){#Image37 align="bottom"
width="27" height="15" border="0"}

Even this listing is not that helpful - there are no hints to properties
such as the size, type and ownership of files, just their names. To see
more detailed information, use the -l option (long listing), which can
be combined with the -a option as follows:

    \$ ls -a -l![](LINUX_html_8d1f4a31.png){#Image38 align="bottom"
width="27" height="15" border="0"}\
      (or, equivalently,)\
    \$ ls -al![](LINUX_html_8d1f4a31.png){#Image39 align="bottom"
width="27" height="15" border="0"}\
 

Each line of the output looks like this:

![](LINUX_html_e8df4132.png){#direntry align="bottom" width="667"
height="128" border="0"}

where:

-   -   *type* is a single character which is either \'d\' (directory),
        \'-\' (ordinary file), \'l\' (symbolic link), \'b\'
        (block-oriented device) or \'c\' (character-oriented device).

    -   *permissions* is a set of characters describing access rights.
        There are 9 permission characters, describing 3 access types
        given to 3 user categories. The three access types are read
        (\'r\'), write (\'w\') and execute (\'x\'), and the three users
        categories are the user who owns the file, users in the group
        that the file belongs to and other users (the general public).
        An \'r\', \'w\' or \'x\' character means the corresponding
        permission is present; a \'-\' means it is absent.

    -   *links* refers to the number of filesystem links pointing to the
        file/directory (see the discussion on hard/soft links in the
        next section).

    -   *owner* is usually the user who created the file or directory.

    -   *group* denotes a collection of users who are allowed to access
        the file according to the group access rights specified in the
        permissions field.

    -   *size* is the length of a file, or the number of bytes used by
        the operating system to store the list of files in a directory.

    -   *date* is the date when the file or directory was last modified
        (written to). The -u option display the time when the file was
        last accessed (read).

    -   *name* is the name of the file or directory.

\
ls supports more options. To find out what they are, type:

    \$ man ls![](LINUX_html_8d1f4a31.png){#Image40 align="bottom"
width="27" height="15" border="0"}

man is the online UNIX user manual, and you can use it to get help with
commands and find out about what options are supported. It has quite a
terse style which is often not that helpful, so some users prefer to the
use the (non-standard) info utility if it is installed:

    \$ info ls![](LINUX_html_8d1f4a31.png){#Image41 align="bottom"
width="27" height="15" border="0"}\
 

-   cd (change \[current working\] directory)

    \$ cd *path*

changes your current working directory to *path* (which can be an
absolute or a relative path). One of the most common relative paths to
use is \'..\' (i.e. the parent directory of the current directory).

Used without any target directory

    \$ cd![](LINUX_html_8d1f4a31.png){#Image42 align="bottom" width="27"
height="15" border="0"}

resets your current working directory to your home directory (useful if
you get lost). If you change into a directory and you subsequently want
to return to your original directory, use

    \$ cd -![](LINUX_html_8d1f4a31.png){#Image43 align="bottom"
width="27" height="15" border="0"}\
 

-   mkdir (make directory)

    \$ mkdir *directory*

creates a subdirectory called  *directory*in the current working
directory. You can only create subdirectories in a directory if you have
write permission on that directory.

-   rmdir (remove directory)

    \$ rmdir *directory*

removes the subdirectory *directory* from the current working directory.
You can only remove subdirectories if they are completely empty (i.e. of
all entries besides the \'.\' and \'..\' directories).\
 

-   cp (copy)

cp is used to make copies of files or entire directories. To copy files,
use:

    \$ cp *source-file(s) destination*

where *source-file(s)* and *destination* specify the source and
destination of the copy respectively. The behaviour of cp depends on
whether the destination is a file or a directory. If the destination is
a file, only one source file is allowed and cp makes a new file called
*destination* that has the same contents as the source file. If the
destination is a directory, many source files can be specified, each of
which will be copied into the destination directory. Section 2.6 will
discuss efficient specification of source files using wildcard
characters.

To copy entire directories (including their contents), use a *recursive*
copy:

     \$ cp -rd *source-directories destination-directory*\
 

-   mv (move/rename)

mv is used to rename files/directories and/or move them from one
directory into another. Exactly one source and one destination must be
specified:

    \$ mv *source destination*

If *destination* is an existing directory, the new name for *source*
(whether it be a file or a directory) will  be *destination/source*. If
*source* and *destination* are both files, *source* is renamed
*destination*. N.B.: if *destination* is an existing file it will be
destroyed and overwritten by *source* (you can use the -i option if you
would like to be asked for confirmation before a file is overwritten in
this way).\
 

-   rm (remove/delete)

    \$ rm *target-file(s)*

removes the specified files. Unlike other operating systems, it is
almost impossible to recover a deleted file unless you have a backup
(there is no recycle bin!) so use this command with care. If you would
like to be asked before files are deleted, use the -i option:

    \$ rm -i myfile![](LINUX_html_8d1f4a31.png){#Image44 align="bottom"
width="27" height="15" border="0"}\
    rm: remove \'myfile\'?

rm can also be used to delete directories (along with all of their
contents, including any subdirectories they contain). To do this, use
the -r option. To avoid rm from asking any questions or giving errors
(e.g. if the file doesn\'t exist) you used the -f (force) option.
Extreme care needs to be taken when using this option - consider what
would happen if a system administrator was trying to delete user will\'s
home directory and accidentally typed:

    \$ rm -rf / home/will![](LINUX_html_8d1f4a31.png){#Image45
align="bottom" width="27" height="15" border="0"}

(instead of rm -rf /home/will).\
 

-   cat (catenate/type)

    \$ cat *target-file(s)*

displays the contents of *target-file(s) * on the screen, one after the
other. You can also use it to create files from keyboard input as
follows (\> is the output redirection operator, which will be discussed
in the next chapter):

    \$ cat \> hello.txt![](LINUX_html_8d1f4a31.png){#Image46
align="bottom" width="27" height="15" border="0"}\
    hello world!![](LINUX_html_8d1f4a31.png){#Image47 align="bottom"
width="27" height="15" border="0"}\
    \[ctrl-d\]\
    \$ ls hello.txt![](LINUX_html_8d1f4a31.png){#Image48 align="bottom"
width="27" height="15" border="0"}\
    hello.txt\
    \$ cat hello.txt![](LINUX_html_8d1f4a31.png){#Image49 align="bottom"
width="27" height="15" border="0"}\
    hello world!\
    \$\
 

-   more and less (catenate with pause)

    \$ more *target-file(s)*

displays the contents of *target-file(s) * on the screen, pausing at the
end of each screenful and asking the user to press a key (useful for
long files). It also incorporates a searching facility (press \'/\' and
then type a phrase that you want to look for).

You can also use more to break up the output of commands that produce
more than one screenful of output as follows (\| is the pipe operator,
which will be discussed in the next chapter):

    \$ ls -l \| more![](LINUX_html_8d1f4a31.png){#Image50 align="bottom"
width="27" height="15" border="0"}

less is just like more, except that has a few extra features (such as
allowing users to scroll backwards and forwards through the displayed
file). less not a standard utility, however and may not be present on
all UNIX systems.

1.  5.  Hard and Soft (Symbolic) links

Direct (hard) and indirect (soft or symbolic) links from one file or
directory to another can be created using the ln command.

    \$ ln *filename linkname*

creates another directory entry for *filename* called *linkname* (i.e.
*linkname* is a hard link). Both directory entries appear identical (and
both now have a link count of 2). If either *filename* or *linkname* is
modified, the change will be reflected in the other file (since they are
in fact just two different directory entries pointing to the same file).

    \$ ln -s *filename linkname*

creates a shortcut called *linkname* (i.e. *linkname* is a soft link).
The shortcut appears as an entry with a special type (\'l\'):

    \$ ln -s hello.txt bye.txt![](LINUX_html_8d1f4a31.png){#Image51
align="bottom" width="27" height="15" border="0"}\
    \$ ls -l bye.txt![](LINUX_html_8d1f4a31.png){#Image52 align="bottom"
width="27" height="15" border="0"}\
    lrwxrwxrwx   1 will finance 13 bye.txt -\> hello.txt\
    \$

The link count of the source file remains unaffected. Notice that the
permission bits on a symbolic link are not used (always appearing as
rwxrwxrwx). Instead the permissions on the link are determined by the
permissions on the target (hello.txt in this case).

Note that you can create a symbolic link to a file that doesn\'t exist,
but not a hard link. Another difference between the two is that you can
create symbolic links across different physical disk devices or
partitions, but hard links are restricted to the same disk partition.
Finally, most current UNIX implementations do not allow hard links to
point to directories.

1.  6.  Specifying multiple Filenames

Multiple filenames can be specified using special pattern-matching
characters. The rules are:

-   \'?\' matches any single character in that position in the filename.

-   \'\*\' matches zero or more characters in the filename. A \'\*\' on
    its own will match all files. \'\*.\*\' matches all files with
    containing a \'.\'.

-   Characters enclosed in square brackets (\'\[\' and \'\]\') will
    match any filename that has one of those characters in that
    position.

-   A list of comma separated strings enclosed in curly braces (\"{\"
    and \"}\") will be expanded as a Cartesian product with the
    surrounding characters.

For example:

1.  ??? matches all three-character filenames.

2.  ?ell? matches any five-character filenames with \'ell\' in the
    middle.

3.  he\* matches any filename beginning with \'he\'.

4.  \[m-z\]\*\[a-l\] matches any filename that begins with a letter from
    \'m\' to \'z\' and ends in a letter from \'a\' to \'l\'.

5.  {/usr,}{/bin,/lib}/file expands to /usr/bin/file /usr/lib/file
    /bin/file and /lib/file.

Note that the UNIX shell performs these expansions (including any
filename matching) on a command\'s arguments *before* the command is
executed.

1.  7.  Quotes

As we have seen certain special characters (e.g. \'\*\', \'-\',\'{\'
etc.) are interpreted in a special way by the shell. In order to pass
arguments that use these characters to commands directly (i.e. without
filename expansion etc.), we need to use special quoting characters.
There are three levels of quoting that you can try:

1.  Try insert a \'\\\' in front of the special character.

2.  Use double quotes (\") around arguments to prevent most expansions.

3.  Use single forward quotes (\') around arguments to prevent all
    expansions.

There is a fourth type of quoting in UNIX. Single backward quotes (\`)
are used to pass the output of some command as an input argument to
another. For example:

    \$ hostname![](LINUX_html_8d1f4a31.png){#Image53 align="bottom"
width="27" height="15" border="0"}\
    rose\
    \$ echo this machine is called
\`hostname\`![](LINUX_html_8d1f4a31.png){#Image54 align="bottom"
width="27" height="15" border="0"}\
    this machine is called rose

Excersises:

Cviceni SSPGM 2. tyden

\

1\. Seznamte se a vyzkousejte utility id, adduser, newgrp

\

2\. Seznamte se a vyzkousejte prikaz chown, umask

\

3\. Nastavte umask tak, aby se defaultne tvorily

soubory rw-\|\-\--\|\-\--

adresare rwx\|\--x\|\--x

adresare rwx\|\--x\|\-\--

\

4\. Vypiste pocet souboru v adreari \$HOME

\

5\. Vypiste, kolikrat je prihlasen uziovatel \<v\>

\

6\. Co vypise

wc \*

wc \* \>pocty

wc \* \>pocty&

wc \* kdyz bude v adresari otevrena roura

\

7\. Analyzujte

cd cv2;l

cd cv2 & l

cd cv2 && l; cd

cd cv2 \|\| l; cd

\

8\. Analyzujte

(pwd;cd cv2;pwd);pwd

{ pwd;cd cv2;pwd;};pwd

\

9\. Vytvorte rouru (mknod) s nazvem napr. roura a

analyzujte napr.

man w \>roura &

cat (more) roura

1.  Try the following command sequence:

    -   cd

    -   pwd

    -   ls -al

    -   cd .

    -   pwd     (where did that get you?)

    -   cd ..

    -   pwd

    -   ls -al

    -   cd ..

    -   pwd

    -   ls -al

    -   cd ..

    -   pwd     (what happens now)

    -   cd /etc

    -   ls -al \| more

    -   cat passwd

    -   cd -

    -   pwd

2.  Continue to explore the filesystem tree using cd, ls, pwd and cat.
    Look in /bin, /usr/bin, /sbin, /tmp and /boot. What do you see?

3.  Explore /dev. Can you identify what devices are available? Which are
    character-oriented and which are block-oriented? Can you identify
    your tty (terminal) device (typing who am i might help); who is the
    owner of your tty (use ls -l)?

4.  Explore /proc. Display the contents of the files interrupts,
    devices, cpuinfo, meminfo and uptime using cat. Can you see why we
    say /proc is a pseudo-filesystem which allows access to kernel data
    structures?

5.  Change to the home directory of another user directly, using cd
    \~username.

6.  Change back into your home directory.

7.  Make subdirectories called work and play.

8.  Delete the subdirectory called work.

9.  Copy the file /etc/passwd into your home directory.

10. Move it into the subdirectory play.

11. Change into subdirectory play and create a symbolic link called
    terminal that points to your tty device. What happens if you try to
    make a hard link to the tty device?

12. What is the difference between listing the contents of directory
    play with ls -l and ls -L?

13. Create a file called hello.txt that contains the words \"hello
    world\". Can you use \"cp\" using \"terminal\" as the source file to
    achieve the same effect?

14. Copy hello.txt to terminal. What happens?

15. Imagine you were working on a system and someone accidentally
    deleted the ls command (/bin/ls). How could you get a list of the
    files in the current directory? Try it.

16. How would you create and then delete a file called \"\$SHELL\"? Try
    it.

17. How would you create and then delete a file that begins with the
    symbol #? Try it.

18. How would you create and then delete a file that begins with the
    symbol -? Try it.

19. What is the output of the command: echo {con,pre}{sent,fer}{s,ed}?
    Now, from your home directory, copy /etc/passwd and /etc/group into
    your home directory in one command given that you can only type /etc
    once.

20. Still in your home directory, copy the entire directory play to a
    directory called work, preserving the symbolic link.

21. Delete the work directory and its contents with one command. Accept
    no complaints or queries.

22. Change into a directory that does not belong to you and try to
    delete all the files (avoid /proc or /dev, just in case!)

23. Experiment with the options on the ls command. What do the d, i, R
    and F options do?

```{=html}
<!-- -->
```
3.  Lecture Three

\
\

1.  1.  Objectives

This lecture covers:

-   File and directory permissions in more detail and how these can be
    changed.

-   Ways to examine the contents of files.

-   How to find files when you don\'t know how their exact location.

-   Ways of searching files for text patterns.

-   How to sort files.

-   Tools for compressing files and making backups.

-   Accessing floppy disks and other removable media.

1.  2.  File and Directory Permissions

\
\

+--------+----------------+-------------------------------------------+
| [**P   | [**File*       | [**Directory**]{.underline}               |
| ermiss | *]{.underline} |                                           |
| ion**] |                |                                           |
| {.unde |                |                                           |
| rline} |                |                                           |
+--------+----------------+-------------------------------------------+
| read   | User can look  | User can list the files in the directory  |
|        | at the         |                                           |
|        | contents of    |                                           |
|        | the file       |                                           |
+--------+----------------+-------------------------------------------+
| write  | User can       | User can create new files and remove      |
|        | modify the     | existing files in the directory           |
|        | contents of    |                                           |
|        | the file       |                                           |
+--------+----------------+-------------------------------------------+
| e      | User can use   | User can change into the directory, but   |
| xecute | the filename   | cannot list the files unless (s)he has    |
|        | as a UNIX      | read permission. User can read files if   |
|        | command        | (s)he has read permission on them.        |
+--------+----------------+-------------------------------------------+

*Fig 3.1: Interpretation of permissions for files and directories*

As we have seen in the previous chapter, every file or directory on a
UNIX system has three types of permissions, describing what operations
can be performed on it by various categories of users. The permissions
are read (r), write (w) and execute (x), and the three categories of
users are user/owner (u), group (g) and others (o). Because files and
directories are different entities, the interpretation of the
permissions assigned to each differs slightly, as shown in Fig 3.1.

File and directory permissions can only be modified by their owners, or
by the superuser (root), by using the chmod system utility.

-   chmod (change \[file or directory\] mode)

    \$ chmod *options files*

chmod accepts options in two forms. Firstly, permissions may be
specified as a sequence of 3 octal digits (octal is like decimal except
that the digit range is 0 to 7 instead of 0 to 9). Each octal digit
represents the access permissions for the user/owner, group and others
respectively. The mappings of permissions onto their corresponding octal
digits is as follows:\
 

+-------------------------------------------------+--------------------+
| **\-\--**                                       | **0**              |
+-------------------------------------------------+--------------------+
| **\--x**                                        | **1**              |
+-------------------------------------------------+--------------------+
| **-w-**                                         | **2**              |
+-------------------------------------------------+--------------------+
| **-wx**                                         | **3**              |
+-------------------------------------------------+--------------------+
| **r\--**                                        | **4**              |
+-------------------------------------------------+--------------------+
| **r-x**                                         | **5**              |
+-------------------------------------------------+--------------------+
| **rw-**                                         | **6**              |
+-------------------------------------------------+--------------------+
| **rwx**                                         | **7**              |
+-------------------------------------------------+--------------------+

For example the command:

    \$ chmod 600 private.txt

sets the permissions on private.txt to rw\-\-\-\-\-\-- (i.e. only the
owner can read and write to the file).

Permissions may be specified symbolically, using the symbols u (user), g
(group), o (other), a (all), r (read), w (write), x (execute), + (add
permission), - (take away permission) and = (assign permission). For
example, the command:

    \$ chmod ug=rw,o-rw,a-x \*.txt

sets the permissions on all files ending in \*.txt to rw-rw\-\-\-- (i.e.
the owner and users in the file\'s group can read and write to the file,
while the general public do not have any sort of access).

chmod also supports a -R option which can be used to recursively modify
file permissions, e.g.

    \$ chmod -R go+r play

will grant group and other read rights to the directory play and all of
the files and directories within play.\
 

-   chgrp (change group)

    \$ chgrp *group files*

can be used to change the group that a file or directory belongs to. It
also supports a -R option.

1.  3.  Inspecting File Content

Besides cat there are several other useful utilities for investigating
the contents of files:

-   file *filename(s)*

file analyzes a file\'s contents for you and reports a high-level
description of what type of file it appears to be:

    \$ file myprog.c letter.txt
webpage.html![](LINUX_html_8d1f4a31.png){#Image55 align="bottom"
width="27" height="15" border="0"}\
    myprog.c:      C program text\
    letter.txt:    English text\
    webpage.html:  HTML document text

*file* can identify a wide range of files but sometimes gets
understandably confused (e.g. when trying to automatically detect the
difference between C++ and Java code).\
 

-   head, tail *filename*

head and tail display the first and last few lines in a file
respectively. You can specify the number of lines as an option, e.g.

    \$ tail -20 messages.txt![](LINUX_html_8d1f4a31.png){#Image56
align="bottom" width="27" height="15" border="0"}\
    \$ head -5 messages.txt![](LINUX_html_8d1f4a31.png){#Image57
align="bottom" width="27" height="15" border="0"}

tail includes a useful -f option that can be used to continuously
monitor the last few lines of a (possibly changing) file. This can be
used to monitor log files, for example:

    \$ tail -f /var/log/messages![](LINUX_html_8d1f4a31.png){#Image58
align="bottom" width="27" height="15" border="0"}

continuously outputs the latest additions to the system log file.\
 

-   objdump *options binaryfile*

objdump can be used to disassemble binary files - that is it can show
the machine language instructions which make up compiled application
programs and system utilities.\
 

-   od *options filename* (octal dump)

od can be used to displays the contents of a binary or text file in a
variety of formats, e.g.

    \$ cat hello.txt![](LINUX_html_8d1f4a31.png){#Image59 align="bottom"
width="27" height="15" border="0"}\
    hello world\
    \$ od -c hello.txt![](LINUX_html_8d1f4a31.png){#Image60
align="bottom" width="27" height="15" border="0"}\
    0000000  h  e  l  l  o     w  o  r  l  d \\n\
    0000014\
    \$ od -x hello.txt![](LINUX_html_8d1f4a31.png){#Image61
align="bottom" width="27" height="15" border="0"}\
    0000000 6865 6c6c 6f20 776f 726c 640a\
    0000014

There are also several other useful content inspectors that are
non-standard (in terms of availability on UNIX systems) but are
nevertheless in widespread use. They are summarised in Fig. 3.2.\
 

+-----------------------------+--------------------+------------------+
| [**File type**]{.underline} | [**Typical         | [**Content       |
|                             | extens             | viewe            |
|                             | ion**]{.underline} | r**]{.underline} |
+-----------------------------+--------------------+------------------+
| Portable Document Format    | .pdf               | acroread         |
+-----------------------------+--------------------+------------------+
| Postscript Document         | .ps                | ghostview        |
+-----------------------------+--------------------+------------------+
| DVI Document                | .dvi               | xdvi             |
+-----------------------------+--------------------+------------------+
| JPEG Image                  | .jpg               | xv               |
+-----------------------------+--------------------+------------------+
| GIF Image                   | .gif               | xv               |
+-----------------------------+--------------------+------------------+
| MPEG movie                  | .mpg               | mpeg_play        |
+-----------------------------+--------------------+------------------+
| WAV sound file              | .wav               | realplayer       |
+-----------------------------+--------------------+------------------+
| HTML document               | .html              | netscape         |
+-----------------------------+--------------------+------------------+

1.  4.  Finding Files

There are at least three ways to find files when you don\'t know their
exact location:

-   find

If you have a rough idea of the directory tree the file might be in (or
even if you don\'t and you\'re prepared to wait a while) you can use
find:

 \$ find *directory* -name *targetfile*
-print ![](LINUX_html_8d1f4a31.png){#Image62 align="bottom" width="27"
height="15" border="0"}

find will look for a file called *targetfile* in any part of the
directory tree rooted at *directory*. *targetfile* can include wildcard
characters. For example:

 \$ find /home -name \"\*.txt\" -print
2\>/dev/null![](LINUX_html_8d1f4a31.png){#Image63 align="bottom"
width="27" height="15" border="0"}

will search all user directories for any file ending in \".txt\" and
output any matching files (with a full absolute or relative path). Here
the quotes (\") are necessary to avoid filename expansion, while the
2\>/dev/null suppresses error messages (arising from errors such as not
being able to read the contents of directories for which the user does
not have the right permissions).

find can in fact do a lot more than just find files by name. It can find
files by type (e.g. -type f for files, -type d for directories), by
permissions (e.g. -perm o=r for all files and directories that can be
read by others), by size (-size) etc. You can also execute commands on
the files you find. For example,

 \$ find . -name \"\*.txt\" -exec wc -l \'{}\' \';\'

counts the number of lines in every text file in and below the current
directory. The \'{}\' is replaced by the name of each file found and the
\';\' ends the -exec clause.

For more information about find and its abilities, use man find and/or
info find.\
 

-   which (sometimes also called whence) *command*

If you can execute an application program or system utility by typing
its name at the shell prompt, you can use which to find out where it is
stored on disk. For example:

    \$ which ls![](LINUX_html_8d1f4a31.png){#Image64 align="bottom"
width="27" height="15" border="0"}\
    /bin/ls\
 

-   locate *string*

find can take a long time to execute if you are searching a large
filespace (e.g. searching from / downwards). The locate command provides
a much faster way of locating all files whose names match a particular
search string. For example:

    \$ locate \".txt\"![](LINUX_html_8d1f4a31.png){#Image65
align="bottom" width="27" height="15" border="0"}

will find all filenames in the filesystem that contain \".txt\" anywhere
in their full paths.

One disadvantage of locate is it stores all filenames on the system in
an index that is usually updated only once a day. This means locate will
not find files that have been created very recently. It may also report
filenames as being present even though the file has just been deleted.
Unlike find, locate cannot track down files on the basis of their
permissions, size and so on.

1.  5.  Finding Text in Files

-   grep (General Regular Expression Print)

    \$ grep *options pattern files*![](LINUX_html_8d1f4a31.png){#Image66
align="bottom" width="27" height="15" border="0"}

grep searches the named files (or standard input if no files are named)
for lines that match a given pattern. The default behaviour of grep is
to print out the matching lines. For example:

    \$ grep hello \*.txt![](LINUX_html_8d1f4a31.png){#Image67
align="bottom" width="27" height="15" border="0"}

searches all text files in the current directory for lines containing
\"hello\". Some of the more useful options that grep provides are:\
-c (print a count of the number of lines that match), -i (ignore case),
-v (print out the lines that don\'t match the pattern) and -n (printout
the line number before printing the matching line). So

    \$ grep -vi hello \*.txt![](LINUX_html_8d1f4a31.png){#Image68
align="bottom" width="27" height="15" border="0"}

searches all text files in the current directory for lines that do not
contain any form of the word hello (e.g. Hello, HELLO, or hELlO).

If you want to search all files in an entire directory tree for a
particular pattern, you can combine grep with find using backward single
quotes to pass the output from find into grep. So

    \$ grep hello \`find . -name \"\*.txt\"
-print\`![](LINUX_html_8d1f4a31.png){#Image69 align="bottom" width="27"
height="15" border="0"}

will search all text files in the directory tree rooted at the current
directory for lines containing the word \"hello\".

The patterns that grep uses are actually a special type of pattern known
as **regular expressions**. Just like arithemetic expressions, regular
expressions are made up of basic subexpressions combined by operators.

The most fundamental expression is a regular expression that matches a
single character.  Most characters, including all letters and digits,
are regular expressions that match themselves.  Any other character with
special meaning may be quoted by preceding it with a backslash (\\). A
list of characters enclosed by \'\[\' and \'\]\' matches any single
character in that list; if the first character of the list is the caret
\`\^\', then it matches any character not in the list. A range of
characters can be specified using a dash (-) between the first and last
items in the list. So \[0-9\] matches any digit and \[\^a-z\] matches
any character that is not a digit.

The caret \`\^\' and the dollar sign \`\$\' are special characters that\
match the beginning and end of a line respectively. The dot \'.\'
matches any character. So

    \$ grep \^..\[l-z\]\$ hello.txt![](LINUX_html_8d1f4a31.png){#Image70
align="bottom" width="27" height="15" border="0"}

matches any line in hello.txt that contains a three character sequence
that ends with a lowercase letter from l to z.

egrep (extended grep) is a variant of grep that supports more
sophisticated regular expressions. Here two regular expressions may be
joined by the operator \`\|\'; the resulting regular expression matches
any string matching either subexpression. Brackets \'(\' and \')\' may
be used for grouping regular expressions. In addition, a regular
expression may be followed by one of several repetition operators:

\`?\' means the preceding item is optional (matched at most once).\
\`\*\'  means the preceding item will be matched zero or more times.\
\`+\' means the preceding item will be matched one or more times.\
\`{N}\'   means the preceding item is matched exactly N times.\
\`{N,}\'  means the preceding item is matched N or more times.\
\`{N,M}\' means the preceding item is matched at least N times, but not
more than M times.

For example, if egrep was given the regular expression

    \'(\^\[0-9\]{1,5}\[a-zA-Z \]+\$)\|none\'

it would match any line that either:

-   -   begins with a number up to five digits long, followed by a
        sequence of one or more letters or spaces, or

    -   contains the word none

You can read more about regular expressions on the grep and egrep manual
pages.

Note that UNIX systems also usually support another grep variant called
fgrep (fixed grep) which simply looks for a fixed string inside a file
(but this facility is largely redundant).

1.  6.  Sorting Files

There are two facilities that are useful for sorting files in UNIX:

-   sort *filenames*

sort sorts lines contained in a group of files alphabetically (or if the
-n option is specified) numerically. The sorted output is displayed on
the screen, and may be stored in another file by redirecting the output.
So

    \$ sort input1.txt input2.txt \>
output.txt![](LINUX_html_8d1f4a31.png){#Image71 align="bottom"
width="27" height="15" border="0"}

outputs the sorted concentenation of files input1.txt and input2.txt to
the file output.txt.

-   uniq *filename*

uniq removes duplicate adjacent lines from a file. This facility is most
useful when combined with sort:

    \$ sort input.txt \| uniq \>
output.txt![](LINUX_html_8d1f4a31.png){#Image72 align="bottom"
width="27" height="15" border="0"}

1.  7.  File Compression and Backup

UNIX systems usually support a number of utilities for backing up and
compressing files. The most useful are:

-   tar (tape archiver)

tar backs up entire directories and files onto a tape device or (more
commonly) into a single disk file known as an archive. An archive is a
file that contains other files plus information about them, such as 
their filename, owner, timestamps, and access permissions. tar does not
perform any compression by default.

To create a disk file tar archive, use

    \$ tar -cvf *archivenamefilenames*

where *archivename* will usually have a .tar extension. Here the c
option means create, v means verbose (output filenames as they are
archived), and f means file.To list the contents of a tar archive, use

    \$ tar -tvf *archivename*

To restore files from a tar archive, use

    \$ tar -xvf *archivename*\
 

-   cpio

cpio is another facility for creating and reading archives. Unlike tar,
cpio doesn\'t automatically archive the contents of directories, so
it\'s common to combine cpio with find when creating an archive:

\$ find . -print -depth \| cpio -ov -Htar \> *archivename*

This will take all the files in the current directory and the\
directories below and place them in an archive called *archivename*.The
-depth option controls the order in which the filenames are produced and
is recommended to prevent problems with directory permissions when doing
a restore.The -o option creates the archive, the -v option prints the
names of the files archived as they are added and the -H option 
specifies an archive format type (in this case it creates a tar
archive). Another common archive type is crc, a portable format with a
checksum for error control.

To list the contents of a cpio archive, use

    \$ cpio -tv \< *archivename*

To restore files, use:

    \$ cpio -idv \< *archivename*

Here the -d option will create directories as necessary. To force cpio
to extract files  on top of files of the same name that already exist
(and have the same or later modification time), use the -u option.

-   compress, gzip

compress and gzip are utilities for compressing and decompressing
individual files (which may be or may not be archive files). To compress
files, use:

    \$ compress *filename*\
or\
    \$ gzip *filename*

In each case, *filename* will be deleted and replaced by a compressed
file called *filename*.Z or *filename*.gz. To reverse the compression
process, use:

    \$ compress -d filename\
or\
    \$ gzip -d filename

1.  8.  Handling Removeable Media

UNIX supports tools for accessing removable media such as CDROMs and
floppy disks.

-   mount, umount

The mount command serves to attach the filesystem found on some device
to the filesystem tree. Conversely, the umount command will detach it
again (it is very important to remember to do this when removing the
floppy or CDROM). The file /etc/fstab contains a list of devices and the
points at which they will be attached to the main filesystem:

\$ cat /etc/fstab![](LINUX_html_8d1f4a31.png){#Image73 align="bottom"
width="27" height="15" border="0"}\
/dev/fd0   /mnt/floppy  auto    rw,user,noauto  0 0\
/dev/hdc   /mnt/cdrom   iso9660 ro,user,noauto  0 0

In this case, the mount point for the floppy drive is /mnt/floppy and
the mount point for the CDROM is /mnt/cdrom. To access a floppy we can
use:

\$ mount /mnt/floppy![](LINUX_html_8d1f4a31.png){#Image74 align="bottom"
width="27" height="15" border="0"}\
\$ cd /mnt/floppy![](LINUX_html_8d1f4a31.png){#Image75 align="bottom"
width="27" height="15" border="0"}\
\$ ls (etc\...)

To force all changed data to be written back to the floppy and to detach
the floppy disk from the filesystem, we use:

\$ umount /mnt/floppy\
 

-   mtools

If they are installed, the (non-standard) mtools utilities provide a
convenient way of accessing DOS-formatted floppies without having to
mount and unmount filesystems. You can use DOS-type commands like \"mdir
a:\", \"mcopy a:\*.\* .\", \"mformat a:\", etc. (see the mtools manual
pages for more details).

Excersises:

Cv3.txt

Cviceni SSPGM 3. tyden

\

1\. Seznamte se s prikazy at, atq, date, atrm, nohup, nice a odzkousejte

\

2\. Archivujte a zpet obnovte z archivu kompletni podadresar cv3

\

3\. V adresari cv3 vytvorte

\

podadresar sdadr1 a zpristupnete jej cely pro cteni uzivatelum \<v\>

a napr. u\<n\> - vas kolega, kolegyne

\

podadresar sdadr2 a zpristupnet jej cely jako rw uzivatelum \<v\>

a napr. u\<n\> - vas kolega, kolegyne

\

podadresar sdadr3 a v nem zpristupnete jako rw soubor sds1 a to vsem

\

\
\

1.  Describe three different ways of setting the permissions on a file
    or directory to r\--r\--r\--. Create a file and see if this works.

2.  Team up with a partner. Copy /bin/sh to your home directory. Type
    \"chmod +s sh\". Check the permissions on sh in the directory
    listing. Now ask your partner to change into your home directory and
    run the program ./sh. Ask them to run the id command. What\'s
    happened?  Your partner can type exit to return to their shell.

3.  What would happen if the system administrator created a sh file in
    this way? Why is it sometimes necessary for a system administrator
    to use this feature using programs other than sh?

4.  Delete sh from your home directory (or at least to do a chmod -s
    sh).

5.  Modify the permissions on your home directory to make it completely
    private. Check that your partner can\'t access your directory. Now
    put the permissions back to how they were.

6.  Type umask 000 and then create a file called world.txt containing
    the words \"hello world\". Look at the permissions on the file.
    What\'s happened? Now type umask 022 and create a file called
    world2.txt. When might this feature be useful?

7.  Create a file called \"hello.txt\" in your home directory using the
    command cat -u \> hello.txt. Ask your partner to change into your
    home directory and run tail -f hello.txt. Now type several lines
    into hello.txt. What appears on your partner\'s screen?

8.  Use find to display the names of all files in the /home subdirectory
    tree. Can you do this without displaying errors for files you can\'t
    read?

9.  Use find to display the names of all files in the system that are
    bigger than 1MB.

10. Use find and file to display all files in the /home subdirectory
    tree, as well as a guess at what sort of a file they are. Do this in
    two different ways.

11. Use grep to isolate the line in /etc/passwd that contains your login
    details.

12. Use find and grep and sort to display a sorted list of all files in
    the /home subdirectory tree that contain the word hello somewhere
    inside them.

13. Use locate to find all filenames that contain the word emacs. Can
    you combine this with grep to avoid displaying all filenames
    containing the word lib?

14. Create a file containing some lines that you think would match the
    regular expression: (\^\[0-9\]{1,5}\[a-zA-z \]+\$)\|none and some
    lines that you think would not match. Use egrep to see if your
    intuition is correct.

15. Archive the contents of your home directory (including any
    subdirectories) using tar and cpio. Compress the tar archive with
    compress, and the cpio archive with gzip. Now extract their
    contents.

16. On Linux systems, the file /dev/urandom is a constantly generated
    random stream of characters. Can you use this file with od to
    printout a random decimal number?

17. Type mount (with no parameters) and try to interpret the output.

```{=html}
<!-- -->
```
4.  Lecture Four

\
\

1.  1.  Objectives

This lecture covers:

-   The concept of a process.

-   Passing output from one process as input to another using pipes.

-   Redirecting process input and output.

-   Controlling processes associated with the current shell.

-   Controlling other processes.

1.  2.  Processes

A **process** is a program in execution. Every time you invoke a system
utility or an application program from a shell, one or more \"child\"
processes are created by the shell in response to your command. All UNIX
processes are identified by a unique process identifier or PID. An
important process that is always present is the init process. This is
the first process to be created when a UNIX system starts up and usually
has a PID of 1. All other processes are said to be \"descendants\" of
init.

1.  3.  Pipes

The pipe (\'\|\') operator is used to create concurrently executing
processes that pass data directly to one another. It is useful for
combining system utilities to perform more complex functions. For
example:

    \$ cat hello.txt \| sort \|
uniq![](LINUX_html_8d1f4a31.png){#Image76 align="bottom" width="27"
height="15" border="0"}

creates three processes (corresponding to cat, sort and uniq) which
execute concurrently. As they execute, the output of the who process is
passed on to the sort process which is in turn passed on to the uniq
process. uniq displays its output on the screen (a sorted list of users
with duplicate lines removed). Similarly:

    \$ cat hello.txt \| grep \"dog\" \| grep -v
\"cat\"![](LINUX_html_8d1f4a31.png){#Image77 align="bottom" width="27"
height="15" border="0"}

finds all lines in hello.txt that contain the string \"dog\" but do not
contain the string \"cat\".

1.  4.  Redirecting input output

The output from programs is usually written to the screen, while their
input usually comes from the keyboard (if no file arguments are given).
In technical terms, we say that processes usually write to **standard
output** (the screen) and take their input from **standard input** (the
keyboard). There is in fact another output channel called **standard
error**, where processes write their error messages; by default error
messages are also sent to the screen.

To redirect standard output to a file instead of the screen, we use the
\> operator:

    \$ echo hello![](LINUX_html_8d1f4a31.png){#Image78 align="bottom"
width="27" height="15" border="0"}\
    hello\
    \$ echo hello \> output![](LINUX_html_8d1f4a31.png){#Image79
align="bottom" width="27" height="15" border="0"}\
    \$ cat output![](LINUX_html_8d1f4a31.png){#Image80 align="bottom"
width="27" height="15" border="0"}\
    hello

In this case, the contents of the file output will be destroyed if the
file already exists. If instead we want to append the output of the echo
command to the file, we can use the \>\> operator:

    \$ echo bye \>\> output![](LINUX_html_8d1f4a31.png){#Image81
align="bottom" width="27" height="15" border="0"}\
    \$ cat output![](LINUX_html_8d1f4a31.png){#Image82 align="bottom"
width="27" height="15" border="0"}\
    hello\
    bye

To capture standard error, prefix the \> operator with a 2 (in UNIX the
file numbers 0, 1 and 2 are assigned to standard input, standard output
and standard error respectively), e.g.:

    \$ cat nonexistent 2\>errors![](LINUX_html_8d1f4a31.png){#Image83
align="bottom" width="27" height="15" border="0"}\
    \$ cat errors![](LINUX_html_8d1f4a31.png){#Image84 align="bottom"
width="27" height="15" border="0"}\
    cat: nonexistent: No such file or directory\
    \$

You can redirect standard error and standard output to two different
files:

    \$ find . -print 1\>errors
2\>files![](LINUX_html_8d1f4a31.png){#Image85 align="bottom" width="27"
height="15" border="0"}

or to the same file:

    \$ find . -print 1\>output
2\>output![](LINUX_html_8d1f4a31.png){#Image86 align="bottom" width="27"
height="15" border="0"}\
or\
    \$ find . -print \>& output![](LINUX_html_8d1f4a31.png){#Image87
align="bottom" width="27" height="15" border="0"}

Standard input can also be redirected using the \< operator, so that
input is read from a file instead of the keyboard:

    \$ cat \< output![](LINUX_html_8d1f4a31.png){#Image88 align="bottom"
width="27" height="15" border="0"}\
    hello\
    bye

You can combine input redirection with output redirection, but be
careful not to use the same filename in both places. For example:

    \$ cat \< output \> output![](LINUX_html_8d1f4a31.png){#Image89
align="bottom" width="27" height="15" border="0"}

will destroy the contents of the file output. This is because the first
thing the shell does when it sees the \> operator is to create an empty
file ready for the output.

One last point to note is that we can pass standard output to system
utilities that require filenames as \"-\":

    \$ cat package.tar.gz \| gzip -d \| tar tvf -

Here the output of the gzip -d command is used as the input file to the
tar command.

1.  5.  Controlling processes associated with the current shell

Most shells provide sophisticated job control facilities that let you
control many running jobs (i.e. processes) at the same time. This is
useful if, for example, you are editing a text file and want ot
interrupt your editing to do something else. With job control, you can
suspend the editor, go back to the shell prompt, and start work on
something else. When you are finished, you can switch back to the editor
and continue as if you hadn\'t left.

Jobs can either be in the **foreground** or the **background**. There
can be only one job in the foreground at any time. The foreground job
has control of the shell with which you interact - it receives input
from the keyboard and sends output to the screen. Jobs in the background
do not receive input from the terminal, generally running along quietly
without the need for interaction (and drawing it to your attention if
they do).

The foreground job may be suspended, i.e. temporarily stopped, by
pressing the Ctrl-Z key. A suspended job can be made to continue running
in the foreground or background as needed by typing \"fg\" or \"bg\"
respectively. Note that suspending a job is very different from
interrupting a job (by pressing the interrupt key, usually Ctrl-C);
interrupted jobs are killed off permanently and cannot be resumed.

Background jobs can also be run directly from the command line, by
appending a \'&\' character to the command line. For example:

    \$ find / -print 1\>output 2\>errors
&![](LINUX_html_8d1f4a31.png){#Image90 align="bottom" width="27"
height="15" border="0"}\
    \[1\] 27501\
    \$

Here the \[1\] returned by the shell represents the job number of the
background process, and the 27501 is the PID of the process. To see a
list of all the jobs associated with the current shell, type jobs:

    \$ jobs![](LINUX_html_8d1f4a31.png){#Image91 align="bottom"
width="27" height="15" border="0"}\
    \[1\]+  Running  find / -print 1\>output 2\>errors &\
    \$

Note that if you have more than one job you can refer to the job as %n
where n is the job number. So for example fg %3 resumes job number 3 in
the foreground.

To find out the process ID\'s of the underlying processes associated
with the shell and its jobs, use ps (process show):

    \$ ps![](LINUX_html_8d1f4a31.png){#Image92 align="bottom" width="27"
height="15" border="0"}\
      PID TTY          TIME CMD\
    17717 pts/10   00:00:00 bash\
    27501 pts/10   00:00:01 find\
    27502 pts/10   00:00:00 ps

So here the PID of the shell (bash) is 17717, the PID of find is 27501
and the PID of ps is 27502.

To terminate a process or job abrubtly, use the kill command. kill
allows  jobs to referred to in two ways - by their PID or by their job
number. So\
    \$ kill %1\
or\
    \$ kill 27501

would terminate the find process. Actually kill only sends the process a
signal requesting it shutdown and exit gracefully (the SIGTERM signal),
so this may not always work. To force a process to terminate abruptly
(and with a higher probability of sucess), use a -9 option (the SIGKILL
signal):

     \$ kill -9 27501

kill can be used to send many other types of signals to running
processes. For example a -19 option (SIGSTOP) will suspend a running
process. To see a list of such signals, run kill -l.

1.  6.  Controlling other processes

You can also use ps to show all processes running on the machine (not
just the processes in your current shell):

    \$ ps -fae![](LINUX_html_8d1f4a31.png){#Image93 align="bottom"
width="27" height="15" border="0"} (or ps -aux on BSD machines)

 ps -aeH displays a full process hierarchy (including the init process).

Many UNIX versions have a system utility called top that provides an
interactive way to monitor system activity. Detailed statistics about
currently running processes are displayed and constantly refreshed.
Processes are displayed in order of CPU utilization. Useful keys in top
are:

    s - set update frequency                  k - kill process (by PID)\
    u - display processes of one user     q - quit

On some systems, the utility w is a non-interactive substitute for top.

One other useful process control utility that can be found on most UNIX
systems is the killall command. You can use killall to kill processes by
name instead of PID or job number. So another way to kill off our
background find process (along with any another find processes we are
running) would be:

    \$ killall find\
    \[1\]+  Terminated find / -print 1\>output 2\>errors\
    \$

Note that, for obvious security reasons, you can only kill processes
that belong to you (unless you are the superuser).

Excersises:

1.  Archive the contents of your home directory using tar. Compress the
    tar file with gzip. Now uncompress and unarchive the .tar.gz file
    using cat, tar and gzip on one command line.

2.  Use find to compile a list of all directories in the system,
    redirecting the output so that the list of directories ends up in a
    file called directories.txt and the list of error messages ends up
    in a file called errors.txt.

3.  Try the command sleep 5. What does this command do?

4.  Run the command in the background using &.

5.  Run sleep 15 in the foreground, suspend it with Ctrl-z and then put
    it into the background with bg. Type jobs. Type ps. Bring the job
    back into the foreground with fg.

6.  Run sleep 15 in the background using &, and then use kill to
    terminate the process by its job number. Repeat, except this time
    kill the process by specifying its PID.

7.  Run sleep 15 in the background using &, and then use kill to suspend
    the process. Use bg to continue running the process.

8.  Startup a number of sleep 60 processes in the background, and
    terminate them all at the same time using the killall command.

9.  Use ps, w and top to show all processes that are executing.

10. Use ps -aeH to display the process hierarchy. Look for the init
    process. See if you can identify important system daemons. Can you
    also identify your shell and its subprocesses?

11. Combine ps -fae with grep to show all processes that you are
    executing, with the exception of the ps -fae and grep commands.

12. Start a sleep 300 process running in the background. Log off the
    server, and log back in again. List all the processes that you are
    running. What happened to your sleep process? Now repeat, except
    this time start by running nohup sleep 300.

13. Multiple jobs can be issued from the same command line using the
    operators ;, && and \|\|. Try combining the commands cat
    nonexistent and echo hello using each of these operators. Reverse
    the order of the commands and try again. What are the rules about
    when the commands will be executed?

14. What does the xargs command do? Can you combine it with find and
    grep to find yet another way of searching all files in the /home
    subdirectory tree for the word hello?

15. What does the cut command do? Can you use it together with w to
    produce a list of login names and CPU times corresponding to each
    active process? Can you now (all on the same command line) use sort
    and head or tail to find the user whose process is using the most
    CPU?

```{=html}
<!-- -->
```
5.  Lecture Five

\
\

1.  1.  Objectives

This lecture introduces other useful UNIX system utilities and covers:

-   Connecting to remote machines.

-   Networking routing utilities.

-   Remote file transfer.

-   Other Internet-related utilities.

-   Facilities for user information and communication.

-   Printer control.

-   Email utilities.

-   Advanced text file processing with sed and awk.

-   Target directed compilation with make.

-   Version control with CVS.

-   C++ compilation facilities.

-   Manual pages.

1.  1.  Connecting to remote machines

-   telnet *machinename*

telnet provides an insecure mechanism for logging into remote machines.
It is insecure because all data (including your username and password)
is passed in unencrypted format over the network. For this reason,
telnet login access is disabled on most systems and where possible it
should be avoided in favour of secure alternatives such as ssh.

telnet is still a useful utility, however, because, by specifying
different port numbers, telnet can be used to connect to other services
offered by remote machines besides remote login (e.g. web pages, email,
etc.) and reveal the mechanisms behind how those services are offered.
For example,

\$ telnet www.doc.ic.ac.uk 80![](LINUX_html_8d1f4a31.png){#Image94
align="bottom" width="27" height="15" border="0"}\
Trying 146.169.1.10\...\
Connected to seagull.doc.ic.ac.uk (146.169.1.10).\
Escape character is \'\^\]\'.\
GET / HTTP/1.0![](LINUX_html_8d1f4a31.png){#Image95 align="bottom"
width="27" height="15" border="0"}\
![](LINUX_html_8d1f4a31.png){#Image96 align="bottom" width="27"
height="15" border="0"}\
HTTP/1.1 200 OK\
Date: Sun, 10 Dec 2000 21:06:34 GMT\
Server: Apache/1.3.14 (Unix)\
Last-Modified: Tue, 28 Nov 2000 16:09:20 GMT\
ETag: \"23dcfd-3806-3a23d8b0\"\
Accept-Ranges: bytes\
Content-Length: 14342\
Connection: close\
Content-Type: text/html

\<HTML\>\
\<HEAD\>\
   \<TITLE\>Department of Computing, Imperial College, London: Home
Page\</TITLE\>\
\</HEAD\>\
(etc)

Here www.doc.ic.ac.uk is the name of the remote machine (in this case
the web server for the Department of Computing at Imperial College in
London). Like most web servers, it offers web page services on port 80
through the daemon httpd (to see what other services are potentially
available on a machine, have a look at the file /etc/services; and to
see what services are actually active, see /etc/inetd.conf). By entering
a valid HTTP GET command (HTTP is the protocol used to serve web pages)
we obtain the top-level home page in HTML format. This is exactly the
same process that is used by a web browser to access web pages.\
 

-   rlogin, rsh

rlogin and rsh are insecure facilities for logging into remote machines
and for executing commands on remote machines respectively. Along with
telnet, they have been superseded by ssh.\
 

-   ssh *machinename* (secure shell)

ssh is a secure alternative for remote login and also for executing
commands in a remote machine. It is intended to replace rlogin and rsh,
and provide secure encrypted communications between two untrusted hosts
over an insecure network. X11 connections (i.e. graphics) can also be
forwarded over the secure channel (another advantage over telnet, rlogin
and rsh). ssh is not a standard system utility, although it is a de
facto standard. It can be obtained from
[[http://www.ssh.org](http://www.ssh.org/)]{.underline}. A good
introduction page giving more background and showing you how to set up
ssh is [<http://www.tac.nyc.ny.us/~kim/ssh/>]{.underline}.

ssh clients are also available for Windows machines (e.g. there is a
good ssh client called putty).

1.  3.  Network routing utilities

-   ping *machinename*

The ping utility is useful for checking round-trip response time between
machines. e.g.

    \$ ping www.doc.ic.ac.uk![](LINUX_html_8d1f4a31.png){#Image97
align="bottom" width="27" height="15" border="0"}

measures the reponse time delay between the current machine and the web
server at the Department of Computing at Imperial College. ping is also
useful to check whether a machine is still \"alive\" in some sense.\
 

-   traceroute *machinename*

traceroute shows the full path taken to reach a remote machine,
including the delay to each machine along the route. This is
particularly useful in tracking down the location of network problems.

1.  4.  Remote file transfer

-   ftp *machinename* (file transfer protocol)

ftp is an insecure way of transferring files between computers. When you
connect to a machine via ftp, you will be asked for your username and
password. If you have an account on the machine, you can use it, or you
can can often use the user \"ftp\" or \"anonymous\". Once logged in via
FTP, you can list files (dir), receive files (get and mget) and send
files (put and mput). (Unusually for UNIX) help will show you a list of
available commands. Particularly useful are binary (transfer files
preserving all 8 bits) and prompt n (do not confirm each file on
multiple file transfers). Type quit to leave ftp and return to the shell
prompt.\
 

-   scp *sourcefiles destination* (secure copy)

scp is a secure way of transferring files between computers. It works
just like the UNIX cp command except that the arguments can specify a
user and machine as well as files. For example:

   \$ scp will@rose.doc.ic.ac.uk:\~/hello.txt
**. **![](LINUX_html_8d1f4a31.png){#Image98 align="bottom" width="27"
height="15" border="0"}

will (subject to correct authentication) copy the file hello.txt from
the user account will on the remote machine rose.doc.ic.ac.uk into the
current directory (.) on the local machine.

1.  5.  Other Internet related utilities

-   netscape

netscape is a fully-fledged graphical web browser (like Internet
Explorer).\
 

-   lynx

lynx provides a way to browse the web on a text-only terminal.\
 

-   wget *URL*

wget provides a way to retrieve files from the web (using the HTTP
protocol).  wget is non-interactive, which means it can run in the
background, while the user is not  logged  in (unlike  most  web
browsers). The content retrieved by wget is stored as raw HTML text
(which can be viewed later using a web browser).

Note that netscape, lynx and wget are not standard UNIX system
utilities, but are frequently-installed application packages.

1.  6.  User Information and Communication

-   finger, who

finger and who show the list of users logged into a machine, the
terminal they are using, and the date they logged in on.

    \$ who![](LINUX_html_8d1f4a31.png){#Image99 align="bottom"
width="27" height="15" border="0"}\
    will      pts/2    Dec  5 19:41\
    \$\
 

-   write, talk

write is used by users on the same machine who want to talk to each
other. You should specify the user and (optionally) the terminal they
are on:

   \$ write will pts/2![](LINUX_html_8d1f4a31.png){#Image100
align="bottom" width="27" height="15" border="0"}\
   hello will![](LINUX_html_8d1f4a31.png){#Image101 align="bottom"
width="27" height="15" border="0"}

Lines are only transmitted when you
press ![](LINUX_html_8d1f4a31.png){#Image102 align="bottom" width="27"
height="15" border="0"} . To return to the shell prompt, press ctrl-d
(the UNIX end of file marker).

talk is a more sophisticated interactive chat client that can be used
between remote machines:

    \$ talk will@rose.doc.ic.ac.uk![](LINUX_html_8d1f4a31.png){#Image103
align="bottom" width="27" height="15" border="0"}

Unfortunately because of increasingly tight security restrictions, it is
increasingly unlikely that talk will work (this is because it requires a
special daemon called talkd to be running on the remote computer).
Sometimes an application called ytalk will succeed if talk fails.

1.  7.  Printer Control

-   -   lpr -P*printqueue filename*

lpr adds a document to a print queue, so that the document is printed
when the printer is available. Look at /etc/printcap to find out what
printers are available.\
 

-   -   lpq -P*printqueue*

lpq checks the status of the specified print queue. Each job will have
an associated job number.\
 

-   -   lprm -P*printqueue jobnumber*

lprm removes the given job from the specified print queue.

Note that lpr, lpq and lprm are BSD-style print management utilities. If
you are using a strict SYSV UNIX, you may need to use the SYSV
equivalents lp, lpstat and cancel.

1.  8.  Email utilities

-   mail

mail is the standard UNIX utility for sending and receiving email.

\$ mail![](LINUX_html_8d1f4a31.png){#Image104 align="bottom" width="27"
height="15" border="0"}\
Mail version 8.1 6/6/93.  Type ? for help.\
\"/var/spool/mail/will\": 2 messages 2 new\
1 jack@sprat.com      Mon Dec 11 10:37 \"Beanstalks\"\
2 bill@whitehouse.gov Mon Dec 11 11:00 \"Re: Monica\"\
&

Some of the more important commands (type ? for a full list) are given
below in Fig. 5.1. Here a *messagelist* is either a single message
specified by a number (e.g. 1) or a range (e.g. 1-2). The special
*messagelist* \* matches all messages.\
 

+------------------+---------------------------------------------------+
| ?                | help                                              |
+------------------+---------------------------------------------------+
| q                | quit, saving changes to mailbox                   |
+------------------+---------------------------------------------------+
| x                | quit, restoring mailbox to its original state     |
+------------------+---------------------------------------------------+
| t *messagelist*  | displays messages                                 |
+------------------+---------------------------------------------------+
| +/-              | show next/previous message                        |
+------------------+---------------------------------------------------+
| d *messagelist*  | deletes messages                                  |
+------------------+---------------------------------------------------+
| u *messagelist*  | undelete messages                                 |
+------------------+---------------------------------------------------+
| m *address*      | send a new email                                  |
+------------------+---------------------------------------------------+
| r *messagelist*  | reply to sender and other receipients             |
+------------------+---------------------------------------------------+
| R *messagelist*  | reply only to sender                              |
+------------------+---------------------------------------------------+

*Fig. 5.1: Common* mail *commands*

You can also use mail to send email directly from the command line. For
example:

\$ mail -s \"Hi\" wjk@doc.ic.ac.uk \<
message.txt![](LINUX_html_8d1f4a31.png){#Image105 align="bottom"
width="27" height="15" border="0"}\
\$

emails the contents of the (ASCII) file message.txt to the recipient
wjk@doc.ic.ac.uk with the subject \"Hi\".

-   mutt, elm, pine

mutt, elm and pine are more friendly (but non-standard) email interfaces
that you will probably prefer to use instead of mail. All have good
in-built help facilities.\
 

-   sendmail, exim

Email is actually sent using an Email Transfer Agent, which uses a
protocol called SMTP (Simple Mail Transfer Protocol). The two most
popular Email Transfer Agents are sendmail and exim. You can see how
these agents work by using telnet to connect to port 25 of any mail
server, for example:

\$ telnet mail.doc.ic.ac.uk 25![](LINUX_html_8d1f4a31.png){#Image106
align="bottom" width="27" height="15" border="0"}\
Trying 146.169.1.47\...\
Connected to diver.doc.ic.ac.uk (146.169.1.47).\
Escape character is \'\^\]\'.\
220 diver.doc.ic.ac.uk ESMTP Exim 3.16 #7\
HELP![](LINUX_html_8d1f4a31.png){#Image107 align="bottom" width="27"
height="15" border="0"}\
214-Commands supported:\
214-    HELO EHLO MAIL RCPT DATA AUTH\
214     NOOP QUIT RSET HELP\
MAIL FROM: alien@xfiles.com![](LINUX_html_8d1f4a31.png){#Image108
align="bottom" width="27" height="15" border="0"}\
250 \<alien@xfiles.com\> is syntactically correct\
RCPT TO: wjk@doc.ic.ac.uk![](LINUX_html_8d1f4a31.png){#Image109
align="bottom" width="27" height="15" border="0"}\
250 \<wjk@doc.ic.ac.uk\> verified\
DATA![](LINUX_html_8d1f4a31.png){#Image110 align="bottom" width="27"
height="15" border="0"}\
354 Enter message, ending with \".\" on a line\
Hi![](LINUX_html_8d1f4a31.png){#Image111 align="bottom" width="27"
height="15" border="0"}\
![](LINUX_html_8d1f4a31.png){#Image112 align="bottom" width="27"
height="15" border="0"}\
This is a message from an alien![](LINUX_html_8d1f4a31.png){#Image113
align="bottom" width="27" height="15" border="0"}\
![](LINUX_html_8d1f4a31.png){#Image114 align="bottom" width="27"
height="15" border="0"}\
.![](LINUX_html_8d1f4a31.png){#Image115 align="bottom" width="27"
height="15" border="0"}\
250 OK id=145UqB-0002t6-00\
QUIT![](LINUX_html_8d1f4a31.png){#Image116 align="bottom" width="27"
height="15" border="0"}\
221 diver.doc.ic.ac.uk closing connection\
Connection closed by foreign host.\
\$

This sends an email to wjk@doc.ic.ac.uk, apparently from
alien@xfiles.com. Email advertisers (aka spammers) often use this
technique to attempt to confuse recipients as to the true source of
messages. Fortunately exim and sendmail include extensive header
information when they forward email, including the IP address of the
computer from where the message was sent.

1.  9.  Advanced Text File Processing

-   sed (stream editor)

sed allows you to perform basic text transformations on an input stream
(i.e. a file or input from a pipeline). For example, you can delete
lines containing particular string of text, or you can substitute one
pattern for another wherever it occurs in a file. Although sed is a
mini-programming language all on its own and can execute entire scripts,
its full language is obscure and probably best forgotten (being based on
the old and esoteric UNIX line editor ed). sed is probably at its most
useful when used directly from the command line with simple parameters:

\$ sed \"s/*pattern1*/*pattern2*/\" *inputfile* \>
*outputfile*![](LINUX_html_8d1f4a31.png){#Image117 align="bottom"
width="27" height="15" border="0"}\
(substitutes *pattern2* for *pattern1* once per line)

\$ sed \"s/*pattern1*/*pattern2*/g\" *inputfile* \>
*outputfile*![](LINUX_html_8d1f4a31.png){#Image118 align="bottom"
width="27" height="15" border="0"}\
(substitutes *pattern2* for *pattern1* for every *pattern1* per line)

\$ sed \"/*pattern1*/d\" *inputfile* \>
*outputfile*![](LINUX_html_8d1f4a31.png){#Image119 align="bottom"
width="27" height="15" border="0"}\
(deletes all lines containing *pattern1*)

\$ sed \"y/*string1*/*string2*/\" *inputfile* \>
*outputfile*![](LINUX_html_8d1f4a31.png){#Image120 align="bottom"
width="27" height="15" border="0"}\
(substitutes characters in *string2* for those in *string1*)\
 

-   awk (Aho, Weinberger and Kernigan)

awk is useful for manipulating files that contain columns of data on a
line by line basis. Like sed, you can either pass awk statements
directly on the command line, or you can write a script file and let awk
read the commands from the script.

Say we have a file of cricket scores called cricket.dat containing
columns for player number, name, runs and the way in which they were
dismissed:

1 atherton     0   bowled\
2 hussain     20   caught\
3 stewart     47   stumped\
4 thorpe      33   lbw\
5 gough        6   run-out

To print out only the first and third columns we can say:

\$ awk \'{ print \$1 \" \" \$3 }\'
cricket.dat![](LINUX_html_8d1f4a31.png){#Image121 align="bottom"
width="27" height="15" border="0"}\
atherton 0\
hussain 20\
stewart 47\
thorpe 33\
gough 6\
\$

Here \$*n* stands for the *n*th field or column of each line in the data
file. \$0 can be used to denote the whole line.

We can do much more with awk. For example, we can write a script
cricket.awk to calculate the team\'s batting average and to check if
Mike Atherton got another duck:

\$ cat \> cricket.awk![](LINUX_html_8d1f4a31.png){#Image122
align="bottom" width="27" height="15" border="0"}\
BEGIN { players = 0; runs = 0 }\
{ players++; runs +=\$3 }\
/atherton/ { if (runs==0) print \"atherton duck!\" }\
END { print \"the batting average is \" runs/players }\
(ctrl-d)\
\$ awk -f cricket.awk cricket.dat![](LINUX_html_8d1f4a31.png){#Image123
align="bottom" width="27" height="15" border="0"}\
atherton duck!\
the batting average is 21.2\
\$

The BEGIN clause is executed once at the start of the script, the main
clause once for every line, the /atherton/ clause only if the word
atherton occurs in the line and the END clause once at the end of the
script.

awk can do a lot more. See the manual pages for details (type man awk).

1.  10. Target Directed Compilation

-   make

make is a utility which can determine automatically which pieces of a
large program need to be recompiled, and issue the commands  to
recompile them. To use make, you need to create a file called Makefile
or makefile that describes  the relationships among files in your
program, and the states the commands for updating each file.

Here is an example of a simple makefile:

scores.out: cricket.awk cricket.dat\
\[TAB\]awk -f cricket.awk cricket.dat \> scores.out

Here \[TAB\] indicates the TAB key. The interpretation of this makefile
is as follows:

-   -   scores.out is the target of the compilation

    -   scores.out depends on cricket.awk and cricket.dat

    -   if either cricket.awk or cricket.dat have been modified since
        scores.out was last modified or if scores.out does not exist,
        update scores.out by executing the command:\
        awk -f cricket.awk cricket.dat \> scores.out

make is invoked simply by typing

\$ make![](LINUX_html_8d1f4a31.png){#Image124 align="bottom" width="27"
height="15" border="0"}\
awk -f cricket.awk cricket.dat \> scores.out\
\$

Since scores.out did not exist, make executed the commands to create it.
If we now invoke make again, nothing happens:

\$ make![](LINUX_html_8d1f4a31.png){#Image125 align="bottom" width="27"
height="15" border="0"}\
make: \`scores.out\' is up to date.\
\$

But if we modify cricket.dat and then run make again, scores.out will be
updated:

\$ touch cricket.dat![](LINUX_html_8d1f4a31.png){#Image126
align="bottom" width="27" height="15" border="0"} (touch simulates file
modification)\
\$ make![](LINUX_html_8d1f4a31.png){#Image127 align="bottom" width="27"
height="15" border="0"}\
awk -f cricket.awk cricket.dat \> scores.out\
\$

make is mostly used when compiling large C, C++ or Java programs, but
can (as we have seen) be used to automatically and intelligently produce
a target file of any kind.

1.  11. Version Control with CVS

-   cvs (Concurrent Versioning System)

cvs is a source code control system often used on large programming
projects to control the concurrent editing of source files by multiple
authors. It keeps old versions of files and maintains a log of when, and
why changes occurred, and who made them.

cvs keeps a single copy of the master sources. This copy is called  the
source \`\`repository\'\'; it contains all the information to permit
extracting previous software releases at any time based on either a
symbolic revision tag, or a date in the past.

cvs has a large number of commands (type info cvs for a full cvs
tutorial, including how to set up a repository from scratch or from
existing code). The most useful commands are:\
 

-   -   cvs checkout *modules\
        \
        *This gives you a private copy of source code that you can work
        on with without interfering with others.

    -   cvs update\
        \
        This updates the code you have checked out, to reflect any
        changes that have subsequently been made by other developers.

    -   cvs add *files\
        \
        *You can use this to add new files into a repository that you
        have checked-out. Does not actually affect the repository until
        a \"cvs commit\" is performed.

    -   cvs remove *files*\
        \
        Removes files from a checked-out repository. Doesn\'t affect the
        repository until a \"cvs commit\" is performed.

    -   cvs commit *files\
        \
        *This command publishes your changes to other developers by
        updating the source code in the central repository.

1.  1.  Compilation C/C++ utilities

-   cc, gcc, CC, g++

UNIX installations usually come with a C and/or C++ compiler. The C
compiler is usually called cc or gcc, and the C++ compiler is usually
called CC or g++. Most large C or C++ programs will come with a makefile
and will support the configure utility, so that compiling and installing
a package is often as simple as:

\$ ./configure![](LINUX_html_8d1f4a31.png){#Image128 align="bottom"
width="27" height="15" border="0"}\
\$ make![](LINUX_html_8d1f4a31.png){#Image129 align="bottom" width="27"
height="15" border="0"}\
\$ make install![](LINUX_html_8d1f4a31.png){#Image130 align="bottom"
width="27" height="15" border="0"}

However, there is nothing to prevent you from writing and compiling a
simple C program yourself:

\$ cat \> hello.c![](LINUX_html_8d1f4a31.png){#Image131 align="bottom"
width="27" height="15" border="0"}\
#include \<stdio.h\>![](LINUX_html_8d1f4a31.png){#Image132
align="bottom" width="27" height="15" border="0"}\
int main() {![](LINUX_html_8d1f4a31.png){#Image133 align="bottom"
width="27" height="15" border="0"}\
  printf(\"hello world!\\n\");![](LINUX_html_8d1f4a31.png){#Image134
align="bottom" width="27" height="15" border="0"}\
  return 0;![](LINUX_html_8d1f4a31.png){#Image135 align="bottom"
width="27" height="15" border="0"}\
}![](LINUX_html_8d1f4a31.png){#Image136 align="bottom" width="27"
height="15" border="0"}\
(ctrl-d)\
\$ cc hello.c -o hello![](LINUX_html_8d1f4a31.png){#Image137
align="bottom" width="27" height="15" border="0"}\
\$ ./hello![](LINUX_html_8d1f4a31.png){#Image138 align="bottom"
width="27" height="15" border="0"}\
hello world!\
\$

Here the C compiler (cc) takes as input the C source file hello.c and
produces as output an executable program called hello. The program hello
may then be executed (the ./ tells the shell to look in the current
directory to find the hello program).

1.  13. Manula Pages

-   man

More information is available on most UNIX commands is available via the
online manual pages, which are accessible through the man command. The
online documentation is in fact divided into sections. Traditionally,
they are

1 User-level commands\
2 System calls\
3 Library functions\
4 Devices and device drivers\
5 File formats\
6 Games\
7 Various miscellaneous stuff - macro packages etc.\
8 System maintenance and operation commands

Sometimes man gives you a manual page from the wrong section. For
example, say you were writing a program and you needed to use the rmdir
system call. man rmdir gives you the manual page for the user-level
command rmdir. To force man to look in Section 2 of the manual instead,
type man 2 rmdir (orman -s2 rmdir on some systems).

man can also find manual pages which mention a particular topic. For
example, man -k postscript should produce a list of utilities that can
produce and manipulate postscript files.\
 

-   info

info is an interactive, somewhat more friendly and helpful alternative
to man. It may not be installed on all systems, however.

Excersises:

1.  Use telnet to request a web page from the web server
    www.doc.ic.ac.uk by connecting to port 80, as shown in the notes.

2.  Use ping to find the round-trip delay to www.altavista.com.

3.  Use traceroute to see the network route taken to www.altavista.com
    (which is in the USA). Can you tell which cities your network
    traffic passes through?

4.  Use ftp to connect to the FTP site sunsite.doc.ic.ac.uk. Obtain the
    latest version of the package units (in the form of a .tar.gz
    file) from the directory packages/gnu/units. Decompress and
    unarchive the .tar.gz file. Type configure and then make. Run the
    executable program that is produced as \"./units -f units.dat\".
    What does the program do? If you were the system administrator, what
    would you have to do to install the package for everyone to use?

5.  Use wget to get a copy of the web page
    http://www.doc.ic.ac.uk/index.html. Have a look at the contents of
    the file. Can you use sed to strip out the HTML tags (text enclosed
    in \< and \>) to leave you with just plain text?

6.  Use finger or who to get a list of users on the machine.

7.  Use write to send them a message. To stop people from sending you
    messages, type \"mesg n\". To reenable messages, type \"mesg y\".

8.  Try use talk to send a message to someone (N.B. this may not work).

9.  List all your processes, using sed to substitute \"me\" for your
    username.

10. Use who, awk, sort and uniq to print out a sorted list of the logins
    of active users.

11. Use awk on /etc/passwd to produce a list of users and their login
    shells.

12. Write an awk script that prints out all lines in a file except for
    the first two.

13. Modify the **awk** script in the notes so that it doesn\'t increase
    the number of players used to calculate the average if the manner of
    dismissal is \"not-out\".

14. Create a file called hello.c containing the simple \"hello world\"
    program in the notes. Create an appropriate makefile for compiling
    it. Run make.

15. Use man -k to find a suitable utility for viewing postscript files.

```{=html}
<!-- -->
```
6.  Lecture Six

    1.  Objectives

This lecture introduces the two most popular UNIX editors: vi and emacs.
For each editor, it covers:

-   Basic text input and navigation.

-   Moving and copying text.

-   Searching for and replacing text.

-   Other useful commands.

-   A quick-reference chart.

6.  2.  1.  Introduction to vi

vi (pronounced \"vee-eye\", short for visual, or perhaps vile) is a
display-oriented text editor based on an underlying line editor called
ex. Although beginners usually find vi somewhat awkward to use, it is
useful to learn because it is universally available (being supplied with
all UNIX systems). It also uses standard alphanumeric keys for commands,
so it can be used on almost any terminal or workstation without having
to worry about unusual keyboard mappings. System administrators like
users to use vi because it uses very few system resources.

To start vi, enter:

    \$ vi *filename*![](LINUX_html_8d1f4a31.png){#Image139
align="bottom" width="27" height="15" border="0"}

where *filename* is the name of the file you want to edit. If the file
doesn\'t exist, vi will create it for you.

6.  2.  2.  Basic Text Input and Navigation in vi

The main feature that makes vi unique as an editor is its mode-based
operation. vi has two modes: command mode and input mode. In command
mode, characters you type perform actions (e.g. moving the cursor,
cutting or copying text, etc.) In input mode, characters you type are
inserted or overwrite existing text.

When you begin vi, it is in command mode. To put vi into input mode,
press i (insert). You can then type text which is inserted at the
current cursor location; you can correct mistakes with the backspace key
as you type.To get back into command mode, press ESC (the escape key).
Another way of inserting text, especially useful when you are at the end
of a line is to press a (append).

In command mode, you are able to move the cursor around your document.
h, j, k and l move the cursor left, down, up and right respectively (if
you are lucky the arrow keys may also work). Other useful keys are \^
and \$ which move you to the beginning and end of a line respectively. w
skips to the beginning of the next word and b skips back to the
beginning of the previous word. To go right to the top of the document,
press 1 and then G. To go the bottom of the document, press G. To skip
forward a page, press \^F, and to go back a page, press \^B. To go to a
particular line number, type the line number and press G, e.g. 55G takes
you to line 55.

To delete text, move the cursor over the first character of the group
you want to delete and make sure you are in command mode. Press x to
delete the current character, dw to delete the next word, d4w to delete
the next 4 words, dd to delete the next line, 4dd to delete the next 4
lines, d\$ to delete to the end of the line or even dG to delete to the
end of the document. If you accidentally delete too much, pressing u
will undo the last change.

Occasionally you will want to join two lines together. Press J to do
this (trying to press backspace on the beginning of the second line does
not have the intuitive effect!)

6.  2.  3.  Moving and Copying Text in vi

vi uses buffers to store text that is deleted. There are nine numbered
buffers (1-9) as well as the undo buffer. Usually buffer 1 contains the
most recent deletion, buffer 2 the next recent, etc.

To cut and paste in vi, delete the text (using e.g. 5dd to delete 5
lines). Then move to the line where you want the text to appear and
press p. If you delete something else before you paste, you can still
retrieve the delete text by pasting the contents of the delete buffers.
You can do this by typing \"1p, \"2p, etc.

To copy and paste, \"yank\" the text (using e.g. 5yy to copy 5 lines).
Then move to the line where you want the text to appear and press p.

6.  2.  4.  Searching and Replacing Text in vi

In command mode, you can search for text by specifying regular
expressions. To search forward, type / and then a regular expression and
press ![](LINUX_html_8d1f4a31.png){#Image140 align="bottom" width="27"
height="15" border="0"} . To search backwards, begin with a ? instead of
a /. To find the next text that matches your regular expression press n.

To search and replace all occurences of pattern1 with pattern2, type
:%s/*pattern1*/*pattern2*/g![](LINUX_html_8d1f4a31.png){#Image141
align="bottom" width="27" height="15" border="0"} . To be asked to
confirm each replacement, add a c to this substitution command. Instead
of the % you can also give a range of lines (e.g. 1,17) over which you
want the substitution to apply.

6.  2.  5.  Other Useful vi Commands

Programmers might like the :set
number![](LINUX_html_8d1f4a31.png){#Image142 align="bottom" width="27"
height="15" border="0"} command which displays line numbers (:set
nonumber turns them off).

To save a file, type :w![](LINUX_html_8d1f4a31.png){#Image143
align="bottom" width="27" height="15" border="0"} . To save and quit,
type :wq![](LINUX_html_8d1f4a31.png){#Image144 align="bottom" width="27"
height="15" border="0"} or press ZZ. To force a quit without saving type
:q!![](LINUX_html_8d1f4a31.png){#Image145 align="bottom" width="27"
height="15" border="0"} .

To start editing another file, type :e
filename![](LINUX_html_8d1f4a31.png){#Image146 align="bottom" width="27"
height="15" border="0"} .

To execute shell commands from within vi, and then return to vi
afterwards, type :!*shellcommand![](LINUX_html_8d1f4a31.png){#Image147
align="bottom" width="27" height="15" border="0"}* . You can use the
letter % as a substitute for the name of the file that you are editing
(so :!echo % prints the name of the current file).

. repeats the last command.

6.  2.  6.  Quick References for vi

**Inserting and typing text:**\
i          insert text (and enter input mode)\
\$a         append text (to end of line)\
ESC        re-enter command mode\
J          join lines

**Cursor movement:**\
h          left\
j          down\
k          up\
l          right\
\^          beginning of line\
\$          end of line\
1 G        top of document\
G          end of document\
\<n\> G      go to line \<n\>\
\^F         page forward\
\^B         page backward\
w          word forwards\
b          word backwards

**Deleting and moving text:**\
Backspace  delete character before cursor\
           (only works in insert mode)\
x          delete character under cursor\
dw         delete word\
dd         delete line (restore with p or P)\
\<n\> dd     delete n lines\
d\$         delete to end of line\
dG         delete to end of file\
yy         yank/copy line (restore with p or P)\
\<n\> yy     yank/copy \<n\> lines

**Search and replace:**\
%s/\<search string\>/\<replace
string\>/g![](LINUX_html_8d1f4a31.png){#Image148 align="bottom"
width="27" height="15" border="0"}

**Miscellaneous:**\
u          undo\
:w         save file\
:wq        save file and quit\
ZZ         save file and quit\
:q!        quit without saving

6.3.1 Introduction to emacs

emacs is a popular editor for UNIX, Windows and Macintosh systems.
Unlike vi, it is not a standard UNIX system utility, but is available
from the Free Software Foundation.

An emacs zealot will tell you how emacs provides advanced facilities
that go beyond simple insertion and deletion of text: you can view two
are more files at the same time, compile and debug programs in almost
any programming language, typeset documents, run shell commands, read
manual pages, email and news and even browse the web from inside emacs.
emacs is also very flexible - you can redefine keystrokes and commands
easily, and (for the more ambitious) you can even write Lisp programs to
add new commands and display modes to emacs, since emacs has its own
Lisp interpreter. In fact most of the editing commands of Emacs are
written in Lisp already; the few exceptions are written in C for
efficiency. However, users do not need to know how to program Lisp to
use emacs (while it is true that only a programmer can write a
substantial extension to emacs, it is easy for anyone to use it
afterwards).

Critics of emacs point out that it uses a relatively large amount of
system resources compared to vi and that it has quite a complicated
command structure (joking that emacs stands for
Escape-Meta-Alt-Control-Shift).

In practice most users tend to use both editors - vi to quickly edit
short scripts and programs and emacs for more complex jobs that require
reference to more than one file simultaneously.

On UNIX systems, emacs can run in graphical mode under the X Windows
system, in which case some helpful menus and mouse button command
mappings are provided. However, most of its facilities are also
available on a text terminal.

To start emacs, enter:

    \$ emacs *filename*![](LINUX_html_8d1f4a31.png){#Image149
align="bottom" width="27" height="15" border="0"}

where *filename* is the name of the file you want to edit. If the file
doesn\'t exist, emacs will create it for you.

6.3.2 Basic Text Input and Navigation in emacs

Text input and navigation in emacs is mostly a matter of using the arrow
keys to position the cursor and typing some text. Issuing more complex
emacs commands usually involves pressing the Ctrl key (sometimes also
labelled Control or Ctl) or the Meta key (sometimes also labelled Alt).
emacs commands are usually described in this way:

-   C-\<chr\>  means hold the Ctrl key while typing the character
    \<chr\>. Thus, C-f would be: hold the Ctrl key and type f.

-   M-\<chr\>  means hold the Meta or Alt key down while typing \<chr\>.
    If there is no Meta or Alt key, instead press and release the ESC
    key and then type \<chr\>.

One initially annoying feature of emacs is that its help facility has
been installed on C-h (Ctrl h). Unfortunately this is also the code for
the backspace key on most systems. You can, however, easily make the key
work as expected by creating a .emacs file (a file always read on start
up) in your home directory containing the following line:

(global-set-key \"\\C-h\" \'backward-delete-char-untabify)

[[Here](http://www.doc.ic.ac.uk/~wjk/UnixIntro/.emacs)]{.underline} is a
.emacs file that contains this line as well as several other useful
facilities (see Section 6.3.6).

To access the help system you can still type M-x
help![](LINUX_html_8d1f4a31.png){#Image150 align="bottom" width="27"
height="15" border="0"} or (for a comprehensive tutorial) M-x
help-with-tutorial![](LINUX_html_8d1f4a31.png){#Image151 align="bottom"
width="27" height="15" border="0"} .

Useful navigation commands are C-a (beginning of line), C-e (end of
line), C-v (forward page), M-v (backwards page), M-\< (beginning of
document) and M-\> (end of document). C-d will delete the character
under the cursor, while C-k will delete to the end of the line. Text
deleted with C-k is placed in a buffer which can be \"yanked\" back
later with C-y.

6.  3.  3.  Moving and Copying Text in emacs

The easiest way to cut and paste text is to go to the start of the text
and press C-k until you have deleted the text you want. Then move to the
spot where you want to paste the text and press C-y to restore the text.
If you make a mistake, C-u will undo the change (emacs supports several
levels of undo). Another way to delete a chunk of text is to go the
start of the text and press C-SPC (SPC is the spacebar; this sets a
mark). Then go to the end of the text you wish to delete and press C-w.
Restore the text in the right spot with C-y.

To copy and paste, delete the target text as above, and then use C-y
twice (once to restore the original text, and once to create the copy).

6.  3.  3.  Searching for and Replacing Text in emacs

To search forwards and backwards incrementally, use C-s and C-r
respectively. Pressing C-s or C-r again will repeat the operation. When
you have found the text you want,
press ![](LINUX_html_8d1f4a31.png){#Image152 align="bottom" width="27"
height="15" border="0"} , or press C-g to cancel the operation and
return your cursor to the position where the search started.

To replace a string, type M-x
replace-string![](LINUX_html_8d1f4a31.png){#Image153 align="bottom"
width="27" height="15" border="0"} (you may want to modify your .emacs
file so that this command is on C-x r). M-% performs a query search and
replace.

6.  3.  3.  Othet Useful emacs Commands

Pressing C-g will cancel any emacs command in progress.

To save a file, press C-x C-s. To start editing a new file, press C-x
C-f.

To bring up two windows (or \"buffers\" in emacs-speak), press C-x 2
(C-x 1 gets you back to 1). C-x o switches between buffers on the same
screen. C-x b lets you switch between all active buffers, whether you
can see them or not. C-x C-k deletes a buffer that you are finished
with.

M-x shell![](LINUX_html_8d1f4a31.png){#Image154 align="bottom"
width="27" height="15" border="0"} brings up a UNIX shell inside a
buffer (you may like to put this on C-x C-u). M-x
goto-line![](LINUX_html_8d1f4a31.png){#Image155 align="bottom"
width="27" height="15" border="0"} skips to a particular line (you may
like to put this on C-x g). M-x
compile![](LINUX_html_8d1f4a31.png){#Image156 align="bottom" width="27"
height="15" border="0"} will attempt to compile a program (using the
make utility or some other command that you can specify). If you are
doing a lot of programming you will probably want to put this on a key
like C-x c.

M-q will reformat a paragraph.

C-x C-c quits emacs.

6.  3.  3.  Quick References for emacs

**Cursor movement:**\
C-a           beginning of line\
C-e           end of line\
C-\<           top of document\
C-\>           end of document\
M-x goto-line Go to line\
C-v           page forward\
M-v           page backward

**Deleting and moving text:**\
Backspace     delete character before cursor\
              (subject to modification of .emacs)\
C-d           delete character under cursor\
M-d           delete word\
C-k           delete to end of line(s)\
              (restore with C-y)\
C-SPC         set mark\
C-w           delete from mark to cursor\
              (restore with C-y)

**Search and replace:**\
C-s           incremental search forward\
C-r           incremental search backward\
C-%           query replace\
M-x replace-string![](LINUX_html_8d1f4a31.png){#Image157 align="bottom"
width="27" height="15" border="0"}
\<searchstr\>![](LINUX_html_8d1f4a31.png){#Image158 align="bottom"
width="27" height="15" border="0"}
\<replstr\>![](LINUX_html_8d1f4a31.png){#Image159 align="bottom"
width="27" height="15" border="0"}

**Miscellaneous:**\
C-x u         undo\
C-x C-s       save file\
C-x C-f       find file\
C-x 2         2 windows\
C-x 1         1 window\
C-x o         switch between windows\
C-x b         switch buffers\
M-q           reformat paragraph\
C-x C-c       quit

**Useful customisable keys (configured using the provided**
[[**.emacs**](http://www.doc.ic.ac.uk/~wjk/UnixIntro/.emacs)]{.underline}
**file):**\
C-x g         goto line\
C-x c         compile program (useful with C-x 2)\
C-x C-u       open Unix shell (useful with C-x 2)\
C-x a         repeat command\
C-x m         manual entry

6.  3.  Other Unix editors

There are many other editors for UNIX systems. Two popular alternatives
to vi and emacs are nedit and pico.

Excersise:

1.  Copy the file
    [[mole.txt]{.underline}](http://www.doc.ic.ac.uk/~wjk/UnixIntro/mole.txt)
    into your home directory (press shift and the left mouse button to
    download the file using Netscape).

2.  Edit your copy of the document using vi.

3.  Go to the end of the document and type in the following paragraph:\
    \
    Joined the library. Got Care of the Skin, Origin of the Species, and
    a book by a woman my mother is always going on about. It is called
    Pride and Prejudice, by a woman called Jane Austen. I could tell the
    librarian was impressed. Perhaps she is an intellectual like me. She
    didn\'t look at my spot, so perhaps it is getting smaller.

4.  Correct  the three  spelling errors in the first three lines of the
    first paragraph (one  error per  line) and  remove the extra
    \"Geography\" in the 3rd line of the first paragraph.

5.  Add the words \"About time!\" to the end of the second paragraph.

6.  Delete  the sentence  \"Time flies like an arrow but  fruit flies
    like a banana\" and re-form the paragraph.

7.  Replace all occurrences of \"is\" with \"was\".

8.  Swap the two paragraphs.

9.  Save the file and quit.

10. Repeat the exercise with emacs. Which did you find easier?

11. Can you write a simple C program (say the hello world program) and
    makefile, compile and run it - all from inside emacs?

12. If you\'d like an indepth vi tutorial try running \"vimtutor\". For
    an indepth emacs tutorial, type M-x help-with-tutorial from inside
    emacs.

```{=html}
<!-- -->
```
7.  Lecture Seven

    1.  Objectives

This lecture covers basic system administration concepts and tasks,
namely:

-   The superuser root.

-   Shutdown and system start-up.

-   Adding users.

-   Controlling user groups.

-   Reconfiguring and recompiling the Linux kernel.

-   Cron jobs.

-   Keeping essential processes alive.

Note that you will not be given administrator access on the lab
machines. However, you might like to try some basic administration tasks
on your home PC.

1.  2.  The Superuser Root

The superuser is a privileged user who has unrestricted access to all
commands and files on a system regardless of their permissions. The
superuser\'s login is usually root. Access to the root account is
restricted by a password (the root password). Because the root account
has huge potential for destruction, the root password should be chosen
carefully, only given to those who need it, and changed regularly.

One way to become root is to log in as usual using the username root and
the root password (usually security measures are in place so that this
is only possible if you are using a \"secure\" console and not
connecting over a network). Using root as your default login in this way
is not recommended, however, because normal safeguards that apply to
other user accounts do not apply to root. Consequently using root for
mundane tasks often results in a memory lapse or misplaced keystrokes
having catastrophic effects (e.g. forgetting for a moment which
directory you are in and accidentally deleting another user\'s files, or
accidentally typing \"rm -rf \* .txt\" instead of \"rm -rf \*.txt\" ).

A better way to become root is to use the su utility. su (switch user)
lets you become another user (at least as far as the computer is
concerned). If you don\'t specify the name of the user you wish to
become, the system will assume you want to become root. Using su does
not usually change your current directory, unless you specify a \"-\"
option which will run the target user\'s startup scripts and change into
their home directory (provided you can supply the right password of
course). So:

    \$ su -![](LINUX_html_8d1f4a31.png){#Image160 align="bottom"
width="27" height="15" border="0"}\
    Password: xxxxxxxx![](LINUX_html_8d1f4a31.png){#Image161
align="bottom" width="27" height="15" border="0"}\
    \#

Note that the root account often displays a different prompt (usually a
#). To return to your old self, simply type \"exit\" at the shell
prompt.

You should avoid leaving a root window open while you are not at your
machine. Consider this paragraph from a humorous 1986 Computer Language
article by Alan Filipski:

\"The prudent administrator should be aware of common techniques used to
breach UNIX security. The most widely known and practised attack on the
security of the UNIX brand operating system is elegant in its
simplicity. The perpetrator simply hangs around the system console until
the operator leaves to get a drink or go to the bathroom. The intruder
lunges for the console and types rm -rf / before anyone can pry his or
her hands off the keyboard. Amateur efforts are characterised by typing
in things such as ls or pwd. A skilled UNIX brand operating system
security expert would laugh at such attempts.\"

1.  3.  Shutdown and Systém Start-up

-   Shutdown: shutdown, halt, reboot (in /sbin)

\
/sbin/shutdown allows a UNIX system to shut down gracefully and
securely.  All logged-in  users  are  notified  that  the system is
going down, and new logins are blocked.  It is possible to shut the
system down  immediately or after a specified delay and to specify what
should happen after the system has been shut down:

\# /sbin/shutdown -r now![](LINUX_html_8d1f4a31.png){#Image162
align="bottom" width="27" height="15" border="0"} (shut down now and
reboot)\
\# /sbin/shutdown -h +5![](LINUX_html_8d1f4a31.png){#Image163
align="bottom" width="27" height="15" border="0"} (shut down in 5
minutes & halt)\
\# /sbin/shutdown -k 17:00![](LINUX_html_8d1f4a31.png){#Image164
align="bottom" width="27" height="15" border="0"} (fake a shutdown at
5pm)

halt and reboot are equivalent to shutdown -h and shutdown -r
respectively.

If you have to shut a system down extremely urgently or for some reason
cannot use shutdown, it is at least a good idea to first run the
command:

    \# sync![](LINUX_html_8d1f4a31.png){#Image165 align="bottom"
width="27" height="15" border="0"}

which forces the state of the file system to be brought up to date.\
 

-   System startup:

At system startup, the operating system performs various low-level
tasks, such as initialising the memory system, loading up device drivers
to communicate with hardware devices, mounting filesystems and creating
the init process (the parent of all processes). init\'s  primary
responsibility is to start up the system services as specified in
/etc/inittab. Typically these services include gettys (i.e. virtual
terminals where users can login), and the scripts in the directory
/etc/rc.d/init.d which usually spawn high-level daemons such as httpd
(the web server). On most UNIX systems you can type dmesg to see system
startup messages, or look in /var/log/messages.

If a mounted filesystem is not \"clean\" (e.g. the machine was turned
off without shutting down properly), a system utility fsck is
automatically run to repair it. Automatic running can only fix certain
errors, however, and you may have to run it manually:

    \# fsck *filesys*![](LINUX_html_8d1f4a31.png){#Image166
align="bottom" width="27" height="15" border="0"}

where *filesys* is the name of a device (e.g. /dev/hda1) or a mount
point (like /). \"Lost\" files recovered during this process end up in
the lost+found directory. Some more modern filesystems called
\"journaling\" file systems don\'t require fsck, since they keep
extensive logs of filesystem events and are able to recover in a similar
way to a transactional database.

1.  4.  Adding Users

-   useradd (in /usr/sbin):

useradd is a utility for adding new users to a UNIX system. It adds new
user information to the /etc/passwd file and creates a new home
directory for the user. When you add a new user, you should also set
their password (using the -p option on useradd, or using the passwd
utility):

    \# useradd bob![](LINUX_html_8d1f4a31.png){#Image167 align="bottom"
width="27" height="15" border="0"}\
    \# passwd bob![](LINUX_html_8d1f4a31.png){#Image168 align="bottom"
width="27" height="15" border="0"}

1.  5.  Controlling User Groups

-   groupadd (in /usr/sbin):

groupadd creates a new user group and adds the new information to
/etc/group:

  \# groupadd *groupname*![](LINUX_html_8d1f4a31.png){#Image169
align="bottom" width="27" height="15" border="0"}\
 

-   usermod (in /usr/sbin):

Every user belongs to a primary group and possibly also to a set of
supplementary groups. To modify the group permissions of an existing
user, use

\# usermod -g *initialgroup username* -G
*othergroups*![](LINUX_html_8d1f4a31.png){#Image170 align="bottom"
width="27" height="15" border="0"}

where *othergroups* is a list of supplementary group names separated by
commas (with no intervening whitespace).\
 

-   groups

You can find out which groups a user belongs to by typing:

  \# groups *username*![](LINUX_html_8d1f4a31.png){#Image171
align="bottom" width="27" height="15" border="0"}

1.  6.  Reconfiguring and Recompiling the Linux Kernel

Linux has a modular, customisable kernel with several switchable options
(e.g. support for multiple processors and device drivers for various
hardware devices). It may happen that some new hardware is added to a
Linux machine which requires you to recompile the kernel so that it
includes device driver support (and possibly new system calls) for the
new hardware. To do this, you will need to rebuild the Linux kernel from
scratch as follows:

-   Look in /usr/src/linux for the kernel source code. If it isn\'t
    there (or if there is just a message saying that only kernel
    binaries have been installed), get hold of a copy of the latest
    kernel source code from
    [[http://www.kernel.org](http://www.kernel.org/)]{.underline} and
    untar it into /usr/src/linux.

-   Change directory to /usr/src/linux.

-   To configure the kernel type either

    \# make config    (simple text mode configuration), or\
    \# make menuconfig (menu-driven text configuration), or\
    \# make xconfig   (graphical configuration for X)

You will be asked to select which modules (device drivers,
multiprocessor support etc.) you wish to include. For each module, you
can chose to include it in the kernel code (y), incorporate it as an
optional module that will be loaded if needed (m) or to exclude it from
the kernel code (n). To find out which optional modules have actually
been loaded you can run lsmod when the system reboots.\
 

-   Now type:

    \# make dep    (to build source code dependencies)\
    \# make clean   (to delete all stale object files)\
    \# make bzImage (to build the new kernel)\
    \# make modules (to build the new optional modules)\
    \# make modules_install (to install the modules)

The file /usr/src/linux/arch/i386/boot/bzImage now contains your new
kernel image. It remains only to install it.\
 

-   Change directory to /usr/src/linux/arch/i386/boot. In the same
    directory should be a script called install.sh which will copy your
    kernel image into /boot/vmlinuz:

\# install.sh *version* bzImage /boot/System.map /boot

where *version* is the kernel version number (of form 2.2.xx).\
 

-   Finally, you may need to update the /etc/lilo.conf file so that lilo
    (the Linux boot loader) includes an entry for your new kernel. Then
    run

    \# lilo![](LINUX_html_8d1f4a31.png){#Image172 align="bottom"
width="27" height="15" border="0"}

to update the changes. When you reboot your machine, you should be able
to select your new kernel image from the lilo boot loader.

1.  7.  Cron jobs

crond is a daemon that executes commands that need to be run regularly
according to some schedule. The schedule and corresponding commands are
stored in the file /etc/crontab.

Each entry in the /etc/crontab file entry contains six fields separated
by spaces or tabs in the following form:

       *minute  hour  day_of_month  month  weekday  command*

These fields accept the following values:

    minute            0 through 59\
    hour              0 through 23\
    day_of_month      1 through 31\
    month             1 through 12\
    weekday           0 (Sun) through 6 (Sat)\
    command           a shell command

You must specify a value for each field. Except for the command field,
these fields can contain the following:

-   A number in the specified range, e.g. to run a command in May,
    specify 5 in the *month* field.

-   Two numbers separated by a dash to indicate an inclusive range, e.g.
    to run a cron job on Tuesday through Friday, place 2-5 in the
    *weekday* field.

-   A list of numbers separated by commas, e.g. to run a command on the
    first and last day of January, you would specify 1,31 in the
    *day_of_month* field.

-   \* (asterisk), meaning all allowed values, e.g. to run a job every
    hour, specify an asterisk in the *hour* field.

You can also specify some execution environment options at the top of
the /etc/crontab file:

SHELL=/bin/bash\
PATH=/sbin:/bin:/usr/sbin:/usr/bin\
MAILTO=root

To run the calendar command at 6:30am. every Mon, Wed, and Fri, a
suitable /etc/crontab entry would be:

30 6 \* \* 1,3,5 /usr/bin/calendar

The output of the command will be mailed to the user specified in the
MAILTO environment option.

You don\'t need to restart the cron daemon crond after changing
/etc/crontab - it automatically detects changes.

1.  8.  Keeping Essential Processes Alive

It is important that daemons related to mission critical services are
immediately respawned if they fail for some reason. You can do this by
adding your own entries to the /etc/inittab file. For example:

rs:2345:respawn:/home/sms/server/RingToneServer

Here rs is a 2 character code identifying the service, and 2345 are the
runlevels (to find about runlevels, type man runlevel) for which the
process should be created. The init process will create the
RingToneServer process at system startup, and respawn it should it die
for any reason.

Excersises:

N.B. Please perform these tasks on your home PC and take extra care when
using the root account. Since your commands will be carried out without
the safeguards that apply to ordinary users, you may do serious damage
to the system. If in doubt, please ask (preferably before
pressing ![](LINUX_html_8d1f4a31.png){#Image173 align="bottom"
width="27" height="15" border="0"} !)

1.  Use su - to become root.

2.  Add a new user of your choosing to the system. Set their password.
    Check that they can log in.

3.  Add a new user group of your choosing to the system. Place yourself
    (i.e. your login, not root), and the user that you have added in the
    group. Check that you are both in the new group.

4.  Remove the user that you added.

5.  Make yourself a cron job that sends you a message (using write)
    every 10 minutes. Remove this when you start to find it irritating.

6.  Discover how to restart the web server httpd (or any other system
    daemon).

7.  [[tinyhttpd.pl]{.underline}](http://www.doc.ic.ac.uk/~wjk/UnixIntro/tinyhttpd.pl)
    is a mini-web server written in Perl. **Switch back to being a
    normal user**, and make a copy of tinyhttpd.pl in your home
    directory. Change the port number on which it operates to a port of
    your choice (currently 8080, but use a different one that noone else
    will be using). Create a public_html directory in your home
    directory and create a home page file inside it called
    \"index.html\". Now run tinyhttpd.pl in the background and use
    telnet (telnet *machine* *port*, where *machine* is the hostname and
    *port* is the port number, and then issue the HTTP command GET /
    HTTP/1.0![](LINUX_html_8d1f4a31.png){#Image174 align="bottom"
    width="27" height="15" border="0"}
    ![](LINUX_html_8d1f4a31.png){#Image175 align="bottom" width="27"
    height="15" border="0"} ) or a web browser (call up
    http://*machine*:*port*) to test that your home page file is in fact
    being served.

8.  Switch back to being root. Add a line to /etc/inittab which will
    ensure that your mini web-server will respawn itself if it dies.
    Kill your web server (using kill) and see if the respawning works
    (init re-examines the /etc/inittab file whenever one of its
    descendant processes dies so you should not have long to wait for
    this to take effect). It may be helpful to monitor the system
    messages file with tail -f /var/log/messages.

\
\

8.  Lecture Eight

\
\

1.  1.  Objetives

This chapter covers:

-   Shells and shell scripts.

-   Shells variables and the environment.

-   Simple shell scripting

-   Advanced shell scripting.

-   Start-up shell scripts.

1.  2.  Shell and Shell scripts

A shell is a program which reads and executes commands for the user.
Shells also usually provide features such job control, input and output
redirection and a command language for writing *shell scripts*. A shell
script is simply an ordinary text file containing a series of commands
in a shell command language (just like a \"batch file\" under MS-DOS).

There are many different shells available on UNIX systems (e.g. sh,
bash, csh, ksh, tcsh etc.), and they each support a different command
language. Here we will discuss the command language for the Bourne shell
sh since it is available on almost all UNIX systems (and is also
supported under bash and ksh).

1.  3.  Shell Variables and the Environment

A shell lets you define variables (like most programming languages). A
variable is a piece of data that is given a name. Once you have assigned
a value to a variable, you access its value by prepending a \$ to the
name:

    \$ bob=\'hello world\'![](LINUX_html_8d1f4a31.png){#Image176
align="bottom" width="27" height="15" border="0"}\
    \$ echo \$bob\
    hello world\
    \$

Variables created within a shell are local to that shell, so only that
shell can access them. The set command will show you a list of all
variables currently defined in a shell. If you wish a variable to be
accessible to commands outside the shell, you can *export* it into the
*environment*:

    \$ export bob![](LINUX_html_8d1f4a31.png){#Image177 align="bottom"
width="27" height="15" border="0"}

(under csh you used setenv). The environment is the set of variables
that are made available to commands (including shells) when they are
executed. UNIX commands and programs can read the values of environment
variables, and adjust their behaviour accordingly. For example, the
environment variable PAGER  is used by the man command (and others) to
see what command should be used to display multiple pages. If you say:

    \$ export PAGER=cat![](LINUX_html_8d1f4a31.png){#Image178
align="bottom" width="27" height="15" border="0"}

and then try the man command (say man pwd), the page will go flying past
without stopping. If you now say:

    \$ export PAGER=more![](LINUX_html_8d1f4a31.png){#Image179
align="bottom" width="27" height="15" border="0"}

normal service should be resumed (since now more will be used to display
the pages one at a time). Another environment variable that is commonly
used is the EDITOR variable which specifies the default editor to use
(so you can set this to vi or emacs or which ever other editor you
prefer). To find out which environment variables are used by a
particular command, consult the man pages for that command.

Another interesting environment variable is PS1, the main shell prompt
string which you can use to create your own custom prompt. For example:

    \$ export PS1=\"(\\h) \\w\> \"![](LINUX_html_8d1f4a31.png){#Image180
align="bottom" width="27" height="15" border="0"}\
    (lumberjack) \~\>

The shell often incorporates efficient mechanisms for specifying common
parts of the shell prompt (e.g. in bash you can use \\h for the current
host, \\w for the current working directory, \\d for the date, \\t for
the time, \\u for the current user and so on - see the bash man page).

Another important environment variable is PATH. PATH is a list of
directories that the shell uses to locate executable files for commands.
So if the PATH is set to:

    /bin:/usr/bin:/usr/local/bin:.

and you typed ls, the shell would look for /bin/ls, /usr/bin/ls etc.
Note that the PATH contains\'.\', i.e. the current working directory.
This allows you to create a shell script or program and run it as a
command from your current directory without having to explicitly say
\"./*filename*\".

Note that PATH has nothing to with filenames that are specified as
*arguments* to commands (e.g. cat myfile.txt would only look for
./myfile.txt, not for /bin/myfile.txt, /usr/bin/myfile.txt etc.)

1.  4.  Simple shell scripting

Consider the following simple shell script, which has been created
(using an editor) in a text file called simple:

#!/bin/sh\
\# this is a comment\
echo \"The number of arguments is \$#\"\
echo \"The arguments are \$\*\"\
echo \"The first is \$1\"\
echo \"My process number is \$\$\"\
echo \"Enter a number from the keyboard: \"\
read number\
echo \"The number you entered was \$number\"

The shell script begins with the line \"#!/bin/sh\" . Usually \"#\"
denotes the start of a comment, but #! is a special combination that
tells UNIX to use the Bourne shell (sh) to interpret this script. The #!
must be the first two characters of the script. The arguments passed to
the script can be accessed through \$1, \$2, \$3 etc. \$\* stands for
all the arguments, and \$# for the number of arguments. The process
number of the shell executing the script is given by \$\$. the read
number statement assigns keyboard input to the variable number.

To execute this script, we first have to make the file simple
executable:

    \$ ls -l simple![](LINUX_html_8d1f4a31.png){#Image181 align="bottom"
width="27" height="15" border="0"}\
    -rw-r\--r\--    1 will  finance  175  Dec 13  simple\
    \$ chmod +x simple![](LINUX_html_8d1f4a31.png){#Image182
align="bottom" width="27" height="15" border="0"}\
    \$ ls -l simple![](LINUX_html_8d1f4a31.png){#Image183 align="bottom"
width="27" height="15" border="0"}\
    -rwxr-xr-x    1 will  finance  175  Dec 13  simple\
    \$ ./simple hello world![](LINUX_html_8d1f4a31.png){#Image184
align="bottom" width="27" height="15" border="0"}\
    The number of arguments is 2\
    The arguments are hello world\
    The first is hello\
    My process number is 2669\
    Enter a number from the keyboard:\
    5![](LINUX_html_8d1f4a31.png){#Image185 align="bottom" width="27"
height="15" border="0"}\
    The number you entered was 5\
    \$

We can use input and output redirection in the normal way with scripts,
so:

    \$ echo 5 \| simple hello
world![](LINUX_html_8d1f4a31.png){#Image186 align="bottom" width="27"
height="15" border="0"}

would produce similar output but would not pause to read a number from
the keyboard.

1.  5.  More Advanced Shell Scripting

-   if-then-else statements

Shell scripts are able to perform simple conditional branches:

if \[ *test* \]\
then\
    *commands-if-test-is-true*\
else\
    *commands-if-test-is-false*\
fi

The *test* condition may involve file characteristics or simple string
or numerical comparisons. The \[ used here is actually the name of a
command (/bin/\[) which performs the evaluation of the test condition.
Therefore there must be spaces before and after it as well as before the
closing bracket. Some common test conditions are:

-s *file*\
    true if *file* exists and is not empty\
-f *file*\
    true if *file* is an ordinary file\
-d *file*\
    true if *file* is a directory\
-r *file*\
    true if *file* is readable\
-w *file*\
    true if *file* is writable\
-x *file*\
    true if *file* is executable\
\$X -eq \$Y\
    true if X equals Y\
\$X -ne \$Y\
    true if X not equal to Y\
\$X -lt \$Y\
    true if X less than \$Y\
\$X -gt \$Y\
    true if X greater than \$Y\
\$X -le \$Y\
    true if X less than or equal to Y\
\$X -ge \$Y\
    true if X greater than or equal to Y\
\"\$A\" = \"\$B\"\
    true if string A equals string B\
\"\$A\" != \"\$B\"\
    true if string A not equal to string B\
\$X ! -gt \$Y\
    true if string X is not greater than Y\
\$E -a \$F\
    true if expressions E and F are both true\
\$E -o \$F\
    true if either expression E or expression F is true\
 

-   for loops

Sometimes we want to loop through a list of files, executing some
commands on each file. We can do this by using a for loop:

for *variable* in *list*\
do\
    *statements * (referring to \$*variable*)\
done

The following script sorts each text files in the current directory:

#!/bin/sh\
for f in \*.txt\
do\
    echo sorting file \$f\
    cat \$f \| sort \> \$f.sorted\
    echo sorted file has been output to \$f.sorted\
done\
 

-   while loops

Another form of loop is the while loop:

while \[ *test* \]\
do\
    *statements*     (to be executed while *test* is true)\
done

The following script waits until a non-empty file input.txt has been
created:

#!/bin/sh\
while \[ ! -s input.txt \]\
do\
  echo waiting\...\
  sleep 5\
done\
echo input.txt is ready

You can abort a shell script at any point using the exit statement, so
the following script is equivalent:

#!/bin/sh\
while true\
do\
  if \[ -s input.txt \]\
    echo input.txt is ready\
    exit\
  fi\
  echo waiting\...\
  sleep 5\
done\
 

-   case statements

case statements are a convenient way to perform multiway branches where
one input pattern must be compared to several alternatives:

case *variable* in\
    *pattern1*)\
        *statement *   (executed if *variable* matches *pattern1*)\
        ;;\
    *pattern2*)\
        *statement*\
        ;;\
    *etc.*\
esac

The following script uses a case statement to have a guess at the type
of non-directory non-executable files passed as arguments on the basis
of their extensions (note how the \"or\" operator \| can be used to
denote multiple patterns, how \"\*\" has been used as a catch-all, and
the effect of the forward single quotes \`):

#!/bin/sh\
for f in \$\*\
do\
  if \[ -f \$f -a ! -x \$f \]\
  then\
    case \$f in\
    core)\
      echo \"\$f: a core dump file\"\
      ;;\
    \*.c)\
     echo \"\$f: a C program\"\
      ;;\
    \*.cpp\|\*.cc\|\*.cxx)\
      echo \"\$f: a C++ program\"\
      ;;\
    \*.txt)\
      echo \"\$f: a text file\"\
      ;;\
    \*.pl)\
      echo \"\$f: a PERL script\"\
      ;;\
    \*.html\|\*.htm)\
      echo \"\$f: a web document\"\
      ;;\
    \*)\
      echo \"\$f: appears to be \"\`file -b \$f\`\
      ;;\
    esac\
  fi\
done\
 

-   capturing command output

Any UNIX command or program can be executed from a shell script just as
if you would on the line command line. You can also capture the output
of a command and assign it to a variable by using the forward single
quotes \` \`:

 #!\\bin\\sh\
 lines=\`wc -l \$1\`\
 echo \"the file \$1 has \$lines lines\"

This script outputs the number of lines in the file passed as the first
parameter.\
 

-   arithmetic operations

The Bourne shell doesn\'t have any built-in ability to evaluate simple
mathematical expressions. Fortunately the UNIX expr command is available
to do this. It is frequently used in shell scripts with forward single
quotes to update the value of a variable. For example:

    lines = \`expr \$lines + 1\`

adds 1 to the variable lines. expr supports the operators +, -, \*, /, %
(remainder), \<, \<=, =, !=, \>=, \>, \| (or) and & (and).

1.  6.  Start-up Shell Scripts

When you first login to a shell, your shell runs a systemwide start-up
script (usually called /etc/profile under sh, bash and ksh and
/etc/.login under csh). It then looks in your home directory and runs
your personal start-up script (.profile under sh, bash and ksh and
.cshrc under csh and tcsh). Your personal start-up script is therefore
usually a good place to set up environment variables such as PATH,
EDITOR etc. For example with bash, to add the directory \~/bin to your
PATH, you can include the line:

    export PATH=\$PATH:\~/bin

in your .profile. If you subsequently modify your .profile and you wish
to import the changes into your current shell, type:

    \$ source .profile\
or\
    \$ . ./profile

The source command is built into the shell. It ensures that changes to
the environment made in .profile affect the current shell, and not the
shell that would otherwise be created to execute the .profile script.

With csh, to add the directory \~/bin to your PATH, you can include the
line:

    set path = ( \$PATH \$HOME/bin )

in your .cshrc.

Excersise:

1.  Use your favourite UNIX editor to create the simple shell script
    given in Section 8.4 of the notes. Run it, and see how the contents
    of the script relates to the output.

2.  Extend the script so that it generates a random secret number
    between 1 and 100 (c.f. Exercise Sheet 3, Question 16) and then
    keeps asking the user to guess the secret number until they guess
    correctly. The script should give the user hints such as \"I\'m
    sorry your guess is too low\" or \"I\'m sorry your guess is too
    high\".

3.  Write a shell script which renames all .txt files as .text files.
    The command basename might help you here.

4.  Write a shell script called pidof which takes a name as parameter
    and returns the PID(s) of processes with that name.

5.  Shell scripts can also include functions. Functions are declared
    as:\
    \
    function *funcname*() {\
    *      statements\
    *}\
    \
    and invoked as *funcname param1 param2*\... The parameters passed to
    the function are accessible inside the function through the
    variables \$1, \$2, etc. Now add a usage() function to your pidof
    script which prints usage instructions. Call usage() if the wrong
    number of parameters is passed to the script.

6.  Modify your .bash_profile script so that your PATH includes the
    current directory (.) and so that your environment variable
    EDITOR is set to emacs or vi (or whatever else you prefer to use).
    Run the modified script using source .bash_profile and check that
    the changes you made have been applied to the current shell (type
    set).

\
\
