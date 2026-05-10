---
title: "komenatr p26_1.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/moje prace/cv6-odevzdat/komenatr p26_1.doc"
date: 2009-05-10
type: DOC
---

## Vypis programu {#vypis-programu .western lang="cs-CZ"}

\...\...\...\...\...\...\...\...\...\...\...\.....

\...\...\...\...\...\...\...\...\...\...\...\.....

\...\...\...\...\...\...\...\...\...\...\...\.....

\

## Vypis procesu {#vypis-procesu .western lang="cs-CZ"}

0 R u4 7137 5499 59 94 19 - 355 - 15:19 pts/0 00:00:02 p26_1

1 S u4 7138 7137 15 76 0 - 355 write\_ 15:19 pts/0 00:00:00 p26_1

0 S u4 7140 5971 0 76 0 - 521 pipe_w 15:19 pts/1 00:00:00 grep p26_1

##  {#section .western lang="cs-CZ"}

## Z dalsi konzole vysleme SIGKILL (SIGINT) potomku, SIGKILL (SIGINT) rodici {#z-dalsi-konzole-vysleme-sigkill-sigint-potomku-sigkill-sigint-rodici .western lang="cs-CZ"}

\

-\> u4@hana:\~\> kill -9 7138 (pripadne kill -s sigkill 7138)

\

### Vypis programu {#vypis-programu-1 .western lang="cs-CZ"}

PID 7137 zachytil signal

PID 7137 zachytil signal

\

0 R u4 7192 5499 47 99 19 - 354 - 15:30 pts/0 00:00:08 p26_1

1 Z u4 7193 7192 19 75 0 - 0 exit 15:30 pts/0 00:00:03 \[p26_1\]
\<defunct\>

0 S u4 7197 5971 0 76 0 - 520 pipe_w 15:30 pts/1 00:00:00 grep

\

\

### Komentar {#komentar .western lang="cs-CZ"}

Po zadani prikazu kill -9 7138 se provede prikaz if(kill(pid,SIGINT==-1)
exit(0)), ktery vyhodi reakci na signal (PID 7137 zachytil signal).

Potomek ukoncen, ale rodic ne - potomek zustal ve stavu zombie.

\

\

\

-\> u4@hana:\~\> kill -9 7137 (pripadne kill -s sigkill 7137)

\

### Vypis programu {#vypis-programu-2 .western lang="cs-CZ"}

Ukončen (SIGTERM) p26_1

Zabit (SIGKILL)

\

### Komentar {#komentar-1 .western lang="cs-CZ"}

Ukoncen jak potomek tak i rodic

\

\

\
