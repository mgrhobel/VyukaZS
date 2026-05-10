---
title: "my4.txt"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/programy/internet/my4.txt"
date: 2009-05-03
type: TXT
---

funkce signal(), kill(), kde jeden proces vytvoøí jiný a pak jej signálem zabije.

#include <stdio.h>
#include <unistd.h>
#include <stdlib.h>
#include <signal.h>
#include <sys/types.h>

/* signal handler */
/*!:*/void int_handler(int sig)/*:!*/
{
    int mypid = getpid();
    printf("[%i] Ouch - shot in the ...\n", mypid);
    printf("[%i] exit\n", mypid);
    exit(2);
}

int main(int argc, char *argv[])
{
    pid_t pid;
    
    pid = fork();
    if (pid < 0)  {
        fprintf(stderr, "fork failed\n");
        exit(1);
    } 
    
    if (pid == 0)  {         // child
        int mypid = getpid();
        /*!:*/signal(SIGINT, int_handler);/*:!*/
        while (1) {
            usleep(50000);
            printf("[%i] Running amok!!!\n", mypid);
        }
    }
    else {                     // parent
        int mypid = getpid();
        int i;
        for(i=0; i<3; i++) {
            printf("[%i] is gonna kill you ...\n", mypid);
            sleep(1);
        }
        printf("[%i] is shooting (SIGINT) !!!\n", mypid);
        /*!:*/kill(pid, SIGINT);/*:!*/
        printf("[%i] exit\n", mypid);
    }
    exit(0);
}
