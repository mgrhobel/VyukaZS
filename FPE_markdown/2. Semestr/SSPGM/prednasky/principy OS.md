---
title: "principy OS.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/prednasky/principy OS.pdf"
date: 2009-02-19
type: PDF (text-based)
---

Principy operačního systému UNIX
Martin Beran
13. října 2003

SISAL MFF UK, Malostranské nám. 25, 118 00 Praha 1
beran@ss1000.ms.mff.cuni.cz
http://www.ms.mff.cuni.cz/~beran/

1

Obsah
• úvod, vývoj UNIXu a C, programátorské nástroje
• základní pojmy a konvence UNIXu a jeho API
• přístupová práva, periferní zařízení, systém souborů
• manipulace s procesy, spouštění programů
• signály
• synchronizace a komunikace procesů
• síťová komunikace
• vlákna
• UNIX z pohledu správce
• závěrečná všehochuť podle toho, kolik zbude času (bezpečnost,
locales, pseudoterminály, X Window)
2

Literatura (1)
• Brodský, J.; Skočovský, L.: Operační systém UNIX a jazyk C.
SNTL, Praha 1989; ISBN 80-03-00049-1
• Skočovský, L.: Principy a problémy operačního systému UNIX.
Science, 1993; ISBN 80-901475-0-X
• Skočovský, Luděk: UNIX, POSIX, Plan9. L. Skočovský, Brno,
1998; ISBN 80-902612-0-5
• Valley, John: Programming for UNIX. Sams Publishing, 1992;
ISBN 0-672-48518-4
• Jelen, Milan: UNIX V - programování v systému. Grada, Praha
1993; ISBN 80-85623-16-1

3

Literatura (2)
• Goodheart, B.; Cox, J.: The Magic Garden Explained: the
Internals of UNIX System V Release 4. Prentice Hall, 1994;
ISBN 0-13-098138-9
• Bach, Maurice J.: Principy operačního systému UNIX. SAS, 1993
• The Single UNIX Specification, Version 2 (UNIX 98). The
Open Group; http://www.UNIX-systems.org
• The Single UNIX Specification, Version 3. The Open Group;
http://www.unix-sustems.org/version3
• manuálové stránky (zejm. sekce 2, 3)

4

Literatura (3)
• Linux - Dokumentační projekt. Computer Press, 1998; ISBN
80-7226-114-2 http://www.cpress.cz/knihy/linux
• Linux Documentation Project. http://linuxdoc.org/
• Welsh, M.; Kaufman, L.: Používáme Linux. Computer Press, 1997;
ISBN 80-7226-001-4
• Stevens, W. Richard: UNIX Network Programming, Vol. 1 –
Networking APIs: Sockets and XTI. Prentice Hall, 1998; ISBN
0-13-490012-X
• Stevens, W. Richard: UNIX Network Programming, Vol. 2 –
Interprocess Communication. Prentice Hall, 1999; ISBN
0-13-081081-9
5

(Pre)historie UNIXu
• 1925 – Bell Laboratories – výzkum v komunikacích
• 60. léta – s General Electric a MIT vývoj OS Multics (MULTIplexed
Information and Computing System)
• 1969 – Bell Labs opouští projekt, Ken Thompson píše asembler,
základní OS a systém souborů pro PDP-7
• 1970 – Multi-cs ⇒ Uni-x (snad Brian Kernighan)
• 1971 – Thompson žádá nový počítač PDP-11 pro další vývoj –
zamítnuto
• Thompson předstírá vývoj systému automatizované kanceláře –
počítač přidělen – zpracování textů
• 1973 – UNIX přepsán do jazyka C vytvořeného za tím účelem
Dennisem Ritchiem
6

Divergence UNIXu
• pol. 70. let – uvolňování UNIXu na univerzity: především University
of California v Berkeley
• 1979 – v Berkeley přepisují UNIX pro 32bitový VAX ⇒ BSD Unix
(Berkeley System Distribution) verze 3.0; dnes verze 4.4
• Bell Labs přecházejí pod AT&T a pokračují ve vývoji verze III
(1982) až V.4 (1984) – tzv. SVR4
• UNIX uvolněn i pro komerci: Microsoft a SCO vyvíjejí pro Intel
XENIX
• vznikají UNIX International, OSF (Open Software Foundation),
X/OPEN, . . .
• 1991 – Linus Torvalds zahájil vývoj OS Linux, verze jádra 1.0 byla
dokončena v r. 1994
7

Současné UNIXy
Komerční
• SUN: Sun OS, Solaris
• SGI: Irix
• Compaq: Tru64 UNIX
• IBM: AIX
• HP: HP-UX
• Novell: UNIXware
• SCO: SCO Unix
Open source
• FreeBSD, NetBSD, OpenBSD
• Linux
8

Standardy UNIXu
• SVID (System V Interface Definition)
– „fialová knihaÿ, kterou AT&T vydala poprvé v roce 1985
– dnes ve verzi SVID3 (odpovídá SVR4)

• POSIX (Portable Operating System based on UNIX)
– série standardů organizace IEEE značená P1003.xx, postupně je
přejímá vrcholový nadnárodní orgán ISO

• XPG (X/Open Portability Guide)
– doporučení konsorcia X/Open, které bylo založeno v r. 1984 předními
výrobci platforem typu UNIX

• Single UNIX Specification
– standard organizace The Open Group, vzniklé v roce 1996 sloučením
X/Open a OSF
– dnes Version 3, předchozí Version 2 (UNIX 98)
– splnění je nutnou podmínkou pro užití obchodního názvu UNIX
9

Jazyk C
• téměř celý UNIX napsaný v C, pouze nejnižší strojově závislá část
v assembleru ⇒ poměrně snadná přenositelnost
• navrhl Dennis Ritchie z Bell Laboratories v roce 1972.
• následník jazyka B Kena Thomsona z Bell Laboratories.
• vytvořen jako prostředek pro přenos OS UNIX na jiné počítače –
silná vazba na UNIX.
• varianty jazyka:
– původní K&R C
– standard ANSI/ISO C

10

Formáty dat
• pořadí bytů – závisí na architektuře počítače
–

–

big endian: 0x11223344 =

11

22

33

44

addr +

0

1

2

3

little endian: 0x11223344 =

44

33

22

11

addr +

0

1

2

3

• Řádky textových souborů končí LF (nikoliv CRLF). Volání
putc(’\n’) tedy píše pouze jeden znak.

11

Deklarace a definice funkce
• K&R
– deklarace
návratový_typ indentifikátor();
– definice
návratový_typ indentifikátor(par [,par...]);
typ par;...
{ /* tělo funkce */ }

• ANSI
– deklarace
návratový_typ indentifikátor(typ par [,typ par...]);
– definice
návratový_typ indentifikátor(typ par [,typ par...]);
{ /* tělo funkce */ }
12

Utility
cc, c89∗ , gcc†

překladač C

CC, g++†

překladač C++

ld

spojovací program (linker)

cxref ∗

křížové odkazy ve zdrojových textech v C

sccs∗ , rcs,cvs

správa verzí zdrojového kódu

make∗

řízení překladu podle závislostí

ar∗

správa knihoven objektových modulů

dbx, gdb†

debuggery

prof, gprof †

profilery

∗

UNIX 98

†

GNU
13

Konvence pro jména souborů
*.c

jména zdrojových souborů programů v C

*.cc

jména zdrojových souborů programů v C++

*.h

jména hlavičkových souborů (headerů)

*.o

přeložené moduly (object files)

a.out

jméno spustitelného souboru (výsledek úspěšné kompilace)

/usr/include

kořen stromu systémových headerů

/usr/lib/lib*.a

statické knihovny objektových modulů

/usr/lib/lib*.so

umístění dynamických sdílených knihoven
objektových modulů

14

Princip překladu

util.c
msg()
{
puts();
}

systémová
knihovna

program
a.out

main
msg ??

main
msg

util.o
msg
puts ??

linker

main()
{
msg();
}

objektové moduly
main.o

překladač

zdrojové moduly
main.c

msg
puts

puts

puts

15

Překlad jednoho modulu (preprocesor)

/usr/include/stdio.h
int puts(char *s);

main.i
int puts(char *s);
preprocesor

main.c
#include <stdio.h>
#include "mydef.h"
main()
{
puts(MSG);
}

mydef.h
#define MSG "Ahoj"
extern int var a;

16

extern int var a;
main()
{
puts("Ahoj");
}

Překlad jednoho modulu (kompilátor)
main.s

main.i

.globl main
.type main, @function
main:
pushhl %ebp
movl %esp, %ebp
pushl $.LC0
call puts
addl $4, %esp
.L1:
leave
ret

extern int var a;
main()
{
puts("Ahoj");
}

kompilátor

int puts(char *s);

17

Překlad jednoho modulu (assembler)
main.s
.globl main
.type main, @function
main:
pushhl %ebp
movl %esp, %ebp
pushl $.LC0
call puts
addl $4, %esp
.L1:
leave
ret

assembler

main.o

18

457f 464c 0101 0001
0000 0000 0000 0000
0001 0003 0001 0000
0000 0000 0000 0000
00ec 0000 0000 0000
0034 0000 0000 0028

Kompilátor
• Volání:
cc [options ] soubor ...
• Nejdůležitější přepínače:
-o soubor jméno výsledného souboru
-c

pouze překlad (nelinkovat)

-E

pouze preprocesor (nepřekládat)

-S

pouze překlad do assembleru

-Olevel

nastavení úrovně optimalizace

-g

překlad s ladicími informacemi

-Djméno

definuj makro pro preprocesor

-Ujméno

oddefinuj makro pro preprocesor

-Iadresář

umístění #include souborů
19

Předdefinovaná makra
__FILE__, __LINE__, __DATE__, __TIME__, __cplusplus, apod.
standardní makra kompilátoru C/C++
unix
vždy definováno v Unixu
mips, i386, sparc
hardwarová architektura
linux, sgi, sun, bsd
klon operačního systému
_POSIX_SOURCE, _XOPEN_SOURCE
překlad podle příslušné normy
Pro překlad podle určité normy by před prvním #include měl být řádek
s definicí makra:
UNIX 98

#define _XOPEN_SOURCE 500

SUSv3

#define _XOPEN_SOURCE 600

POSIX

#define _POSIX_C_SOURCE 200112L
20

Linker
• Volání:
ld [options ] soubor ...
cc [options ] soubor ...
• Nejdůležitější přepínače:
-o soubor

jméno výsledného souboru (default a.out)

-llib

linkuj s knihovnou liblib.so nebo liblib.a

-Lpath

cesta pro knihovny (-llib )

-shared

vytvořit sdílenou knihovnu

-non shared

vytvořit statický program

21

Práce s archivem (ar)
• manipulace s archivy souborů (např. staticky linkované knihovny)
• soubory uloženy bez cesty
• volání:
ar [-dmpqrtx] [-abuv] [pos ] archive [file ...]
• operace:
– r(eplace) – přepis souboru v archivu, přepínače:
∗ a(fter), b(ehind) – umístění za/před soubor pos
∗ u(pdate) – přepis jen novějších
– q(uick) – rychlé přidání na konec (nekontroluje duplicitu)
– m(ove), d(elete) – přesun/smazání souboru v archivu
– p(rint), t(able) – výpis obsahu souboru/archivu
– x(tract) – výpis z archivu do normálního souboru
22

Řízení překladu a linkování (make)
• zdrojové texty
main.c
#include "util.h"
main()
{
msg();
}

util.h
void msg();

• závislosti

util.c
#include "util.h"
msg()
{
puts();
}

• soubor Makefile
prog : main.o util.o
main.c
&
cc -o prog main.o util.o
main.o
main.o : main.c util.h
%
&
util.h
prog
cc -c main.c
&
%
util.o : util.c util.h
util.o
%
cc -c util.c
util.c
23

Syntaxe vstupního souboru (make)
• popis závislostí cíle:

targets : [files ]

• prováděné příkazy:

<Tab>command

• komentář:

#comment

• pokračovací řádek:

line-begin \
line-continuation

24

Makra (make)
• definice makra:
name = string
• pokračování vkládá mezeru
• nedefinovaná makra jsou prázdná
• nezáleží na pořadí definic různých maker
• definice na příkazové řádce:
make target name =string
• vyvolání makra:
$name (pouze jednoznakové name ),
${name } nebo $(name )
• systémové proměnné jsou přístupné jako makra
25

Debugger dbx
• Volání:
dbx [ options ] [ program [ core ] ]
• Nejběžnější příkazy:
run [arglist ]
where
print expr
set var = expr
cont
next, step
stop condition
trace condition
command n
help [name ]
quit

start programu
vypiš zásobník
vypiš výraz
změň hodnotu proměnné
pokračování běhu programu
proveď řádku (bez/s vnořením do funkce)
nastavení breakpointu
nastavení tracepointu
akce na breakpointu (příkazy následují)
nápověda
ukončení debuggeru
26

Debugger gdb
• Volání:
gdb [ options ] [ program [ core ] ]
• Nejběžnější příkazy:
run [arglist ]
bt
print expr
set var = expr
cont
next, step
break condition
help [name ]
quit

start programu
vypiš zásobník
vypiš výraz
změň hodnotu proměnné
pokračování běhu programu
proveď řádku (bez/s vnořením do funkce)
nastavení breakpointu
nápověda
ukončení debuggeru

27

Standardní hlavičkové soubory (ANSI)
stdlib.h
errno.h
stdio.h
ctype.h
string.h
time.h
math.h
setjmp.h
assert.h
stdarg.h
limits.h
signal.h

...
...
...
...
...
...
...
...
...
...
...
...

základní makra a funkce
ošetření chyb
vstup a výstup
práce se znaky
práce s řetězci
práce s datem a časem
matematické funkce
dlouhé skoky
ladicí funkce
práce s proměnným počtem parametrů
implementačně závislé konstanty
ošetření signálů
28

Standardní hlavičkové soubory (2)
unistd.h

...

nejpoužívanější systémová volání

sys/types.h

...

datové typy používané v API UNIXu

fcntl.h

...

řídící operace pro soubory

sys/stat.h

...

informace o souborech

dirent.h

...

procházení adresářů

sys/wait.h

...

čekání na synovské procesy

sys/mman.h

...

mapování paměti

curses.h

...

ovládání terminálu

regex.h

...

práce s regulárními výrazy

29

Standardní hlavičkové soubory (3)
sys/ipc.h

...

společné deklarace pro System V IPC

sys/msg.h

...

fronty zpráv

sys/sem.h

...

semafory (System V)

semaphore.h

...

semafory (POSIX)

sys/shm.h

...

sdílená paměť (System V)

pthread.h

...

vlákna (POSIX threads)

sys/socket.h

...

síťová komunikace

arpa/inet.h

...

manipulace se síťovými adresami

30

Funkce main()
• Při spuštění programu je předáno řízení funkci main().
• int main (int argc, char *argv []);
– argc . . . počet argumentů příkazové řádky
– argv . . . pole argumentů
∗ podle konvence je argv[0] cesta k programu
∗ poslední prvek je argv[argc] == NULL

– návrat z main() nebo volání exit() ukončí program
– standardní návratové hodnoty EXIT_SUCCESS (0) a
EXIT_FAILURE (1)
ls -l /
argc
argv

3

argv[0]
argv[1]
argv[2]
argv[3]

31

"ls"
"-l"
"/"

Proměnné prostředí
• Seznam všech proměnných prostředí (environment variables) se
předává jako proměnná
extern char **environ;
• Je to pole ukazatelů (ukončené NULL) na řetězce ve tvaru:
proměnná =hodnota
environ
environ[0]
environ[1]
environ[2]
environ[3]

"SHELL=/bin/bash"
"DISPLAY=:0"
"LOGNAME=beran"

32

Manipulace s proměnnými prostředí
• přímá změna proměnné environ
• char *getenv (const char *name );
– vrátí hodnotu proměnné name
• int putenv (char *string );
– vloží string ve tvaru jméno =hodnota do prostředí (přidá novou
nebo modifikuje existující proměnnou)
• změny se přenášejí do synovských procesů, ale prostředí otce zůstává
nezměněno

33

Zpracování argumentů programu
• obvyklý zápis v shellu: program -přepínače argumenty
• přepínače tvaru -x nebo -x hodnota , kde x je jedno písmeno nebo
číslice, hodnota je libovolný řetězec
• Několik přepínačů lze sloučit dohromady: ls -lRa
• Argument ‘ --‘ nebo první argument nezačínající ‘ - ukončuje
přepínače, následující argumenty nejsou považovány za přepínače, i
když začínají znakem ‘ -‘ .
• Tento tvar argumentů požaduje norma a lze je zpracovávat
automaticky funkcí getopt().

34

Zpracování přepínačů: getopt()
int getopt(int argc, char *const argv [],
const char *optstring );
extern char *optarg ;
extern int optind, opterr, optopt ;
• Funkce dostane parametry z příkazového řádku, při každém volání
zpracuje a vrátí další přepínač. Pokud má přepínač hodnotu, vrátí ji
v optarg.
• Když jsou vyčerpány všechny přepínače, vrátí -1 a v optind je číslo
prvního nezpracovaného argumentu.
• Možné přepínače jsou zadány v optstring, když za znakem
přepínače následuje ‘ :‘ , má přepínač hodnotu.
• Při chybě (neznámý přepínač, chybí hodnota) vrátí ‘ ?‘ , uloží znak
přepínače do optopt a když opterr nebylo nastaveno na nulu,
vypíše chybové hlášení.
35

Příklad použití getopt()
struct {
int a, b; char c[128];
} opts;
int opt; char *arg1;
while((opt = getopt(argc, argv, "abc:")) != -1)
switch(opt) {
case ’a’: opts.a = 1; break;
case ’b’: opts.b = 1; break;
case ’c’: strcpy(opts.c, optarg); break;
case ’?’: fprintf(stderr,
"usage: %s [-ab] [-c Carg] arg1 arg2 ...\n",
basename(argv[0])); break;
}
arg1 = argv[optind];
36

GNU tvar přepínačů
• GNU programy používají dlouhý zápis přepínačů:
--jméno nebo --jméno=hodnota
• Argumenty se permutují tak, aby přepínače byly na začátku, např.
ls * -l je totéž jako ls -l *, standardní chování lze docílit
nastavením proměnné POSIXLY_CORRECT.
• Zpracovávají se funkcí getopt long(), která používá pole struktur
popisujících jednotlivé přepínače:
struct option {
const char *name; /* Jméno přepínače */
int has arg; /* Hodnota: ano, ne, volitelně */
int *flag; /* Když je NULL, funkce vrací val, jinak vrací 0
a dá val do *flag */
int val; /* Návratová hodnota */
};
37

Dlouhé přepínače (GNU): getopt long()
int getopt long(int argc, char * const argv [],
const char *optstring,
const struct option *longopts,
int *longindex );
• optstring obsahuje jednopísmenné přepínače, longopts obsahuje
adresu pole struktur pro dlouhé přepínače (poslední záznam pole
obsahuje samé nuly)
• Pokud funkce narazí na dlouhý přepínač, vrací odpovídající val nebo
nulu (pokud flag nebyl NULL), jinak je chování shodné s getopt().
• Do *longindex (když není NULL) dá navíc index nalezeného
přepínače v longopts.
38

Klasická struktura operačního systému
aplikace

rozhraní volání služeb
správa souborů
správa I/O zařízení
správa paměti
správa procesoru
hardware

39

Struktura OS UNIX
uživatelský proces
přerušení
návrat

uživatelský
režim

rozhraní volání jádra
režim
jádra

subsystém
řízení souborů
buffery

subsystém
řízení
procesů
a paměti

znakové
blokové
ovladače

strojově závislá vrstva ovládání hardware
hardware
40

IPC
plánovač
přidělování
paměti

Procesy, vlákna, programy
• proces . . . systémový objekt charakterizovaný svým paměťovým
prostorem a kontextem a identifikovaný jednoznačným číslem
(process ID, PID); „kód a data v pamětiÿ
• vlákno (thread) . . . systémový objekt, který existuje uvnitř procesu
a je charakterizován svým stavem. Všechna vlákna jednoho procesu
sdílí stejný paměťový prostor kromě registrů procesoru a zásobníku
(automatických proměnných); „linie výpočtuÿ, „to, co běžíÿ
• program . . . soubor přesně definovaného formátu obsahující
instrukce, data a služební informace nutné ke spuštění; „spustitelný
soubor na diskuÿ
◦ Paměť se přiděluje procesům.
◦ Procesory se přidělují vláknům.
◦ Vlákna jednoho procesu mohou běžet na různých procesorech.
41

Volání služeb a komunikace mezi procesy
• UNIX
proces

proces

proces

rozhraní volání jádra
jádro
• distribuovaný OS
uživatelský
proces

uživatelský
proces

server

server

server

jádro

jádro

jádro

jádro

jádro

42

Systémová volání, funkce
• V UNIXu se rozlišují systémová volání a knihovní funkce. Toto
rozlišení dodržují i manuálové stránky: sekce 2 obsahuje systémová
volání (syscalls), sekce 3 knihovní funkce (library functions).
– Knihovní funkce se vykonávají v uživatelském režimu, stejně jako
ostatní kód programu.
– Systémová volání mají také tvar volání funkce. Příslušná funkce
ale pouze dohodnutým způsobem zpracuje argumenty volání a
předá řízení jádru pomocí instrukce synchronního přerušení. Po
návratu z jádra funkce upraví výsledek a předá ho volajícímu.
• Standardy tyto dvě kategorie nerozlišují, protože z hlediska
programátora je jedno, jestli určitou funkci provede jádro nebo
knihovna.
43

Návratové hodnoty systémových volání
• Celočíselná návratová hodnota (int, pid t, off t, apod.)
– >= 0 . . . operace úspěšně provedena
– == -1 . . . chyba
• Návratová hodnota typu ukazatel
– != NULL . . . operace úspěšně provedena
– == NULL . . . chyba
• Po neúspěšném volání je kód chyby v proměnné
extern int errno;
• Úspěšné volání nemění hodnotu v errno! Je tedy třeba nejprve
otestovat návratovou hodnotu a pak teprve errno.
• Chybové hlášení podle hodnoty v errno vypíše funkce
void perror(const char *s );
• Textový popis chyby s daným číslem vrátí funkce
char *strerror(int errnum );
44

Seznam uživatelů (/etc/passwd)
beran:x:1205:106:Martin Beran:/home/beran:/bin/bash
Význam jednotlivých polí:
• uživatelské jméno
• zakódované heslo (nově v /etc/shadow)
• číslo uživatele (UID); superuživatel (root) má UID 0
• číslo primární skupiny (GID)
• plné jméno
• domovský adresář
• login-shell
45

Seznam skupin (/etc/group)
sisal:*:106:forst,beran
Význam jednotlivých polí:
• jméno skupiny
• heslo pro přepnutí do skupiny
• číslo skupiny (GID)
• seznam členů skupiny
Ve skupině jsou navíc i všichni uživatelé, kteří ji mají uvedenu jako svoji
primární skupinu.

46

Testování přístupových práv
• Uživatel je identifikován číslem uživatele (UID) a čísly skupin, do
kterých patří (primary GID, supplementary GIDs).
• Tuto identifikaci dědí každý proces daného uživatele.
• Soubor S má vlastníka (U IDS ) a skupinového vlastníka (GIDS ).
• Algoritmus testování přístupových práv pro proces
P (U IDP , GIDP , SU P G) a soubor S(U IDS , GIDS ):
Jestliže

P má vůči S

if(U IDP == 0)

. . . všechna práva

else if(U IDP == U IDS )

. . . práva vlastníka

else if(GIDP == GIDS ||
GIDS ∈ SU P G)

. . . práva člena skupiny

else

. . . práva ostatních
47

Reálné a efektivní UID/GID
• U každého procesu se rozlišuje:
– reálné UID (RUID) – který uživatel je skutečným vlastníkem
procesu
– efektivní UID (EUID) – uživatel, jehož práva proces používá
• Podobně se rozlišuje reálné a efektivní GID procesu.
• Obvykle platí RUID==EUID && RGID==EGID.
• Propůjčování práv . . . spuštění programu s nastaveným SUID (set
user ID) bitem změní EUID procesu na UID vlastníka programu,
RUID se nezmění.
• Podobně SGID bit ovlivňuje EGID procesu.
• Při kontrole přístupových práv se používají vždy EUID, EGID a
supplementary GIDs.
48

Identifikace vlastníka procesu
• uid t getuid(void)
Vrací reálné user ID volajícího procesu.
• uid t geteuid(void)
Vrací efektivní user ID volajícího procesu.
• gid t getgid(void)
Vrací reálné group ID volajícího procesu.
• gid t getegid(void)
Vrací efektivní group ID volajícího procesu.
• int getgroups(int gidsz, gid t glist [])
Do glist dá nejvýše gidsz supplementary group IDs volajícího
procesu a vrátí počet všech GIDs procesu.
49

Změna vlastníka procesu
• int setuid(uid t uid );
– V procesu s EUID == 0 nastaví RUID i EUID na uid.
– Pro ostatní procesy nastavuje jen EUID, a uid musí být buď
rovné RUID, nebo původní hodnotě EUID procesu, která je
uschovaná jako saved set-user-ID.
• int setgid(gid t gid );
obdoba setuid(), nastavuje group-IDs procesu.
• int setgroups(int ngroups, gid t *gidset );
Nastavuje supplementary GIDs procesu, může být použito jen
superuživatelským procesem.

50

Systém souborů
• Adresáře tvoří strom, spolu se soubory acyklický graf (na jeden
soubor může existovat více odkazů).
• Navíc každý adresář obsahuje odkaz na sebe ‘ .‘ (tečka) a na
nadřazený adresář ‘ ..‘ (dvě tečky).
• Pomocí rozhraní systému souborů se přistupuje i k dalším entitám
v systému:
– periferní zařízení
– pojmenované roury
– sokety
– procesy (/proc)
– paměť (/dev/mem, /dev/kmem)
– pseudosoubory (/dev/tty, /dev/fd/0,. . . )

• Z pohledu jádra je každý obyčejný soubor pole bajtů.
• Všechny (i síťové) disky jsou zapojeny do jednoho stromu.
51

Jednotný hierarchický systém souborů
/

etc

dev

usr
tty

52

home

Typická skladba adresářů
/bin

...

základní systémové příkazy

/dev

...

speciální soubory (zařízení, devices)

/etc

...

konfigurační adresář

/lib

...

základní systémové knihovny

/tmp

...

veřejný adresář pro dočasné soubory

/home

...

kořen domovských adresářů

/var/adm

...

administrativní soubory

/usr/include

...

knihovny headerů pro C

/usr/local

...

lokálně instalovaný software

/usr/man

...

manuálové stránky

/var/spool

...

spool (pošta, tisk,. . .)
53

Přístup k periferním zařízením
• Adresář /dev obsahuje speciální soubory zařízení. Proces otevře
speciální soubor systémovým voláním open() a dále komunikuje se
zařízením pomocí volání read(), write(), ioctl(), apod.
• Speciální soubory se dělí na
– znakové . . . data se přenáší přímo mezi procesem a ovladačem
zařízení, např. sériové porty
– blokové . . . data prochází systémovou vyrovnávací pamětí (buffer
cache) po blocích pevně dané velikosti, např. disky

• Speciální soubor identifikuje zařízení dvěma čísly
– hlavní (major) číslo . . . číslo ovladače v jádru
– vedlejší (minor) číslo . . . číslo v rámci jednoho ovladače

54

Fyzické uložení systému souborů
• Systém souborů (svazek, filesystem) lze vytvořit na:
– oddílu disku (partition) – část disku, na jednom disku může být více
oddílů
– logickém oddílu (logical volume) – takto lze spojit více oddílů, které
mohou být i na několika discích, do jednoho svazku.

• Další možnosti: striping, mirroring, RAID
/home

/

disk 1

/usr

disk 2

55

disk 3

Organizace systému souborů
blok č.
0
zaváděcí blok (boot block)
1
superblok
2 oblast i-uzlů (i-nodes)

...
oblast datových bloků

56

0

9 12

Navigace v adresářové struktuře
/etc/passwd

i-nodes
i-node 2

data

i-node 37

i-node 71

.
..

2
2

.
..

37
2

etc

37

passwd

71

57

root:x:0:...

Linky
hard link
/var
password

originál
/etc
20

...
i-nodes
data

0

passwd

symbolický link
/usr
20

...
...

...
...

20
root:x:0:...

passwd

31
../etc/passwd

Hard linky lze vytvářet pouze v rámci jednoho (logického) svazku.

58

31

Vylepšení systému souborů
• cíl: snížení fragmentace souborů, omezení pohybu hlav disku
umístěním i-uzlů a datových bloků blíž k sobě
• UFS (Unix File System), původně Berkeley FFS (Fast File System)
• členění na skupiny cylindrů, každá skupina obsahuje
– kopii superbloku
– řídicí blok skupiny
– tabulku i-uzlů
– bitmapy volných i-uzlů a datových bloků
– datové bloky
• bloky velikosti 4 až 8 kB, fragmenty bloků
• jména dlouhá 255 znaků
59

Virtuální systém souborů (Virtual File
System)
struct
struct
struct
struct
struct file
file
file
file
file
*file
f vnode
f vnode
f vnode
f vnode
VNODE

VNODE

VNODE

VNODE

VNODE

v data
INODE

v data
INODE

v data
INODE

v data
INODE

v data
INODE
s realvp

ufs vnodeops
ufs file system

s5 vnodeops
s5 file system
60

spec vnodeops
spec file system

Hierarchie souborových systémů
struct file
f vnode

vfs mount list
rootvfs
VFS

VFS

vfs next

vfs next

vfs data

vfs data

root vnode
super block

root vnode
super block

vfs op

v vfsp VNODE
v op
INODE

vnodeops
vfs mountedhere

vfs op

vfs vnodecovered
v vfsp
vfsops

vfsops

VNODE
v op
INODE

vfssw[]

vsw vfsops
vnodeops

61

mount
point
in
rootvfs

Otevřené soubory z pohledu jádra
struct proc
uf next

struct
ufchunk

uf next

struct
ufchunk

. . .2 1 0

struct
ufchunk

. . .2 1 0

u proc

u first

struct user

. . . 2 1 0 uf ofile[]

p cred

struct
cred

f cred

f next

struct
file

struct
file

struct
file

struct
file

f prev

VNODE

struct
file
f vnode

VNODE

VNODE

VNODE
62

VNODE

struct file
*file

Oprava konzistence souborového systému
• Pokud není svazek před zastavením systému korektně odpojen,
mohou být data v nekonzistentním stavu.
• Ke kontrole a opravě svazku slouží příkaz fsck. Postupně testuje
možné nekonzistence:
– vícenásobné odkazy na stejný blok
– odkazy na bloky mimo rozsah datové oblasti systému souborů
– špatný počet odkazů na i-uzly
– nesprávná velikost souborů a adresářů
– neplatný formát i-uzlů
– bloky které nejsou obsazené ani volné
– chybný obsah adresářů
– neplatný obsah superbloku
• Operace fsck je časově náročná.
• Žurnálové systémy souborů (např. XFS v IRIXu, EXT3 v Linuxu)
nepotřebují fsck.
63

Přístupová práva
vlastník (u) skupina (g) ostatní (o)
z }| {
z }| {
z }| {
nejvyšší bit

4
2

suid
sgid
sticky

1

r
w
x

• SGID pro soubor bez práva spuštění pro skupinu: kontrola zámků
při každém přístupu (mandatory locking)
• sticky bit pro adresáře: právo mazat a přejmenovávat soubory mají
jen vlastníci souborů
• SGID pro adresář: nové soubory budou mít stejnou skupinu jako
adresář
64

API pro soubory
• Před použitím musí proces každý soubor nejprve otevřít voláním
open() nebo creat().
• Otevřené soubory jsou dostupné přes deskriptory souborů (file
descriptors), číslované od 0, více deskriptorů může sdílet jedno
otevření souboru (mód čtení/zápis, ukazovátko pozice)
• Standardní deskriptory:
– 0 . . . standardní vstup (jen pro čtení)
– 1 . . . standardní výstup (jen pro zápis)
– 2 . . . chybový výstup (jen pro zápis)
• Čtení a zápis z/do souboru: read(), write()
• Změna pozice: lseek(), zavření: close(), informace: stat(),
řídicí funkce: fcntl(), práva: chmod(), . . .
65

Otevření souboru: open()
int open(const char *path, int oflag, ... );
• Otevře soubor daný jménem (cestou) path, vrátí číslo jeho
deskriptoru (použije první volné), oflag je OR-kombinace příznaků
– O RDONLY/O WRONLY/O RDWR . . . otevřít pouze pro čtení / pouze
pro zápis / pro čtení i zápis
– O APPEND . . . připojování na konec
– O CREAT . . . vytvořit, když neexistuje
– O EXCL . . . chyba, když existuje
– O TRUNC . . . zrušit předchozí obsah
– ...
• Při O CREAT definuje třetí parametr přístupová práva (ještě se
modifikuje podle umask).
66

Vytvoření souboru
• open() s příznakem O CREAT vytvoří soubor, pokud ještě neexistuje.
V zadané hodnotě přístupových práv se vynulují bity, které byly
nastaveny pomocí funkce
mode t umask(mode t cmask );
int creat(const char *path, mode t mode );
• Funkce je ekvivalentní volání
open(path, O WRONLY|O CREAT|O TRUNC, mode);
int mknod(const char *path, mode t mode, dev t dev );
• Vytvoří speciální soubor zařízení.
int mkfifo(const char *path, mode t mode );
• Vytvoří pojmenovanou rouru.
67

Zápis a čtení souborů: write(), read()
ssize t write(int fildes, const void *buf, size t nbyte );
• Do otevřeného souboru s číslem deskriptoru fildes zapíše na
aktuální pozici max. nbyte bajtů dat uložených od adresy buf.
• Vrací velikost skutečně zapsaných dat (<= nbyte).
ssize t read(int fildes, void *buf, size t nbyte );
• Z otevřeného souboru s číslem deskriptoru fildes přečte od
aktuální pozice max. nbyte bajtů dat a uloží je od adresy buf.
• Vrací počet skutečně přečtených bajtů (<= nbyte), 0 znamená
konec souboru.

68

Uzavření souboru: close()
int close(int fildes );
• Uvolní deskriptor fildes, pokud to byl poslední deskriptor, který
odkazoval na otevření souboru, zavře soubor a uvolní záznam o
otevření souboru.
• Když je počet odkazů na soubor 0, jádro uvolní data souboru. Tedy i
po zrušení všech odkazů (jmen) mohou se souborem pracovat
procesy, které ho mají otevřený. Soubor se smaže, až když ho zavře
poslední proces.
• Když se zavře poslední deskriptor roury, všechna zbývající data
v rouře se zruší.
• Při skončení procesu se automaticky provede close() na všechny
deskriptory.
69

Příklad: kopírování souborů
#define BUFSIZE 4096
int main(int argc, char *argv[])
{
char buf[BUFSIZE];
int inf, outf; int len, ilen, olen;
inf = open(argv[1], O_RDONLY);
outf = creat(argv[2], 0666);
while((ilen = read(inf, buf, BUFSIZE)) >0)
write(outf, buf, ilen);
close(inf);
close(outf);
exit(0);
}
70

Nastavení pozice: lseek()
off t lseek(int fildes, off t offset, int whence );
• Nastaví pozici pro čtení a zápis v otevřeném souboru daném číslem
deskriptoru fildes na hodnotu offset.
• Podle hodnoty whence se offset počítá:
– SEEK SET . . . od začátku souboru
– SEEK CUR . . . od aktuální pozice
– SEEK END . . . od konce souboru
• Vrací výslednou pozici počítanou od začátku souboru.
• lseek(fildes, 0, SEEK CUR) pouze vrátí aktuální pozici.

71

Změna velikosti: truncate()
int truncate(const char *path, off t length );
int ftruncate(int fildes, off t length );
• Změní délku souboru zadaného cestou nebo číslem deskriptoru na
požadovanou hodnotu.
• Při zkrácení souboru zruší nadbytečná data.
• Standard ponechává nespecifikované, jestli funguje prodloužení
souboru (s vyplněním přidaného úseku nulami). Proto je lepší
k prodloužení souboru použít
char buf = ’\0’;
lseek(fildes, length-1, SEEK_SET);
write(fildes, buf, 1);
72

Duplikace deskriptoru: dup(), dup2()
int dup(int fildes );
• Duplikuje deskriptor fildes na první volný deskriptor, vrátí nový
deskriptor, který odkazuje na stejné otevření souboru.
• Ekvivalent fcntl(fildes, F DUPFD, 0);
int dup2(int fildes, int fildes2 );
• Duplikuje deskriptor fildes na deskriptor fildes2.
• Ekvivalent
close(fildes2);
fcntl(fildes, F DUPFD, fildes2);

73

Příklad: implementace shellového
přesměrování
• $ program < in > out 2>> err
close(0);
open("in", O_RDONLY);
close(1);
open("out", O_WRONLY | O_CREAT | O_TRUNC, 0666);
close(2);
open("err", O_WRONLY | O_CREAT | O_APPEND, 0666);
• $ program > out 2>&1
close(1);
open("out", O_WRONLY | O_CREAT | O_TRUNC, 0666);
close(2);
dup(1);
74

Řídicí funkce souborů a zařízení: fcntl(),
ioctl()
int fcntl(int fildes, int cmd, ...);
• Slouží pro duplikaci deskriptorů, nastavování zámků, testování a
nastavování různých příznaků souboru.
Příklad: zavření standardního vstupu při spuštění programu (volání
typu exec)
fcntl(0, F SETFD, FD CLOEXEC);
int ioctl(int fildes, int request, ... );
• Rozhraní pro řídicí funkce periferních zařízení
• Používá se jako univerzální rozhraní pro ovládání zařízení, každé
zařízení definuje množinu příkazů, kterým rozumí.
75

Informace o souboru: stat()
int stat(const char *path, struct stat *buf );
int fstat(int fildes, struct stat *buf );
• Pro soubor zadaný cestou, resp. číslem deskriptoru, vrátí strukturu
obsahující informace o souboru, např.:
– st ino . . . číslo i-uzlu
– st dev . . . číslo zařízení obsahujícího soubor
– st uid, st gid . . . vlastník a skupina souboru
– st mode . . . typ a přístupová práva
– st size, st blksize, st blocks . . . velikost souboru
v bajtech, velikost bloku a počet bloků
– st atime, st mtime, st ctime . . . časy posledního přístupu,
modifikace souboru a modifikace i-uzlu
– st nlink . . . počet odkazů na soubor
76

Informace o souboru (2)
• Pro typ souboru jsou v <sys/stat.h> definovány konstanty S_IFMT
(maska pro typ), S_IFBLK (blokový speciální), S_IFCHR (znakový
speciální), S_IFIFO (FIFO), S_IFREG (obyčejný), S_IFDIR
(adresář), S_IFLNK (symlink).
• Typ lze testovat pomocí maker S_ISBLK(m), S_ISCHR(m),
S_ISFIFO(m), S_ISREG(m), S_ISDIR(m), S_ISLNK(m).
• Konstanty pro přístupová práva: S_IRUSR (čtení pro vlastníka),
S_IWGRP (zápis pro skupinu), atd.
int lstat(const char *path, struct stat *buf );
• Když je zkoumaný soubor symlink, stat() vrátí informace o
souboru, na který ukazuje. Tato funkce vrací informace o symlinku.
77

Nastavení časů souboru
int utime(const char *path, const struct utimbuf *times );
• Nastaví čas poslední modifikace souboru a čas posledního přístupu
k souboru.
• Nelze změnit čas poslední modifikace i-uzlu.
• Volající proces musí mít právo zápisu pro soubor.

78

Test přístupových práv: access()
int access(const char *path, int amode );
• Otestuje, zda volající proces má k souboru path práva daná
OR-kombinací konstant v amode:
– R_OK . . . test práva na čtení
– W_OK . . . test práva na zápis
– X_OK . . . test práva na spuštění
– F_OK . . . test existence souboru

79

Nastavení přístupových práv
int chmod(const char *path, mode t mode );
• Změní přístupová práva souboru path na hodnotu mode.
• Tuto službu může volat pouze vlastník souboru nebo superuživatel
(root).
int chown(const char *path, uid t owner, gid t group );
• Změní vlastníka a skupinu souboru path. Hodnota -1 znamená
zachovat vlastníka, resp. skupinu.
• Měnit vlastníka může jen superuživatel, aby uživatelé nemohli
obcházet nastavené quoty tím, že své soubory předají někomu
jinému.
• Běžný uživatel může měnit skupinu svých souborů a musí přitom
patřit do cílové skupiny.
80

Manipulace se jmény souborů
int link(const char *path1, const char *path2 );
• Vytvoří nový odkaz (položku adresáře) path2 na soubor path1.
Funguje pouze v rámci jednoho svazku.
int unlink(const char *path );
• Zruší odkaz na soubor. Po zrušení posledního odkazu na soubor a
uzavření souboru všemi procesy je soubor smazán.
int rename(const char *old, const char *new );
• Změní jméno souboru (přesně odkazu na soubor) z old na new.
Funguje pouze v rámci jednoho svazku.

81

Symbolické linky
int symlink(const char *path1, const char *path2 );
• Vytvoří symbolický link path2 → path1.
• Cíl symbolického linku může být i na jiném svazku, popřípadě
nemusí vůbec existovat.
int readlink(const char *path, char *buf, size t bufsize );
• Do buf dá max. bufsize znaků z cesty, na kterou ukazuje symlink
path.
• Vrátí počet znaků uložených do buf.
• Obsah buf není zakončen nulou (znakem ’\0’)!

82

Manipulace s adresáři
int mkdir(const char *path, mode t mode );
• Vytvoří nový prázdný adresář, (bude obsahovat pouze položky ‘ .‘ a
‘ ..‘ ).
int rmdir(const char *path );
• Smaže adresář path. Adresář musí být prázdný.
DIR *opendir(const char *dirname );
struct dirent *readdir(DIR *dirp );
int closedir(DIR *dirp );
• Slouží k sekvenčnímu procházení adresářů.
• Struktura dirent obsahuje položky
– d_ino . . . číslo i-uzlu
– d_name . . . jméno souboru
83

Příklad: procházení adresáře
int main(int argc, char *argv[])
{
int i;
DIR *d;
struct dirent *de;
for(i=1; i<argc; i++) {
d = opendir(argv[i]);
while(de = readdir(d))
printf("%s\n", de->d_name);
closedir(d);
}
exit(0);
}
84

Aktuální adresář procesu
• Každý proces má svůj aktuální (pracovní) adresář, vůči kterému jsou
udávány relativní cesty k souborům. Počáteční nastavení pracovního
adresáře se dědí od otce při vzniku procesu.
int chdir(const char *path );
int fchdir(int fildes );
• Nastaví nový pracovní adresář procesu.
char *getcwd(char *buf, size t size );
• Uloží absolutní cestu k aktuálnímu adresáři do pole buf, jeho délka
(size) musí být aspoň o 1 větší než délka cesty.

85

Paměť procesu v uživatelském režimu
text
data
bss

nelze adresovat
uživ. programem

{

zásobník
oblast user

86

















adresovatelné

uživ. programem
















Paměť procesu v režimu jádra
text jádra
data a bss jádra
(tabulky, proměnné, apod.)
struktura user
bežícího procesu

extern struct user u;
zásobník jádra

87

Paměťové segmenty procesu
a segs
struct as

read only
shared

s as
s prev

text

s next

read/write
private

data

read/write
private

zásobník

read/write
shared

sdílená paměť

struct proc

88

Virtuální paměť

  




paměť
procesu 1

reálná
paměť

paměť
procesu 2

  
 

paměť
procesu 3

   
   
  




89

paměť
procesu 4

     
     
  
  
 

Implementace virtuální paměti
• Procesy v UNIXu používají k přístupu do paměti virtuální adresy,
které na fyzické adresy převádí hardware ve spolupráci s jádrem
systému.
• Při nedostatku volné paměti se odkládají nepoužívané úseky paměti
do odkládací oblasti (swap) na disk.
• Před verzí SVR2 se procesem swapper (nyní sched) odkládaly celé
procesy.
• Od verze SVR2 se používá stránkování na žádost (demand paging)
a copy-on-write. Stránky se alokují až při prvním použití a privátní
stránky se kopírují při první modifikaci. Uvolňování a odkládání
jednotlivých stránek provádí proces pageout, odkládání celých
procesů nastupuje až při kritickém nedostatku paměti.
90

Stavy procesu
běží
v uživ.
režimu

vznik

*

přerušení
preempce
připraven
v paměti

odložení

běží
v režimu
jádra

přidělení
procesoru

zavedení

připraven
na disku

návrat

probuzení
probuzení
91

zánik

†

wait

exit
kill

mátoha
(zombie)

uspání
spí
v paměti
odložení
spí
na disku

Plánování procesů
• Preemptivní plánování – jestliže se proces nevzdá procesoru (neuspí
se čekáním na nějakou událost), je mu odebrán procesor po uplynutí
časového kvanta.
• Procesy jsou zařazeny do front podle priority, procesor je přidělen
vždy prvnímu připravenému procesu z fronty, která má nejvyšší
prioritu.
• V SVR4 byly zavedeny prioritní třídy a podpora procesů reálného
času (real-time) s garantovanou maximální dobou odezvy.
• Na rozdíl od předchozích verzí znamená v SVR4 vyšší číslo vyšší
prioritu.

92

Prioritní třídy
• systémová
– priorita 60 až 99
– rezervována pro systémové procesy (pageout, sched, . . . )
– pevná priorita
• real-time
– priorita 100 až 159
– pevná priorita
– pro každou hodnotu priority definováno časové kvantum
• sdílení času (time-shared)
– priorita 0 až 59
– proměnná dvousložková priorita, pevná uživatelská a proměnná
systémová část – pokud proces hodně využívá procesor, je mu
snižována priorita (a zvětšováno časové kvantum)
93

Identifikace procesu
pid t getpid(void);
• Vrací process ID volajícího procesu.
pid t getpgrp(void);
• Vrací ID skupiny procesů, do které patří volající proces.
pid t getppid(void);
• Vrací process ID rodiče.
pid t getsid(pid t pid );
• Vrací group ID vedoucího procesu session (sezení, terminálové
relace) pro proces pid (0 znamená pro volající proces)
94

Vytvoření procesu: fork()
getpid() == 1234
switch(pid = fork()) {
case -1: /* Chyba */
case 0: /* Dítě */
default: /* Rodič */
}
rodič (pokračuje)

dítě (nový proces)

getpid()==1234, pid==2345
switch(pid = fork()) {
case -1: /* Chyba */
case 0: /* Dítě */
default: /* Rodič */
}

getpid()==2345, pid==0
switch(pid = fork()) {
case -1: /* Chyba */
case 0: /* Dítě */
default: /* Rodič */
}
95

Spuštění programu: exec
extern char **environ;
int execl(const char *path, const char *arg0, ... );
• Spustí program, jehož kód je v souboru path, další argumenty volání
se předají spuštěnému programu v parametrech argc a argv funkce
main(). Seznam argumentů je ukončen pomocí (char *)0, tj.
NULL. Argument arg0 by měl být stejný jako path.
• Úspěšné volání execl() se nikdy nevrátí, protože spuštěný program
zcela nahradí dosavadní adresový prostor procesu.
• Program dědí proměnné prostředí, tj. obsah environ.
• Handlery signálů se nahradí implicitní obsluhou.
• Zavřou se deskriptory souborů, které mají nastavený příznak
FD CLOEXEC (implicitně není nastaven).
96

Varianty služby exec
int execv(const char *path, char *const argv []);
• Obdoba execl(), ale argumenty jsou v poli argv, jehož poslední
prvek je (char *)0.
int execle(const char *path, const char *arg0, ... ,
char *const envp []);
• Obdoba execl(), ale místo environ se použije envp.
int execve(const char *path, char *const argv [],
char *const envp []);
• Obdoba execv(), ale místo environ se použije envp.
int execlp(const char *file, const char *arg0, ...);
int execvp(const char *file,char *const argv []);
• Obdoby execl() a execv(), ale pro hledání spustitelného souboru
se použije proměnná PATH.
97

Formát spustitelného souboru
• Common Object File Format (COFF) – starší System V
• Extensible Linking Format (ELF) – nový v SVR4
• Často se mluví o a.out formátu, protože tak se jmenuje (pokud není
použit přepínač -o) výstup linkeru.
• Formát ELF:

hlavička souboru
tabulka programových hlaviček
sekce 1
..
.
sekce N
tabulka hlaviček sekcí
98

Ukončení procesu
void exit(int status );
• Ukončí proces s návratovým kódem status.
• Nikdy se nevrátí na instrukci následující za voláním.
pid t wait(int *stat loc );
• Počká, až skončí některý synovský proces, vrátí jeho PID a do
stat_loc uloží návratový kód, který lze dále testovat:
– WIFEXITED(stat val) . . . proces volal exit()
– WEXITSTATUS(stat val) . . . argument exit()
– WIFSIGNALED(stat val) . . . proces dostal signál
– WTERMSIG(stat val) . . . číslo signálu
– WIFSTOPPED(stat val) . . . proces pozastaven
– WSTOPSIG(stat val) . . . číslo signálu
pid t waitpid(pid t pid, int *stat loc, int opts );
• Čekání na jeden proces.
99

Příklad: spuštění programu a čekání
int status;
pid = fork()
rodič
if(pid > 0)

wait(&status);

dítě
else
execl("/bin/ls",
"/bin/ls", "/", NULL);
/bin/ls
int main(int argc, char *argv[])
{
...
exit(result);
}
100

Roura: pipe()
int pipe(int fildes [2]);
• Vytvoří rouru a dva deskriptory
– fildes[0] . . . čtení z roury
– fildes[1] . . . zápis do roury
• Roura zajišťuje synchronizaci čtení a zápisu:
– zapisující proces se zablokuje, když je roura plná,
– čtoucí proces se zablokuje, když je roura prázdná.
• Čtoucí proces přečte konec souboru (tj. read() vrátí 0), pokud jsou
uzavřeny všechny kopie fildes[1].
• Pojmenovaná roura (vytvořená voláním mkfifo()) funguje stejně,
ale má přidělené jméno v systému souborů a mohou ji tedy používat
libovolné procesy.
101

Příklad: roura mezi dvěma procesy
shell: ls | more

int pd[2];
pipe(pd);
switch(fork()) {

producent (dítě)

konzument (rodič)

case 0:

default:

close(1);

close(0);

dup(pd[1]);

dup(pd[0]);

close(pd[0]);

close(pd[0]);

close(pd[1]);

close(pd[1]);

execl("/bin/ls", "/bin/ls",

execl("/bin/more",

"/", NULL);

"/bin/more", NULL);

pd[1]

pd[0]

/bin/ls

/bin/more
102

Mapování souborů do paměti (1)
void *mmap(void *addr, size t len, int prot, int flags,
int fildes, off t off );
• Do paměťového prostoru procesu od adresy addr (0 . . . adresu
přidělí jádro) namapuje úsek délky len začínající na pozici off
souboru reprezentovaného deskriptorem fildes.
• Vrací adresu namapovaného úseku nebo MAP FAILED.
• V prot je OR-kombinace PROT READ (lze číst), PROT WRITE (lze
zapisovat), PROT EXEC (lze spouštět), nebo PROT NONE (nelze
k datům přistupovat).
• Ve flags je OR-kombinace MAP PRIVATE (změny jsou privátní pro
proces, neukládají se do souboru), MAP SHARED (změny se ukládají
do souboru), MAP FIXED (jádro nezmění addr).
103

Mapování souborů do paměti (2)
int msync(void *addr, size t len, int flags );
• Zapíše změněné stránky v úseku len bajtů od adresy addr do
souboru. Hodnota flags je OR-kombinace
– MS ASYNC . . . asynchronní zápis
– MS SYNC . . . synchronní zápis
– MS INVALIDATE . . . zrušit namapovaná data, která se liší od
obsahu souboru
int munmap(void *addr, size t len );
• Zapíše změny a zruší mapování souboru v délce len od adresy addr.
int mprotect(void *addr, size t len, int prot );
• Změní přístupová práva k namapovanému úseku souboru. Hodnoty
prot jsou stejné jako u mmap().
104

Příklad: mapování souborů do paměti
int main(int argc, char *argv[])
{
int fd, fsz; char *addr, *p1, *p2, c;
fd = open(argv[1], O_RDWR);
fsz = lseek(fd, 0, SEEK_END);
p1 = addr = mmap(0, fsz, PROT_READ|PROT_WRITE,
MAP_SHARED, fd, 0);
p2 = p1 + fsz - 1;
while(p1<p2) {
c = *p1; *p1++ = *p2; *p2-- = c;
}
munmap(addr, fsz);
close(fd);
exit(0);
}
105

Dynamický přístup ke knihovnám
void *dlopen(const char *file, int mode );
• Zpřístupní knihovnu v souboru file, vrátí handle nebo NULL.
• V mode je OR-kombinace RTLD NOW (okamžité relokace),
RTLD LAZY (odložené relokace), RTLD GLOBAL (symboly budou
globálně dostupné), RTLD LOCAL (nebudou globálně dostupné).
void *dlsym(void *handle, const char *name );
• Vrátí adresu symbolu zadaného jména z knihovny.
int dlclose(void *handle );
• Ukončí přístup ke knihovně.
char *dlerror(void);
• Vrátí textový popis chyby při práci s knihovnami.
106

Příklad: zpřístupnění knihovny
void *handle; char *libname = "libm.so", *fun name = "sin";
double x = 1.3, y, (*fun)(double);
if( !(handle = dlopen(libname, RTLD_NOW)) ) {
fprintf(stderr, "%s\n", dlerror());
exit(1);
}
fun = dlsym(handle, fun_name);
if(err = dlerror()) {
fprintf(stderr, "%s\n", err);
exit(1);
}
y=fun(x);
dlclose(handle);
107

Signály
• Informují proces o výskytu určité události.
• Na uživatelské úrovni zpřístupňují mechanismy přerušení.
• Kategorie signálů:
– chybové události generované běžícím procesem, např. pokus o
přístup mimo přidělenou oblast paměti (SIGSEGV)
– asynchronní události vznikající mimo proces, např. signál
poslaný jiným procesem, vypršení nastaveného času (SIGALRM),
odpojení terminálu (SIGHUP), stisk Ctrl-C (SIGINT)
• Nejjednodušší mechanismus pro komunikaci mezi procesy – nesou
pouze informaci o tom, že nastala nějaká událost.
• Zpracovávají se asynchronně – příchod signálu přeruší běh procesu a
vyvolá handler.
108

Poslání signálu
int kill(pid t pid, int sig );
• Pošle signál s číslem sig procesu (nebo skupině procesů) podle
hodnoty pid:
– > 0 . . . procesu s číslem pid
– == 0 . . . všem procesům ve stejné skupině
– == -1 . . . všem procesům, kromě systémových
– < -1 . . . procesům ve skupině abs(pid)
• sig == 0 znamená, že se pouze zkontroluje oprávnění poslat signál,
ale žádný signál se nepošle.
• Právo procesu poslat signál jinému procesu závisí na UID obou
procesů.
109

Ošetření signálů
• implicitní akce (default)
– zrušení procesu (exit)
– ukončení procesu a uložení obsahu jeho paměti do souboru core
(core)
– ignorování (ignore)
– pozastavení procesu (stop)
– pokračování pozastaveného procesu (continue)
• ignorování signálu
• ošetření uživatelsky definovanou funkcí (handler), po návratu
z handleru proces pokračuje od místa přerušení
Signály SIGKILL a SIGSTOP vždy vyvolají implicitní akci (zrušení, resp.
pozastavení).
110

Přehled signálů (1)
SIGABRT
SIGALRM
SIGFPE
SIGHUP
SIGILL
SIGINT
SIGKILL
SIGPIPE
SIGQUIT
SIGSEGV
SIGTERM
SIGUSR1
SIGUSR2
SIGCHLD

ukončení procesu (core)
plánované časové přerušení (exit)
chyba aritmetiky v pohyblivé čárce (core)
odpojení terminálu (exit)
nepovolená instrukce (core)
stisk speciální klávesy Ctrl-C (exit)
zrušení procesu (exit, nelze ošetřit ani ignorovat)
zápis do roury, kterou nikdo nečte (exit)
stisk speciální klávesy Ctrl-\ (core)
použití nepovolené adresy v paměti (core)
zrušení procesu (exit)
uživatelsky definovaný signál 1 (exit)
uživatelsky definovaný signál 2 (exit)
změna stavu synovského procesu (ignore)
111

Přehled signálů (2)
SIGCONT
SIGSTOP
SIGTSTP
SIGTTIN
SIGTTOU
SIGBUS
SIGPOLL
SIGPROF
SIGSYS
SIGTRAP
SIGURG
SIGVTALRM
SIGXCPU
SIGXFSZ

pokračování pozastaveného procesu (continue)
pozastavení (stop, nelze ošetřit ani ignorovat)
pozastavení z terminálu Ctrl-Z (stop)
čtení z terminálu procesem na pozadí (stop)
zápis na terminál procesem na pozadí (stop)
přístup k nedef. části paměťového objektu (core)
testovatelná událost (exit)
vypršení profilujícího časovače (exit)
chybné systémové volání (core)
ladicí přerušení (core)
urgentní událost na soketu (ignore)
vypršení virtuálního časovače (exit)
překročení časového limitu CPU (core)
překročení limitu velikosti souboru (core)
112

Nastavení obsluhy signálů
int sigaction(int sig, const struct sigaction *act,
struct sigaction *oact );
• Nastaví obsluhu signálu sig podle act a vrátí předchozí nastavení
v oact.
• Obsah struktury sigaction:
– void(*sa handler )(int) . . . SIG DFL, SIG IGN, nebo adresa
handleru
– sigset t sa mask . . . signály blokované v handleru, navíc je
blokován signál sig
– int sa flags . . . SA RESETHAND (při vstupu do handleru
nastavit SIG DFL), SA RESTART (restartovat přerušená systémová
volání), SA NODEFER (neblokovat signál sig během obsluhy)
113

Příklad: časově omezený vstup
#define BUFSZ 4096
void handler(int sig)
{ fprintf(stderr," !!! TIMEOUT !!! \n"); }
int main()
{
char buf[BUFSZ]; struct sigaction act; int sz;
act.sa_handler = handler;
sigemptyset(&act.sa_mask); act.sa_flags = 0;
sigaction(SIGALRM, &act, NULL); alarm(5);
sz = read(0, buf, BUFSZ);
if(sz > 0)
write(1, buf, sz);
exit(0);
}
114

Blokování signálů
• Blokované signály budou procesu doručeny a zpracovány až po
odblokování.
int sigprocmask(int how, const sigset t *set,
sigset t *oset );
• Nastaví masku blokovaných signálů a vrátí starou masku.
• Pro manipulaci s maskou signálů slouží funkce: sigaddset(),
sigdelset(), sigemptyset(), sigfillset(), sigismember()
int sigpending(sigset t *set );
• Vrátí čekající zablokované signály.

115

Příklad: blokování signálů
sigset_t sigs, osigs; structure sigaction sa;
sigfillset(&sigs); sigprocmask(SIG_BLOCK, &sigs, &osigs);
switch(cpid = fork()) {
case -1: /* Chyba */
sigprocmask(SIG_SETMASK, &osigs, NULL);
...
case 0: /* Synovský proces */
sa.sa_handler = h_cld; sigemptyset(&sa.sa_mask);
sa.sa_flags = 0;
sigaction(SIGINT, &sa, NULL);
sigprocmask(SIG_SETMASK, &osigs, NULL);
...
default: /* Rodičovský proces */
sigprocmask(SIG_SETMASK, &osigs, NULL);
...
}
116

Čekání na signál
int pause(void);
• Pozastaví volající proces do příchodu signálu. Volání se vrátí po
návratu z handleru.
int sigsuspend(const sigset t *sigmask );
• Jako pause(), ale navíc po dobu čekání masku blokovaných signálů
změní na sigmask.
int sigwait(const sigset t *set, int *sig );
• Čeká na příchod signálu z množiny set (tyto signály musí být
předtím zablokované), číslo signálu vrátí v sig.
• Nevolá se handler signálu (to ale není v normě jednoznačně
definováno).
117

Problém: konflikt při sdílení dat
• Máme strukturu struct { int a, b; } shared ;
• Se strukturou bude pracovat cyklus
for(;;) {
a=shared.a; b=shared.b;
if(a!=b) printf("NEKONZISTENTNÍ STAV");
shared.a=val; shared.b=val; /* neatomická operace */
}
• Jestliže tento cyklus spustíme ve dvou různých procesech (nebo
vláknech), které obě sdílejí stejnou strukturu shared a mají různé
hodnoty val, bude docházet ke konfliktům.
• Příčina: změna datové struktury ve zvýrazněném řádku není
atomická.
118

Scénář konfliktu
Procesy A(val==1) a B(val==2)

a

b

1.

Počáteční stav struktury

?

?

2.

Proces A zapíše do položky a

1

?

3.

Proces B zapíše do položky a

2

?

4.

Proces B zapíše do položky b

2

2

5.

Proces A zapíše do položky b

2

1

6.

Struktura je v nekonzistentním
stavu a jeden z procesů to zjistí.

119

Řešení: vzájemné vyloučení procesů
• Je potřeba zajistit atomicitu operací nad strukturou, tzn. jeden
proces provádí modifikaci a dokud neuvede strukturu do
konzistentního stavu, druhý proces s ní nemůže manipulovat.
Procesy A(val==1) a B(val==2)

a

b

Počáteční stav struktury

?

?

Proces A zapíše do položky a

1

?

Proces B musí čekat

1

?

Proces A zapíše do položky b

1

1

Proces B zapíše do položky a

2

1

6.

Proces B zapíše do položky b

2

2

7.

Struktura je v konzistentním stavu.

1.



2.


3.


 4.

 5.


120

Problém: konflikt zapisovatelů a čtenářů
• Několik běžících procesů zapisuje protokol o své činnosti do
společného log-souboru. Nový záznam je připojen vždy na konec
souboru.
• Pokud zápis záznamu není proveden atomickou operací, může dojít
k promíchání více současně zapisovaných záznamů.
• Zapisovat smí vždy pouze jeden proces.
• Další procesy čtou data z log-souboru.
• Při přečtení právě zapisovaného záznamu obdržíme nesprávná
(neúplná) data.
• Během operace zápisu ze souboru nelze číst. Když nikdo nezapisuje,
může více procesů číst současně.
121

Řešení: zamykání souborů
• Zapisující proces zamkne soubor pro zápis. Ostatní procesy
(zapisovatelé i čtenáři) se souborem nemohou pracovat a musí čekat
na odemčení zámku.
• Čtoucí proces zamkne soubor pro čtení. Zapisovatelé musí čekat na
odemčení zámku, ale ostatní čtenáři mohou také zamknout soubor
pro čtení a číst data.
• V jednom okamžiku může být na souboru aktivní nejvýše jeden
zámek pro zápis nebo libovolně mnoho zámků pro čtení, ale ne oba
typy zámků současně.
• Z důvodu efektivity by každý proces měl držet zámek co nejkratší
dobu a pokud možno nezamykat celý soubor, ale jen úsek, se kterým
pracuje. Preferované je pasivní čekání, aktivní čekání je vhodné jen
na velmi krátkou dobu.
122

Synchronizační mechanismy
• Teoretické řešení – algoritmy vzájemného vyloučení (Dekker 1965,
Peterson 1981)
• Zákaz přerušení (na jednoprocesorovém stroji), speciální instrukce
(test-and-set)
• Lock-soubory
• Nástroje poskytované operačním systémem
– semafory (součást System V IPC)
– zámky pro soubory (fcntl(), flock())
– synchronizace vláken: mutexy (ohraničují kritické sekce, pouze
jedno vlákno může držet mutex), podmínkové proměnné
(zablokují vlákno, dokud jiné vlákno nesignalizuje splnění
podmínky), read-write zámky (sdílené a exkluzivní zámky,
podobně jako pro soubory)
123

Lock-soubory
• Pro každý sdílený zdroj existuje dohodnuté jméno souboru. Zamčení
zdroje se provede vytvořením souboru, odemčení smazáním souboru.
Každý proces musí otestovat, zda soubor existuje, a pokud ano, tak
počkat.
void lock(char *lockfile) {
while( (fd = open(lockfile,
O_RDWR|O_CREAT|O_EXCL, 0600)) == -1)
; /* Čekáme ve smyčce na odemčení */
close(fd);
}
void unlock(char *lockfile) {
unlink(lockfile);
}
124

Lock-soubory na NFS
• Pokud je lock-soubor uložen na vzdáleném svazku připojeném
pomocí NFS, nemusí se kombinace O CREAT|O EXCL chovat
korektně. Řešení:
void lock(char *lockfile)
{
sprintf(fname, "%s%d", lockfile, getpid());
fd = open(fname, O_RDWR|O_CREAT, 0600); close(fd);
for(;;) {
link(fname, lockfile);
stat(fname, &buf);
if(buf.st_nlink == 2) break;
}
unlink(fname);
}

125

Zamykání souborů: fcntl()
int fcntl(int fildes, int cmd, ...);
• K nastavení zámků pro soubor fildes se používá cmd:
– F GETLK . . . vezme popis zámku z třetího argumentu a nahradí
ho popisem existujícího zámku, který s ním koliduje
– F SETLK . . . nastaví nebo zruší zámek popsaný třetím
argumentem, pokud nelze zámek nastavit, ihned vrací −1
– F SETLKW . . . jako F SETLK, ale uspí proces, dokud není možné
nastavit zámek
• Třetí argument obsahuje popis zámku a je typu struct flock *

126

Zamykání souborů: struct flock
• l type . . . typ zámku
– F RDLCK . . . sdílený zámek (pro čtení), více procesů
– F WRLCK . . . exkluzivní zámek (pro zápis), jeden proces
– F UNLCK . . . odemčení
• l whence . . . jako u lseek(), tj. SEEK SET, SEEK CUR, SEEK END
• l start . . . začátek zamykaného úseku
• l len . . . délka úseku, 0 znamená do konce souboru
• l pid . . . PID procesu držícího zámek, používá se jen pro F GETLK

127

Deadlock
• Máme dva sdílené zdroje res1 a res2 chráněné zámky lck1 a lck2.
Procesy p1 a p2 chtějí každý výlučný přístup k oběma zdrojům.
p1
lock(lck1); /* OK */

p2
lock(lck2); /* OK */

lock(lck2); /* Čeká na p2 */
use(res1, res2);
unlock(lck2);
unlock(lck1);

lock(lck1); /* Čeká na p1 */
Deadlock
use(res1, res2);
unlock(lck2);
unlock(lck1);

• Pozor na pořadí zamykání!

128

System V IPC
• IPC je zkratka pro Inter-Process Communication
• Komunikace mezi procesy v rámci jednoho systému, tj. nezahrnuje
síťovou komunikaci
• Semafory . . . použití pro synchronizaci procesů
• Sdílená paměť . . . předávání dat mezi procesy, přináší podobné
problémy jako sdílení souborů, k řešení lze použít semafory
• Fronty zpráv . . . spojují komunikaci (zpráva nese data) se
synchronizací (čekání procesu na příchod zprávy)
• Prostředky IPC mají podobně jako soubory definovaná přístupová
práva (pro čtení a zápis) pro vlastníka, skupinu a ostatní.
129

Semafory
• Zavedl je E. Dijkstra
• Semafor s je datová struktura obsahující
– celé nezáporné číslo i (volná kapacita)
– frontu procesů q, které čekají na uvolnění
• Operace nad semaforem:
init(s, n)
vyprázdnit s.q; s.i = n
P(s) (z holandského „Proberenÿ – otestovat)
if(s.i > 0) s.i-- else
uspat volající proces a zařadit do s.q
V(s) (z holandského „Verhogenÿ – inkrementovat)
if(s.f prázdná) s.i++ else
odstranit jeden proces z s.q a probudit ho
130

Vzájemné vyloučení pomocí semaforů
• Jeden proces inicializuje semafor
sem s;
init(s, 1);
• Kritická sekce se doplní o operace nad semaforem
...
P(s);
kritická sekce;
V(s);
...

131

API pro semafory
int semget(key t key, int nsems, int semflg );
• Vrátí identifikátor pole obsahujícího nsems semaforů asociovaný
s klíčem key (klíč IPC PRIVATE . . . privátní semafory, při každém
použití vrátí jiný identifikátor). semflg je OR-kombinace
přístupových práv a konstant IPC CREAT (vytvořit, pokud
neexistuje), IPC EXCL (chyba, pokud existuje).
int semctl(int semid, int semnum, int cmd, ...);
• Řídicí funkce, volitelný čtvrtý parametr arg je typu union semun.
int semop(int semid, struct sembuf *sops, size t nsops );
• Zobecněné operace P a V.
132

API pro semafory: semctl()
• semnum . . . číslo semaforu v poli
• Možné hodnoty cmd:
– GETVAL . . . vrátí hodnotu semaforu
– SETVAL . . . nastaví semafor na hodnotu arg.val
– GETPID . . . PID procesu, který provedl poslední operaci
– GETNCNT . . . počet procesů čekajících na větší hodnotu
– GETZCNT . . . počet procesů čekajících na nulu
– GETALL . . . uloží hodnoty všech semaforů do pole arg.array
– SETALL . . . nastaví všechny semafory podle arg.array
– IPC STAT . . . do arg.buf dá počet semaforů, přístupová práva
a časy posledních semctl() a semop()
– IPC SET . . . nastaví přístupová práva
– IPC RMID . . . zruší pole semaforů
133

API pro semafory: semop()
• Operace se provádí atomicky (tj. buď se povede pro všechny
semafory, nebo pro žádný) na nsops semaforech podle pole sops
struktur struct sembuf:
– sem num . . . číslo semaforu
– sem op . . . operace
∗ P(sem num, abs(sem op)) pro sem op < 0
∗ V(sem num, sem op) pro sem op > 0
∗ čekání na nulovou hodnotu semaforu pro sem op == 0
– sem flg . . . OR-kombinace
∗ IPC NOWAIT . . . když nelze operaci hned provést, nečeká a
vrátí chybu
∗ SEM UNDO . . . při ukončení procesu vrátit operace se
semaforem
134

Sdílená paměť (1)
int shmget(key t key, size t size, int shmflg );
• Vrátí identifikátor segmentu sdílené paměti o velikosti size bajtů
spojeného s klíčem key (IPC PRIVATE . . . při každém použití nový
segment). V shmflg je kombinace přístupových práv a konstant
IPC CREAT, IPC EXCL se stejným významem jako u semaforů.
void *shmat(int shmid, const void *shmaddr, int shmflg );
• Připojí segment do adresového prostoru procesu na adresu shmaddr
(NULL . . . adresu přidělí systém), vrátí adresu.
• shmflg může obsahovat
– SHM RDONLY . . . připojit jen pro čtení
– SHM RND . . . zaokrouhlit adresu připojení
135

Sdílená paměť (2)
int shmdt(const void *shmaddr );
• Odpojí segment sdílené paměti z adresového prostoru procesu.
int shmctl(int shmid, int cmd, struct shmid ds *buf );
• Operace se segmentem paměti podle cmd:
– IPC STAT . . . v buf vrátí velikost segmentu, počet připojení,
přístupová práva, PID procesu, který segment vytvořil a procesu,
který ho naposled připojil/odpojil, časy posledního shmat(),
shmdt() a shmctl()
– IPC SET . . . nastavení přístupových práv
– IPC RMID . . . zrušení segmentu
136

Semafory a sdílená paměť: producent
key_t key = 1234; struct sembuf sops;
shm_id = shmget(key, sizeof(struct shmem), IPC_CREAT|0600);
pshmem = (struct shmem *) shmat(shm_id, NULL, 0);
sem_id = semget(key, 2, IPC_CREAT|0600);
sem_arg=0; semctl(sem_id, 0, SETVAL, sem_arg);
sem_arg=1; semctl(sem_id, 1, SETVAL, sem_arg);
for(;;) {
 sops.sem_num=1; sops.sem_op=-1; sops.sem_flg=0;









semop(sem_id,&sops,1);


sz = pshmem->sz = read(0, pshmem->buf, BUFSZ);






sops.sem_num
=
0;
sops.sem_op
=
1;
sops.sem_flg
=
0;




semop(sem_id, &sops, 1);
if(sz <= 0) break;
}
137

Semafory a sdílená paměť: konzument
key_t key = 1234; struct sembuf sops;
sem_id = semget(key, 2, 0); shm_id = shmget(key, 0, 0);
pshmem = (struct shmem *) shmat(shm_id, NULL, 0);
for(;;) {


sops.sem_num
=
0;
sops.sem_op
=
-1;
sops.sem_flg
=
0;








semop(sem_id,
&sops,
1);






 if(pshmem->sz == 0) break;



write(1, pshmem->buf, pshmem->sz);








sops.sem_num
=
1;
sops.sem_op
=
1;
sops.sem_flg
=
0;






semop(sem_id, &sops, 1);
}
shmdt(pshmem); shmctl(shm_id, IPC_RMID, NULL);
semctl(sem_id, 0, IPC_RMID);
138

Fronty zpráv (1)
int msgget(key t key, int msgflg );
• Vrátí identifikátor fronty zpráv spojené s klíčem key (IPC PRIVATE
. . . při každém použití nová fronta zpráv). V msgflg je kombinace
přístupových práv a konstant IPC CREAT, IPC EXCL se stejným
významem jako u semaforů.
int msgctl(int msqid, int cmd, struct msqid ds *buf );
• Operace s frontou podle cmd:
– IPC STAT . . . v buf vrátí aktuální počet zpráv, max. velikost
fronty, přístupová práva, PID a časy posledního msgsnd() a
msgrcv()
– IPC SET . . . nastavení přístupových práv a max. velikosti fronty
– IPC RMID . . . zrušení segmentu
139

Fronty zpráv (2)
int msgsnd(int msqid, const void *msgp, size t msgsz,
int msgflg );
• Pošle zprávu msgp o velikosti msgsz do fronty msqid.
• Zpráva má libovolný obsah, ale na začátku musí být typ zprávy, tj.
položka typu long int s kladnou hodnotou.
• Typ zprávy se nezapočítává do velikosti zadané v parametru msgsz.
• Maximální velikost zprávy je limitována systémem.
• Pokud je fronta plná, funkce čeká, až bude ve frontě místo na
zprávu. Příznak IPC NOWAIT způsobí, že se nečeká, ale volání se
vrátí s chybou.

140

Fronty zpráv (3)
ssize t msgrcv(int msqid, void *msgp, size t msgsz,
long int msgtyp, int msgflg );
• Z fronty msqid je přečtena zpráva do bufferu msgp. Vrací velikost
zprávy. Pro příliš dlouhé zprávy se do msgp uloží jen prvních msgsz
bajtů, pokud je v msgflg příznak MSG NOERROR. Jinak vrátí chybu.
• Typ zprávy se nezapočítává do velikosti zprávy.
• Z fronty se vybere první zpráva zadaného typu:
– msgtyp == 0 . . . libovolný typ
– msgtyp > 0 . . . typ msgtyp
– msgtyp < 0 . . . typ <= abs(msgtyp)
• Jestliže zpráva požadovaného typu není k dispozici, proces čeká. Při
nastavení IPC NOWAIT v msgflg místo čekání vrátí chybu.
141

Fronty zpráv: producent
int sz,id;
key_t key=1234;
struct {
long int mtype;
char buf[BUFSZ];
} msg;
id = msgget(key, IPC_CREAT|0600);
msg.mtype=1;
while( (sz = read(0, msg.buf, BUFSZ)) > 0)
msgsnd(id, &msg, sz, 0);
msg.mtype=2;
msgsnd(id, &msg, 0, 0);

142

Fronty zpráv: konzument
int sz;
key_t key=1234;
struct {
long int mtype;
char buf[BUFSZ];
} msg;
id = msgget(key, 0);
for(;;) {
sz = msgrcv(id, &msg, BUFSZ, 0, 0);
if(msg.mtype == 1)
write(1,msg.buf,sz);
else { /* msg.mtype == 2 */
msgctl(id, IPC_RMID, NULL);
break;
}
}
143

Vytváření prostředků IPC
• Jeden proces prostředek vytvoří, ostatní se k němu připojí.
• Po skončení používání je třeba prostředek IPC zrušit.
• Funkce semget(), shmget() a msgget() mají jako první parametr
klíč identifikující prostředek IPC. Skupina procesů, která chce
komunikovat, se musí domluvit na společném klíči. Různé skupiny
komunikujících procesů by měly mít různé klíče.
key t ftok(const char *path, int id );
• Vrátí klíč odvozený ze zadaného jména souboru path a čísla id. Pro
stejné id a libovolnou cestu odkazující na stejný soubor vrátí stejný
klíč. Pro různá id nebo různé soubory na stejném svazku vrátí různé
klíče.
144

Další prostředky IPC
• POSIX a UNIX98 definují ještě další prostředky komunikace mezi
procesy:
– signály . . . pro uživatelské účely lze využít signály SIGUSR1 a
SIGUSR2
– POSIXová sdílená paměť přístupná pomocí shm open() a
mmap()
– POSIXové semafory . . . sem open(), sem post(),
sem wait(), . . .
– POSIXové fronty zpráv . . . mq open(), mq send(),
mq receive(), . . .
• Z BSD pochází sokety (sockets) umožňující komunikaci
v doménách AF UNIX (komunikace v rámci jednoho počítače) a
AF INET (komunikace na jednom počítači nebo po síti).
145

Síťová komunikace
UUCP (UNIX-to-UNIX Copy Program) – první aplikace pro
komunikaci UNIXových systémů propojených přímo nebo přes
modemy, součást Version 7 UNIX (1978)
Sokety (sockets) – zavedeny ve 4.1aBSD (1982); soket je jeden konec
obousměrného komunikačního kanálu vytvořeného mezi dvěma
procesy buď lokálně na jednom počítači, nebo s využitím síťového
spojení
TLI (Transport Layer Interface) – SVR3 (1987); knihovna zajišťující
síťovou komunikaci na úrovni 4. vrstvy referenčního modelu ISO OSI
RPC (Remote Procedure Call) – SunOS (1984); protokol pro přístup
ke službám na vzdáleném stroji, data přenášena ve tvaru XDR
(External Data Representation)
146

TCP/IP
• protokoly
– IP (Internet Protocol) – přístupný jen pro uživatele root
– TCP (Transmission Control Protocol) – streamový,
spojovaný, spolehlivý
– UDP (User Datagram Protocol) – datagramový, nespojovaný,
nespolehlivý
• IP adresa – 4 bajty, definuje síťové rozhraní, nikoliv počítač
• port – 2 bajty, rozlišení v rámci 1 IP adresy, porty s číslem < 1024
jsou rezervované (jejich použití vyžaduje práva uživatele root)
• DNS (Domain Name System) – převod mezi symbolickými jmény
a numerickými IP adresami
147

Spojované služby (TCP), sekvenční obsluha
server

síť

fd = socket()

klient

fd = socket()

bind(fd)
listen(fd)
fd2 = accept(fd)

connect(fd)

read(fd2); write(fd2)

write(fd);read(fd)

close(fd2)

close(fd)
148

Spojované služby (TCP), paralelní obsluha
server

síť

klient

fd = socket()
bind(fd)
listen(fd)
fd2 = accept(fd)
fork()

fd = socket()
connect(fd)

close(fd2)
syn
while(waitpid(
read(fd2)
-1, stat,
write(fd2)
WNOHANG)>0) ;
exit(0)
149

write(fd);read(fd)
close(fd)

Spojované služby, paralelní accept()
server

síť

klient

fd = socket()
bind(fd)
listen(fd)
fork()

...

fd = socket()

fd2=accept(fd)
read(fd2)
write(fd2)
close(fd2)
150

connect(fd)
write(fd);read(fd)
close(fd)

Datagramové služby (UDP)
server

síť

klient

fd = socket()

fd = socket()

bind(fd)
recvfrom(fd)
sendto(fd)

sendto(fd)
recvfrom(fd)
close(fd)
151

Vytvoření soketu: socket()
int socket(int domain, int type, int protocol );
• Vytvoří soket a vrátí jeho deskriptor.
• domain:
– AF UNIX . . . lokální komunikace, adresa je jméno souboru
– AF INET . . . síťová komunikace, adresa je dvojice (IP adresa,
port)
• type:
– SOCK STREAM . . . spojovaná spolehlivá služba, poskytuje
obousměrný sekvenční proud dat
– SOCK DGRAM . . . nespojovaná nespolehlivá služba, přenos
datagramů
• protocol: 0 (default pro daný type) nebo platné číslo protokolu
(např. 6 = TCP, 17 = UDP)
152

Pojmenování soketu: bind()
int bind(int socket, const struct sockaddr *address,
socklen t address len );
• Přiřadí soketu zadanému deskriptorem socket adresu address o
velikosti address len bajtů.
• struct sockaddr:
– sa family t sa family . . . doména
– char sa data [] . . . adresa
• Pro AF INET se používá struct sockaddr in:
– sa family t sin family . . . doména (AF INET)
– in port t sin port . . . číslo portu (16 bitů)
– struct in addr sin addr . . . IP adresa (32 bitů)
– unsigned char sin zero [8] . . . výplň
153

Čekání na spojení: listen()
int listen(int socket, int backlog );
• Označí soket zadaný desktriptorem socket jako akceptující spojení.
• Maximálně backlog žádostí o spojení může najednou čekat ve
frontě na obsloužení (implementace může hodnotu backlog změnit,
pokud není v podporovaném rozsahu). Žádosti, které se nevejdou do
fronty, jsou odmítnuty (tj. volání connect() skončí s chybou).
• Soket čeká na spojení na adrese, která mu byla dříve přiřazena
voláním bind(). Pro doménu AF INET stačí zadat číslo portu a IP
adresu INADDR ANY, která znamená libovolnou adresu.

154

Akceptování spojení: accept()
int accept(int socket, struct sockaddr *address,
socklen t *address len );
• Vytvoří spojení mezi lokálním soketem socket (který dříve zavolal
listen()) a vzdáleným soketem, který žádal o spojení pomocí
connect(). Vrátí deskriptor (nový soket), který lze používat pro
komunikaci se vzdáleným procesem. Původní deskriptor socket
umožňuje přijímat další spojení pomocí accept().
• V address vrátí adresu vzdáleného soketu.
• address len je velikost struktury pro uložení adresy, po návratu
obsahuje skutečnou délku adresy.
• Podobně jako bind() i accept() používá pro adresy v doméně
AF INET strukturu sockaddr in.
155

Navázání spojení: connect()
int connect(int sock, struct sockaddr *address,
socklen t address len);
• Naváže spojení lokálního soketu sock se vzdáleným procesem, který
pomocí listen() a accept() čeká na spojení na adrese address
(o délce address len).
• Jestliže pro soket sock nebyla definována adresa voláním bind(), je
mu přiřazena nějaká nepoužitá adresa.
• Pokud se spojení nepovede, je soket v nedefinovaném stavu. Před
novým pokusem o spojení by aplikace měla zavřít deskriptor sock a
vytvořit nový soket.

156

Poslání zprávy: sendto()
ssize t sendto(int socket, void *msg, size t len,
int flags, struct sockaddr *addr,
socklen t addr len );
• Prostřednictvím soketu socket pošle zprávu msg o délce len na
adresu addr (o délce addr len).
• Parametr flags může obsahovat příznaky:
– MSG EOB . . . ukončení záznamu (pokud je podporováno
protokolem)
– MSG OOB . . . poslání urgentních (out-of-band) dat, jejichž
význam je závislý na protokolu

157

Přijetí zprávy: recvfrom()
ssize t recvfrom(int sock, void *buf, size t len,
int flg, struct sockaddr *address,
socklen t *address len );
• Přijme zprávu ze soketu sock, uloží ji do bufferu buf o velikosti len,
do address dá adresu odesílatele zprávy, do address len délku
adresy. Vrátí délku zprávy. Když je zpráva delší než len, nadbytečná
data se zahodí (SOCK STREAM nedělí data na zprávy, data se
nezahazují).
• Ve flg mohou být příznaky:
– MSG PEEK . . . zpráva se bere jako nepřečtená, další recvfrom()
ji vrátí znovu
– MSG OOB . . . přečte urgentní (out-of-band) data
– MSG WAITALL . . . čeká, dokud není načten plný objem dat, tj.
len bajtů
158

Uzavření soketu: close()
int close(int fildes);
• Zruší deskriptor, při zrušení posledního deskriptoru soketu zavře
soket.
• Pro SOCK STREAM soket záleží na nastavení příznaku SO LINGER
(default je l onoff == 0, mění se funkcí setsockopt()).
– l onoff == 0 . . . volání close() se vrátí, ale jádro se snaží dál
přenést zbylá data
– l onoff == 1 && l linger != 0 . . . jádro se snaží přenést
zbylá data do vypršení timeoutu l linger, když se to nepovede,
close() vrátí chybu, jinak vrátí OK po přenesení dat.
– l onoff == 1 && l linger == 0 . . . provede se reset spojení

159

Uzavření soketu: shutdown()
int shutdown(int socket, int how );
• Uzavře soket (ale neruší deskriptor) podle hodnoty how:
– SHUT RD . . . pro čtení
– SHUT WR . . . pro zápis
– SHUT RDWR . . . pro čtení i zápis

160

Další funkce pro sokety
int getsockopt(int socket, int level, int opt name,
void *opt value, socklen t *option len );
• Přečtení parametrů soketu
int setsockopt(int socket, int level, int opt name,
const void *opt value, socklen t option len );
• Nastavení parametrů soketu
int getsockname(int socket, struct sockaddr *address,
socklen t *address len );
• Zjištění (lokální) adresy soketu
int getpeername(int socket, struct sockaddr *address,
socklen t *address len );
• Zjištění adresy vzdáleného soketu (druhého konce spojení)
161

Pořadí bajtů
• Síťové služby používají pořadí bajtů, které se může lišit od pořadí
používaného na lokálním systému. Pro převod lze použít funkce
(makra):
– uint32 t htonl(uint32 t hostlong );
host → síť, 32 bitů
– uint16 t htons(uint16 t hostshort );
host → síť, 16 bitů
– uint32 t ntohl(uint32 t netlong );
síť → host, 32 bitů
– uint16 t ntohs(uint16 t netshort );
síť → host, 16 bitů
• Síťové pořadí bajtů je big-endian, tj. nejprve vyšší bajt. Používá se
hlavně ve funkcích pracujících s adresami a čísly portů.
162

Čísla protokolů a portů
struct protoent *getprotobyname(const char *name );
• V položce p proto vrátí číslo protokolu se jménem name (např. pro
"tcp" vrátí 6).
• Čísla protokolů jsou uložena v souboru /etc/protocols.
struct servent *getservbyname(const char *name,
const char *proto );
• Pro zadané jméno služby name a jméno protokolu proto vrátí
v položce s port číslo portu.
• Čísla portů jsou uložena v souboru /etc/services.
Funkce vrací NULL, když v databázi není odpovídající položka.
163

Jména a IP adresy
struct hostent *gethostbyname(const char *name );
• Pro dané jméno vrátí v poli char **h addr list seznam
příslušných síťových adres. Za poslední adresou je ukazatel NULL.
Délka jedné adresy je v položce h length.
struct hostent *gethostbyaddr(const void *addr, size t len,
int type );
• Pro danou adresu addr o délce len v doméně type vrátí jméno
v položce h name a případné aliasy v nulou ukončeném poli
h aliases.
− Při vyhodnocování dotazů na adresy a jména se používá DNS a
lokální databáze uložená v souboru /etc/hosts.
− Vrací NULL, když v databázi není hledaný záznam.
164

Příklad: TCP server
int nclients = 10, fd, newsock, sz;
struct servent *sp; struct protoent *pp;
struct sockaddr_in sa,ca;
sp = getservbyname(argv[1], "tcp");
pp = getprotobyname("tcp");
fd = socket(AF_INET, SOCK_STREAM, pp->p_proto);
sa.sin_family = AF_INET; sa.sin_port=sp->port;
sa.sin_addr.s_addr = INADDR_ANY;
bind(sockfd,(struct sockaddr *)&sa,sizeof(sa));
listen(sockfd, nclients);
for(;;) {
sz = sizeof(ca); newsock = accept(fd, &ca, &sz);
/* Komunikace s klientem */
close(newsock);
}
165

Příklad: TCP klient
char *host; struct servent *se;
struct hostent *ha; struct protoent *pp;
int sockfd; struct sockaddr_in sa;
host = argv[1];
se = getservbyname(argv[2], "tcp");
ha = gethostbyname(host);
pp = getprotobyname("tcp");
sockfd = socket(AF_INET, SOCK_STREAM, pp->p_proto);
sa.sin_family = AF_INET; sa.sin_port = se->s_port;
memcpy(&sa.sin_addr.s_addr, ha->h_addr_list[0],
ha->h_length);
connect(sockfd, &sa, sizeof(sa));
/* Komunikace se serverem */
close(sockfd);
166

Čekání na data: select()
int select(int nfds, fd set *readfds,
fd set *writefds, fd set *errorfds,
struct timeval *timeout );
• Zjistí, které ze zadaných deskriptorů jsou připraveny pro čtení, zápis,
nebo na kterých došlo k výjimečnému stavu. Pokud žádný takový
deskriptor není, čeká do vypršení času timeout (NULL . . . čeká
libovolně dlouho). Parametr nfds udává rozsah testovaných
deskriptorů (0, ..., nfds-1).
• Pro nastavení a test masek deskriptorů slouží funkce:
– void FD ZERO(fd set *fdset ) . . . inicializace
– void FD SET(int fd, fd set *fdset ) . . . nastavení
– void FD CLR(int fd, fd set *fdset ) . . . zrušení
– int FD ISSET(int fd, fd set *fdset ) . . . test
167

Čekání na data: poll()
int poll(struct pollfd fds [], nfds t nfds, int timeout );
• Čeká na událost na některém z deskriptorů v poli fds o nfds
prvcích po dobu timeout ms (0 . . . vrátí se hned, -1 . . . čeká
libovolně dlouho).
• Prvky fds:
– fd . . . číslo deskriptoru
– events . . . očekávané události, OR-kombinace POLLIN (lze
číst), POLLOUT (lze psát), atd.
– revents . . . události, které nastaly, příznaky jako v events,
navíc např. POLLERR (nastala chyba)

168

Příklad: použití select()
/* Deskriptor fd odkazuje na soket, přepisuje síťovou
komunikaci na terminál a naopak */
int sz; fd_set rfdset, efdset; char buf[BUFSZ];
for(;;) {
FD_ZERO(&rfdset); FD_SET(0, &rfdset);
FD_SET(fd, &rfdset); efdset = rfdset;
select(fd+1, &rfdset, NULL, &efdset, NULL);
if(FD_ISSET(0, &efdset)) /* Výjimka na stdin */;
if(FD_ISSET(fd, &efdset)) /* Výjimka na fd */;
if(FD_ISSET(0, &rfdset)) {
sz = read(0, buf, BUFSZ); write(fd, buf, sz);
}
if(FD_ISSET(fd, &rfdset)) {
sz = read(fd, buf, BUFSZ); write(1,buf,sz);
}
}
169

Implementace vláken
library-thread model
• Vlákna jsou implementována v knihovnách, jádro je nevidí.
• Run-time knihovna plánuje vlákna na procesy a jádro plánuje
procesy na procesory.
⊕ Menší režie přepínání kontextu
ª Nemůže běžet více vláken stejného procesu najednou.
kernel-thread model
• Vlákna jsou implementována přímo jádrem.
⊕ Více vláken jednoho procesu může běžet najednou na různých
procesorech.
ª Plánování threadů používá systémová volání místo knihovních
funkcí, tím více zatěžuje systém.
hybridní modely
• Vlákna se multiplexují na několik jádrem plánovaných entit.
170

Soukromé atributy vláken
• čítač instrukcí
• zásobník (automatické proměnné)
• thread ID, dostupné funkcí
pthread t pthread self(void);
• plánovací priorita a politika
• hodnota errno
• klíčované hodnoty – dvojice (pthread key t key, void *ptr )
– Klíč vytvořený voláním pthread key create() je viditelný ve
všech vláknech procesu.
– V každém vláknu může být s klíčem asociována jiná hodnota
voláním pthread setspecific().
171

Vytvoření vlákna
int pthread create(pthread t *thread,
const pthread attr t *attr,
void *(*start fun )(void*), void *arg );
• Vytvoří nové vlákno, do thread uloží jeho ID.
• Nastaví atributy (velikost zásobníku, plánovací politika) podle attr
(použije implicitní atributy při attr == NULL).
• Ve vytvořeném vláknu spustí funkci start fun() s argumentem
arg. Po návratu z této funkce se zruší vlákno.
• S objekty pthread attr t lze manipulovat funkcemi
pthread attr init(), pthread attr destroy(),
pthread attr getstackaddr(), pthread attr setstackaddr(),
...
172

Inicializace
int pthread once(pthread once t *once control,
void (*init routine )(void));
• V parametru once control se předává ukazatel na staticky
inicializovanou proměnnou
pthread once t once control = PTHREAD ONCE INIT;
• První vlákno, které zavolá pthread once(), provede inicializační
funkci init routine(). Ostatní vlákna už tuto funkci neprovádějí,
navíc, pokud inicializační funkce ještě neskončila, zablokují se a
čekají na její dokončení.
• Lze použít např. na dynamickou inicializaci globálních dat
v knihovnách, jejichž kód může zavolat více vláken současně, ale je
třeba zajistit, že inicializace proběhne jen jednou.
173

Ukončení vlákna
void pthread exit(void *value ptr );
• Ukončí volající vlákno.
• Obdoba exit() pro proces
int pthread join(pthread t thread, void **value ptr );
• Počká na ukončení vlákna thread a ve value ptr vrátí hodnotu
ukazatele value ptr z volání pthread exit() nebo návratovou
hodnotu hlavní funkce vlákna.
• Obdoba čekání na synovský proces pomocí wait()
int pthread detach(pthread t thread );
• Nastaví okamžité uvolnění paměti po ukončení vlákna, na vlákno
nelze použít pthread join().
174

Zrušení vlákna
int pthread cancel(pthread t thread );
• Požádá o zrušení vlákna thread. Závisí na nastavení
int pthread setcancelstate(int state, int *old );
• Nastaví nový stav a vrátí starý:
– PTHREAD CANCEL ENABLE . . . povoleno zrušit
– PTHREAD CANCEL DISABLE . . . nelze zrušit, žádost bude čekat
na povolení
int pthread setcanceltype(int type, int *old );
• PTHREAD CANCEL ASYNCHRONOUS . . . okamžité zrušení
• PTHREAD CANCEL DEFERRED . . . žádost čeká na vstup do určitých
funkcí (např. open(), read(), wait()), nebo na volání
void pthread testcancel(void);
175

Příklad: vlákna
pthread_t id_a, id_b;
void *res_a, *res_b;
pthread_create(&id_a, NULL, do_a, "a");
pthread_create(&id_b, NULL, do_b, "b");
void *do_a(void *arg)
{
...
return arg;
}

void *do_b(void *arg)
{
...
return arg;
}

pthread_join(id_a, &res_a);
pthread_join(id_b, &res_b);
176

Soukromé klíčované hodnoty ve vláknech
int pthread key create(pthread key t *key,
void (*destructor )(void *));
• Vytvoří klíč, který lze asociovat s hodnotou typu (void *). Funkce
destructor() se volají opakovaně pro všechny klíče, jejichž
hodnota není NULL, při ukončení vlákna.
int pthread key delete(pthread key t key );
• Zruší klíč, nemění asociovaná data.
int pthread setspecific(pthread key t key,
const void *value );
• Přiřadí ukazatel value ke klíči key.
void *pthread getspecific(pthread key t key );
• Vrátí hodnotu ukazatele příslušného ke klíči key.
177

Úklid při ukončení/zrušení vlákna
• Vlákno má zásobník úklidových handlerů, které se volají při ukončení
nebo zrušení vlákna funkcemi pthread exit() a
pthread cancel(). Jako první se spouští naposledy vložený
handler.
• Po provedení handlerů se volají destruktory privátních klíčovaných
dat vlákna.
void pthread cleanup push(void (*routine )(void *),
void *arg );
• Vloží handler do zásobníku.
void pthread cleanup pop(int execute );
• Vyjme naposledy vložený handler ze zásobníku. Provede ho, pokud
je execute nenulové.
178

Signály a vlákna
• Signály mohou být generovány pro proces (voláním kill()), nebo
pro vlákno (chybové události, volání pthread kill()).
• Nastavení obsluhy signálů je stejné pro všechna vlákna procesu, ale
masku blokovaných signálů má každé vlákno vlastní, nastavuje se
funkcí
int pthread sigmask(int how, const sigset t *set,
sigset t *oset );
• Signál určený pro proces ošetří vždy právě jedno vlákno, které nemá
tento signál zablokovaný.
• Lze vyhradit jedno vlákno pro synchronní příjem signálů pomocí
volání sigwait(). V ostatních vláknech budou signály blokovány.
179

Synchronizace vláken: mutex
int pthread mutex init(pthread mutex t *mx,
const pthread mutexattr t *attr );
• Inicializuje mutex mx s atributy attr (nastavují se pomocí
pthread mutexattr ...(), NULL = default).
int pthread mutex destroy(pthread mutex t *mx );
• Zruší mutex.
int pthread mutex lock(pthread mutex t *mx );
• Zamkne mutex, případně uspí vlákno.
int pthread mutex trylock(pthread mutex t *mx );
• Zamkne mutex, když nelze, skončí s chybou.
int pthread mutex unlock(pthread mutex t *mx );
• Odemkne mutex.
180

Podmínkové proměnné (1)
int pthread cond init(pthread cond t *cond,
const pthread condattr t *attr );
• Inicializuje podmínkovou proměnnou cond s atributy attr
(nastavují je funkce pthread condattr ...()), NULL = default.
int pthread cond destroy(pthread cond t *cond );
• Zruší podmínkovou proměnnou.
int pthread cond wait(pthread cond t *cond,
pthread mutex t *mutex );
• Čeká na podmínkové proměnné dokud jiné vlákno nezavolá
pthread cond signal() nebo pthread cond broadcast().
181

Podmínkové proměnné (2)
int pthread cond timedwait(pthread cond t *cond,
pthread mutex t *mutex,
const struct timespec *abstime );
• Čeká na pthread cond signal() nebo
pthread cond broadcast(), ale maximálně do vypršení timeoutu
abstime.
int pthread cond signal(pthread cond t *cond );
• Probudí jeden proces čekající na podmínkové proměnné cond.
int pthread cond broadcast(pthread cond t *cond );
• Probudí všechny procesy čekající na podmínkové proměnné cond.
182

Použití podmínkových proměnných
pthread_cond_t cond; pthread_mutex_t mutex;
...
pthread_mutex_lock(&mutex);
while(!podminka(data))
pthread_cond_wait(&cond, &mutex);
set_data(data, ...);
pthread_mutex_unlock(&mutex);
...
pthread_mutex_lock(&mutex);
set_data(data, ...);
pthread_cond_signal(&cond);
pthread_mutex_unlock(&mutex);

183

Read-write zámky (1)
int pthread rwlock init(pthread rwlock t *l,
const pthread rwlockattr t *attr );
• Vytvoří zámek s atributy podle attr (nastavují se funkcemi
pthread rwlockattr ...(), NULL = default).
int pthread rwlock destroy(pthread rwlock t *l );
• Zruší zámek.
int pthread rwlock rdlock(pthread rwlock t *l );
int pthread rwlock tryrdlock(pthread rwlock t *rwlock );
• Zamkne zámek pro čtení (více vláken může držet zámek pro čtení),
pokud má někdo zámek pro zápis, uspí volající vlákno (rdlock())
resp. vrátí chybu (tryrdlock()).
184

Read-write zámky (2)
int pthread rwlock wrlock(pthread rwlock t *rwlock );
• Zamkne zámek pro zápis, pokud má někdo zámek pro čtení nebo
zápis, čeká.
int pthread rwlock trywrlock(pthread rwlock t *rwlock );
• Jako pthread rwlock wrlock(), ale když nemůže zamknout, vrátí
chybu.
int pthread rwlock unlock(pthread rwlock t *rwlock );
• Odemkne zámek.

185

Úkoly správce systému
• instalace a konfigurace operačního systému a aplikací
• údržba systému souborů (kontrola konzistence svazků – fsck,
zálohování dat)
• správa uživatelských účtů a přidělování diskového prostoru
uživatelům (quota)
• sledování zatížení systému (top, sar, du)
• sledování provozních hlášení systému (syslogd)
• konfigurace periodicky prováděných akcí (cron)
• správa síťových služeb (inetd, sendmail, ftpd, httpd)
• zajištění bezpečnosti systému
186

Start systému
• Nejprve je implementačně závislým způsobem načteno do paměti a
spuštěno jádro systému.
• Jádro provede svoji inicializaci, připojí kořenový svazek souborů,
vytvoří nový proces a spustí program init. Zbytek inicializace
systému probíhá v uživatelském režimu a je řízen procesem init.
• init čte /etc/inittab a podle jeho obsahu spouští další procesy.
• Původně UNIX rozlišoval víceuživatelský režim běhu systému
(normální běh systému) a jednouživatelský režim (init spouští jen
nejzákladnější procesy, které umožní přihlášení uživatele root,
používá se pro instalaci a konfiguraci komponent systému). Takto
některé unixové systémy fungují dodnes, např. FreeBSD.
187

Úrovně běhu systému
• System V zavedl více úrovní běhu systému, superuživatel přepíná
systém do úrovně U příkazem init U .
– 0 . . . zastavení systému
– 1 . . . administrátorský režim
– 2 . . . víceuživatelský režim
– 3 . . . víceuživatelský režim se sdílením síťových zdrojů
– 4 . . . alternativní víceuživatelský režim
– 5 . . . zastavení systému a přechod do firmware
– 6 . . . restart systému (reboot)
– S, s . . . jednouživatelský (single-user) režim
• Kromě označení úrovně init rozlišuje:
– q, Q . . . znovu načíst /etc/inittab
– a, b, c . . . spuštění procesů podle /etc/inittab bez změny
úrovně běhu systému
188

Formát souboru /etc/inittab
id:úrovně:akce:proces
• id . . . jednoznačný identifikátor, max. 4 znaky
• úrovně . . . označení úrovní, ve kterých má proces běžet, při vstupu
do jiné úrovně bude zrušen
• akce:
– respawn . . . vytvořit proces při vstupu do úrovně, obnovit při
zániku procesu
– wait . . . při vstupu do úrovně vytvořit proces a čekat na
ukončení
– once . . . vytvořit proces při vstupu do úrovně
– off . . . nepoužívaná položka
– initdefault . . . používán pouze při počátečním spuštění
programu init, definuje standardní číslo úrovně
– proces . . . příkaz, který má být spuštěn
189

Příklad: /etc/inittab
is:2:initdefault:
s0:06s:wait:/etc/rc0 >/dev/console 2>&1 </dev/console
s2:23:wait:/etc/rc2 >/dev/console 2>&1 </dev/console
s3:3:wait:/etc/rc3 >/dev/console 2>&1 </dev/console
s4:06:wait:/etc/umountfs > /dev/console 2>&1
t1:23:respawn:/sbin/getty ttyd1 console # alt console
t2:23:off:/sbin/getty -N ttyd2 co_9600 # port 2
t3:23:off:/sbin/getty -N ttyd3 co_9600 # port 3
t4:23:off:/sbin/getty -N ttyd4 co_9600 # port 4

190

Inicializační skripty
init 2
/etc/rc2
/etc/rc2.d/K08autofs stop

/etc/init.d/autofs

/etc/rc2.d/K20nfs stop

case $1 in
start )
... ;;
stop )
... ;;
*)
echo "usage: " \
"$0 (start|stop)"
;;
esac

/etc/rc2.d/K89portmap stop
/etc/rc2.d/S10network start
/etc/rc2.d/S21random start
/etc/rc2.d/S30syslog start

191

Zastavení systému
• Uživatel root používá k zastavení systému příkaz shutdown, který
přepne systém do úrovně 0 (přitom spouští příslušné ukončovací
skripty), uloží nezapsaná data, odpojí disky a zastaví jádro.
• Příkaz reboot je obdoba shutdown, ale přepne systém do úrovně 6,
tj. způsobí zastavení a nové nastartování systému.
• Jestliže dojde k závažné chybě systému (neplatná adresa použitá
jádrem, zrušení procesu init), jádro vytvoří protokol o chybě
(včetně kompletního obsahu paměti jádra), vypíše hlášení tvaru
„panic: příčina chyby ÿ a zastaví se.

192

Přihlašování uživatelů
init

fork+exec

getty

exec

login

exec

sh

• init spouští na každém terminálu proces getty.
• getty vypíše výzvu login:, načte jméno uživatele a spustí program
login.
• login přečte heslo, nastaví nové UID, GIDs a spustí shell.
• Po odhlášení uživatele init spustí znovu getty.
• V některých implementacích se místo getty používá jeden proces
ttymon, který monitoruje všechny terminály.
• Při přihlašování po síti přebírá roli getty síťový server (např.
telnetd nebo sshd).
193

Periodicky opakované akce: cron
• Provádění určitých akcí opakovaně v zadaném čase zajišťuje démon
cron.
• Při své práci se cron řídí obsahem konfiguračního souboru
(crontab), který existuje pro každého uživatele.
• Konfigurační soubor se zobrazuje příkazem crontab -l a vytváří
příkazem crontab < soubor.
• Každý řádek souboru má tvar:
03 3 * * 0,2,4 root /backup/bin/backup
Prvních pět položek definuje čas (minuta, hodina, den v měsíci,
měsíc, den v týdnu), kdy se má příkaz uvedený na zbytku řádku.
• Jednorázové akce lze v daný čas spustit příkazem at.
194

Síťové služby: inetd
• Servery síťových služeb se spouští buď při startu systému, nebo je
startuje démon inetd při připojení klienta.
• Démon inetd čeká na portech definovaných v /etc/inetd.conf a
když detekuje připojení klienta, naváže spojení, spustí příslušný
server a přesměruje mu deskriptory 0, 1 a 2 do soketu, přes který lze
komunikovat s klientem.
• Příklad obsahu /etc/inetd.conf:
ftp stream tcp nowait root /usr/etc/ftpd ftpd -l
shell stream tcp nowait root /usr/etc/rshd rshd -L
login stream tcp nowait root /usr/etc/rlogind rlogind
exec stream tcp nowait root /usr/etc/rexecd rexecd
finger stream tcp nowait guest /usr/etc/fingerd fingerd
ntalk dgram udp wait root /usr/etc/talkd talkd
tcpmux stream tcp nowait root internal
echo stream tcp nowait root internal
195

Formát souboru /etc/inetd.conf
služba soket proto čekání uživ server argumenty
• služba . . . jméno síťové služby podle /etc/services
• soket . . . stream nebo dgram
• proto . . . komunikační protokol (tcp, udp)
• čekání . . . wait (inetd čeká na ukončení serveru před
akceptováním dalšího klienta), nowait (inetd akceptuje dalšího
klienta hned)
• uživatel . . . server poběží s identitou tohoto uživatele
• server . . . úplná cesta k programu serveru nebo internal (službu
zajišťuje inetd)
• argumenty . . . příkazový řádek pro server, včetně argv[0]
196

Práce s řetězci
• Chyby při zpracování řetězců jsou častou příčinou bezpečnostích děr
typu buffer overflow: program dostane dlouhý řetězec a bez
kontroly délky ho uloží do paměti. Řetězec přeteče z oblasti, která je
pro něj vymezena, do sousedního úseku paměti (může obsahovat
např. návratovou adresu na zásobníku) a přepíše ho. Tím jsou
poškozena data programu nebo lze dokonce spustit kód obsažený
v řetězci. Útokem na privilegovaný proces je možné získat práva
superuživatele a to i po síti, pokud se jedná o síťový server.
• Základní ochrana: před uložením do paměti kontrolovat délku
řetězců (dat obecně), používat funkce strncat(), strncpy(),
snprintf(), fgets(), apod.
• Řetězec délky n potřebuje na uložení n + 1 bajtů!
197

Formátové chyby
• Některé funkce, např. printf(), sprintf(), syslog(), dostávají
jako první parametr formátový řetězec a za ním volitelně proměnný
počet parametrů, které se interpretují podle obsahu formátového
řetězce.
• Jestliže místo printf("%s", string) použijeme printf(string)
a řetězec string není obsažen přímo v programu, ale získán od
uživatele, může uživatel vhodnými formátovacími direktivami nejen
vypsat obsah zásobníku, ale pomocí direktivy %n dokonce libovolně
změnit obsah paměti procesu a vynutit spuštění vlastního strojového
kódu.
• Výsledkem je havárie programu nebo dokonce získání práv uživatele
root, pokud je takto napaden např. nějaký SUID program.
198

Národní prostředí (1)
• UNIX obsahuje mechanismus locale. Tím lze definovat národní
zvyklosti v kategoriích:
– LANG . . . definuje následující kategorie, pro které nejsou
nastavené specifické proměnné LC *
– LC CTYPE . . . znaková sada
– LC COLLATE . . . uspořádání znaků a řetězců
– LC MESSAGES . . . katalog zpráv vypisovaných programy
– LC TIME . . . formát data a času
– LC NUMERIC . . . formát čísel
– LC MONETARY . . . formát peněžních částek
– LC ALL . . . všechny kategorie (přednost před LC * a LANG)
• Definiční soubory např. /usr/lib/locale/jméno/kategorie
• Jména POSIX a C vždy existují a definují implicitní locale.
• Pro češtinu se používají jména cs nebo cs_CZ.
199

Národní prostředí (2)
char *setlocale(int category, const char *locale );
• Nastaví locale pro danou kategorii. Vrací locale nebo NULL, pokud
zadané locale nelze nastavit.
• Jestliže je locale == "", použije příslušnou proměnnou prostředí
(LC CTYPE, LC COLLATE, LC MESSAGES, LC TIME, LC NUMERIC,
LC MONETARY nebo LC ALL). Proměnná LC ALL má přednost před
všemi ostatními. Když některá proměnná není definována, použije
místo ní hodnotu proměnné LANG. Když je locale == NULL, funkce
pouze vrátí aktuální locale.
int strcoll(const char *s1, const char *s2 );
• Porovnání řetězců s použitím aktuálního LC COLLATE.
200

Terminály
• Vstup z terminálu může pracovat v jednom ze dvou základních
režimů:
– raw . . . napsané znaky jsou okamžitě předávány aplikaci
– cooked . . . aplikace dostává text po řádcích, jádro zajišťuje
zpracování speciálních znaků (např. poslání signálu při stisku
Ctrl-C)
• Při výstupu na terminál lze řídicími sekvencemi znaků (escape
sequences) ovládat funkce jako posun kurzoru. Knihovna curses
poskytuje tyto funkce bez nutnosti používat konkrétní sekvence,
využívá databázi typů terminálů terminfo (např.
v /usr/share/lib/terminfo/).
• Vlastnosti terminálů (rychlost, echo, speciální znaky, apod.) se
nastavují a testují příkazem stty nebo systémovými voláními
tcsetattr() a tcgetattr().
201

Pseudoterminály
• Jádro simuluje terminálové rozhraní pro programy jako xterm nebo
telnet pomocí pseudoterminálů (dvojice zařízení master a slave,
data zapsaná na straně master lze číst na straně slave a naopak).
mfd=open("/dev/ptmx", ...);
sname=ptsname(mfd);
grantpt(mfd);
unlockpt(mfd);
fork();
sfd=open(sname, ...);
close(mfd); dup2(sfd,0);
dup2(sfd,1); dup2(sfd,2);
close(sfd);
execl("/bin/sh", ...);

/* Emulace terminálu
na zařízení mfd */

202

Knihovna curses
• Implementace řízení terminálu nezávisle na konkrétním typu
terminálu. Výstup do oken na terminálu, pohyb kurzoru, nastavení
barev, apod.
• Inicializace:
initscr(); cbreak(); noecho();
intrflush(stdscr, FALSE); keypad(stdscr, TRUE);
• Posun kurzoru: int move(int y,int x );
• Výstup na zadanou pozici:
int mvprintw(int y, int x, char *fmt, ...);
• Vykreslení změn: refresh();
• Načtení znaku: int getch(void);
• Konec curses, obnovení nastavení terminálu: endwin();
203

X Window System
• standardní UNIXové grafické uživatelské rozhraní
• distribuovaný systém – aplikace mohou běžet na jiném počítači
než kde sedí uživatel, na jedné obrazovce mohou být okna aplikací
z různých počítačů
• vytvořen na MIT od roku 1984
• verze X11 v roce 1987
• poslední verze je X11 Release 6.6
• další vývoj zajišťuje konsorcium X.Org
• dodáván výrobci UNIXových systémů jako součást operačního
systému
• volně šiřitelná implementace XFree86
204

Struktura X
aplikace

aplikace

aplikace

emulátor
terminálu

window
manager





























toolkit
Xlib

klienti

síť

...
205

X server

Komponenty X
• X server . . . proces, který zajišťuje výstup na obrazovku a vstup
z klávesnice, myši, popř. dalších vstupních zařízení (např. tablet)
– Na jednom počítači může být více X serverů (display), každý
může mít několik obrazovek (screen).
• X klient . . . aplikace, která používá X pro své GUI
• X protokol . . . síťový protokol pro komunikaci mezi X serverem a
X klientem
• Xlib . . . API knihovna, překládá volání funkcí X na zprávy
X protokolu
– funkce na úrovni základní manipulace s okny, kreslení a přijímání
událostí od klávesnice a myši
– server informuje aplikaci pomocí událostí o akcích uživatele
206

Komponenty X (2)
• toolkity (X Toolkit, Motif, GTK+, Qt) . . . poskytují prvky
uživatelského rozhraní (tlačítka, menu, scrollbary, atd.)
• window manager . . . kreslí rámečky oken, řídí manipulace s okny
(posouvání, zvětšování, zavírání. . .)
– samostatná aplikace, uživatel si může zvolit window manager,
který mu nejvíce vyhovuje (twm, mwm, olwm, fvwm95,
Enlightenment. . .)
• terminálový emulátor (xterm) . . . pomocí pseudoterminálů
emuluje terminál pro aplikace s textovým vstupem a výstupem
(především shell)
• Existují i celá integrovaná grafická prostředí, jako CDE, KDE nebo
Gnome.
207

Spuštění aplikace X
• Buď pomocí menu v prostředí X, nebo ze shellu
• Proměnná prostředí DISPLAY určuje, s kterým X serverem bude
aplikace pracovat
– DISPLAY=:0.0 . . . lokální X server na stejném počítači, kde běží
aplikace
– DISPLAY=omega.ms.mff.cuni.cz:1.0 . . . display číslo 1,
obrazovka č. 0 na počítači omega.ms.mff.cuni.cz
– obecně DISPLAY=[host ]:display [.screen ]
• Aplikace, která se připojí k X serveru má přístup ke všemu, co se na
X serveru děje, může manipulovat i s okny ostatních aplikací. Proto
je potřeba omezit přístup k serveru:
– xhost . . . povolení přístupu pouze z některých počítačů
– xauth . . . povolení pouze pro aplikace, které znají klíč
(MIT-MAGIC-COOKIE)
208

Start X Window
• Z textové systémové konzole (ze shellu) se X spustí obvykle
příkazem startx.
startx [clientargs] [-- serverargs]
xinit [[client [opts]] [-- [server] [display] [opts]]
server

klienti

~/.xserverrc

~/.xinitrc

/usr/lib/X11/xinit/xserverrc

/usr/bin/X11/X

/usr/lib/X11/xinit/xinitrc

twm

209

xterm

xman

X Display Manager (xdm)
• Démon xdm dovoluje logování na grafických stanicích i na X
terminálech přímo do X, bez nutnosti loginu na textovém terminálu
a následného spuštění xinit.
xdm
X server

/usr/lib/X11/xdm/Xsetup

login:
password:

xlogin
Xstartup
/usr/lib/X11/xdm/Xsession
/usr/lib/X11/xdm/Xreset
210

~/.xsession

Konfigurace xdm
• Konfigurační soubory v adresáři /usr/lib/X11/xdm
– xdm-config . . . hlavní konfigurační soubor
– Xservers . . . seznam (obvykle lokálních) serverů, které mají být
pořád řízeny tímto xdm. Dále xdm řídí servery, které o to požádají
pomocí protokolu XDMCP (X Display Manager Control
Protocol)
– Xaccess . . . nastavuje protokol XDMCP
– Xsetup . . . inicializace serveru
– Xstartup . . . akce po zadání uživatelského jména a hesla
– Xsession . . . uživatelská inicializace, spouští window manager a
aplikace, po skončení je uživatel odlogován
– Xreset . . . akce prováděné při odlogování uživatele
• Chybová hlášení z Xsetup, Xstartup, Xsession a Xreset se
zapisují do /usr/lib/X11/xdm/xdm-errors.
211

X Resources
• Textový zápis konfiguračních hodnot aplikací ve tvaru:
aplikace[.podobjekt...].atribut: hodnota
– ‘ !‘ . . . uvozuje komentářový řádek
– ‘ \‘ . . . na konci řádku znamená pokračování hodnoty na
dalším řádku
– ‘ *‘ . . . zastupuje libovolný počet úrovní hierarchie
– ‘ ?‘ . . . zastupuje jednu úroveň hierarchie
– ‘ \n‘ . . . znak konce řádku v hodnotě
– ‘ \nnn‘ . . . oktalový zápis znaku
– ‘ \ ‘ , ‘ \tab ‘ zápis mezery nebo tabulátoru na začátku
hodnoty (obyčejné mezery a tabulátory jsou na začátku zápisu
hodnoty ignorovány)
• Každou úroveň hierarchie lze zadat jako instanci (obvykle začíná
malým písmenem) nebo třídu (velké písmeno na začátku).
212

X Resources (příklad)
xterm.vt100.scrollBar:

True

instance

XTerm.VT100.ScrollBar:

True

třída

xterm.?.scrollBar:

True

vynechání úrovně

*scrollBar:

True

vynechání více úrovní

xtNoScroll*scrollBar:

False

použije se, když se xterm spustí
s přepínačem -name xtNoScroll

213

X Resources – vyhodnocování
• Přednost má nejvíce specifikovaná hodnota.
• Těsná vazba ‘ .‘ (tight binding) má přednost před volnou vazbou
‘ *‘ (loose binding).
• Instance má přednost před třídou.
• Instance a třída mají přednost před ‘ ?‘ .
• Levé komponenty mají větší váhu než pravé. Např.
xterm*background má přednost před *window.bakground.

214

X Resources – použití v aplikaci
1. Resources specifické pro aplikaci třídy Class v souboru
/usr/lib/X11/app-defaults/Class .
2. Obsah resource databáze v X serveru vytvořené pomocí příkazu
xrdb.
3. Obsah souboru definovaného proměnnou prostředí XENVIRONMENT.
4. Hodnoty zadané na příkazovém řádku přepínačem -xrm.
• Startovací skripty xinitrc (pro startx) a Xsession (pro xdm)
obvykle zajistí načtení resources do X serveru pomocí xrdb ze
souboru ~/.Xresources.

215

Konec

216

