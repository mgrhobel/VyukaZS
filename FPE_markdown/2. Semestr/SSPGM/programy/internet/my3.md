---
title: "my3.txt"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/programy/internet/my3.txt"
date: 2009-05-03
type: TXT
---

//funkci fork(), wait(), kde jeden proces vytvoøí jiný a pak èeká na jeho ukonèení.

#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <sys/wait.h>
#include <sys/types.h>

int main(int argc, char *argv[])
{
    pid_t pid;
    
    /*!:*/if((pid = fork()) == 0)/*:!*/ 
    { // child
        printf("sleeping...\n");
        sleep(3);
        printf("waking ... and exiting\n");
    } 
    else if (pid > 0) 
    { // parent
        printf("waiting for child\n");
        /*!:*/wait(NULL);/*:!*/
        printf("child woke up\n");
    }
    exit(0);
}
