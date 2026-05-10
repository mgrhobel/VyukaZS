---
title: "hwm14cz.htm"
source: "/mnt/f/git/mgr/FPE_navazujici/1. Semestr/SM/Projekty/thaletova vìta/Mat Aplety/m14cz/hwm14cz.htm"
date: 2006-05-06
type: HTML
---

+:---------------------------------:+:---------------------------------:+
| ![Mathematik](../m14_             | **Matematické Java aplety**       |
| gifs/javamath.gif){align="center" |                                   |
| width="124" height="124"}         | **Technická poznámka**            |
+-----------------------------------+-----------------------------------+

[]{#browser}

## 1. Prohlížeè a Java podpora

**Java aplet není žádný samostatnì spustitelný program. Aplet bìží v
rámci dané WWW stránky a vyžaduje, aby použitý prohlížeè tuto možnost
podporoval. Pokud máte nìkterou ze starších verzí prohlížeèù a nebo nový
Internet Explorer verze 6.0 (vyjímka potvrzující pravidlo), pøeète te si
bedlivì následující øádky.**

**Problémy mohou nastat z následujících dùvodù :**

  -------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  **a)**   **Na poèítaè je nutné nainstalovat Java prostøedí. To se týká zejména Internet Exlorer 6, který - na rozdíl od pøedchozí verze - Java prostøedí pøímo nepodporuje. Potøebné Java prostøedí mùžete stáhnout ze stránek [Sun Microsystems](http://java.sun.com).**
  -------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

+-----------------------+-----------------------+-----------------------+
| **b)**                | **Verze Java:**       | **Programovací jazyk  |
|                       |                       | Java byl nìkolikrát v |
|                       |                       | dùležitých bodech     |
|                       |                       | zmìnìn a rozšíøen.    |
|                       |                       | Díky tomu starší      |
|                       |                       | verze nainstalovaného |
|                       |                       | Java prostøedí mohou  |
|                       |                       | zpùsobovat, že aplety |
|                       |                       | vùbec nebo èásteènì   |
|                       |                       | nebudou fungovat.     |
|                       |                       | Proto jsou zde k      |
|                       |                       | dispozici i starší    |
|                       |                       | verze \"Matematických |
|                       |                       | Java apletù\", pro    |
|                       |                       | ty, kteøí na svém PC  |
|                       |                       | nemají aktuální verzi |
|                       |                       | Java podpory:**       |
|                       |                       |                       |
|                       |                       | -   **[Java           |
|                       |                       |     1.0]              |
|                       |                       | (http://www.zum.de/ma |
|                       |                       | /fendt/math/md10.htm) |
|                       |                       |     (od 28. dubna     |
|                       |                       |     2000 není dále    |
|                       |                       |     aktualizováno)**  |
|                       |                       | -   **[Java           |
|                       |                       |     1.1](http://www.w |
|                       |                       | alter-fendt.de/m11d/) |
|                       |                       |     (od 16. ledna     |
|                       |                       |     2003 není dále    |
|                       |                       |     aktualizováno)**  |
|                       |                       | -   **[Java           |
|                       |                       |     1.4](http://www.w |
|                       |                       | alter-fendt.de/m14d/) |
|                       |                       |     (aktuální         |
|                       |                       |     verze)**          |
+-----------------------+-----------------------+-----------------------+

  -------- ---------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  **c)**   **Nesprávná Java implementace:**   **Bohužel nìkteré prohlížeèe jsou sice schopné základní Java aplety prezentovat, ale v dùsledku chyb v tzv. \"Virtual Machine\" složitìjší aplety nezobrazí správnì nebo dokonce prohlížeè spadne.**
  -------- ---------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

  ----------------------- ----------------------- -----------------------
  **d)**                  **Bezpeènostní          **Pro Java aplety platí
                          opatøení:**             pøísné bezpeènostní
                                                  opatøení, která musí
                                                  zamezit tomu, aby aplet
                                                  mohl na Vašem poèítaèi
                                                  zpùsobit jakoukoliv
                                                  škodu. Tu a tam se však
                                                  vždy najde nìjaká ta
                                                  díra v bezpeènosti,
                                                  proto nìkteré
                                                  prohlížeèe mají
                                                  standardnì jazyk Java
                                                  zakázán. Jestliže máte
                                                  prohlížeè správné
                                                  verze, stejnì tak i
                                                  Java prostøedí a pøesto
                                                  Java aplety nebìhají,
                                                  musíte v nastavení
                                                  prohlížeèe povolit
                                                  jazyk Java.\
                                                  (*Žádný strach, moje
                                                  aplety jsou naprosto
                                                  neškodné!*)**

  ----------------------- ----------------------- -----------------------

## 2. Chyby?

**Jistì znáte Murphyho zákon: \"Jestli se mùže nìco pokazit, tak se to i
pokazí!\" Aplety této sbírky byly peèlivì testovány, pøesto nìjaká chyba
není zcela vyloèena. Obèas se mùže zdát, že aplet neraguje na zmìnu
parametrù, ale je to jen díky tomu, že pøi zadávání hodnot do textových
polí nebylo zadání potvrzeno klávesou Enter. Pokud však v kterémkoliv
Java apletu objevíte jakoukoliv chybu, budu vdìèný, pokud mi zašlete**

s co nejpodrobnìjšími informacemi (URL, použitý operaèní systém, typ a
verze prohlížeèe, verze Java prostøedí, zadané parametry atd.). Budu se
snažit tuto chybu co nejrychleji odstranit.

## 3. Stažení (download) apletù

**Pro školy je smysluplné aplety umístit pøímo na vlastní server, aby
byly k dipozici i v pøípadì, kdy není k možné pøímé pøipojení k
Internetu. Na zaèátku [obsahu](index.html) je umístìn odkaz, ze kterého
mùžete stáhnout celou sbírku. Aby nebylo nutné stahovat všechny soubory
jednotlivì, byly sbaleny pomocí ZIP-formátu do souboru jediného. Abyste
mohli Java aplety používat musíte tento ZIP soubor rozbalit na Vás
harddisk do nìjakého vámi vytvoøeného adresáøe (napø. JavaMath). Pro
rozbalení souboru potøebjete \"rozbalovací\" program - napø. WinZip. Po
rozbalení by ve Vašem adresáøi mìly vytvoøit tyto složky:**

-   **m14 (HTML texty, pøípona *htm* èi *html*)**
-   **m14_gifs (obrázky, pøípona *gif* èi *jpg*)**
-   **m14_jar (java aplety, pøípona *jar*)**
-   **m14d (HTML texty, pøípona *htm* èi *html*)**

**Nyní by mìly Java aplety fungovat i bez pøístupu na Internet. Pokud i
v tuto chvíli Java aplety nefungují (nejsou vidìt), pøeètì si ještì
jednou a pozornì [bod 1](#browser).**

Pøíjemnou zábavu!

------------------------------------------------------------------------

Poslední zmìna: 13.3.2006
