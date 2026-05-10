---
title: "my1.txt"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/programy/internet/my1.txt"
date: 2009-05-03
type: TXT
---

//ètení argumentù pøíkazové øádky
#include <stdio.h>
 
 int main(int argc, char *argv[])
 {
     int i;
     for(i=0; i<argc; i++) {
         printf("argv[%2i] = '%s'\n", i, argv[i]);
     }
     return 0;
 }
