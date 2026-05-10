---
title: "cv2.txt"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/FPE Volume P/cv2.txt"
date: 2006-10-03
type: TXT
---

Cviceni SSPGM 2. tyden

Vyzkousejte prikazy:

1. cd, mkdir, rmdir, rm, cp, mv, pwd, cat, touch, ln (hard, symblic) na soubory, adresare
   who, w, id

2. Seznamte se a vyzkousejte utility id, adduser, newgrp

3. Seznamte se a vyzkousejte prikaz chmod, chown, chgrp, umask

4. Nastavte umask tak, aby se defaultne tvorily
soubory rw-|---|---
adresare rwx|--x|--x
adresare rwx|--x|---

5. Vypiste pocet souboru v adresari $HOME
Pomocny priklad:
vypocet poctu podadresaru v aktualnim adresari:
(echo -n -2+;{ l|grep 4096|wc -l|bc -l; }) |bc -l


6. Vypiste, kolikrat je prihlasen uzivatel <v>

7. Co vypise
wc *
wc * >pocty
wc * >pocty&
wc *   kdyz bude v adresari otevrena roura

8. Analyzujte
cd cv2;l
cd cv2 & l
cd cv2 && l; cd
cd cv2 || l; cd

9. Analyzujte
(pwd;cd cv2;pwd);pwd
{ pwd;cd cv2;pwd;};pwd

10. Vytvorte rouru (mknod roura p) s nazvem napr. roura a
analyzujte napr.
man w >roura &
cat (more) roura

