---
title: "UvodDoUnixu.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/internet/unix-lekce/UvodDoUnixu.pdf"
date: 2009-05-01
type: PDF (text-based)
---

Úvod do systému UNIX

Studijní materiál pro cvičení z předmětu OSA

Úvod do operačního systému UNIX
UNIX je
• víceuživatelský (v systému může pracovat více uživatelů najednou) a
• víceúlohový (každý uživatel může mít spuštěno několik úloh)
operační systém.
Hlavní úlohou OS je
• řídit přidělování procesoru
• řídit přidělování paměti
• řídit přidělování prostoru na disku
• řídit obsluhu terminálů
• řídit obsluhu ostatních zařízení připojených k počítači
• poskytovat uživateli prostředí pro běžnou činnost

Některé vlastnosti OS UNIX:
• Jednoduché uživatelské rozhraní. Disponuje jak řádkovým, tak i grafickým UI.
• Hierarchický souborový systém.
• Vstup a výstup nezávislý na zařízení. Všechna zařízení se považují za soubory a
jako se soubory se s nimi i pracuje.
• Silný příkazový jazyk. Shelly UNIXu jsou opravdové programovací jazyky.
• Užitečné nástroje. UNIX obsahuje spoustu nástroju, které lze skládat do mnohem
složitějších programových celků. Najdete zde nástroje pro vyhledávání textů
v souborech, pro porovnávání souborů mezi sebou, prohledávání adresářů atd.
• Kompilátor jazyka C je součástí systému. (Spolu s debuggerem, profilerem a
dalšími analytickými nástroji.)
• Nástroje pro práci v síti (telnet, rlogin, ftp, ...).

První krůčky

Abyste mohli v UNIXu pracovat, musíte mít zavedené tzv. konto. Konta uživatelů zakládá
obvykle správce systému (superuživatel). Součástí vašeho konta přitom je
• Uživatelské jméno. Obvykle více než 6 znaků, musí začínat písmenem, casesensitive, jedinečné v celém systému.
• Heslo
• Primární skupina
• Uživatelské číslo (UID)
• Doplňující informace (jméno, příjmení, ...)
• Domovský adresář
• Shell (interpret příkazů)
• Další informace (čas posledního přihlášení, doba platnosti hesla, ...)
Práce v systému pak obvykle probíhá následovně:
1. Přihlášení
2. Vlastní relace
3. Odhlášení

login as: student0
Sent username "student0"
student0@labe.felk.cvut.cz's password:
Po úspěšném přihlášení se
• vypíší systémové zprávy
• vypíše se případné sdělení správce systému
• domovský adresář uživatele se nastaví jako pracovní
• spustí se požadovaný shell
Datum poslední aktualizace: 3.11.2004

1/11

Úvod do systému UNIX
•

Studijní materiál pro cvičení z předmětu OSA

vypíše se výzva shellu – prompt ($, >, … - liší pro jednotlivé shelly a lze jej
změnit)

Last login: Thu Oct 7 11:22:11 2004 from stud2-170.felk.cvut.cz
Copyright (c) 1980, 1983, 1986, 1988, 1990, 1991, 1993, 1994
The Regents of the University of California. All rights reserved.
FreeBSD 4.10-STABLE (Labe-4.9) #0: Tue Jul

6 10:30:35 CEST 2004

Welcome to FreeBSD!
labe:/home/student/student0 >
Odhlášení se provede stiskem ^D (konec vstupu z klávesnice). Jako opatření proti
náhodnému odhlášení bývá často ^D zablokováno a odhlašování se provádí voláním exit
nebo logout.

Zadávání příkazů

Zadávání příkazů se děje prostřednictvím tzv. shellu.

Shell

Shell je nejen interpret příkazů, ale celý programovací jazyk (skriptovací). Čte příkazy ze
souboru nebo terminálu a předává je k vykonání jádru, spouští požadované vnitřní a
vnější příkazy apod.
Nejznámější shelly:
• Bourne sh (sh) a jeho nástupce Bourne-again shell (bash)
• C-shell (sh) a jeho nástupce TC-shell (tcsh)
• Korn shell (ksh)
• Z-shell, …

Při zadávání příkazů je dobré vědět následující věci:
• UNIX je case-sensitive, tj. dělají se rozdíly mezi velkými a malými písmeny
• Shell interpretuje příkazy po stisku Enter
• Příkazy je možné zadávat do zásoby
• Některé shelly si pamatují historii příkazů a umožňují již zadané příkazy znovu
vyvolat a pozměnit
• Existují speciální znaky se zvláštním významem

Shell čte ze vstupu "slova" vzájemně oddělená "bílými znaky" (mezera, tabulátor).
Obecný formát příkazového řádku tedy je:
arg0 arg1 arg2 arg3 …

Řetězec arg0 je vždy jménem příkazu. Příkazy jsou vnitřní (implementovány v shellu
samotném) nebo vnější (realizované jako přídavná utilita uložená v systému souborů).
Řetězec arg0 se nejprve hledá v seznamu vnitřních příkazů a následně podle seznamu
cest v proměnné prostředí PATH.
V příkazovém řádku jsou dále identifikovány řídicí operátory a operátory přesměrování (i
uvnitř jednotlivých řetězců argX, tj. operátory nemusí být odděleny bílými znaky).
Každý příkaz při svém ukončení vrací návratovou hodnotu (exit status). Hodnota 0
znamená OK, cokoli jiného značí chybu.

Datum poslední aktualizace: 3.11.2004

2/11

Úvod do systému UNIX

Studijní materiál pro cvičení z předmětu OSA

Speciální znaky

Znaky se zvláštním významem. Mají své názvy, ale mohou se pod nimi skrývat různá
tlačítka na klávesnici.
Název
znaku
intr
quit
erase
kill
eof
stop
start
susp
...

Typická
klávesa
^C
^\
^h
^u
^d
^s
^q
^z
…

Popis
násilné ukončení běžícího procesu
ukončení programu
výmaz znaku
zrušení zadávaného řádku
konec vstupu – třeba z terminálu
pozastavení výpisu
pokračování ve výpisu
pozastavení procesu (používat uvážlivě,
nevyplácí se zapomínat procesy)
...

Pokud tyto speciální znaky potřebujete zadat do vstupu, musíte před nimi vložit “\”
(zpětné lomítko), aby ztratily svůj speciální význam.
Nastavení speciálních znaků je možné zjistit z nastavení vašeho terminálu příkazem
stty –a:
labe:/home/student/student0 > stty -a
speed 9600 baud; 24 rows; 80 columns;
<---cut--->
cchars: discard = ^O; dsusp = ^Y; eof = ^D; eol = <undef>;
eol2 = <undef>; erase = ^?; erase2 = ^H; intr = ^C; kill = ^U;
lnext = ^V; min = 1; quit = ^\; reprint = ^R; start = ^Q;
status = ^T; stop = ^S; susp = ^Z; time = 0; werase = ^W;
labe:/home/student/student0 >
Změna nastavení se provádí voláním stty <název- znaku> <klávesa>:
labe:/home/student/student0 > stty erase '^h'
labe:/home/student/student0 > stty -a
speed 9600 baud; 24 rows; 80 columns;
<---cut--->
cchars: discard = ^O; dsusp = ^Y; eof = ^D; eol = <undef>;
eol2 = <undef>; erase = ^H; erase2 = ^H; intr = ^C; kill = ^U;
lnext = ^V; min = 1; quit = ^\; reprint = ^R; start = ^Q;
status = ^T; stop = ^S; susp = ^Z; time = 0; werase = ^W;
labe:/home/student/student0 >
V tomto případě se změní klávesa pro výmaz znaku na Delete.

Oprava chyb

Chyby v zápisu příkazů (než je stisknuto Enter) lze provádět pomocí speciálních znaků
erase (^h - obvykle BackSpace, lze změnit např. na ^? - Delete) nebo kill (^u).
Poznámka: používáte-li terminálové emulátory (např. PuTTy), nastavení spec znaků
ztrácí svou důležitost, speciální znaky bývají často obhospodařovány emulátorem.

Systém souborů

Různé typy UNIXovských systémů používají různé systémy souborů:
Datum poslední aktualizace: 3.11.2004

3/11

Úvod do systému UNIX
•
•
•
•

Studijní materiál pro cvičení z předmětu OSA

ufs (Solaris)
efs (IRIX)
ext2fs (Linux)
…

UNIXovské systémy umí pracovat i s jinými systémy souborů, např. FAT, nfs, iso9660,
atd.

V UNIXech obvykle existuje několik typů souborů: adresáře, obyčejné soubory,
symbolické odkazy, speciální soubory a pojmenované roury.

Adresáře

Adresáře UNIXu nejsou nic jiného než soubory se speciálním obsahem. Obsahují v
podstatě tabulku položek o dvou polích: jméno souboru a číslo příslušného i-uzlu (i-uzel
je datová oblast na disku s informacemi o daném souboru, viz dále).
• Oddělovačem jmen adresářů je znak "/"
• Kořenový adresář "/"
• Pracovní adresář
• Absolutní ("/…/…/…") a relativní ("…/…/…") cesta
• V každém adresáři najdete dvě položky, které nejdou odstranit:
o "." aktuální adresář
o ".." nadřazený adresář

Obsah adresáře si lze prohlédnout příkazem ls. Výpis včetně skrytých souborů se
provede voláním ls –a. Rozšířený výpis s více informacemi o souborech lze vyvolat
pomocí ls –l. Výpis včetně čísel příslušných i-uzlů vykoná příkaz ls –i. Volby lze i
kombinovat, např. ls –lai.
Formát dlouhého výpisu pomocí ls –l:

drwxr-xr-x

2 student0

student

512 Oct 13 12:03 adresar

2

student0

student

drwxr-xr-x

typ souboru
a přístupová
práva

počet
odkazů
na
soubor

vlastník
souboru

skupina

512

velikost

Oct 13 12:03

datum a čas
poslední
aktualizace

adresar

jméno
souboru

Adresáře se vytvářejí příkazem mkdir.
labe:/home/student/student0 > ls
labe:/home/student/student0 > mkdir adresar
labe:/home/student/student0 > ls
adresar
labe:/home/student/student0 > ls -l
total 1
drwxr-xr-x 2 student0 student 512 Oct 13 12:03 adresar
labe:/home/student/student0 >
Přesun mezi adresáři (tj. změna pracovního adresáře) se provádí příkazem cd
<adresář>. Lze přitom použít absolutní i relativní cestu.
labe:/home/student/student0 > cd adresar
labe:...ent/student0/adresar > cd /
labe:/ > cd
labe:/home/student/student0 > cd /
labe:/ > cd ~student0
labe:/home/student/student0 > cd ~student1
Datum poslední aktualizace: 3.11.2004

4/11

Úvod do systému UNIX

Studijní materiál pro cvičení z předmětu OSA

labe:/home/student/student1 > ls
ahojda fa
soubor
labe:/home/student/student1 > cd
labe:/home/student/student0 >
V tomto příkladě jsme se nejprve přesunuli do vytvořeného adresáře „adresar“. Z něj
jsme přešli do kořenového adresáře (/). Příkazem cd bez argumentů jsme se vrátili do
našeho domovského adresáře. Podobně se lze do domovského adresáře uživatele vrátit i
voláním cd ~student0. Tímto způsobem lze ovšem rychle navštívit i domovské adresáře
jiných uživatelů (cd ~student1).
Odstranění adresářů se provádí příkazem rmdir.

labe:/home/student/student0 > ls
adresar
labe:/home/student/student0 > rmdir adresar
labe:/home/student/student0 > ls
labe:/home/student/student0 >
Výzva shellu je na mnoha systémech nastavena tak, aby obsahovala aktuální adresář (viz
příklady). Na některých systémech ale může výzvou být jen znak $ (nebo nějaký jiný).
Ke zjištění aktuálního adresáře pak můžete použít příkaz pwd.
labe:/home/student/student0 > pwd
/home/student/student0
labe:/home/student/student0 >

Soubory

Soubor je z hlediska systému pojmenovaná posloupnost bajtů a systému je jedno, jaký
význam tyto bajty mají (význam jim "přidělí" až programy, které je využijí). Každý
soubor, adresář nebo zařízení má v systému souborů alespoň jedno jméno:
• Jméno může být dlouhé max. 255 znaků. Je-li delší, zkracuje se bez varování.
• Může obsahovat libovolné znaky. Jediný nepřípustný znak je "/" (odděluje části
cesty). Nedoporučuje se ale používat ani znaky "?", "*", "[", "]", "\" a všechny
druhy apostrofů a uvozovek (mají speciální význam pro shell). Dobrým mravem je
omezit se jen na alfanumerické znaky a tečky.
• I jména souborů jsou case-sensitive.
• Zvláštní význam mají soubory se jménem začínajícím znakem ".". Jsou to většinou
různé konfigurační a záložní soubory. Neobjevují se ve výpisu příkazu ls, abychom
je viděli, musíme použít příkaz ls –a.

U textových souborů se pro oddělení řádků používá jen znak LF (na rozdíl od produktů
MS, které používají kombinaci CR LF).

Soubor lze vytvořit mnoha způsoby. Pro naše demonstrační účely poslouží příkaz touch
<soubor>, který založí prázdný soubor.
labe:/home/student/student0 > ls
labe:/home/student/student0 > touch pokus
labe:/home/student/student0 > ls -l
total 0
-rw-r--r-- 1 student0 student 0 Oct 13 12:37 pokus
labe:/home/student/student0 >
Ke kopírování souborů slouží příkaz cp <zdroj> <cíl>.
labe:/home/student/student0 > ls
pokus
Datum poslední aktualizace: 3.11.2004

5/11

Úvod do systému UNIX

Studijní materiál pro cvičení z předmětu OSA

labe:/home/student/student0 > cp pokus pokus-kopie
labe:/home/student/student0 > ls
pokus
pokus-kopie
labe:/home/student/student0 >
Přesouvání (a přejmenování) souborů se provádí podobně příkazem mv <zdroj> <cíl>.
labe:/home/student/student0 > ls
pokus
pokus-kopie
labe:/home/student/student0 > mv pokus novypokus
labe:/home/student/student0 > ls
novypokus
pokus-kopie
labe:/home/student/student0 >
Soubory se mažou příkazem rm <soubor>. Lze v něm používat i tzv. divoké znaky (*,
?). Volbou –r se zapíná rekurzivní výmaz včetně podadresářů (doporučuji používat tuto
volbu jen v případě, že si jste naprosto jistí, co chcete udělat; příkaz se na nic neptá a
rovnou výmaz provede). Volba –i zapíná interaktivní výmaz, tj. před smazáním každého
souboru se dotáže, zda tento konkrétní soubor chcete vymazat.
labe:/home/student/student0 > ls
novypokus
pokus-kopie
labe:/home/student/student0 > rm pokus-kopie
labe:/home/student/student0 > ls
novypokus
labe:/home/student/student0 > rm -i *
remove novypokus? y
labe:/home/student/student0 > ls
labe:/home/student/student0 >
Soubor lze naplnit daty opět různým způsobem. Pro naše účely využijeme operátoru
přesměrování >. Řetězec „Ahoj svete“ lze vložit do soubor třeba tak, že zadáme příkaz
echo Ahoj svete > nastext. Příkaz echo jen opisuje své argumenty na standardní
výstup. Ten jsme ale přesměrovali do souboru s názvem nastext. Celý příkaz proto
vytvoří soubor nastext, ktery bude obsahovat retezec Ahoj svete.
labe:/home/student/student0 > echo Ahoj svete > nastext
labe:/home/student/student0 > ls
nastext
Obsah souboru lze vypsat na monitor třeba příkazem more.
labe:/home/student/student0 > more nastext
Ahoj svete
labe:/home/student/student0 >

Symbolické odkazy

Symbolický odkaz je soubor, který zastupuje jiný soubor (zástupce jiného souboru,
pseudonym jiného souboru). Vytvářejí se příkazem ln –s <staré-jméno> <novéjméno>.

Kromě symbolických odkazů existují ještě pevné odkazy (vytvářejí se opět pomocí ln,
ovšem bez -s). Ty jsou ovšem málo flexibilní (neumožňovaly vytvářet odkazy na adresáře
a na soubory umístěné mimo aktuální systém souborů) a byly nahrazeny symbolickými
odkazy.

Datum poslední aktualizace: 3.11.2004

6/11

Úvod do systému UNIX

Studijní materiál pro cvičení z předmětu OSA

Symbolický odkaz je vlastně textový soubor, který obsahuje cestu k souboru, který
zastupuje. Délka souboru symbolického odkazu proto bývá obvykle odlišná od délky
odkazovaného souboru a rovná se počtu znaků v zápisu cesty k odkazovanému souboru.
labe:/home/student/student0 > ls
nastext
labe:/home/student/student0 > ln -s nastext odkaznatext
labe:/home/student/student0 > ls -l
total 1
-rw-r--r-- 1 student0 student 11 Oct 13 12:56 nastext
lrwxr-xr-x 1 student0 student
7 Oct 13 13:11 odkaznatext -> nastext
labe:/home/student/student0 > more nastext
Ahoj svete
labe:/home/student/student0 > more odkaznatext
Ahoj svete
labe:/home/student/student0 >

Speciální soubory

Speciální soubory v systému zastupují fyzická zařízení připojená k systému, jako jsou
např. disky, terminály, tiskárny nebo třeba paměť. Jsou umístěny v adresáři /dev. V
některých vlastnostech se odlišují od normálních souborů.
Existují dva druhy speciálních souborů – blokové a znakové. Znakové soubory odpovídají
zařízením, jako jsou třeba terminály nebo tiskárny. Blokové představují zařízení schopná
přenést celý blok dat (např. disky). Některá zařízení mohou mít jak blokový, tak i
znakový speciální soubor.
Ke každému speciálnímu souboru jsou navíc přiřazena dvě čísla:
•
•

Hlavní číslo zařízení. Udává typ zařízení.
Vedlejší číslo zařízení. Rozlišuje zařízení stejného typu.

Příklady speciálních souborů:
/dev/console
/dev/hda1
/dev/sda1
/dev/lp1
/dev/cua0
/dev/tty1
/dev/null

Konzola počítače (obrazovka a klávesnice)
První IDE disk a jeho první oblast
První SCSI disk a jeho první oblast
Paralelní rozhraní Centronics (LPT1)
Sériové rozhraní RS232 (COM1)
První virtuální konzola
Prázdné zařízení (černá díra). Přijme všechna data, při čtení ihned
předá EOF

I pevné disky jsou speciálním blokovým souborem. Systém se snaží minimalizovat počet
přístupů k disku, proto je disku samotnému předřazena vyrovnávací paměť (pro čtení i
zápis). Na pozadí běží systémový proces (démon se jménem flush, bdflush, update,
fsflush, apod.), který každých 30 sekund synchronizuje obsah vyrovnávací paměti a
disku.
Speciální soubory se zakládájí příkazem mknod <jméno> [c | b] <hlavní-číslo>
<vedlejší-číslo> [vlastník:skupina]. Tyto soubory ovšem vytváří téměř výhradně
správce systému.

Pojmenované roury

Roury slouží především pro komunikaci mezi procesy a fungují jako FIFO paměť. Při
zápisu do roury se data ukládají na disk téměř stejně jako při zápisu do souboru. Na
rozdíl od normálních souborů, to, co se z roury jednou přečte, již nemůže být čteno
znovu. Vytvářejí se příkazem mkfifo <jméno-roury> (na některých systémech

Datum poslední aktualizace: 3.11.2004

7/11

Úvod do systému UNIX

Studijní materiál pro cvičení z předmětu OSA

mknode <jmeno-roury> p). I-uzel roury obsahuje ukazatel pro čtení a ukazatel pro
zápis.
labe:/home/student/student0 > mkfifo roura
labe:/home/student/student0 > ls -l
total 1
-rw-r--r-- 1 student0 student 11 Oct 13 12:56 nastext
lrwxr-xr-x 1 student0 student
7 Oct 13 13:11 odkaznatext -> nastext
prw-r--r-- 1 student0 student
0 Oct 13 14:20 roura
labe:/home/student/student0 > echo Ahoj svete > roura &
[1] 78206
labe:/home/student/student0 > more roura
Ahoj svete
[1]+ Done
echo Ahoj svete >roura
Ve výše uvedeném příkladu jsme příkazem mkfifo roura založili pojmenovanou rouru,
což dokládá i výpis adresáře příkazem ls –l. Na dalším řádku vyšleme příkazem echo
Ahoj svete > roura & řetězec „Ahoj svete“ do námi vytvořené roury a tuto činnost
spustíme na pozadí jako samostatný proces (pomocí znaku & na konci řádku). Další
řádek výpisu pak obsahuje PID (identifikační číslo) procesu, který jsme právě vytvořili.
Tento proces je zatím pozastaven a je připraven plnit rouru v okamžiku, kdy z jejího
druhého konce začne jiný proces data odebírat. To provedeme příkazem more roura. Na
výstupu se objeví jednak text zaslaný do roury a jednak informace o tom, že proces,
který rouru plnil, dokočil svoji činnost.

Typ souborů a přístupová práva

V této části se dozvíte, jak poznat, zda konkrétní soubor je adresářem, rourou nebo
speciálním zařízením, a také to, jaká má nastavená přístupová práva. Přestože tyto dvě
informace spolu nijak nesouvisí, je jejich popis uveden v jednom odstavci, protože je
„vedle sebe“ najdete ve výstupu příkazu ls –l.
drwxr-xr-x
-rw-r--r-lrwxr-xr-x
prw-r--r-crw-rw-rwbrw-rw-r--

2 student0
1 student0
1 student0
1 student0
1 root
1 root

student 512 Oct 13 14:40 adresar
student
11 Oct 13 12:56 nastext
student
7 Oct 13 13:11 odkaznatext -> nastext
student
0 Oct 13 14:40 roura
sys
14,0 Apr 25 1995 audio
sys
2,0 Jan 1 1989 fd0

V tomto výpisu je první soubor adresář, druhý obyčejný soubor, třetí je odkaz, čtvrtý je
roura, pátý je speciální znakové zařízení a šestý je speciální blokové zařízení. Rozlišit se
dají podle prvního písmenka na řádku:
d
l
p
c
b

obyčejný soubor
adresář
odkaz
roura
speciální znakové zařízení
speciální blokové zařízení

Význam prvního znaku na řádku je již jasný, zbývajících 9 znaků určuje přístupová
práva, která vzhledem k danému souboru mají jeho vlastník, skupina uživatelů, do níž
patří vlastník, a ostatní uživatelé.

V i-uzlu souboru jsou uloženy (kromě jiného) i informace
• o vlastníku souboru (UID uživatele, který soubor vytvořil nebo kterému jej
superuživatel věnoval),
• o skupině vlastníka (GID skupiny, do které byl uživatel v okamžiku vytvoření
souboru přihlášen nebo na kterou bylo GID změněno) a
Datum poslední aktualizace: 3.11.2004

8/11

Úvod do systému UNIX
•

Studijní materiál pro cvičení z předmětu OSA

o přístupových právech.

Přístupová práva se určují odděleně pro
• vlastníka (u – user)
• skupinu (g - group) a
• ostatní (o - others).

Určují se zvláš’t pro
• čtení (r - read)
• zápis (w - write)
• spouštění (x - execute)
v případě souborů a pro
• výpis (r)
• vytváření a rušení souborů (w)
• prohledávání (x)
v případě adresářů. Adresář musí mít nastavené právo x, abychom se do něj mohli
přepnout, vypsat jej nebo použít soubory v adresáři uložené. Jinými slovy:
• Číst soubor mohu, pokud mám právo vstupu do adresáře (x) a právo čtení
souboru (r).
• Zapisovat do souboru mohu, pokud mám právo vstupu do adresáře (x) a právo
zápisu do souboru (w).
• Spustit soubor mohu, pokud mám právo vstupu do adresáře (x) a právo
provedení souboru (x).

Z první desítky znaků ve výpisu ls –l má tedy posledních devět znaků následující
význam:
pro vlastníka
r
w
x

pro skupinu
r
w
x

pro ostatní
r
w
x

Příklady přístupových práv:
drwxr-xr-x

-rw-r--r--rwxr-x--x

adresář (d) s plným přístupem (rwx) pro vlastníka, ovšem členové
skupiny a ostatní uživatelé nemohou v tomto adresáři vytvářet ani rušit
soubory (r-x)
obyčejný soubor (-), vlastník jej může číst (rw-) i pozměňovat, ostatní
pouze číst (r--)
obyčejný soubor (-) spustitelný pro všechny, vlastník jej navíc může číst i
upravovat, skupina si jej může prohlížet, ale ostatní jej mohou pouze
spouštět

Přístupová práva jsou ovšem v i-uzlu uložena na 12 bitech:

SUID, SGID, Sticky bit, r, w, x, r, w, x, r, w, x

Pokud je některý z prvních tří bitů nastaven, výpis příkazu ls –l se pozmění následujícím
způsobem:
SUID

-rwSr-x--x

SGID

-rwxr-S--x

Set User ID bit. Spuštěný program neběží pod UID toho, kdo jej
spustil, ale pod UID vlastníka. Pokud např. uživatel ze skupiny
ostatní potřebuje udělat se souborem něco, na co má právo jen
vlastník souboru, může to udělat prostřednictvím takovéhoto
programu. Typickým příkladem je passwd, který jakémukoli
uživateli propůjčuje superuživatelská práva, ale jen pro účely
změny vlastního hesla.
Set Group ID bit. Podobné jako v předchozím případě, ale program
běží s GID skupiny.

Datum poslední aktualizace: 3.11.2004

9/11

Úvod do systému UNIX
Sticky

-rwxr-x--T

Studijní materiál pro cvičení z předmětu OSA

Sticky bit. Dříve sděloval systému, že program má být trvale
zaveden v paměti (např. textový editor vi). Dnes se hojně používá
na veřejně přístupných internetových serverech pro zajištění toho,
aby si jednotliví uživatelé navzájem nepřemazávali soubory.
(Sticky bit může nastavovat jen root.)

Přístupová práva lze nastavovat příkazem chmod <práva> <soubor> buď symbolicky,
nebo číselně. Symbolické vyjádření je flexibilnější, umožňuje popsat i přidání nebo
odebrání práv, nejen nastavení na konkrétní hodnotu. Příklady možných zadání práv
v příkazu chmod:
go+x
a-r
ugo=rx
u+s
755
4511

Skupině (g) a ostatním (o) přidej (+) práva pro spouštění (x).
Všem (a) odeber (-) právo na čtení (r).
Všem (ugo) nastav (=) pouze práva na čtení a spuštění (rx).
Pokud byl v některé trojici předtím nastaven bit pro zápis, bude
vymazán.
Nastav SUID bit.
Absolutní vyjádření práv v osmičkové soustavě. 7(o)=111(b),
5(o)=101(b), takže 755(o)=111101101(b), tedy práva rwxrxr-x
511 se dá rozepsat jako r-x--x--x, 4 na začátku je 100, tj.
nastavení SUID bitu, finální práva proto budou r-S--x--x.

Aplikaci těchto přístupových práv ukazuje i následující výpis.
labe:/home/student/student0 > touch program
labe:/home/student/student0 > ls -l
-rw-r--r-- 1 student0 student 0 Oct 13 17:14 program
labe:/home/student/student0 > chmod go+x program
labe:/home/student/student0 > ls -l
-rw-r-xr-x 1 student0 student 0 Oct 13 17:14 program
labe:/home/student/student0 > chmod a-r program
labe:/home/student/student0 > ls -l
--w---x--x 1 student0 student 0 Oct 13 17:14 program
labe:/home/student/student0 > chmod ugo=rx program
labe:/home/student/student0 > ls -l
-r-xr-xr-x 1 student0 student 0 Oct 13 17:14 program
labe:/home/student/student0 > chmod u+s program
labe:/home/student/student0 > ls -l
-r-sr-xr-x 1 student0 student 0 Oct 13 17:14 program
labe:/home/student/student0 > chmod 755 program
labe:/home/student/student0 > ls -l
-rwxr-xr-x 1 student0 student 0 Oct 13 17:14 program
labe:/home/student/student0 > chmod 4511 program
labe:/home/student/student0 > ls -l
-r-s--x--x 1 student0 student 0 Oct 13 17:14 program
labe:/home/student/student0 >
Poznámka: způsob zadávání práv v příkazu chmod je ještě bohatší, ale pro naše účely
tyto funkce stačí.

Pokud v systému založíte nějaký soubor nebo adresář, jsou mu přidělena jistá implicitní
práva. To, která práva jsou vlastníkovi, skupině a ostatním přidělena, můžete ovlivnit
příkazem umask. Argumentem umask je sada osmičkových číslic (podobně jako u
chmod). Pokud se na dané pozici v binárním vyjádření číslice vyskytuje 1, znamená to,
že příslušné přístupové právo bude souboru odejmuto (na rozdíl od příkazu chmod, kde
1 znamená přidělení určitého práva). Pokud např. zadáte příkaz umask 022, můžete si
být jisti, že žádný nově vytvořený soubor nebude mít nastavená zapisovací práva pro

Datum poslední aktualizace: 3.11.2004

10/11

Úvod do systému UNIX

Studijní materiál pro cvičení z předmětu OSA

skupinu a ostatní. Naopak, pokud je na určité pozici 0, neznamená to ještě, že dané
právo bude souboru přiděleno; znamená to spíš, že u daného práva je vám jedno, jestli
ho soubor mít bude nebo ne.

Implementace systému souborů

Systém souborů je obvykle umístěn na disku. Ten musí kromě vlastních souborů a
adresářů obsahovat i jisté množství administrativních informací. Na disku se tak vytváří
struktura podobná této:
• Boot blok. Obsahuje zaváděcí program.
• Superblok. Důležité informace o celkovém počtu bloků, počtu bloků obsazených iuzly nebo začátek seznamu volných bloků.
• I-uzly souborů. Každý i-uzel popisuje právě 1 soubor (první i-uzel popisuje
kořenový adresář) a obsahuje informace o vlastníkovi, typu souboru, přístupových
právech a odkazy na datové bloky příslušející souboru. Neobsahuje jméno
souboru, to je obsaženo v adresáři.
• Datové bloky.

Jak systém přečte určitý soubor?

Představme si situaci, kdy musí systém přečíst např. soubor /bin/bash. Systém ví, že
kořenovému adresáři / přísluší i-uzel číslo 2.1 Přečte si, které datové bloky jsou obsazeny
souborem s obsahem kořenového adresáře. V tomto souboru pak najde, který i-node
přísluší adresáři bin. V i-uzlu adresáře bin přečte, kde najde datové bloky se souborem
popisujícím obsah adresáře bin. V tomto souboru opět zjistí číslo i-uzlu příslušející
souboru bash. V tomto i-uzlu si přečte, na kterých datových blocích se soubor bash
nachází a konečně může tyto bloky přečíst.

Typický adresářový strom

/
Jádro systému
/bin
Adresář s příkazu systému (sh, bash, cp, mv, …)
/dev
Adresář se speciálními soubory (periferie)
/etc
Systémové programy a data
/home
Domovské adresáře uživatelů
/lib
Sdílené knihovny
/mnt
Adresář rezervovaný pro připojování dalších svazků
/usr
Další adresáře systému
/usr/bin
Méně často používané příkazy systému
/usr/include Hlavičkové soubory jazyka C
/usr/lib
Knihovny a datové soubory používané různými programy systému
/usr/local
Lokální programy a datové soubory (obvykle je zde také umístěno všechno
programové vybavení, které není součástí systému)
/var
Soubory, které za běhu systému mění svou velikost
/var/spool
Soubory určené pro tisk nebo pro přenos v síti
/var/tmp
Pracovní soubory

Literatura

Při sestavování tohoto textu byly použity následující materiály:
1. Slidy pro cvičení Luboše Krále.
2. Manuálové stránky systému UNIX.
3. Petrlík, Lukáš. Jemný úvod do systému UNIX. BEN.
K čemu se využívá i-node 0 se mi nepodařilo zjistit (prý to nikdo neví už hodně dlouho).
I-node 1 dříve obsahoval seznam vadných bloků na magnetickém pásku. První volný inode má tedy číslo 2.

1

Datum poslední aktualizace: 3.11.2004

11/11

