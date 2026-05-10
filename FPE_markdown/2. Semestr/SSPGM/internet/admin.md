---
title: "admin.html"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/internet/admin.html"
date: 2009-04-27
type: HTML
---

<div>

</div>

------------------------------------------------------------------------

## LINUX - admin.

------------------------------------------------------------------------

1.  [**Pøíkazy pro administraci**](#LIN.PRIK)
2.  [**RPM**](#LIN.RPM)
3.  [**YUM, APT**](#LIN.YUM)
4.  [**Informace o hw, syst.**](#LIN.INF)
5.  [**Zapomenuté heslo pro root**](#LIN.PASS)
6.  [**Mathematica - fonty**](#LIN.MATH)
7.  [**hpacucli - utilita pro konfiguraci diskového
    pole**](#LIN.HPACUCLI)
8.  [**Imggen - utilita pro zašifrování textu do obrázku - ochrana proti
    spamerùm**](#LIN.IMGGEN)

------------------------------------------------------------------------

[]{#LIN}

### [Pøíkazy pro administraci]{#LIN.PRIK}

------------------------------------------------------------------------

-   **chfn** \[volby\] \[jmeno_uzivatele\]
    umožní zmìnit informace v souboru /etc/passwd
-   **logrotate** \[volby\] konfiguracni_soubory
    manipuluje žurnálové soubory podle pøíkazu v konfiguraèních
    souborech
-   **ncftp**
    nahrazuje ftp - bezpeènìjší
-   **rpm** \[volby\]
    manager balíku Red Hat pro instalaci softwaru
-   **su -l uzivatel**
    nastaví prostøedí uživatele
-   **unlink** adresar
    smaže neprázdný adresáø
-   **uptime**
    vypíše èas posledního rebootu
-   **useradd** \[volby\] \[uzivatel\]
    vytvoøí nový uživatelský úèet nebo aktualizuje implicitní
    uživatelské informace
-   **userdel** \[volby\] \[uzivatel\]
    smaže všechny položky daného uživatele v systémových úèetních
    souborech
-   **usermod** \[volby\] \[uzivatel\]
    modifikuje informace pro úèet daného uživatele
-   **timeconfig**
    modifikuje èasovou zónu
-   **xmkmf**
    vytvoøí Makefile z Imakefilu
-   **http://rpmfind.net**
    hledá rpm balík, který obsahuje soubor zadaný a)celým jménem,
    b)zaèátkem jména, c)èástí jména
-   **service sluzba restart**
    restart démona
-   **/sbin/mkbootdisk kernelversion**
    vytvoøení bootovací diskety, kernelversion se zjistí pøíkazem uname
    -r
-   **printconf-gui**
    definice tiskárny - pøes jinou stanici (print server)
-   **host jmeno_stanice**
    vypise IP adresu, aliasy stanice

------------------------------------------------------------------------

### [RPM]{#LIN.RPM}

------------------------------------------------------------------------

-   **rpm -i nazev_balicku.rpm**
    instalace balíèku
-   **rpm \--rebuild nazev_balicku.src.rpm**
    pøekompilovaní zdroje, vytvoøení binárního rpm - uloží je do
    /usr/src/redhat/RPMS/i386,
    pak nainstalovat: rpm -i vytvoreny_balicek
-   **rpm -Uvh nazev_balicku.rpm**
    upgrade balíèku
-   **rpm -e nazev_balicku.rpm**
    odstranìní balíèku
-   **rpm -qa**
    výpis všech nainstalovaných balíèkù
-   **rpm -ql nazev_balicku.rpm**
    vypíše seznam všech souborù, které balíèek obsahuje
-   **rpm -qi nazev_balicku.rpm**
    zobrazí hlavièku s informacemi o balíèku
-   **rpm -qf jmeno_knihovny**
    vypise balicek, ktery knihovnu obsahuje
-   **rpm -dbpath/usr/lib/rpmdb/i386-redhat-linux/redhat -qal \| grep
    ndbm.h**
    dotaz do databáze, kde je soubor ndbm.h\
    odpovìïé /usr/include/db1/ndbm.h
-   **rpm -dbpath/usr/lib/rpmdb/i386-redhat-linux/redhat -qf
    /usr/include/db1/ndbm.h**
    dotaz do databáze, kde je soubor /usr/include/db1/ndbm.h\
    jmeno balíèku: /qlibc-devel-2.1.2-11
-   **rpm -i \--force \--nodeps nazev_balicku.rpm**
    pøi instalaci nejsou kontrolovány závislosti a nereaguje na chyby a
    balíèek
    nainstaluje

------------------------------------------------------------------------

### [YUM, APT]{#LIN.YUM}

------------------------------------------------------------------------

Oba programy mají seznam zdrojù dostupných na Internetu, lokální síti èi
výmìnném mediu, dokáží stáhnout balíèek, zjistí závislosti, dokáží
upgradovat. Využívají služeb rpm.

-   **yum**
    -   **yum search string**
        najde balíèky obsahující øetìzec (v popisu balíèku) vèetnì
        závislostí
    -   **yum install pkg1 \[pkg2 \...\],**
        instaluje balíèky
    -   **yum update pkg**
-   **apt**
    -   **apt-get update**
        synchronizuje index file zdrojù
    -   **apt-cache showpkg pkg1 \...**
        vypíše balíèky, najde závislosti
    -   **apt-get install pkg1 \...**

------------------------------------------------------------------------

### [Informace o hw, syst.]{#LIN.INF}

------------------------------------------------------------------------

-   **/sbin/arp -a**
    vypíše intern. i HW adresy všech hostitelù
-   **dmesg** \[volby\]
    zobrazí øídící zprávy systému od posledního restartu
-   **free** \[volby\]
    zobrazí statistické informace o využití pamìti
-   **fuser** \[volby\] soubor \... \[-\]
    vypíše PID procesù, které používají zadané soubory nebo souborové
    systémy
-   **groups** \[uzivatel\]
    vypíše skupiny, do kterých náleží zadaný uživatel
-   **host** \[volby\] hostitel \[server\]
    vypíše informace o specifikovaných hostitelích
-   **hostname -s** - vypíše jméno stanice
    **hostname -d** - vypíše jméno domainy
    **hostname -i** - vypíše IP adresu
-   **/sbin/ifconfig**
    vypíše ethernet. adresu, masku, inter. adresu
-   **informace o systému**
    less **/var/log/dmesg**
    v adresáøi **/proc** (less cpuinfo, less meminfo, \...)
-   **logname** \[volby\]
    vypíše jméno uživatele
-   **/sbin/lsmod** \[volby\]
    vypíše moduly vložené do kernelu
-   **man -a prikaz**
    vypíše mananualové stránky ze všech sekcí
-   **netstat** \[volby\]
    zobrazuje sí?ovou statistiku
    **netstat -r** zobrazí smìrovací tabulku jádra
-   **nslookup** \[ - volba\] \[hledany_hostitel \| - \[server\]\]
    slouží pro dotazování serveru internetových domainových jmen
-   **pidof** \[volby\] \[programy\]
    zobrazí PID zadaných programù
-   **/sbin/route**
    vypíše IP adresu, gateway, mask
-   **runlevel**
    zobrazí pøedcházející a aktuální úroveò bìhu
-   **rusers** \[volby\] \[pocitac\...\]
    vypíše seznam uživatelù pøihlášených na poèítaèích v lokální síti
    (obdoba **who** na vzdálených poèítaèích)
-   **showmount** \[volby\] \[hostitel\]
    zobrazí informace o serveru NFS
-   **traceroute** \[volby\] hostitel \[velikost_paketu\]
    zjiš?uje cestu, kterou se packet dostává k sí?ovému hostiteli
-   **uname** \[volby\]
    vypíše informace o poèítaèi a o operaèním systému
-   **chkconfig \--list**
    vypíše inforace o službách, které jsou pro rùzné levely spuštìné

------------------------------------------------------------------------

### [Zapomenuté heslo pro root]{#LIN.PASS}

------------------------------------------------------------------------

Reboot pocitaèe - zastavit \[CTRL\] \[X\]\

Pøi promptu boot:

**linux single**\

Pøi promptu bash#\

**passwd root**

Nastavit heslo\

**shutdown -r now**

------------------------------------------------------------------------

### [Mathematica - fonty]{#LIN.MATH}

------------------------------------------------------------------------

    Pøidání fontù mathematica lokálnì na linuxové poèítaèe pc152c (noe1), pc182c (noe2), pc211c (noe3):

    cd /usr/share/fonts
    mkdir mathematica

    scp -r jonas:/usr/local/Wolfram/Mathematica/5.0/SystemFiles/Fonts/* \ 
        /usr/share/fonts/mathematica

    Opravit konfiguraèní file:

    vi /etc/X11/fs/config

    pøidat 4 øádky (adresáøe fontù pro mathematica)

        /usr/share/fonts/mathematica/AFM,
        /usr/share/fonts/mathematica/BDF,
        /usr/share/fonts/mathematica/Common,
        /usr/share/fonts/mathematica/Type1,

    Restart fontserveru:
        service xfs start
        
    Restart xserveru:  reboot

------------------------------------------------------------------------

### [hpacucli - utilita pro konfiguraci diskového pole]{#LIN.HPACUCLI}

------------------------------------------------------------------------

    hp array configuration utility command line interface

    Pøíklad pro linux054b.fzu.cz (samson)- physical drive


     /usr/sbin/hpacucli ctrl slot=0 pd all show status

        physicaldrive 2:0 (port 2:id 0, 300 GB): OK
        physicaldrive 2:1 (port 2:id 1, 300 GB): OK
        physicaldrive 2:2 (port 2:id 2, 300 GB): OK
        physicaldrive 2:3 (port 2:id 3, 300 GB): OK
        physicaldrive 2:4 (port 2:id 4, 300 GB, spare): OK
        physicaldrive 2:5 (port 2:id 5, 300 GB, spare): OK

        (4 disky v RAID 5, 2 spare disky)

    Dalí pøíklady výpisu statusu:

     /usr/sbin/hpacucli ctrl all show status

        Smart Array 6i in Slot 0
           Controller Status: OK
           Cache Status: OK
           Battery Status: OK

    Výpis pro logical drive:

     /usr/sbin/hpacucli ctrl slot=0 ld all show 

        Smart Array 6i in Slot 0

          array A
          logicaldrive 1 (838 GB, RAID 5, OK)

------------------------------------------------------------------------

### [Imggen - utilita pro zašifrování textu do obrázku - ochrana proti spamerùm]{#LIN.IMGGEN}

------------------------------------------------------------------------

-   Na stránce **http://www-hep.fzu.cz/tools/imggen/crypttext.aspx**
    napíšeme požadovaný text\
    (napø. **emailovou adresu**) a zadáme pøíkaz **Zašifrovat**. Zobrazí
    se zašifrovaný text.
-   **Šifrovaný text vložíme do filu jako obrázek**\
    \<img
    src=:http://www-hep.fzu.cz/tools/imggen/genpic.aspx?text=zasifrovany_text\"
    alt=\"nahradni_text\"\>
-   Grafický výstup lze ovlivnit parametry:
    -   bgcolor=rrggbb - barva pozadí (default ffffff - bilá)
    -   wsize=int - šíøka obr. (default 100)
    -   hsize=int - výška obr. (default 15)
    -   font=string - typ písma (default Times)
    -   fontsize=int - velikost písma (default 16)
    -   fontcolor=rrggbb - barva písma (default 000000 - èerná)
-   Pøíklad: \<img
    src=:http://www-hep.fzu.cz/tools/imggen/genpic.aspx?text=zasifrovany_text&hsize=20&wsize=120\"
    alt=\"nahradni_text\"\>
-   Upozorneni: V pripade ze zadate nektery parametr spatne, vysledny
    obrazek se nezobrazi

------------------------------------------------------------------------

J.K.
