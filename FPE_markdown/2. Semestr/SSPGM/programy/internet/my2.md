---
title: "my2.txt"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/programy/internet/my2.txt"
date: 2009-05-03
type: TXT
---

//funkce exec()

#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <sys/wait.h>
#include <sys/types.h>

int main(int argc, char *argv[])
{
    pid_t pid;
    
    pid = fork();
    if (pid < 0) {
        fprintf(stderr, "fork failed\n");
        exit(1);
    }
    
    if(pid == 0) {
        /*!:*/execlp("ls", "ls", "-a", "-l", (char *) NULL);/*:!*/
        // pokud exec neselze tento kod se nevykona
        perror("execl failed");
        exit(2);
    }
    printf("parent carries on\n");
    exit(0);
}

