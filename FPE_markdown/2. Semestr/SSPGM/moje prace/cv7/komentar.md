---
title: "komentar.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/moje prace/cv7/komentar.doc"
date: 2009-05-10
type: DOC
---

    1]

    Vypis
    0 S u4        7446  5499  0  76   0 -   354 pause  16:19 pts/0    00:00:00 cv7_1
    1 S u4        7447  7446  0  76   0 -   355 pause  16:19 pts/0    00:00:00 cv7_1





    P31.c

    A]
    pocet arg = 2
    Potomek: 18268
    Potomek: 18269
    Potomek: 18270
    Potomek: 18271
    Potomek: 18272
    Potomek: 18273
    Potomek: 18274
    Potomek: 18275
    Potomek: 18276
    Potomek: 18277
    Potomek: 18278
    Potomek: 18279
    Potomek: 18280
    Potomek: 18281
    Potomek: 18282
    Wait ret_val= -1  ret_code= -4214497
    Wait ret_val= -1  ret_code= -4214497

    Nastavena ignorance pro signal SIGCHD. Rodic ve stavu wait nereaguje na signal SIGCHLD

    B]
    Potomek: 18205
    Potomek: 18206
    Potomek: 18207
    Potomek: 18208
    Potomek: 18209
    Potomek: 18210
    Potomek: 18211
    Potomek: 18212
    Potomek: 18213
    Potomek: 18214
    Potomek: 18215
    Potomek: 18216
    Potomek: 18217
    Potomek: 18218
    Potomek: 18219
    Wait ret_val= 18219  ret_code= 14
    Wait ret_val= 18218  ret_code= 13

    Po ukončení potomka příkazem exit se rodiči zašle signál SIGCHLD o ukončení potomka. Rodič tento signál přijme (obslouží), pokud je ve stavu wait. 

    P30.c

    Signál SIGCHLD je aktivován, ale tím, že zde chybí příkaz wait() pro odchytávání těchto odstraněných potomků, zůstávají v rodici zaregistrováni, ikdyz jsou už odstraněni z paměti (jsou ve stavu mátoha).

    1
    Potomek: 18394
    2
    Potomek: 18395
    3
    Potomek: 18396
    4
    Potomek: 18397



    0 S u4       18393  8066  0  76   0 -   353 -      19:48 pts/0    00:00:00 p30
    1 Z u4       18394 18393  0  76   0 -     0 exit   19:48 pts/0    00:00:00 [p30] <defunct>
    1 Z u4       18395 18393  0  75   0 -     0 exit   19:48 pts/0    00:00:00 [p30] <defunct>
    1 Z u4       18396 18393  0  76   0 -     0 exit   19:48 pts/0    00:00:00 [p30] <defunct>
    1 Z u4       18397 18393  0  76   0 -     0 exit   19:48 pts/0    00:00:00 [p30] <defunct>


    Signál SIGCHLD je ignorován, 

    1
    Potomek: 18415
    2
    Potomek: 18416
    3
    Potomek: 18417
    4
    Potomek: 18418

    0 S u4       18414  8066  0  75   0 -   354 -      19:52 pts/0    00:00:00 p30 a
