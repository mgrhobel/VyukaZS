---
title: "unix_slides_notes.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/prednasky/unix_slides_notes.pdf"
date: 2009-02-19
type: PDF (text-based)
---

Programování v Unixu
Jan Pechanec
12. ledna 2006
(slajdy jsou pokračováním materiálů Martina Berana
přednášejícího tuto přednášku v letech 1999 – 2004)

SISAL MFF UK, Malostranské nám. 25, 118 00 Praha 1
jp@devnull.cz
http://www.devnull.cz

Organizační věci:
• předmět UNIX je 2/1, cvičení bude jednou za dva týdny v laboratoři UNIX
• informace a materiály k přednášce na http://www.devnull.cz/mff
• zapsat se na cvičení na webu
• zápočet za zápočtový program
• zkouška písemná a ústní, nutno získat zápočet před zkouškou
• zkoušet se bude to, co bude odpředneseno (kromě témat na vyplnění případně
zbylého času), tj. po administraci systému včetně. Většina informací je ve
slidech, ale řada podrobností chybí, proto je třeba buď chodit na přednášku,
nebo studovat literaturu a experimentovat.
• předpoklady:
– uživatelská znalost UNIXu, programování v shellu (na úrovni přednášky
Úvod do UNIXu a TCP/IP)
– znalost jazyka C
– znalost základních pojmů teorie operačních systémů

1

Obsah
• úvod, vývoj UNIXu a C, programátorské nástroje
• základní pojmy a konvence UNIXu a jeho API
• přístupová práva, periferní zařízení, systém souborů
• manipulace s procesy, spouštění programů
• signály
• synchronizace a komunikace procesů
• síťová komunikace
• vlákna, synchronizace vláken
• UNIX z pohledu správce
• závěrečná všehochuť podle toho, kolik zbude času (bezpečnost,
locales, pseudoterminály, X Window)

• budeme se zabývat hlavně principy UNIXu a téměř výhradně programováním
pro UNIX v jazyce C.
• při popisu API se budeme držet specifikace Single UNIX Specification, version 2. Systémy podporující tuto specifikaci se mohou označit značkou UNIX 98.
Další verze těchto textů budou opraveny (pokud to bude potřeba) pro aktuální specifikaci verze 3, označující tuto normu podporující systémy jako
UNIX 03.

2

Literatura v češtině (1)
• Brodský, J.; Skočovský, L.: Operační systém UNIX a jazyk C.
SNTL, Praha 1989
• Skočovský, L.: Principy a problémy operačního systému UNIX.
Science, 1993
• Skočovský, Luděk: UNIX, POSIX, Plan9. L. Skočovský, Brno, 1998
• Jelen, Milan: UNIX V - programování v systému. Grada, Praha
1993
. . . ohledně Unixu spíše doporučuji literaturu v anglickém jazyce
• Herout, Pavel: Učebnice jazyka C. 2 díly. Kopp, České Budějovice,
1994

1. klasická česká kniha o UNIXu a C, ale dnes už zastaralá
2. novější verze (1), bez C, všestranný úvod do UNIXu, ale dost stručná
3. pokročilejší pohled, ale předpokládá předběžné znalosti, místy těžko stravitelná
4. programování v C pro UNIX System V, práce se soubory a s procesy, System
V IPC, nepopisuje např. vlákna, sítě

3

Literatura (2)
• Uresh Vahalia: UNIX Internals: The New Frontiers. Prentice
Hall; 1st edition, 1995
• McKusick, M. K., Neville-Neil, G. V.: The Design and
Implementation of the FreeBSD Operating System.
Addison-Wesley, 2004
• Goodheart, B.; Cox, J.: The Magic Garden Explained: the
Internals of UNIX System V Release 4. Prentice Hall, 1994
• Bach, Maurice J.: Principy operačního systému UNIX. SAS, 1993
(originál Prentice Hall, 1986)
• Unixové specifikace, viz http://www.unix.org
• manuálové stránky (zejm. sekce 2, 3)

1. skvělá kniha, zabývá se obecnými myšlenkami UNIXu a porovnává systémy
SVR4.2, 4.4BSD, Solarix 2.x a Mach. V prosinci (12/2005) by mělo vyjít nové
vydání.
2. popis struktury a funkcí jádra FreeBSD 5.2; tato kniha navazuje na klasickou
knihu The Design and Implementation of the 4.4 BSD Operating
System od stejného autora (resp. jeden ze čtyř, uvedený jako první)
3. popis struktury a funkcí jádra UNIX System V Rel. 4
4. opět klasika, popis struktury a funkcí jádra UNIX System V Rel. 2, částečně i 3; přestože je to kniha z dnešního pohledu již zastaralá, lze ji pořád
jednoznačně doporučit
5. homepage posledních specifikací rozhraní UNIXu
6. podrobný popis jednotlivých funkcí (v Linuxu často nedostatečné, manuálové stránky v tomto systému typicky výrazně horší kvality než u ostatních
systémů)

4

Literatura (3)
• Linux - Dokumentační projekt. Computer Press, 1998;
http://www.cpress.cz/knihy/linux
• Linux Documentation Project. http://tldp.org/
• Rochkind, M. J.: Advanced UNIX Programming,
Addison-Wesley; 2nd edition, 2004
• Stevens, W. R., Fenner B., Rudoff, A. M.: UNIX Network
Programming, Vol. 1 – The Sockets Networking API. Prentice
Hall, 3rd edition, 2004
• Butenhof, D. R.: Programming with POSIX Threads,
Addison-Wesley; 1st edition, 1997

1. česká kniha shrnující dokumentaci Linuxu
2. homepage linuxové dokumentace
3. klasická kniha, jedna z nejlepších k tomuto tématu; existuje i druhý díl UNIX
Network Programming, Volume 2: Interprocess Communications,
která se zabývá komunikací mezi procesy (roury, POSIX IPC, System V IPC,
synchronizace vláken, RPC).
4. aktualizované vydání další z klasických knih o programování pod Unixem
. . . a spousta dalších knih, online dokumentací a internetových zdrojů, poslední
dobou vychází poměrně hodně knih o Linuxu, zaměřených na používání i
programování
. . . jděte na http://www.amazon.com/ a zadejte klíčové slovo „unixÿ. Pokud
byste z Amazonu něco kupovali, dejte pozor na to, že mnoho knih má aktualizovaná vydání i po několika málo letech, někdy i levnější než ta původní,
která jsou však stále na skladu a v on-line nabídce; tak ať zbytečně nekoupíte
starší vydání než to aktuální. Navíc se vyplatí zkontrolovat i u příslušného
vydavatelství, že není v brzké době naplánováno vydání nové – tato informace
někdy na Amazonu je, někdy ne.

5

Literatura (historie UNIXu)
• Peter Salus: A Quarter Century of UNIX, Addison-Wesley;
1st edition (1994)
• Libes D., Ressler, S.: Life With Unix: A Guide for Everyone,
Prentice Hall (1989)
• Open Sources: Voices from the Open Source Revolution,
kapitola Twenty Years of Berkeley Unix From AT&T-Owned to
Freely Redistributable; O‘ Reilly (1999); on-line na webu
. . . mnoho materiálů na webu; často však obsahující ne zcela přesné
informace

• kapitola o BSD Unixu napsaná Marshallem Kirk McKusickem je opravdu
výborná

6

(Pre)historie UNIXu
• 1925 – Bell Telephone Laboratories – výzkum v komunikacích
(např. 1947: transistor)
• 1965 – BTL s General Electric a MIT vývoj OS Multics
(MULTIplexed Information and Computing System)
• 1969 – Bell Labs opouští projekt, Ken Thompson píše assembler,
základní OS a systém souborů pro PDP-7
• 1970 – Multi-cs ⇒ Uni-cs ⇒ Uni-x
• 1971 – UNIX V1, a portován na PDP-11
• prosinec 1971 – první edice UNIX Programmer‘ s Manual

• po odchodu BTL z projektu Multics prodala GE svoji počítačovou divizi
firmě Honeywell včetně projektu Multics, který se pak pod její patronací
dále vyvíjel (virtuální paměť, multiprocesory, . . . ). Poslední instalace systému
Multics fungovala na kanadském Ministerstvu obrany (Canadian Department
of National Defence) a byl například ještě aktivně používán pro vojenské
operace během války v Perském zálivu. Definitivní shutdown byl proveden
31. října 2000. Více informací na http://www.multicians.org.
• před počátkem práce na vývojovém prostředí pro PDP-7 napsal Thompson
program Space Travel, který byl vyvinut na jiném prostředí (Honeywell 635)
a na pásce přenesen na PDP-7.
• celkem bylo 10 edicí tohoto manuálu, korespondující deseti verzím UNIXu
vzniklých v BTL.
• UNIX V1 neměl pipe() !!!
• za povšimnutí stojí, že UNIX je o zhruba 10 let starší než DOS
• systém Multics měl 9 hlavních cílů, jak popsáno v článku Introduction and
Overview of the Multics System z roku 1965. Za nejzajímavější cíl bych považoval požadavek na nepřerušovaný běh systému.
• Multics byl napsaný v jazyce PL/I (Programming Language #1), tedy dříve
než byl UNIX přepsaný do C !
• Multicsu byl v roce 1980 udělen jako prvnímu systému level B2. Po několik
let to byl jediný systém s tímto bezpečnostím levelem.

7

• GE byla založena v roce 1892 sloučením dvou společností, z nichž jedna byla
Edison General Electric Company (založ. 1879) Thomasem Alvou Edisonem, vynálezcem žárovky, filmové kamery, . . . ; v současné době její dceřinné společnosti pokrývají mnoho oblastí, včetně dodávky motorů pro Airbus 380 (verze s jejich motory má vzlétnout v roce 2006), bankovnictví.
(http://www.ge.cz) atd.
• PDP = Programmed Data Processor. První PDP mašina, PDP-1, se prodávala za $120.000 v době, kdy se jiné počítače prodávaly za ceny přes milión.
To byla také strategie fy DEC - pojem computer tehdy znamenal drahou věc,
potřebující sál a tým lidí, který se o to všechno bude starat. Proto DEC své
mašiny nenazýval počítači, ale pravě slovem PDPs.
• PDP-11 je legendární mašina od firmy DEC, postupně vznikaly verze PDP1 az PDP-16, kromě PDP-2, PDP-13. Existují PDP-11 systémy, které ještě
dnes běží.

Historie UNIXu, pokračování
• únor 1973 – UNIX V3 obsahoval cc překladač (jazyk C byl vytvořen
Dennisem Ritchiem pro potřeby UNIXu)
• říjen 1973 – UNIX byl představen veřejnosti článkem The UNIX
Timesharing System na konferenci ACM
• listopad 1973 – UNIX V4 přepsán do jazyka C
• 1975 – UNIX V6 byl první verzí UNIXu běžně k dostání mimo BTL
• 1979 – UNIX V7, pro mnohé „the last true UNIXÿ, obsahoval uucp,
Bourne shell; velikost kernelu byla pouze 40KB !!!
• 1979 – UNIX V7 portován na 32-bitový VAX-11
• 1980 – Microsoft příchází s XENIXem, který je založený na
UNIXu V7

• akt přepsání UNIXu do jazyka C byl možná nejvýznamnějším momentem v historii tohoto systému ⇒ UNIX mohl být mnohem jednodušeji portován na jiné architektury
• na verzi 6 je založena legendární kniha A commentary on the Unix Operating
System, jejíž autorem je John Lions.
• Microsoft neprodával XENIX přímo, ale licensoval ho OEM výrobcům (Original Equipment Manufacturer) jako byl Intel, SCO a jiní. Jiné firmy pak
XENIX dále portovaly na 286 (Intel) a 386 (SCO, 1987). Na webu je možné
najít zajímavé informace popisující tuto dobu a tehdy kladný vztah Microsoftu k UNIXu.

8

Divergence UNIXu
• pol. 70. let – uvolňování UNIXu na univerzity: především University
of California v Berkeley
• 1979 – z UNIX/32V (zmíněný port na VAX) poskytnutého do
Berkeley se vyvíjí BSD Unix (Berkeley Software Distribution)
verze 3.0; poslední verze 4.4 v roce 1993
• 1982 AT&T, vlastník BTL, může vstoupit na trh počítačů
(zakázáno od roku 1956) a příchází s verzí System III (1982) až V.4
(1988) – tzv. SVR4
• vznikají UNIX International, OSF (Open Software Foundation),
X/OPEN, . . .
• 1991 – Linus Torvalds zahájil vývoj OS Linux, verze jádra 1.0 byla
dokončena v r. 1994

• UNIX je univerzální operační systém fungující na široké škále počítačů od
embedded a handheld systémů (Linux), přes osobní počítače až po velké
servery a superpočítače.
• UNIX V3 = UNIX verze 3, UNIX V.4 = system 5 release 4 atd.
• UNIX System III tedy není UNIX V3; v této době (pozdní 70. léta) bylo
v BTL několik skupin, které příspívaly do vývoje UNIXu. Vx verze byly
vyvíjeny v rámci Computer Research Group, další skupiny byly Unix System
Group (USG), Programmer‘ s WorkBench (PWB). Další větví UNIXu byl
Columbus UNIX též v rámci BT. Na těchto různých verzích je právě založena
verze System III. Zájemce o více informací odkazuji na web.
• UNIX se rozštěpil na dvě hlavní větve: AT&T a BSD, jednotliví výrobci přicházeli s vlastními modifikacemi. Jednotlivé klony od sebe navzájem přebíraly
vlastnosti.
• Berkeley univerzita získala jako jedna z prvních licenci UNIXu v roce 1974.
Během několika let studenti (jedním z nich byl Bill Joy, pozdější zakladatel
firmy Sun Microsystems a autor C-shellu) vytvořili SW balík Berkeley Software Distribution (BSD) a prodávali ho v roce 1978 za $50. Tyto počáteční
verze BSD obsahovaly pouze SW a utility (první verze: Pascal překladač,
editor ex ), ne systém ani žádné jeho změny. To příšlo až s verzí 3BSD.
• verze 4BSD vzniká roku 1980 již jako projekt financovaný agenturou DARPA
a vedený Billem Joyem. Trpí problémy spojenými s nedostatečným výkonem,
vzniká tak vyladěný systém 4.1BSD dodávaný od roku 1981.

9

• 4.1BSD mělo být původně 5BSD, ale AT&T mělo námitky, že by to mohlo
mást zákazníky, kteří by si mohli plést 5BSD se systémem System V. Proto
BSD přešlo na číslování 4.xBSD.
• (1988) 4.3BSD-Tahoe měl již rozdělený kód kernelu na závislý na architektuře
a nezávislý
• (1989) Networking Release 1, první volně šiřitelný kód z Berkeley obsahující
síťový kód z Tahoe, nezávislý na licenční politice AT&T. Licenční politika z
Berkeley byla oproti politice AT&T velmi liberální.
• další běžnou věcí bylo i to, že než psát vlastní kód, vývojáři z Berkeley se
raději nejdříve podívali kolem, co je již hotové. Tak BSD například převzalo
virtuální paměť z Machu a nebo NFS-compatibilní kód vyvinutý na jedné
kanadské univerzitě.
• 386/BSD založené na Networking Release 2 ; Bill Jolitz vytvořil 6 chybějících
souborů a dal tak dohromady funkční BSD systém pro i386. Tento systém se
stal základem systémů NetBSD a FreeBSD (a dalších, z těchto dvou systémů
vycházejících).
• (červen 1995) 4.4BSD-Lite Release 2, po které následuje rozpuštění
CSRG, která skoro 20 let pilotovala vývoj BSD větve.
• . . . více již zmíněná kapitola o BSD Unixu.

10

Současné UNIXy
Komerční
• SUN: SunOS (není již dále vyvíjen), Solaris
• SGI: IRIX
• Compaq: Tru64 UNIX
• IBM: AIX
• HP: HP-UX
• Novell: UNIXware
• SCO: SCO Unix
Open source
• FreeBSD, NetBSD, OpenBSD, DragonFlyBSD, OpenSolaris
• Linux

• když jsem cca v roce 1998 projel nmapem všechny DNS root servery, abych
zjistil na kterých systémech běží, bylo 80% z nich na SunOS/Solaris. IRIX
je zase systém, který po mnoho let ovládal televizní/filmový průmysl (např.
Pixar studio kde na IRIXu vznikly filmy jako A Bug‘ s Life, Toy Story a další).
A na AIX například běžel Blue Deep, paralelní superpočítač, který v roce
1997 porazil v šesti fascinujících zápasech 3.5 ku 2.5 úřadujícího velmistra
šachu Garriho Kasparova. Jinými slovy – každý systém má svoje úspěchy.
• Tru64 UNIX vychází z UNIXu firmy DEC (Ultrix, Digital Unix).
• DragonFly BSD je nedávná (2003) odnož FreeBSD 4.x řady.
• OpenSolaris je projekt vzniklý v červnu 2005 a je založen na podmnožině
zdrojových textů pro Solaris (kernel, knihovny, příkazy). V blízké budoucnosti by se měl stát základem pro další verze (komerčního) Solarisu. Oficiální
distribuce založená na vývojové verzi Solarisu (interní název Nevada) se jmenuje Solarix Express. Distribuce vzešlé z komunity jsou LiveCD SchilliX a
BeleniX, další distribuce se očekávají.
• výrobci hardware dodávali varianty UNIXu pro své počítače a komercializace
tak ještě zhoršila situaci co týče diverzifikace UNIXu
• postupně se objevila snaha o standardizaci. Standard říká, jak má vypadat systém navenek (pro uživatele, programátora a správce), nezabývá se
implementací. Cílem je přenositelnost aplikací i uživatelů. všechny systémy
totiž z dálky vypadaly jako UNIX, ale z blízka se lišily v mnoha důležitých
vlastnostech. System V a BSD se např. lišily v použitém filesystému, síťové
architektuře i v architektuře virtuální paměti.

11

• každá komerční varianta tak vycházela z jednoho z těchto dvou hlavních
systémů a přidávala si své věci
• vzniká velký počet různých standardů, skoro jako počet různých verzí UNIXů.
Nakonec se většína výrobců shodla na několika základních standardech.
• graf znázorňující historii Unixu a závislosti mezi systémy na 19-ti A4 listech
ve formátu PS/PDF je k nalezení na http://www.levenez.com/unix/

12

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

• AT&T dovolila výrobcům nazývat svoji komerční UNIX variantu „System
Vÿ pouze pokud splňovala podmínky standardu SVID.
• POSIX vzal jako společnou věc SVR3 a 4.3BSD. Prvním dokumentem je
POSIX1003.1, známým spíše jako POSIX.1, obsahující programovací API
(práce s procesy, signály, soubory, časovači atd.)
• SUSV3 je společný standard The Open Group, IEEE (Std. 1003.1, 2003 Edition) a ISO (ISO/IEC 9945-2003).
• dnes je asi nejdůležitější Single UNIX Specification (splnění je podmínkou
pro užití názvu UNIX), Je postaven na bázi POSIXu. My se budeme držet
této normy (verze 2 nebo 3, odlišnosti nejsou pro naše účely příliš velké).
Popis datových struktur a algoritmů jádra bude většinou vycházet ze System
V Rel. 4.
• AT&T také publikovala System V Verification Suite (SVVS), které ověřilo,
zda daný systém odpovídá standardu.
• (1987) AT&T koupilo 20% firmy Sun Microsystems a plánovalo společný vývoj SVR4. Sun navíc prohlásil, že jejich příští systém (tj. Solaris) bude na
rozdíl od SunOS založeného na 4BSD založený na SVR4. To vyprovokovalo
prudkou reakci od ostatních dodavatelů UNIXových systémů, kteří se báli, ze
SMI bude mít konkurenční výhodu. Vzniká proto Open Software Foundation
(OSF) s cílem vyvinout systém, uživatelské prostředí a distribuované prostředí nezávislé na licencích fy AT&T. Reakcí je vznik UNIX International.
• (1989) OSF vydává grafický uživatelský interface Motif, velmi dobře přijatý.
Objevuje se iniciální verze operačního systému OSF/1, založená na systému
Mach 2.5.
13

• OSF a UI se staly velkými rivaly, ale velmi rychle se střetly s nečekaným
protivníkem - s firmou Microsoft. A to už je jiná story. . .

Jazyk C
• téměř celý UNIX je napsaný v C, pouze nejnižší strojově závislá část
v assembleru ⇒ poměrně snadná přenositelnost
• navrhl Dennis Ritchie z Bell Laboratories v roce 1972.
• následník jazyka B od Kena Thomsona z Bell Laboratories.
• vytvořen jako prostředek pro přenos OS UNIX na jiné počítače –
silná vazba na UNIX.
• varianty jazyka:
– původní K&R C
– standard ANSI/ISO C
• úspěch jazyka C daleko přesáhl úspěch samotného UNIXu

• CPL ⇒ BCPL ⇒ B (Thompson, interpret) ⇒ C
• K&R C – jazyk C tak, jak je popsaný v knize Brian W. Kernighan, Dennis
M. Ritchie: The C Programming Language (Prentice-Hall, 1978).
• ANSI/ISO C – norma ISO/IEC 9899:1999

14

Formáty dat
• pořadí bajtů – závisí na architektuře počítače
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

• řádky textových souborů končí v UNIXu znakem LF (nikoliv CRLF).
Volání putc(’\n’) tedy píše pouze jeden znak.
• big endian – SPARC, MIPS, síťové pořadí bajtů
• little endian – Intel

• velký pozor na výstupy programů typu hexdump, které defaultně vypisují
soubor ve 2-bajtových číslech, což svádí vidět soubor jinak, než jak je opravdu
zapsaný na disku; viz příklad (i386, FreeBSD):
jp@sarrix:~$ echo -n 1234 > test
jp@sarrix:~$ hexdump test
0000000 3231 3433
0000004
je samozřejmě možné použít jiný formát výstupu:
jp@sarrix:~$ hexdump -C test
00000000 31 32 33 34
00000004

|1234|

• UNIX norma hexdump nemá, ale všude je od (octal dump), takže zde je
hexdumpu ekvivalentní formát výpisu na SPARCu (Solaris); všimněte si změny
oproti výpisu pod FreeBSD!
pechanec@u-us:~$ od -tx2 test
0000000 3132 3334
0000004

15

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

• používejte pouze novější (ANSI) typ deklarací a vždy deklarujte prototypy
funkcí (inkludovat hlavičkové soubory). Výjimkou může asi jen to, pokud
budete pracovat s kódem, který byl napsaný podle K&R.
• různými zápisy deklarací se dostáváme rovnou i k různým stylům psaní zdrojových textů. Některé systémy to příliš neřeší (Linux), jiné systémy mají
velmi striktní pravidla pro psaní zdrojových textů (např. Solaris, viz on-line
C Style and Coding Standards for SunOS ). Skoro každý UNIXový systém
má program indent(1), který vám pomocí přepínačů přeformátuje jakýkoli C
zdrojový text do požadovaného výstupu.

16

Utility
cc, c89∗ , gcc†

překladač C

CC, g++

překladač C++

†

ld

spojovací program (linker)

ldd

pro zjistění závislostí dynamického objektu

cxref

křížové odkazy ve zdrojových textech v C

∗

sccs , rcs,cvs

správa verzí zdrojového kódu

make∗

řízení překladu podle závislostí

∗

ar

správa knihoven objektových modulů

∗

dbx, gdb

prof, gprof
∗

debuggery

†
†

profilery

UNIX 98 † GNU

UNIX 98
• standardní příkaz volání kompilátoru a linkeru C je c89 (podle ISO normy
pro C z roku 1989)
• lint je v LEGACY (co je v LEGACY by se nemělo používat; UNIX 03 již
lint vůbec nemá)
• cb (C program beautifier) není
• pro správu verzí je sccs
• debuggery a profilery nejsou

17

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

statické knihovny – při linkování se stanou součástí výsledného spustitelného
programu. Dnes se už moc nepoužívá.
sdílené knihovny – program obsahuje pouze odkaz na knihovnu, při spuštění
programu se potřebné knihovny natáhnou do paměti ze souborů *.so a přilinkují.
• dnes se většinou používají sdílené knihovny, protože nezabírají tolik diskového prostoru (knihovna je na disku jednou, není součástí každého spustitelného souboru) a snadněji se upgradují (stačí instalovat novou verzi knihovny,
není třeba přelinkovat programy). Poslední verze Solarisu už například vůbec
neobsahuje libc.a, díky čemuž již programátor nemůže vytvořit statickou
binárku, aniž by neměl dostatečné znalosti systému.
• někdy se bez statických knihoven neobejdeme. V některých situacích není
možné použít knihovny dynamické, spustitelné soubory jsou takzvané standalone binaries a použití naleznou například při bootování operačního systému.

18

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

• u složitějších programů bývá zvykem rozdělit zdrojový text programu do několika modulů, které obsahují příbuzné funkce a tyto moduly se pak mohou
překládat zvlášť (dokonce každý modul může být v jiném jazyce a překládán
jiným překladačem). Výhodou je jednak urychlení překladu (překládají se
vždy jen moduly změněné od posledního překladu) a jednak flexibilita (některé moduly se mohou používat v různých programech). Pro řízení překladu
se obvykle používá utilita make.
• překladač jednotlivé zdrojové moduly přeloží do tvaru tzv. objektových modulů, jež obsahují kód programu (včetně volání lokálních funkcí), ale namísto
volání externích funkcí obsahují jen tabulku jejich jmen.
• po fázi překladu nastupuje spojovací program (též linker editor nebo loader ),
který zkompletuje výsledný program včetně vyřešení externích odkazů mezi
moduly a systémovými knihovnami resp. mezi moduly navzájem.
• použité statické knihovny jsou zkopírovány do spustitelného souboru. Na sdílené knihovny jsou ve spustitelném souboru pouze odkazy a linkuje je runtime
linker při každém spuštění programu (ld-elf.so.1 ve FreeBSD, ld.so.1 na
Solarisu atd.)
• pomocí parametrů linkeru lze určit, zda se budou používat statické nebo
dynamické knihovny. Zdrojový kód je v obou případech stejný. Existuje i
mechanismus (dlopen(), dlsym(). . . ), pomocí kterého se za běhu programu
vybere sdílená knihovna a dají se volat její funkce. Tímto způsobem můžete
také zjistit, zda v systému je přítomna příslušná funkcionalita a pokud ne,
zachovat se podle toho.

19

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

extern int var a;
main()
{
puts("Ahoj");
}

• preprocesor provádí expanzi maker, čtení vložených (include) souborů a vynechává komentáře.
• výstup preprocesoru lze získat pomocí cc -E případně přímo zavoláním cpp.
Preprocesor můžete samozřejmě používat i pro jiné projekty, které s překladem zdrojových souborů v jazyce C nemusí mít vůbec nic společného. Například podmíněná kompilace se může hodit třeba při vytváření dokumentů
v systému LATEX, jak je tomu i pro tyto slajdy pro vkládání poznámek pro
neveřejnou verzi (kde však přece jen používám obecnější makro procesor m4).
• použití preprocesoru se může velmi hodit v situaci, kdy potřebujete zasáhnout
do cizího kódu, plného podmínečných vkládání různých hlavičkových souborů
a různých definic závislých na daných podmínkách. Při hledání původce chyby
vám právě může hodně pomoci samostatného zpracování vstupního souboru
pomocí preprocesuru, kde problém již většinou rozpoznáte snadno.
• cpp vám dokáže zobrazit i celý strom vkládaných souborů, což opět při podmínečných překladech může být velmi užitečná věc

20

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

• překlad z C do assembleru
• výstup této fáze překladu lze získat pomocí cc -S.

21

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
457f 464c 0101 0001
0000 0000 0000 0000
0001 0003 0001 0000
0000 0000 0000 0000
00ec 0000 0000 0000
0034 0000 0000 0028

• překlad z assembleru do strojového kódu
• objektový modul je výsledkem příkazu cc -c.

22

Kompilátor
• volání:
cc [options ] soubor ...
• nejdůležitější přepínače:
-o soubor jméno výsledného souboru
-c

pouze překlad (nelinkovat)

-E

pouze preprocesor (nepřekládat)

-l

slinkuj s příslušnou knihovnou

-Ljméno

přidej adresář pro hledání knihoven z -l

-Olevel

nastavení úrovně optimalizace

-g

překlad s ladicími informacemi

-Djméno

definuj makro pro preprocesor

-Iadresář

umístění #include souborů

• -l/-L jsou přepínače linker editoru, tj. kompilátor příslušné informace předá,
ale jsou používány tak často, že jsou vloženy i do tohoto slajdu.
• kompilátor a linker mají mnoho dalších přepínačů ovlivňujících generovaný
kód, vypisování varovných hlášení nebo variantu jazyka (K&R/ANSI). Je
třeba nastudovat dokumentaci konkrétního produktu.

23

Předdefinovaná makra
__FILE__, __LINE__, __DATE__, __TIME__, __cplusplus, apod.
jsou standardní makra kompilátoru C/C++
unix
vždy definováno v Unixu
mips, i386, sparc
hardwarová architektura
linux, sgi, sun, bsd
klon operačního systému
_POSIX_SOURCE, _XOPEN_SOURCE
překlad podle příslušné normy
pro překlad podle určité normy by před prvním #include měl být řádek
s definicí makra:
UNIX 98

#define _XOPEN_SOURCE 500

SUSv3

#define _XOPEN_SOURCE 600

POSIX

#define _POSIX_C_SOURCE 200112L

v dokumentaci konkrétního kompilátoru je možné najít, která další makra se
používají. Množství maker je definováno také v systémových hlavičkových souborech.

24

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

• pozor na to, že na různých systémech se některé přepínače mohou lišit, například ldd na Solarisu nezná přepínače -shared a -non shared, je nutné
použít jiné
• u malých programů (v jednom souboru) lze provést překlad a linkování jedním
příkazem cc. U větších programů skládajících se z mnoha zdrojových souborů
a knihoven se obvykle odděluje překlad a linkování a celý proces je řízen
utilitou make.

25

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
main.o
:
main.c util.h
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

• závislosti

• program je možné také přeložit a slinkovat jedním voláním kompilátoru, nebo
definovat postup překladu a linkování pomocí shellového skriptu. Důvodem
pro použití make je to, že vyhodnocuje závislosti mezi soubory a po změně
některého zdrojového souboru překládá jenom to, co na něm závisí. Častý
způsob překladu softwaru po aplikování změn způsobem „make clean; make
allÿ je v situaci, kdy celý překlad trvá minuty (desítky minut, hodiny. . . ),
trochu nevhodný – právě proto je důležité mít dobře napsaný Makefile.
• řádek „prog : main.o util.oÿ definuje, že se má nejprve rekurzivně zajistit
existence a aktuálnost souborů main.o a util.o. Pak se zkontroluje, zda
soubor (cíl) prog existuje a je aktuální (datum poslední modifikace souboru
je mladší než main.o a util.o). Pokud ano, nedělá se nic. Když ne, provede
se příkaz na následujícím řádku.
• make se spouští typicky s parametrem určující příšlušný cíl (target); při spuštění bez parametrů se vezme první target. Ten typicky bývá all, což většinou
podle unixové konvence přeloží vše, co se přeložit má. Následuje pak třeba
zavolání make s parametrem install apod.
• make je samozřejmě univerzální nástroj, použitelný i jinde než u překladů

26

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

• pozor na to, že řádek s příkazem začíná tabulátorem, nikoliv mezerami. Každý příkazový řádek se provádí samostatným shellem, pokud je
potřeba provést více řádků pomocí jednoho shellu, musí se všechny až na poslední ukončit backslashem (shell je dostane jako jeden řádek). Viz příklad,
ve kterém dva poslední echo příkazy jsou součástí jednoho if příkazu, který
je spuštěn samostatným shellem:
jp@sarrix:~/src/make$ cat Makefile
# Makefile test
all:
@echo $$$$
@echo $$$$
@if true; then \
echo $$$$; \
echo $$$$; \
fi
jp@sarrix:~/src/make$ make
5513
5514
5515
5515
• zdvojením $ se potlačí speciální význam dolaru (viz následující slajd)
• znak @ na začátku řádku potlačí jeho výpis – make jinak standardně vypisuje
nejdříve to, co bude vykonávat.

27

• znak - na začátku řádku způsobí ignorování nenulové návratové hodnoty;
jinak make vždy v takové situaci zahlásí chyby a okamžitě skončí.

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

• když je stejné makro definováno vícekrát, platí poslední definice.
• makra by se neměla definovat rekurzivně, toto často nefunguje, v závislosti
na použitém make, je vhodné se tomu úplně vyhnout:
M=value1
M=$(M) value2
• často se používají různé rozšířené verze make (např. GNU, BSD), které umí,
podmíněné sekce v Makefile, redefinice proměnných, apod.
• všechny příkazy make většinou podporují zpětné uvozovky pro vkládání výstupu příkazu do proměnné. Pro jednoduchý podmínečný překlad v závislosti
na systému a kde se dají očekávat různé verze příkazu make, je možné použít
například toto:
CFLAGS=‘x=\‘uname\‘; \
if [ $${x} = FreeBSD ]; then \
echo ’-Wall’; \
elif [ $${x} = SunOS ]; then \
echo ’-v’; \
elif [ $${x} = Linux ]; then \
echo ’-Wall -g’; \
fi‘
all:
@echo "$(CFLAGS)"
28

• v ostatních situacích je vhodné, případně nezbytné použít programy typu
autoconf nebo automake
• make je velmi silný nástroj, stačí se podívat do systémových Makefile souborů jakéhokoli Unixového systému. Typickou společnou vlastností je to, že
neexistuje dokumentace jak je daný makefile framework postaven.

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

• základní řádkový symbolický debugger, aby bylo možné ho plně využít, musí
být program přeložen s ladicími informacemi (cc -g). Laděný program se
startuje z debuggeru příkazem run, nebo se debugger připojí k již běžícímu
procesu. Pomocí dbx lze analyzovat i havarovaný program, který vygeneroval
soubor core.
• je možné ho najít např. na Solarisu, na Linuxu a FreeBSD defaultně není.

29

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

• GNU řádkový debugger, obdoba dbx
• na různých platformách existují i debuggery s grafickým rozhraním, např.
debugger (Solaris), cvd (IRIX), xxgdb (GNU), ddd (GNU). Často fungují
jako nadstavby nad dbx, gdb.
• #include <stdio.h>
int main(void) {
printf("hello, world\n");
return 0;
}
jp@sarrix:~/src/gdb$ cc -g main.c
jp@sarrix:~/src/gdb$ gdb -q a.out
(gdb) break main
Breakpoint 1 at 0x8048548: file main.c, line 4.
(gdb) run
Starting program: /share/home/jp/src/gdb/a.out
Breakpoint 1, main () at main.c:4
4
printf("hello, world\n");
(gdb) next
hello, world
5
return 0;
(gdb) c
Continuing.
Program exited normally.
(gdb) q

30

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

• tyto headery nejsou specifické pro UNIX, jsou součástí standardu ANSI C (a
který je součástí POSIX.1).
• příslušný hlavičkový soubor pro konkrétní funkci najdete v manuálové stránce
dané funkce
• jednotlivá makra obsažená v těchto souborech tam většinou nejsou vysvětlena, co znamená které makro je možné si vyhledat v příslušných specifikacích, které jsou on-line.
• makro assert() je možné z během kompilace odstranit pomocí makra NDEBUG

31

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

Tyto headery už patří do UNIXu.

32

Standardní hlavičkové soubory (3)
semaphore.h

...

semafory (POSIX)

pthread.h

...

vlákna (POSIX threads)

sys/socket.h

...

síťová komunikace

arpa/inet.h

...

manipulace se síťovými adresami

sys/ipc.h

...

společné deklarace pro System V IPC

sys/shm.h

...

sdílená paměť (System V)

sys/msg.h

...

fronty zpráv (System V)

sys/sem.h

...

semafory (System V)

Dokončení nejdůležitějších UNIXových headerů. Existují samozřejmě ještě další.

33

Funkce main()
• při spuštění programu je předáno řízení funkci main().
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

"ls"
"-l"
"/"

• první parametr (typu int) udává počet argumentů na příkazovém řádku
(včetně parametru 0 – jména programu) a druhý parametr (typu char**) je
pole ukazatelů na tyto řetězce. Za posledním řetězcem je ještě NULL pointer.
• při spuštění programu je z inicializačního kódu standardní knihovny předáno řízení funkci main(). Její nepřítomnost v programu způsobí chybu na
úrovni linkeru. Této funkci se předá jméno spuštěného programu, argumenty
z příkazové řádky a proměnné prostředí. Ukončení této funkce znamená konec programu a návratová hodnota se použije jako kód ukončení programu
pro OS. Jinou možností ukončení programu je použití funkce exit() nebo
_exit(), kterou lze použít kdykoliv, nejen ve funkci main(). V C lze používat
obě metody ukončení programu.
• návratový typ funkce main by měl být vždy int; překladač si jinak bude
stěžovat.
• rozdíl mezi funkcemi exit() a _exit() je v tom, že exit() před ukončením programu ještě zavře streamy stdio a volá funkce zaregistrované pomocí
atexit(). V závislosti na systému to mohou být i další akce.
• například ve FreeBSD je exit() systémové volání, exit() knihovní funkce.
V Solarisu jsou obě systémová volání.
• startování dynamicky linkovaných programů je složitější, protože loader (dynamický linker) musí za běhu programu hledat a přilinkovat sdílené knihovny.
• pozor na to, že na rozdíl od jazyka C návratová hodnota 0 má v shellu význam
true (úspěch) a nenula význam false (neúspěch).
• varianta main() s proměnnými prostředí:
int main(int argc, char *argv [], char *envp ); vypadá takto:
34

Proměnné prostředí
• seznam všech proměnných prostředí (environment variables) se
předává jako proměnná
extern char **environ;
• je to pole ukazatelů (ukončené NULL) na řetězce ve tvaru:
proměnná =hodnota
environ
environ[0]
environ[1]
environ[2]
environ[3]

"SHELL=/bin/bash"
"DISPLAY=:0"
"LOGNAME=beran"

• shell předává spuštěnému programu ty proměnné, které jsou označeny jako
exportované (na příklad v Bourne shellu příkazem export variable ).
• po změně obsahu již jednou exportované proměnné samozřejmě není potřeba
proměnnou znovu exportovat
• při nahrazení aktuálního obrazu procesu obrazem jiným se předává, pokud
se neřekne jinak, synovským procesům celé pole environ automaticky. Je
možné ve volání příslušné varianty funkce exec předat pole jiné.
• jaké proměnné prostředí konkrétní příkaz používá (a jak je používá) by mělo
být v manuálové stránce. Typicky v sekci nazvané ENVIRONMENT nebo
ENVIRONMENT VARIABLES
• man například používá PAGER, vipw pak proměnnou EDITOR atd.

35

Manipulace s proměnnými prostředí
• je možné přímo změnit proměnnou environ
• char *getenv (const char *name );
– vrátí hodnotu proměnné name
• int putenv (char *string );
– vloží string ve tvaru jméno =hodnota do prostředí (přidá novou
nebo modifikuje existující proměnnou)
• změny se přenášejí do synovských procesů
• změny v prostředí syna samozřejmě prostředí otce neovlivní
• existují i funkce setenv() a unsetenv()

• důležité je zapamatovat si, že synovský proces zdědí v okamžiku svého vzniku
od rodiče všechny proměnné prostředí, ale jakákoliv manipulace s nimi v
synovi je lokální a do otce se nepřenáší. Každý proces má svou kopii proměnných, proto ani následná změna prostředí otce po vytvoření syna nemění
proměnné syna.
• rozdíl mezi putenv a setenv je ten, že v setenv mohu definovat, zda existující
proměnnou chci nebo nechci přepsat. putenv vždy přepisuje.
• #include <stdio.h>
#include <stdlib.h>
int main(void)
{
printf("%s\n", getenv("USER"));
return 0;
}
jp@sarrix:~/src/environ$ ./a.out
jp

36

Zpracování argumentů programu
• obvyklý zápis v shellu: program -přepínače argumenty
• přepínače tvaru -x nebo -x hodnota , kde x je jedno písmeno nebo
číslice, hodnota je libovolný řetězec
• několik přepínačů lze sloučit dohromady: ls -lRa
• argument ‘ --‘ nebo první argument nezačínající ‘ -‘ ukončuje
přepínače, následující argumenty nejsou považovány za přepínače, i
když začínají znakem ‘ -‘ .
• tento tvar argumentů požaduje norma a lze je zpracovávat
automaticky funkcí getopt().

• argumenty lze samozřejmě zpracovávat vlastní funkcí, ale standardní funkce
je pohodlnější.
• argumenty se typicky mohou opakovat, ale to má smysl jen v některých situacích
• pořadí přepínačů může být důležité a je na aplikaci, aby toto specifikovala
• UNIX norma definuje pomocí 13 pravidel velmi přesně, jak by měly vypadat názvy příkazů a formát přepínačů. Například jméno příkazu by mělo být
pouze malými písmeny, dlouhé 2–9 znaků, z přenositelné znakové sady. Přepínače bez argumentů by mělo být možné dát do skupiny za jedním znakem
‘ –‘ . Atd.
• někdy můžete narazit na upozornění, že používat číslice jako přepínače je
zastaralé; ani norma UNIX 03 však o tom nemluví.
• pozor na Linux a jeho (poněkud zvláštní a nestandardní) permutování argumentů (viz další slidy).

37

Zpracování přepínačů: getopt()
int getopt(int argc, char *const argv [],
const char *optstring );
extern char *optarg ;
extern int optind, opterr, optopt ;
• funkce dostane parametry z příkazového řádku, při každém volání
zpracuje a vrátí další přepínač. Pokud má přepínač hodnotu, vrátí ji
v optarg.
• když jsou vyčerpány všechny přepínače, vrátí -1 a v optind je číslo
prvního nezpracovaného argumentu.
• možné přepínače jsou zadány v optstring, když za znakem
přepínače následuje ‘ :‘ , má přepínač povinnou hodnotu.
• při chybě (neznámý přepínač, chybí hodnota) vrátí ‘ ?‘ , uloží znak
přepínače do optopt a když opterr nebylo nastaveno na nulu,
vypíše chybové hlášení.

• obvykle se nejprve pomocí getopt() načtou přepínače a pak se vlastními
prostředky zpracují ostatní argumenty (často jsou to jména souborů).

38

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

• dobrým zvykem je při detekování neznámého přepínače (nebo obecně špatného zápisu parametrů programu) vypsat stručnou nápovědu (případně s
odkazem na podrobnější dokumentaci) a ukončit program s chybou, tj. s
nenulovou návratovou hodnotou.
• příklad také ukazuje nebezpečné použití funkce strcpy()
• z použití funkce getopt() je vidět, že je stavová. Zpracovat další pole argumentů, případně znovuzpracovat původní, je možné nastavením externí
proměnné optreset na 1.
• standardní getopt() zachová pořadí přepínačů při zpracování
• při použití nedefinovaného přepínače funkce vypíše chybu; to lze potlačit
nastavením opterror na 1.

39

Dlouhý tvar přepínačů
• poprvé se objevilo v GNU knihovně libiberty:
--jméno nebo --jméno=hodnota
• argumenty se permutují tak, aby přepínače byly na začátku, např.
ls * -l je totéž jako ls -l *, standardní chování lze docílit
nastavením proměnné POSIXLY_CORRECT.
• zpracovávají se funkcí getopt long(), která používá pole struktur
popisujících jednotlivé přepínače:
struct option {
const char *name; /* jméno přepínače */
int has arg; /* hodnota: ano, ne, volitelně */
int *flag; /* když je NULL, funkce vrací val, jinak vrací 0
a dá val do *flag */
int val; /* návratová hodnota */
};

verze jak se objevila ve FreeBSD (funkce getopt long() není standarizovaná):
• pokud všechny dlouhé přepínače mají nastaveny krátkou variantu ve val, je
chování getopt long() kompatibilní s getopt()
• je možné zadávat argument k dlouhému přepínači i s mezerou (--color green)
• pokud je nastaven flag, tak getopt long() vrací 0, čímž se tyto dlouhé přepínače bez krátké varianty zpracují v jedné větvi příkazu case
• existuje i volání getopt long only(), které povoluje i dlouhé přepínače uvozené jednou uvozovkou (-option)
• funkci getopt long() je možné používat dvěmi způsoby. První způsob je, že
každý dlouhý přepínač má korespondující krátký – takto lze jednoduše přidat
dlouhé přepínače do existujícího programu a je kompatibilní s getopt.
Druhý způsob umožňuje mít samostatné dlouhé přepínače. V tom případě
funkce vrací vždy 0 (nekompatibilita s getopt) a proměnná *flag se nastaví
na val.
• na konkrétním příkladu na následující stránce je vidět, jak to celé funguje

40

Dlouhé přepínače (pokračování)
int getopt long(int argc, char * const argv [],
const char *optstring,
const struct option *longopts,
int *longindex );
• optstring obsahuje jednopísmenné přepínače, longopts obsahuje
adresu pole struktur pro dlouhé přepínače (poslední záznam pole
obsahuje samé nuly)
• pokud funkce narazí na dlouhý přepínač, vrací odpovídající val nebo
nulu (pokud flag nebyl NULL), jinak je chování shodné s getopt().
• do *longindex (když není NULL) dá navíc index nalezeného
přepínače v longopts.

• toto je upravený příklad z manuálové stránky na FreeBSD:
#include <stdio.h>
#include <getopt.h>
#include <fcntl.h>
int ch, fd, daggerset, bflag = 0;
static struct option longopts[] = {
{ "buffy",
no_argument,
{ "fluoride",
required_argument,
{ "daggerset", no_argument,
{ NULL,
0,

NULL,
NULL,
&daggerset,
NULL,

’b’ },
’f’ },
1 },
0 }};

int main(int argc, char **argv)
{
while ((ch = getopt_long(argc, argv, "bf:", longopts, NULL)) != -1)
switch (ch) {
case ’b’:
bflag = 1; break;
case ’f’:
if ((fd = open(optarg, O_RDONLY, 0)) == -1)
printf("unable to open %s", optarg);
break;
case 0:
if (daggerset) {
printf("Buffy will use her dagger to "
"apply fluoride to dracula’s teeth\n");
}
break;
default: printf("usage: ...\n");
}
argc -= optind; argv += optind;
return 0;
}

41

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

IPC
plánovač
přidělování
paměti

strojově závislá vrstva ovládání hardware
hardware

• toto schéma je převzato z [Bach86], viz literatura. Zdůrazňuje dva ústřední
pojmy v modelu systému UNIX – soubory a procesy. V praxi se jádro od
modelu typicky odlišuje, ale zde je důležitá základní představa.
• UNIX rozlišuje dva režimy běhu procesoru: uživatelský režim a režim jádra. V uživatelském režimu nejsou přístupné privilegované instrukce (např.
mapování paměti, I/O, maskování přerušení). Tyto dva režimy musí být podporovány na hardwarové úrovni (procesorem).
• procesy běží obvykle v uživatelském režimu, do režimu jádra přechází buď
instrukcí synchronního přerušení (trap) pro volání služby jádra, nebo na základě asynchronních přerušení (hodiny, I/O). Dále se v režimu jádra ošetřují
výjimečné stavy procesoru (výpadek stránky, narušení ochrany paměti, neznámá instrukce apod.). Některé speciální akce jsou zajišťovány systémovými
procesy, které běží celou dobu v režimu jádra.
• klasické UNIXové jádro je tvořeno monolitickým kódem. Původně bylo potřeba vygenerovat (tj. přeložit ze zdrojových textů a slinkovat) jádro při
změně některého parametru nebo přidání ovladače zařízení. V novějších implementacích je možno nastavovat parametry jádra, někdy i za běhu, pomocí
systémových utilit bez nutnosti rekompilace jádra. Moderní UNIXy umožňují
rozšiřovat kód jádra za běhu pomocí tzv. modulů jádra (loadable kernel modules). Například systém FreeBSD 5.4-RELEASE má 392 takových modulů.
• existují dva způsoby práce s perifériemi: bloková (block devices) a znaková
zařízení (character, raw devices). Data z blokových zařízení (např. disky) procházejí přes vyrovnávací paměti (buffers) po blocích, znaková zařízení (např.
terminály) umožňují pracovat s jednotlivými bajty a nepoužívají vyrovnávací
paměť.
42

Procesy, vlákna, programy
• proces . . . systémový objekt charakterizovaný svým kontextem,
identifikovaný jednoznačným číslem (process ID, PID); jinými slovy
„kód a data v pamětiÿ
• vlákno (thread) . . . systémový objekt, který existuje uvnitř procesu
a je charakterizován svým stavem. Všechna vlákna jednoho procesu
sdílí stejný paměťový prostor kromě registrů procesoru a zásobníku
(automatických proměnných); „linie výpočtuÿ, „to, co běžíÿ
• program . . . soubor přesně definovaného formátu obsahující
instrukce, data a služební informace nutné ke spuštění; „spustitelný
soubor na diskuÿ
◦ paměť se přiděluje procesům.
◦ procesory se přidělují vláknům.
◦ vlákna jednoho procesu mohou běžet na různých procesorech.

• kontext je paměťový prostor procesu, obsah registrů a datové struktury jádra
týkající se daného procesu
• jinak – kontext procesu je jeho stav. Když systém vykonává proces, říká se,
že běží v kontextu procesu. Jádro (klasické) obsluhuje přerušení v kontextu
přerušeného procesu.
• vlákna se dostala do UNIXu až později, původně v něm existovaly pouze
procesy (s jediným hlavním vláknem). Možnost použít v procesu více vláken
byla zavedena, protože se ukázalo, že je vhodné mít více paralelních linií
výpočtu nad sdílenými daty.
• paměťové prostory procesů jsou navzájem izolované, ale procesy spolu mohou
komunikovat (později se dozvíme, že mohou i částečně sdílet paměť).
• procesy jsou entity na úrovni jádra, vlákna mohou být částečně nebo zcela
implementována knihovními funkcemi (tj. vlákna nemusí jádro vůbec podporovat). S vlákny je spojena menší režie než s procesy.
• systémový proces, který běží na pozadí obvykle po celou dobu běhu systému
a zajišťuje některé systémové služby (inetd, cron, sendmail. . . ) se nazývá
démon (angl. daemon). Systém BSD tedy nemá ve znaku čerta, ale démona.

43

Jádro, režimy, přerušení (klasický UNIX)
• procesy typicky běží v uživatelském režimu
• systémové volání způsobí přepnutí do režimu jádra
• proces má pro každý režim samostatný zásobník
• jádro je částí každého uživatelského procesu, není to samostný
proces (procesy)
• přepnutí na jiný proces se nazývá přepnutí kontextu
• obsluha přerušení se provádí v kontextu přerušeného procesu
• jádro je nepreemptivní

• raději ještě jednou: jádro není oddělená množina procesů, běžících
paralelně s uživatelskými procesy, ale je částí každého uživatelského
procesu.
• přechod mezi uživatelským režimem a režimem jádra není přepnutí kontextu
– proces běží pořád v tom samém
• přerušený proces nemusel přerušení vůbec způsobit
• v režimu jádra může proces přistupovat i k adresám jádra, která z uživatelského režimu přístupná nejsou; taktéž může přistupovat k instrukcím (např.
instrukce manipulující se stavovým registrem), jejichž vykonání v uživatelském režimu vede k chybě
• přerušovací rutina se nemůže zablokovat, protože tím by zablokovala proces;
proces se totiž může zablokovat jen ze své vlastní vůle. Moderní Unixy dnes
používají interrupt vlákna, v jejichž kontextu se mohou drivery zablokovat.
• to, že klasické unixové jádro je nepreemptivní znamená, že jeden proces
nemůže zablokovat jiný proces
• při obsluze přerušení se může stát, že nastane další přerušení. Pokud je jeho
priorita větší, je procesorem přijmuto. Posloupnost přijmutých přerušení je
uchována v zásobníku kontextových vrstev.
• u moderních kernelů je situace často velmi rozdílná – obsluha přerušení, preeptivnost kernelu atd.; k některým věcem se možná dostaneme později během semestru

44

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

• pokud unixový proces vyžaduje provedení systémové služby, pomocí systémového volání předá řízení jádru. Jádro je kus kódu sdílený všemi procesy
(ovšem přístupný jen pro ty, které jsou právě v režimu jádra). Jádro tedy
není samostatný privilegovaný proces, ale vždy běží v rámci některého procesu (toho, který požádal jádro o službu, nebo toho, který běžel v okamžiku
příchodu přerušení).
• komunikace mezi procesy v UNIXu je řešena pomocí systémových volání, je
tedy zprostředkovaná jádrem.
• aby to nebylo tak jednoduché, mohou existovat systémové procesy (označované jako kernel threads), které běží celou dobu v režimu jádra, tj. nemají
uživatelský kód. Naprostá většina systémových procesů však běží v uživatelském režimu a liší se jen tím, že mají větší přístupová práva. Plánovač procesů
přepíná mezi procesy a tím umožňuje běh více procesů současně i na jednom
procesoru. Na multiprocesorových počítačích pak funguje skutečný paralelismus procesů a vláken (dokonce se proces může při přeplánování dostat i na
jiný procesor).
• v distribuovaném operačním systému má jádro obvykle formu mikrojádra, tj.
zajišťuje pouze nejzákladnější služby řízení procesoru, přidělování paměti a
komunikace mezi procesy. Vyšší systémové služby, které jsou v UNIXu součástí jádra (např. přístup k systému souborů) jsou realizovány speciálními
procesy (servery) běžícími v uživatelském režimu procesoru. Jádro předá požadavek uživatelského procesu příslušnému serveru, který může běžet i na
jiném uzlu sítě.
• dostupných mikrokernelů je v dnešní době mnoho. Můžete zkusit například
45

Minix (unix-like výukový systém), případně systém HURD, který běží nad
mikrojádrem Mach.

Systémová volání, funkce
• v UNIXu se rozlišují systémová volání a knihovní funkce. Toto
rozlišení dodržují i manuálové stránky: sekce 2 obsahuje systémová
volání (syscalls), sekce 3 knihovní funkce (library functions).
– knihovní funkce se vykonávají v uživatelském režimu, stejně jako
ostatní kód programu.
– systémová volání mají také tvar volání funkce. Příslušná funkce
ale pouze dohodnutým způsobem zpracuje argumenty volání a
předá řízení jádru pomocí instrukce synchronního přerušení. Po
návratu z jádra funkce upraví výsledek a předá ho volajícímu.
• standardy tyto dvě kategorie nerozlišují, protože z hlediska
programátora je jedno, jestli určitou funkci provede jádro nebo
knihovna.

• zjednodušeně lze říci, že systémové volání je funkce, která jen upraví své argumenty do vhodné podoby, přepne režim procesoru a skutečnou práci nechá na
jádru. Nakonec zase upraví výsledek. Knihovní funkce může a nemusí volat
jádro, ale vždy sama dělá nějakou netriviální činnost v uživatelském režimu.
• v assembleru je možné zavolat volání jádra přímo
• API jádra je definované na úrovni volání funkcí standardní knihovny, nikoliv
na úrovni přerušení a datových struktur používaných těmito funkcemi pro
předání řízení jádru. Mechanismus přepnutí mezi uživatelským režimem a
režimem jádra se totiž může lišit nejen v závislosti na hardwarové platformě,
ale i mezi různými verzemi systému na stejném hardwaru.

46

Návratové hodnoty systémových volání
• celočíselná návratová hodnota (int, pid t, off t, apod.)
– >= 0 . . . operace úspěšně provedena
– == -1 . . . chyba
• návratová hodnota typu ukazatel
– != NULL . . . operace úspěšně provedena
– == NULL . . . chyba
• po neúspěšném systémovém volání je kód chyby v globální proměnné
extern int errno;
• úspěšné volání nemění hodnotu v errno! Je tedy třeba nejprve
otestovat návratovou hodnotu a pak teprve errno.
• chybové hlášení podle hodnoty v errno vypíše funkce
void perror(const char *s );
• textový popis chyby s daným číslem vrátí funkce
char *strerror(int errnum );

• úspěšnost funkcí ze stdio.h je třeba testovat pomocí
int ferror(FILE *stream );
• funkce pro práci s vlákny pthread *() nenastavují errno, ale vrací buď nulu
(úspěch) nebo přímo kód chyby.
• pro některá volání může mít smysl i návratová hodnota -1. Pak je třeba
nejprve nastavit errno = 0 a po návratu zkontrolovat, zda se errno změnilo.
Např. funkce strtol() vrací při chybě 0, což je platná hodnota i pro správný
výsledek (a −1 je samozřejmě platný výsledek také).
• je tedy vždy nutné si přečíst manuálovou stránku pro příšlušné volání nebo
knihovní funkci

47

Uživatelé a skupiny
beran:x:1205:106:Martin Beran:/home/beran:/bin/bash
význam jednotlivých polí: uživatelské jméno, zakódované heslo (nově v
/etc/shadow), číslo uživatele (UID); superuživatel (root) má UID 0,
číslo primární skupiny (GID), plné jméno, domovský adresář, login-shell
sisal:*:106:forst,beran
význam jednotlivých polí: jméno skupiny, heslo pro přepnutí do
skupiny, číslo skupiny (GID), seznam členů skupiny

• informace o uživatelích v souborech /etc/passwd, /etc/shadow a /etc/group
jsou zpracovávány různými systémovými programy, např. login (přihlášení
do systému na základě uživatelského jména a hesla) nebo su (změna identity).
Jádro o těchto souborech nic neví, používá pouze numerickou identifikace uživatele a skupiny.
• některé systémy uchovávají informace o uživatelích jinak. Např. na FreeBSD
se soubor /etc/passwd (bez hesel) generuje ze souboru /etc/master.passwd,
který obsahuje i zakódovaná hesla a není přístupný pro běžné uživatele.
• existují i jiné systémy, které (nejen) pro autentizaci /etc/passwd nemusí
vůbec používat, například NIS (Network Information Service).
• skupina uživatele uvedená v /etc/passwd je primární. Tuto skupinovou identifikaci dostanou např. soubory vytvořené procesy uživatele. Další skupiny,
ve kterých je uživatel uveden v souboru /etc/group, jsou doplňkové (supplementary) a rozšiřují přístupová práva uživatele: skupinový přístup je povolen
ke všem objektům, jejichž skupinový vlastník je roven buď primární, nebo
jedné z doplňkových skupin.
• původně měl v UNIXu každý uživatel vždy aktivní pouze jednu skupinovou
identitu. Po nalogování byl ve své primární skupině, pro získání práv jiné
skupiny bylo třeba se do ní přepnout příkazem newgrp (skupinová obdoba
su, řídí se obsahem souboru /etc/group), který spustil nový shell.
• v novějších UNIXech není třeba pro přístup k souborům měnit primární skupinovou identitu procesu, pokud uživatel patří do potřebné skupiny. Změna
identity je nutná, pouze když chceme vytvářet soubory s jinou skupinovou
identitou než je primární skupina uživatele. Lokálně pro určitý adresář toho

48

lze dosáhnout nastavením skupinového vlastníka adresáře na požadovanou
skupinu a nastavením bitu SGID v přístupových právech adresáře – to platí
pro systémy založené na System V. U BSD stačí změnit požadovanou skupinu
u adresáře.
• druhá položka v řádcích /etc/group obsahuje zakódované skupinové heslo
používané příkazem newgrp, to se již dnes nepoužívá. Například na FreeBSD
je příkaz newgrp přístupný už jen superuživateli (kvůli volání setgroups).

Name service switch
• dnešní systémy nejsou omezeny na používání /etc/passwd a
/etc/groups
• systém používá databáze (passwd, groups, services, protocols, . . . )
• data databází pocházejí ze zdrojů (soubory, DNS, NIS, LDAP, . . . )
• soubor nsswitch.conf definuje jaké databáze používají jaké zdroje
• knihovní funkce toto samozřejmě musí explicitně podporovat
• je možné některé zdroje kombinovat, například uživatel se nejdříve
může hledat v /etc/passwd a poté v NISu
• poprvé se objevilo v Solarisu, další systémy pak tuto myšlenku
převzalo

• systémy mají typicky manuálovou stránku nsswitch.conf(5), kde lze nalézt
podrobnosti v závislosti na konkrétním operačním systému
• zde je část skutečného souboru nsswitch.conf ze stroje u-us:
passwd:
group:

files ldap
files ldap

# You must also set up the /etc/resolv.conf file for DNS name
# server lookup. See resolv.conf(4).
hosts:
files dns
# Note that IPv4 addresses are searched for in all of the
# ipnodes databases before searching the hosts databases.
ipnodes:
files dns
networks:
files
protocols: files
rpc:
files
ethers:
files
49

Testování přístupových práv
• uživatel je identifikován číslem uživatele (UID) a čísly skupin, do
kterých patří (primary GID, supplementary GIDs).
• tuto identifikaci dědí každý proces daného uživatele.
• soubor S má vlastníka (U IDS ) a skupinového vlastníka (GIDS ).
• algoritmus testování přístupových práv pro proces
P (U IDP , GIDP , SU P G) a soubor S(U IDS , GIDS ):
Jestliže

P má vůči S

if(U IDP == 0)

. . . všechna práva

else if(U IDP == U IDS )

. . . práva vlastníka

else if(GIDP == GIDS ||
. . . práva člena skupiny

GIDS ∈ SU P G)

. . . práva ostatních

else

• procesy superuživatele root mohou měnit svoji uživatelskou a skupinovou
identitu. Toho využívá např. proces login, který běží jako root a po zkontrolování jména a hesla spustí shell s uživatelskou identitou (pomocí volání
setuid() – viz další slajdy).
• z algoritmu plyne, že pro roota není relevantní nastavení práv (má vždy
neomezený přístup). Pokud se shoduje uživatel, nepoužijí se nikdy práva
skupiny nebo ostatních, i když povolují více než uživatelská práva. Podobně
práva ostatních se nepoužijí, jestliže se shoduje skupinová identita. Tedy pokud má můj soubor nastaveny práva ---rwxrwx, nemohu ho číst, zapisovat
ani spustit (dokud nastavení práv nezměním).
• některé systémy se odklánějí od klasického modelu, kdy mnoho procesů běželo
pod uživatelem s UID 0 a při bezpečnostní chybě v takové aplikaci často
útočník získal vládu nad celým systémem a zavádějí modely jako je least
privilege model v Solarisu 10, systrace v OpenBSD, . . .

50

Reálné a efektivní UID/GID
• u každého procesu se rozlišuje:
– reálné UID (RUID) – který uživatel je skutečným vlastníkem
procesu
– efektivní UID (EUID) – uživatel, jehož práva proces používá
• podobně se rozlišuje reálné a efektivní GID procesu.
• obvykle platí RUID==EUID && RGID==EGID.
• propůjčování práv . . . spuštění programu s nastaveným SUID (set
user ID) bitem změní EUID procesu na UID vlastníka programu,
RUID se nezmění.
• podobně SGID bit ovlivňuje EGID procesu.
• při kontrole přístupových práv se používají vždy EUID, EGID a
supplementary GIDs.

• bity SUID a SGID se používají u programů, které potřebují větší přístupová
práva, než má uživatel, jenž je spouští. Příkladem je program passwd, který
musí aktualizovat soubory /etc/passwd a /etc/shadow, které běžný uživatel
nemůže měnit a druhý z nich ani číst. Další příklad je program su. Ten
musí mít právo libovolně změnit uživatelskou a skupinovou identitu, což je
privilegium procesů s UID 0. Jiným příkladem je příkaz ping, který musí
získat přístup k raw socketu (bude později).
• SUID a SGID programy by měly být pečlivě naprogramovány, aby dovolily
pouze ty operace, pro které jsou určeny, a neumožnily zneužít jejich privilegia
pro neoprávněné akce (např. spuštění rootovského shellu). Zkušenost ukazuje,
že tyto programy jsou jednou z nejčastějších příčin bezpečnostích problémů
UNIXových systémů.
• základním pravidlem pro SUID programy je: nepište je. Pokud je to nevyhnutelné, měli byste opravdu vědět, co děláte. Pokud nevíte co je tím myšleno,
použijte základní pravidlo.

51

Identifikace vlastníka procesu
• uid t getuid(void)
vrací reálné user ID volajícího procesu.
• uid t geteuid(void)
vrací efektivní user ID volajícího procesu.
• gid t getgid(void)
vrací reálné group ID volajícího procesu.
• gid t getegid(void)
vrací efektivní group ID volajícího procesu.
• int getgroups(int gidsz, gid t glist [])
– do glist dá nejvýše gidsz supplementary group IDs volajícího
procesu a vrátí počet všech GIDs procesu.

• getgroups(): když gidsz == 0, jen vrátí počet skupin. Když 0 < gidsz <
#skupin, vrátí -1.
• v UNIXu je mnoho typů jako uid_t, gid_t, size_t, apod. Vesměs jsou to
celočíselné typy, často je najdete v /usr/include/sys/types.h

52

Změna vlastníka procesu
• int setuid(uid t uid );
– v procesu s EUID == 0 nastaví RUID i EUID na uid.
– pro ostatní procesy nastavuje jen EUID, a uid musí být buď
rovné RUID, nebo původní hodnotě EUID procesu, která je
uschovaná jako saved set-user-ID.
• int setgid(gid t gid );
obdoba setuid(), nastavuje group-IDs procesu.
• int setgroups(int ngroups, gid t *gidset ); nastavuje
supplementary GIDs procesu, může být použito jen
superuživatelským procesem.

• proces s efektivními právy superuživatele může libovolně měnit identitu.
Ostatní procesory mohou pouze střídat svá reálná a efektivní práva.
• program login využívá volání setuid()
• pokud chce process s UID == 0 změnit svou identitu, musí nejprve volat
setgid() a setgroups(). Teprve pak lze zavolat setuid(). Při opačném
pořadí volání by proces po provedení setuid už neměl práva na setgid() a
setgroups().
• setgroups() není uvedeno v UNIX 98 ani UNIX 03.
• RUID/EUID jsou uložené v záznamu tabulky procesů pro příslušný proces
a zároveň v tzv. u-area (viz například [Bach]). EUID v tabulce procesů se
nazývá uschované EUID, neboli saved UID. Uschované UID se používá pro
kontrolu, když se proces chce vrátit k EUID, se kterým byl spuštěn (po té,
co dočasně nastavil své EUID na UID uživatele, který proces spustil, tj. na
RUID).

53

Systém souborů
• adresáře tvoří strom, spolu se soubory acyklický graf (na jeden
soubor může existovat více odkazů).
• každý adresář navíc obsahuje odkaz na sebe ‘ .‘ (tečka) a na
nadřazený adresář ‘ ..‘ (dvě tečky).
• pomocí rozhraní systému souborů se přistupuje i k dalším entitám
v systému:
– periferní zařízení
– pojmenované roury
– sokety
– procesy (/proc)
– paměť (/dev/mem, /dev/kmem)
– pseudosoubory (/dev/tty, /dev/fd/0,. . . )

• z pohledu jádra je každý obyčejný soubor pole bajtů.
• všechny (i síťové) disky jsou zapojeny do jednoho stromu.

• root může v některých unixech zacyklit strukturu adresářů, ale tím zmate utility pro procházení filesystému. Symbolické linky na adresáře fungují všude.
• pojmenované roury lze použít i mezi procesy, které nejsou příbuznensky spřízněné. Jinak fungují stejně jako nepojmenované roury.
• zmiňované sokety jsou v doméně UNIX, tj. slouží pro komunikaci v rámci
jednoho systému. Sokety z domény INET (přes ně probíhá síťová komunikace)
se v systému souborů neobjevují.
• debuggery používají paměťové obrazy procesů dostupné v /proc. Např. v Linuxu a FreeBSD obsahuje podstrom /proc údaje o jádru systému a běžících
procesech ve formě textových souborů.
• dnešní moderní unixy mívají speciální filesystém devfs, jehož obsah odráží
aktuální konfiguraci systému co se týče připojených zařízení. Tj. např. při
připojení USB sticku se v /dev objeví příslušné diskové zařízení. Po odpojení
toto zařízení zase zmizí.

54

Jednotný hierarchický systém souborů
/

etc

dev

usr

home

tty

• svazek (angl. file system) je část souborového systému, kterou lze samostatně
vytvořit, připojit, zrušit. . . Každý filesystém může mít jinou vnitřní strukturu
(s5, ufs, ext2, xfs, atd.) a může být uložen na lokálním disku nebo na jiném
počítači a přístupný po síti (nfs, afs).
• po startu jádra je připojený jen kořenový filesystém, další filesystémy se zapojují do hierarchie na místa adresářů příkazem mount. Tento příkaz je možné
spustit ručně (uživatel root libovolně, ostatní pouze na některých systémech
a s omezeními) nebo automaticky během inicializace systému (řídí se obsahem souboru /etc/fstab). Před zastavením systému se filesystémy odpojují
příkazem umount.
• další možnost je připojení filesystému na žádost (při prvním přístupu) a jeho
odpojení po určité době nečinnosti. Tuto funkci zajišťuje démon automounter
(autofs, automount, amd).
• UNIX nemá žádné A, B, C, D. . . disky apod.

55

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

administrativní soubory (ne na BSD)

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

• v /bin, /lib, /sbin jsou příkazy a knihovny potřebné při startu systému,
kdy je připojen pouze kořenový filesystém. Ostatní příkazy a knihovny jsou
typicky v /usr/bin, /usr/lib a /usr/sbin (/usr bývá často samostatný
filesystém, čímž jeho obsah není dostupný během startu systému).
• podstrom /usr obsahuje soubory, které se nemění při běžném provozu a
nejsou závislé na konkrétním počítači. Proto by měl jít sdílet read-only. Na
své stanici doma ho ale samozřejmě budete mít read-write.
• v podstromu /var jsou data, která se za provozu mění a jsou specifická pro
každý počítač.
• různé systémy (i instalace jednoho systému) se mohou lišit.
• hier(7) na FreeBSD popisuje adresářovou hierarchii tohoto systému; ostatní
systémy budou pravděpodobně mít něco podobného

56

Přístup k periferním zařízením
• adresář /dev obsahuje speciální soubory zařízení. Proces otevře
speciální soubor systémovým voláním open() a dále komunikuje se
zařízením pomocí volání read(), write(), ioctl(), apod.
• speciální soubory se dělí na
– znakové . . . data se přenáší přímo mezi procesem a ovladačem
zařízení, např. sériové porty
– blokové . . . data prochází systémovou vyrovnávací pamětí (buffer
cache) po blocích pevně dané velikosti, např. disky

• speciální soubor identifikuje zařízení dvěma čísly
– hlavní (major) číslo . . . číslo ovladače v jádru
– vedlejší (minor) číslo . . . číslo v rámci jednoho ovladače

• vyrovnávací paměti urychlují periferní operace. Při čtení se data hledají nejprve v bufferu. Teprve když nejsou k dispozici, tak se čtou z disku. Při příštím
čtení stejného bloku jsou data v bufferu. Při zápisu se data uloží do bufferu.
Na disk je systém přepíše později. Lze si vynutit i okamžitý zápis dat na disk.
• disky v UNIXu jsou obvykle přístupné přes znakové (používané při mkfs –
vytvoření svazku – a fsck – kontrola konzistence) i blokové rozhraní (používané při normálním provozu systému souborů). Některé systémy (FreeBSD)
ale už v /dev vůbec soubory pro bloková zařízení nemají, pouze znaková.
• dříve musel administrátor systému po změně hardwarové konfigurace upravit
obsah adresáře /dev skriptem MAKEDEV nebo ručně. Nově (IRIX, FreeBSD,
. . . ) již speciální soubory dynamicky vznikají a zanikají podle toho, jak jádro
detekuje přidání nebo odebrání hardwarových komponent (viz devfs)
• okamžitý zápis na disk lze vynutit přes O DIRECT command ve volání fcntl()

57

Fyzické uložení systému souborů
• systém souborů (svazek, filesystem) lze vytvořit na:
– oddílu disku (partition) – část disku, na jednom disku může být více
oddílů
– logickém oddílu (logical volume) – takto lze spojit více oddílů, které
mohou být i na několika discích, do jednoho svazku.

• další možnosti: striping, mirroring, RAID
/home

/

disk 1

/usr

disk 2

disk 3

• výraz systém souborů se používá v několika významech:
– jeden filesystém, tj. to, co vyrobí příkaz mkfs
– celá hierarchie připojených svazků v systému (to, co vypíše příkaz mount)
– způsob organizace svazku (tj. typ fs) a tomu odpovídající modul jádra,
který s daty manipuluje (UFS2, Ext3, XFS, . . .)
• striping je od slova stripe, ne strip; podle toho se také vyslovuje. Znamená,
že za sebou následující bloky dat se ukládají paralelně na různé disky a tím
se zvyšuje přenosová rychlost.
• mirroring ukládá kopie dat pro případ havárie primárního disku.
• paritní disky: data se ukládají na dva disky, na třetí se ukládá XOR prvních
dvou, po havárii libovolného disku jsou všechna data stále čitelná.
• jednotlivé úrovně RAID (Redundant Array of Inexpensive Disks) zahrnují
striping, mirroring a využití paritních disků.
• na terminologii je třeba dát velký pozor. Např. to, co se v DOS světě nazývá
partition, se v BSD nazývá slice. Tam jsou pak partitions definovány v rámci
jednoho slice a v nich se vytvářejí filesystémy.

58

Organizace systému souborů s5
blok č.
zaváděcí blok (boot block)
0
1
superblok
2 oblast i-uzlů (i-nodes)

0

9 12

...
oblast datových bloků

• původní UNIXový systém souborů standardně používaný do verze System V
Release 3; v BSD se primárně používal do verze 4.1
• vlastnosti:
– bloky délky 512, 1024 nebo 2048 bajtů
– jediný (neduplikovaný) superblok
– datový prostor pevně rozdělený na oblast i-uzlů a oblast datových bloků
– při velikosti bloku 1024 bajtů byla teoretická velikost filesystému přes
16 GB
• boot block – pro uložení zavaděče OSu
• superblok – základní informace o svazku: počet bloků pro i-uzly, počet bloků
svazku, seznam volných bloků (pokračuje ve volných blocích), seznam volných i-uzlů (po vyčerpání se prohledává tabulka i-uzlů), zámky pro seznamy
volných bloků a i-uzlů, příznak modifikace (pro kontrolu korektního odpojení
svazku), čas poslední aktualizace, informace o zařízení
• i-uzel – typ souboru, přístupová práva, vlastník, skupina, časy posledního
přístupu, modifikace dat a modifikace i-uzlu (čas vytvoření souboru není
uložen), počet odkazů na soubor, velikost souboru, 10 odkazů na datové bloky
a 3 odkazy na nepřímé bloky
• maximální velikost souboru: 2113674 bloků, tj. přibližně 1 GB při použití
bloků velikosti 512 B
• jména souborů – max. 14 znaků (14 + 2 = 16, tedy mocnina dvou a tedy
bezproblémové uložní adresářových položek do bloků)
59

• při použití tohoto filesystému byla výkonnost disků využita jen cca na 2% a
rychlost čtení byla v řádu jen několika desítek kilobajtů za sekundu (!!!)
• pro srovnání – MS-DOS 2.0 z roku 1983 podporoval pouze FAT12, počítající
s maximální velikostí filesystému 16 MB. Velikost svazku do 2 GB byla umožněna až ve verzi 4.0 (1988); tato verze zároveň zavedla diskové vyrovnávací
paměti, tedy to, co UNIX má od svého vzniku v roce 1970. . .

Navigace v adresářové struktuře
i-nodes

/etc/passwd

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

root:x:0:...

Když cesta začíná znakem ‘ /‘ , začíná navigace v kořenovém adresáři, jinak
začne v pracovním adresáři procesu.

60

Linky
hard link
/var
password

originál
/etc
20

passwd

...
i-nodes
data

0

symbolický link
/usr
20

...
20

...

passwd

31

...
...

root:x:0:...

31
../etc/passwd

Hard linky lze vytvářet pouze v rámci jednoho (logického) filesystému.

hardlink
• odkaz na stejný i-uzel
• vlastně druhé jméno souboru
• není rozdíl mezi originálem a hardlinkem
• lze vytvářet jen v rámci filesystému
• nelze vytvářet pro adresáře
symbolický link (symlink, softlink)
• pouze odkaz na skutečnou cestu k souboru jiného typu (ls -l ho označuje ‘ l‘ ), tj. symbolický link je typem odlišný od běžného souboru a
jeho data obsahují obýčejný řetězec – jméno cesty, ať již relativní nebo
absolutní
• odlišné chování pro originál a link (např. při mazání)
• pozor na relativní a absolutní cesty při přesouvání symbolického linku
• může ukazovat i na adresář nebo na neexistující soubor
Nejjednošší způsob jak si ověřit, zda dané dva linky ukazují na stejný soubor
na disku je použít -i přepínač příkazu ls.
jp@sarrix:~$ ls -i /etc/passwd
172789 /etc/passwd

61

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

• superblok v každé cylinder skupině posunut tak, aby superbloky nebyly na
stejné plotně
• další typy filesystémů: UFS2, Ext3, ReiserFS, XFS, ZFS aj.
• http://www.devnull.cz/mff/programovani-v-unixu/filesystems.ps je
porovnání osmi různých filesystémů podle různých implementačních kritérií
• UFS byl stále 32-bitový, což se odráželo na maximální délce souboru i na
maximální velikosti filesystému
• žurnálování (XFS, Ext3, ReiserFS) – snaha o zmenšení nebezpečí ztráty dat
v případě havárie, urychlení zotavení po havárii

62

Vývoj ve správě adresářových položek
• maximální délka jména souboru 14 znaků nebyla dostačující
• FFS – délka až 255; každá položka zároveň obsahuje i její délku
• nové filesystémy používají pro vnitřní strukturu adresářů různé
varianty B-stromů
– výrazně zrychluje práci s adresáři obsahující velké množství
souborů
– XFS, JFS, ReiserFS, . . .
• UFS2 zavádí zpětně kompatibilní tzv. dirhash, kdy při prvním
přečtení adresáře se vytvoří v paměti hash struktura, následné
přístupy do adresáře jsou pak srovnatelné se systémy používající
B-stromy

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

63

spec vnodeops
spec file system

• původně byl v UNIXu pouze jeden typ systému souborů. Přidávání dalších
typů si vynutilo vznik mechanismu, který by umožnil jádru přistupovat jednotným způsobem k souborům na různých souborových systémech. Proto
vznikl VFS.
• VFS se poprvé objevilo v roce 1985 v Solarisu 2.0; brzy bylo převzato BSD
– FFS s podporou VFS je právě UFS.
• každému otevření souboru procesem přísluší struktura file. Ta ukazuje na
vnode (virtual node). Vnode obsahuje část nezávislou na konkrétním systému
souborů a strukturu inode, specifickou pro každý typ souborového systému.
Každý typ systému souborů definuje tabulku funkcí pro jednotlivé operace, na
kterou se odkazují všechny vnodes odpovídající souborům na všech svazcích
daného typu.
• u speciálních souborů je situace složitější, v SVR4 struktura file ukazuje na
snode (shadow-special-vnode), který definuje operace se zařízením (pomocí
souborového systému spec) a prostřednictvím ukazatele s realvp se odkazuje
na reálný vnode pro operace se speciálním souborem; ten je potřeba například pro kontrolu práv přístupu. Každému zařízení může odpovídat více speciálních souborů, a tedy více snodes a příslušných reálných vnodes. Všechny
takové snodes pro jedno zařízení mají ukazatel s commonvp na jeden společný
snode (toto není na obrázku zachyceno). Více viz například [Vahalia].
• při otevření speciálního souboru se hledá v hešovací tabulce snodes otevřených zařízení položka odpovídající speciálnímu souboru (podle major a minor
čísla zařízení). Když snode není nalezen, vytvoří se nový. Tento snode se pak
používá při operacích se zařízením.

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

64

mount
point
in
rootvfs

• struktura vfs – generické informace o filesystému, nezávislé na konkréntím
typu filesystému (podobně jako vnode funguje pro soubory)
• rootvfs – odkaz na root file system
• vfsops – tabulka funkcí pro konkrétní typ systému souborů
• vfssw[] – pole odkazů na tabulky vfsops pro všechny systémem podporované typy filesystémů, z tabulky se vybírá při připojování svazku podle typu
filesystému zadaného při volání mount()
• v vfsp – odkaz z vnode na filesystém (strukturu vfs), na kterém leží soubor
reprezentovaný pomocí vnode
• v vfsmountedhere – pouze ve vnode, který reprezentuje mount point (adresář, na kterém je připojen kořen jiného filesystému); odkazuje na strukturu
vfs reprezentující připojený filesystém
• v vnodecovered – odkaz na vnode adresáře, na kterém je filesystém připojen

Otevřené soubory z pohledu jádra
struct proc
uf next

uf next

u proc

u first

struct
ufchunk

struct
ufchunk

struct
ufchunk

...2 1 0

...2 1 0

. . . 2 1 0 uf ofile[]

struct user
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

struct
file

VNODE

VNODE

VNODE

VNODE

f prev

VNODE

struct file
*file

f vnode

• struktury proc a user vytváří jádro pro každý proces a drží v nich služební
informace o procesu.
• struktura ufchunk obsahuje NFPCHUNK (obvykle 24) deskriptorů souborů, po
zaplnění se alokuje další ufchunk.
• struktura file (otevření souboru) obsahuje mód souboru (otevřen pro čtení,
zápis, atd.), počet deskriptorů, které se na ni odkazují, ukazatel na vnode a
pozici v souboru. Jedno otevření souboru může být sdíleno více deskriptory,
jestliže byl původní deskriptor zkopírován, např. voláním fork() nebo dup().

65

• struktura cred obsahuje uživatelskou a skupinovou identitu procesu, který
otevřel soubor.
• jeden vnode odpovídající jednomu souboru může být sdílen několika strukturami file, pokud byl daný soubor vícekrát otevřen1 .
• ne všechny vnodes jsou asociovány s tabulkou otevřených souborů. Např. při
spuštění programu je potřeba přistupovat do spustitelného souboru a proto
se alokuje vnode.

Oprava konzistence souborového systému
• pokud není filesystém před zastavením systému korektně odpojen,
mohou být data v nekonzistentním stavu.
• ke kontrole a opravě svazku slouží příkaz fsck. Postupně testuje
možné nekonzistence:
– vícenásobné odkazy na stejný blok
– odkazy na bloky mimo rozsah datové oblasti systému souborů
– špatný počet odkazů na i-uzly
– nesprávná velikost souborů a adresářů
– neplatný formát i-uzlů
– bloky které nejsou obsazené ani volné
– chybný obsah adresářů
– neplatný obsah superbloku
• operace fsck je časově náročná.
• žurnálové systémy souborů (např. XFS v IRIXu, Ext3 v Linuxu)
nepotřebují fsck.

• data se přepisují na disky z vyrovnávacích pamětí se zpožděním. Uložení
všech vyrovnávacích pamětí lze vynutit systémovým voláním sync(). Periodicky vyrovnávací paměti ukládá zvláštní systémový proces (démon).
• zde je ukázka fsck na odpojený filesystém:
toor@shewolf:~# fsck /dev/ad0a
** /dev/ad0a
** Last Mounted on /mnt/flashcard
** Phase 1 - Check Blocks and Sizes
** Phase 2 - Check Pathnames
** Phase 3 - Check Connectivity
** Phase 4 - Check Reference Counts
** Phase 5 - Check Cyl groups
24 files, 8848 used, 12951 free (7 frags, 1618 blocks, 0.0% fragmentation)
1 Jak se při otvírání souboru zjistí, že pro soubor už existuje vnode, když neexistuje evidence
všech vnodes?

66

Další způsoby zajištění konzistence
filesystému
• tradiční UFS používá synchronní zápis metadat; nevýhoda je, že
např. aplikace vytvářející nový soubor čeká na inicializaci inode na
disku; tyto operace pak pracují rychlostí disku a ne rychlostí CPU
– ext2 dokonce defaultně používá asynchronní zápis metadat, při
použítí synchronního zápisu je výrazně pomalejší než UFS
• řešení problémů s nekonzistencí metadat na disku:
– journalling – skupina na sobě závislých operací se nejdříve
atomicky uloží do žurnálu; při problémech se pak žurnál může
„přehrátÿ
– bloky metadat se nejdříve zapíší do non-volatile paměti
– soft-updates – sleduje závislosti mezi ukazately na diskové
struktury a zapisuje data na disk metodou write-back tak, že
data na disku jsou vždy konzistentní
– ZFS je nový filesystém v Solarisu, který používá copy-on-write

• filesystem metadata = inodes, directories, free block maps
• závislé operace jsou například smazání položky z adresáře a smazání diskového inode. Pokud by se stalo, že se nejdříve smaže diskový inode a pak teprve
položka v adresáři, při výpadku mezi těmito dvěmi operacemi vniká nekonzistence – link ukazuje na diskový soubor, který neexistuje. Není problém se
tomuto vyhnout při synchronním zápisu metadat (víme kdy a co zapisujeme,
určujeme tedy pořadí zápisu), ale při metodě write-back je již nutné řešit
závislosti jednotlivých bloků na sebe, protože při klasické synchronizaci vyrovnávacích pamětí na disk jádro nezajímá, který blok se zapíše dřív a který
později.
• často jsou bloky na sobě závislé ve smyčce. Soft updates dokáže takovou
smyčku rozbít tím, že provede roll-back a po zápisu pak roll-forward
• výkon soft updates je srovnatelný výkonu UFS filesystému s asynchronním
zápisem metadat
• soft updates zaručují, že po rebootu není potřeba použít fsck, tj. že filesystém bude v takovém stavu, že je možné nabootovat. Je však nutné použít
tzv. background fsck pro opravy nezávažných chyb – to je považováno stále
za velkou nevýhodu soft updates zvláště s tím, jak rostou velikosti běžně používaných disků. Takovou chybou, která nebrání nabootování, ale je nutné ji
odstranit je například blok, který je označen jako použitý, ale žádný soubor
ho nepoužívá.
• soft updates nejsou vždy doporučovány pro root filesystém. Problém je to,
že ztráta metadat na root filesystému (viz 30-ti sekundová perioda zápisu)
může být výrazně větší hrozbou zde než na /usr, /home atd.

67

• ZFS, 128-bitový filesystém, teprve přijde do update 2 pro Solaris 10

Přístupová práva
nejvyšší bit

vlastník (u) skupina (g) ostatní (o)
z }| {
z }| {
z }| {

4
2

suid
sgid
sticky

1

r
w
x

• SGID pro soubor bez práva spuštění pro skupinu v System V:
kontrola zámků při každém přístupu (mandatory locking)
• sticky bit pro adresáře: právo mazat a přejmenovávat soubory mají
jen vlastníci souborů
• SGID pro adresář: nové soubory budou mít stejnou skupinu jako
adresář (System V; u BSD systémů to funguje jinak, viz poznámky)

• SGID pro adresáře u BSD systémů způsobí, že soubory a podadresáře vytvořené v tomto adresáři budou mít stejného majitele jako je majitel daného
adresáře. Nutným předpokladem je dále to, že daný UFS filesystém musí být
namontován s suiddir příznakem a v jádru je option SUIDDIR (a to není
default). Navíc to nefunguje pro roota. Tato možnost existuje kvůli Sambě a
Nettalku.
• sticky bit pro adresáře: přejmenovat nebo smazat soubor může jen jeho vlastník (v některých implementacích stačí i právo zápisu do souboru), nestačí
právo zápisu do adresáře. Toto nastavení se používá pro veřejné adresáře
(např. /tmp).
• původně měl sticky bit význam i pro spustitelné soubory: program s nastaveným sticky bitem zůstal po ukončení v paměti a jeho opětovné spuštění bylo
rychlejší. Dnes se sticky bit v tomto významu už nepoužívá.
• některé filesystémy (XFS, AFS, UFS2) mají tzv. access control lists (ACLs),
které dovolují jemnější přidělování práv jednotlivým uživatelům a skupinám.

68

API pro soubory
• před použitím musí proces každý soubor nejprve otevřít voláním
open() nebo creat().
• otevřené soubory jsou dostupné přes deskriptory souborů (file
descriptors), číslované od 0, více deskriptorů může sdílet jedno
otevření souboru (mód čtení/zápis, ukazovátko pozice)
• standardní deskriptory:
– 0 . . . standardní vstup (jen pro čtení)
– 1 . . . standardní výstup (jen pro zápis)
– 2 . . . chybový výstup (jen pro zápis)
• čtení a zápis z/do souboru: read(), write()
• změna pozice: lseek(), zavření: close(), informace: stat(), řídicí
funkce: fcntl(), práva: chmod(), . . .

• každá funkce, která alokuje deskriptory (nejen open() a creat(), ale např. i
pipe(), dup(), socket()) alokuje vždy volné deskriptory s nejnižším číslem.
• proces dědí otevřené soubory od rodiče, tyto soubory nemusí znovu otvírat.
Obvykle (ale ne vždy) proces dostane otevřené alespoň deskriptory 0, 1 a 2.
• funkce deklarované v headeru stdio.h (např. fopen(), fprintf(), fscanf())
a odkazy na soubory pomocí ukazatele na FILE jsou definovány ve standardní
knihovně a pro svojí činnost používají volání jádra (např. open(), write(),
read()). My se nebudeme knihovnou stdio zabývat.

69

Otevření souboru: open()
int open(const char *path, int oflag, ... );
• otevře soubor daný jménem (cestou) path, vrátí číslo jeho
deskriptoru (použije první volné), oflag je OR-kombinace příznaků
– O RDONLY/O WRONLY/O RDWR . . . otevřít pouze pro čtení / pouze
pro zápis / pro čtení i zápis
– O APPEND . . . připojování na konec
– O CREAT . . . vytvořit, když neexistuje
– O EXCL . . . chyba, když existuje (použití s O CREATE)
– O TRUNC . . . zrušit předchozí obsah
– ...
• při O CREAT definuje třetí parametr mode přístupová práva (ještě se
modifikuje podle umask).

• mode nemá defaultní hodnotu, tj. vezme se to, co je na zásobníku i když
tento parametr není přítomen! Flagy i mód jsou uloženy v systémové tabulce
otevřených souborů.
• pokud se znovu použije dříve využívaná položka v tabulce deskriptorů nebo
v tabulce otevřených souborů, vše potřebné se vynuluje (pozice v souboru,
flagy deskriptoru, . . . )
• existují ještě další nastavitelné příznaky:
– O SYNC (O DSYNC, O RSYNC – není na BSD) . . . operace se souborem
skončí až po fyzickém uložení dat (synchronized I/O)
– O NOCTTY . . . při otvírání terminálu procesem, který nemá řídicí terminál, se tento terminál nestane řídícím terminálem procesu
– O NONBLOCK . . . pokud nelze čtení nebo zápis provést okamžitě, volání
read()/write() skončí s chybou místo zablokování procesu
• v přístupových právech se vynulují ty bity, které jsou nastavené pomocí
umask().
• otevírání pojmenované roury je závislé na tom, s jakými flagy rouru otevíráme
a zda je již jiným procesem otevřená (a s jakými flagy). Podrobné informace
viz UNIX 03.

70

Vytvoření souboru
int creat(const char *path, mode t mode );
• open() s příznakem O CREAT vytvoří soubor, pokud ještě neexistuje.
V zadané hodnotě přístupových práv se vynulují bity, které byly
nastaveny pomocí funkce
mode t umask(mode t cmask );
• funkce je ekvivalentní volání
open(path, O WRONLY|O CREAT|O TRUNC, mode);
int mknod(const char *path, mode t mode, dev t dev );
• vytvoří speciální soubor zařízení.
int mkfifo(const char *path, mode t mode );
• vytvoří pojmenovanou rouru.

• test, zda soubor existuje, a jeho případné vytvoření je atomická operace. Toho
se využívá při používání lock souborů.
• speciální soubory může vytvářet pouze root, protože se pomocí nich definují
přístupová práva k periferním zařízením.
• hodnoty pro mode je možné nalézt většinou v manuálové stránkce pro chmod

71

Zápis a čtení souborů: write(), read()
ssize t write(int fildes, const void *buf, size t nbyte );
• do otevřeného souboru s číslem deskriptoru fildes zapíše na
aktuální pozici max. nbyte bajtů dat uložených od adresy buf.
• vrací velikost skutečně zapsaných dat (<= nbyte).
ssize t read(int fildes, void *buf, size t nbyte );
• z otevřeného souboru s číslem deskriptoru fildes přečte od
aktuální pozice max. nbyte bajtů dat a uloží je od adresy buf.
• vrací počet skutečně přečtených bajtů (<= nbyte), 0 znamená
konec souboru.

• pro UNIX je každý soubor posloupnost bajtů bez další vnitřní struktury.
• chování read() a write() závisí na typu souboru (obyčejný soubor, periferní
zařízení, roura, soket) a na tom, zda je soubor v blokujícím nebo neblokujícím
módu (příznak O NONBLOCK při otevření souboru).
• volání read() vrátí nenulový počet bajtů menší než nbyte, jestliže v souboru zbývá méně než nbyte bajtů do konce, volání bylo přerušeno signálem,
nebo soubor je roura, speciální soubor (zařízení) nebo soket a aktuálně je
k dispozici méně než nbyte bajtů.
• pokud nejsou aktuálně k dispozici žádná data, blokující read() se zablokuje, dokud se nějaká data neobjeví, neblokující read() vrátí -1 a nastaví
errno = EAGAIN.
• volání write() vrátí nenulový počet bajtů menší než nbyte, jestliže se do
souboru nevejde víc dat (zaplněný disk nebo dosažený limit velikosti souboru), zápis je přerušen signálem nebo je nastaveno O_NONBLOCK a do roury,
soketu nebo zařízení se vejde pouze část zapisovaných dat. Bez O_NONBLOCK
se vždy čeká, dokud se nepodaří zapsat vše.
• když read() nebo write() vrátí méně než nbyte z důvodu chyby, opakované
volání téže funkce vrátí -1 a nastaví kód chyby v errno.
• pokud nelze aktuálně zapsat nic, blokující write() se zablokuje, dokud není
možné zapisovat, neblokující write() vrátí -1 a nastaví errno = EAGAIN.
• přerušení read(), write() signálem dřív, než se podaří přečíst, resp. zapsat
aspoň jeden bajt, způsobí návrat s hodnotou -1 a nastavení errno = EINTR.
• příznak otevření souboru O_APPEND zajistí atomický zápis na konec souboru
(pouze na lokálním disku), tj. každý zápis se provede na konec souboru.
72

Uzavření souboru: close()
int close(int fildes );
• uvolní deskriptor fildes, pokud to byl poslední deskriptor, který
odkazoval na otevření souboru, zavře soubor a uvolní záznam o
otevření souboru.
• když je počet odkazů na soubor 0, jádro uvolní data souboru. Tedy i
po zrušení všech odkazů (jmen) mohou se souborem pracovat
procesy, které ho mají otevřený. Soubor se smaže, až když ho zavře
poslední proces.
• když se zavře poslední deskriptor roury, všechna zbývající data
v rouře se zruší.
• při skončení procesu se automaticky provede close() na všechny
deskriptory.

• pokud proces potřebuje dočasný soubor, může ho vytvořit, ihned smazat a
pak s ním pracovat přes existující deskriptor (tento deskriptor lze předat
synovským procesům). Když je takový soubor zavřen všemi procesy, jádro
smaže jeho data z disku.
• i operace close() může selhat. Např. některé filesystémy zapisují data na
disk až v okamžiku zavření souboru, když zápis skončí chybou, close() vrátí
-1.
• otevírání souborů a nezavírání je při ukončení práce s nimi vede k alokované
paměti, kterou již nemáme jak uvolnit (ztratili jsme na ni odkaz) – situace
kde takto paměť „ztrácímeÿ se nazývá memory leak

73

Příklad: kopírování souborů
#include <fcntl.h>
#define BUFSIZE 4096
int main(int argc, char *argv[])
{
char buf[BUFSIZE];
int inf, outf; int len, ilen, olen;
inf = open(argv[1], O RDONLY);
outf = creat(argv[2], 0666);
while((ilen = read(inf, buf, BUFSIZE)) > 0)
write(outf, buf, ilen);
close(inf);
close(outf);
exit(0);
}

• je neefektivní číst a zapisovat soubor po jednotlivých bajtech, lepší je najednou zpracovávat rozumně velké bloky.
• pokud potřebujete pracovat s malými částmi/buffery, je lepší použít stream
orintované knihovní funkce fopen(), fread(), . . . které data vnitřně bufferují

74

Nastavení pozice: lseek()
off t lseek(int fildes, off t offset, int whence );
• nastaví pozici pro čtení a zápis v otevřeném souboru daném číslem
deskriptoru fildes na hodnotu offset.
• podle hodnoty whence se offset počítá:
– SEEK SET . . . od začátku souboru
– SEEK CUR . . . od aktuální pozice
– SEEK END . . . od konce souboru
• vrací výslednou pozici počítanou od začátku souboru.
• lseek(fildes, 0, SEEK CUR) pouze vrátí aktuální pozici.

• lze se přesunout i na pozici za koncem souboru. Pokud se pak provede zápis,
soubor se prodlouží a v přeskočené části budou samé nuly (samotné lseek()
nestačí). Některé filesystémy takové bloky celých nul pro úsporu místa neukládají.
• velikost souboru je možné zjistit pomocí lseek(fildes, 0, SEEK END).
• nejčastější operace s lseek jsou tři: nastavení konkrétní pozice od začátku
souboru, nastavení pozice na konec souboru a zjištění aktuální pozice v souboru (0 společně se SEEK CUR)
• při použití lseek se žádné I/O neprovede, žádný příkaz se nepošle na řadič
disku
• lseek nemusí sloužit jen pro operace read a write, ale také pro následnou
operaci lseek
• ukládání nul může vést k problémům se zálohami

75

Změna velikosti: truncate()
int truncate(const char *path, off t length );
int ftruncate(int fildes, off t length );
• změní délku souboru zadaného cestou nebo číslem deskriptoru na
požadovanou hodnotu.
• při zkrácení souboru zruší nadbytečná data.
• standard ponechává nespecifikované, jestli funguje prodloužení
souboru (s vyplněním přidaného úseku nulami). Proto je lepší
k prodloužení souboru použít
char buf = ’\0’;
lseek(fildes, length-1, SEEK_SET);
write(fildes, buf, 1);

• zrušit veškerý obsah souboru při otevření se dá příznakem O TRUNC ve funkci
open().
• podrobnosti je třeba hledat v manuálové stránce, např. ve FreeBSD v sekci
BUGS nalezneme toto: Use of truncate() to extend a file is not portable.

76

Duplikace deskriptoru: dup(), dup2()
int dup(int fildes );
• duplikuje deskriptor fildes na první volný deskriptor, vrátí nový
deskriptor, který odkazuje na stejné otevření souboru.
• ekvivalent fcntl(fildes, F DUPFD, 0);
int dup2(int fildes, int fildes2 );
• duplikuje deskriptor fildes na deskriptor fildes2.
• ekvivalent
close(fildes2);
fcntl(fildes, F DUPFD, fildes2);

• duplikovaný a původní deskriptor sdílí stejné otevření souboru a tedy i aktuální pozici a mód čtení/zápis.
• ekvivalent pro dup2 není zcela ekvivalentní, např. pokud je fildes rovný
fildes2. Více viz norma.

77

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

• další příklad použití dup() uvidíme, až se budeme zabývat rourami.
• je potřeba si dát pozor na stav deskriptorů. Druhý příklad nebude fungovat,
když bude deskriptor 0 uzavřen, protože open() vrátí deskriptor 0 (první
volný) a dup() vrátí chybu (pokus o duplikaci uzavřeného deskriptoru).
Možné řešení:
close(1);
if((fd = open("out", O WRONLY | O CREAT | O TRUNC, 0666)) == 0)
dup(0);
close(2);
dup(1);
if(fd == 0)
close(0);
nebo
fd = open("out", O WRONLY | O CREAT | O TRUNC, 0666);
if(fd != 1) {
dup2(fd, 1);
close(fd);
}
dup2(1, 2);

78

Řídicí funkce souborů a zařízení: fcntl(),
ioctl()
int fcntl(int fildes, int cmd, ...);
• slouží pro duplikaci deskriptorů, nastavování zámků, testování a
nastavování různých příznaků souboru.
příklad: zavření standardního vstupu při spuštění programu (volání
typu exec)
fcntl(0, F SETFD, FD CLOEXEC);
int ioctl(int fildes, int request, ... );
• rozhraní pro řídicí funkce periferních zařízení
• používá se jako univerzální rozhraní pro ovládání zařízení, každé
zařízení definuje množinu příkazů, kterým rozumí.

• možné hodnoty cmd ve funkci fcntl():
– F DUPFD . . . duplikace deskriptoru
– F GETFD . . . zjištění příznaků deskriptoru (FD CLOEXEC – uzavření při
exec). FD CLOEXEC je jediný flag pro deskriptory, definovaný v normě
UNIX 03.
– F SETFD . . . nastavení příznaků deskriptoru
– F GETFL . . . zjištění módu čtení/zápis a příznaků otevření souboru (jako
u open())
– F SETFL . . . nastavení příznaků otevření souboru (O APPEND, O DSYNC,
O NONBLOCK, O RSYNC, O SYNC). Nemohu nastavit příznaky pro čtení/zápis,
ani flagy pro vytvoření, zkrácení nebo exkluzivní přístup.
– F GETLK, F SETLK, F SETLKW . . . nastavování zámků
• je důležité si uvědomit, že jsou dva druhy příznaků – příznak(y) pro souborový deskriptor a příznaky pro otevřený soubor – tj. příznaky jsou uložené
ve dvou různých tabulkách.
• periferní zařízení podporují čtení a zápis dat pomocí read(), write() a
mapování dat do paměti (mmap()), veškeré další operace se zařízením (např.
nastavení parametrů, zamčení nebo eject) se dělají funkcí ioctl().
• při nastavování příznaků nejdřív vždy zjistěte, jaké byly předtím. I když
jste si jisti, že v dané chvíli jsou nulové a je tedy možné provést fcntl(fd,
O APPEND), nemůžete vědět, co se může změnit (například o pár řádků výše
nějaký flag přidáte, aniž byste věděli, že jste ovlivněni kódem dole). Tedy
vždy použijte například toto:

79

flags = fcntl(fd, F_GETFL);
if (fcntl(fd, F_SETFL, flags | O_APPEND) == -1)
...
. . . a podobně pro odebrání flagu – je špatné řešení nastavit hodnotů flagů na
nulu, místo toho je třeba použít bitového jedničkového doplňku příslušného
flagu

Informace o souboru: stat()
int stat(const char *path, struct stat *buf );
int fstat(int fildes, struct stat *buf );
• pro soubor zadaný cestou, resp. číslem deskriptoru, vrátí strukturu
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

• metadata jsou informace o souboru – tedy mód, časy přístupu, délka, vlastník
a skupina atd. Nepatří mezi ně skutečná data souboru, a ani jméno, které
není uloženo v rámci daného souboru, ale v adresáři či v adresářích.
• metadata je možné přečíst, i když proces nemá práva pro čtení obsahu souboru.
• toutou funkcí nezískám flagy deskriptoru ani flagy z pole tabulky otevřených souborů v systému, zde jde o informace ohledně souboru uloženého na
paměťovém médiu.
• c time není čas vytvoření soubor (creation time), ale čas změny (change
time)
• norma nespecifikuje pořadí položek ve struktuře ani nezakazuje přidat další

80

Informace o souboru (2)
• pro typ souboru jsou v <sys/stat.h> definovány konstanty S_IFMT
(maska pro typ), S_IFBLK (blokový speciální), S_IFCHR (znakový
speciální), S_IFIFO (FIFO), S_IFREG (obyčejný), S_IFDIR
(adresář), S_IFLNK (symlink).
• typ lze testovat pomocí maker S_ISBLK(m), S_ISCHR(m),
S_ISFIFO(m), S_ISREG(m), S_ISDIR(m), S_ISLNK(m).
• konstanty pro přístupová práva: S_IRUSR (čtení pro vlastníka),
S_IWGRP (zápis pro skupinu), atd.
int lstat(const char *path, struct stat *buf );
• když je zkoumaný soubor symlink, stat() vrátí informace o
souboru, na který ukazuje. Tato funkce vrací informace o symlinku.

• typ a práva souboru jsou uložena společně v st_mode, proto existují zmiňovaná makra.
• S IFMT specifikuje tu část bitů, které jsou věnované typu souboru, makra pro
jednotlivé typy pak nejsou masky, ale hodnoty, takže test na typ souboru je
nutné udělat takto: (st mode & S IFMT == S IFREG). Všechna makra jsou
v normě, takže jejich používáním zaručíme přenositelný kód.

81

Nastavení časů souboru
int utime(const char *path, const struct utimbuf *times );
• nastaví čas poslední modifikace souboru a čas posledního přístupu
k souboru.
• nelze změnit čas poslední modifikace i-uzlu.
• volající proces musí mít právo zápisu pro soubor.

• tuto funkci používají hlavně kopírovací a archivační programy, aby zajistily
stejné časy kopie a originálu.
• shellové rozhraní pro funkci utime() představuje příkaz touch.

82

Test přístupových práv: access()
int access(const char *path, int amode );
• otestuje, zda volající proces má k souboru path práva daná
OR-kombinací konstant v amode:
– R_OK . . . test práva na čtení
– W_OK . . . test práva na zápis
– X_OK . . . test práva na spuštění
– F_OK . . . test existence souboru
• na rozdíl od stat(), výsledek závisí na RUID a RGID procesu

• volání access() aplikuje mechanismus testování přístupových práv k zadanému souboru pro volající proces a vrátí výsledek.
• funkce access() volání byla pro setuid proces, aby si mohl ověřit, zda uživatel
běžící daný setuid proces by měl za normálních okolností k příslušnému souboru přístup. Z toho vyplývá, že toto volání je security hole – mezi testem
a následnou akcí se soubor může změnit, což proces nemůže nikdy ošetřit.
Řešením je vrátit se zpátky k reálným UID/GID a přístup vyzkoušet.

83

Nastavení přístupových práv
int chmod(const char *path, mode t mode );
• změní přístupová práva souboru path na hodnotu mode.
• tuto službu může volat pouze vlastník souboru nebo superuživatel
(root).
int chown(const char *path, uid t owner, gid t group );
• změní vlastníka a skupinu souboru path. Hodnota -1 znamená
zachovat vlastníka, resp. skupinu.
• měnit vlastníka může jen superuživatel, aby uživatelé nemohli
obcházet nastavené quoty tím, že své soubory předají někomu
jinému.
• běžný uživatel může měnit skupinu svých souborů a musí přitom
patřit do cílové skupiny.

• parametr mode zde samozřejmě neobsahuje typ souboru, jako tomu je například u volání stat(). Hodnoty mode viz chmod(2).
• pokud nejsem vlastník, nemohu celkem logicky změnit mód ani u souboru s
nastaveným přístupem rw-rw-rw• v některých implementacích může vlastník souboru předat vlastnictví někomu jinému, např. v IRIXu je chování chown() nastavitelné jako parametr
jádra.
• není běžné volat funkci chmod() z uživatelských aplikací, na to se používají
flagy u volání open(), hlavní použití je v aplikaci chmod(1)

84

Manipulace se jmény souborů
int link(const char *path1, const char *path2 );
• vytvoří nový odkaz (položku adresáře) path2 na soubor path1.
Funguje pouze v rámci jednoho svazku.
int unlink(const char *path );
• zruší odkaz na soubor. Po zrušení posledního odkazu na soubor a
uzavření souboru všemi procesy je soubor smazán.
int rename(const char *old, const char *new );
• změní jméno souboru (přesně odkazu na soubor) z old na new.
Funguje pouze v rámci jednoho svazku.

• volání link() vytváří hardlinky, tj. zobrazení ze jména souboru na číslo iuzlu. Čísla i-uzlů jsou jednoznačná pouze v rámci svazku, proto pro linky
mezi filesystémy je nutné použít symlinky.
• parametr path2 nesmí existovat, tedy nelze takto přejmenovávat
• unlink() nefunguje na adresáře
• shellový příkaz mv používá rename pro přesuny v rámci jednoho svazku. Přesun souboru mezi filesystémy vyžaduje nejprve soubor zkopírovat a pak smazat originál voláním unlink.
• rename() funguje nad symlinky, ne nad soubory, na které symlink ukazuje

85

Symbolické linky
int symlink(const char *path1, const char *path2 );
• vytvoří symbolický link path2 → path1.
• cíl symbolického linku může být i na jiném svazku, popřípadě nemusí
vůbec existovat.
int readlink(const char *path, char *buf, size t bufsize );
• do buf dá max. bufsize znaků z cesty, na kterou ukazuje symlink
path.
• vrátí počet znaků uložených do buf.
• obsah buf není zakončen nulou (znakem ’\0’)!

• shellový příkaz ln volá symlink() nebo link(), podle toho, jestli je použit
přepínač -l nebo ne.
• smazání hardlinku nesmaže soubor, pokud na něj vede ještě jiný hardlink.
Naopak soubor (položku adresáře i data) je možné smazat, i když na něj
ukazují nějaké symlinky.
• readlink() je na použitelný v situaci, pokud chci smazat soubor, na který
daný symlink ukazuje
• bufsize se typicky dává o 1 menší než velikost bufferu, to pro ukončení
znakem ‘
0‘

86

Manipulace s adresáři
int mkdir(const char *path, mode t mode );
• vytvoří nový prázdný adresář, (bude obsahovat pouze položky ‘ .‘ a
‘ ..‘ ).
int rmdir(const char *path );
• smaže adresář path. Adresář musí být prázdný.
DIR *opendir(const char *dirname );
struct dirent *readdir(DIR *dirp );
int closedir(DIR *dirp );
• slouží k sekvenčnímu procházení adresářů.
• struktura dirent obsahuje položky
– d_ino . . . číslo i-uzlu
– d_name . . . jméno souboru

• položky adresáře nejsou nijak uspořádány, readdir() je může vracet v libovolném pořadí.
• v některých implementacích (např. FreeBSD) lze adresář otevřít pro čtení (ne
pro zápis) jako normální soubor a číst ho pomocí read(), ale je třeba znát jeho
vnitřní organizaci. Proto je readdir() pro zpracování obsahu adresáře lepší než
read(), který vrací raw data adresáře. Kromě toho, norma nevyžaduje, aby
adresář bylo možné číst funkcí read(), Linux to například nedovolí.
• readdir() je stavová funkce. Pro vrácení se na začátek je možné použít funkci
rewinddir(). S vlánky pak používat readdir r(), protože struktura dirent je
statická.
• d ino není moc užitečné, protože v případě, kdy daný adresář je mount point,
tak ukazuje na adresář, na který je další filesystém namontován, ne na kořen
namontovaného filesystému
• rmdir nefunguje na neprázný adresář, je možné použít například toto:
system("rm -r xxx")

87

Příklad: procházení adresáře
int main(int argc, char *argv[])
{
int i;
DIR *d;
struct dirent *de;
for(i = 1; i < argc; i++) {
d = opendir(argv[i]);
while(de = readdir(d))
printf("%s\n", de->d_name);
closedir(d);
}
exit(0);
}

• příkaz ls je založen na takovéto smyčce, navíc provádí např. třídění jmen
souborů a zjišťování dalších informací pomocí stat().
• konec adresáře se pozná tak, že readdir() vrátí NULL. To však vrátí i v případě,
pokud nastala chyba. V takovém případě je kód chyby v proměnné errno, v
případě prvním je errno nezměněna. Proto by errno mělo být vždy nastavené
na nulu před voláním readdir(). V příkladu tomu tak není, protože z důvodu
málo místa nekontrolujeme errno vůbec.

88

Aktuální adresář procesu
• každý proces má svůj aktuální (pracovní) adresář, vůči kterému jsou
udávány relativní cesty k souborům. Počáteční nastavení pracovního
adresáře se dědí od otce při vzniku procesu.
int chdir(const char *path );
int fchdir(int fildes );
• nastaví nový pracovní adresář procesu.
char *getcwd(char *buf, size t size );
• uloží absolutní cestu k aktuálnímu adresáři do pole buf, jeho délka
(size) musí být aspoň o 1 větší než délka cesty.

• funkci fchdir() se předává deskriptor získaný voláním open() na adresář.
• funkce getcwd() může vrátit jinou cestu než tu, po které jsme se do aktuálního adresáře dostali, jesliže část cesty v chdir() byl symlink nebo došlo k
přesunu (přejmenování) některého adresáře na cestě od kořene. U současných
unixů by se to ale už stát nemělo.

89

Paměť procesu v uživatelském režimu
text
data
bss

nelze adresovat
uživ. programem

{

zásobník
oblast user

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


adresovatelné
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

• text . . . kód programu
• data . . . icializované proměnné
• sekce text a data jsou uloženy ve spustitelném souboru
• bss . . . neinicializované proměnné (bss pochází z assembleru IBM 7090 a
znamená „block started by symbolÿ). Za běhu programu tvoří sekce data
a bss dohromady datový segment procesu. Velikost datového segmentu lze
měnit pomocí systémových volání brk() a sbrk().
• (uživatelský) zásobník . . . automatické proměnné, parametry funkcí, návratové adresy. Každý proces má dva zásobníky, jeden pro uživatelský režim a
jeden pro režim jádra. Uživatelský zásobník procesu automaticky roste podle
potřeby (neplatí, pokud se používají vlákna).
• oblast user (u-area) . . . obsahuje informace o procesu používané jádrem, které
nejsou potřebné, když je proces odložen na disku (počet otevřených souborů,
nastavení ošetření signálů, počet segmentů sdílené paměti, argumenty programu, proměnné prostředí, aktuální adresář, atd.). Tato oblast je přístupná
pouze pro jádro, které vždy vidí právě jednu u-oblast patřící právě běžícímu
procesu. Další informace o procesu, které jádro může potřebovat i pro jiný
než právě běžící proces, nebo i když je proces odložen, jsou ve struktuře proc.
Struktury proc pro všechny procesy jsou stále rezidentní v paměti a viditelné
v režimu jádra.

90

Paměť procesu v režimu jádra
text jádra
data a bss jádra
(tabulky, proměnné, apod.)
struktura user
bežícího procesu

extern struct user u;
zásobník jádra

• proces se dostane do režimu jádra buď příchodem přerušení vyvolaného procesorem (výpadek stránky, neznámá instrukce,. . .), časovačem (v pravidelných
intervalech je potřeba aktivovat plánovač procesů), periferním zařízením,
nebo instrukcí synchronního přerušení (standardní knihovna takto předává
řízení jádru, aby obsloužilo systémové volání).
• v paměti je pouze jedna kopie kódu a dat jádra, sdílená všemi procesy. Kód
jádra je vždy celý rezidentní v paměti, není odkládán na disk.
• text jádra . . . kód jádra operačního systému, zavedený při startu systému
a rezidentní v paměti po celou dobu běhu systému. Některé implementace
umožňují přidávat funkční moduly do jádra za běhu (např. při přidání nového
zařízení se do jádra dynamicky přidá nový ovladač), není proto třeba kvůli
každé změně regenerovat jádro a restartovat systém.
• data a bss jádra . . . datové struktury používané jádrem, součástí je i u-oblast
právě běžícího procesu.
• zásobník jádra . . . samostatný pro každý proces, je prázdný, jestliže je proces
v uživatelském režimu (a tedy používá uživatelský zásobník).

91

Paměťové segmenty procesu
a segs
struct as

read only
text
shared
s as
s prev
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

• každý proces má tři základní segmenty:
– text
– data
– zásobník
• dále lze do adresového prostoru připojit segmenty sdílené paměti (shmat())
nebo soubory (mmap()).
• text je sdílen všemi procesy, které provádí stejný kód. Datový segment a
zásobník jsou privátní pro každý proces.

92

Virtuální paměť
paměť
procesu
   1

   
   
   
   

paměť
procesu 2

  
  
  
  

paměť
procesu 3



paměť
procesu 4





     

   
     
    
reálná 
    
paměť 
   

 
 
 

   
   
   


• každý proces vidí svůj adresový prostor jako souvislý interval (virtuálních)
adres od nuly po nějakou maximální hodnotu. Přístupné jsou pouze ty adresy,
na kterých je namapován některý segment procesu.
• jádro dále rozděluje paměť procesu na stránky. Každá stránka má své umístění v rámci fyzické paměti. Toto umístění je dáno stránkovacími tabulkami
jádra a stránky mohou být v rámcích libovolně promíchány vůči jejich pořadí
ve virtuální adresovém prostoru.
• pokud není stránka právě používána, může být také odložena na disk.
• paměťový manager jádra zajišťuje mapování mezi virtuálními adresami používanými kódem uživatelských procesů i jádra na fyzické adresy a načtení
odložených stránek z disku při výpadku stránky.

93

Implementace virtuální paměti
• procesy v UNIXu používají k přístupu do paměti virtuální adresy,
které na fyzické adresy převádí hardware ve spolupráci s jádrem
systému.
• při nedostatku volné paměti se odkládají nepoužívané úseky paměti
do odkládací oblasti (swap) na disk.
• před verzí SVR2 se procesem swapper (nyní sched) odkládaly celé
procesy.
• od verze SVR2 se používá stránkování na žádost (demand paging)
a copy-on-write. Stránky se alokují až při prvním použití a privátní
stránky se kopírují při první modifikaci. Uvolňování a odkládání
jednotlivých stránek provádí proces pageout, odkládání celých
procesů nastupuje až při kritickém nedostatku paměti.

překlad adres: Přístup na neplatnou adresu nebo pokus o zápis do paměti pouze
pro čtení vyvolá signál SIGSEGV.
swap: Odkládací prostor se vytváří na samostatném oddílu disku, od SVR4 může
být i v souboru.
swapper: Proces swapper se snaží odložit na disk nějaký proces, který není zamčen v paměti, a na uvolněné místo zavést dříve odložený proces.
demand paging: Při žádosti procesu o paměť se pouze upraví tabulka stránek.
První instrukce adresující obsah stránky vyvolá výjimku. Jádro ji ošetří tím,
že alokuje stránku.
copy-on-write: Více procesů může sdílet zapisovatelnou fyzickou stránku, která
je ale logicky privátní pro každý proces (tato situace nastane např. po vytvoření procesu voláním fork()). Dokud procesy z paměti pouze čtou, přistupují
ke sdílené stránce. Pokud se proces pokusí obsah stránky změnit, vyvolá výjimku. Jádro zkopíruje stránku, přidělí procesu kopii, která už je privátní a
proces ji může dále libovolně měnit. Ostatní procesy používají stále nezměněnou původní stránku.
stránky k odložení se hledají algoritmem NRU (not recently used): každá
stránka má příznaky referenced a modified, na začátku vynulované. Při prvním přístupu se nastaví referenced, při změně modified. Oba příznaky se periodicky nulují. Přednostně se uvolňují stránky, které nejsou modifikované ani použité.
Stránky kódu programu a mapovaných souborů se neukládají do odkládacího prostoru, ale obnovují se z příslušného souboru.

94

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

• po ukončení procesu voláním exit() nebo v reakci na signál přechází proces
do stavu mátoha (zombie), protože jádro si musí pamatovat k číslu procesu jeho návratovou hodnotu. Celá paměť procesu je uvolněna, zbývá pouze
struktura proc. Proces lze definitivně zrušit, až když se jeho rodič zeptá na
návratovou hodnotu voláním wait().
• v dnešních UNIXech se obvykle do odkládací oblasti na disku (swap area)
neodkládají celé procesy, ale jednotlivé stránky paměti.
• proces je uspán, když o to sám požádá, např. začne čekat na dokončení periferní operace. Preempce je naopak nedobrovolné odebrání procesoru plánovačem.

95

Plánování procesů
• preemptivní plánování – jestliže se proces nevzdá procesoru (neuspí
se čekáním na nějakou událost), je mu odebrán procesor po uplynutí
časového kvanta.
• procesy jsou zařazeny do front podle priority, procesor je přidělen
vždy prvnímu připravenému procesu z fronty, která má nejvyšší
prioritu.
• v SVR4 byly zavedeny prioritní třídy a podpora procesů reálného
času (real-time) s garantovanou maximální dobou odezvy.
• na rozdíl od předchozích verzí znamená v SVR4 vyšší číslo vyšší
prioritu.

• základem preemptivního plánování jsou pravidelná přerušení od časovače,
která odeberou procesor běžícímu procesu a předají řízení jádru (aktivuje se
plánovač procesů).
• jiná varianta je nepreemptivní (kooperativní) plánování, kdy proces běží, dokud se sám nevzdá procesoru, tj. dokud nezavolá takovou systémovou funkci,
která přepne kontext na jiný proces. Nevýhodou kooperativního plánování
je, že jeden proces může stále blokovat procesor a ostatní procesy se nikdy
nedostanou na řadu.
• UNIX používá pouze preemptivní plánování pro uživatelské procesy.
• tradiční UNIXové jádro funguje kooperativním způsobem, tj. proces běžící v
režimu jádra není přeplánován, dokud se sám nevzdá procesoru. Jádra moderních UNIXů jsou již preemtivní – je to hlavně kvůli real-time systémům;
tam je potřeba mít možnost běžící proces zbavit procesoru okamžitě, nečekat
na to, až se vrátí z režimu jádra nebo se sám uspí.
• při preemptivním plánování může být proces kdykoliv přerušen a řízení předáno jinému procesu. Proces si proto nikdy nemůže být jistý, že určitou
operaci (více než jednu intstrukci, kromě systémových volání se zaručenou
atomičností) provede atomicky, bez ovlivnění ostatními procesy. Pokud je
třeba zajistit atomičnost nějaké akce, musí se procesy navzájem synchronizovat. Při kooperativním plánování problém synchronizace odpadá (atomická
posloupnost operací se zajistí tím, že se proces během ní nevzdá procesoru).

96

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

• systémová třída je používána pouze jádrem, uživatelský proces běžící v režimu jádra si ponechává svou plánovací charakteristiku.
• procesy ve třídě reálného času mají nejvyšší prioritu, proto musí být správně
nakonfigurovány, aby nezablokovaly zbytek systému.
• jestliže je proces ve třídě sdílení času uspán a čeká na nějakou událost, je mu
dočasně přiřazena systémová priorita. Po probuzení se takový proces dostane
na procesor dříve, než ostatní procesy, které nespí.
• pevná část priority procesu ve třídě sdílení času se dá nastavit pomocí
int setpriority(int which, id t who, int nice );
nebo
int nice(int incr );

97

Skupiny procesů, řízení terminálů
• každý proces patří do skupiny procesů, tzv. process group
• každá skupina může mít vedoucí proces, tzv. group leader
• každý proces může mít řídící terminál (je to obvykle login terminál),
tzv. controlling terminal
• speciální soubor /dev/tty je asociován s řídícím terminálem
každého procesu
• každý terminál je asociován se skupinou procesů, tato skupina se
nazývá řídící skupina (controlling group)
• kontrola jobů (job control) je mechanizmus, jak pozastavovat a
znovu probouzet skupiny procesů a řídit jejich přístup k terminálům
• session (relace) je kolekce skupin procesů vytvořená pro účely řízení
jobů

• když se uživatel přihlásí do systému, je vytvořená nová relace, která se skládá
z jedné skupiny procesů, ve které je jeden proces – ten který vykonává uživatelův shell. Tento proces je zároveň vedoucí této jediné skupiny procesů a
také je vedoucí relace. V případě, že job control je povolen, každý příkaz nebo
kolona příkazů vytvoří novou skupinu procesů, jeden z procesů v každé skupině se vždy stane vedoucím procesem dané skupiny. Jedna ze skupin může
běžet na popředí, ostatní běží na pozadí. Signály které jsou generované
z klávesnice (tj. stiskem kombinace kláves, nemyslí se tím spuštění
příkazu kill!) jsou zaslány pouze skupině, která běží na popředí.
• pokud job control není zapnut, znamená spustění příkazu na pozadí pouze
to, že shell nečeká na jeho ukončení. Existuje pouze jedna skupina procesů,
signály z klávesnice se posílají všem procesům bežícím na popředí i na pozadí.
Nelze přesouvat procesy z pozadí na popředí a naopak.
• když proces, který má kontrolní terminál, otevře soubor /dev/tty, tak se
asociuje se svým kontrolním terminálem. Tj. pokud dva různé procesu z
různých relací otevřou tento soubor, přistupují oba k různým terminálům.

98

Identifikace procesu
pid t getpid(void);
• vrací process ID volajícího procesu.
pid t getpgrp(void);
• vrací ID skupiny procesů, do které patří volající proces.
pid t getppid(void);
• vrací process ID rodiče.
pid t getsid(pid t pid );
• vrací group ID vedoucího procesu session (sezení, terminálové
relace) pro proces pid (0 znamená pro volající proces)

skupiny procesů umožňují posílat signály najednou celé skupině.
session (relace, sezení) je kolekce procesů vytvořená pro účely řízení prací (job
control ). Procesy sezení sdílejí jeden řídící terminál. Session zahrnuje jednu
nebo více skupin procesů. Max. jedna skupina v rámci sezení běží na popředí
(foreground process group) a má přístup k řídicímu terminálu pro vstup i
výstup, ostatní běží na pozadí (background process groups) a mají k řídicímu
terminálu přístup volitelně jen pro výstup nebo vůbec (nepovolená operace
s terminálem pozastaví proces). Proces, který ještě není vedoucím skupiny
procesů, se může stát vedoucím sezení a zároveň skupiny procesů voláním
setsid(). Jestliže proces už je vedoucím skupiny, setsid() selže, pak je
třeba provést fork() a setsid() zavolat v synovském procesu. Takový proces nemá řídicí terminál, může ho získat otevřením terminálu, který ještě
není řídicím terminálem sezení, když při open() neuvede příznak O NOCTTY,
nebo jiným implementačně závislým způsobem.
rodičovský proces: Každý proces (kromě swapperu, pid == 0) má rodiče, tj.
proces, který ho stvořil voláním fork(). Jestliže rodič skončí dříve než dítě,
adoptivním rodičem se stává proces init s pid == 1, který se také postará
o uklizení zombie po skončení procesu.

99

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

• dítě je přesnou kopií rodiče, liší se PID, dále parent PID a některé další
podrobnosti (účtovací časy se nastaví na 0, nedědí se nastavení alarm() a
zámky souborů).
• pro urychlení a menší spotřebu paměti se adresový prostor nekopíruje, ale
používá se mechanismus copy-on-write.
• je logické, že otec dostane jako návratovou hodnotu volání fork PID syna a
syn 0; syn si může velmi jednoduše svůj vlastní PID zjistit. Otec by ale již
neměl možnost jednoduše zjistit, jaký je PID syna který byl právě vytvořen,
navíc v situaci, kdy již vytvořil dříve syny jiné.

100

Spuštění programu: exec
extern char **environ;
int execl(const char *path, const char *arg0, ... );
• spustí program, jehož kód je v souboru path, další argumenty volání
se předají spuštěnému programu v parametrech argc a argv funkce
main(). Seznam argumentů je ukončen pomocí (char *)0, tj.
NULL. Argument arg0 by měl být stejný jako path.
• úspěšné volání execl() se nikdy nevrátí, protože spuštěný program
zcela nahradí dosavadní adresový prostor procesu.
• program dědí proměnné prostředí, tj. obsah environ.
• handlery signálů se nahradí implicitní obsluhou.
• zavřou se deskriptory souborů, které mají nastavený příznak
FD CLOEXEC (implicitně není nastaven).

• v path musí být celá (absolutní nebo relativní) cesta ke spustitelnému souboru. Obsah proměnné prostředí PATH se používá jen při voláních execlp()
a execvp(), když argument path neobsahuje znak ‘ /‘ .
• novější UNIXy umí spouštět i skripty, které začínají řádkem
#!/interpreter path /interpreter name [args]
• někdy se používá argv[0] různé od jména spustitelného souboru. Např.
login vloží na začátek jména spouštěného shellu znak ‘ -‘ . Shell podle toho
pozná, že má fungovat jako login-shell, tj. spustit /etc/profile.

101

Varianty služby exec
int execv(const char *path, char *const argv []);
• obdoba execl(), ale argumenty jsou v poli argv, jehož poslední
prvek je (char *)0.
int execle(const char *path, const char *arg0, ... ,
char *const envp []);
• obdoba execl(), ale místo environ se použije envp.
int execve(const char *path, char *const argv [],
char *const envp []);
• obdoba execv(), ale místo environ se použije envp.
int execlp(const char *file, const char *arg0, ...);
int execvp(const char *file,char *const argv []);
• obdoby execl() a execv(), ale pro hledání spustitelného souboru
se použije proměnná PATH.

• kromě execlp() a execvp() je nutné vždy zadávat celou cestu.
• všechny varianty kromě execle() a execve() předávají spouštěnému programu své aktuální prostředí, tj. obsah pole environ.

102

Formát spustitelného souboru
• Common Object File Format (COFF) – starší System V
• Extensible Linking Format (ELF) – nový v SVR4
• často se mluví o a.out formátu, protože tak se jmenuje (pokud není
použit přepínač -o) výstup linkeru.
• Formát ELF:

hlavička souboru
tabulka programových hlaviček
sekce 1
..
.
sekce N
tabulka hlaviček sekcí

• hlavička souboru (ELF header ) obsahuje základní informace o souboru.
• tabulka programových hlaviček (program header table) je přítomna pouze u
souborů obsahujících spustitelné programy. Obsahuje informaci o rozvržení
virtuální paměti procesu.
• sekce obsahují instrukce, data, tabulku symbolů, relokační data, apod.
• tabulka hlaviček sekcí (section header table) obsahuje služební informace pro
linker.

103

Ukončení procesu
void exit(int status );
• ukončí proces s návratovým kódem status.
• nikdy se nevrátí na instrukci následující za voláním.
pid t wait(int *stat loc );
• počká, až skončí některý synovský proces, vrátí jeho PID a do
stat_loc uloží návratový kód, který lze dále testovat:
– WIFEXITED(stat val) . . . proces volal exit()
– WEXITSTATUS(stat val) . . . argument exit()
– WIFSIGNALED(stat val) . . . proces dostal signál
– WTERMSIG(stat val) . . . číslo signálu
– WIFSTOPPED(stat val) . . . proces pozastaven
– WSTOPSIG(stat val) . . . číslo signálu
pid t waitpid(pid t pid, int *stat loc, int opts );
• čekání na jeden proces.

• _exit() . . . jako exit(), ale neprovádí se flush stdio streamů a nevolají se
funkce nastavené pomocí atexit()
• ve standardu je ještě
WIFCONTINUED(stat val) . . . pokračování po zastavení
• opts ve waitpid() – OR-kombinace:
– WCONTINUED . . . vrátí status procesu, který nebyl testován od pokračování procesu po zastavení
– WNOHANG . . . nečeká, pokud není status okamžitě k dispozici
– WUNTRACED . . . vrátí status zastaveného procesu, který nebyl testován
po jeho zastavení
• pid ve waitpid():
– == -1 . . . libovolné dítě
– > 0 . . . jedno dítě
– == 0 . . . dítě ve stejné skupině procesů jako volající proces
– < -1 . . . dítě ve skupině abs(pid)
• rodič by měl vždy na své děti zavolat wait() nebo waitpid(), protože jinak
se v systému hromadí zombie (ukončené procesy, které pouze čekají, až si
rodič přečte jejich návratovou hodnotu).

104

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

toto je klasický způsob jak spustit nějaký program a po jeho skončení pokračovat. Rodič nemusí jen čekat na ukončení potomka, ale může vykonávat dál svůj
kód.

105

Roura: pipe()
int pipe(int fildes [2]);
• vytvoří rouru a dva deskriptory
– fildes[0] . . . čtení z roury
– fildes[1] . . . zápis do roury
• roura zajišťuje synchronizaci čtení a zápisu:
– zapisující proces se zablokuje, když je roura plná,
– čtoucí proces se zablokuje, když je roura prázdná.
• čtoucí proces přečte konec souboru (tj. read() vrátí 0), pokud jsou
uzavřeny všechny kopie fildes[1].
• pojmenovaná roura (vytvořená voláním mkfifo()) funguje stejně,
ale má přidělené jméno v systému souborů a mohou ji tedy používat
libovolné procesy.

• nepojmenovanou rouru vytváří jeden proces a může ji předat pouze svým
potomkům (pomocí deskriptorů zděděných při fork()). Toto omezení se dá
obejít pomocí předání otevřeného deskriptoru přes unix-domain socket.
• jestliže funkce write() zapíše do roury nejvýše PIPE BUF (systémová konstanta) bajtů, je zaručeno, že zápis bude atomický, tj. tato data nebudou
proložena daty zapisovanými současně jinými procesy.

106

Příklad: roura mezi dvěma procesy
shell: ls / | more

int pd[2];
pipe(pd);
switch(fork()) {

producent (dítě)

konzument (rodič)
default:

case 0:
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
/bin/more

/bin/ls

• zavření zápisového deskriptoru pd[1] (ozn. .) v procesu konzumenta je nutné,
protože jinak se na rouře nikdy nedetekuje konec souboru.
• čtecí deskriptor v procesu producenta pd[0] je také vhodné zavírat (ozn. .),
protože když konzument předčasně skončí, dostane producent signál SIGPIPE.
Kbyby deskriptor v producentovi nebyl zavřen, producent se nedozví, že konzument skončil, a po naplnění bufferu roury v jádru se zablokuje.
• pokud nemáme jistotu, že před voláním pipe() byl otevřen deskriptor 0, musíme v producentovi použít dup2(pd[1], 1), protože dup(pd[1]) by mohl
vrátit deskriptor 0 místo požadovaného 1. Také je třeba testovat, zda neplatí
pd[1] == 1, abychom si nechtěně nezavřeli rouru. Podobně je třeba otestovat
pd[0] == 0 v konzumentovi.
• je lepší vytvářet rouru od syna k otci, protože typicky nejdřív skončí proces
zapisující do roury, čtoucí proces přečte zbylá data, zpracuje je, něco vypíše
a teprve pak skončí.
shell čeká na otce, takže když směřuje roura od otce k synovi, otec skončí,
shell vypíše prompt, ale pak ještě syn vypíše výstup. Možným řešením je
čekání otce na skončení syna, jenže to se nedá zajistit, pokud otec provede
exec.
• původní Bourne shell staví rouru tak, že poslední proces v rouře vytvoří
předposlední jako svého syna, ten vytvoří předchozí proces a tak se postupuje
až k začátku roury.
• v shellu bash jsou všechny procesy v rouře přímo potomky shellu (shell volá
fork() tolikrát, jak dlouhá je roura). Shell před vypsáním promptu čeká, až
všechny procesy roury skončí.
107

Sdílená paměť – úvod
• pajpy a soubory jako metody meziprocesové komunikace vyžadují
systémová volání
• výhoda: procesy nemohou poškodit adresový prostor jiného procesu
• nevýhoda: velká režie pro systémová volání, typicky read, write
• sdílená paměť je namapování části paměti do adresového prostoru
více procesů
• odstranění nevýhody, ztráta dosavadní výhody
• synchronizace přístupu do sdílené paměti
– System V semafory
– POSIX semafory bez nutnosti systémového volání v běžném
případě

• mapování souborů do paměti je jednou z implementací sdílené paměti. Pro
popis úseku sdílené paměti používá soubor.
• takto implementovaná sdílená paměť je tedy pravidelně zapisována na disk
• pro sdílení bez režie zápisu změněných dat na disk je možné použít memory
based filesystém, například tmpfs (Solaris, NetBSD – zde byl tmpfs napsán
jako součást letošního Summer of Code sponzorovaného firmou Google, FreeBSD má podobnou vlastnost pod názvem memory disk ). Jako tzv. backing
store pro paměťové stránky patřící těmto filsystémům je obecně možné použít
swap oblast na disku.

108

Mapování souborů do paměti (1)
void *mmap(void *addr, size t len, int prot, int flags,
int fildes, off t off );
• do paměťového prostoru procesu od adresy addr (0 . . . adresu přidělí
jádro) namapuje úsek délky len začínající na pozici off souboru
reprezentovaného deskriptorem fildes.
• vrací adresu namapovaného úseku nebo MAP FAILED.
• v prot je OR-kombinace PROT READ (lze číst), PROT WRITE (lze
zapisovat), PROT EXEC (lze spouštět), nebo PROT NONE (nelze
k datům přistupovat).
• ve flags je OR-kombinace MAP PRIVATE (změny jsou privátní pro
proces, neukládají se do souboru), MAP SHARED (změny se ukládají
do souboru), MAP FIXED (jádro nezmění addr).

• mapování souborů do paměti je alternativou ke zpracování souborů pomocí
read(), write(), lseek(). Po namapování lze se souborem pracovat jako s
datovou strukturou v paměti. Soubor se nekopíruje celý do paměti, alokují
se pouze stránky na které se přistupuje. Pokud je potřeba stránku uvolnit,
obsah se ukládá zpět do souboru (při MAP SHARED) nebo do swapu – používá
se mechanismus copy-on write (při MAP PRIVATE).
• hodnota off+len může překračovat aktuální velikost souboru.
• mapuje se vždy po celých stránkách, hodnoty off (a při MAP FIXED i addr)
musí být správně zarovnané. Poslední stránka je za koncem souboru doplněna
nulami a tento úsek se nikdy nepřepisuje do souboru.
• přístup do namapovaného úseku, ale za poslední existující stránku namapovaného objektu, způsobí signál SIGBUS.
• namapování souboru nahradí případné předchozí mapování stránek v rozsahu
addr až addr+len.
• existující rozšíření:
– příznak MAP ANONYMOUS v Linuxu – vytvoření anonymního segmentu bez
vazby na soubor (není třeba zadávat platný deskriptor souboru). Ve
FreeBSD dělá totéž příznak MAP ANON, deskriptor musí být -1.
– v IRIXu lze pomocí MAP AUTOGROW automaticky zvětšit namapovaný objekt při přístupu za jeho stávající konec.

109

Mapování souborů do paměti (2)
int msync(void *addr, size t len, int flags );
• zapíše změněné stránky v úseku len bajtů od adresy addr do
souboru. Hodnota flags je OR-kombinace
– MS ASYNC . . . asynchronní zápis
– MS SYNC . . . synchronní zápis
– MS INVALIDATE . . . zrušit namapovaná data, která se liší od
obsahu souboru
int munmap(void *addr, size t len );
• zapíše změny a zruší mapování souboru v délce len od adresy addr.
int mprotect(void *addr, size t len, int prot );
• změní přístupová práva k namapovanému úseku souboru. Hodnoty
prot jsou stejné jako u mmap().

• uložení změn do souboru na disk je zaručené až po provedení msync() nebo
munmap(), ale ostatní procesy, které mají soubor namapován, vidí změny
hned.
• mapování paměti a nastavování přístupových práv používá např. knihovna
Electric Fence, která slouží pro ladění chyb při práci s dynamickou pamětí.

110

Příklad: mapování souborů do paměti
int main(int argc, char *argv[])
{
int fd, fsz; char *addr, *p1, *p2, c;
fd = open(argv[1], O RDWR);
fsz = lseek(fd, 0, SEEK END);
p1 = addr = mmap(0, fsz, PROT READ|PROT WRITE,
MAP SHARED, fd, 0);
p2 = p1 + fsz - 1;
while(p1<p2) {
c = *p1; *p1++ = *p2; *p2-- = c;
}
munmap(addr, fsz);
close(fd);
exit(0);
}

Tento program otočí pořadí znaků v souboru (zapíše soubor od konce k začátku).

111

Dynamický přístup ke knihovnám
void *dlopen(const char *file, int mode );
• zpřístupní knihovnu v souboru file, vrátí handle nebo NULL.
• v mode je OR-kombinace RTLD NOW (okamžité relokace), RTLD LAZY
(odložené relokace), RTLD GLOBAL (symboly budou globálně
dostupné), RTLD LOCAL (nebudou globálně dostupné).
void *dlsym(void *handle, const char *name );
• vrátí adresu symbolu zadaného jména z knihovny.
int dlclose(void *handle );
• ukončí přístup ke knihovně.
char *dlerror(void);
• vrátí textový popis chyby při práci s knihovnami.

• pomocí těchto funkcí lze implementovat dynamicky nahrávané plug-in moduly načítané aplikací podle potřeby (např. podle obsahu jejího konfiguračního souboru).
• dynamickým načítáním knihoven se také dá vyřešit situace, kdy potřebujeme
využít několik knihoven, které definují symbol se stejným jménem. Jedna
knihovna se přímo přilinkuje k programu, k ostatním se přistupuje pomocí
dlopen().
• soubor musí být ve správném formátu (sdílená knihovna .so ve formátu
ELF ).
• konstanty pro mode:
– RTLD NOW . . . všechny relokace (vyřešení všech odkazů) jsou provedeny
okamžitě po natažení knihovny, aplikace má jistotu, že jsou všechny
symboly přístupné
– RTLD LAZY . . . relokace mohou být odloženy až do chvíle použití symbolu
– RTLD GLOBAL . . . symboly z knihovny mohou být použity při zpracování
relokací v ostatních knihovnách a jsou dostupné pomocí
dlopen(0, RTLD GLOBAL)
• speciální handle RTLD NEXT . . . hledá symbol pouze v knihovnách nahraných
po knihovně, ve které je volání dlsym(). Hodí se pro předefinování existujících
funkcí, pokud v redefinované funkci potřebujeme volat původní. Knihovna
s novou funkcí se nahrává jako první (např. pomocí environmentové proměnné LD PRELOAD), adresu původní funkce získá voláním dlsym(RTLD NEXT,
fun name ).

112

Příklad: zpřístupnění knihovny
void *handle; char *libname = "libm.so", *fun name = "sin";
double x = 1.3, y, (*fun)(double);
if( !(handle = dlopen(libname, RTLD NOW)) ) {
fprintf(stderr, "%s\n", dlerror());
exit(1);
}
fun = dlsym(handle, fun name);
if(err = dlerror()) {
fprintf(stderr, "%s\n", err);
exit(1);
}
y=fun(x);
dlclose(handle);

• zde se volá funkce sin() z matematické knihovny libm.so.
• funkce dlsym() vrátí adresu symbolu daného jména, ale vždy jako ukazatel
na void, neprobíhá žádná typová kontrola ani není k dispozici žádná informace o typu symbolu. Ten, kdo tuto adresu používá, musí zajistit její správné
přetypování.
• při použití knihoven v C++ je třeba si uvědomit, že C++ používá name
mangling, tj. do jména funkce (metody) je zakódováno případné jméno třídy
nebo namespace a typy parametrů.

113

Signály
• informují proces o výskytu určité události.
• na uživatelské úrovni zpřístupňují mechanismy přerušení.
• kategorie signálů:
– chybové události generované běžícím procesem, např. pokus o
přístup mimo přidělenou oblast paměti (SIGSEGV)
– asynchronní události vznikající mimo proces, např. signál
poslaný jiným procesem, vypršení nastaveného času (SIGALRM),
odpojení terminálu (SIGHUP), stisk Ctrl-C (SIGINT)
• nejjednodušší mechanismus pro komunikaci mezi procesy – nesou
pouze informaci o tom, že nastala nějaká událost.
• zpracovávají se asynchronně – příchod signálu přeruší běh procesu a
vyvolá handler.

• se signálem není svázána žádná jiná informace než číslo signálu.
• po návratu z handleru (pokud k němu dojde) proces pokračuje od místa
přerušení.
• historicky signály vznikly jako mechanismus pro „násilnéÿ ukončení procesu.
Z toho vyplynul i název funkce kill() pro poslání signálu.

114

Poslání signálu
int kill(pid t pid, int sig );
• pošle signál s číslem sig procesu (nebo skupině procesů) podle
hodnoty pid:
– > 0 . . . procesu s číslem pid
– == 0 . . . všem procesům ve stejné skupině
– == -1 . . . všem procesům, kromě systémových
– < -1 . . . procesům ve skupině abs(pid)
• sig == 0 znamená, že se pouze zkontroluje oprávnění poslat signál,
ale žádný signál se nepošle.
• právo procesu poslat signál jinému procesu závisí na UID obou
procesů.

• proces s EUID == 0 může poslat signál libovolnému procesu.
• ostatní procesy:
– Linux, Solaris: RUID nebo EUID procesu, který poslal signál, se musí
shodovat s reálným UID nebo saved set-user-ID cílového procesu.
– FreeBSD: musí se shodovat EUID obou procesů.
– IRIX: RUID nebo EUID procesu, který poslal signál, se musí shodovat s
reálným nebo efektivním UID nebo saved set-user-ID cílového procesu.

115

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
signály SIGKILL a SIGSTOP vždy vyvolají implicitní akci (zrušení, resp.
pozastavení).

většina signálů implicitně ukončí proces, některé navíc způsobí vytvoření souboru core, který je možné použít pro ladicí účely.

116

Přehled signálů (1)
signály je možné logicky rozdělit do několika skupin. . .
detekované chyby:
SIGBUS

přístup k nedef. části paměťového objektu (core)

SIGFPE

chyba aritmetiky v pohyblivé čárce (core)

SIGILL

nepovolená instrukce (core)

SIGPIPE

zápis do roury, kterou nikdo nečte (exit)

SIGSEGV

použití nepovolené adresy v paměti (core)

SIGSYS

chybné systémové volání (core)

SIGXCPU

překročení časového limitu CPU (core)

SIGXFSZ

překročení limitu velikosti souboru (core)

• generování těchto signálů vychází z chyb programu
• pro signály BUS, FPE, ILL a SEGV není normou přesně definována příčina,
ale obvykle jsou to chyby detekované hardwarem
• pro tyto čtyči signály také platí tato speciální pravidla:
– pokud byly nastavené jako ignorované voláním sigaction, je jejich chování normou nedefinováno
– návratová hodnova handleru je nedefinována
– následek situace, kdy jeden z těchto signálu je maskován v okamžiku
jeho vygenerovaní je nedefinovaný
• jinými slovy – pokud je hardwarem detekovaná chyba reálná (signál není
poslán přes kill), váš program se přes tuto chybu nemusí vůbec dostat. Není
bezpečné chybu ignorovat, pokračovat v běhu po návratu z handleru nebo
oddálit řešení pomocí zamaskování. Pokud máte pro tyto signály handler, je
potřeba pořešit danou situaci jak uznáte za vhodné a pak ukončit
program.
• poznámka: pokud je něco normou nedefinováno (undefined ), obecně to znamená, že se neočekává, že by programátor potřeboval znát přesné chování v
takové situaci. Pokud je to potřeba, pravděpodobně je ve vašem programu
něco špatně. Jako vždy, určite by se našly vyjímky potvrzující pravidlo.

117

Přehled signálů (2)
generované uživatelem nebo aplikací:
SIGABRT

ukončení procesu (core)

SIGHUP

odpojení terminálu (exit)

SIGINT

stisk speciální klávesy Ctrl-C (exit)

SIGKILL

zrušení procesu (exit, nelze ošetřit ani ignorovat)

SIGQUIT

stisk speciální klávesy Ctrl-\ (core)

SIGTERM

zrušení procesu (exit)

SIGUSR1

uživatelsky definovaný signál 1 (exit)

SIGUSR2

uživatelsky definovaný signál 2 (exit)

• SIGINT a SIGQUIT jsou obvykle generovány z terminálu (Ctrl-C a Ctrl-\)
a lze je předefinovat příkazem stty nebo pomocí funkce tcsetattr().
• SIGTERM je defaultní signál pro příkaz kill
• SIGUSR1 a SIGUSR2 nejsou použity žádným systémovým voláním a jsou plně
k dispozici uživateli
• SIGALRM a související funkce alarm() se používají pro odměřování časových
intervalů v uživatelském procesu (např. při implementaci timeoutů).
• signál SIGHUP se často používá jako způsob, jak oznámit běžícímu démonu,
že se změnil jeho konfigurační soubor a má si ho proto znovu načíst.
• klávesy Ctrl-C a Ctrl-\ lze předefinovat příkazem stty

118

Přehled signálů (3)
job control:
SIGCHLD

změna stavu synovského procesu (ignore)

SIGCONT

pokračování pozastaveného procesu (continue)

SIGSTOP

pozastavení (stop, nelze ošetřit ani ignorovat)

SIGTSTP

pozastavení z terminálu Ctrl-Z (stop)

SIGTTIN

čtení z terminálu procesem na pozadí (stop)

SIGTTOU

zápis na terminál procesem na pozadí (stop)

• platí, že nikdy není povoleno více procesům najednou číst z
kontrolního terminálu, ale více procesů najednou může na terminál
zapisovat.

Přehled signálů (4)
časovače:
SIGALRM

plánované časové přerušení (exit)

SIGPROF

vypršení profilujícího časovače (exit)

SIGVTALRM

vypršení virtuálního časovače (exit)

různé:
SIGPOLL

testovatelná událost (exit)

SIGTRAP

ladicí přerušení (core)

SIGURG

urgentní událost na soketu (ignore)

119

Nastavení obsluhy signálů
int sigaction(int sig, const struct sigaction *act,
struct sigaction *oact );
• nastaví obsluhu signálu sig podle act a vrátí předchozí nastavení
v oact.
• obsah struktury sigaction:
– void(*sa handler )(int) . . . SIG DFL, SIG IGN, nebo adresa
handleru
– sigset t sa mask . . . signály blokované v handleru, navíc je
blokován signál sig
– int sa flags . . . SA RESETHAND (při vstupu do handleru
nastavit SIG DFL), SA RESTART (restartovat přerušená systémová
volání), SA NODEFER (neblokovat signál sig během obsluhy)

• když je act == NULL, pouze se zjistí nastavení obsluhy, nemění se. Jestliže
nás předchozí nastavení nezajímá, lze použít oact == NULL.
• pokud není nastaveno SA RESTART, systémová volání aktivní v bodě příchodu
signálu skončí s chybou EINTR. Restartování nemusí fungovat pro všechna
systémová volání, např. na FreeBSD je select() přerušen signálem vždy, i
když je nastaveno SA RESTART.
• pozor na problém vzájemného vyloučení mezi procesem a handlerem, popř.
mezi handlery pro různé signály. Jestliže je nastaveno SA NODEFER, měl by
být handler reentrantní.
• v signálovém handleru by se měly používat pouze funkce, které jsou pro
takové použití bezpečné. Musí buď být reentrantní, nebo je nutné zajistit,
aby nepřišel signál v nevhodnou dobu (např. uvnitř funkce přijde signál, v
jehož handleru se volá stejná funkce). Bezpečné funkce ze systémové knihovny
jsou vyjmenovány v manuálové stránce k funkci sigaction() (v SUSv3 jsou
v kapitole System Interfaces: General Information, Signal Concepts).
• funkce sigaction() je obecnější než starší funkce signal() a sigset().
• pro výskok z handleru signálu jinam než na místo vzniku signálu se dají použít funkce sigsetjmp() a siglongjmp(). Pozor na to, že v tomto případě
si musíme být jisti, že v okamžiku příchodu signálu není program uvnitř
nereentrantní funkce. Výskokem z handleru do hlavního programu není vykonávání takové funkce ukončeno a mohou nastat stejné problémy jako při
volání nereentrantní funkce přímo z handleru.

120

Příklad: časově omezený vstup
#define BUFSZ 4096
void handler(int sig)
{ fprintf(stderr," !!! TIMEOUT !!! \n"); }
int main()
{
char buf[BUFSZ]; struct sigaction act; int sz;
act.sa handler = handler;
sigemptyset(&act.sa mask); act.sa flags = 0;
sigaction(SIGALRM, &act, NULL); alarm(5);
sz = read(0, buf, BUFSZ);
if(sz > 0)
write(1, buf, sz);
exit(0);
}

• lze používat i časovače s jemnějším rozlišením než 1 s. Nastavují a testují se
funkcemi setitimer() a getitimer(). Při vypršení posílají signály procesu,
který časovače nastavil:
– ITIMER REAL . . . měří reálný čas, posílá SIGALRM
– ITIMER VIRTUAL . . . měří virtuální čas (pouze čas, kdy proces běží),
posílá SIGVTALRM
– ITIMER PROF . . . měří virtuální čas a čas, kdy systém běží na konto
procesu, posílá SIGPROF
• v příkladu je drobný problém: funkce fprintf() není bezpečná pro použití
v handleru signálu.

121

Blokování signálů
• blokované signály budou procesu doručeny a zpracovány až po
odblokování.
int sigprocmask(int how, const sigset t *set,
sigset t *oset );
• nastaví masku blokovaných signálů a vrátí starou masku.
• pro manipulaci s maskou signálů slouží funkce: sigaddset(),
sigdelset(), sigemptyset(), sigfillset(), sigismember()
int sigpending(sigset t *set );
• vrátí čekající zablokované signály.

• je rozdíl mezi ignorováním a blokováním signálu. Ignorovaný signál jádro
zahodí a proces ho nedostane, blokovaný signál proces dostane po jeho odblokování.
• závisí na implementaci, zda při vícenásobném doručení stejného signálu procesu, který má tento signál zablokovaný, bude signál po odblokování ošetřen
jednou nebo vícekrát.

122

Příklad: blokování signálů
sigset t sigs, osigs; structure sigaction sa;
sigfillset(&sigs); sigprocmask(SIG BLOCK, &sigs, &osigs);
switch(cpid = fork()) {
case -1: /* Chyba */
sigprocmask(SIG SETMASK, &osigs, NULL);
...
case 0: /* Synovský proces */
sa.sa handler = h cld; sigemptyset(&sa.sa mask);
sa.sa flags = 0;
sigaction(SIGINT, &sa, NULL);
sigprocmask(SIG SETMASK, &osigs, NULL);
...
default: /* Rodičovský proces */
sigprocmask(SIG SETMASK, &osigs, NULL);
...
}

• blokování je vhodné použít tam, kde ošetření přerušení uprostřed posloupnosti operací by bylo příliš složité, nebo kde korektní ošetření není jinak
možné.
• př.: proces vytváří potomky pomocí fork() a je potřeba, aby potomci měli
jiný handler signálů než rodičovský proces.
• v uvedeném příkladě by bez blokování signálů mohl synovský proces dostat
signál dřív, než stihne změnit handler.
• další příklad je proces, který při vypršení timeoutu přeruší prováděnou posloupnost operací voláním siglongjmp() zevnitř handleru signálu. Je potřeba zablokovat signál SIGALRM během provádění atomických podposloupností (tj. takových, které se musí provést buď celé, nebo vůbec ne).

123

Čekání na signál
int pause(void);
• pozastaví volající proces do příchodu signálu. Volání se vrátí po
návratu z handleru.
int sigsuspend(const sigset t *sigmask );
• jako pause(), ale navíc po dobu čekání masku blokovaných signálů
změní na sigmask.
int sigwait(const sigset t *set, int *sig );
• čeká na příchod signálu z množiny set (tyto signály musí být
předtím zablokované), číslo signálu vrátí v sig.
• nevolá se handler signálu (to ale není v normě jednoznačně
definováno).

pomocí těchto funkcí a blokování signálů se implementuje synchronní obsluha
signálů. Proces nejprve zablokuje signály, které ho zajímají, a pak na ně ve vhodných chvílích buď čeká, nebo jen testuje (pomocí sigpending()), zda signál přišel,
a pokud ne, pokračuje dál.

124

Problém: konflikt při sdílení dat
• máme strukturu struct { int a, b; } shared ;
• for(;;) {
a=shared.a; b=shared.b;
if(a!=b) printf("NEKONZISTENTNÍ STAV");
/* neatomická operace */
shared.a=val; shared.b=val;
}
• jestliže tento cyklus spustíme ve dvou různých procesech (nebo
vláknech), které obě sdílejí stejnou strukturu shared a mají různé
hodnoty val, bude docházet ke konfliktům.
• příčina: změna datové struktury ve zvýrazněném řádku není
atomická.

• ani operace, kterou lze v C zapsat jedním příkazem, nemusí být atomická.
Př.: na RISCových procesorech se příkaz a++ typicky přeloží jako sekvence
load reg,[a]
inc reg
store [a],reg
• obecně obdobný problém nastává, když více procesů sdílí nějaký systémový
zdroj.

125

Scénář konfliktu
Procesy A(val==1) a B(val==2)

a

b

1.

počáteční stav struktury

?

?

2.

proces A zapíše do položky a

1

?

3.

proces B zapíše do položky a

2

?

4.

proces B zapíše do položky b

2

2

5.

proces A zapíše do položky b

2

1

6.

struktura je v nekonzistentním
stavu a jeden z procesů to zjistí.

• další možnost (reálně se může stát spíše jen na multiprocesorovém systému):
1. struktura je v konzistentním stavu, např. (1, 1)
2. proces B zapíše 2 do položky a
3. proces A přečte hodnotu struktury (2, 1) dříve, než proces B stihne
zapsat položku b

126

Řešení: vzájemné vyloučení procesů
• je potřeba zajistit atomicitu operací nad strukturou, tzn. jeden
proces provádí modifikaci a dokud neuvede strukturu do
konzistentního stavu, druhý proces s ní nemůže manipulovat.
Procesy A(val==1) a B(val==2)

a

b

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

počáteční stav struktury

?

?

proces A zapíše do položky a

1

?

proces B musí čekat

1

?

proces A zapíše do položky b

1

1

proces B zapíše do položky a

2

1

6.

proces B zapíše do položky b

2

2

7.

Struktura je v konzistentním stavu.



• je třeba zajistit vzájemné vyloučení i při čtení, aby čtoucí proces nepřečetl
nekonzistentní obsah struktury uprostřed změn. Při zápisu je nutné vyloučit
všechny ostatní procesy, ale při čtení stačí vyloučit jen zápis, současné čtení
více procesy nevadí.
• kritická sekce – kus kódu, který by měl provádět pouze jeden proces (vlákno),
jinak může dojít k nekonzistencím (špatně pospojovaný vázaný seznam, neodpovídající si indexy v databázi, . . . ). Kritická sekce by měla být co nejkratší,
aby ostatní procesy (vlákna) žádající o vstup do této sekce čekaly co nejkratší
možnou dobu.

127

Problém: konflikt zapisovatelů a čtenářů
• několik běžících procesů zapisuje protokol o své činnosti do
společného log-souboru. Nový záznam je připojen vždy na konec
souboru.
• pokud zápis záznamu není proveden atomickou operací, může dojít
k promíchání více současně zapisovaných záznamů.
• zapisovat smí vždy pouze jeden proces.
• další procesy čtou data z log-souboru.
• při přečtení právě zapisovaného záznamu obdržíme nesprávná
(neúplná) data.
• během operace zápisu ze souboru nelze číst. Když nikdo nezapisuje,
může více procesů číst současně.

na lokálním disku lze pro synchronizaci zapisovatelů použít řešení pomocí O APPEND,
které ale nemusí fungovat např. na vzdáleném disku přístupném přes NFS nebo
v případě, že zápis jedné logovací zprávy je proveden více než jedním voláním
write(). Navíc to neřeší synchronizaci čtenářů – lze číst i v průběhu zápisu.

128

Řešení: zamykání souborů
• zapisující proces zamkne soubor pro zápis. Ostatní procesy
(zapisovatelé i čtenáři) se souborem nemohou pracovat a musí čekat
na odemčení zámku.
• čtoucí proces zamkne soubor pro čtení. Zapisovatelé musí čekat na
odemčení zámku, ale ostatní čtenáři mohou také zamknout soubor
pro čtení a číst data.
• v jednom okamžiku může být na souboru aktivní nejvýše jeden
zámek pro zápis nebo libovolně mnoho zámků pro čtení, ale ne oba
typy zámků současně.
• z důvodu efektivity by každý proces měl držet zámek co nejkratší
dobu a pokud možno nezamykat celý soubor, ale jen úsek, se kterým
pracuje. Preferované je pasivní čekání, aktivní čekání je vhodné jen
na velmi krátkou dobu.

dva způsoby čekání:
aktivní (busy waiting) – proces v cyklu testuje podmínku, na kterou čeká, dokud není splněna
pasivní – proces se zaregistruje v jádru jako čekající na podmínku a pak se uspí,
jádro ho probudí, když dojde ke splnění podmínky

129

Synchronizační mechanismy
• teoretické řešení – algoritmy vzájemného vyloučení (Dekker 1965,
Peterson 1981)
• zákaz přerušení (na 1 CPU stroji), speciální instrukce (test-and-set)
• lock-soubory
• nástroje poskytované operačním systémem
– semafory (součást System V IPC)
– zámky pro soubory (fcntl(), flock())
– synchronizace vláken: mutexy (ohraničují kritické sekce, pouze
jedno vlákno může držet mutex), podmínkové proměnné
(zablokují vlákno, dokud jiné vlákno nesignalizuje splnění
podmínky), read-write zámky (sdílené a exkluzivní zámky,
podobně jako pro soubory)

• obě řešení potřebovala k dosažení požadavaného výsledku pouze sdílenou
paměť, tj. několik proměnných sdílených oběma procesy
• Dekkerovo řešení se udává jako první řešení problému vzájemného vyloučení
dvou procesů, aniž by bylo nutné aplikovat naivní algoritmus striktního střídání, tj. pokud druhý proces nevykazoval zájem o vstup do kritické sekce,
mohl tam první (a naopak) proces vstoupit tolikrát za sebou, kolikrát chtěl.
Dekkerovo řešení není vůbec triviální, porovnejte s o 16 let mladším řešením
Petersonovým, například na en.wikipedia.org
• my se nebudeme zabývat teoretickými algoritmy vzájemného vyloučení ani
nebudeme popisovat hardwarové mechanismy používané jádrem. Zaměříme
se pouze na použití lock souborů (které využívají atomičnosti některých souborových operací) a speciálních synchronizačních nástrojů poskytovaných jádrem.
• podmínkové proměnné = conditional variables

130

Lock-soubory
• pro každý sdílený zdroj existuje dohodnuté jméno souboru. Zamčení
zdroje se provede vytvořením souboru, odemčení smazáním souboru.
Každý proces musí otestovat, zda soubor existuje, a pokud ano, tak
počkat.
void lock(char *lockfile) {
while( (fd = open(lockfile,
O RDWR|O CREAT|O EXCL, 0600)) == -1)
; /* Čekáme ve smyčce na odemčení */
close(fd);
}
void unlock(char *lockfile) {
unlink(lockfile);
}

• klíčem k úspěchu je samozřejmě použití flagu O EXCL
• při havárii procesu nedojde ke zrušení případných zámků a ostatní procesy
by čekaly věčně. Proto je vhodné si do lock-souboru poznamenat PID procesu, který zámek vytvořil. Proces, který čeká na odemčení, může testovat,
zda proces, kterému zámek patří, stále běží. Když ne, lze zámek zrušit a
znovu zkusit vytvořit. User level příkaz který toto umí a dovoluje používat lock soubory z shellových skriptů je například shlock(1) (na FreeBSD v
/usr/ports/sysutils/shlock), teoreticky by však mohl způsobit situaci z
následujícího odstavce.
• POZOR: jestliže více procesů najednou zjistí, že proces držící zámek už neexistuje, může dojít k následující chybě: Jeden proces smaže zámek a znovu
ho vytvoří se svým PID. Další proces udělá totéž, protože operace přečtení
obsahu souboru a jeho následného smazání není atomická. Teď si ale oba
procesy myslí, že získaly zámek!
• problém: funkce lock() obsahuje aktivní čekání na uvolnění zámku. Lze řešit
např. tak, že proces, který získá zámek, otevře pro zápis pojmenovanou rouru.
Čekající procesy se uspí tím, že zkusí číst z roury. Součástí unlock() bude i
zavření roury a tím uvolnění čekajících procesů.

131

Zamykání souborů: fcntl()
int fcntl(int fildes, int cmd, ...);
• k nastavení zámků pro soubor fildes se používá cmd:
– F GETLK . . . vezme popis zámku z třetího argumentu a nahradí
ho popisem existujícího zámku, který s ním koliduje
– F SETLK . . . nastaví nebo zruší zámek popsaný třetím
argumentem, pokud nelze zámek nastavit, ihned vrací −1
– F SETLKW . . . jako F SETLK, ale uspí proces, dokud není možné
nastavit zámek
• třetí argument obsahuje popis zámku a je typu struct flock *

• zamykání souborů sdílených přes NFS zajišťuje démon lockd.
• zámky jsou obecně dvou typů:
advisory locks – pro správnou funkci musí všechny procesy pracující se
zámčenými soubory konstrolovat zámky před čtením nebo zápisem souboru; jsou více používané
mandatory locks – jestliže je na souboru zámek, budou čtecí a zápisové
operace se souborem automaticky zablokovány, tj. zámek se uplatní i v
procesech, které ho explicitně nekontrolují
– nedoporučují se, ne vždy fungují (např. lockd implementuje pouze
advisory locking)
– pro určitý soubor se zapne nastavením bitu SGID a zrušením práva
spuštění pro skupinu (tj. nastavení, které jinak nemá smysl - mít
set UID executable bit na souboru, který není spustitelný). Systém,
který mandatory locking implementuje, je například Solaris nebo
Linux, FreeBSD tuto vlastnost naopak nepodporuje.

132

Zamykání souborů: struct flock
• l type . . . typ zámku
– F RDLCK . . . sdílený zámek (pro čtení), více procesů
– F WRLCK . . . exkluzivní zámek (pro zápis), jeden proces
– F UNLCK . . . odemčení
• l whence . . . jako u lseek(), tj. SEEK SET, SEEK CUR, SEEK END
• l start . . . začátek zamykaného úseku
• l len . . . délka úseku, 0 znamená do konce souboru
• l pid . . . PID procesu držícího zámek, používá se jen pro F GETLK

• soubory se dají zamykat po částech a dá se zjistit, který proces drží zámek.
Při ukončení procesu se automaticky uvolní všechny jeho zámky.
• pokud při použití F GETLK není příslušná část souboru zamčená, je struktura flock vrácena bez změny kromě první položky, která je nastavena na
F UNLCK.
• zamykání přes fcntl i lockf má jednu důležitou vlastnost, kterou výstižně
popisuje například manuálová stránka pro fcntl v systému FreeBSD:
This interface follows the completely stupid semantics of System V and IEEE
Std 1003.1-1988 („POSIX.1ÿ) that require that all locks associated with a file
for a given process are removed when any file descriptor for that file is closed
by that process. This semantic means that applications must be aware of any
files that a subroutine library may access. For example if an application for
updating the password file locks the password file database while making the
update, and then calls getpwnam(3) to retrieve a record, the lock will be lost
because getpwnam(3) opens, reads, and closes the password database.

133

Deadlock
• máme dva sdílené zdroje res1 a res2 chráněné zámky lck1 a lck2.
Procesy p1 a p2 chtějí každý výlučný přístup k oběma zdrojům.
p2

p1
lock(lck1); /* OK */
lock(lck2); /* Čeká na p2 */
use(res1, res2);
unlock(lck2);
unlock(lck1);

lock(lck2); /* OK */

lock(lck1); /* Čeká na p1 */
Deadlock
use(res1, res2);
unlock(lck2);
unlock(lck1);

• pozor na pořadí zamykání!

• obecně deadlock vznikne, jestliže proces čeká na událost, která nemůže nastat.
Zde např. na sebe dva procesy čekají navzájem, až ten druhý uvolní zámek,
ale k tomu nikdy nedojde. Další možností je deadlock jednoho procesu, který
čte z roury a předtím zapomněl uzavřít zápisový konec roury. Jestliže rouru
nemá už nikdo další otevřenou, pokus o čtení ze zablokuje, protože nejsou zavřeny všechny kopie zápisového deskriptoru a tedy nenastane konec souboru
na rouře, ale čtoucí proces svůj zápisový deskriptor nemůže zavřít, protože
čeká.
• volání fcntl() provádí kontrolu a při výskytu deadlocku vrací chybu EDEADLK.
• je vhodné se deadlocku snažit vyvarovat správným naprogramováním a nespoléhat se na kontrolu systému.

134

System V IPC
• IPC je zkratka pro Inter-Process Communication
• komunikace mezi procesy v rámci jednoho systému, tj. nezahrnuje
síťovou komunikaci
• semafory . . . použití pro synchronizaci procesů
• sdílená paměť . . . předávání dat mezi procesy, přináší podobné
problémy jako sdílení souborů, k řešení lze použít semafory
• fronty zpráv . . . spojují komunikaci (zpráva nese data) se
synchronizací (čekání procesu na příchod zprávy)
• prostředky IPC mají podobně jako soubory definovaná přístupová
práva (pro čtení a zápis) pro vlastníka, skupinu a ostatní.

• prostředky IPC existují i poté, kdy skončí proces, který je vytvořil. O jejich zrušení je nutno explicitně požádat (ze shellu lze zjistit seznam IPC
prostředků příkazem ipcs a smazat je příkazem ipcrm). Stav a obsah existujících prostředků IPC zůstává v platnosti, i když s nimi právě nepracuje
žádný proces (např. data ve sdílené paměti zůstávají, i když ji nemá žádný
proces připojenou).
• další dva prostředky System V IPC, které se běžně v unixových systémech vyskytují a jsou součástí normy, tj. sdílená paměť a zasílání
zpráv, nebudeme probírat. Pro sdílenou paměť je možné použít již
probrané volání mmap, místo zasílání zpráv je možné použít sockety
(budou v některé z příštích přednášek).

135

Semafory
• zavedl je E. Dijkstra
• semafor s je datová struktura obsahující
– celé nezáporné číslo i (volná kapacita)
– frontu procesů q, které čekají na uvolnění
• operace nad semaforem:
init(s, n)
vyprázdnit s.q; s.i = n
P(s) (z holandského „proberen te verlagenÿ – zkus dekrementovat)
if(s.i > 0) s.i-- else
uspat volající proces a zařadit do s.q
V(s) (z holandského „verhogenÿ – inkrementovat)
if(s.f prázdná) s.i++ else
odstranit jeden proces z s.q a probudit ho

• operace P(s) a V(s) lze zobecnit: hodnotu semaforu je možné měnit o libovolnou hodnotu n . . . P(s, n), V(s, n).
• Allen B. Downey: The Little Book of Semaphores, Second Edition, on-line na
http://greenteapress.com/semaphores/
• binární semafor má pouze hodnotu 0 nebo 1

136

Vzájemné vyloučení pomocí semaforů
• jeden proces inicializuje semafor
sem s;
init(s, 1);
• kritická sekce se doplní o operace nad semaforem
...
P(s);
kritická sekce;
V(s);
...

inicializace semaforu na hodnotu n dovolí vstoupit do kritické sekce n procesům.
Zde semafor funguje jako zámek, vždy ho odemyká (zvyšuje hodnotu) stejný proces,
který ho zamknul (snížil hodnotu).

137

API pro semafory
int semget(key t key, int nsems, int semflg );
• vrátí identifikátor pole obsahujícího nsems semaforů asociovaný
s klíčem key (klíč IPC PRIVATE . . . privátní semafory, při každém
použití vrátí jiný identifikátor). semflg je OR-kombinace
přístupových práv a konstant IPC CREAT (vytvořit, pokud
neexistuje), IPC EXCL (chyba, pokud existuje).
int semctl(int semid, int semnum, int cmd, ...);
• řídicí funkce, volitelný čtvrtý parametr arg je typu union semun.
int semop(int semid, struct sembuf *sops, size t nsops );
• zobecněné operace P a V.

• největší zajímavost na System V implementaci semaforů je skutečnost, že
daný syscall neoperuje nad jedním semaforem, ale nad polem semaforů, atomicky. Většinou však budete potřebovat pouze jeden semafor, tj. pole o jednom prvku.
• další důležitá informace je, že System V semafory jsou bohužel značně složité
• přístupová práva jsou jen pro čtení a zápis.
• podobné schéma API funkcí (funkce na vytvoření, řízení a operace) dodržují
i ostatní System V IPC mechanismy.
• jakmile je jednou pole semaforů jedním procesem vytvořeno, mohou i ostatní
procesy použít semctl() a semop(), aniž by předtím volaly semget(). To
platí i pro semafory vytvořené s klíčem IPC PRIVATE, pro které nelze volat
semget(), protože by se tím vytvořilo nové pole semaforů.

138

API pro semafory: semctl()
• semnum . . . číslo semaforu v poli
• možné hodnoty cmd:
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

volání semctl(semid, semnum, SETVAL, arg) odpovídá obecné semaforové
inicializační operaci init(s, n).

139

API pro semafory: semop()
• operace se provádí atomicky (tj. buď se povede pro všechny
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

• atomičnost zajistí, že nedojde k deadlocku v následující situaci: dva procesy
A a B budou používat dva semafory k řízení přístupu (zamykání) ke dvěma
systémovým zdrojům. Proces A je bude zamykat v pořadí (0, 1) a proces B
v pořadí (1, 0). Ve chvíli, kdy proces A zamkne semafor 0 a B zamkne 1,
dojde k deadlocku, protože ani jeden proces nemůže pokračovat (potřeboval
by zamknout druhý semafor). Při použití atomické operace zamčení obou
semaforů najednou bude úspěšný vždy právě jeden proces, který získá oba
semafory, druhý bude čekat.
• SEM UNDO zajistí, že při ukončení procesu dojde k odemčení semaforů (použitých jako zámky), které tento proces měl zamčené.

140

Vytváření prostředků IPC
• jeden proces prostředek vytvoří, ostatní se k němu připojí.
• po skončení používání je třeba prostředek IPC zrušit.
• funkce semget(), shmget() a msgget() mají jako první parametr
klíč identifikující prostředek IPC. Skupina procesů, která chce
komunikovat, se musí domluvit na společném klíči. Různé skupiny
komunikujících procesů by měly mít různé klíče.
key t ftok(const char *path, int id );
• vrátí klíč odvozený ze zadaného jména souboru path a čísla id. Pro
stejné id a libovolnou cestu odkazující na stejný soubor vrátí stejný
klíč. Pro různá id nebo různé soubory na stejném svazku vrátí různé
klíče.

Poznámky k ftok():
• Z id se použije jen nejnižších 8 bitů.
• Není specifikováno, zda bude stejný klíč vrácen i po smazání a znovuvytvoření
souboru.
• Různé klíče pro různé soubory nejsou vždy zaručené. Např. na Linuxu se
klíč získá kombinací 16 bitů čísla i-uzlu, 8 bitů id a 8 bitů vedlejšího čísla
zařízení. Stejný klíč pro různé soubory je vrácen, pokud se čísla i-uzlů shodují
na spodních 16 bitech.

141

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

• POSIXové IPC používá pro pojmenování jednotlivých IPC objektů řetězce
místo numerických identifikátorů, proto do značné míry odpadají problémy
s identifikací známé ze System V IPC (kde se řeší např. funkcí ftok()).
• sokety se z BSD rozšířily i do ostatních UNIXových systémů a dostaly se i
do normy UNIX 98.

142

Síťová komunikace
UUCP (UNIX-to-UNIX Copy Program) – první aplikace pro
komunikaci UNIXových systémů propojených přímo nebo přes
modemy, součást Version 7 UNIX (1978)
sokety (sockets) – zavedeny ve 4.1aBSD (1982); soket je jeden konec
obousměrného komunikačního kanálu vytvořeného mezi dvěma
procesy buď lokálně na jednom počítači, nebo s využitím síťového
spojení
TLI (Transport Layer Interface) – SVR3 (1987); knihovna zajišťující
síťovou komunikaci na úrovni 4. vrstvy referenčního modelu ISO OSI
RPC (Remote Procedure Call) – SunOS (1984); protokol pro přístup
ke službám na vzdáleném stroji, data přenášena ve tvaru XDR
(External Data Representation)

• ISO (International Standards Organization) OSI (Open Systems Interconnect) – vrstvy (layers):
1. fyzická (physical)
2. linková (data link)
3. síťová (network)
4. transportní (transport)
5. relační (session)
6. prezentační (presentation)
7. aplikační (application)
• UUCP je tvořeno aplikačními programy, nevyžaduje žádnou podporu v jádru.
Implementace soketů a TLI jsou součástí jádra. TLI je ve verzi SVR4 implementováno s využitím mechanismu STREAMS. RPC existuje jako knihovna
linkovaná k aplikacím, která využívá sokety (funguje nad protokoly TCP a
UDP). RPC bylo vyvinuto jako komunikační protokol pro NFS (Networked
File System).
• existuje více (vzájemně nekompatibilních) implementací RPC
• komunikační kanál je specifikován adresami dvou soketů.
• sokety pro komunikaci pouze v rámci jednoho počítače jsou v doméně AF UNIX
a jejich jména jsou jména speciálních souborů, které reprezentují sokety v
systému souborů.
• sokety AF UNIX jsou něco jiného než lokální TCP/IP komunikace přes loopback rozhraní localhost (127.0.0.1).

143

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

• UNIX používá pro síťovou komunikaci nejčastěji rodinu protokolů TCP/IP.
Pro účely programování aplikací nás budou zajímat především protokoly
TCP (spojovaná spolehlivá komunikace) a UDP (nespojovaná nespolehlivá
komunikace). V obou protokolech je jeden konec komunikačního kanálu (odpovídá soketu v doméně AF INET) identifikován IP adresou síťového rozhraní
a číslem portu (pomocí portů se rozlišují síťové služby běžící na jednom počítači).
• IP – protokol 3. vrstvy, zajišťuje přenos paketů (datagramů) mezi rozhraními
identifikovanými IP adresou; je nespolehlivý (nezaručuje doručení dat). RFC
791. Nedílnou součástí IP je Internet Control Message Protocol (ICMP), RFC
792.
• UDP – jednoduchá nadstavba nad IP, přidává čísla portů, zůstává nespolehlivý a datagramově orientovaný
• TCP – vytváří obousměrné spojení mezi dvěma body (IP+port), poskytuje
tok dat (stream) bez rozdělení na zprávy, zajišťuje řízení toku dat a spolehlivé
doručování
• DNS – hierarchicky organizovaná databáze, její struktura nemusí mít nic
společného se strukturou IP adres

144

Spojované služby (TCP), sekvenční obsluha
server

síť

klient

fd = socket()

fd = socket()
bind(fd)
listen(fd)
fd2 = accept(fd)

connect(fd)

read(fd2); write(fd2)

write(fd);read(fd)

close(fd2)

close(fd)

• server vytvoří jedno spojení, teprve po jeho ukončení akceptuje dalšího klienta.
• systémová volání:
– socket() – vytvoří soket, vrátí jeho desktiptor
– bind() – definuje adresu soketu (IP adresu a číslo portu), musí to být
buď adresa jednoho ze síťových rozhraní počítače, na kterém je vytvořen
soket (pak bude soket přijímat žádosti klientů pouze přes toto rozhraní),
nebo je to speciální hodnota „libovolná adresaÿ (pak soket přijímá požadavky prostřednictvím všech síťových rozhraní)
– listen() – oznámí jádru, že soket bude přijímat požadavky klientů
– accept() – uspí proces, dokud nebude k dispozici nějaká žádost klienta
o spojení, vytvoří spojení a vrátí nový deskriptor, přes který bude probíhat další komunikace s klientem, původní deskriptor lze použít k novému
volání accept() pro obsloužení dalšího klienta
– close() – ukončí komunikaci
– connect() – žádost klienta o navázání spojení, IP adresa a číslo portu
serveru se zadávají jako parametry, komunikace probíhá přes deskriptor
fd (na rozdíl od accept() nevytváří nový deskriptor)
• klient nemusí volat bind(), v takovém případě mu jádro přidělí některý volný
port. Existují služby (např. rsh), které vyžadují, aby se klient spojoval z
privilegovaného portu. Takový klient pak musí provést bind() (a navíc běžet
s rootovskými právy alespoň do okamžiku provedení bind()).

145

Spojované služby (TCP), paralelní obsluha
server

síť

fd = socket()
bind(fd)
listen(fd)
fd2 = accept(fd)
fork()

klient

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

write(fd);read(fd)
close(fd)

• server akceptuje spojení od klienta a na vlastní komunikaci vytvoří nový
proces, který po uzavření spojení s klientem skončí. Rodičovský proces může
mezitím akceptovat další klienty a spouštět pro ně obslužné procesy. Současně
je tedy obsluhováno více klientů.
• po provedení fork(), ale před zahájením obsluhy spojení, může synovský
proces provést exec – takto funguje např. inetd.
• volání waitpid() v cyklu odstaňuje ze systému zombie. Jinou možností je
využití signálu SIGCHLD, jeho explicitní ignorování zabrání vzniku zombií,
popř. lze instalovat handler, v němž se volá wait().

146

Spojované služby, paralelní accept()
server

síť

klient

fd = socket()
bind(fd)
listen(fd)
fork()

fd = socket()

...

connect(fd)

fd2=accept(fd)
read(fd2)
write(fd2)
close(fd2)

write(fd);read(fd)
close(fd)

• po bind() a listen() se vytvoří několik synovských procesů a každý v
cyklu volá accept() a obsluhuje klienty. Jádro vybere (nedeterministicky)
pro každý požadavek jeden proces, v němž accept() naváže spojení.
• jednotlivé procesy serveru mezi sebou mohou komunikovat, aby v případě,
že současných požadavků je více než serverových procesů, se tato skutečnost
zjistila a hlavní server mohl dynamicky vytvořit další serverový proces.
• takto funguje např. webový server Apache.
• všechny tři uvedené způsoby činnosti serveru fungují se stejným klientem –
činnost klienta nezávisí na variantě serveru.

147

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

• z pohledu volaných síťových funkcí je funkce serveru a klienta shodná. Klient
je zde ten, kdo pošle první datagram.
• stejně jako v případě TCP, klient nemusí dělat bind(), jestliže mu nezáleží na
tom, jaké číslo portu bude používat. Server zjistí jeho port z obsahu adresní
části prvního datagramu.
• výhodou nespojované služby je menší režie a to, že přes jeden soket lze komunikovat s více procesy (při spojované komunikaci je spojení vždy navázáno s
jedním procesem).
• pro UDP je možné volat connect(). Tím se nenaváže spojení, ale soket se
nastaví tak, že může nadále komunikovat pouze s adresou a portem specifikovanými ve volání connect(). Místo sendto() a recvfrom() se pak používají
funkce send() a recv().

148

Vytvoření soketu: socket()
int socket(int domain, int type, int protocol );
• vytvoří soket a vrátí jeho deskriptor.
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

• sokety jsou přístupné přes deskriptory souborů. Po navázání spojení je (spojovaná) komunikace přes soket podobná komunikaci pomocí roury.
• v některých implementacích se rozlišují konstanty začínající PF_ (protocol
family, např. PF_INET, PF_UNIX) používané v socket() a konstanty AF_ (address family, např. AF_INET, AF_UNIX) používané při zadávání adres soketů.
Hodnoty odpovídajících konstant AF_ a PF_ jsou typicky stejné.
• existují další typy soketů pro přístup k IP, ICMP, nebo k informacím z routovací tabulky.

149

Pojmenování soketu: bind()
int bind(int socket, const struct sockaddr *address,
socklen t address len );
• přiřadí soketu zadanému deskriptorem socket adresu address o
velikosti address len bajtů.
• struct sockaddr:
– sa family t sa family . . . doména
– char sa data [] . . . adresa
• Pro AF INET se používá struct sockaddr in:
– sa family t sin family . . . doména (AF INET)
– in port t sin port . . . číslo portu (16 bitů)
– struct in addr sin addr . . . IP adresa (32 bitů)
– unsigned char sin zero [8] . . . výplň

• volání bind() přiřazuje soketu lokální adresu, tj. zdrojovou adresu odesílaných dat a cílovou adresu přijímaných dat. Vzdálená adresa (adresa druhého
konce komunikačního kanálu) se nastavuje pomocí connect().
• jeden soket lze spojit se všemi lokálními adresami nastavením sin_addr na
INADDR_ANY.
• nelze spojit více soketů s jednou dvojicí (adresa, port).
• volání bind() lze vynechat, jádro pak soketu (v případě TCP, UDP) přiřadí
adresu INADDR_ANY a některý volný port. Obvykle bind() volá pouze server,
protože klienti očekávají, že bude poslouchat na pevném portu. Naopak klient
pevný port nepotřebuje, server se port klienta dozví při navázání spojení nebo
z prvního přijatého datagramu.
• v doméně AF_UNIX se používá adresová struktura struct sockaddr_un:
– sa family t sun family . . . doména
– char sun path [] . . . jméno soketu
– délka jména není ve standardu definována, závisí na implementaci. Obvyklé hodnoty jsou mezi 92 a 108.

150

Čekání na spojení: listen()
int listen(int socket, int backlog );
• označí soket zadaný desktriptorem socket jako akceptující spojení.
• maximálně backlog žádostí o spojení může najednou čekat ve
frontě na obsloužení (implementace může hodnotu backlog změnit,
pokud není v podporovaném rozsahu). Žádosti, které se nevejdou do
fronty, jsou odmítnuty (tj. volání connect() skončí s chybou).
• soket čeká na spojení na adrese, která mu byla dříve přiřazena
voláním bind(). Pro doménu AF INET stačí zadat číslo portu a IP
adresu INADDR ANY, která znamená libovolnou adresu.

hodnota INADDR ANY se používá nejčastěji. Konkrétní IP adresa serveru se zadává tehdy, jestliže je potřeba rozlišit, přes které síťové rozhraní přišel požadavek
na spojení (pro každé rozhraní máme jeden soket). Tuto možnost využívají web
servery, které podle IP adresy rozlišují virtuální servery . Obvykle se na takovém
serveru jednomu fyzickému rozhraní přiřazuje několik IP adres (IP aliasing). Novější rozlišení virtuálních serverů podle HTTP hlavičky „Host:ÿ už nepotřebuje IP
aliasy.

151

Akceptování spojení: accept()
int accept(int socket, struct sockaddr *address,
socklen t *address len );
• vytvoří spojení mezi lokálním soketem socket (který dříve zavolal
listen()) a vzdáleným soketem, který žádal o spojení pomocí
connect(). Vrátí deskriptor (nový soket), který lze používat pro
komunikaci se vzdáleným procesem. Původní deskriptor socket
umožňuje přijímat další spojení pomocí accept().
• v address vrátí adresu vzdáleného soketu.
• address len je velikost struktury pro uložení adresy, po návratu
obsahuje skutečnou délku adresy.
• podobně jako bind() i accept() používá pro adresy v doméně
AF INET strukturu sockaddr in.

• vytvoření druhého deskriptoru pro komunikaci umožňuje na původním deskriptoru ihned znovu volat accept().
• jestliže se více klientů ze stejného počítače najednou připojí k jednomu serveru (tj. na jednu serverovou IP adresu a jeden port), jsou jednotlivá spojení
rozlišena jen číslem portu na klientské straně.

152

Navázání spojení: connect()
int connect(int sock, struct sockaddr *address,
socklen t address len);
• naváže spojení lokálního soketu sock se vzdáleným procesem, který
pomocí listen() a accept() čeká na spojení na adrese address
(o délce address len).
• jestliže pro soket sock nebyla definována adresa voláním bind(), je
mu přiřazena nějaká nepoužitá adresa.
• pokud se spojení nepovede, je soket v nedefinovaném stavu. Před
novým pokusem o spojení by aplikace měla zavřít deskriptor sock a
vytvořit nový soket.

• po úspěšném navázání spojení mohou server i klient pro komunikaci používat
běžná souborová volání write() a read(), nebo funkce send(), recv(),
sendmsg(), recvmsg(). Chování funkcí pro zápis a čtení dat je podobné jako
write() a read() pro roury.
• i pro nespojované služby (UDP) se dá volat connect(), tím se nenaváže spojení, ale pouze se omezí adresa protistrany, se kterou může soket komunikovat.
V tomto případě mohou connect() volat obě strany komunikace.

153

Poslání zprávy: sendto()
ssize t sendto(int socket, void *msg, size t len,
int flags, struct sockaddr *addr,
socklen t addr len );
• prostřednictvím soketu socket pošle zprávu msg o délce len na
adresu addr (o délce addr len).
• parametr flags může obsahovat příznaky:
– MSG EOB . . . ukončení záznamu (pokud je podporováno
protokolem)
– MSG OOB . . . poslání urgentních (out-of-band) dat, jejichž
význam je závislý na protokolu

• používá se hlavně pro sokety typu SOCK DGRAM.
• místo sendto() se dá použít obecnější funkce sendmsg().
• pro sokety, na které bylo voláno connect() se místo sendto() volá send().
• úspěšný návrat z libovolné funkce zapisující data do soketu neznamená úspěšné
doručení zprávy protistraně, ale pouze uložení dat do lokálního bufferu odesílaných dat.

154

Přijetí zprávy: recvfrom()
ssize t recvfrom(int sock, void *buf, size t len,
int flg, struct sockaddr *address,
socklen t *address len );
• přijme zprávu ze soketu sock, uloží ji do bufferu buf o velikosti len,
do address dá adresu odesílatele zprávy, do address len délku
adresy. Vrátí délku zprávy. Když je zpráva delší než len, nadbytečná
data se zahodí (SOCK STREAM nedělí data na zprávy, data se
nezahazují).
• ve flg mohou být příznaky:
– MSG PEEK . . . zpráva se bere jako nepřečtená, další recvfrom()
ji vrátí znovu
– MSG OOB . . . přečte urgentní (out-of-band) data
– MSG WAITALL . . . čeká, dokud není načten plný objem dat, tj.
len bajtů

• používá se hlavně pro sokety typu SOCK DGRAM.
• místo recvfrom() se dá použít obecnější funkce recvmsg().
• pro sokety, na které bylo voláno connect(), se místo recvfrom() volá recv().

155

Uzavření soketu: close()
int close(int fildes);
• zruší deskriptor, při zrušení posledního deskriptoru soketu zavře
soket.
• pro SOCK STREAM soket záleží na nastavení příznaku SO LINGER
(default je l onoff == 0, mění se funkcí setsockopt()).
– l onoff == 0 . . . volání close() se vrátí, ale jádro se snaží dál
přenést zbylá data
– l onoff == 1 && l linger != 0 . . . jádro se snaží přenést
zbylá data do vypršení timeoutu l linger, když se to nepovede,
close() vrátí chybu, jinak vrátí OK po přenesení dat.
– l onoff == 1 && l linger == 0 . . . provede se reset spojení

• po uzavření může TCP soket zůstat po nějakou dobu v přechodném stavu
(který je definován protokolem TCP při ukončování spojení). Než je soket
zcela zrušen, nelze použít jiný soket na stejném portu (pokud toto nebylo
povoleno nastavením příznaku SO REUSEADDR pomocí funkce setsockopt()).
• při použití SO_REUSEADDR se dá po uzavření poslouchajícího serverového soketu znovu spustit server – volat socket(), bind(), listen() a accept()
na stejné adrese a portu – i když ještě dobíhají spojení vytvořená předchozí
instancí serveru.
• podrobnosti
k
výše
uvedenému
lze
nalézt
například
http://hea-www.harvard.edu/ fine/Tech/addrinuse.html

na:

• reset spojení je abnormální ukončení spojení. V TCP se použije paket s nastaveným příznakem RST. Na druhé straně se normální ukončení spojení projeví
jako konec souboru (při čtení), reset způsobí chybu ECONNRESET.

156

Uzavření soketu: shutdown()
int shutdown(int socket, int how );
• Uzavře soket (ale neruší deskriptor) podle hodnoty how:
– SHUT RD . . . pro čtení
– SHUT WR . . . pro zápis
– SHUT RDWR . . . pro čtení i zápis

Při normálním ukončení spojení na úrovni protokolu TCP každá strana signalizuje, že už nebude nic zapisovat. To platí i v případě použití close() nebo
shutdown(fd, SHUT RDWR). Při použití shutdown(fd, SHUT WR) lze ze soketu dál
číst. Druhá strana dostane EOF při čtení, ale může dál zapisovat.

157

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

• Hodnota level v getsockopt() a setsockopt() je obvykle SOL_SOCKET.
• Funkce getsockname() se používá, když nevoláme bind() a potřebujeme
zjistit, jaká adresa byla jádrem soketu přidělena.
• Volání getsockopt(sock, SOL_SOCKET, SO_ERROR, &val, &len) vrátí (a
vymaže) příznak chyby na soketu. Asi nejužitečnější je při zjišťování, jak
dopadl neblokující connect().

158

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

Pokud lokální systém používá stejné pořadí bajtů jako síť, nedělají převodní
funkce nic.

159

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

V uvedených souborech je definováno mapování mezi jmény a čísly pro standardní protokoly a služby.

160

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

• Lze stanovit, zda má prioritu DNS nebo lokální databáze adres.
• Jméno domény a adresy name serverů jsou v souboru /etc/resolv.conf.

161

Příklad: TCP server
int nclients = 10, fd, newsock, sz;
struct servent *sp; struct protoent *pp;
struct sockaddr in sa,ca;
sp = getservbyname(argv[1], "tcp");
pp = getprotobyname("tcp");
fd = socket(AF INET, SOCK STREAM, pp->p proto);
sa.sin family = AF INET; sa.sin port=sp->s port;
sa.sin addr.s addr = INADDR ANY;
bind(fd,(struct sockaddr *)&sa,sizeof(sa));
listen(fd, nclients);
for(;;) {
sz = sizeof(ca); newsock = accept(fd, &ca, &sz);
/* Komunikace s klientem */
close(newsock);
}

Toto je obecná kostra serveru. Jméno služby se zadává jako parametr programu,
odpovídající číslo portu hledá funkce getservbyname().

162

Příklad: TCP klient
char *host; struct servent *se;
struct hostent *ha; struct protoent *pp;
int sockfd; struct sockaddr in sa;
host = argv[1];
se = getservbyname(argv[2], "tcp");
ha = gethostbyname(host);
pp = getprotobyname("tcp");
sockfd = socket(AF INET, SOCK STREAM, pp->p proto);
sa.sin family = AF INET; sa.sin port = se->s port;
memcpy(&sa.sin addr.s addr, ha->h addr list[0],
ha->h length);
connect(sockfd, &sa, sizeof(sa));
/* Komunikace se serverem */
close(sockfd);

Využíváme automatického přidělení volného portu systémem při volání connect(),
kterému nepředcházel bind().

163

Čekání na data: select()
int select(int nfds, fd set *readfds,
fd set *writefds, fd set *errorfds,
struct timeval *timeout );
• zjistí, které ze zadaných deskriptorů jsou připraveny pro čtení, zápis,
nebo na kterých došlo k výjimečnému stavu. Pokud žádný takový
deskriptor není, čeká do vypršení času timeout (NULL . . . čeká
libovolně dlouho). Parametr nfds udává rozsah testovaných
deskriptorů (0, ..., nfds-1).
• pro nastavení a test masek deskriptorů slouží funkce:
– void FD ZERO(fd set *fdset ) . . . inicializace
– void FD SET(int fd, fd set *fdset ) . . . nastavení
– void FD CLR(int fd, fd set *fdset ) . . . zrušení
– int FD ISSET(int fd, fd set *fdset ) . . . test

• motivace: jestliže chceme číst data z více deskriptorů, jde nastavit příznak
O NONBLOCK a neblokujícím read() střídavě testovat jednotlivé deskriptory,
mezi každým kolem testů pak třeba použít sleep(1). Lepší řešení, tj. bez
aktivního čekání a testování, je použít select() a následně read() na ty
deskriptory, které select() ohlásí jako připravené.
• připravený (ready) znamená, že read nebo write s vynulovaným příznakem
O NONBLOCK by se nezablokovalo, tedy ne nutně že nějaká data jsou připravena (read např. může vrátit 0 pro end-of-file)
• při volání jsou v množinách deskriptory, které chceme testovat, po návratu
zůstanou nastavené jen ty deskriptory, na kterých nastala testovaná událost.
Je nutné je tedy před dalším voláním select() znovu nastavit. Typicky to jsou bitové masky, ale nemusí tomu být tak; z pozice programátora
je to samožřejmě jedno.
• funkce select() je použitelná i pro čekání na možnost zápisu do roury nebo
soketu – čeká se, až druhá strana něco přečte a uvolní se místo v bufferu pro
další data.
• místo množiny pro deskriptory je možné uvést NULL, speciální případ při
nastavení všech množin na NULL je volání, které se pouze zablokuje do
příchodu signálu nebo do vypršení time-outu.
• po návratu je nutné otestovat každý deskriptor zvlášť, není k dispozici volání,
které by vám vytvořilo množinu připravených deskriptorů.
• pokud obsluhuje síťový server více portů, může volat select() na příslušné
deskriptory soketů a následně accept() na deskriptory, pro které select()
ohlásil příchod žádosti klienta (připravenost ke čtení).
164

• volání connect() na neblokujícím soketu se hned vrátí, navázání spojení
ohlásí následný select() jako připravenost k zápisu.
• další možnost použití select() je síťový server, který v jednom procesu obsluhuje paralelně několik klientů. Pomocí select() se testuje stav deskriptorů odpovídajících spojení s jednotlivými klienty a přes deskriptory připravené pro čtení/zápis se komunikuje. Aby se mohli připojovat noví klienti,
testuje se i deskriptor soketu, který se používá pro accept(). Využívá se
toho, že select() ohlásí deskriptor s čekající žádostí klienta o spojení jako
připravený pro čtení. Na takový deskriptor je možné volat accept().
• jako výjimečnou událost (množina errorfds) select() ohlásí příchod outof-band dat.
• pozor na to, že select může změnit strukturu timeval, existuje nové volání
pselect, které (mimo jiné) strukturu pro timeout nezmění.
• pro nfds je možné použít FD SETSIZE, což je systémová konstanta pro maximální počet deskriptorů. Typicky to však nebude příliš efektivní, protože
tato konstanta je většinou 1024 na 32-bitových systémech, na Solarisu to však
pro 64-bitové architektury je už 65536.
• pokud se čas nastaví na 0 (tj. teď nemluvíme o nastavení ukazatele na NULL),
select se dá použít pro tzv. polling – zjistí současný stav a hned se vrátí.

Čekání na data: poll()
int poll(struct pollfd fds [], nfds t nfds, int timeout );
• čeká na událost na některém z deskriptorů v poli fds o nfds prvcích
po dobu timeout ms (0 . . . vrátí se hned, -1 . . . čeká libovolně
dlouho).
• prvky fds:
– fd . . . číslo deskriptoru
– events . . . očekávané události, OR-kombinace POLLIN (lze
číst), POLLOUT (lze psát), atd.
– revents . . . události, které nastaly, příznaky jako v events,
navíc např. POLLERR (nastala chyba)

• tato funkce je obdoba volání select().
• na Solarisu je to systémové volání, select pak knihovní funkce implementovaná pomocí poll, poll je zde prefererováno. Je nutné poll použít v případě,
že chcete testovat deskriptor větší nebo rovno než FD SETSIZE.
165

• čas nastavený na -1 je to samé jako NULL u select.

Příklad: použití select()
/* deskriptor fd odkazuje na soket, přepisuje síťovou
komunikaci na terminál a naopak */
int sz; fd set rfdset, efdset; char buf[BUFSZ];
for(;;) {
FD ZERO(&rfdset); FD SET(0, &rfdset);
FD SET(fd, &rfdset); efdset = rfdset;
select(fd+1, &rfdset, NULL, &efdset, NULL);
if(FD ISSET(0, &efdset)) /* Výjimka na stdin */;
if(FD ISSET(fd, &efdset)) /* Výjimka na fd */;
if(FD ISSET(0, &rfdset)) {
sz = read(0, buf, BUFSZ); write(fd, buf, sz);
}
if(FD ISSET(fd, &rfdset)) {
sz = read(fd, buf, BUFSZ); write(1,buf,sz);
}
}

• zde je typické použití select(), kdy je třeba číst data současně ze dvou
zdrojů.
• před každým voláním select() se musí znovu nastavit množiny deskriptorů.
• lepší řešení je nastavit oba deskriptory jako neblokující a používat select()
i na zápis. Logika řízení je pak taková, že pro každý směr datové komunikace
máme samostatný buffer. Příslušný čtecí deskriptor bude v množině pro čtení
v select(), právě když je buffer prázdný. Naopak zápisový deskriptor bude
v množině pro zápis, právě když je buffer neprázdný.

166

Vlákna
• vlákno (thread) = linie výpočtu (thread of execution)
• vlákna umožňují mít více linií výpočtu v rámci jednoho procesu
• klasický unixový model: jednovláknové procesy
• vlákna nejsou vhodná pro všechny aplikace
• výhody vláken:
– zrychlení aplikace, typicky na víceprocesorech (vlákna jednoho
procesu mohou běžet současně na různých procesorech)
– modulární programování
• nevýhody vláken:
– není jednoduché korektně napsat složitější kód používající vlákna
– obtížnější debugging

• pro aplikace, kde každý krok závisí na kroku předcházejícím, nemají vlákna
příliš velký smysl.
• debuggery typicky mají podporu vláken, ale debugging změní timing, takže
to co v reálu dělá problém se při debuggingu vůbec nemusí projevit. Toto
samozřejmě není problémem u klasických 1-vláknových procesů.

167

Implementace vláken
library-thread model
• vlákna jsou implementována v knihovnách, jádro je nevidí.
• run-time knihovna plánuje vlákna na procesy a jádro plánuje
procesy na procesory.
⊕ menší režie přepínání kontextu
nemůže běžet více vláken stejného procesu najednou.
kernel-thread model
• vlákna jsou implementována přímo jádrem.
⊕ více vláken jednoho procesu může běžet najednou na různých
procesorech.
plánování threadů používá systémová volání místo knihovních
funkcí, tím více zatěžuje systém.
hybridní modely
• vlákna se multiplexují na několik jádrem plánovaných entit.

• původně UNIX s vlákny nepracoval a první implementace byly čistě knihovní,
bez účasti jádra. Dnes se používá spíše implementace vláken v jádru nebo
smíšený model.
• existují i jiné typy implementace vláken než jsou zde uváděná POSIXová
vlákna (např. systémové volání sproc() v IRIXu, Cthreads, Solaris threads,
. . . ).
• zatímco při práci s více procesy je nutné vyvinou jisté úsilí proto,
aby dané procesy mohly data sdílet, u vláken je naopak nutné řešit
situaci, jak přirozené sdílení dat uhlídat.
• vlákna implementována pouze v knihovně mohou být preemptivní i nepreemptivní. Pro preemptivnost je možné použít časovače a signály. Pokud multithreading (= použití vláken v aplikaci) není použit pro zvýšení výkonu
aplikace, typicky není problém s použitím nepreemptivních vláken. Střídání
vláken se automaticky dosáhne používáním blokujících systémových volání.
• pokud se volání v library-thread modelu zablokuje, zablokuje se celý proces,
tj. žádné vlákno nemůže běžet. To vyplývá z toho, že jádro v tomto modelu
o pojmu vlákno nic neví. Knihovní funkce jsou proto přepsány tak, že místo
blokujících volání se použijí neblokující a kontext se přepne na jiné vlákno.

168

Vytvoření vlákna
int pthread create(pthread t *thread,
const pthread attr t *attr,
void *(*start fun )(void*), void *arg );
• vytvoří nové vlákno, do thread uloží jeho ID.
• nastaví atributy (velikost zásobníku, plánovací politika) podle attr
(použije implicitní atributy při attr == NULL).
• ve vytvořeném vláknu spustí funkci start fun() s argumentem arg.
Po návratu z této funkce se zruší vlákno.
• s objekty pthread attr t lze manipulovat funkcemi
pthread attr init(), pthread attr destroy(),
pthread attr getstackaddr(), pthread attr setstackaddr(),
...

• pozor na konstrukce typu:
for(i = 0; i < N; i++)
pthread create(&tid, attr, start routine, &i);
na první pohled takto předáme každému vláknu jeho index. Jenže plánovač
může způsobit to, že než si nově spuštěné vlákno stačí přečíst hodnotu i,
příkaz for provede další iteraci a hodnota se změní. Obecně vlákno může
dostat místo správné hodnoty i libovolnou větší.
• co ale je možné použít, pokud potřebujeme předat pouze jednu hodnotu, je
toto:
assert(sizeof(void *) >= sizeof(int));
for(i = 0; i < N; i++)
pthread create(&tid, attr, start routine, (void *) i);
. . . a ve funkci void *start routine(void *arg) pak přetypovat ukazatel
zpátky na integer a máme potřebný identifikátor vlákna:
printf("thread %d started\n", (int) arg);
• pokud potřebujeme předat více bajtů než je velikost ukazatele, tak už opravdu
musíme předat ukazatel na paměť s příslušnými předávanými daty nebo použít globální proměnné.

169

Soukromé atributy vláken
• čítač instrukcí
• zásobník (automatické proměnné)
• thread ID, dostupné funkcí
pthread t pthread self(void);
• plánovací priorita a politika
• hodnota errno
• klíčované hodnoty – dvojice (pthread key t key, void *ptr )
– klíč vytvořený voláním pthread key create() je viditelný ve
všech vláknech procesu.
– v každém vláknu může být s klíčem asociována jiná hodnota
voláním pthread setspecific().

• každé vlákno má zásobník pevné velikosti, který se automaticky nezvětšuje.
• běžné globální proměnné (a také dynamicky alokovaná data) jsou společné
pro všechna vlákna. Klíčované hodnoty představují způsob, jak vytvořit globální proměnnou, která je ale lokální v rámci vlákna.

170

Ukončení vlákna
void pthread exit(void *value ptr );
• Ukončí volající vlákno.
• Obdoba exit() pro proces
int pthread join(pthread t thread, void **value ptr );
• počká na ukončení vlákna thread a ve value ptr vrátí hodnotu
ukazatele value ptr z volání pthread exit() nebo návratovou
hodnotu hlavní funkce vlákna.
• obdoba čekání na synovský proces pomocí wait()
int pthread detach(pthread t thread );
• nastaví okamžité uvolnění paměti po ukončení vlákna, na vlákno
nelze použít pthread join().

• pokud nemáme v úmyslu po skončení vlákna volat pthread join(), je třeba
zavolat pthread detach(). Jinak po ukončeném vláknu zbydou v paměti
data nutná pro zjištění jeho výsledku pomocí pthread join(). To je podobná situace, jako když rodičovský proces nepoužívá wait() a v systému
se hromadí zombie. Ve funkci pro vlákno doporučuji použít toto:
pthread detach(pthread self());
• čekat na ukončení vlákna může libovolné jiné vlákno, nejen to, které ho spustilo.

171

Inicializace
int pthread once(pthread once t *once control,
void (*init routine )(void));
• v parametru once control se předává ukazatel na staticky
inicializovanou proměnnou
pthread once t once control = PTHREAD ONCE INIT;
• první vlákno, které zavolá pthread once(), provede inicializační
funkci init routine(). Ostatní vlákna už tuto funkci neprovádějí,
navíc, pokud inicializační funkce ještě neskončila, zablokují se a
čekají na její dokončení.
• lze použít např. na dynamickou inicializaci globálních dat
v knihovnách, jejichž kód může zavolat více vláken současně, ale je
třeba zajistit, že inicializace proběhne jen jednou.

variantou je inicializace globálních dat ještě předtím, než se proces rozdělí na
vlákna.

172

Zrušení vlákna
int pthread cancel(pthread t thread );
• požádá o zrušení vlákna thread. Závisí na nastavení
int pthread setcancelstate(int state, int *old );
• nastaví nový stav a vrátí starý:
– PTHREAD CANCEL ENABLE . . . povoleno zrušit
– PTHREAD CANCEL DISABLE . . . nelze zrušit, žádost bude čekat
na povolení
int pthread setcanceltype(int type, int *old );
• PTHREAD CANCEL ASYNCHRONOUS . . . okamžité zrušení
• PTHREAD CANCEL DEFERRED . . . žádost čeká na vstup do určitých
funkcí (např. open(), read(), wait()), nebo na volání
void pthread testcancel(void);

• vlákna je možné zvenku „násilněÿ rušit (obdoba ukončení procesu pomocí signálu) buď okamžitě, nebo jen na určitých místech (tzv. cancellation points).
• vunkce pthread_cancel() se podobá zrušení procesu signálem poslaným
voláním kill().
• funkce pthread_setcancelstate() a pthread_setcanceltype() jsou obdobou zakázání a povolení zrušení procesu signálem pomocí manipulace s
maskou blokovaných signálů (sigprocmask()).

173

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

toto je triviální příklad, kdy proces (hlavní vlákno) vytvoří dvě další vlákna a
počká na jejich ukončení.

174

Soukromé klíčované hodnoty ve vláknech
int pthread key create(pthread key t *key,
void (*destructor )(void *));
• vytvoří klíč, který lze asociovat s hodnotou typu (void *). Funkce
destructor() se volají opakovaně pro všechny klíče, jejichž
hodnota není NULL, při ukončení vlákna.
int pthread key delete(pthread key t key );
• Zruší klíč, nemění asociovaná data.
int pthread setspecific(pthread key t key,
const void *value );
• přiřadí ukazatel value ke klíči key.
void *pthread getspecific(pthread key t key );
• vrátí hodnotu ukazatele příslušného ke klíči key.

• při vytvoření klíče je s ním asociována hodnota NULL.
• při ukončení nebo zrušení vlákna se volají destruktory (v nespecifikovaném
pořadí) pro všechny klíče s hodnotou různou od NULL. Aktuální hodnota je
destruktoru předána v parametru. Jestliže po skončení všech destruktorů zbývají klíče s hodnotou různou od NULL, znovu se volají destruktory. Implementace může (ale nemusí) zastavit volání destruktorů po PTHREAD DESTRUCTOR ITERATIONS
iteracích. Destruktor by tedy měl nastavit hodnotu na NULL, jinak hrozí nekonečný cyklus.
• destruktor si musí sám zjistit klíč položky, ke které patří, a zrušit hodnotu
voláním pthread setspecific(key, NULL).
• SUSv3 tento nesmyslný požadavek odstraňuje, protože definuje, že před vstupem do destruktoru je hodnota automaticky nastavená na NULL.

175

Úklid při ukončení/zrušení vlákna
• vlákno má zásobník úklidových handlerů, které se volají při ukončení
nebo zrušení vlákna funkcemi pthread exit() a
pthread cancel(). Jako první se spouští naposledy vložený
handler.
• po provedení handlerů se volají destruktory privátních klíčovaných
dat vlákna.
void pthread cleanup push(void (*routine )(void *),
void *arg );
• Vloží handler do zásobníku.
void pthread cleanup pop(int execute );
• vyjme naposledy vložený handler ze zásobníku. Provede ho, pokud je
execute nenulové.

• handlery se volají jako routine(arg).
• tyto handlery se dají používat např. na úklid lokálních dat funkcí (obdoba
volání destruktorů pro automatické proměnné v C++).

176

fork() a vlákna
• je nutné definovat sémantiku volání fork v aplikacích používajících
vlákna. Norma definuje, že:
– nový proces obsahuje přesnou kopii volajícího vlákna, včetně
případných stavů mutexů a jiných zdrojů
– ostatní vlákna v synovském procesu neexistují
– pokud taková vlákna měla naalokovanou paměť, zůstane tato
paměť naalokovaná (= ztracená)
– obdobně to platí pro zamčený mutex již neexistujícího vlákna
• vytvoření nového procesu z multivláknové aplikace má smysl pro
následné volání exec (tj. včetně volání popen apod.)

• pokud mělo již neexistující vlákno zamčený mutex, tak je přístup k příslušným sdíleným datům ztracen, protože zamčený mutex může odemknout
pouze to vlákno, které ho zamknulo.
• ostatní vlákna přestanou existovat, nevolají se žádné rutiny jako při volání
pthread exit, pthread cancel nebo destruktory klíčovaných dat
• je možné použít handlery pro fork pomocí funkce pthread atfork. To my
potřebovat nebudeme, zájemce odkazuji například na [Butenhof].

177

Signály a vlákna
• signály mohou být generovány pro proces (voláním kill()), nebo
pro vlákno (chybové události, volání pthread kill()).
• nastavení obsluhy signálů je stejné pro všechna vlákna procesu, ale
masku blokovaných signálů má každé vlákno vlastní, nastavuje se
funkcí
int pthread sigmask(int how, const sigset t *set,
sigset t *oset );
• signál určený pro proces ošetří vždy právě jedno vlákno, které nemá
tento signál zablokovaný.
• lze vyhradit jedno vlákno pro synchronní příjem signálů pomocí
volání sigwait(). V ostatních vláknech se signály zablokují.

• jestliže je pro signál nastaveno ukončení procesu, skončí celý proces, nejen
jedno vlákno.
• vytvořené vlákno dědí nastavení signálové masky od vlákna, které ho vytvořilo
• při použití sigwait tak vlastně zablokujete příslušné signály ve všech vláknech, včetně vlákna, ve kterém chcete zpracovávávat signály. Viz přednáška
o signálech. Tento způsob zpracování signálů bývá často jediný opravdu doporučovaný, navíc je asi nejjednoduššeji implementovatelný.
• v reálné aplikaci není rozumné blokovat všechny signály, tj. včetně signálů
posílaných jako oznámení chyb – SEGV, FPE atd. Viz přednáška o signálech.

178

Synchronizace vláken: mutexes (1)
• nejjednodušší způsob zajištění synchronizovaného přístupu ke
sdíleným datům mezi vlákny je použitím mutexu
• statické vers. dynamické mutexy
• statická inicializace mutexu:
pthread mutex t mutex = PTHREAD MUTEX INITIALIZER
• inicializace mutexu mx s atributy attr (nastavují se pomocí
pthread mutexattr ...(), NULL = default)
int pthread mutex init(pthread mutex t *mx,
const pthread mutexattr t *attr );
• po skončení používání mutexu je nutné ho zrušit:
int pthread mutex destroy(pthread mutex t *mx );

• mutex = mutual exclusion (vzájemné vyloučení)
• je to speciální forma Dijkstrových semaforů – rozdíl mezi mutexy a binárními
semafory je ten, že zamčený mutex může odemknout pouze to vlákno, které
ho zamklo. To u semaforů neplatí.
• mutexy jsou určené pouze ke krátkodobému držení a měly by fungovat rychle.
Slouží pro implementaci kritických sekcí, podobně jako lock-soubory nebo
semafory (použité jako zámky).
• inicializace statického mutexu pomocí zmíněného makra nastaví pro mutex
jeho defaultní atributy.
• dynamické mutexy můžeme potřebovat například v situaci, kdy dynamicky
alokujeme datovou strukturu, jejíž součástí je i mutex, který sdílená data
struktury chrání. I zde, před zavoláním funkce free na datovou strukturu,
by se mělo použít volání pro zrušení mutexu.
• je možné dynamicky inicializovat i statické mutexy, ale je třeba zajistit, že se
vždy inicializují před použitím (to samozřejmě platí i pro dynamické mutexy)
a že se inicializují pouze jednou
• kopírovat mutexy není koretní – výsledek takové operace není definován. Je
možné samozřejmě zkopírovat ukazatel na mutex a s tímto ukazatelem pak
dále pracovat.

179

Mutexes (2)
• pro zamčení a odemčení mutexu použijeme volání:
int pthread mutex lock(pthread mutex t *mx );
a
int pthread mutex unlock(pthread mutex t *mx );
• pokud je mutex již zamčený, pokus o zamknutí vyústí v zablokování
vlákna. Je možné použít i volání:
int pthread mutex trylock(pthread mutex t *mx );
. . . které se pokusí zamknout mutex, a pokud to nelze provést, skončí s
chybou

• nelze zamknout mutex, pokud ho dané vlákno již zamčené má. Někdy může
dojít i k self dead-locku.
• nelze odemknout nezamčený mutex
• nelze odemknout mutex, který zamknulo jiné vlákno. Pokud je toto potřeba,
použijte binární semafor.
• při vytváření aplikace, kde je efektivita klíčovým faktorem, je nutné rozmyslet, jak, kde a kolik mutexů používat. Z knihovny, která nebyla napsaná pro
použití v aplikacích používající vlákna, je možné udělat thread-safe knihovnu
tak, že před zavoláním jakékoli funkce knihovny zamknu jeden giant mutex a
po skončení funkce ho odemknu. Mám tedy pouze jeden mutex a šetřím tak
čas, ale vlákna používající tuto knihovnu často spí při čekání na přístup. Na
druhou stranu, pokud zamykám přístup ke konkrétním, malým sekcím, mohu
potřebovat spoustu mutexů a hodně času strávím ve funkcích které s mutexy
pracují. Je proto často nutné podle situace zvolit vhodný kompromis.

180

Podmínkové proměnné (1)
• mutexy slouží pro synchronizaci přístupu ke sdíleným datům
• podmínkové proměnné pak k předání informací o těchto sdílených
datech
• z toho plyne, že každá podmínková proměnná je vždy
asociována s jedním mutexem
• jeden mutex může být asociován s více podmínkovými proměnnými
• společně pomocí mutexů a podmínkových proměnných je možné
vytvářet další synchronizační primitiva
– semafory
– bariéry
– ...

• jinými slovy – podmínkové proměnné se používají v situaci, kdy vlákno potřebuje otestovat nějakou podmínku nad sdílenými daty (např. stav čítače
položek ve frontě), a uspat se, když není splněna. Spící vlákno může být
probuzeno jiným vláknem, které změní datovou strukturu tak, že podmínka
bude splněna. Dané vlákno však musí explicitně oznámit, že data změnilo.
• není to tak, že při deklaraci podmínkové proměnné, což je pro programátora zcela transparentní typ, definujete podmínku např. „n je větší než 7 ÿ.
Podmínkovou proměnnou totiž můžete přirovnat k praporu nějaké barvy, a
pokud ho zvednete, znamená to, že ta vlákna, která čekají až s tímto praporem někdo zamává nad hlavou, jsou o této situaci informována a mohou se
podle toho zařídit. Některá vlákna tak mohou čekat na to, až n bude větší
než 7, jiná mohou čekat pouze na to, až se n jakkoli změní. Je pouze na
programátorovi, zda pro každou konkrétní situaci použije jednu podmínkovou proměnnou, nebo jednu pro situace všechny. Pro druhou situaci platí,
že vlákna čekající na nějakou událost musí vždy otestovat, která ze situací
nastala. Pokud ne ta, na kterou vlákno čeká, znovu se uspí. Jak je však uvedeno dále, z implementačních důvodů je nutné podmínku otestovat vždy, i
když pro ni používáte samostatnou podmínkovou proměnnou – může se stát,
že systém tím praporem zamává sám, aniž by to udělalo to vlákno, které v
naší názorné situaci ten čítač n mění a následně to oznamuje.

181

Podmínkové proměnné (2)
int pthread cond init(pthread cond t *cond,
const pthread condattr t *attr );
• Inicializuje podmínkovou proměnnou cond s atributy attr
(nastavují je funkce pthread condattr ...()), NULL = default.
int pthread cond destroy(pthread cond t *cond );
• zruší podmínkovou proměnnou.
int pthread cond wait(pthread cond t *cond,
pthread mutex t *mutex );
• čeká na podmínkové proměnné dokud jiné vlákno nezavolá
pthread cond signal() nebo pthread cond broadcast().

• je nutné, aby po té, co vlákno zamkne mutex a dříve, než vlákno zavolá
pthread cond wait, otestovat podmínku. Pokud tuhle operaci vlákno neprovede, mohlo by se uspat na neurčitou dobu, protože hláška o splnění podmínky od jiného vlákna by prošla „bez povšimnutíÿ. Jinak řečeno, nesmím
se uspat při čekání na situaci, která už mezitím nastala. Nefunguje to jako
signály, které pro vás systém drží, pokud je máte například zablokované. Co
je důležité je to, že ten test provádíte pod ochranou mutexu, tedy si opravdu
můžete být jistí hodnotou našeho čítače n.

182

Podmínkové proměnné (3)
int pthread cond timedwait(pthread cond t *cond,
pthread mutex t *mutex,
const struct timespec *abstime );
• čeká na pthread cond signal() nebo
pthread cond broadcast(), ale maximálně do vypršení timeoutu
abstime.
int pthread cond signal(pthread cond t *cond );
• probudí jeden proces čekající na podmínkové proměnné cond.
int pthread cond broadcast(pthread cond t *cond );
• probudí všechny procesy čekající na podmínkové proměnné cond.

• v parametru abstime funkce pthread cond timedwait() se předává absolutní čas, tj. timeout vyprší, když systémový čas dosáhne hodnoty větší nebo
rovné abstime. Pro absolutní čas bylo rozhodnuto proto, aby programátor
nemusel při případných probuzeních, kdy následně zjistí, že daná podmínka
neplatí, přepočítávat časový rozdíl.
• jak již bylo řečeno, jedna podmínková proměnná může být použita pro hlášení
několika rozdílných situací najednou – například při vložení prvku do fronty i
při jeho vyjmutí. Z toho důvodu je nutné po probuzení otestovat podmínku,
na kterou se čeká. Další věc, která z toho vychází je ta, že v takovém případě musíte použít broadcast. Stačí si představit následující situaci – čekáte
na podmínku „změnil se stav frontyÿ, na které čekají čtenáři i zapisovatelé
(předpokládejme, že jednu frontu používá více čtenářů i více zapisovatelů).
Pokud po vložení zprávy pouze vypustíte jednu signalizaci, tak se může stát,
že tato signalizace probudí jiného zapisovatele, který ale samozřejmě čeká
na situaci, kdy čtenář z fronty zprávu odebere. Tím se stane, že ve frontě
zůstane zpráva, která může být vytlačena až další signalizací.
• vlákno může být probuzeno jiným vláknem i v případě, že čeká na jednu
konkrétní událost, která však po probuzení vlákna již neplatí a přitom pro
jiné události příslušná podmínková proměnná není použita (a přitom nebyl
použit broadcast!). Představte si, že těsně po té, kdy jiné vlákno zahlásí
splnění podmínky, může další vlákno zamknout mutex a nějakou akcí, např.
vyjmutím prvku z fronty, zrušit platnost podmínky „ve frontě je zprávaÿ. To
vlákno, které je probuzeno, tak najde frontu prázdnou. Další důvod pro to,
že podmínkové proměnné je nutné vždy testovat v cyklu.
• v řídkých případech je možné, že se vlákno probudí a podmínka není platná
i díky konkrétní implementaci. Z toho opět vyplývá nutnost použití cyklu.
183

Použití podmínkových proměnných
pthread cond t cond; pthread mutex t mutex;
...
pthread mutex lock(&mutex);
while(!podminka(data))
pthread cond wait(&cond, &mutex);
set data(data, ...);
pthread mutex unlock(&mutex);
...
pthread mutex lock(&mutex);
set data(data, ...);
pthread cond signal(&cond);
pthread mutex unlock(&mutex);

• pro zopakování – ke každé podmínkové proměnné je potřeba mít ještě mutex.
• funkce pthread cond wait() atomicky odemkne mutex a uspí vlákno. Když
je vlákno probuzeno, nejprve se znovu zamkne mutex (tj. toto zamknutí se
provede v rámci příslušné implementace podmínkových proměnných!) a teprve pak se volání pthread cond wait() vrátí.
• když signalizujeme, že se něco změnilo, neznamená to ještě, že po změně
bude platit podmínka. Navíc, pthread cond wait() se může vrátit, i když
nebylo voláno ani pthread cond signal() ani pthread cond broadcast().
K probuzení vlákna a návratu z pthread cond wait() může tedy dojít, i
když podmínka není splněna, proto je potřeba znovu otestovat podmínku a
případně obnovit čekání.
• všimněte si, že odemknutí zámku následuje až po signalizaci podmínky

184

Read-write zámky (1)
int pthread rwlock init(pthread rwlock t *l,
const pthread rwlockattr t *attr );
• vytvoří zámek s atributy podle attr (nastavují se funkcemi
pthread rwlockattr ...(), NULL = default)
int pthread rwlock destroy(pthread rwlock t *l );
• zruší zámek
int pthread rwlock rdlock(pthread rwlock t *l );
int pthread rwlock tryrdlock(pthread rwlock t *rwlock );
• zamkne zámek pro čtení (více vláken může držet zámek pro čtení),
pokud má někdo zámek pro zápis, uspí volající vlákno (rdlock())
resp. vrátí chybu (tryrdlock()).

• najednou může mít zámek buď několik vláken zamčeno pro čtení, nebo maximálně jedno vlákno zamčeno pro zápis (a nikdo pro čtení).
• read-write zámky jsou obdobou zamykání souborů pomocí fcntl().

185

Read-write zámky (2)
int pthread rwlock wrlock(pthread rwlock t *rwlock );
• zamkne zámek pro zápis, pokud má někdo zámek pro čtení nebo
zápis, čeká.
int pthread rwlock trywrlock(pthread rwlock t *rwlock );
• jako pthread rwlock wrlock(), ale když nemůže zamknout, vrátí
chybu.
int pthread rwlock unlock(pthread rwlock t *rwlock );
• odemkne zámek

• Zvláštnost: pokud vlákno čekající na zámek dostane signál, po návratu z
handleru se vždy pokračuje v čekání, tj. nenastane chyba EINTR. Takto se
chovají i mutexy a podmínkové proměnné.
• SUSv3 k probraným mechanismům synchronizace vláken přidává ještě bariérovou synchronizaci (funkce pthread barrier wait() a několik pomocných
funkcí).

186

Bariéra, semafory
• bariéra (barrier ) je způsob, jak udržet členy skupiny pohromadě
• všechna vlákna čekají na bariéře, dokud ji nedosáhne poslední
vlákno; pak mohou pokračovat
• typické použití je paralelní zpracování dat na multiprocesorech
• bariéry nemají API, je možné je vytvořit pomocí mutexů a
podmínkových proměnných

• semafory pochází přímo z POSIXu
• jména funkcí nezačínají pthread , ale sem (sem init, sem post,
sem wait, . . . )
• je možné je použít s vlákny

• bariéru můžete využít např. v situaci, kdy mezi jednotlivými fázemi zpracování je potřeba provést jistou inicializaci, vlákna před ní tedy na sebe vždy
musí počkat, protože inicializace další fáze může začít až tehdy, kdy skončí
fáze předchozí.
• podmínka pro bariéru je třeba hodnota čítače rovnající se nule. Každé vlákno,
které dosáhne bariéry, sníží čítač, který je na začátku inicializován na počet
vláken. Pokud vlákno po dekrementování čítače zjistí, že ještě není roven
nule, uspí se na podmínkové proměnné. Pokud dané vlákno je tím vláknem,
které sníží čítač na nulu, místo zavolání pthread cond wait pošle broadcast,
který následně probudí všechna vlákna spící na bariéře (signalling zde nestačí,
chcete probudit všechna vlákna, ne jen jedno!). Před spuštěním další fáze
zpracování se čítač reinicializuje na původní hodnotu. I zde je nutné řešit
různé problémy, například není možné jen tak reinicializovat čítač poté, co
bariéry dosáhne poslední vlákno, protože jak již víme, vlákna po probuzení
z pthread cond wait musí vždy otestovat, zda čítač je opravdu nulový a
pokud není, opět se uspí. Takže by se vám mohlo stát, že by se probudila jen
některá vlákna, nebo taky žádná. Jak byste to řešili?
• funkce pro semafory se drží klasické UNIXové sémantiky – při chybě vracejí
-1 a nastaví errno

187

Typické použití vláken
• pipeline
– každé z vláken provádí svoji operaci nad daty, která se postupně
předávají mezi vlákny
– každé vlákno typicky provádí jinou operaci
. . . zpracování obrázku, kde každé vlákno provede jiný filtr
• work crew
– vlákna provádějí stejnou operaci, ale nad jinými daty
. . . zpracování obrázku dekompozicí – každé vlákno zpracovává jinou
část obrázku, výsledkem je spojení zpracovaných dat ze všech
vláken; zde se hodí řešení s bariérou
• client – server

• dané rozdělení je jen orientační, použití vláken je samozřejmě neomezené,
toto jsou asi ty tři nejčastější použití

188

Thread-safe, reentrantní funkce
• thead-safe znamená, že kód může být volán z více vláken najednou
bez destruktivních následků
– do funkce, která nebyla navržena jako thread-safe, je možné
přidat jeden zámek – na začátku funkce se zamkne, na konci
odemkne
– tento způsob ale samozřejmě není efektivní. . .
• slovem reentrantní se často myslí, že daná funkce byla navržena s
přihlédnutím na existenci vláken
– . . . tedy že daná funkce pracuje efektivně i ve vícevláknovém
prostředí
– taková funkce by se měla vyvarovat použití statických dat a
pokud možno i prostředků pro synchronizaci vláken, které jinak
zpomalují běh aplikace

• v dnešní době thread-safe většinou znamená reentrantní, tj. funkce jsou přepsány tak, aby pracovaly efektivně i s vlákny, ale je dobré vědět, že někdy to
může vyjadřovat rozdíl.

189

Nepřenositelná volání
• nepřenositelná volání končí řetězcem np (non-portable)
• jednotlivé systémy si takto definují vlastní volání
• FreeBSD
– pthread set name np(pthread t tid, const char *name)
→ umožňuje pojmenovat vlákno
• Solaris
– pthread cond reltimedwait np(...)
→ jako timedwait, ale časový timeout je relativní
• OpenBSD
– int pthread main np(void)
→ umožňuje zjistit, zda volající vlákno je hlavní (= main())

• tyto informace jsou pro zajímavost, abyste věděli, že se s podobnými věcmi
můžete setkat. Nepřenositelná volání by se měla používat spíše pro ladící
účely. Nikdy nevíte, kdo bude potřebovat váš kód spustit na jiném systému,
což se stane typicky a nečekaně po té, co zrovna opustíte vaši společnost a
nemáte již čas to opravit.
• zjistit, jaká nepřenositelná volání váš systém poskytuje je jednoduché, třeba
pomocí apropos np

190

Úkoly správce systému
• instalace a konfigurace operačního systému a aplikací
• správa uživatelských účtů a přidělování diskového prostoru
uživatelům (quota)
• údržba systému souborů (kontrola konzistence svazků – fsck,
zálohování dat)
• sledování zatížení systému (top, sar, du)
• sledování provozních hlášení systému (syslogd)
• konfigurace periodicky prováděných akcí (cron)
• správa síťových služeb (inetd, sendmail, ftpd, httpd)
• zajištění bezpečnosti systému

• k bezpečnosti systému: UNIX tradičně zajišťuje ochranu mezi procesy různých uživatelů. Předpokládá se ale, že uživatel vždy ví, co dělá, a není proto
snaha chránit uživatele před následky jeho vlastní činnosti. To je problematické ze dvou důvodů:
– uživatelé dělají chyby.
– uživatelé zpracovávají data a používají programy, které pochází z nedůvěryhodných zdrojů (z Internetu).
• zajištění bezpečnosti:
– testování integrity a detekce narušení ochrany systému
– sledování novinek – konference, zprávy o bezpečnostních chybách, instalace patchů
– správné nastavení práv souborů a SUID programů
– vypnutí nepotřebných démonů, hlavně pro síťové služby
– filtrace síťového provozu

191

Uživatel root
• uživatel se všemi přístupovými právy
• smí „všechnoÿ, včetně změny identity na jiné uživatele
• systém všechno nebo nic není ideální
• základní otázka: jak propůjčit uživateli práva superuživatele pouze
na některé operace?
• je možné použít tyto nástroje:
– sudo (superuser do), konfigurace je v sudoers souboru
(přenositelné)
– RBAC – role based access control (Solaris)

• uživatel root má všechna přístupová práva, kromě jiného smí číst a měnit
soubory patřící všem uživatelům (včetně změny přístupových práv a vlastníků). Dále smí bez použití hesla změnit svou identitu na libovolného jiného
uživatele (příkazem su, resp. systémovým voláním setuid()).
• privilegia uživatele root umožňují správci provádět i destruktivní zásahy,
např. nechtěné rm -rf / má velmi nemilé následky. Proto by administrátor
systému typicky má normální uživatelský účet s běžnými právy a jako root
se loguje jen v nezbytných případech.
• sudo je velmi populární a používá se velmi často. Jeho největší výhoda proti
RBAC je ta, že tento nástroj funguje prakticky na všech unixových systémech. Funguje tak, že můžete nastavit až do granularity jednotlivých příkazů,
co který uživatel může spustit.
• RBAC je nativní nástroj Solarisu, poprvé se objevil ve verzi 8 (2000). Používá
se ve zkratce tak, že definujete profily, kterými určujete, co je a není možné
provádět. Profil pak přiřadíte roli. Role pak přiřazujete uživatelům. O RBAC
jádro nic neví, neví co jsou role, vše se děje v uživatelském prostoru.

192

Start systému (1)
• závislé na architektuře, na operačním systému, na boot manažeru
• IBM PC a spol: BIOS načte 1. blok z boot disku do paměti a skočí
na jeho první instrukci (0. level)
• načte se první blok ze zvoleného oddílu na disku (partition) a skočí
se na jeho první instrukci (1. level)
• načtou se další bloky zavaděče z prvního levelu
• načte se do paměti jádro operačního systému
• . . . nebo načte další „složitějšíÿ zavaděč, který následně načte jádro
systému
• vícestupňový start umožňuje volbu konkrétního jádra, výpis souborů
na disku, hledání PnP zařízení, načtení kernel modulů, . . .

• popsaná procedura je ze systému FreeBSD. V 1. levelu můžete zvolit konkrétní jádro, ale nemůžete například načíst kernel moduly. To můžete až ve
2. levelu.
• některé boot manažery (boot manager ) mohou zajistit všechny tyto úrovně,
například GRUB
• je dobré si uvědomit, zda potřebujete složité boot manažery. Čím více kódu,
tím větší pravděpodobnost chyb a to všechno v situaci, která je velmi kritická
– samotný start systému.

193

Start systému (2)
• po implementačně závislým způsobem načtení jádra do paměti a
jeho spuštění následuje. . .
• jádro provede svoji inicializaci, připojí kořenový svazek souborů,
vytvoří nový proces a spustí program init. Zbytek inicializace
systému probíhá v uživatelském režimu a je řízen procesem init.
• v závislosti na operačním systému:
– (System V) init čte /etc/inittab a podle jeho obsahu spouští
další procesy
– (BSD) init předá kontrolu skriptu /etc/rc, poté zpracuje
/etc/ttys

• soubor /etc/ttys obsahuje popis terminálových linek v systému včetně pseudo
terminálů, definuje jaký program se má případně na konkrétní terminálové
lince spustit
• rc znamená „run commandÿ, to pochází z dávné historie

194

Úrovně běhu systému (System V)
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
• kromě označení úrovně init rozlišuje:
– q, Q . . . znovu načíst /etc/inittab
– a, b, c . . . spuštění procesů podle /etc/inittab bez změny
úrovně běhu systému

• aktuální úroveň lze zjistit příkazem who -r (System V) nebo runlevel (Linux).
• existují i odlišnosti, např. Linux běží standardně v run-level 3 (nebo 5, pokud
je zapnuto xdm a logování probíhá v grafickém režimu), IRIX v run-level 2 (3
se nepoužívá).

195

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

procesům, které nemají běžet v nové úrovni, posílá init signál SIGTERM a po
chvíli SIGKILL.

196

Příklad: /etc/inittab
id:3:initdefault:
si::sysinit:/sbin/depscan.sh
l0:0:wait:/sbin/rc shutdown
l1:S1:wait:/sbin/rc single
l2:2:wait:/sbin/rc nonetwork
l3:3:wait:/sbin/rc default
l4:4:wait:/sbin/rc default
l5:5:wait:/sbin/rc default
l6:6:wait:/sbin/rc reboot
# TERMINALS
c1:12345:respawn:/sbin/agetty 38400 tty1 linux
c2:12345:respawn:/sbin/agetty 38400 tty2 linux
x:a:once:/etc/X11/startDM.sh
...

• zde je vidět nastavení defaultní úrovně, spouštění skriptů při vstupu do nové
úrovně a inicializace terminálů.
• toto nastavení můžete vidět na Gentoo systémech v MFF laborce
• řádky sysinit se spustí jako první. Opět zde platí, že mezi systémy mohou
být rozdíly, akce používaná na jednom systému není vůbec definována na
systému jiném atd.

197

Inicializační skripty (1)
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

• nejdříve se spustí skripty začínající K (kill), které ukončí ty procesy, které v
dané úrovni nemají běžet. Pak se spustí skripty se S (start)
• skripty pro úroveň U jsou v adresáři /etc/rc.U . Ve skutečnosti jsou to pouze
symlinky na soubory v adresáři /etc/init.d.
• schéma inicializačních skriptů se v různých implementacích dost liší. Např.
někdy je vložena ještě jedna úroveň adresářů, místo /etc/init.d je
/etc/rc.d/init.d, místo /etc/rc.0 je /etc/rc.d/rc.0, atd.
• zapínání a vypínání určité funkce v nějaké úrovni se provádí vytvořením,
resp. smazáním symlinku v příslušném adresáři /etc/rc?.d.
• tento systém spuštění skriptů má dva hlavní problémy: není flexibilní a nelze
jednoduše řešit závislosti.

198

Inicializační skripty (2)
• NetBSD 1.5 (prosinec 2000) přichází s rcNG (rc Next Generation)
– skripty mají v komentářích definované metainformace o službách,
které poskytují a o závislostech na službách jiných:
# PROVIDE: syslogd
# REQUIRE: mountcritremote cleanvar
# BEFORE: SERVERS
• Solaris 10: Service Management Facility (SMF)
– služby jsou startovány paralelně a podle závislostí
– služby jsou v případě potřeby automaticky restartovány
– každá služba má vlastní log soubor

• před rcNG měly systémy BSD pouze sadu „hardwiredÿ skriptů, které se staraly o jednotlivé části systému, např. rc.network, rc.serial (konfigurace
sériových zařízení), rc.pccard atd. a které byly postupně spuštěny hlavním
skriptem rc. Přidání lokálních skriptů se provádělo například jejich nakopírováním do /usr/local/etc/rc.d adresáře, kde se spouštěly podle abecedy;
běžným zvykem bylo opět začínat jejich názvy číslem, čímž jste docílili potřebného uspořádání. Takový systém byl například FreeBSD 4.x, tento systém
stále běží a určitě ještě chvíli běžet bude na mailu.
• závislosti dovolují vytvořit posloupnost skriptů tak, aby nastartovaly v tom
pořadí, jaký je požadováno – bez explicitního zásahu administrátora. Systém
samozřejmě zjistí problémy, například kruhovou závislost a takové chyby nahlásí.
• rcNG se tak přiblížil způsobu, jakým startují System V-like systémy či Linux
– každá služba má svůj skript. Klasický System V-like řešení však nepracuje
se závislostmi, což platí i pro mnoho dnešních Linuxových distribucí. Úrovně
běhu systému jako je známe ze System V však BSD ani teď nemají.
• rcNG velmi rychle převzaly další systémy založené na BSD – FreeBSD, DragonflyBSD, MacOS X. Gentoo používá podobnou myšlenku, i když implementace je trochu jiná.
• podrobnosti je možné nalézt v článku Luke Mewburn: The Design and Implementation of the NetBSD rc.d system

199

Zastavení systému
• uživatel root používá k zastavení systému příkaz shutdown, který
přepne systém do úrovně 0 (přitom spouští příslušné ukončovací
skripty), uloží nezapsaná data, odpojí disky a zastaví jádro.
• příkaz reboot je obdoba shutdown, ale přepne systém do úrovně 6,
tj. způsobí zastavení a nové nastartování systému.
• jestliže dojde k závažné chybě systému (neplatná adresa použitá
jádrem, zrušení procesu init), jádro vytvoří protokol o chybě
(včetně kompletního obsahu paměti jádra), vypíše hlášení tvaru
„panic: příčina chyby ÿ a zastaví se.

• násilné vypnutí systému (bez korektního ukončení a odpojení disků) např.
při výpadku napájení, vypnutí síťového vypínače nebo panice jádra obvykle
způsobí nekonzistence a případně i částečnou ztrátu dat na discích. Při restartu je pak třeba spustit fsck. Žurnálované filesystémy mají výhodu, že
nepotřebují fsck a doba zotavení je velmi krátká a nezávislá na velikosti
filesystému.
• z historie (http://www.multicians.org/unix.html):
. . . we went to lunch afterward, and I remarked to Dennis that easily
half the code I was writing in Multics was error recovery code. He
said, ”We left all that stuff out. If there‘ s an error, we have this
routine called panic, and when it is called, the machine crashes,
and you holler down the hall, ‘ Hey, reboot it.‘ ”
• v systémech založených na BSD je zastavení systému podobné, opět se to
samozřejmě netýká úrovní, které BSD systémy nemají. V BSD ještě bývá
pro zastavení systému příkaz halt.

200

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
• po odhlášení uživatele init spustí znovu getty.
• v některých implementacích se místo getty používá jeden proces
ttymon, který monitoruje všechny terminály.
• při přihlašování po síti přebírá roli getty síťový server (např.
telnetd nebo sshd).

• v BSD je seznam terminálových linek v souboru /etc/ttys. init spustí
příkaz ze druhého pole v případě, že zařízení v poli prvním existuje. Danému
příkazu se jako poslední argument dá právě první pole. Zde je část /etc/ttys
na systému FreeBSD:
# Virtual terminals
ttyv1
"/usr/libexec/getty Pc"
ttyv2
"/usr/libexec/getty Pc"
ttyv3
"/usr/libexec/getty Pc"
ttyv4
"/usr/libexec/getty Pc"

cons25
cons25
cons25
cons25

on
on
on
on

secure
secure
secure
secure

a část výpisu getty procesů pak vypadá takto:
jp@sarrix:~$ ps -ax | grep getty
483 v0 Is+
0:00.00 /usr/libexec/getty Pc ttyv0
485 v2 Is+
0:00.00 /usr/libexec/getty Pc ttyv2
• shell na začátku interpretuje inicializační skripty, což jsou v případě /bin/sh
soubory /etc/profile a $HOME/profile
• přihlašování přímo do X Window systému probíhá jinak, ale opět existuje
proces (xdm) běžící jako root, který kontroluje jméno a heslo a spouští uživatelské inicializační skripty, které připraví pracovní prostředí uživatele.
• v některých implementacích (Solaris, Linux, BSD) se používá PAM (Pluggable Authentication Modules) pro konfigurovatelnou autentizaci uživatelů.

201

Periodicky opakované akce: cron
• provádění určitých akcí opakovaně v zadaném čase zajišťuje démon
cron.
• při své práci se cron řídí obsahem konfiguračního souboru
(crontab), který existuje pro každého uživatele.
• konfigurační soubor se zobrazuje příkazem crontab -l a vytváří
příkazem crontab < soubor.
• každý řádek souboru má tvar:
03 3 * * 0,2,4 root /backup/bin/backup
prvních pět položek definuje čas (minuta, hodina, den v měsíci,
měsíc, den v týdnu), kdy se má příkaz uvedený na zbytku řádku.
• jednorázové akce lze v daný čas spustit příkazem at.

• čárky znamenají různé časy v rámci jednoho pole, tj. 15,45 v minutách znamená, že příkaz se spustí v x:15 a x:45. Opakovaní je možné zadat pomocí
*/x, například */5, což znamená „každých pět minutÿ, samozřejmě v závislosti na ostatních časových polích.
• obvyklé akce spouštěné démonem cron: mazání nepotřebných souborů (např.
staré soubory core), rotace logů, zálohování.
• v některých Linuxových distribucích nebo na FreeBSD se cron řídí i tabulkou
/etc/crontab. Ta se z konvence používá pro akce týkající se celého systému,
například rotace logů, periodicky prováděné údržbové práce, synchronizace
času apod.

202

Síťové služby: inetd
• servery síťových služeb se spouští buď při startu systému, nebo je
startuje démon inetd při připojení klienta.
• démon inetd čeká na portech definovaných v /etc/inetd.conf a
když detekuje připojení klienta, naváže spojení, spustí příslušný
server a přesměruje mu deskriptory 0, 1 a 2 do soketu, přes který lze
komunikovat s klientem.
• příklad obsahu /etc/inetd.conf:
ftp stream tcp nowait root /usr/etc/ftpd ftpd -l
shell stream tcp nowait root /usr/etc/rshd rshd -L
login stream tcp nowait root /usr/etc/rlogind rlogind
exec stream tcp nowait root /usr/etc/rexecd rexecd
finger stream tcp nowait guest /usr/etc/fingerd fingerd
ntalk dgram udp wait root /usr/etc/talkd talkd
tcpmux stream tcp nowait root internal
echo stream tcp nowait root internal

• typicky se pomocí inetd spouští servery, které se používají málo nebo jejichž
inicializace je relativně nenáročná (telnetd, ftpd). Silně vytížené a dlouho
startující servery (httpd) se obvykle startují ze systémových inicializačních
skriptů a běží stále.
• často má cenu inetd mít vypnutý úplně. Pokud na vašem stroji běží např.
pouze SSH, tak pro to se inetd ve většině případů nepoužívá, inetd by byl
jen dalším serverem běžícím na stroji a zdroj potenciálního nebezpečí, pokud
by se v něm objevila bezpečnostní chyba.

203

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

• soket typu stream:
– wait . . . server dostane soket, na který musí aspoň jednou zavolat
accept(). Teprve tím získá nový soket, přes který může komunikovat s
klientem. Po skončení serveru přebírá řízení soketu zpět inetd.
– nowait . . . inetd zavolá accept() a získaný soket předá serveru, server tedy může rovnou komunikovat (může používat standardní vstup a
výstup) a nemusí vědět, že komunikuje po síti. Mezitím inetd čeká na
další klienty a podle potřeby spouští další instance serveru.
• pro soket typu dgram má smysl pouze wait. Server musí přečíst ze soketu
aspoň jeden datagram.
• jestliže inetd restartuje server (kromě stream nowait) příliš často (cca jednou za sekundu), usoudí, že nastala chyba a po určitou dobu (asi 10 minut)
službu zablokuje (nespouští server a odmítá spojení). Ostatní servery spouští
normálně dál.

204

Syslog, newsyslog
• různé služby je dobré logovat do různých souborů
• je dobré mít jeden společný interface
• některé služby syslog nepoužívají (typicky apache – httpd)
• logovat je vhodné na samostatnou partition
• většina síťových zařízení podporuje logování na vzdálených syslog
server
• log soubory je nutné rotovat
• administrátor definuje počet rotací, limit velikosti log souboru
• lepší je ponechat více dat než méně – pokud máte místo

• existují programy, které dokáží log soubory zpracovat a vygenerovat užitečné
statistiky. To je vhodné například u web, ftp serverů apod.
• zde je opět vidět, jak je aplikována jedna ze základních myšlenek UNIXu –
definuje nástroje, které mají dělat jednu věc a dobře. Je zbytečné, aby syslog
uměl svoje log soubory i rotovat, naopak newsyslog je pak možné použít i
pro rotaci takových log souborů, které si vytvářejí různé služby samy – httpd
apod.

205

Konec

206

