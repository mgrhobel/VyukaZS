---
title: "vlakna4.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/FPE Volume P/vlakna4.pdf"
date: 2006-10-03
type: PDF (text-based)
---

Operační systémy -- Procesy

II-05

Pojetí procesů
 OS zprostředkovává více různě pojmenovaných provádění

programů

• dávkové systémy – úlohy, dávky (jobs)
• systémy se sdílením času (multiuživatelské, multitakingové)
– procesy (processes, tasks), vlákna (threads)

Procesy

 budeme používat generický pojem proces,

příp. pojem vlákno pro „dílčí“ proces v rámci „procesu“
 proces

 Pojetí procesu
 Plánování procesů

• akt provádění programu
• běh procesu má sekvenční charakter

 Operace s procesy

 Proces lze sledovat

• posloupnost operací a stavů pamětí proces obsahuje
• čítač instrukcí, zásobník, datovou sekci, program
II-05

Jan Staudek, FI MU Brno, Operační systémy -- Procesy

1

II-05

Jan Staudek, FI MU Brno, Operační systémy -- Procesy

Klíčová role procesů v OS

Stavy procesu

 hierarchické rodiny procesů
• rodič, potomek (proces vytvořený na žádost jiného procesu –
rodiče)
sourozenec (procesy vytvořené jedním rodičem)

 proces ve svém běhu prochází více stavy:

• nový
• běžící

2

právě vytvořený proces
jeho program se právě realizuje
některým procesorem
• čekající
– waiting:
čeká až nastane jistá událost
• připravený – ready:
čekají na přidělení procesoru
• ukončený – terminated: ukončil své provádění

 OS
• maximalizuje využití procesoru prokládáním běhů procesů
• minimalizuje dobu odpovědi prokládáním běhů procesů
• spravuje prostředky přidělováním procesům podle vhodné politiky
¾ priorita, vzájemná výlučnost
¾ a musí přitom zabránit “uváznutí” procesů
• podporuje optimální strukturování aplikačních systémů
¾ podporuje tvorbu procesů a meziprocesovou komunikaci

– new:
– running:

 všechny OS s multiprogramováním

jsou založeny konceptu „proces“

 „Proces“ je mnohdy nazýván „task“
II-05

Jan Staudek, FI MU Brno, Operační systémy -- Procesy

Jan Staudek, FI MU Brno

3

II-05

Jan Staudek, FI MU Brno, Operační systémy -- Procesy

4

1

Operační systémy -- Procesy

II-05

Process Control Block (PCB)

Proces existuje ve virtuální paměti

 Tabulka OS obsahující informace

potřebné pro
definici a správu procesu

• stav procesu
• čítač instrukcí
• registry procesoru
• informace potřebné pro plánování CPU
• informace potřebné pro správu paměti
• účtovací informace
• informace potřebné pro správu I/O

LAP2

jádro, komunikační prostor
II-05

Jan Staudek, FI MU Brno, Operační systémy -- Procesy

5

CPU mezi procesy přepíná OS

II-05

Jan Staudek, FI MU Brno, Operační systémy -- Procesy

6

Proč se používá multitasking?
 interaktivní zpracování – zkrácení doby odpovědi
 zvýšení stupně multitaskingu – zvýšení využití

procesoru

procesor

• pravděpodobnost,
že proces čeká na V/V,
tj. neběží

p = t v/v / (tp + t v/v)

Jan Staudek, FI MU Brno, Operační systémy -- Procesy

Jan Staudek, FI MU Brno

µ [%]
100

p=0.1

80

p=0.5

že v tomto stavu se nachází
60
n procesů

dispečer
II-05

V/V

• model

činnost OS
vyvolaná
přerušením
nebo
voláním
systému

pn

40

a využití procesoru
n procesy

20

µ = 1 - pn
7

II-05

p=0.7
p=0.9
n

2

4

Jan Staudek, FI MU Brno, Operační systémy -- Procesy

6

8

10
8

2

Operační systémy -- Procesy

II-05

Fronty plánování procesů

Fronty procesů – příklad

 fronta úloh

Fronta připravených procesů
a několik front na
I/O zařízení

• množina všech procesů v systému
 fronta připravených procesů – ready

• množina procesů sídlících v hlavní paměti a připravených k běhu
 fronta na zařízení

• množina procesů čekajících I/O zařízení
 fronta odložených procesů

• množina procesů čekajících na přidělení místa v hlavní paměti
 fronta na semafor

• množina procesů čekajících synchronizační událost
 …
 Procesy mezi různými frontami migrují
II-05

Jan Staudek, FI MU Brno, Operační systémy -- Procesy

9

II-05

Jan Staudek, FI MU Brno, Operační systémy -- Procesy

Plánovače v OS – strategický a dispečer

Odkládání, swapping

 Dlouhodobý plánovač



(strategický plánovač, job scheduler)

• alespoň částečně

• vybírá který proces lze zařadit mezi připravené procesy
 krátkodobý plánovač

Každý proces se jednou musí
dostat do RAM



(operační plánovač, dispečer):

• reprezentace správy
procesoru(-ů)
• vybírá, který proces
poběží a přiděluje
mu procesor (CPU)



I když se použije virtuální
paměť, příliš mnoho procesů v
RAM snižuje výkonnost
OS musí provádění některých
procesů odložit
• tj. „plácnout“ je na disk



dva další stavy
• odložený čekající
• odložený připravený



přechody mezi stavy
• čekající → odložený čekající
¾

Jan Staudek, FI MU Brno, Operační systémy -- Procesy

Jan Staudek, FI MU Brno

11

II-05

všechny procesy jsou
čekající a OS dělá prostor
pro přidělení běžícímu procesu

• odložený čekající →
odložený připravený
¾

stala se očekávaná událost
(stavovou info má OS přístupnou)

• odložený připravený →
připravený
¾

fronta připravených se vyprázdnila
(skoro)

• připravený →
odložený připravený
¾
¾

II-05

10

(nepravděpodobné)
nejsou čekající procesy a je potřeba
uvolnit RAM

Jan Staudek, FI MU Brno, Operační systémy -- Procesy

12

3

Operační systémy -- Procesy

II-05

Plánovače v OS (2) – taktika s FAP

5-stavový model

 Střednědobý plánovač

 Odložené procesy

obnova

odložené procesy

odložení
běží

uvolňují operační
paměť :

(taktický plánovač)

• vybírá který proces lze zařadit mezi odsunuté procesy
• vybírá který odsunutý proces lze zařadit mezi připravené procesy

• je mnoho čekajících procesů
• uživatel –
spuštění
vlastník
ukončení
vytvoření
procesu
připravený
běžící
si to přeje
potlačení
čas, priorita
• předpisuje
obnova
potlačení
to časový
odložení
čekání na událost
odložený,
aktivace
plán
aktivace
připravený
vznik události
• přeje
čekající
čekající
čekající
si to rodič
odložení
z důvodu
aktivace’
synchronizace
ukončení
odložený,
sourozenců, ...

 Logicky náleží částečně i do správy hlavní paměti

• taktika využívání omezené kapacity FAP při multitaskingu

čekající

II-05

Jan Staudek, FI MU Brno, Operační systémy -- Procesy

13

II-05

Jan Staudek, FI MU Brno, Operační systémy -- Procesy

Plánovače v OS (3) – přehled

Přepnutí kontextu

 krátkodobý plánovač – dispečer
• vyvoláván velmi často, řádově v intervalech milisekund
• musí být velmi rychlý
• přiděluje procesor procesům

 vyžádá se služba, akceptuje se některé asynchronní

přerušení, obslouží se a nově se vybere jako běžící proces

 proces i – operační systém – proces j : přepnutí kontextu
 když OS přepojuje CPU z jednoho procesu na jiný proces,

 dlouhodobý plánovač
• vyvoláván řídce, řádově v intervalech sekundy až minuty
• nemusí být rychlý
• definuje stupeň multiprogramování

musí

• nejprve uchovat (zapamatovat v PCBi) stav původně běžícího
procesu i a poté
• zavést stav nově běžícího procesu j (z PCBj)

 Procesy lze charakterizovat jako
• vázané na I/O – I/O-bound process
¾ více času se řeší I/O než vlastní výpočty v CPU, CPU se využívá
nárazově více krátkými dávkami
• vázané na procesor – CPU-bound process
¾ více času se řeší vlastní výpočty v CPU než I/O, CPU se využívá v málo
dlouhých dávkách

 přepnutí kontextu představuje režijní ztrátu (zátěž)
• během přepínání systém nedělá nic efektivního

II-05

II-05

Jan Staudek, FI MU Brno, Operační systémy -- Procesy

Jan Staudek, FI MU Brno

14

15

 doba přepnutí závisí na rozsahu hardwarové podpory
• minimální hardwarová podpora při přerušení:
¾ uchování čítače instrukcí ve vektoru přerušení
¾ zavedení čítače instrukcí hodnotou adresy vstupního bodu z vektoru
přerušení
Jan Staudek, FI MU Brno, Operační systémy -- Procesy

16

4

Operační systémy -- Procesy

II-05

Vytvoření procesu

Vytvoření procesu (2)

 rodič [čovský proces] vytváří procesy potomky

 adresový prostor (jeden ze zdrojů)

• potomek je úplným duplikátem rodiče a každý z obou procesů se
při vytváření procesu dozvídá zda je rodič nebo potomek
• do potomkova adresového prostoru se při vytváření procesu
zavádí program určený rodičem

 Potomci mohou vystupovat v roli rodičů a vytvářet svoje

potomky, …

 formuje se tak strom genealogický strom procesů
 Sdílení zdrojů – varianty

• rodič a potomek sdílejí zdroje původně vlastněné rodičem
• potomek sdílí rodičem vyčleněnou podmnožinu zdrojů s rodičem
• potomek a rodič jsou plně samostatné procesy, nesdílí žádný zdroj

 UNIX examples

• volání systému fork
vytváří nový proces
• volání systému exec
se použije po volání
systému fork pro
náhradu programu
v adresovém
prostoru procesu
novým programem

 Běh

• rodič a potomek může běžet souběžně
• rodič čeká na ukončení potomka

II-05

Jan Staudek, FI MU Brno, Operační systémy -- Procesy

17

II-05

Jan Staudek, FI MU Brno, Operační systémy -- Procesy

Ukončení procesu

Kooperující procesy

 Proces provede poslední příkaz a žádá OS o (své) ukončení

 Nezávislé procesy
• nemohou se vzájemně ovlivňovat

(exit)

 Přínosy kooperace procesů
• sdílení informací
• urychlení výpočtů
• modularita
• pohodlí

 O ukončení procesu-potomka žádá jeho rodič (abort),

protože (např.)

• potomek překročil stanovenou mez potřeby zdrojů
• úkol přidělený potomkovi rodič dále nepotřebuje
• Rodič kočí svoji existenci a nebylo povoleno, aby potomek přežil
svého rodiče

II-05

 Příklady typových úloh (paradigmat) kooperace
• producent – konzument
• klient – server
• jejich rozbor je předmětem magisterského studia

může docházet ke kaskádnímu ukončování

Jan Staudek, FI MU Brno, Operační systémy -- Procesy

Jan Staudek, FI MU Brno

18

 Kooperující procesy
• mohou ovlivňovat běh jiných procesů nebo jiné procesy mohou
ovlivňovat jejich běh

• výstupní data procesu-potomka se předají procesu-rodiči,
který čeká v provádění služby wait
• Zdroje končícího procesu se uvolňují operačním systémem

¾

genealogický strom
procesů v Unixu

19

II-05

Jan Staudek, FI MU Brno, Operační systémy -- Procesy

20

5

