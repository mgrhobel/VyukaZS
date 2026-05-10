---
title: "vlakna3.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/prednasky/vlakna3.pdf"
date: 2009-02-19
type: PDF (text-based)
---

Operační systémy pro řízení

Cvičení 4.

4. Cvičení OSŘ
Vlákna, procesy, plánování…
Vlákna vs. Procesy
Pro snadnější pochopení rozdílu mezi vlákny a procesy si zavedeme analogii s domem. Dům
je v podstatě kontejner (jakési uložiště) s určitými atributy (jako je počet pater, počet
oken….). Sám o sobě dům aktivně nic nevykonává, jedná se o pasivní objekt a to dokonale
popisuje proces. Oproti tomu vlákna (threads) by v této analogii odpovídali lidem žijícím
v domě. Lidé jsou aktivní objekty (používají jednotlivé pokoje domů, sledují TV, vaří,
sprchují se …). Graficky lze proces a jeho vlákna znázornit jako je tomu na obr.1.
Jedno-vláknový proces (single threaded) - pokud žije v domě pouze jeden člověk, může bez
omezení a kdykoliv ve svém domě dělat cokoliv.
Více-vláknový proces (multi threaded) - situace se dramatizuje když do domu nastěhujete
dalšího člověka. Najednou není možné kdykoliv si dát sprchu, protože druhá osoba ji může
právě používat. Pokud jsou v domě dvě dospěle osoby není třeba se zabývat otázkami např.
bezpečnosti, protože předpokládáte, že druhá osoba nezačne podpalovat kuchyň apod.
Přidejme do domu nějaké dětičky a náhle celá situace začne být mnohem zajímavější.
Z předchozího textu můžeme vypozorovat následující srovnaní. Tak jako dům obsazuje
skutečný prostor na stavební parcele, tak proces obsazuje paměť. A stejně tak jako obyvatelé
domu mohou jít do kteréhokoliv pokoje, tak všechna vlákna daného procesu mají přístup do
této paměti. Pokud si vlákno něco alokuje (např. doma se objeví nový počítač ☺ ), všechny
ostatní vlákna okamžitě získávají přístup k této věci. Podobně když proces alokuje nějakou
paměť, tato paměť je stejně tak dostupná pro všechny vlákna. V takovém případě je však
nutné synchronizovat přístup vláken k takovéto společné paměti. Pokud je zajištěno že do
paměti přistupuje jen určité vlákno, nutnost synchronizace odpadá.
Proces

Vlákno
Obr.1. Grafické znázornění vícevláknového procesu
Každý proces v systému obsahuje minimálně jedno vlákno, které se nazývá hlavní.
Disponuje-li systém pouze jedním procesorem pak v jeden časový okamžik může běžet pouze
jedno vlákno. V případě víceprocesorového systému s identickými procesory sdílejícími
paměť a zařízení (tzv. SMP – Symetrical Multi Procesor) je počet vláken běžících v jeden
časový okamžik zároveň limitován počtem procesoru.

-1-

Operační systémy pro řízení

Cvičení 4.

Funkce jádra při práci s vlákny
Kdo tedy rozhoduje o tom, které vlákno poběží v daném časovém okamžiku?
Toto je práce kernelového jádra. Kernel rozhoduje (mimo jiné), kterému vláknu bude přiřazen
CPU v daný moment a provede tzv. přepnutí kontextu (context switching). CPU obsahuje
registry (přesný počet závisí na rodině procesorů x86, MIPS,…) v nichž jsou v době běhu
vlákna uloženy informace o běhu vlákna (např. současná pozice v programu). Pokud tedy
kernel rozhodne o tom, že by mělo běžet jiné vlákno pak je třeba:
1. uložit registry a další kontextové údaje doposud běžícího vlákna
2. nahrát registry a kontext nového vlákna do CPU
Ale na základě čeho kernel rozhodne, že by mělo běžet jiné vlákno?
To pochopitelně záleží na tom, zda-li je dané vlákno připraveno a schopno použít CPU
v konkrétní okamžik. Ne všechny vlákna mohou být k tomuto připraveny. Některá se mohou
nacházet v rozličných blokovacích stavech. Zajímavější situace nastane pokud několik vláken
je najednou schopno použít procesor.
Koho má kernel vybrat?
Při tomto výběru hrají roli dva faktory: (vyhodnocované v tomto pořadí)
• priorita
• plánovací algoritmus (scheduling algorithm)
Priorita
Každé vlákno má v systému přiřazenu prioritu. Ta se může nezávisle na plánovacím
algoritmu pohybovat v rozsahu 1 - 63, kde 63 je nejvyšší priorita. Existuje ještě speciální
vlákno "idle" (v proces manažeru)
na prioritní úrovni 0, jenž je vždy
připraveno k běhu a zabírá
procesor v případě, že žádné
vlákno není ve stavu READY.
Vlákna jsou ve frontě připravených
vláken řazena podle své priority
(obr.2.) Fronta je implementována
jako 64 samostatných front, jedna
pro každou prioritní úroveň.
Vlákna jsou v těchto frontách
řazena FIFO způsobem. Pro běh je
vybráno první vlákno s nejvyšší
prioritou (z nejvyšší prioritní
fronty). Pokud jiné vlákno
připravené pro použití procesoru
(tj. ve stavu READY) a má vyšší
prioritu než vlákno běžící, dojde
okamžitě k přepnutí kontextu.
Obr.2. Prioritní fronta Ready vláken

-2-

Operační systémy pro řízení

Cvičení 4.

Pozn. Pro zjištění maximální a minimální hodnoty priority slouží C funkce
sched_get_priority_max() a sched_get_priority_min() umístěné v hlavičkovém soboru
<sched.h>.
V případě, že je několik vláken připraveno na převzetí CPU společně s jedním, které zrovna
CPU používá a všechny mají stejnou prioritu, pak při rozhodování o přepnutí kontextu
přichází na řadu přichází plánovací algoritmus.
Plánovací algoritmus
Kernelové jádro (Neutrino) rozlišuje dva plánovací algoritmy (politka)
•
•

FIFO
Round Robin (RR)

FIFO politika umožňuje procesu používat CPU tak dlouho, jak potřebuje. Teoreticky takovéto
vlákno může běžet třeba věčně. Pokud vlákno skončí nebo jiným způsobem „vrátí“ CPU, pak
CPU je přiděleno následujícímu vláknu čekající ve frontě READY vláken na příslušné
prioritě. Pokud na této úrovni nejsou žádné další čekající vlákna, pak kernel prochází fronty
na nižších prioritních úrovních.
Round Robin plánovací algoritmus je identický s FIFO s výjimkou toho, že vlákno nemůže
běžet neomezenou dobu, pokud existuje READY vlákno o stejné prioritě. Takové vlákno běží
jen v předdefinovaném časovém okamžiku tzv. timeslice, který je fixně daný a nemůže být
měněn. (jeho velikost vrací funkce sched_rr_get_interval() )

Obr.3 FIFO a Round Robin plánování
Shrnutí plánovacích pravidel (pro jednoprocesorový systém) v pořadí podle důležitosti
• Pouze jedno vlákno může běžet v daný okamžik
• Vlákno s nejvyšší prioritou ve stavu READY( schopno využít CPU ) poběží
• Vlákno poběží, dokud nebude ukončeno či zablokováno
• Vlákno s plánováním RR poběží maximálně po dobu tzv. timeslice, a pak kernel provede
přeplánování (pokud je vyžadováno)

-3-

Operační systémy pro řízení

Cvičení 4.

Funkce pro získávání informací o prioritě a plánovacích algoritmech procesu jsou uvedeny
v následující tabulce. Před jejich použitím je nutno připojit hlavičkový soubor <sched.h>
Volání POSIX
sched_getparam()
sched_setparam()
sched_getscheduler()
sched_setscheduler()

Volání Mikrokernelu
SchedGet()
SchedSet()
SchedGet()
SchedSet()

Popis
Získání priority
Nastavení priority
Získání plánovacího algoritmu
Nastavení plánovacího algoritmu

Funkce pracují s datovým typem sched_param_t, což je datová struktura obsahující mj.
prioritu procesu (.sched_priority)
Stavy vláken
V předchozím textu jsme se již zmínili o pojmech běžící, připraveno na CPU a blokované
vlákno. Tyto pojmy souvisí se stavem, ve kterém se vlákno nachází. Existují tři hlavní stavy
vláken.
•

RUNNING – běžící stav jednoduše znamená, že vlákno využívá přidělené CPU. Na
jednoprocesorovém systému může být pouze jedno vlákno v tomto stavu.

•

READY - stav připraven znamená, že toto vlákno může okamžitě běžet, avšak neběží,
protože jiné vlákno je v tuto chvíli ve stavu RUNNIG.

•

BLOCKED – ke stavu zablokován dochází ve všech ostatních případech, tj. když vlákno
čeká na určitou událost, např z důvodu synchronizace, čekaní na zprávu apod. V Neutrinu
existuje asi tucet různých blokovacích stavů, a to proto, že si jádro tímto uchovává
informaci o důvodu, proč došlo k zablokování vlákna. (výpis všech stavů vláken je
k dispozici v souboru <sys/neutrio.h> )

Všechny ostatní stavy vláken jsou znázorněny na následujícím obr.4.
Pozn. Mějte na paměti, že pokud je vlákno ve stavu BLOCKED, pak bez ohledu na důvod
svého blokovaní nijak nezatěžuje procesor.

-4-

Operační systémy pro řízení

Cvičení 4.

Obr.4. Možné stavy vláken v systému

Vztah mezi vlákny a procesy
Už víte, že je možné mít proces s jedním nebo více vlákny (proces bez vlákna nebude schopen
nic dělat). Systém s jádrem Neutrino může mít jeden či více procesů. Každý proces je
zodpovědný za poskytování služby určitého druhu (souborový systém, ovladač zobrazovače,
řídicí modul….). Uvnitř každého procesu může být rozdílný počet vláken. O tom kolik bude
mít proces vláken rozhoduje programátor a záleží na povaze problému, který řeší.
Proč vlastně existují procesy? Proč nemít jeden proces s několika tisíci či milióny vláken?
Výhody rozdělení do více procesu spočívá v modularitě, minimální spřaženosti,
udržovatelnosti a spolehlivosti celého systému.
Nejpatrnější je zvýšení spolehlivosti systému. Vlákno může přistupovat k paměti pouze uvnitř
procesu, čímž je vlastně dokonale izolováno od ostatních vláken jiných procesů.
Adresní prostor procesu je přidělen po spuštění procesu tzv. procesním manažerem (process
manager) a dojde ke spuštění hlavního vlákna. Přidělená paměť je označena a je ve
vlastnictví procesu. Pokud kernel potřebuje přepnout kontext mezi vlákny jednoho procesu,
celá operace je velmi efektivní. Není totiž nutné měnit adresní prostor. V opačném případě
k této záměně dochází a ta je spojená s vyšší režií = zabere více času.
Např.Pro testovací účely si napíšeme program v C, který bude cyklicky vypisovat na
obrazovku obsah citace, který se bude v každém kroku zvyšovat.
-5-

Operační systémy pro řízení

Cvičení 4.

#include <stdio.h>
int main(void)
{
int i=0;
while (0==0)
{
printf(" %d \n",i);
i++;
}
}
Po uložení souboru na disk, vytvořte ze souboru bineární spustitelný program jeho
překompilováním. K tomuto účelu lze použít řádkový překladač gcc. Tento překladač
disponuje množstvím nastavovacích parametrů. Pro standardní kompilaci pod x86 lze použít
příkaz make (make program).
Na tomto příkladu si lze vyzkoušet vliv priorit na vykonávání programu. Spusťte vámi
vytvořený program s prioritou 8 (nice -2 ./program) . V druhém terminálu udělejte totéž,
avšak s prioritou o 1 vyšší (nice -1 ./program). Prioritu si pak za běhu můžete měnit pomocí
renice -1 PID nebo slay –P10 program.¨

Spouštění procesu z programu
V předchozích cvičeních jsme si ukázali jak spustit proces z příkazové řádky (shellu), což je
v podstatě základní požadavek na shell. Nyní se zaměříme přímo na funkce poskytované
Neutrinem.
• system()
• exec() rodina funkcí
• spawn() rodina funkcí
• fork()

system()
Volání system() se jeví jako nejjednodušší varianta. Funguje stejně jako příkazová řádka, ve
skutečnosti spouští instanci shellu pro zpracování zadaného příkazu.
Příklad: system("ls -l");

spawn()
Volání funkce z rodiny spawn*() vytvoří jiný proces (s novým PID), který je shodný s
programem uvedeným jako parametr funkce. Pouze dvě z funkcí spawn() a spawnp()
odpovídají normě POSIX. Ostatní jsou implementací v systému QNX, viz. nápověda

-6-

Operační systémy pro řízení

Cvičení 4.

Význam jednotlivých přípon (i v případě rodiny exec*()) je tento:
Přípona
Význam
L (malé Seznam argumentů je určen pomocí seznamu parametrů vlastního volání
L)
zakončeného argumentem NULL.
Je předáno prostředí - Seznam proměnných prostředí zakončených argumentem
e
NULL.
p
V případě, že není určena úplná cesta, je použita proměnná prostředí PATH.
v
Seznam argumentů je předán pomocí ukazatele na argumentový vektor.
Příklad:
spawnl (P_WAIT, "/bin/ls", "/bin/ls", "-a", "-l", NULL);
Vypíše pracovní adresář nového procesu. Jedná se o široký výpis i se skrytými soubory. V
shellu: "ls -a -l"
První argument určuje chování procesů:
P_WAIT
Volající proces je zablokován dokud nově vytvořený program neskončí.
P_NOWAIT Oba programy běží konkurenčně - volající proces není blokován.
P_NOWAITO Jako předchozí, ale nelze použít funkci wait() pro získání návratového kódu.
Zamění volající program za volaný beze změny PID. Stejné jako funkce z
P_OVERLAY
rodiny exec*()

exec()
Volání funkce z rodiny exec*() zamění aktuální proces za nově vytvářený. Proces nemění
PID. Pouze dvě z funkcí execlpe() a execvpe() neodpovídají normě POSIX.
Příklad:
execl ("/bin/ls", "/bin/ls", "-a", "-l", NULL);
Vypíše pracovní adresář transformovaného procesu. Jedná se o široký výpis i se skrytými
soubory. V shellu: "ls -a -l"

fork()
Vytvoří přesnou kopii procesu. Ta běží souběžně s rodičovským procesem. Procesy mají
stejný kód a data. Stejné jsou také deskriptory otevřených souborů. PID jednotlivých procesů
se však liší, jelikož nelze vytvořit dva procesy se stejným identifikátorem. Existuje ješte
několik rozdílů, které lze snadno zjistit v "Library reference".
Rozlišit mezi rodičovským a nově vytvořeným procesem lze pomocí návratové hodnoty
funkce fork. U nově vytvořeného procesu je rovna nule a u procesu rodičovského je to PID
nového procesu.

-7-

Operační systémy pro řízení

Cvičení 4.

Příklad:
printf ("PID rodicovskeho procesu je %d\n", getpid ());
fflush (stdout);
if (child_pid = fork ()) {
printf ("Toto je rodicovsky proces,pid nového procesu je %d\n",child_pid);
}
else {
printf ("Hlásí se nový proces, pid je %d\n", getpid ());
}

Následuje příklad,v němž budou jednotlivé metody spouštění procesu vyzkoušeny pro
porovnání.
/*
*
Spousteni procesu z procesu:
*
demonstracni program pro ukazku funkci system, spawn, exec, fork
*/
#include <stdio.h>
// hlavickove soubory nutne ke kompilaci
#include <stdlib.h>
// jsou uvedeny v napovede ke kazde funkci
#include <process.h>
#include <sys/types.h>
int main(void)
// hlavni program
{
int volba;
// delkarace pouzivanych promennych
int rs;
// návratová hodnota
char konec=0;
// ukončení programu
while (konec==0){
printf("\nJak spustit proces ?");
printf("\n1] command");
printf("\n2] spawn");
printf("\n3] exec");
printf("\n\n4] fork \n VOLBA >>");
scanf("%d",&volba);
switch (volba){
// v zavislosti na zvolene volbe vetveni programu
case 1:
rs=system("ls /");
// predani rizeni shellu a pe provedeni prikazu rizeni vraceno
// rodicovskemu procesu
printf("\n System return status : %d",rs);
break;
case 2:
spawnl(P_WAIT,"/bin/ls","/bin/ls","ls",NULL);
// vytvari novy proces, Rodicovsky proces ceka na ukonceni
// (P_WAIT) nove vytvor. Procesu
break;
case 3:
execlp("ls","ls",NULL);
// zamena aktualniho procesu za novy (shodne PID)
break;
case 4:
printf("pred FORK");
//
vytvoreni noveho procesu a soubezny beh obou procesu
rs=fork();
printf("za FORKem, new PID: %d",rs);
break;
default:konec=1;
}
}
return EXIT_SUCCESS;
}

-8-

