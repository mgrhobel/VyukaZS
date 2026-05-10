---
title: "OS_UNIX_zaklady.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/prednasky/OS_UNIX_zaklady.pdf"
date: 2009-02-19
type: PDF (text-based)
---

Operační systém UNIX – základy
Michal Brandejs

1. Úvod
1.1 Historie UNIXu
1965-69
Projekt Multics (Bell Labs, General Electric, MIT).
1970
Ken Thompson na papíře vytváří nový mechanismus multiuživatelské správy
souborů.
Denis Ritchie a K.T. jej implementují na počítači PDP-7.
1971
Přesvědčí Bell Labs o vhodnosti zakoupit PDP-11/20 pro vývoj systému na
zpracování textů (pro patentové oddělení).
Vzniká název UNIX (autor Brian Kernighan)
K. Thompson zahajuje implementaci Fortranu pro UNIX; vzniká jazyk B.
D. Ritchie přidává datové typy se strukturami a vzniká jazyk C.
1973
Většina operačního systému přepsána do jazyka C.
http://www.UNIX-systems.org/what_is_unix.html
http://www.UNIX-systems.org/what_is_unix/flavors_of_unix.html
http://www.UNIX-systems.org/images/chronology_big.gif
Ochranná známka UNIX
Bell Labs
AT&T
USL UNIX System Laboratories (1991)
Novell
X/Open (1993)
Open Group (součástí je X/Open) (1996)
1.2 Pravidla vývoje UNIXu

1

Vývoj UNIXu se od počátku řídil těmito pravidly:
Psát programy, které budou dělat právě jednu věc, a tu budou dělat
dobře.
Psát programy tak, aby mohly navzájem spolupracovat.
Psát programy tak, aby povely přijímaly hromadně ze vstupu v textové
podobě.
Psát programy tak, aby výstupy produkovaly v textové podobě a mohly
být použity jako vstupy do programů dalších.
Příčiny popularity UNIXu
Systém je napsán programovacím jazykem vyšší úrovně.
Jsou dostupné zdrojové texty systému.
Má jednoduché a zdokumentované uživatelské rozhraní.
Nabízí prostředky na budování komplexních programů z jednodušších.
Poskytuje jednoduché konzistentní rozhraní periferních zařízení.
atp.
1.3 Vlastnosti operačního systému UNIX
multiprogramový
multiuživatelský
s terminálovým přístupem
Pojmy
server
souborový server
terminál
operační systém
síťový systém
Operační systém musí uživateli u terminálu vytvořit pocit, že počítač
schovaný za terminálem je "pouze" jeho.
ochrana uživatelského prostředí
ochrana souborů
ochrana procesů
ochrana systému proti uživatelům
1.4 Prvky ochrany uživatelů v multiuživatelském OS UNIX
Účet uživatele:
přihlášení
práce v sezení (relaci)
odhlášení
2

Účet obsahuje:
Uživatelské jméno
login name, 3-8 znaků, začíná písmenem, jedinečné v systému, záleží na
velikosti písmen
Heslo
password
Primární skupina
group
Uživatelské číslo
user identification UID
Doplňující identifikace uživatele
jméno, příjmení, ...
Domácí adresář
Shell (interpret příkazů)
/bin/sh, /bin/ksh, /bin/bash, ...
Další informace
čas posledního přihlášení, doba platnosti hesla, ... (záleží na implementaci)
1.5 Prvky ochrany uživatelů v multiuživatelském OS UNIX (2)
Práva pro přístup k souborům a adresářům:
určují se zvlášť pro
majitele souboru (u - user)
skupinu uživatelů (g - group)
ostatní, svět (o - other)
zvlášť pro
čtení/zápis/provedení (soubor)
výpis/modifikace/vstup (adresář)
Speciální uživatel root (superuživatel)
Jediný uživatel v systému, kterému se přístupová práva nekontrolují.
1.6 Přístup uživatele k systému: přihlášení
login: xnovak
uživatelské jméno, malými písmeny; nemusí být znám typ terminálu - proto
nemusí fungovat znaky BACKSPACE apod.
password: moje heslo
neopisuje se, libovolné znaky vč. mezer a CTRL znaků; musí být netriviální;
alespoň 6 znaků (významných 8)
Heslo nelze zpětně zjistit.
Při chybném přihlášení je vnucena prodleva a vypíše se:
3

Login incorrect
login:
Při úspěšném přihlášení:
vypíší se systémové zprávy
vypíše se případné sdělení správce systému
domovský adresář se nastaví jako běžný (pracovní)
spustí se požadovaný shell
vypíše se výzva shellu (prompt)
$

Prompt závisí na nastavení shellu (proměnná PS1)
set|grep PS1
exit nebo ^D (může být potlačeno)

1.7 Zadávání příkazů shellu
Dělají se rozdíly mezi malými a velkými písmeny
Shell interpretuje příkazy po stisku Enter
Příkazy lze zadávat "do zásoby"
Některé shelly si pamatují historii příkazů s možností editace a
opětovného použití
Dokud řádek není ukončen stiskem Enter, lze
o smazat poslední znak stiskem znaku erase
o zrušit celý řádek stiskem znaku kill
Nastavení speciálních znaků zjistíme příkazem:
stty -a

Nezobrazitelné znaky se v UNIXu vypisují:
jako ^C ... ctrl-C (ordinální hodnota 3)
nebo \012 ... tři číslice oktalově
1.8. Zadávání příkazů shellu (2)
bash$ stty -a
intr = ^C; quit = ^\; erase = ^?; kill = ^U;
eof = ^D; eol = <undef>; eol2 = <undef>;
start = ^Q; stop = ^S; susp = ^Z; rprnt = ^R;
werase = ^W; lnext = ^V; flush = ^O; min = 1;
time = 0;

intr

4

Násilně ukončí běžící proces (^C)
eof
Ukončení vstupu (např. z klávesnice; ^D; End of File; EOF)
stop
Pozastavení výpisu (např. na obrazovku; ^S; X-off)
start
Pokračování ve výpisu (^Q; X-on)
susp
Pozastavení procesu (resp. jeho převedení pod job control; ^Z). Používejte
uvážlivě - je nebezpečné zapomínati procesy
Příklad:
yes
^Z
ps
kill -9 ...

1.9 Nápověda - man
on-line manual pages
Nápověda k určitému příkazu:
man passwd
man stty
man man
Reference ve tvaru:
man(1)
jméno příkazu(sekce manuálu UNIXu)
Sekce
1.
2.
3.
4.
5.
6.
7.
8.

Příkazy uživatelské úrovně
Systémová volání
Knihovní funkce
Zařízení a ovladače zařízení
Formáty (konfiguračních) souborů
Hry
Různé (ASCII), popisy maker
Nástroje pro údržbu systému

Sekce se zadává:
man passwd
(IRIX 6.2) vypíše nápovědu k příkazu passwd(1) pro změnu hesla

5

man 4 passwd
Vypíše nápovědu k formátu souboru /etc/passwd passwd(4)
Zadávání sekce v jiných implementacích:
man -s 3 tzset
man -S 3 tzset

2. Systémové soubory
2.1 Systémy souborů
Různé systémy souborů:
Základní pro UNIX:
ufs (Solaris), efs (IRIX), ext2fs (Linux) a další
Doplňující:
msdos, vfat, nfs (Network fs), iso9660, swap, tmpfs a další
Vyrovnávání diskových operací:
"Špinavé" bloky zapisuje na disk každých 30 vteřin démon bdflush, update,
fsflush apod. jmen.
Systém souborů:
Zaváděcí blok
Superblok
Seznam i-uzlů
Seznam datových bloků

2.2 Jméno souborů a adresáře
Jméno souboru smí být dlouhé nejvýše 255 znaků. Na tuto délku je
zkracováno bez varování.
Může obsahovat libovolné znaky. Komplikace způsobují řídicí znaky
shellu. Výjimka: v kořenovém adresáři nesmí být soubor jména "/".
Rozlišují se malá a velká písmena.
Zvláštní význam mají jména souborů začínající znakem "." (tečka),
např. ".profile". Při expanzi nahrazovacího znaku "*" se taková jména
nepoužijí. Vyzkoušejte též "ls" a "ls -a".
Adresáře
Oddělovačem jmen adresářů je znak "/" (lomítko).
Kořenový adresář (root) "/"
Běžný (pracovní) adresář
Rozlišujeme cestu absolutní "/.../.../..." a relativní ".../.../...".
Každý adresář obsahuje položky "." (tento adresář) a ".." (nadřazený
adresář)
Příklady

6

pwd
Print Working Directory (zjištění cesty k běžnému adresáři)
cd adresář
Change Current Directory (bez parametru nastaví domovský)
cd ..
./program
mkdir adresář ...
Make Directories
rmdir adresář ...
Remove Directories (lze rušit pouze prázdné adresáře)

2.3 Reprezentace souboru na disku
Obsah souboru:
Z pohledu UNIXu je soubor posloupností bajtů. Systém obsah souboru
neinterpretuje.
Poznámka: V textovém souboru se řádky oddělují znakem LF (vs. MS-*
odděluje řádky znaky CR LF).
Informace o souborech jsou soustředěny do jednoho místa na
paměťovém médiu - do seznamu i-uzlů (i-node).
Jeden soubor (nebo adresář) je popsán právě jedním i-uzlem.

i-uzly neobsahují jméno souboru.
"ls -il" vypíše obsah adresáře vč. čísla i-uzlu.
i-uzel číslo 2 ukazuje vždy na kořenový adresář.

7

2.4 Formát adresáře
Kořenový adresář a jeho podadresář:

Prázdná položka má číslo i-uzlu nulové.
Příkazy:
Vytvoření souboru:
Mnoho způsobů; např. "touch soubor ..."
(prázdný soubor se vytvoří pouze vedlejším efektem tohoto příkazu)
Zrušení souboru:
rm soubor ...
Kopie souboru:
cp zdroj cíl
Přesun/přejmenování souboru/adresáře:
mv zdroj cíl

2.5 Odkaz (Tvrdý odkaz)
Situace: vytvořili jsme soubor "jméno1"

8

ln jméno1 jméno3

Zjištění počtu odkazů na souboru:
ls -l
-rw-r--r-- 2 brandejs users 5 Mar 10 21:25 jméno1
-rw-r--r-- 2 brandejs users 5 Mar 10 21:25 jméno3

Hodnota "2" je počet odkazů na soubor.
Úvodní "-" (minus) znamená, že jde o obyčejný soubor.
Položky "jméno1" a "jméno3" jsou rovnocenné.
rm jméno1

ls -l
-rw-r--r-- 1 brandejs users 5 Mar 10 21:25 jméno3

Nelze vytvářet (tvrdé) odkazy na adresáře. Proč?
Odkazy lze dělat pouze uvnitř systému souborů. Proč?
Komu patří vlastnictví nově vytvořeného odkazu?

2.6 Odkazy a adresáře

9

bash$ ls -ld test
drwxr-xr-x 3 brandejs users 1024 Mar 10 22:09 test
bash$ cd test
bash$ ls -ld pokus
drwxr-xr-x 2 brandejs users 1024 Mar 10 22:09 pokus
bash$

Úvodní "d" znamená, že jde o adresář.
V případě nejasností lze použít "ls -ild".
bash$ ls -ild pokus
81937 drwxr-xr-x 2 brandejs users 1024 Mar 10 22:09 pokus
bash$ cd pokus
bash$ ls -ild .
81937 drwxr-xr-x 2 brandejs users 1024 Mar 10 22:09 .
bash$

2.7 Symbolické odkazy
Symbolické odkazy umožňují:

10

Odkazy na adresáře
Odkazy mimo jeden systém souborů
Situace: máme soubor jméno3

ln -s jméno3 jméno9

ls -l
-rw-r--r-- 1 brandejs users 5 Mar 10 22:46 jméno3
lrwxrwxrwx 1 brandejs users 6 Mar 10 22:48 jméno9 -> jméno3

Úvodní "l" (písmeno L) znamená, že jde o symbolický odkaz.
Hodnota 6 je velikost souboru, tj. počet písmen "jméno3".
Položky "jméno3" a "jméno9" nejsou v žádném vztahu.

2.8 Formát i-uzlu
i-uzel na disku
i-uzel v paměti
na disku
volný x obsazený
ID vlastníka souboru
ID skupiny vlastníků
typ souboru (obyčejný, adresář, znakový nebo blokový speciální
soubor, FIFO)
přístupová práva
datum a čas poslední modifikace obsahu souboru, modifikace i-uzlu,
přístupu k souboru

11

počet odkazů na soubor
seznam diskových adres uložení souboru
velikost souboru v bajtech
paměťová kopie obsahuje navíc
identifikaci uzamknutí (pro výlučný přístup)
...
počet odvolávek (např. kolik instancí souboru je otevřených)
soubor je místem připojení dalšího systému souborů

Na disku jsou i-uzly v jednorozměrném poli <1 .. max>, v paměti jsou
zřetězeny do seznamu.

2.9 Superblok
velikost systému souborů
počet volných bloků v systému souborů
seznam volných bloků
index následujícího volného bloku v seznamu
velikost seznamu i-uzlů
počet volných i-uzlů
seznam volných i-uzlů
index následujícího volného i-uzlu v seznamu
pole zámků pro seznam volných bloků a i-uzlů
příznak modifikace superbloku

2.10 Speciální soubory
Rozlišujeme:
o Znakový speciální soubor
o Blokový speciální soubor
Součástí jádra jsou "ovladače zařízení"
Uživatelské rozhraní vůči zařízením se realizuje prostřednictvím
systému souborů
Speciální soubor je odkaz na i-uzel, který ukazuje na ovladač

12

Příkaz pro vytvoření speciálního souboru:
mknod jméno typ hlavní_číslo vedlejší_číslo
typ
je "b" (blokové zařízení) nebo "c" (znakové zařízení)
hlavní_číslo
je číslo udávající typ zařízení - ukazuje do tabulky zařízení
vedlejší_číslo
je číslo jednotky
Znakový a blokový speciální soubor vytváří superuživatel
Zpravidla uloženy v adresáři /dev
Ve výpise příkazu ls -l se objeví (údaje v pořadí hlavní číslo, vedlejší
číslo) např.:
crw-rw-rw- 1 root sys 14, 4 Apr 25 1995 audio
brw-rw-r-- 1 root mail 2, 0 Jan 1 1980 fd0

2.11 Příklady speciálních souborů Příklady z Linuxu:
/dev/console
konzola počítače (obrazovka a klávesnice),
/dev/fd0
disketa číslo 0,
/dev/hda1
první IDE disk a jeho první oblast,
/dev/sda1
první SCSI disk a jeho první oblast,
/dev/lp1
paralelní rozhraní Centronics odpovídající LPT1:,
/dev/cua0
sériové rozhraní RS-232 odpovídající COM1:,
/dev/tty1
první virtuální konzola,
/dev/null
prázdné zařízení, které přijme všechna data a které při čtení předá ihned eof
(konec souboru).
Příklady ze Systému V:
/dev/dsk/c0t2d0s6
SCSI zařízení - disk z čísla řadiče 0, SCSI adresy 2, SCSI LUN 0 a oblasti 6
/dev/pty/78
pseudo terminal driver (pty, pts)
/dev/rst12
magnetická páska (před zápisem souboru se vždy převine na začátek)
/dev/nrst12
13

2.12 Speciální soubory (2)
FIFO - pojmenovaná roura
Vytváří se příkazem:
mknod jméno p
p (pipe) roura
Pro přenos dat mezi procesy
Při zápisu do roury se data ukládají na disk téměř stejně jako při zápisu
do souboru
i-uzel obsahuje ukazatel pro čtení a ukazatel pro zápis
Ukazatele nelze měnit jinak než čtením/zápisem - důsledně FIFO
Příklad:
mknod trubka p
ls -l
prw-r--r-- 1 brandejs users 0 Mar 18 22:12 trubka

man mknod > trubka &
Přesměrováním > výstup nepůjde na obrazovku, ale do souboru "trubka".
Ukončením příkazu znakem & jej spustíme na pozadí.
more trubka
Výpis obsahu souboru po obrazovkách.
rm trubka
Zrušení položky "trubka" v adresáři a zrušení i-uzlu.

2.13 Typický adresářový strom
/unix, /bsd
Jádro OS
/bin/ls, cp, sh
Základní systémové programy a příkazy
/dev
Adresář speciálních souborů
/etc
Adresář většinou konfiguračních souborů systému
/lib
Adresář knihoven
/mnt
Pomocný adresář pro připojování dočasných systémů souborů
/tmp
Veřejný adresář pro pomocné a dočasné soubory
/home
Adresář s domovskými adresáři uživatelů
/usr/bin, etc, lib, tmp
Adresáře se soubory, které typicky z kapacitních důvodů nejsou v kořenovém
adresáři.
14

/usr/include
.h soubory pro překladač jazyka C
/usr/man
Manuálové stránky
/usr/local/bin, man, etc, lib, ...
Programy lokálně instalované

2.14 Typický adresářový strom (2)
/usr/sbin
Systémové programy určené zpravidla superuživateli
/usr/X11, openwin
Okénkový systém
/var
Adresář pracovních/administrativních/... souborů systému
/var/mail
Poštovní schránky uživatelů
/var/spool
Dočasné soubory systémových operací
/var/adm
Záznamy o činnosti systému a uživatelů
/var/tmp
/var/preserve
Pracovní soubory editoru vi, které zůstávají při násilném ukončení editoru.

2.15 Přístupová práva
V i-uzlu pro vyhodnocení přístupových práv jsou:
vlastník souboru
Číselné UID toho uživatele, který soubor vytvořil nebo kterému jej
superuživatel věnoval.
skupina vlastníka
Číselné GID skupiny, do které byl uživatel v okamžiku vytváření souboru
přihlášen nebo na kterou bylo GID změněno.
přístupová práva
Přístupová práva jsou v objektu uložena ve 12 bitech.
Ve výpisu ls -l
-rwxr-xr-x 1 novák student ...

vlastník (označuje se u jako 'user')
Vlastníkem je ten, jehož UID je zapsáno v i-uzlu.
skupina (označuje se g jako 'group')

15

ostatní (označuje se o jako 'others')
Touto kategorií určujeme, co s tímto objektem mohou provádět všichni.
Přístupová práva se vyhodnocují v pořadí ugo.

2.16 Přístupová práva (2) Pro soubor se operace definují následovně:
r

Soubor je povoleno číst.
w

Do souboru je povoleno zapisovat.
x

Soubor je povoleno spustit (provést).
Pro adresáře mají operace tyto významy:
r

Adresář je povoleno vypsat; nikoli však zpřístupnit soubory v něm
odkazované.
w

Do adresáře je povoleno zapisovat; tj. lze vytvářet a rušit soubory.
x

Do adresáře je možné vstoupit; tj. adresář může být argumentem příkazu cd
a lze zpřístupnit i-uzly souborů, na které se adresář odkazuje.
Příklady vyhodnocení přístupových práv:
Vytvořit soubor mohu v kterémkoli adresáři, do kterého mám právo
vstupu (x) a současně zápisu (w).
Zrušit soubor libovolného vlastníka mohu v libovolném adresáři, do
kterého mám právo vstupu (x) a současně zápisu (w).
Toto je problém zvláště u adresářů typu /tmp
drwxrwxrwx 9 root root 2048 Mar 18 22:12 tmp

Pro tyto adresáře se zavádí tzv. sticky bit:
drwxrwxrwt 9 root root 2048 Mar 18 22:12 tmp

Soubor v takto označeném adresáři může zrušit pouze vlastník souboru
nebo vlastník adresáře.

2.17 Přístupová práva (3)

16

Číst soubor mohu, pokud mám právo vstupu do adresáře (x) a právo
čtení souboru (r).
Zapisovat do souboru mohu, pokud mám právo vstupu do adresáře a
právo zápisu do souboru (w).
Spustit soubor mohu, pokud mám právo vstupu do adresáře a právo
provedení souboru (x).
Soubor běží pod UID toho, kdo jej spustil.
Jiné možnosti:
o

o

Chci, aby soubor běžel pod UID vlastníka souboru bez ohledu
na to, kdo jej spustil: použiji Set User ID (SUID) bit
rwsr-xr-x
Totéž pro skupinu: použiji Set Group ID (SGID) bit
rwxr-sr-x

Přístupová práva jsou uložena ve 12 bitech a popisují se osmičkově
následovně:
4000 SUID
2000 SGID
1000 sticky bit
0400 r pro vlastníka
0200 w pro vlastníka
0100 x pro vlastníka
0070 rwx pro skupinu vlastníků
0007 rwx pro ostatní
Všechny kombinace jsou možné, ne však významné.

2.18 Přístupová práva (4)
Příklady symbolického zápisu příst. práv:
rwsr-sr-x (6755)
rwxrwxrwt (1777)
rwxrwxrwT (1776)
rwSr--r-- (4644)

Příkaz umask
Zadávání implicitních přístupových práv pro vytváření souborů a
adresářů.
Interní příkaz shellu.

17

umask nnn
Zadává se zpravidla numericky třemi osmičkovými číslicemi (nejvýše
třemi)
Maska se zadává inverzně
umask 022
touch soubor (rw-r--r--)
mkdir adresář (rwxr-xr-x)
umask 027
touch soubor (rw-r-----)
mkdir adresář (rwxr-x---)

2.19 Příkaz chmod
chmod mode soubor
Nastavení přístupových práv.
Kdo smí přístupová práva nastavovat?
mode
absolutně vyjádřeno 1-4 osmičkovými číslicemi
symbolicky - lze popsat následující gramatikou:
mode ::= clause[,clause ...]
clause ::= [who ...][action ...]last_action
action ::= op[perm ...]
last_action ::= op[perm ...]
who ::= a|u|g|o
op ::= +|-|=
perm ::= r|s|t|w|x|X|u|g|o

who:
'u' (user), 'g' (group), 'o' (other); 'a' (all) je totéž co 'ugo'
Je-li who nezadáno, potom je to totéž co 'a' (all), ale nenastaví se bity označené
příkazem umask.
perm:
'X' je totéž co 'x', ale aplikuje se pouze na adresáře nebo na soubory, které mají
alespoň jeden bit 'x' nastavený.
'u', 'g', 'o' použije se současné nastavení příst. práv uživatele, skupiny,
ostatních.
op:
'+' přidávají se práva, '-' ubírají se práva, '=' absolutní nastavení.

2.20 Příkazy pro nastavování příst. práv
Příklady použití příkazu chmod
chmod go-w soubor
18

zakáže zápis pro skupinu a ostatní
644
nastaví rw-r--r-=rw,+X
nastaví 'rw' podle umask a 'x' pro všechny ('ugo') tehdy, je-li soubor
proveditelný alespoň pro jednoho z 'ugo' nebo jde o adresář.
go=
smaže všechny bity pro 'go'
a+rwxt
typické nastavení pro veřejný pracovní adresář
u+s
nastavení SUID
g+s
nastavení SGID (majitel souboru musí být členem skupiny)

2.21 Příkazy pro nastavování příst. práv (2)
chown vlastník soubor ...
Změna vlastníka souboru nebo adresáře.
Vlastník se zadává buď už. jménem, nebo číselně UID.
Jak zjistím svoje UID?
Vlastníka souboru smí měnit pouze superuživatel.
POSIX 1003.2 povoluje syntaxi:
chown vlastník:skupina soubor ...
pro současnou změnu vlastníka i skupiny.
newgrp skupina
Přihlášení do jiné skupiny.
Příkazem se mění aktuální GID přihlášeného uživatele.
Uživateli je přihlášením do systému nastaveno jisté GID (zaznamenáno v účtě)
a tímto příkazem může uživatel svoje GID měnit na jedno z těch, které má
povoleno v /etc/group.
Příkaz bez uvedení skupiny nastaví GID podle účtu.
chgrp skupina soubor ...
Změna skupiny souboru nebo adresáře.
Skupinu smí měnit vlastník souboru nebo superuživatel. Vlastník souboru však
pouze tehdy, pokud náleží do cílové skupiny.

3. Shell
3.1 Uživatelské rozhraní
Známé:
Bourne shell (sh)
C-shell (csh)
19

Korn shell (ksh)
Bourne-again shell (bash)
Co je shell?
Shell je interpretační programovací jazyk. Čte příkazy z terminálu nebo ze
souboru a provádí je.
Obecný formát příkazového řádku:
arg0 arg1 arg2 ...
Řetězec arg0 je vždy jméno příkazu.
Příkazy:
vnitřní
vnější
arg0 se nejprve hledá v seznamu vnitřních příkazů a potom podle seznamu cest
proměnné PATH
Ukončovací kód (exit status):
Každý příkaz při svém ukončení vrací numerický stav. Hodnota 0 znamená
OK. Nenulová hodnota značí chybu.
Lexikální analýza příkazového řádku
Shell čte ze vstupu "slova" vzájemně oddělená "bílým místem" (mezera,
tabulátor) a operátory:
Řídicí operátory:
& && ( ) ; ;; | || nový řádek

Operátory přesměrování:
< > >| << >> <& >& <<- <>

3.2 Řídicí znaky
Obrácené lomítko (backslash):
Znak následující za \ ztrácí svůj řídicí charakter a stává se normálním znakem.
Výjimka: \ na konci řádku (\nový řádek) sděluje, že další řádek je
pokračováním tohoto.
Apostrof (single quote):
Uzavřením znaků mezi dva apostrofy '...' znaky ztrácejí svůj řídicí význam
(vyjma ').
Úvozovky (double quotes):
Uzavřením znaků do dvojice úvozovek "..." ztrácejí znaky svůj řídicí význam
vyjma:
20

$ (dolar)
` (obrácený apostrof)
\ (obrácené lomítko)

Obrácené lomítko uvnitř dvojice úvozovek lze použít pouze pro:
\$ \` \" \\ \nový řádek

Jinak se \ interpretuje jako normální znak.
Vyzkoušejte si příkazem echo
echo \'
echo '\'
echo \\
echo "'"
echo "\'"
touch muj\ soubor

3.3 Přesměrování vstupu a výstupu
Shell přesměrování-propojení zajistí před provedením příkazu.
File descriptor number (n)
příkaz n> soubor
příkaz n< soubor
Každý proces má nastaveno:
0
tzv. standardní vstup
1
tzv. standardní výstup
2
tzv. standardní chybový výstup
Další si nastavuje programátor.
Implicitní varianty:
1> je totéž co >
0< je totéž co <

Přesměrování vstupu:
příkaz n< soubor
Soubor musí existovat
Přesměrování výstupu:

21

příkaz n> soubor
Pokud soubor neexistuje, vytvoří se
Pokud soubor existuje, v okamžiku otevření se zkrátí na velikost 0 a
bude se přepisovat
Pokud však byl proveden příkaz "set -C" (nebo "export noclobber="),
potom nelze přesměrovat výstup do existujícího souboru. Toto omezení
odstraní operátor ">|".

3.4 Přesměrování vstupu a výstupu (2)
Příklady:
$ ls neni je
ls: neni: No such file or directory
je
$ ls neni je > a 2> b

Nesmí se použít: ls > a > b
Soubor 'a' zůstane prázdný, soubor 'b' se naplní stand. výstupem. Problém lze
řešit např.:
ls|tee a > b

Připojení výstupu na konec souboru
příkaz n>> soubor
Pokud soubor neexistuje, vytvoří se.
Vstup dokumentu ze stejného zdroje jako příkazy
příkaz n<<ukončení
'ukončení' je symbol konce vstupu (řetězec označující konec vstupu)
Řetězec 'n<<ukončení' musí být bez mezer.
mail novak <<EOF
První řádek dopisu
Druhý řádek dopisu
EOF

Ve variantě 'n<<-ukončení' se vypouštějí všechny znaky TAB na
začátku čtených řádků.
mail novak <<-EOF
První řádek dopisu
Druhý řádek dopisu
EOF

22

3.5 Přesměrování vstupu a výstupu (3)
Použití souboru spojeného s jiným deskriptorem:
n>&m
Použije se soubor spojený s deskriptorem 'm' i pro výstup deskriptoru
'n'. 'n' je implicitně 1 (stand. výstup).
Příklad:
ls neni je 2>&1 > dirlist

Deskriptoru 2 se přiřadí terminál a deskriptoru 1 se přiřadí soubor dirlist.
Není-li uvedeno 'n' a 'm', potom >& slouží jako operátor přesměrování
stand. výstupu a současně stand. chybového výstupu do souboru:
ls neni je >& vse

Totéž, ale pro vstup:
n<&m
Použije se soubor spojený s deskriptorem 'm' i pro vstup z deskriptoru
'n'.
'n' je implicitně 0 (stand. vstup).
Zavření vstupu nebo výstupu:
n<&n>&Otevření deskriptoru pro vstup i výstup:
n<>soubor

3.6 Spojování příkazů do kolon
příkaz1 | příkaz2 [ | příkaz3 ... ]
Operátor | propojí standardní výstup příkazu1 se standardním vstupem
příkazu2 rourou.
Příkazy takto propojené nazýváme kolonou.
Ukončovacím kódem kolony je ukončovací kód posledního příkazu
v koloně.
Zápisem
! příkaz1 | příkaz2 [ | příkaz3 ... ]
se ukončovací kód kolony neguje.
Negace ukončovacího kódu znamená:
o 0 se mění na 1

23

o nenulová hodnota se mění na 0
Zápisem
příkaz1 2>&1 | příkaz2
se na standardní vstup příkazu2 předá jak standardní výstup, tak i stand.
výstup příkazu1 (v tomto případě nelze deskriptor za & vypustit).

Spuštění příkazu na pozadí
příkaz1 & [ příkaz2 & ...]
Shell příkaz spustí asynchronně, tj. nečeká na dokončení.
Stand. vstup takto spuštěného procesu je napojen na /dev/null
Na takto spuštěný proces nebo procesy se nevztahuje znak intr.

3.7 Job Control
Jak dostat úlohu pod správu Job Control?
1. Spustíme-li úlohu na pozadí (&), vypíše se identifikace:
2. yes > /dev/null &
[1] 1234

Číslo úlohy je 1 a má top-level proces 1234.
3. Běží-li úloha normálně spuštěná na popředí a chceme s ní nějak naložit,
stiskneme znak susp. Shell pošle procesu signál STOP a vypíše se:
4. yes > /dev/null
5. ^Z
[2]+ Stopped

yes > /dev/null

Příkazy:
jobs
Vypíše seznam řízených úloh
[1]- Running

yes > /dev/null &

[2]+ Stopped

yes > /dev/null

'+' znamená current job, '-' znamená previous job.
Na úlohu se lze odkazovat několika způsoby:
%+
nebo %%
current job
%previous job

24

%n
určená úloha, kde n je její číslo z [n]
%řetězec
úloha, jejíž spouštěcí příkaz začíná řetězcem
%?řetězec
úloha, jejíž libovolná část spouštěcího příkazu obsahuje řetězec

3.8 Job Control (2)
Příkazy:
fg [job]
Úloha se spustí na popředí
Není-li zadán job, potom se použije current job.
bg [job]
Totéž, ale na pozadí.
kill [signál] job ...
Pošle signál (implicitně TERM) úloze.
wait [job]
Zahájí čekání na dokončení úlohy a převezme její ukončovací kód.
Není-li job zadán, čeká se na ukončení všech úloh a návratový kód
bude 0.

3.9 Seznamy
Seznamem rozumíme posloupnost žádného nebo více příkazů
oddělených novým řádkem, středníkem (;), nebo ampersandem (&).
Shell příkazy provádí v pořadí, v jakém jsou zapsány.
Pokud zápis končí ampersandem (&), ihned se zahájí provádění
následujícího.
Návratový kód seznamu je návratový kód posledního prováděného
procesu.
cd adresář ; ls
cd adresář;ls

Příkazy lze oddělovat operátory && a ||.
Oddělovač && znamená, že se druhý příkaz provede pouze tehdy,
pokud ukončovací kód předchozího byl 0.
Oddělovač || znamená, že se druhý příkaz provede pouze tehdy, pokud
ukončovací kód předchozího byl nenulový.
25

cd adresář&&ls

Operátory && a || mají stejnou prioritu.
Stejnou, ale nižší, mají operátory ; & nový řádek.
cd adresář && ls ; touch soubor
cd adresář && ls && touch soubor
ls adresář 2>/dev/null || mkdir adresář

3.10 Substituce příkazů
`příkaz`
Operátor obrácený apostrof
Určeno k zahrnutí standardního výstupu příkazu do příkazového řádku.
Shell zadaný příkaz provede ve vnořeném shellu (subshell).
Případné znaky "nový řádek" se nahrazují mezerou.
ls `pwd`
grep -i 'moje jméno' `cat /tmp/které_soubory`

Proměnné
Deklarace a přiřazení hodnoty proměnné:
jméno=[hodnota]
Hodnotou je řetězec (i prázdný) podléhající všem dosud popsaným
expanzím (nepodléhá '*' expanzi, viz dále).
Použití proměnné:
$jméno
${jméno}
ADRESAR=/home/novak/vyuka/unix
ls $ADRESAR
mkdir $ADRESAR/projekt
ls ${ADRESAR}
mkdir ${ADRESAR}NEW

Výpis nastavených proměnných:
set
set|more

26

3.11 Proměnné (2)
Zrušení proměnných:
unset proměnná ...
Označení proměnných určených k exportování do potomků:
export proměnná ...
V některých shellech lze současně nastavovat a exportovat:
export proměnná=[hodnota]
Načítání obsahu proměnných ze stand. vstupu:
read proměnná ...
Příkaz čte ze standardního vstupu slova a přiřazuje je do proměnných.
Při čtení se provedou všechny expanze vyjma '*'.
Příklad:
echo Zadej adresář a soubor, \
které se mají vytvořit:
read ADRESAR SOUBOR
mkdir $ADRESAR 2>/dev/null||\
echo Chyba při vytváření $ADRESAR
touch $ADRESAR/$SOUBOR

3.12 Některé proměnné užívané shellem
HOME
Domovský adresář pro příkaz "cd bez parametru" apod.
PWD
Běžný (pracovní) adresář; pwd (echo $PWD).
OLDPWD
Předchozí běžný adresář; cd MAIL
Jméno souboru s poštovní schránkou uživatele.
PATH
Seznam adresářů prohledávaných při spouštění souboru.
MANPATH
Seznam adresářů prohledávaných příkazem man.
PS1
Řetězec primárního promptu (implicitně $).
PS2
Řetězec sekundárního promptu (implicitně >), tj. prompt pokračovacích řádků.
IFS
Internal Field Separator - oddělovače polí v příkazu. Proměnná normálně
obsahuje: mezeru, tabulátor, nový řádek.

27

Další viz "man sh" (ksh, bash, ... příslušný shell)

3.13 Závorkování
(seznam)
Posloupnost příkazů 'seznam' se provede ve vnořeném shellu.
Tzn. že proměnné nastavené uvnitř závorek se po opuštění pravé
závorky ztrácejí.
Návratový kód je návratový kód seznamu.
{ seznam;}
Posloupnost příkazů 'seznam' se provede v aktuálním shellu.
Příklad:
(pwd; cd nic; pwd); pwd
{ pwd;cd nic;pwd;};pwd
cd nic 2>/dev/null||{ mkdir nic;cd nic;}

3.14 Složené příkazy
for jméno [ in slovo; ] do seznam; done
Příkaz expanduje 'slovo' a postupně vytvářené položky přiřazuje
proměnné 'jméno' a provádí posloupnost příkazů 'seznam'.
Není-li 'in slovo;' zadáno, potom se 'seznam' provede pro
každý poziční parametr (viz dále).
Příklady:
for JMENO in *; do echo $JMENO; done
for POLOZKA in a b c d
do
echo $POLOZKA
done

case slovo in
vzorek [ | vzorek ... ]) seznam;;

28

...
esac
Příkaz expanduje 'slovo' a hledá je mezi zadanými vzorky
s použitím expanzních znaků pro jména souborů (viz dále).
Jakmile se shoduje, provede se seznam příkazů. Po nalezení
první shody se dále už nehledá.
Příklad:
echo Zadej akci a soubor:
read AKCE SOUBOR
case $AKCE in
smaz|remove|delete) rm $SOUBOR;;
vytvor|create)

touch $SOUBOR;

chmod 777 $SOUBOR;;
esac

3.15 Složené příkazy (2)
if seznam; then seznam; [ elif seznam; then seznam; ] ...
[ else seznam; ] fi
Provede se 'if seznam;'. Pokud jeho návratový kód je nulový
(OK), provede se 'then seznam;'. Jinak se provede 'elif seznam;'
(...) nebo 'else seznam;'.
Návratový kód je kód posledního provedeného procesu
nebo 0, pokud se neprovedl žádný příkaz.
while seznam; do seznam; done
until seznam; do seznam; done
Seznam 'do seznam;' se provádí tak dlouho, dokud je návratový
kód
'while seznam;' nulový
'until seznam;' nenulový
break [n]
Ukončí n-tou úroveň cyklu for, while, until.
29

continue [n]
Zahájí další iteraci cyklu.
true
Návratový kód vždy 0.
false
Návratový kód vždy 1.
Příklad:
while true; do
echo y
done

3.16 Příkaz test
test výraz
[ výraz ]
Příkaz vyhodnotí výraz a nastaví návratový kód 0 (true) nebo 1
(false).
Testování typu souboru
-b soubor
soubor existuje a je blokovým speciálním souborem.
-c soubor
soubor existuje a je znakovým speciálním souborem.
-d soubor
soubor existuje a je adresářem.
-e soubor
soubor existuje (pouze vestavěný příkaz test).
-f soubor
soubor existuje a je normálním souborem.
-h soubor nebo -L soubor
soubor existuje a je symbolickým odkazem.
-p soubor
soubor existuje a je pojmenovanou rourou.
-S soubor

30

soubor existuje a je socket.
-t [fd]
fd je otevřeno na terminál. Vynecháme-li fd, potom se použije hodnota 1
(standardní výstup).
Testování přístupových práv
-g soubor
soubor existuje a má nastaven bit SGID.
-k soubor
soubor existuje a má nastaven 'sticky' bit.
-r soubor
soubor existuje a lze jej číst.
-u soubor
soubor existuje a má nastaven bit SUID.
-w soubor
soubor existuje a lze do něj zapisovat.
-x soubor
soubor existuje a je proveditelný.

3.17 Příkaz test (2)
Testování charakteristik souborů
-e soubor
soubor existuje.
-s soubor
soubor existuje a má velikost větší než nula.
soubor1 -nt soubor2
soubor1 je novější (podle času poslední modifikace obsahu) než soubor2.
soubor1 -ot soubor2
soubor1 je starší (podle času poslední modifikace obsahu) než soubor2.
soubor1 -ef soubor2
soubor1 a soubor2 jsou na stejném zařízení a mají stejné číslo i-uzlu (tzn. jde
o dva tvrdé odkazy na tentýž soubor).
Testování řetězců
-z řetězec
Délka řetězce je nulová
-n řetězec nebo řetězec
Délka řetězce je nenulová.
řetězec1 = řetězec2
Řetězce jsou shodné.
řetězec1 != řetězec2
Řetězce se neshodují.

31

3.18 Příkaz test (3)
Numerické testy
Na místě numerického argumentu se smí vyskytovat buď číslo (může
být i záporné), nebo speciální výraz
-l řetězec
který se nahradí délkou řetězce.
Numerické relační výrazy se vytvářejí následovně:
číslo1 -eq číslo2
číslo1 = číslo2
číslo1 -ne číslo2
číslo1 se nerovná číslo2
číslo1 -lt číslo2
číslo1 < číslo2
číslo1 -le číslo2
číslo1 je menší nebo rovno číslo2
číslo1 -gt číslo2
číslo1 > číslo2
číslo1 -ge číslo2
číslo1 je větší nebo rovno číslo2
Uveďme si jeden příklad kombinace unárního výrazu -l a binárního -gt:
test -l abc -gt 1 && echo ano

Logické výrazy
! výraz
výraz je nepravdivý.
výraz1 -a výraz2
výraz1 a výraz2 jsou pravdivé.
výraz1 -o výraz2
výraz1 nebo výraz2 je pravdivý.
Priority můžeme upravovat i závorkami (); nesmíme však zapomenout závorky
odstínit od shellovských expanzí např. \( \)
3.19 Shell skript - scénář
Soubor s příkazy pro shell.
Soubor 'skript' lze číst

32

Přístupové právo 'r'
Spuštění ve vnořeném shellu:
sh skript
Soubor 'skript' se hledá v běžném adresáři a $PATH
Spuštění v běžném shellu:
. skript
Souboru 'skript' se hledá v $PATH a v běžném adresáři.
Soubor 'skript' lze číst a provést
Přístupová práva 'rx'
Spuštění ve vnořeném shellu:
skript
Soubor 'skript' se hledá v $PATH
Shell skript se provede vždy tím programem (shellem), ze kterého byl
spuštěn.
Program, kterým se shell skript má provést, lze specifikovat na prvním
řádku od prvního sloupce:
#!/bin/sh

Soubor se shell skriptem musí být vždy čitelný (r).
Shell skript nelze SUID, SGID.
Komentáře (poznámky) lze psát za znak '#' (znak je buď na začátku
řádku, nebo jej bezprostředně předchází bílé místo).
3.20 Poziční parametry
Poziční parametr je pojmenován číslem větším než 0.
$1 $2 $3 ... $9
${1} ${2} ${3} ... ${9} ${10} ${11} ...
Shell poziční parametry implicitně nastavuje na hodnoty argumentů uvedených
na spouštěcím řádku.
Příklad:
skript a b c
#!/bin/sh
echo $1 $2 $9 ${10}

33

Explicitně se poziční parametry nastavují příkazem set následovně:
set -- a b c
echo $1 $2 $3

shift [n]
Příkaz "posune" obsahy pozičních parametrů o n nebo jeden
doleva. Počet pozičních parametrů ($#) se sníží o jeden.
Zvláštní parametry
$*
Expanduje se do pozičních parametrů od prvního do posledního zadaného. Je-li
parametr uveden uvnitř dvojice úvozovek, expanduje se do jednoho slova tak,
že se parametry oddělí prvním znakem uvedeným v IFS (nebo mezerou, není-li
IFS).
skript 1 2 '3 4' 5
#!/bin/sh
IFS=!
echo "$*"

# Vypíše 1!2!3 4!5

3.21 Zvláštní parametry (2)
$#
Expanduje se do počtu pozičních parametrů.
#!/bin/sh
if [ $# = 0 ]; then
echo Příkaz se spouští s těmito parametry ...
exit 1
fi

$?
Expanduje se do návratového kódu posledního dokončeného procesu.
#!/bin/sh
mkdir adresar 2> /dev/null
if [ $? != 0 ]; then
echo Chyba ...
fi

$Expanduje se do řetězce znaků zadaných jako volby.
$$
Expanduje se do čísla procesu shellu, který provádí expanzi (viz typický
příklad na vytvoření pomocného souboru jedinečného jména).

34

#!/bin/sh
TEMP=/tmp/pomocny.$$
touch $TEMP
...
rm $TEMP

$!
Expanduje se do čísla nejposlednějšího procesu spuštěného na pozadí.
yes &
sleep 2
kill $!

$0
Expanduje se do uživatelem zadaného jména skriptu.
3.22 Expanze proměnných
${proměnná}
Nejjednodušší tvar.
${proměnná:-slovo}
Použij implicitní hodnotu.
Pokud je proměnná nedefinována nebo prázdná, použije se
expandované slovo.
${proměnná:=slovo}
Přiřaď implicitní hodnotu.
Pokud je proměnná nedefinována nebo prázdná, přiřadí se a použije se
expandované slovo.
${proměnná:?slovo}
Oznam chybu.
Pokud je proměnná nedefinována nebo prázdná, předá se na stand.
chybový výstup hlášení slovo.
${proměnná:+slovo}
Použij jinou hodnotu.
Pokud je proměnná nedefinována nebo prázdná, předá se prázdná
hodnota. Je-li neprázdná, použije se slovo.
Vypustí-li se dvojtečka, testuje se pouze nedefinovanost.
${#proměnná}
Délka řetězce proměnné ve znacích.

35

3.23 Expanze proměnných (řetězce)
${proměnná%slovo}
Odstraní nejkratší sufix (podřetězec končící s koncem řetězce).
Zadané slovo se expanduje do podoby vzorku na obsahu proměnné.
Pokud operátor najde vzorek na konci řetězce, odstraní jeho nejkratší
vyhovující část.
${proměnná%%slovo}
Odstraní nejdelší sufix.
Zadané slovo se expanduje do podoby vzorku na obsahu proměnné.
Pokud operátor najde vzorek na konci řetězce, odstraní jeho nejdelší
vyhovující část.
${proměnná#slovo}
Odstraní nejkratší prefix (podřetězec začínající se začátkem řetězce).
Zadané slovo se expanduje do podoby vzorku na obsahu proměnné.
Pokud operátor najde vzorek na začátku řetězce, odstraní jeho
nejkratší vyhovující část.
${proměnná##slovo}
Odstraní nejdelší prefix.
Zadané slovo se expanduje do podoby vzorku na obsahu proměnné.
Pokud operátor najde vzorek na začátku řetězce, odstraní jeho nejdelší
vyhovující část.

3.24 Vlnková expanze
~novak
Domovský adresář uživatele novak (např. /home/novak).
~novak/pub
Např. /home/novak/pub
~
Domovský adresář běžného uživatele (podle $HOME).
~/.profile
Soubor .profile v domovském adresáři běžného uživatele.

36

~+
Běžný adresář (podle $PWD).
~Předchozí běžný adresář (podle $OLDPWD).

3.25 * apod. expanze
*
Vyhovuje libovolnému počtu libovolných znaků.
?
Vyhovuje právě jednomu libovolnému znaku.
[]
Definuje třídu vyhovujících znaků; obsah hranatých závorek popisuje právě
jeden znak.
[ACd-i]*
Vyhovuje jménům začínajícím znakem A, C, d, e, f, ..., i.
[!0-9]*
Vyhovuje jménům začínajícím čímkoli vyjma číslic. Smysl obrací operátor !
(starší shelly používaly ^).
Expanze jmen souborů a adresářů
Vzorek nesmí obsahovat lomítko, tzn. do jednoho vzorku lze zahrnout
nejvýše jeden adresář.
Příklad: /usr/s*/*
Vzorek nevyhovuje jménům adresářových položek začínajících tečkou.
Nutno zadat explicitně.
Příklad: .* *
Každé expadované slovo se nahradí posloupností vyhovujících jmen
oddělených mezerou.
Příklad: .[!.]*
Vše mimo .. (a položek, jejichž jméno začíná ..).

3.26 Funkce v shellu
Syntax definice:

37

jméno() { seznam;}
Volání:
jméno [argumenty]
Příklad:
datum()
{
date '+%-d. %-m. %Y %H:%M'
}
datum

Proměnné globální a lokální:
Globální: nastavovány klasickým způsobem
Lokální:
local proměnná[=...]
local je interní příkaz shellu.
Lze použít pouze uvnitř funkce.
Deklaruje-li se lokální proměnná stejného jména jako globální, lokální
zdědí počáteční hodnotu z globální.
Hodnota nastavená lokální proměnné uvnitř funkce nezmění globální
hodnotu po opuštění funkce.
Lokální proměnná se dědí do vnořených funkcí.

3.27 Funkce v shellu (2)
Poziční parametry se nastaví tak, jak byly zadány při spuštění funkce
(vyjma $0).
Příklad: Vyzkoušejte si
fce()
{
echo $0
echo $*
}
fce a b c d

Příkaz: return [návratový kód]
o Interní příkaz shellu.
o Ukončí právě prováděnou funkci.
Funkce se provádějí v běžném shellu.
Funkce mohou být rekurzivní (bez omezení počtu vnoření).
38

Funkce se nedědí.

3.28 Aritmetické expanze
$((výraz))
Alternativním způsobem zápisu v některých shellech (např. bash) je:
$[výraz]
Výraz se interpretuje podle těchto pravidel:
1. výraz se interpretuje tak, jako by byl uzavřen do uvozovek (uvozovky
uvnitř výrazu nemají řídicí význam),
2. ve výrazu se expandují parametry ($...) a substituce příkazů (`...`),
3. příkaz se vyčíslí.
Výraz se vyčísluje v aritmetice long integer bez kontroly přetečení.
Jako příklad si uveďme skript, který spočítá počet podadresářů
v běžném adresáři:
#!/bin/sh
POM=0
for JMENO in *
do
if [ -d $JMENO ]; then
POM=$(($POM+1))
fi
done
echo V adresari `pwd` je $POM podadresaru.

3.29 Aritmetické expanze (2)
Operátory (zapsány s klesající prioritou):
-+

unární minus a plus

!~

logická negace a inverze bitů

*/%

násobení, dělení, zbytek po dělení

+-

sečítání, odčítání

39

<< >>

posun bitů vlevo a vpravo (co<<o kolik bitů)

<= >= < >

porovnávání

== !=

rovnost, nerovnost

&

součin (AND) po bitech

^

exkluzivní součet (XOR - nonekvivalence) po bitech

|

součet (OR) po bitech

&&

logický součin

||

logický součet

= *= /= %= += -=

operace s přiřazením výsledku

<<= >>= &= ^= |=

Operandy s operátory lze uzavírat do závorek ( ). Závorky pak mají
nejvyšší prioritu.
Proměnnou lze expandovat i na operátor.
Konstanty:

Formát
zápisu
0n
0xn
báze#n}
n

Konstanta n je v
osmičkové soustavě
šestnáctkové soustavě (nebo též 0Xn)
soustavě o základu báze, kde báze je číslo desítkové v intervalu
2 až 36
desítkové soustavě

Konstanta se vždy převádí do desítkové soustavy.
3.30 Pořadí vyhodnocování expanzí
1. ~ expanze, expanze parametrů, substituce příkazů (` `), aritmetické
expanze (všechny tyto expanze ve vyhodnocují na stejné úrovni),
2. oddělení polí generovaných v kroku 1 (pokud je IFS neprázdné),
3. * apod. expanze (jména souborů a adresářů), nebyla-li při spuštění
shellu uvedena volba -f,
4. odstranění apostrofů a uvozovek.

40

Nalezení a provedení příkazu
Shell rozlišuje tři různé typy příkazů:
shellovské funkce,
interní příkazy a
normální programy.
Shell příkazy rovněž hledá v tomto pořadí:
1. Po zadání příkazu prohledá seznam shellovských funkcí,
2. potom seznam interních příkazů a
3. nakonec adresáře v seznamu PATH.
Volba -touch -- -l
ls
rm -- -l

3.31 Interní příkazy shellu
. soubor [argumenty]
source soubor [argumenty]
Příkaz přečte a provede obsah souboru soubor v rámci aktuálního shellu.
Návratový kód posledního příkazu provedeného uvnitř souboru se
stane návratovým kódem příkazu (nebo se vrací 0, pokud nebyl
proveden žádný příkaz).
Pokud slovo soubor neobsahuje lomítko, potom se jméno soubor hledá
podle seznamu v PATH. Soubor nalezený podle PATH se provede, i
když nebude proveditelný. Pokud se soubor nenajde, je návratový kód
1.
Volitelné argumenty se spuštěnému souboru předají jako poziční
parametry. Pokud argumenty nejsou zadány, potom se poziční
parametry nemění.
alias [přezdívka[=řetězec] ...]
Příkazem se definují přezdívky pro řetězce. Řetězcem může být příkaz nebo
příkaz vč. argumentů, např.
alias l='ls -l'

41

Je-li uvedena přezdívka bez řetězce, vypíše se její aktuální nastavení.
Příkaz alias bez argumentů vypíše aktuální nastavení všech přezdívek.
Návratový kód příkaz vrací nulový vyjma případu, kdy uživatel zadá
k výpisu obsah neexistující přezdívky. Viz též unalias.
bg [úloha] ...
Přesune provádění určené úlohy na pozadí tak, jako by byla spuštěna
oddělovačem příkazů &. Pokud není zadána úloha, potom se příkaz odkazuje
na běžnou úlohu (viz příkaz job).
Příkaz vrací návratový kód 0 vyjma následujících případů: job control je
vypnutý, úloha neexistuje nebo byla spuštěna bez job control. Viz též
fg, kill.

3.32 Interní příkazy shellu (pokrač.)
builtin interní_příkaz [ argumenty]
Příkaz provede zadaný interní příkaz shellu, případně mu předá zadané
argumenty a převezme návratový kód.
Tento příkaz je užitečný v případě, že jsme si definovali funkci shellu,
která má jméno shodné s některým z interních příkazů.
cd [adresář|-]
Příkaz změní běžný adresář na adresář.
Změna se mj. projeví v novém nastavení obsahu proměnné PWD.
Uživatel si může definovat proměnnou prostředí CDPATH a nastavit do
ní seznam cest k adresářům, ve kterých se bude hledat argument

adresář. Jednotlivé cesty se oddělují dvojtečnou (:).
Pokud adresář začíná lomítkem (/), potom se seznam cest v CDPATH
ignoruje.
Příkaz cd vedle proměnné PWD také nastavuje proměnnou OLDPWD.
V této proměnné příkaz uchovává cestu k předchozímu běžnému
adresáři.
Příkaz cd proměnnou OLDPWD použije tehdy, když jako argument
zadáme minus (-). V tomto případě se jako běžný adresář nastaví ten,
který byl běžný před aktuálním běžným adresářem.
command [-pVv] příkaz [ argumenty]
Zadaný příkaz se spustí bez prohledávání seznamu shellovských funkcí.
42

3.33 Interní příkazy shellu (pokrač.)
echo [-neE] [argumenty]
Příkaz vypíše na standardní výstup argumenty oddělené mezerou.
Návratový kód je vždy 0.
Po uvedení volby -n se potlačí výstup nového řádku za posledním
argumentem.
Volba -e zapíná řídicí význam následujících sekvencí. Volba -E tento
význam vypíná (u systémů, které je implicitně interpretují jako řídicí).
\a pípne (alert)
\b o znak vzad (backspace)
\c potlačí výstup nového řádku
\f nová stránka (form feed)
\n nový řádek (new line)
\r návrat na začátek řádku (cr)
\t horizontální tabulátor
\v vertikální tabulátor
\\ obrácené lomítko
\nnn osmičkový kód ASCII znaku
echo -e 'Dnešní datum: \c'; date

eval [argumenty]
Příkaz přečte, expanduje a spojí argumenty do jednoho příkazu. Takto
vytvořený příkaz se předá shellu k expanzi a provedení.
Návratový kód provedeného příkazu se předá jako návratový kód
příkazu eval. Při zadání prázdného nebo žádného argumentu je
návratový kód nulový.
Následující příklad vypíše 'C':
A=B; B=C
eval echo \$$A

3.34 Interní příkazy shellu (pokrač.)
exec [[-] příkaz [argumenty]]

43

Existuje-li příkaz, spustí se nahrazením shellu. Nevytváří se žádný nový
proces. Uvedené argumenty se předají spuštěnému příkazu.
Je-li uvedeno minus (-), potom se jménu nového příkazu v parametru
$0 předřadí minus. Toto login automaticky provádí u prvního
spuštěného procesu.
Pokud příkaz není zadán, uplatní se pouze případná přesměrování a
návratový kód se nastaví na 0.
exit [návratový_kód]
Příkaz ukončí shell a předá návratový kód. Pokud operand zadán není, předá se
návratový kód posledního ukončeného procesu.
export [jméno ... ]
Příkaz uvedené proměnné označí jako exportovatelné do procesů, které budou
aktuálním shellem spouštěny. Takto označené proměnné synovské procesy
dědí, ostatní ne.
Pokud se v příkazu žádný argument neuvede, vypíší se ty proměnné,
které již takto označeny jsou.
Shellovské funkce se nedědí ani po označení tímto příkazem.
fg [úloha] ...
Přesune provádění určené úlohy na popředí.
Pokud není zadána úloha, potom se příkaz odkazuje na běžnou úlohu
(viz příkaz job).
Příkaz vrací návratový kód takový, jaký předá ukončený proces (ten, co
byl přesunut na popředí), nebo vrátí chybový návratový kód pokud: job
control je vypnutý, úloha neexistuje nebo byla spuštěna bez job control.
Viz též bg, kill.

3.35 Interní příkazy shellu (pokrač.)
getopts povolené_volby jméno [argumenty]
#!/bin/sh
while getopts abo: VOLBA
do
case $VOLBA in
a|b) FLAGS=$FLAGS$VOLBA;;
o)

OARG=$OPTARG;;

\?)

echo Pouziti ... 1>&2

44

exit 1;;
esac
done
echo $*
shift $(($OPTIND-1))
echo $*

Při každém volání getopts se předá jedna volba z příkazového řádku do
proměnné jméno a index volby následující se uloží do proměnné
OPTIND . Při každém spuštění shellu nebo skriptu se proměnná
OPTIND nastavuje na hodnotu 1.
Tento skript lze spustit např. jedním z následujících způsobů:
skript -a -b -o "xxx z yy" soubor
skript -ab -o "xxx z xx" -- soubor

Příkaz getopts implicitně zpracovává volby, které byly zadány na
příkazovém řádku. Explicitně však volby můžeme zadat i na řádku
s getopts jako argumenty. V tomto případě se použijí argumenty místo
obsahu příkazového řádku.

3.36 Interní příkazy shellu (pokrač.)
hash [-r] [jméno]
Shell si vytváří pomocný seznam jmen příkazů s již zjištěnou absolutní cestou.
Příkazem hash bez uvedení parametru vypíšeme aktuální verzi
seznamu.
help [vzorek]
Příkaz zobrazí nápovědu buď k interním příkazům zadaným vzorkem, nebo
vypíše seznam všech interních příkazů. Návratový kód je nula vyjma případu,
kdy zadanému vzorku nevyhovoval žádný příkaz.
jobs [-lnp] [úloha ...]
Příkaz vypíše všechny aktivní úlohy. Po uvedení volby -l se zahrnou i čísla
procesů, které tvoří úlohy. Volba -p zapíná výpis pouze čísel prvních procesů
jednotlivých úloh. Zadáním volby -n požadujete výpis pouze změn od
předchozího spuštění příkazu.
kill [-signál] pid|úloha ...
kill -l
Příkaz předá procesu (zadaným číslem pid) nebo úloze (určené kódem úloha)
signál.

45

let argument ...
Příkaz vyčíslí každý ze zadaných artimetických výrazů. Je-li výsledek
posledního aritmetického výrazu nenulový, potom je návratový kód příkazu let
nulový. V opačném případě se vrací jednička.
local [jméno[=hodnota]]
Příkaz definuje lokální proměnnou a přiřadí jí počáteční hodnotu. Příkaz lze
použít pouze uvnitř funkce.
pwd
Příkaz vypíše absolutní cestu k právě nastavenému běžnému adresáři.
3.37 Interní příkazy shellu (pokrač.)
read [jméno ...]
Příkaz přečte ze standardního vstupu jeden řádek a první přečtené slovo přiřadí
prvnímu jménu proměnné, druhé slovo druhé proměnné atd.
Pokud se neuvedou žádná jména, potom se celý přečtený řádek přiřadí
do proměnné REPLY.
Návratový kód je nulový vyjma případu, kdy se načte konec souboru
(^D).
readonly [jméno[= hodnota] ...]
Příkazem označené proměnné lze od okamžiku zadání tohoto příkazu pouze
číst.
return [n]
Příkaz ukončuje provádění funkce a vrátí řízení volajícímu. Návratový kód je
buď n, nebo návratový kód posledního dokončeného příkazu.
Příkaz lze použít ve skriptu spuštěném příkazem '.' (source) se stejným
významem. Při použití příkazu jinde se nastaví chybový návratový kód.
set [{-volby|+volby|--}] [argumenty]
Bez parametrů příkaz vypisuje seznam proměnných a jejich aktuální obsah.
V aktuálním shellu mění nastavení voleb.
Předponou '-' se volba nastavuje, předponou '+' se volba ruší. Volbou '-'
se ukončuje zadávání voleb.
Zadané argumenty se interpretují jako nové hodnoty pozičních
parametrů. Potřebujeme-li zrušit poziční parametry, zadáme:
set --

46

Poziční parametry zrušíme také příkazem 'shift $#'.
shift [n]
Příkaz "posune" poziční parametry o jednu nebo n pozic.
3.38 Interní příkazy shellu (pokrač.)
trap [akce] [signál ...]
Příkazem se definuje, jaká akce se má provést v případě, že shell přijme
(rozpozná) zadaný signál.
Pokud se nezadá akce, nebo se na místě akce zadá '-', potom se
chování pro zadané signály nastaví na implicitní (tak, jak je nastaveno
po spuštění shellu).
Pokud je argument akce prázdný (tj. dva apostrofy bezprostředně za
sebou), potom se signál ignoruje.
Zadáte-li akci pro signál 0 (EXIT), potom se tato akce provede při
ukončování shellu (např. příkazem exit).
type jméno ...
Příkaz pro každé zadané jméno vypíše, jak se bude interpretovat (co se spustí).
ulimit [-volba [limit]]
Příkazem se nastavují limitní hodnoty užívání zdrojů systému.
Tvrdý (hard) limit (volba H) se smí nastavit pouze jednou (příp. jej smí
nastavit pouze superuživatel), uživatel smí měnit hodnotu měkkého
(soft) limitu (volba S) a to nejvýše na tvrdou hodnotu.
-a
vypíší se všechny nastavené limity,
-c
nastaví se maximální velikost paměťového obrazu jádra, které se ukládá na
disku (core, core dump),
-d
maximální velikost datového segmentu nebo haldy,
-f
maximální velikost vytvářeného souboru,
-n
maximální počet otevřených souborů,
-s
maximální velikost segmentu se zásobníkem,
-t
maximum času procesoru,
-v
maximální velikost virtuální paměti.
47

3.39 Interní příkazy shellu (pokrač.)
umask [nnn]
Příkazem se nastaví implicitní formát masky pro přidělování přístupových práv
vytvářenému objektu (souboru, adresáři).
Operand se zadává zpravidla osmičkově a představuje ty bity
přístupových práv, které se nemají nastavit.
Např. 'umask 022' znamená, že se pro skupinu a ostatní nenastaví právo
w (právo zápisu).
unalias [-a] [jméno ...]
Příkazem se odstraní zadané jméno (nebo jména) ze seznamu přezdívek (viz
příkaz alias).
Volbou -a se odstraní všechny přezdívky.
unset jméno ...
Příkaz odstraní uvedené proměnné.
Odstranit nelze proměnné PATH, PS1, PS2, MAILCHECK a IFS (příp. i
další).
wait [n]
Příkaz čeká na ukončení specifikovaného procesu nebo úlohy.
Jakmile se proces ukončí, ukončí se i příkaz a od procesu převezme
návratový kód a vrátí jej jako svůj návratový kód. Pokud zadaný proces
neexistuje, vrací se 127.
Parametr n je buď číslo procesu, nebo kód úlohy. Bez zadání
parametru příkaz čeká na dokončení všech v době zadání příkazu
aktivních synovských procesů a vrátí nulový návratový kód.

3.40 Spuštění shellu
Login shell je ten interpret příkazů, který má jméno ve tvaru '-jméno',
tzn. příkaz 'echo $0' vrátí např. '-ksh'.
Předpokládá se, že jde o první shell uživatele - shell, který se
uživateli spustí při přihlášení.

48

Interaktivní shell je ten, který má standardní vstup a standardní výstup
připojen k terminálu nebo byl spuštěn s volbou -i.
Spuštění login shellu
Po spuštění login shellu se nejprve hledá soubor
/etc/profile
Pokud existuje, provede se. Dále se hledá soubor
~/.profile
Pokud existuje, rovněž se provede.
Spuštění ostatních shellů a pokračování login shellu
Po spuštění každého shellu (tedy i v login shellu po provedení ~/.profile) se
provádí skript, který je uveden v proměnné ENV.
Tuto operaci lze zapsat následovně:
if [ "$ENV" ]; then . $ENV; fi

Zpravidla se takový skript jmenuje ~/.kshrc, ~/.bashrc apod.
Do tohoto souboru zpravidla ukládáme definice vlastních shellovských
funkcí (ty se jinak nedědí), definice aliasů apod.

3.41 Volby shellu
Při spuštění shellu na příkazovém řádku nebo
interaktivně uvnitř aktuálního shellu příkazem set
-a allexport
Automaticky označuje všechny proměnné příznakem exportování (viz export).
-b notify
Zapíná okamžité ohlašování ukončení procesů spuštěných na pozadí (ne až
před výpisem promptu).
-C noclobber
Při přesměrování výstupu (>) do existujícího souboru se tento nepřepíše.
-e errexit
Neinteraktivní shell se ukončí při zjištění prvního chybového návratového
kódu, který není ve skriptu testován. Shell se neukončuje tehdy, pokud proces
s chybným návratovým kódem řídí příkazy if, elif, while, until, nebo pokud je

49

za procesem uveden operátor && nebo || (nebo pokud se návratový kód neguje
uvedením !).
-f noglob
Zakazuje se expanze jmen souborů a adresářů.
-i interactive
Násilně prohlásí shell za interaktivní.
-m monitor
Zapne job control (implicitní varianta v interaktivním shellu).
-n noexec
V neinteraktvní shellu příkazy pouze čte, ale neprovádí je. Volba je vhodná
k testování syntaxe skriptů a ignoruje se v interaktivní shellu.
-o jméno_volby
Za volbou -o se zadávají volby jménem, např. -o allexport. Kromě voleb
uvedených výše a níže, lze zadat i některé další:
ignoreeof
Shell nelze ukončit stiskem ^D.
... pokračuje
3.42 Volby shellu (pokrač.)
-t
Shell se ukončí po přečtení a provedení jednoho příkazu.
-u nounset
Shell vypíše na standardní chybový výstup hlášení při pokusu o expanzi
nedefinované (unset) proměnné. Není-li shell interaktivní, tak se navíc ukončí
s nenulovým návratovým kódem.
-v verbose
Shell opisuje vstup na standardní chybový výstup (užitečné pro ladění skriptů).
-x xtrace
Po expanzi každého příkazu jej před provedením vypíše na standardní chybový
výstup s prefixem '+ ' (nebo s hodnotou uloženou v PS4).
Volby zadávané pouze při spuštění shellu
Pokud není zadána volba -c ani -s, potom se první argument chápe
jako jméno skriptu, který se má v rámci spouštěného shellu provést.
Ostatní argumenty se stávají pozičními parametry.
50

-c řetězec
Shell přečte příkazy z řetězce, provede je a skončí.
-s
Shell se spustí jako interaktivní. Příkazy se čtou ze standardního vstupu a
hlášení shellu se posílají na standardní chybový výstup. Následují-li na
příkazovm řádku argumenty, použijí se jako poziční parametry. Interaktivní
shell se spustí také v případě, že na příkazovém řádku není žádný argument.
-i
Shell se spustí jako interaktivní. Příkazy se čtou ze standardního vstupu a
hlášení shellu se posílají na standardní chybový výstup.
-r
Spustí shell v omezeném (restricted) režimu.
Ostatní volby, které zde lze také použít, jsou popsány pod heslem

Volby shellu.

3.43 Shell v omezeném režimu
Shell se do omezeného (restricted) režimu dostane
buď spuštěním s volbou -r,
nebo spuštění shellu jménem typu rsh, rksh apod.
Tato jména bývají zpravidla odkazy na sh, ksh apod.
Omezený shell se liší v následujících bodech:
1.
2.
3.
4.
5.

je vypnuto přesměrovávání výstupu,
nelze použít interní příkaz cd,
nelze měnit proměnnou PATH,
jména začínající / nejsou akceptována,
proměnná SHELL se nastaví např. na rsh a nelze ji změnit.

Výše uvedená omezení vstupují v platnost až po provedení souboru
.profile

4.

Zpracování textu

4.1 Editor vi - Visual Interactive
Spuštění:
51

vi soubor
Nejdůležitější informace - Editor se ukončuje následovně:
:

Ukončí obrazovkový režim a přejde do řádkového režimu.
q

Ukončí editor tehdy, nebyly-li provedeny změny textu.
q!

Ukončí editor bez uložení změn.
x

Ukončí editor s uložením změn do souboru soubor.
Režimy editoru vi:
Rozlišujeme tyto základní režimy činnosti editoru:
obrazovkový režim
o režim zadávání příkazů (po spuštění)
o vkládací režim
řádkový režim
Do vkládacího režimu se z režimu zadávání příkazů dostaneme příkazy
a, i apod.

Režim se ukončuje stiskem ESC a vrátíme se do režimu zadávání
příkazů.
Do řádkového režimu vstoupíte po stisku :.

4.2 Editor ed
Standardní textový editor UNIXu.
Pracuje pouze v řádkovém režimu (nelze obrazovkový režim).
Editovaný soubor se při otevírání kopíruje do vnitřního bufferu editoru.
Editor ed po celou dobu editace pracuje pouze s pracovní kopií, změna
originálního souboru se provede až po zadání příkazu w.
Editor ed v omezeném režimu se spouští příkazem red (editace pouze
souborů v běžném adresáři, nelze ! apod.).
Příkazy editoru ed lze použít jako příkazy řádkového režimu editoru vi.
Editor ed podporuje pouze základní (omezené) regulární výrazy
(rozšířené viz egrep a další).
Použití regulárních výrazů:
o pro určení řádku (vyhledáním podle vzorku)
o náhrada řetězce (záměna vzorku za jiný)
ed diplomka.tex
1,$s/unix\([^a-z]\)/UNIX\1/g

52

w
q

Editor po načtení souboru do bufferu vypíše počet načtených znaků. Na chybu
reaguje pouze výpisem otazníku.

4.3 Základní regulární výrazy
Jednoznakové regulární výrazy (RE):
4.3.1
Konkrétní znak vyhovuje sám sobě.
a vyhovuje a

4.3.2
Dvojice znaků obrácené lomítko a znak vyhovuje vždy znaku za obráceným
lomítkem. Významné je v souvislosti s těmito zvláštními znaky:
4.3.3
. * [ \ jsou vždy zvláštními znaky
4.3.4
^ je zvláštním znakem na úplném začátku RE nebo v kombinaci s [^]
4.3.5
$ je zvláštním znakem na úplném konci RE
4.3.6
Zvláštním znakem je znak sloužící k oddělení RE; např.
s/RE/náhrada/

4.3.7
. vyhovuje každému znaku vyjma nového řádku.
4..3.8
Neprázdný řetězec znaků uzavřený do dvojice hranatých závorek:
[0-9]
[^0-9]

Použití zvláštních znaků:
[]a-b]
[-a-b]
[a^]
[[a]

4.4 Základní regulární výrazy (2)
53

Konstrukce RE z jednoznakových RE:
4.4.1
Jednoznakový RE (JRE) je RE.
4.4.2
JRE bezprostředně následovaný hvězdičkou vyhovuje řetězci tvořenému
žádným nebo více výskyty JRE.
Pozor: Nepleťte si výraz [a-d]* zapsaný na příkazovém řádku
shellu určený k expanzi s RE.
Řetězec [a-d]* určený k shellovské expanzi odpovídá RE [a-d].*
Při více možnostech se vybere nejdelší možný levostranný výskyt
(hladový přístup).
Nejdelší možný:
aaabbabaabbbbaaaabab
s/[a-b]*/xx/
xx

Levostranný:
ababa
s/aba/xx/
xxba

4.4.3
JRE\{n\} n výskytů JRE
JRE\{n,\} >= n výskytů JRE
JRE\{n,m\} >= n a <= m výskytů JRE
Je-li více možností, vybere se nejvyšší možný počet výskytů.

4.5 Základní regulární výrazy (3)
4.5.1
\( \)

4.5.2
\n
Příklady:

54

Michal Brandejs
s/^\([^ ]*\) \([^ ]*\)$/\2 \1/
Brandejs Michal
echo Michal Brandejs|\
sed 's/^\([^ ]*\) \([^ ]*\)$/\2 \1/'

^\(.*\)\1$

Vyhovuje všemu, co obsahuje 2 opakující se řetězce na řádku.
Využití RE pro hledání slov:
4.5.3
\< znamená začátek slova (číslice, písmena, podtržení)
4.5.4
\> znamená konec slova
Příklad:
\<a\>

'a' pouze jako slovo
Řetězce na začátku a konci řádku:
4.5.5
^ na začátku RE znamená, že se hledá od začátku řádku
4.5.6
$ na konci RE znamená, že se hledá na konci řádku
4.5.7
^...$ celý řádek
Opakování RE:
Prázdný RE se nahradí posledním neprázdným.

4.6 Adresace řádků editoru ed
.

55

běžný řádek
$
poslední řádek editované pracovní kopie
n
n-tý řádek (desítkově)
'x
řádek označený značkou x (písmeno [a-z]; nastavuje se kx)
/RE/
řádek vyhovující RE směrem vpřed
?RE?
řádek vyhovující RE směrem vzad
cokoli+n
od cokoli vpřed o n řádků
cokoli-n
od cokoli vzad o n řádků
+n
od běžného řádku o n řádků vpřed
-n
od běžného řádku o n řádků vzad
cokoli+
přičítá se 1
cokoliodčítá se 1
,
totéž co 1,$
;
totéž co .,$

4.7 Příkazy editoru ed
Na jednom příkazovém řádku se smí vyskytnout nejvýše jeden příkaz.
Za některými příkazy (vyjma e, f, r a w) může být přípona l, n nebo p,
která říká, jakým způsobem se má běžný řádek vypsat.
(.)a
text
.

Příkaz append vloží žádný nebo více řádků textu za adresovaný řádek
pracovní kopie souboru.
(.)c
text
.

56

Příkaz change zruší v pracovní kopii souboru adresované řádky a na místo
těchto řádků vloží žádný nebo více zadaných řádků.
(.,.)d
Příkaz delete zruší v pracovní kopii souboru adresované řádky.
e soubor
Příkazem edit zrušíme celý obsah pracovní kopie souboru a načteme do ní
jmenovaný soubor.
E soubor
Příkaz Edit se chová podobně jako e s tím rozdílem, že nekontroluje, zda od
posledního příkazu w byly v pracovní kopii souboru učiněny změny.
Zapamatuje se použité jméno souboru pro pozdější použití příkazy e, r
a w.
Pokud jméno souboru se nahradí znakem vykřičník (!), potom se zbytek
řádku předá shellu k provedení. Výstup z tohoto příkazu se načte.
f soubor

Příkaz filename změní zapamatované jméno na zadané jméno.
(1,$)g/RE/seznam příkazů
Příkaz global označí všechny řádky, které vyhovují zadanému RE a potom pro
každý označený řádek provede seznam příkazů tak, že zpracovávaný označený
řádek je nastaven jako běžný.

4.8 Příkazy editoru ed (2)
(1,$)G/RE/
Interaktivní příkaz Global nejprve označí všechny řádky, které vyhovují
zadanému RE. Potom pro každý označený řádek provede tyto operace: vypíše
jej, nastaví jej jako běžný a čeká na zadání jednoho příkazu (jiného než a, c, i,
g, G, v a V).
h

Příkaz help vypíše stručné vysvětlení posledního stavu avizovaného výpisem
znaku ?.
H

57

Příkazem Help se editor přepíná do (nebo z) režimu podrobnějšího výpisu
chybových hlášení.
(.)i

text
.

Příkazem insert vkládáme řádky před běžný řádek. Jinak je příkaz totožný
s příkazem a. Adresa 0 není povolena.
(.,.+1)j
Příkaz join spojí posobě jdoucí řádky do jednoho zrušením znaků nového
řádku.
(.)kx
Příkaz mark označí adresovaný řádek malým písmenem x (musí být [a-z]). Na
tento řádek se později budeme odvolávat adresou 'x.
(.,.)l
Příkaz list vypíše adresované řádky následovně: znaky ve výpisu
nejednoznačné (tabulátor, backspace) nahradí symbolickým zápisem,
netisknutelné znaky se nahradí osmičkovým kódem, dlouhé řádky se rozloží,
konec řádku se označí $. Příkaz l smí na řádku následovat za všemi příkazy
vyjma e, f, r a w.

4.9 Příkazy editoru ed (3)
(.,.)ma
Příkaz move přesune adresované řádky za řádek s adresou a.
(.,.)n
Příkaz number vypíše adresované řádky tak, že na začátku bude vždy číslo
řádku a za ním tabulátor.
(.,.)p
Příkaz print vypíše adresované řádky.

58

P

Editor před každým příkazem vypíše prompt ve tvaru hvězdičky.
q

Příkazem quit se ukončí editor bez ukládání obsahu pracovní kopie do
souboru.
Q

Příkazem Quit se editor ukončí bez toho, aniž by se kontrolovalo, zda došlo ke
změně v pracovní kopii od posledního příkazu w.
($)r soubor
Příkaz read načte obsah souboru soubor do editované pracovní kopie.
(.,.)ta
Funkce příkazu je podobná příkazu m. Rozdíl je v tom, že se provádí kopie,
nikoli přesun.
u

Příkaz undo odstraní změny v pracovní kopii, které provedl poslední příkaz a,
c, d, g, i, j, m, r, s, t, v, G nebo V.
(1,$)v/RE/seznam příkazů
Funkce příkazu je podobná příkazu g. Rozdíl je v tom, že se označí řádky,
které nevyhovují zadanému RE.

4.10 Příkazy editoru ed (4)
(1,$)V/RE/
Příkaz je podobný interaktivnímu příkazu G. Liší se v tom, že se označí řádky,
které nevyhovují zadanému RE.
(1,$)w soubor

59

Příkaz write zapíše obsah editované pracovní kopie do souboru.
(1,$)W soubor
Příkaz Write je podobný příkazu w. Rozdíl je v tom, že se neukládá do
souboru od začátku, ale přidává se nakonec.
($)=
Příkaz vypíše číslo adresovaného řádku. Běžný řádek se provedením tohoto
příkazu nemění.
!příkaz shellu

Řetězec za vykřičníkem se předá k provedení shellu. Předtím se však případný
znak procento (%) nahradí zapamatovaným jménem souboru.
(.+1)nový řádek
I pouhá adresa na řádku je příkazem. Běžný řádek se nastaví na tuto adresu a
řádek se vypíše. Pouhý stisk klávesy ENTER je totéž, co zadání příkazu '.+1p'
(užitečné pro procházení souborem).

4.11 Příkazy editoru ed (5)
(.,.)s/RE/náhrada/
(.,.)s/RE/náhrada/g
(.,.)s/RE/náhrada/n

kde n je číslo 1 až 512

Příkaz substitute nahrazuje nalezený vzorek zapsaný RE jeho
náhradou. Prohledává se každý řádek v zadaném rozsahu adres.
V globální variantě (na konci je uvedeno g) se nahradí
všechny vyhovující vzorky na řádku; pokud globální
indikátor není uveden, potom se nahradí pouze první
vyhovující vzorek na každém řádku.
Uvedeme-li číslo n, potom se nahradí pouze n-tý výskyt
vyhovujícího vzorku na řádku. Pokud se ani na jednom

60

z adresovaných řádků nenajde alespoň jeden vyhovující
vzorek, hlásí se chyba.
Na místě oddělovače lomítko (/) se smí uvést libovolný
znak vyjma mezery a znaku nového řádku (znak
bezprostředně za s určuje, jaký oddělovač bude použit).
Běžným řádkem se stane řádek s posledním nalezeným
výskytem vzorku.
Znak ampersand (&) nalezený v řetězci náhrada se
nahradí řetězcem, který vyhovoval RE (na daném řádku,
či vyhovujícím vzorku na řádku). Řídicí význam znaku '&'
lze v řetězci náhrada potlačit uvedením '\&'.
V obecnějším významu můžeme v řetězci náhrada použít
symboly '\n', kde n je číslice. Symbol se nahradí vzorkem,
který vyhovoval obsahu n-té závorky \(...\) uvnitř RE.
Závorky se počítají zleva od jedničky a počítá se vždy
pořadí otevírací závorky.
Je-li jediným znakem řetězce náhrada znak procento (%),
potom se pro definici aktuální náhrady použije řetězec

náhrada z bezprostředně předcházejícího nahrazovacího
příkazu. Řídicí význam znaku '%' se v řetězci náhrada
potlačuje tehdy, pokud řetězec obsahuje více než jeden
znak, nebo pokud je uvedeno '\%'.
Zpracovávaný řádek lze v řetězci náhrada rozdělit na dva
(nebo více) zápisem znaku nového řádku, kterému
bezprostředně předcházel znak obrácené lomítko (\). Tuto
substituci však nelze použít jako součást příkazů g nebo v.

4.12 Neinteraktivní textový editor sed
sed [-n] [-e] skript [-f soubor] [soubor]

61

-n
Řádky se implicitně nekopírují na výstup.
-e skript
Skript k provedení.
-f soubor
Soubor se skriptem.
soubor
Editovaný soubor.
Výstup jde vždy na standardní výstup.
sed kopíruje řádek vstupu do vzorkovacího prostoru.
S obsahem vzorkovacího prostoru se provedou všechny příkazy, jejichž
adresa vyhovuje.
Poté se obsah vzorkovacího prostoru zkopíruje na stand. výstup.
Náhrady:
[adr1[,adr2]]s/RE/náhrada/příznaky
g

Všechny vyhovující řetězce na řádku (impl.

první).
p

Pokud se provedla alespoň jedna náhrada,

opíše řádek na výstup.
w soubor

Totéž do souboru.

A=a:b:c:d
A=`echo $A|sed 's/:b//'`
echo $A

4.13 Rozšířené regulární výrazy (egrep, awk)
Jednoznakový RE následovaný '+' vyhovuje řetězci tvořenému alespoň
jedním výskytem JRE (vs. '*').
Jednoznakový RE následovaný '?' vyhovuje řetězci tvořenému žádným
nebo jedním výskytem JRE.
Jednoznakovými RE jsou:
[:alnum:]
písmena, číslice;
[:alpha:]
písmena;
[:cntrl:]
řídicí znaky (< 32, 127);
[:digit:]
číslice;
[:graph:]
všechny viditelné znaky (33 až 126);
[:lower:]
62

malá písmena;
[:print:]
všechny tištitelné znaky (32 až 126);
[:punct:]
viditelné znaky vyjma písmen a číslic;
[:space:]
mezera, tabulátory, CR, LF;
[:upper:]
velká písmena;
[:xdigit:]
číslice a písmena [a-fA-F].
Symboly používáme uvnitř třídy, např. [[:alnum:]] je totéž co [0-9AZa-z]

4.14 Rozšířené regulární výrazy (2)
\w je synonymem pro [[:alnum:]]
\W je synonymem pro [^[:alnum:]]
\b je prázdný řetězec na hranici slova
\B je prázdný řetězec "zde není hranice slova"

JRE následovaný {m}, {m,}, {,n} nebo {m,n} je RE, který vyhovuje
konkrétnímu počtu výskytů jednoznakového RE.
RE1|RE2
Výsledný RE vyhovuje buď RE1 nebo RE2.
Nejvyšší priorita: ?*+{
Střední priorita: konkatenace RE (dva nebo více RE vedle sebe)
Nejnižší priorita: alternativa |
Prioritu lze měnit závorkami.

ggrep -E 'W{3}' ...
ggrep -E '(A|W){3}' ...

4.15 grep, egrep, fgrep - Global Regular Expression Print
grep
Řádky vyhovující zadanému základnímu RE se vypíší.
grep -E (egrep)
Možnost použití rozšířených RE.

63

grep -F (fgrep)
Vzorek není RE.
grep [-e] vzorek soubor ...
grep -f soubor soubor ...
-i
Ignorují se rozdíly mezi malými a velkými písmeny.
-q
Potlačí se normální výstup (můžeme testovat návratový kód).
-s
Potlačí se chybové výstupy.
-v
Invertuje se význam vzorku.
-l
Místo vyhovujících řádků se vypisují jména souborů, ve kterých vyhovuje
alespoň jeden řádek.
Je-li zadáno více souborů, potom se před každým řádkem vypíše
jméno souboru. Chci-li totéž s jedním souborem:
grep vzorek soubor /dev/null

GNU grep v Systému V se často nazývá ggrep.
-2
Vypíše 2 řádky před a 2 řádky po vyhovujícím řádku.

4.16 sort
Příkaz sort řadí, zatřizuje (merge) a kontroluje seřazení souborů.
-b
Ignoruje se úvodní bílé místo.
-d
Ignorují se všechny znaky vyjma písmen, číslic a bílých míst.
-f
Malá písmena se řadí jako velká.
-n
Řadí se numericky, před číslem se ignoruje libovolně dlouhé bílé místo.
-r
Obrátí se smysl řazení.
-t oddělovač
Uvedený znak se použije pro hledání n-tého pole.
+pos1 [-pos2]

64

Určení řadicích polí (může být i více).
Pole a znaky se číslují od nuly.
-k pos1,pos2
Totéž, ale čísluje se od jedničky.

Další významy příkazu sort:
-c
Provede se kontrola na seřazenost.
-m
Zatřizuje soubory do jednoho. Zatřizování je rychlejší než řazení. Předpokládá
se, že soubory na vstupu jsou již seřazeny.

4.17 cut
Ze souboru vybere určitá pole nebo sloupce.
-b seznam
Určuje se pořadí bajtů na řádku.
-c seznam
Určuje se pořadí znaků na řádku (od -b se může lišit lokalizacemi).
-f seznam
Určuje se pořadí polí na řádku.

seznam např. 1,3,6-8
Čísluje se od jedničky.
-d oddělovač
Oddělovač polí pro -f.
Př: ps -efl|cut -c 7-14,40-53
uniq
Příkaz kopíruje řádky na stand. výstup s tím, že sousední shodné řádky
předá pouze jednou.
Vstup se musí nejprve seřadit příkazem sort.
Př: ps -ef|cut -c1-8|sed 's/ //g'|sort|uniq

4.18 join
65

Slučuje soubory dle slučovacích polí.
SOUBOR1

SOUBOR2

Novacek Jan

Novacek 1.1.1960

Novak Adam

Novak 31.12.1965

Novotny Petr

Novotny 21.2.1968

join SOUBOR1 SOUBOR2
Novacek Jan 1.1.1960
Novak Adam 31.12.1965
Novotny Petr 21.2.1968

-t oddělovač
Implicitně tabulátor.
-1 číslo
-2 číslo
Pořadí slučovacího pole v příslušném souboru (čísluje se od 1). Pouze GNU.
-o seznam
Popis výstupního řádku. Každý element se zadává ve tvaru n.m (n je pořadí
souboru, m je pořadí pole). Seznam musí být zadán jako jedno slovo, položky
se oddělují čárkou.
wc
Vypíše počet bajtů, slov a řádků v souboru nebo souborech.
-c
počet bajtů
-w
počet slov
-l
počet řádků

Př: ls|wc -l

4.19 Příkazy pro textové zpracování:
tail
Příkaz tail vypíše (impl.) 10 posledních řádků.
Př:
tail -2 soubor Vypíše poslední 2 řádky.
tail -f logfile

Trvale vypisuje.

66

pr
Připraví text do podoby pro tisk na tiskárně:
čísluje stránky
přidává hlavičky, patičky
formátuje do sloupců
Př:
pr -4

upraví do 4 sloupců vertikálně

pr -a -4 upraví do 4 sloupců horizontálně
pr -4 -b vertikálně s vyrovnaným počtem řádků na poslední straně

tr

Transformuje znaky (implicitně).
Maže znaky.
Ruší opakující se znaky.
Transformace znaků:
tr sada1 sada2
Znaky nalezené v sadě1 se převedou na odpovídající znaky ze sady2 . Ostatní
znaky se ponechají beze změny.
Př:
tr a-z A-Z
tr '\012' @

Rušení znaků:
tr -d '\000' Zruší všechny bajty obsahující binární nulu.

4.20 Příkazy pro textové zpracování:
cat (Catenate = sřetězit)
Příkaz cat zadané soubory vypíše na standardní výstup.
cat

stnd. vstup přenese na stnd. výstup

cat soubor . . . soubory přenese na stnd. výstup
stnd. vstup přenese na stnd. výstup
cat Př:
cat >
soubor
Text ...
.....

67

^D

Čtení souboru z klávesnice

Př:
Výpis souboru na obrazovku
nl (Number Lines)
cat soubor

Příkaz nl zkopíruje na stnd. výstup obsah stnd. vstupu, nebo obsah souborů s
tím, že před některý nebo každý řádek přidá pořadové číslo řádku.
nl
nl soubor . . .
nl od (Octal Dump)
Vypíše soubory v osmičkové soustavě nebo v jiném určeném formátu.
head
Vypíše (implicitně) 10 prvních řádků.
Př:
Vypíše prvních 5 řádků.
head -5 soubor

4.21 tac
Předá soubory na std. výstup v pořadí od posledního záznamu do prvního.
Nezadáme-li soubor nebo zadáme-li na místě souboru minus '-', potom se
použije std. vstup. Záznamy jsou implicitně odděleny novým řádkem. Jiný
oddělovač záznamů zadáme volbou -s. Oddělovač se implicitně předpokládá
na konci záznamu.
fmt
Upraví text v odstavci tak, aby všechny řádky byly přibližně stejně dlouhé.
fold
Rozdělí dlouhé řádky na více řádků tak, aby řádky nebyly delší než je určená
šířka.
split
Rozdělí jeden soubor do více souborů zadané velikosti. Tu lze specifikovat
počtem řádků nebo bajtů.
csplit
Rozdělí jeden soubor podle zadaných vzorků (kontextově) do více souborů.
sum
Vytvoří kontrolní součet z obsahu souboru. Příkaz se používá pro kontrolu, zda
obsah souboru nedoznal změn. Spočítáme kontrolní součet např. před
přenosem a po něm a obě hodnoty porovnáme.
cksum
Pro každý zadaný soubor počítá kontrolní součet metodou CRC (cyclic
redundancy check).
comm
Porovnává dva seřazené soubory řádek po řádku.
paste
68

Spojuje odpovídající řádky z více souborů do jednoho řádku a ten předá na std.
výstup.
expand
Převádí tabulátory na mezery.
unexpand
Převádí mezery na tabulátory.

5. Další nástroje pro práci s textem
5.1 Procházení adresářovým stromem
find [cesta ...] [výraz]
Cesta odkud se adresářový strom prochází.
Pro každou adresářovou položku provádí výraz
Výraz se vyhodnocuje zleva doprava a dle priorit
Každý operand výrazu nabývá hodnot pravda a nepravda.
Výraz se vyhodnocuje jen do okamžiku, kdy je výsledek jasný, např: 'a
AND b' b se nevyhodnocuje, pokud je a=0
Cesta je implicitně běžný adresář
Výraz je implicitně akce -print
Výraz lze složit z těchto operandů:
Voleb ... Vracejí vždy hodnotu "Pravda"
Testů ... "Pravda" nebo "Nepravda"
Akcí ... "Pravda" nebo "Nepravda"
Neuvedeme-li operátor, použije se implicitní -and

Pozor: * je potřeba ochránit před expanzí shellu!

69

5.2 Procházení adresářovým stromem : find (pokrač.)
Volby find:
-depth Nejprve se zpracuje obsah adresáře před adresářem samým.
-follow Budou se procházet symbolické odkazy.
Testy find:
Numerické hodnoty se vždy zadávají následovně:
+n pro >n
-n pro <n
n pro =n
-atime n Soubor byl naposledy zpřístupněn před n dny.
-empty Soubor nebo adresář je prázdný.
-mtime n Soubor byl naposledy modifikován před n dny.
Uživatel
-user
-name Jméno
-type b blokový speciální soubor
-type c znakový speciální soubor
-type d adresář
-type p roura
-type f soubor
-type l symbol. odkaz

5.3 Procházení adresářovým stromem : find (pokrač.)
Akce find:
-exec příkaz [argumenty]
Provede se zadaný příkaz, je-li návratový kód = 0, vrací se hodnota "Pravda".
{} se nahradí aktuální položkou adresáře.
find . -type f -exec grep -i smaž {} \; -exec rm {} \;
find . -type f -exec grep -i smaž {} \; -exec rm {} \; > /dev/null

-ok příkaz [argumenty]
Totéž, příkaz se nechá před provedením potvrdit.
-print
Na standardní výstup se předá kompletní jméno souboru od zadané cesty.
Vždy "Pravda".
Operátory:
(...)

Závorkování

! výraz

Negace výsledku

výraz1

výraz2 Logický součin.

výraz1 -and výraz2 Logický součin.
výraz1 -or

výraz2 Logický součet.

5.4 Příkazy pro porovnání souborů:
70

cmp
cmp soubor1 soubor2
Porovnává dva soubory a vypíše offset a obsah prvního rozdílného bajtu.
diff
Hledá rozdílné a shodné části dvou souborů, či adresářů. Rozdíly vypisuje v
různých tvarech, implicitně:
LaR - Za řádek "L" prvního souboru je přidán rozsah řádků "R" ve druhém
souboru.
8a12,15
> ...
> ...
> ...

FcT - řádky "F" prvního souboru jsou nahrazeny řádky "T" druhého souboru.
213c214
<

první soubor

-->

druhý soubor

RdL - řádky "R" z prvního souboru chybí ve druhém souboru za řádkem "L".
5,7d3
< ...
< ...

patch
Podle výstupu z diff a orig. souboru vytvoří soubor nový z porovnávaných
souborů.

5.5 Další příkazy pro práci se soubory:
dd (Konvertuje a kopíruje soubor)
Příkaz dd kopíruje soubor ze stnd. vstupu na stnd. výstup se změnou velikosti
bloku a volitelně s konverzemi přenášených dat.
dd [operandy ...]
bs = n
Nastaví velikost vstupního a výstupního bloku.
ibs = n
Vstupní blok.
Obs = n
Výstupní blok.
if = soubor Vstupní soubor místo stnd. vstupu.
of = soubor Výstupní soubor místo stnd. výstupu.
Př:
Úprava velikosti bloku při zápisu na pásku (podle dokumentace zařízení):
tar cvf - * |dd bs=60k of=/dev/rst12

Další operandy viz man dd.

5.6 Další příkazy pro práci se soubory:

71

tee
Příkaz tee čte stnd. vstup, tento kopíruje jak na stnd. výstup, tak i do všech
zadaných souborů.
tee [-a] soubor ...
Volba -a znamená append.
strings
V souborech hledá sekvence tisknutelných znaků a jen ty vypisuje.
strings [-n číslo] soubor ...
Číslo n udává minimální délku vypisované posloupnosti (impl.4)
file
Pokusí se odhadnout typ obsahu zadaného souboru(ů).
file soubor ...
Příkaz v souboru hledá řetězce podle definice v souboru /etc/magic
du
Vypisuje informace o obsazení diskové kapacity.
du [-volby] cesta ...
Kapacitu souboru nebo adresáře vypisuje v blocích (512B) nebo KB
(viz man du).
-a Všechny soubory, ne jenom adresáře.
-k V KB
-s Pro každý zadaný argument vypíše celkovou kapacitu.

5.7 Příkazy pro archivaci souborů
tar (Tape Archiver)
Vytváření / Rozbalování / Prohlížení archivačních souborů.
Určeno pro archivaci adresářových stromů.
tar [-volby] jméno ....
minus není povinné
Volby:
c - vytvoření archivu
x - rozbalení archivu
c - výpis adresáře z archivu

72

Př: tar c *
Všechny soubory běžného adresáře vč. podadresářů uloží do archiv. souboru a
zapíše na /dev/rmt0
Př: tar x
Všechny soubory a podadresáře z archiv. souboru čteného z /dev/rmt0 rozbalí
na místo podle jména v archivu:
absolutní /../..
relativní ../../..
Př: tar x soubor
Z arch. souboru rozbalí pouze uvedený soubor (nebo adresáře vč.
podadresářů).

5.8 Příkazy pro archivaci souborů (pokrač.):
Volby tar:
f
Následující argument se použije jako jméno archivačního souboru místo
/dev/rmt0. Je-li jméno souboru '-', čte/zapisuje se archiv z/do standard.
vstupu/výstupu.
Př: tar cf adresář.tar adresář
tar tf adresář.tar| more
adresář/
adresář/soubor1
.
.
.
tar xf adresář.tar adresář/soubor1

Př: Využití příkazu tar na kopírování celé adresářové struktury. cd odkud; tar cf
- . |(cd kam; tar xf -)

v
Normálně tar nic nevypisuje.
Např: cv vypisuje kompletní jména souborů vkládaná do archivu.
Např: tv vypisuje o souboru více informací.
Informace vypisuje na stnd. výstup, nebo na stnd. chybový výstup při cf
-.
Jiný archivační program: cpio

5.9 Příkazy pro kompresi/dekompresi souborů
compress
Komprimuje uvedené soubory.

73

compress soubor ...
soubor -> soubor.Z
uncompress
uncompress soubor.Z ...
soubor.Z -> soubor
zcat
zcat soubor.Z ...
vypisuje rozbalený obsah komprimovaných souborů.
Gzip soubor -> soubor.gz
gunzip soubor.gz -> soubor
zcat soubor.gz

gzip, gunzip, zcat dosahují lepší kompresní poměr.
Nejsou součástí běžných UNIXů.
zip
zip soubor.zip soubor
unzip
zipsplit
zipsplit [-n velikost] soubor.zip
Rozdělí zip archiv na více archivů velikosti maximálně velikost.

5.10 Další příkazy shellu
who
who
who am i
w
Kdo je přihlášen a co dělá.
last
last [uživatel]
Kdo, kdy odkud a jak dlouho byl přihlášen.
finger
finger @počítač
Kdo je přihlášen na vzdáleném počítači.
finger uživatel@počítač
Informace o uživateli.
write
write uživatel [terminál]
zpráva lokálnímu uživateli, případně i na konkrétní terminál, je-li přihlášen
vícekrát.
mesg
mesg -n = Zakáže se příjem zpráv zaslaných příkazem write.
mesg -y = Povolí.

74

5.11 bc - jazyk libovolně přesného kalkulátoru
Speciální proměnné
ibase
základ vstupní soustavy
obase
základ výstupní soustavy
Př.
bc
ibase=16;obase=2
1A
11010

last
poslední vypsaná hodnota
scale
přesnost v počtu des. číslic (impl. 0)
komentář /* ........ */
výrazy
výraz+výraz
*
/
%

zbytek

^
()

relační výrazy výsledek 1/0; Pravda/Nepravda
< > <= >= == != !výraz
výraz& && výraz výraz || výraz

řízení toku viz awk
if (výraz) then příkaz1 [else příkaz2]
while (výraz) příkaz
...

75

proměnné a pole
proměnné
pole [index]

5.12 matematická knihovna
bc -l

zavede se matemat. knihovna a přesnost se
nastaví na 20.
s(x) sinus x v radiánech
c(x) kosinus
a(x) arcustangens
l(x) přirozený logaritmus
e(x) exp
Př. pi=$(echo "scale=10;4*a(1)" | bc -l)
definice funkcí
define jméno (parametry) {
!nový řádek!
[auto lokální proměnné;] seznam příkazů }
volání:

jméno(paramerty)

Př.: definice funkce pro výpočet faktoriálu
define f (x) {
if (x <= 1) return (1);
return (f(x-1) * x);
}
f(400);

pseudofunkce (GNU)
limits omezení aktuální implementace

76

6. Nějaké příklady
Ve všech souborech v běžném adresáři, které mají příponu jména '.tex' nahraďte řetězec
'\end{syntax}' řetězcem '\end{syntax}%'.

Zjistěte, zda existuje adresář zadaný prvním pozičním parametrem. Pokud ne,
vytvořte jej a tento stav oznamte uživateli hlášením na stnd. chybový výstup.

Vytvořte skript, který smaže všechny soubory zadané jako poziční parametry. Před
mazáním každého souboru nechť se zeptá, zda se tento soubor má smazat. Uživatel
musí odpovědět 'y' nebo 'n'. Pokud odpoví 'y', soubor smažte, pokud odpoví cokoli
jiného, soubor ponechte. Použijte jiné řešení než 'rm -i'.

Předejte na standardní výstup poslední poziční parametr.

Zjistěte, zda existuje proveditelný soubor zadaný prvním pozičním parametrem.
Pokud ano, spusťte jej a předejte mu další poziční parametry.

Následující posloupností příkazů přejmenujte všechny soubory.txt na soubory.TXT v
běžném adresáři. Doplňte příkaz ?????
ls *.txt > pom
ed pom <<EOF
?????
w
q
EOF
sh pom
rm pom

77

Máte v běžném adresáři soubory jmen např.:
1 10 11 2 20 21 22 3 4 5 55 6 70 71

Hromadně přejmenujte všechny soubory pojmenované pouze jednou číslicí na 01 02 03 ...
Ostatní ponechte bez přejmenování.
Napište skript, který zkontroluje, zda je zadán právě jeden poziční parametr a tento
jeden poziční parametr je jméno existujícího neprázdného souboru. Pokud není, pak
o tom vypište hlášení.
Na standardní chybový výstup vypište hlášení '*Stala se chyba*'.
Napište příkaz, který smaže všechny normální soubory v běžném adresáři a všech
jeho podadresářích, které byly naposledy změněny před více než dvěma dny.
Napište příkaz, který smaže všechny normální soubory v běžném adresáři a všech
jeho podadresářích, které neobsahují řetězec 'nemaz'.
Napište příkaz, který smaže všechny soubory (nikoli adresáře) v běžném adresáři a
všech jeho podadresářích, které mají nulovou velikost.
Napište příkaz, který smaže všechny soubory (nikoli adresáře) v běžném adresáři a
všech jeho podadresářích, které obsahují řetězec 'malý pivo'.
Na standardní výstup předejte počet normálních souborů umístěných v adresářovém
podstromu od běžného adresáře, které obsahují alespoň jeden řetězec 'velký pivo'.
Napište příkaz, který v běžném adresáři a všech jeho podadresářích přidá normálním
souborům a podadresářům právo zápisu pro skupinu.
Napište příkaz, který v běžném adresáři a všech jeho podadresářích spočítá počet
souborů a adresářů, které buď vlastní uživatel 'novak', nebo kdekoli ve jméně
obsahují řetězec 'novak'.

78

Michal Brandejs <brandejs>

Soubor obsahuje pouze záznamy tohoto typu. Každý záznam na jednom řádku. Pole na řádku
jsou oddělena mezerou. Všechny záznamy souboru změňte do tvaru:
<brandejs> Brandejs Michal

Napište příslušný příkaz pro editor ed nebo řádkový režim editoru vi. Realizujte jedním
příkazem.

Michal Brandejs <brandejs>

Soubor obsahuje pouze záznamy tohoto typu. Každý záznam na jednom řádku. Pole na řádku
jsou oddělena mezerou. Všechny záznamy souboru změňte do tvaru:
Jmeno: Michal Prijmeni: Brandejs e-mail: brandejs

Napište příslušný příkaz pro editor ed nebo řádkový režim editoru vi. Realizujte jedním
příkazem.
Napište příkaz pro editor ed nebo řádkový režim editoru vi, který všechny řádky
v souboru nahradí z tvaru:
brandejs:*:11000:100:Michal Brandejs:/home/brandejs:/bin/ksh

do tvaru:
Michal Brandejs <brandejs>

Realizujte jedním příkazem.
Soubor CONFIG obsahuje řádky ve tvaru:
starysemestr:1995zima
tedsemestr:1996leto
novysemestr:1996zima

Nastavte proměnnou SEMESTR na hodnotu klíče 'tedsemestr' ze souboru CONFIG (tj.
v tomto případě nechť proměnná SEMESTR nabyde hodnoty 1996leto).
Napište filtr pomocí příkazu 'sed', který bude měnit záznamy z typu:

79

Michal Brandejs:brandejs:brandejs:odborný asistent

na typ:
Michal Brandejs:brandejs:odborný asistent

tj. vypustí se třetí pole. Čtvrté pole v originálním záznamu může obsahovat libovolný počet
dvojteček.
Ze souboru /etc/passwd, který má záznamy ve tvaru:
brandejs:x:11000:100:Michal Brandejs:/home/brandejs:/bin/ksh

vytvořte seznam ve tvaru (je zaměněno pořadí příjmení a jména):
Brandejs, Michal
...

Všem položkám běžného adresáře nastavte přístupová práva tak, aby s nimi mohl
jakkoli pracovat pouze vlastník. Pozor: neproveditelným souborům nenastavujte 'x'.
Všem adresářům a proveditelným souborům běžného adresáře nastavte přístupová
práva tak, aby do nich mohli vstupovat a spouštět je i ostatní. Přístupová práva
neproveditelných souborů ponechte beze změny.
Napište všechny potřebné příkazy, kterými vytvoříte adresář pom, v němž bude moci
kdokoli vytvářet soubory, ale rušit je bude smět pouze jejich vlastník.
Jakým příkazem zruším všechny soubory a podadresáře (i neprázdné) běžného
adresáře, jejichž jméno začíná tečkou (pozor - nesmějí se zrušit položky '.' a '..').
Provedeme-li posloupnost příkazů:
rm -rf /tmp/a
mkdir -p /tmp/a/b/c /tmp/a/b/d /tmp/a/b/d/e
touch /tmp/a/b/d/f /tmp/a/b/f
ls -ld /tmp/a/b

Kolik odkazů bude uvedeno na řádku, který vypíše příkaz ls?

80

Všem adresářům v běžném (pouze) adresáři přidejte právo čtení a vstupu pro
ostatní.
Napište skript, který soubor zadaný prvním pozičním parametrem zkopíruje do
souborů zadaných druhým až posledním pozičním parametrem.
Napište skript, kterému při spuštění zadáme na příkazovém řádku jména souborů.
Pokud je zadáno více než 100 souborů, skript všechny soubory smaže.
Napište skript, který smaže všechny soubory zadané pozičními parametry. Pokud je
však některý z pozičních parametrů '*', vypište dotaz, zda lze všechny soubory
v běžném adresáři smazat. Pokud je odpověď 'y', potom je smažte.
Napište skript, který přečte všechny soubory zadané na příkazovém řádku a jejich
obsah předá na standardní výstup (varianta příkazu cat) s tím, že opakující se řádky
(ze všech) předá pouze jednou. Opakující se řádky nemusejí být bezprostředně za
sebou. Pořadí řádků na výstupu nemusí odpovídat pořadí řádků na vstupu.
Napište skript, který v běžném adresáři ze všech souborů vyřadí řádky, které
v prvním sloupci začínají znakem #.
Napište příkaz, který čte standardní vstup a na výstup předá pouze ty řádky, které
v prvním sloupci nezačínají znakem #
Proměnná KDO obsahuje libovolně dlouhý seznam uživatelů oddělených mezerami.
Vyřaďte vlastní jméno, které získáte z proměnné LOGNAME.
Napište skript, který ze všech souborů v běžném adresáři vyřadí řádky, které začínají
řetězcem 'Jan Novák'.
Ze seznamu cest zadaných v proměnné PATH vyjměte cestu '.'.
Napište skript, který proměnným prom1, prom2, prom3, ... přiřadí postupně obsahy
pozičních parametrů (první do prom1, druhý do prom2, ...). Počet pozičních
parametrů není omezen.

81

Proměnné LAST přiřaďte poslední poziční parametr.

82

