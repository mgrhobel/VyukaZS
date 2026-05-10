---
title: "test_1.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/Pomùcky z minulých let/test_1.doc"
date: 2006-12-12
type: DOC
---

SSPGM 2006, test_1

1.  Nakreslete blokovou strukturu OS UNIX 0,1,2

2.  Co je multitasking, nepreemptivní multitasking 0,1,2

3.  Co je i-node, UID, GID, PID, PPID 0,1,2

4.  Nastavte masku tak, aby se vytvořil soubor s atributy\
    -\|rwx\|r\--\|\-\-- , -\|\-\--\|-w-\|-w- , -\|rw-\|rw-\|rw- ,
    -\|\-\--\|\-\--\|\-\-- 0,1,3

5.  Nastavte pomocí oktalového čísla atributy -\|rwsr-s\|r-x a
    vysvětlete\
    význam atributu „s" 0,1,3

6.  Jaké číslo má signál SIGSEGV a co vyjadřuje 0,2

7.  Popište mechanismus swap přes vyrovnávací paměť, jaké základní\
    algoritmy jsou uplatňovány, stanovte velikost přenášených bloků
    0,1,3

8.  Které signály nelze předefinovat 0,2

9.  Komu je zaslán signál: kill --s SIGINT 0, kill --s SIGINT 1 a to\
    v případě vyslání signálu běžným uživatelem, suprvisorem 0,1,3

10. Který proces má číslo 0 0,1

11. Čím je limitováno vytvoření procesu, návratové chyby při neúspěchu
    0,2

12. Co se stane, když „potomek" skončí a „rodič" pokračuje,\
    vyjádřete výpisem procesů 0,2

13. Co zdědí „potomek" od „rodiče" 0,2

14. Jaké jsou možnosti ukončení procesu? 0,2

15. Jaké číslo se vrací procesu „rodič" a „potomek" při volání fork()
    0,2

16. Jaký je rozdíl mezi echo '\`ls\`' a echo "\`ls\`" 0,2

17. Vyjádřete možnosti spuštění skriptu 0,1,2

18. Nakreslete blokově datovou strukturu procesu s uvedením adres.
    prostoru 0,1,2

19. Co je propůjčení identifikace, SUID, SGID, sticky bit 0,1,2

20. Nakreslete blokově volání jádra fork s ošetřením

chybových stavů při vzniku potomka 0,1,2

21. Vyjmenujte některé signály 0,1,2

22. Napište konkrétní shell příklad pro filter (přesměrování), rouru,
    kolonu 0,1,2

23. (pwd[;cd adresar;pwd]{lang="en-US"});pwd

{ pwd;cd adresar;pwd;};pwd

vše v adresáři \$HOME, jaký je rozdíl 0,3

24. Co se stane po ukončení potomka exitem a rodič stále běží,

jak se zachová jádro 0,3

25. Co se stane s potomkem, když rodič skončí 0,3

26. Napište program, který přesměruje standardní výstup do souboru 0,3

27. Co je reálné a efektivní ID a k čemu se vztahují 0,3

28. Vysvětlete princip propůjčení identifikace při spuštění programu pr

uživatelem u2, viz příklad. Označte, který případ řeší tento
mechanismus. 0,2,4

-rwsr-xr-x u1(600) sspgm pr (executeable program)

-r[\-\-\-\-\-\-\-\-\--]{lang="en-US"} u1(600) sspgm su1 (soubor)

-r\-\-\-\-\-\-\-\-\-- u2(601) sspgm su2 (soubor)

\

a\) uid=601 euid=600

fdsu1= fdsu2=

\

b\) uid=601 euid=601

fdsu1= fdsu2=

\

max. počet bodů ... 66, min. počet bodů nutný, nikoliv postačující
k zápočtu ... 40
