---
title: "skoleni-unix-1.html"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/internet/unix-lekce/skoleni-unix-1.html"
date: 2009-05-01
type: HTML
---

[Dal¹í](http://www.kiv.zcu.cz/%7Etxkoutny/common/ups/skoleni/skoleni-unix-2.html)
Pøedchozí
[Obsah](http://www.kiv.zcu.cz/%7Etxkoutny/common/ups/skoleni/skoleni-unix.html#toc1)

------------------------------------------------------------------------

## [1. Souborový systém UNIXu]{#s1}

Døív ne¾ budete moci nastavovat slo¾itìj¹í èásti systému, bude dobré se
nauèit nìco o tom, jak je systém organizován a jaké pøíkazy je mo¾né
pou¾ívat k vyhledávání souborù a programù. Tato kapitola vás obeznámí s
organizací systému.

## [1.1 Struktura souborového systému]{#ss1.1}

První výrazný rozdíl mezi Unixem a jinými systémy najdeme v uspoøádání
souborového systému. Pro zaèáteèníky: Nepou¾ívají se písmena k
oznaèování diskových oddílù. Pod Unixem máme jeden hlavní adresáø.
Mù¾ete si ho pøedstavit tøeba jako C: pod DOSem. Ka¾dý oddíl ve va¹em
systému je mountován (pøipojován) do adresáøe v onom hlavním adresáøi.
Vypadá to jako nìjaký stále se nafukující harddisk.

Tomuto hlavnímu adresáøi øíkáme *root* (koøenový) adresáø a oznaèujeme
jej prostì lomítkem (`/`{.FILENAME}). Toto pojetí mo¾ná vypadá podivnì,
ale ve skuteènosti vám velmi usnadòuje ¾ivot v situaci, kdy chcete
diskový prostor roz¹íøit. Napøíklad se vám stane, ¾e u¾ se nevejdete na
disk, kde máte pøipojený adresáø `/home`{.FILENAME}. Tak¾e, kdy¾ diskový
oddíl mù¾e být pøipojen pod libovolný adresáø, mù¾ete jednodu¹e skoèit
do obchodu, koupit tam dal¹í harddisk a namountovat (pøipojit) si jej
pod adresáø `/home`{.FILENAME}. No a máte \"naroubováno\" o nìco více
prostoru do va¹eho systému. A to v¹e bez nutnosti hýbat s mnoha vìcmi
okolo.

Dále si popí¹eme hlavní adresáøe nacházející se na nejvrchnìj¹í úrovni
souborového systému Unixu.

`/bin`{.FILENAME}
:   Zde jsou ulo¾eny ty nejzákladnìj¹í u¾ivatelské programy. Ty
    pøedstavují nejminimálnìj¹í sadu programù nutných k tomu, aby
    u¾ivatel mohl systém pou¾ívat. Jsou tu ulo¾eny takové vìci, jako je
    shell, pøíkazy souborového systému (`ls`{.FILENAME},
    `cp`{.FILENAME}) a podobnì. Adresáø `/bin`{.FILENAME} se po
    nainstalování systému u¾ zpravidla nemìní. Pokud ano, tak obvykle
    jen z dùvodu upgradu softwarových balíèkù.

`/dev`{.FILENAME}
:   Se v¹emi vìcmi v Unixu se zachází jako se soubory. Tak¾e i s
    hardwarovými zaøízeními jako napø. sériovými porty, harddisky a
    scanery. Abychom mohli k tìmto zaøízením pøistupovat, musí být
    pøítomen speciální soubor nazývaný \"device node\". V¹echy \"device
    nodes\" jsou ulo¾eny v adresáøi `/dev`{.FILENAME}.

`/etc`{.FILENAME}
:   V tomto adresáøi jsou ulo¾eny systémové konfiguraèní soubory.
    V¹echno od konfigruaèních souborù pro X Window, pøes u¾ivatelské
    databáze a¾ po systémové startovací skripty je zde. Systémový
    administrátor se èasem s tímto adresáøem hodnì s¾ije.

`/home`{.FILENAME}
:   Unixx je víceu¾ivatelský operaèní systém. Ka¾dému u¾ivateli je v
    systému zøízen úèet a jedineèný adresáø pro jeho osobní soubory.
    Tento adresáø je nazýván jako u¾ivatelùv domovský (home). Adresáø
    `/home`{.FILENAME} je pou¾íván jako defaultní lokace pro umístìní
    u¾ivatelských domovských adresáøù.

`/lib`{.FILENAME}
:   Zde jsou ulo¾eny systémové knihovny, které jsou vy¾adovány pro
    základní operace. Najdeme tu napøíklad knihovnu jazyka C, dynamický
    zavadìè, knihovnu ncurses, moduly jádra, atd.

`/proc`{.FILENAME}
:   Toto je velmi zvlá¹tní adresáø. Ve skuteènosti není èástí
    souborového systému, ale je virtuálním souborovým systémem, který
    poskytuje pøístup k informacím jádra. Rùzné informace, které vám
    chce kernel dávat na vìdomí, jsou vám dávány prostøednictvím
    \"souborù\" v adresáøi `/proc`{.FILENAME}. Rovì¾ vy mù¾ete zasílat
    informace do kernelu prostøednictvím nìkterých tìchto \"souborù\".
    Vyzkou¹ejte si tøeba `cat /proc/cpuinfo`{.USERINPUT}.

`/root`{.FILENAME}
:   Správce systému - administrátor - je systému znám pod jménem root.
    Rootùv domovský adresáø je v `/root`{.FILENAME} místo v
    `/home/root`{.FILENAME}. Dùvod k tomu je jednoduchý. Co kdyby
    `/home`{.FILENAME} byl na jiném diskovém oddílu ne¾ `/`{.FILENAME} a
    nemohl by být pøipojen? Root by se mìl pøirozenì pøihlásit do
    systému a opravit tento problém. Kdyby byl jeho domovský adresáø na
    po¹kozeném filesystému, asi by mu to pøihla¹ování hodnì
    zkomplikovalo.

`/sbin`{.FILENAME}
:   Zde jsou programy, které mù¾e spou¹tìt jen root a nebo které jsou
    spou¹tìny v prùbìhu startu systému. Normální u¾ivatelé nemohou
    spou¹tìt programy z tohoto adresáøe.

`/tmp`{.FILENAME}
:   Místo pro umis»ování doèasnì existujících souborù. V¹ichni u¾ivatelé
    mohou z tohoto adresáøe èíst i zapisovat do nìj.

`/usr`{.FILENAME}
:   Toto je nejvìt¹í adresáø v linuxovém systému. V¹echno ostatní musí
    jít hezky sem: Programy, dokumentace, zdrojový kód kernelu a X
    Window systém. Vìt¹inu programù budete instalovat do tohoto
    adresáøe.

`/var`{.FILENAME}
:   Systémové logovací soubory, cache data a programové zámky jsou
    ukládány sem. Toto je adresáø pro èasto se mìnící data.

## [1.2 Zji¹tìní aktuálního adresáøe - pøíkaz pwd]{#ss1.2}

Syntaxe tohoto pøíkazu je velmi jednoduchá:

> ` `
>
> ------------------------------------------------------------------------
>
>     $ pwd
>     /usr/bin
>
> ------------------------------------------------------------------------

## [1.3 Vytvoøení adresáøe - pøíkaz mkdir]{#ss1.3}

Pøíkazem `mkdir` vytvoøíte nový adresáø. Následující pøíklad vytvoøí
adresáø `manka` v aktuálním adresáøi:

> ` `
>
> ------------------------------------------------------------------------
>
>     $ mkdir manka
>
> ------------------------------------------------------------------------

Taky mù¾ete zadat cestu:

> ` `
>
> ------------------------------------------------------------------------
>
>     $ mkdir /usr/local/manka
>
> ------------------------------------------------------------------------

Volbou `-p` øekneme mkidiru, aby vytvoøil i nadøízené adresáøe. Vý¹e
uvedený pøíklad toti¾ zhavaruje, pokud `/usr/local` neexistuje. Volba
`-p` zajistí i vytvoøení `/usr/local`:

> ` `
>
> ------------------------------------------------------------------------
>
>     $ mkdir -p /usr/local/manka
>
> ------------------------------------------------------------------------

## [1.4 Zmìna adresáøe - pøíkaz cd]{#ss1.4}

Pøíkaz `cd` se pou¾ívá ke zmìnì pracovního (aktuálního) adresáøe.
Jednodu¹e napí¹te `cd` následovaný jménem cesty k adresáøi. Zde je pár
pøíkladù:

> ` `
>
> ------------------------------------------------------------------------
>
>     darkstar:~$ cd /bin
>     darkstar:/bin$ cd usr
>     bash: cd: usr: No such file or directory
>     darkstar:/bin$ cd /usr
>     darkstar:/usr$
>
> ------------------------------------------------------------------------

## [1.5 Mazání adresáøe - pøíkaz rmdir]{#ss1.5}

Pøíkazem `rmdir` se ma¾ou adresáøe. Pøed vymazáním musí být adresáø
prázdný, jinak se vymazání neprovede. Syntaxe je jednoduchá:

> ` `
>
> ------------------------------------------------------------------------
>
>     $ rmdir <directory>
>
> ------------------------------------------------------------------------

Následující pøíklad vyma¾e podadresáø `cipisek` z aktuálního adresáøe.
Kdyby adresáø `cipisek` neexistoval, `rmdir` vám to poví:

> ` `
>
> ------------------------------------------------------------------------
>
>     $ rmdir cipisek
>
> ------------------------------------------------------------------------

Rovnì¾ mù¾ete smazat adresáø vèetnì jeho nadøízených adresáøù zadáním
volby `-p`. Systém se nejdøíve pokusí smazat adresáø `hejaz` uvnitø
adresáøe `/tmp`. Pokud se to podaøí, bude se dále sna¾it smazat adresáø
`/tmp`. `rmdir` pokraèuje v mazání tak dlouho, dokud se buï neobjeví
chyba, nebo dokud není celý zadaný strom smazán.

> ` `
>
> ------------------------------------------------------------------------
>
>     $ rmdir -p /tmp/hejaz
>
> ------------------------------------------------------------------------

## [1.6 Vlastnictví souborù]{#ss1.6}

Unix je víceu¾ivatelský operaèní systém. Ka¾dý aspekt tohoto systému je
víceu¾ivatelský, i souborový systém. Systém ukládá informace o tom kdo
vlastní soubor a kdo jej smí èíst. Jsou tu i dal¹í úkoly souborového
systému, jako odkazy.

Souborový systém ukládá informace o vlastnictví pro ka¾dý soubor a
adresáø v systému. Tj. který u¾ivatel a skupina vlastní ten který
soubor. Nejsnaz¹í zpùsob jak zobrazit tyto informace je pou¾ít pøíkaz
`ls`:

> ` `
>
> ------------------------------------------------------------------------
>
>     $ ls -l /usr/bin/wc
>     -rwxr-xr-x   1 root     bin    7368 Jul 30  1999 /usr/bin/wc
>
> ------------------------------------------------------------------------

Zajímá nás tøetí a ètvrtý sloupec. Ty obsahují jméno u¾ivatele a
skupiny, kteøí vlastní tento soubor. Vidíme, ¾e tento soubor vlastní
u¾ivatel `root` a skupina `bin`.

Vlastníky mù¾eme mìnit pøíkazy `chown` (znaèí \"change owner\" - zmìò
vlastníka) a `chgrp` (znaèí \"change group\" - zmìò skupinu). Abychom
zmìnili vlastníka souboru na `daemon`, pou¾ijeme `chown`:

> ` `
>
> ------------------------------------------------------------------------
>
>     # chown daemon /usr/bin/wc
>
> ------------------------------------------------------------------------

Ke zmìnì skupiny vlastníkù na `root` pou¾ijeme `chgrp`:

> ` `
>
> ------------------------------------------------------------------------
>
>     # chgrp root /usr/bin/wc
>
> ------------------------------------------------------------------------

Pomocí `chown` mù¾eme zmìnit i vlastníka i skupinu:

> ` `
>
> ------------------------------------------------------------------------
>
>     # chown daemon.root /usr/bin/wc
>
> ------------------------------------------------------------------------

## [1.7 Pøístupová práva]{#ss1.7}

Práva (permissions) jsou dal¹í dùle¾itou úlohou víceu¾ivatelského
aspektu souborového systému. S jejich pomocí mù¾ete mìnit kdo smí èíst,
zapisovat a spou¹tìt soubory.

Informace o právech jsou ukládána jako ètyøi osmièkové èíslice, ka¾dá
specifikuje jinou mno¾inu práv. Jsou to práva pro vlastníka, skupinu a
ostatní (world). Ètvrá cifra je pou¾itá k ulo¾ení speciálních informací
jako je nastavené u¾ivatelské ID, nastavené skupinové ID a \"sticky\"
bit. Osmièkové hodnoty pøidìlené módùm oprávnìní jsou (mají té¾
pøidìlená písmena, která zobrazují programy jako `ls` a mohou být
vyu¾ívána programem `chmod`):

  ---------------------------- ------------------- ----------------------
  Druh práva Permission Type   Osmièková hodnota   Písmenkové vyjádøení
  \"sticky\" bit               1                   t
  nastav ID u¾ivatele          4                   s
  nastav ID skupiny            2                   s
  ètení                        4                   r
  zápis                        2                   w
  spou¹tìní                    1                   x
  ---------------------------- ------------------- ----------------------

Pro ka¾dou skupinu práv zadáváte osmièkové hodnoty. Napøíklad pokud
chcete aby práva skupiny byla \"ètení\" a \"zápis\", mìli byste pro
práva skupiny zadat \"6\".

Pro zmìnu práv pou¾ijeme pøíkaz `chmod` (co¾ znamená \"change mode\" -
\"zmìò mód\"), kterým nastavíme práva souboru `example`. Nastavte
osmièková èísla práv, která chcete. Aby vlastník mohl èíst, psát a
spou¹tìt, mìl by mít hodnotu 7. Èíst a spou¹tìt by bylo 5. Dejte to
dohromady a zadejte to do pøíkazu `chmod`:

> ` `
>
> ------------------------------------------------------------------------
>
>     $ chmod 755 /tmp/example
>     $ ls -l /tmp/example
>     -rwxr-xr-x   1 david    users    0 Apr 19 11:21 /tmp/example
>
> ------------------------------------------------------------------------

K nastavení zvlá¹tních oprávnìní zadáme èísla do prvního sloupce.
Napøíklad k nastavení ID u¾ivatele a ID skupiny dáme do prvního sloupce
\"6\":

> ` `
>
> ------------------------------------------------------------------------
>
>     $ chmod 6755 /tmp/example
>     $ ls -l /tmp/example
>     -rwsr-sr-x   1 david    users    0 Apr 19 11:21 /tmp/example
>
> ------------------------------------------------------------------------

Pokud vás osmièková èísla pletou, mù¾ete místo nich pou¾ívat písmena.
Skupiny oprávnìní pro `chmod` pak vypadají takto:

  ----------------- ---
  Vlastník          u
  Skupina           g
  Ostatní           o
  V¹ichni zmínìní   a
  ----------------- ---

Abychom dosáhli toho, co nahoøe, museli bychom pou¾ít nìkolik
pøíkazových øádkù:

> ` `
>
> ------------------------------------------------------------------------
>
>     $ chmod a+rx /tmp/example
>     $ chmod u+w /tmp/example
>     $ chmod ug+s /tmp/example
>
> ------------------------------------------------------------------------

Nìkteøí lidé dávají pøednost písmenùm pøed èíslicemi. Obì cesty vyús»ují
do té samé sady oprávnìní.

Na nìkolika místech jsme se zmínili o nastavování ID u¾ivatele a ID
skupiny. Mo¾ná si øíkáte, o co jde? Obyèejnì, kdy¾ spustíte program, ten
pak pracuje pod va¹ím u¾ivatelským úètem. To znamená, ¾e má v¹echa ta
oprávnìní, která máte vy jako u¾ivatel. Toté¾ platí pro skupinu.
Jestli¾e spustíte program, vykonává se pod va¹í souèasnou skupinou. S
nastaveným oprávnìním ID u¾ivatele si mù¾ete vynutit, aby program v¾dy
bì¾el jako majitel programu (tøeba jako \"root\"). Nastavení ID skupiny
je toté¾, ale pro skupinu.

Zacházejte s tím opatrnì. Nastavení ID u¾ivatele a ID skupiny programùm
mù¾e ve va¹em systému otevøít významné bezpeènostní mezery. Pokud èasto
nastavujete ID u¾ivatele programùm, které vlastní \"root\", povolíte
ka¾dému, aby provozoval tento program stejnì jako root. A proto¾e root
nemá v systému ¾ádná omezení, mù¾ete si sami pøedstavit, jak velký
bezpeènostní problém to je. Struènì øeèeno, není ¹patné pou¾ívat
nastavení oprávnìní ID u¾ivatele a ID skupiny, ale dìlejte to s citem.

## [1.8 Odkazy na soubory]{#ss1.8}

Odkazy (links) jsou ukazovátka mezi soubory. Pomocí odkazù mù¾ete mít
soubory na mnoha místech a mít je pøístupné pod mnoha názvy. Existují
dva typy odkazù: Pevné a symbolické.

Pevné odkazy jsou názvy pro konkrétní soubor. Ty mohou existovat pouze
uvnitø jediného adresáøe a jsou vyjmuty jedinì tehdy, kdy¾ je ze systému
vyjmuto reálné jméno. Jsou v urèitých pøípadech u¾iteèné, ale mnoho
u¾ivatelù shledává symbolické linky mnohostrannìj¹ími.

Symbolický odkaz, té¾ nazývaný \"mìkký\", mù¾e ukazovat na soubor vnì
svého adresáøe. Je to vlastnì malý souborek, obsahující informaci,
kterou potøebuje. Symbolické odkazy mù¾ete pøidávat i mazat bez zasa¾ení
vlastního souboru

Odkazy nemají svou vlastní sadu práv èi vlastnictví, ale místo toho je
pøebírají od souboru, na který ukazují. Zde je obecný pøíklad:

> ` `
>
> ------------------------------------------------------------------------
>
>     $ ls -l /bin/sh
>     lrwxrwxrwx   1 root     root     4 Apr  6 12:34 /bin/sh -> bash
>
> ------------------------------------------------------------------------

Odkazy se vytváøejí pøíkazem `ln`:

> ` `
>
> ------------------------------------------------------------------------
>
>     $ ln soubor [jméno_odkazu]
>
> ------------------------------------------------------------------------

Pøíkaz vytvoøí odkaz na soubor. Není-li uveden druhý parametr, pak je
odkaz vytvoøen v aktuálním adresáøi a dostane stejné jméno, jako
originální soubor. Uvedeným zpùsobem vytvoøíte odkaz pevný. Pro
vytvoøení symbolického odkazu pøidejte za pøíkaz `ln` parametr `-s`.

> ` `
>
> ------------------------------------------------------------------------
>
>     $ ln -s soubor [jméno_odkazu]
>
> ------------------------------------------------------------------------

## [1.9 Mountování diskù]{#ss1.9}

V Unixu se diskové zaøízení musí nejdøív pøipojit k souborovému systému.
Bì¾nì se to nazývá pøimountovat. V Unixu toti¾ nemají jednotlivé disky
písmenka, jako ve windows, disk se musí pøipojit k nìjakému adresáøi a
po jeho pøípojení v tom adresáøi bude obsah toho disku. Po práci je
potøeba disk zase odmountovat, speciálnì se to týká disket, pøed tím ne¾
se vyndá tak se musí odmountovat, jinak pøijdete s velkou
pravdìpodobností o data. Data se na disketu zapisují se zpo¾dìním a kdy¾
dáte pøíkaz k odmountování, tak se teprve zapí¹í. Kdy¾ vytáhnete
neodmountovanou disketu, koledujete si o problémy, nejen ¾e mù¾ete
pøijít o data, ale nepùjde vám pøimountovat ani dal¹í disketa.

S cédéèky je to podobné, ale snaz¹í. Zaprve se na nì nic nezapisuje a
zadruhé Unix nedovolí otevøít dvíøka mechaniky, dokud není cédéèko
odpojeno. Mù¾e se vým stát, ¾e disk nepùjde odpojit. To znamená, ¾e
nìkterý program pøistupuje k tomu disku, napø. má otevøen soubor, který
se na disku nachází. Musíte tomu programu øíct, a» ten soubor zavøe a
nebo ten program ukonèit. Nemusí jít jen o otevøený soubor, staèí abyste
mìli v `mc` zobrazen obsah toho disku v panelu s kurzorem (pak je
adresáø toho disku pracovním adresáøem mc) a u¾ také nepùjde odpojit.
Kdy¾ nebudete tu¹it, kde to vázne, pomù¾e vám pøíkaz `fuser` (jako root
dejte na zkou¹ku pøíkaz `fuser -v /` a zjistíte co v¹echno vám visí na
disku pøipojeném ke koøenovému adresáøi).

Obecnì se mountování disku dìlá pøíkazem `mount` a odmountování pøíkazem
`umount`. Proto¾e nìkteré disky se mountují pravidelnì nebo se spoustou
rùzných parametrù, tøeba hardisky, a bylo by nepohodlné je po ka¾dém
startu poèítaèe èi v pøípadì potøeby mountovat ruènì, je tu konfiguraèní
soubor `/etc/fstab`, v kterém si mountování disku mù¾ete
pøedkonfigurovat. Mù¾ete i zadat, které disky se mají pøimountovat
rovnou pøi startu poèítaèe.

Obecnì je pøi mountování potøeba zadat:

1.  typ souborového systému, který je na disku
2.  zaøízení (disk) který chcete pøimountovat
3.  adresáø, ke kterému se ma disk pøimountovat

Disketu s win formátem (FAT) pak mù¾ete pøimountovat pøíkazem:

> ` `
>
> ------------------------------------------------------------------------
>
>     $ mount -t vfat /dev/fd0 /mnt/fd0
>
> ------------------------------------------------------------------------

-   `-t vfat` je typ souborového systému, místo vfat mù¾ete zadat jiný,
    tøeba cdromy mají iso9660. Pøíkaz mount umí nìkteré poznat sám,
    tak¾e to mù¾ete zkusit i bez tohoto parametru, a teprve, kdy¾
    obdr¾íte chybové hlá¹ení, ¾e mount nedokázal rozeznat formát, zadáte
    mu jej ruènì.
-   `/dev/fd0` je zaøízení \'první disketovka\' ve windows známá jako
    a:\
    `/dev/fd1` je druhá\
    `/dev/hda1` je první partition prvního ide disku (primary master)\
    `/dev/hdc6` je ¹está partition tøetího ide disku (secondary master)
    a tak dále.
-   `/mnt` je adresáø v koøenovém adresáøi, zadaný adresáø musí
    existovat.

V souboru `/etc/fstab` mù¾ete mít pak tento øádek:

> ` `
>
> ------------------------------------------------------------------------
>
>       /dev/fd0       /mnt/fd0               auto    noauto,user,showexec=no       0 0
>
> ------------------------------------------------------------------------

Tento øádek znamená, ¾e máte pøedkonfigurováno pøipojení první
disketovky k adresáøi `/mnt/fd0` s automatickým rozli¹ováním formátu
(auto) a s nìjakým dal¹ím nastavením (noauto znamená nepøipojovat
automaticky po startu a tak podobnì). Parametry jsou oddìleny èárkami a
NESMÍ být mezi nimi mezera. Kdy¾ máte toto pøedkonfigurování, staèí vám
pak jen dát pøíkaz:

> ` `
>
> ------------------------------------------------------------------------
>
>     $ mount /mnt/fd0
>
> ------------------------------------------------------------------------

a Unix si u¾ to ostatní doplní a disk pøipojí. Po skonèení práce dejte
pøíkaz:

> ` `
>
> ------------------------------------------------------------------------
>
>     $ umount /mnt/fd0
>
> ------------------------------------------------------------------------

a to je v¹echno. V pøípadì potí¾í:

> ` `
>
> ------------------------------------------------------------------------
>
>     $ fuser /mnt/fd0
>
> ------------------------------------------------------------------------

## [1.10 Soubor fstab]{#ss1.10}

> ` `
>
> ------------------------------------------------------------------------
>
>     # Ukazka moznosti pripojovaji v souboru /etc/fstab
>     #
>     # poradi udaju (oddluji se mezerami nebo tabulatory):
>     # svazek(zarizeni) pripojny_bod typ_soub_systemu volby,oddelene,carkama priznak_zalohovani kontorla_fsck
>     #
>     # Podrobnosti viz:
>     #  $ man fstab
>     #  $ man mount
>
>     # pripojeni root oddilu
>     LABEL=/     /                  ext2      defaults                       1 1
>
>     # (pred)pripojeni CD-ROM - druhy radek jen cteni bez prava spoustet programy
>     # treti radek pripojuje vypalovacku (propojuje se jako SCSI CD)
>     /dev/cdrom  /mnt/cdrom  iso9660   noauto,owner,ro                0 0
>     /dev/cdrom  /cd     iso9660   noauto,owner,ro,user,mode=0444 0 0
>     /dev/scd0   /mnt/scsi_cd    auto    noauto,iocharset=8859-2,umask=0,codepage=852,ro,exec    0 0
>
>     # (pred0pripojovani disketove jednotky
>     /dev/fd0    /mnt/floppy        auto      noauto,owner                   0 0
>     /dev/fd0    /a                 auto      noauto,owner,noexec            0 0
>
>     # pripojeni oddilu /usr
>     LABEL=/usr  /usr               ext2      defaults                       1 2
>
>     # pripojeni virtualniho filesystemu /proc a /dev/pts
>     none        /proc              proc      defaults                       0 0
>     none        /dev/pts           devpts    gid=5,mode=620                 0 0
>
>     # tomuhle nejak nerozumim :o) - ze by pripojeni ftp oddilu z ip 192.168.10.2 ?
>     none        /mnt/fm            ftpfs     noauto,owner,user,ip=192.168.10.2,user=cf,pass=cf-pwd,ro 0 0
>
>     # pripojeni swap oddilu (je na dvou ruznych discich)
>     /dev/hda3   swap               swap      defaults                       0 0
>     /dev/hdb3   swap               swap      defaults                       0 0
>
>     # pripojovani ruznych linuxovych oddilu
>     /dev/hdb2   /mnt/oldlin        ext2      defaults                       0 0
>     /dev/hdb7   /mnt/data          ext2      defaults                       0 0
>     /dev/hdb8   /mnt/oldlin/home   ext2      defaults                       0 0
>
>     # pripojovani ruznych FAT32 oddilu (MS Windows)
>     /dev/hda1   /mnt/windows    vfat    iocharset=8859-2,umask=0,codepage=852   0 0
>     /dev/hda5   /mnt/a5     vfat      user                           0 0
>
>     # pripojeni adresare z jineho pocitace pres nfs
>     /pocitac:/usr/share/soubory /mnt/poc_soub   nfs hard,intr
>
>     # pripojeni iso obrazu instalacnich cd RedHatu - tohle se mi genialne libi! :o)
>     /mnt/data2/enigma-i386-disc2.iso     /mnt/rh2  iso9660  loop,rw 0 0
>     /mnt/data/all/enigma-i386-disc1.iso  /mnt/rh1  iso9660  loop,rw 0 0
>
> ------------------------------------------------------------------------

------------------------------------------------------------------------

[Dal¹í](http://www.kiv.zcu.cz/%7Etxkoutny/common/ups/skoleni/skoleni-unix-2.html)
Pøedchozí
[Obsah](http://www.kiv.zcu.cz/%7Etxkoutny/common/ups/skoleni/skoleni-unix.html#toc1)
