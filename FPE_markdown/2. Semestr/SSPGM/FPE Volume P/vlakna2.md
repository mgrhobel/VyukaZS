---
title: "vlakna2.htm"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/FPE Volume P/vlakna2.htm"
date: 2006-10-03
type: HTML
---

[![\[ Title \]](vlakna2_soubory/title.gif){height="26" width="29"
align="bottom" border="0"}](http://home.zcu.cz/~mlazar/dpma/dpma.html)
  [![\[ « \]](vlakna2_soubory/prev.gif){height="26" width="29"
align="bottom"
border="0"}](http://home.zcu.cz/~mlazar/dpma/dpma-node12.html)   [![\[ »
\]](vlakna2_soubory/next.gif){height="26" width="29" align="bottom"
border="0"}](http://home.zcu.cz/~mlazar/dpma/dpma-node14.html)   [![\[
Index \]](vlakna2_soubory/index.gif){height="26" width="29"
align="bottom"
border="0"}](http://home.zcu.cz/~mlazar/dpma/dpma-node42.html)   [![\[
Download \]](vlakna2_soubory/download.gif){height="26" width="29"
align="bottom"
border="0"}](http://home.zcu.cz/~mlazar/dpma/download/index.php)

------------------------------------------------------------------------

-   [2.3.1 Vlákna
    POSIX](http://home.zcu.cz/~mlazar/dpma/dpma-node13.html#SECTION00431000000000000000){#tex2html620}
    -   [2.3.1.1 Vytvoøení a ukonèení
        vlákna](http://home.zcu.cz/~mlazar/dpma/dpma-node13.html#SECTION00431100000000000000){#tex2html621}
    -   [2.3.1.2 Kritické sekce a
        mutexy](http://home.zcu.cz/~mlazar/dpma/dpma-node13.html#SECTION00431200000000000000){#tex2html622}
    -   [2.3.1.3
        Semafory](http://home.zcu.cz/~mlazar/dpma/dpma-node13.html#SECTION00431300000000000000){#tex2html623}
-   [2.3.2
    OpenMP](http://home.zcu.cz/~mlazar/dpma/dpma-node13.html#SECTION00432000000000000000){#tex2html624}
    -   [2.3.2.1 Paralelní
        konstrukce](http://home.zcu.cz/~mlazar/dpma/dpma-node13.html#SECTION00432100000000000000){#tex2html625}
    -   [2.3.2.2 Knihovní funkce a promìnné
        prostøedí](http://home.zcu.cz/~mlazar/dpma/dpma-node13.html#SECTION00432200000000000000){#tex2html626}
-   [2.3.3 Standard ANSI
    X3H5](http://home.zcu.cz/~mlazar/dpma/dpma-node13.html#SECTION00433000000000000000){#tex2html627}
-   [2.3.4 Preprocesor
    KAP](http://home.zcu.cz/~mlazar/dpma/dpma-node13.html#SECTION00434000000000000000){#tex2html628}
-   [2.3.5 HPF - High Performance
    Fortran](http://home.zcu.cz/~mlazar/dpma/dpma-node13.html#SECTION00435000000000000000){#tex2html629}
    -   [2.3.5.1 Programový model
        HPF](http://home.zcu.cz/~mlazar/dpma/dpma-node13.html#SECTION00435100000000000000){#tex2html630}
    -   [2.3.5.2 Distribuce
        dat](http://home.zcu.cz/~mlazar/dpma/dpma-node13.html#SECTION00435200000000000000){#tex2html631}
    -   [2.3.5.3 Paralelní konstrukce
        HPF](http://home.zcu.cz/~mlazar/dpma/dpma-node13.html#SECTION00435300000000000000){#tex2html632}
    -   [2.3.5.4 Mapování
        dat](http://home.zcu.cz/~mlazar/dpma/dpma-node13.html#SECTION00435400000000000000){#tex2html633}
    -   [2.3.5.5 Vnitøní
        funkce](http://home.zcu.cz/~mlazar/dpma/dpma-node13.html#SECTION00435500000000000000){#tex2html634}
    -   [2.3.5.6 HPF verze
        2.0](http://home.zcu.cz/~mlazar/dpma/dpma-node13.html#SECTION00435600000000000000){#tex2html635}
-   [2.3.6 Dal¹í prostøedky pro programování tìsnì vázaných
    systémù](http://home.zcu.cz/~mlazar/dpma/dpma-node13.html#SECTION00436000000000000000){#tex2html636}

------------------------------------------------------------------------

# []{#SECTION00430000000000000000}[]{#sw_shared} 2.3 Prostøedky pro programování tìsnì vázaných systémù

Tìsnì vázané systémy byly popsány v kap.
[1.3.2](http://home.zcu.cz/~mlazar/dpma/dpma-node6.html#sharedmem).
Nejvýznamnìj¹ím rysem je ulo¾ení informací v jedné sdílené pamìti a
pøístup k této pamìti ze v¹ech procesorù v poèítaèi.

Stejnì jako u volnì vázaných systémù, i zde mù¾eme rozdìlit paralelní
prostøedky na specializované programovací jazyky a na knihovny funkcí
pro univerzální programovací jazyky. Èasto je roz¹íøen nìkterý bì¾ný
programovací jazyk (obvykle Fortran, nebo C) o paralelní konstrukce
pomocí direktiv. Takto funguje napøíklad HPF, OpenMP, KAP, X3H5 a dal¹í.
Struèná charakteristika tìchto prostøedkù bude uvedena v samostatných
odstavcích dále.

Tìsnì vázané systémy lze také programovat zasíláním zpráv. Knihovny PVM
a MPI lze tedy pou¾ít i na systémech se sdílenou pamìtí. Zpráva
neprochází sí»ovým rozhraním, zaslání je simulováno sdílenou pamìtí.

## []{#SECTION00431000000000000000}[]{#pthread} 2.3.1 Vlákna POSIX

[]{#4085}[]{#4086}*Proces (process)* je souhrn kódù programu, dat
programu, zásobníku, údajù o procesem otevøených souborech a dal¹ích
informací. V¹echny tyto informace má proces soukromé a nemù¾e je
(jednodu¹e) sdílet s jiným procem. []{#4090}[]{#4091}*Vlákno (thread)*
si mù¾eme pøedstavit jako []{#4095}[]{#4096}*odlehèený proces
(lightweight process)*. Vlastní je jenom kód a zásobník, v¹e ostatní je
sdíleno s ostatními vlákny tého¾ procesu. Vlákno je podmno¾inou procesu
a proces mù¾e vlastnit nìkolik vláken.

V zaèátcích, kdy se zaèala vlákna objevovat, mìl ka¾dý operaèní systém
jiné aplikaèní rozhraní pro práci s vlákny, a proto byly programy ¹patnì
pøenositelné. Proto vznikla norma []{#4100}*POSIX*, která mimo jiné také
definuje aplikaèní rozhraní pro práci s vlákny (POSIX 1003.1c). Anglicky
se nìkdy vlákna POSIX zkrácenì oznaèují []{#4103}[]{#4104}*Pthread*.
Vlákna jsou realizována jako knihovna funkcí jazyka C.

Vlákna nejsou urèená pro nároèné výpoèty. Mají minimální podporu ve
Fortranu a chybí podpora datové paralelizace. Vlákna jsou spí¹e
systémový prostøedek na ni¾¹í úrovni. Pøesto se vlákna pou¾ívají i
v oblasti nároèných výpoètù. Proto se na vlákna POSIX v následujících
odstavcích podíváme trochu podrobnìji.

### [2.3.1.1 Vytvoøení a ukonèení vlákna]{#SECTION00431100000000000000}

Program zaène jako sekvenèní, tzn. ¾e vykonáváno je jen jedno vlákno.
Vlákno mù¾e voláním pøíslu¹né funkce vytvoøit dal¹í vlákna. Nové vlákno
zaène vykonávat funkci zadanou jako parametr.

Vlákno se mù¾e samo ukonèit, nebo mù¾e být ukonèeno jiným vláknem. Lze
také èekat na ukonèení jiného vlákna. Schématicky je to znázornìno na
obr.
[2.12](http://home.zcu.cz/~mlazar/dpma/dpma-node13.html#fig:thread).

::: {align="center"}
[]{#fig:thread}[]{#3634}

+-----------------------------------------------------------------------+
| ::: {align="center"}                                                  |
| ![\\includegr                                                         |
| aphics{pics/sw/pthread}](vlakna2_soubory/dpma-img90.gif){height="127" |
| width="585" align="bottom" border="0"}                                |
| :::                                                                   |
+-----------------------------------------------------------------------+

: **Obrázek 2.12:** Vytvoøení vlákna (`pthread_create()`), ukonèení
vlákna (`pthread_exit()`) a èekání na ukonèení vlákna
(`pthread_join()`). Chvíli bì¾í obì vlákna souèasnì. ©rafovanì je
vyznaèená oblast, kdy vlákno 1 èeká na ukonèení vlákna 2.
:::

### [2.3.1.2 Kritické sekce a mutexy]{#SECTION00431200000000000000}

Za []{#4108}*kritickou sekci* pova¾ujeme tu èást kódu vlákna, která
operuje nad sdílenými daty a hrozí, ¾e paralelnì mù¾e jiné vlákno
operovat nad stejnými daty. Dùsledkem mù¾e být nekonzistence dat.
Zabrání se tomu tak, ¾e do kritické sekce mù¾e vstoupit pouze jedno
vlákno. Takovéto kritické sekce se nazývají
[]{#4110}[]{#4111}[]{#4112}*vzájemné vylouèení (MUTual EXclusion,
MUTEX)*.

Mutex má dva stavy - zamèený a odemèený. Pøed vstupem do kritické sekce
se mutex zamkne. Po ukonèení práce se sdílenými zdroji se mutex uvolní.
Pøi pokusu zamknout zamknutý mutex (tj., kdy¾ kritickou sekci právì
vykonává jiné vlákno) je vlákno pozastaveno dokud se mutex neuvolní.
Také je mo¾né se pouze pokusit zamknout mutex. Pokud je ji¾ mutex
zamknutý, je proveden návrat s pøíslu¹ným návratovým kódem a vlákno
pokraèuje dál ve vykonávání, nesmí v¹ak do kritické sekce.

U mutexu se mù¾eme setkat s tím, ¾e bude tøeba mutex zamknout
v závislosti na podmínce. Toho lze dosáhnout voláním pøíslu¹né funkce
v kritické sekci. Tato funkce automaticky odemkne mutex, pozastaví
vlákno a èeká na signál od podmínky. Po pøíchodu signálu je mutex
uzamèen a tato funkce dokonèena. Signál lze zaslat jednomu (nelze
specifikovat kterému) vláknu, nebo v¹em vláknùm èekajícím na podmínku.
Èekání lze èasovì omezit.

### [2.3.1.3 Semafory]{#SECTION00431300000000000000}

[]{#4120}[]{#4121}*Semafory (semaphore)* se pou¾ívají pro podobný úèel
jako mutexy, a to pro kontrolování vstupu do kritických sekcí. Ale na
rozdíl od mutexu mù¾e být v sekci souèasnì více vláken. Semafor si
mù¾eme pøedstavit jako poèítadlo s poèáteèní hodnotou, kterou nastaví
u¾ivatel. V¾dy pøi vstupu do kritické sekce se èeká, dokud není hodnota
semaforu vìt¹í ne¾ nula. Pokud je, pak se hodnota zmen¹í o jednu a
vstoupí se do kritické sekce. Na konci sekce se hodnota semaforu
o jednièku zvedne.

## [2.3.2 OpenMP]{#SECTION00432000000000000000}

[]{#4125}[]{#4126}*OpenMP (Open Multi Processing)* je standard pro
programování paralelních aplikací na systémech se sdílenou pamìtí.
Pomocí direktiv a knihovních funkcí umo¾òuje OpenMP psát pøenositelné
paralelní aplikace v jazycích Fortran, C a C++. Direktivy roz¹iøují
výpoèetní model o paralelní konstrukce. Knihovní funkce a promìnné
prostøedí umo¾òují øízení paralelního programu za bìhu.

OpenMP pou¾ívá []{#4132}[]{#4133}*rozvìtvi a spoj (fork-join)* model
paralelního výpoètu. Internì u¾ívá OpenMP vlákna. Program zaène
\'\'vedoucí\'\' vlákno které provádí sekvenèní èást programu. Paralelní
úsek vykonává \'\'tým\'\' vláken vytvoøený vedoucím vláknem.

### [2.3.2.1 Paralelní konstrukce]{#SECTION00432100000000000000}

Paralelní konstrukce se vytváøejí pomocí direktiv. Ve¹kerá paralelnì
provádìná èást je uzavøena mezi dvojici direktiv `parallel` a
`end parallel`. Pøi vstupu do paralelní sekce lze definovat, kolik
vláken se má spustit. Uvnitø paralelní èásti lze definovat paralelní
konstrukce. U vìt¹iny direktiv lze uvést klauzule. Pomoci klauzulí lze
napøíklad urèit, které promìnné se mají sdílet a které mají být
soukromé. Speciální klauzulí `reduction` lze definovat paralelní
redukci.

OpenMP obsahuje direktivy pro vyznaèení paralelnì proveditelných smyèek,
souèasnì proveditelných èástí programu, kritických sekcí, synchronizaci,
atomických operací a dal¹ích paralelních konstrukcí. Referenèní pøehled
v¹ech direktiv lze najít
v \[[49](http://home.zcu.cz/~mlazar/dpma/dpma-node41.html#openmp_c)\]
pro jazyk C a
v \[[50](http://home.zcu.cz/~mlazar/dpma/dpma-node41.html#openmp_f)\]
pro jazyk Fortran.

### [2.3.2.2 Knihovní funkce a promìnné prostøedí]{#SECTION00432200000000000000}

Knihovní funkce se pou¾ívají k øízení (napø. nastavit poèet vláken) a
zji¹»ování informací o paralelním prostøedí (napø. poèet procesorù
v poèítaèi). Navíc je k dispozici mno¾ina obecnì pou¾itelných funkcí pro
práci se zámky a funkce pro práci s èasem.

Øídit paralelní program lze také pomocí promìnných prostøedí. Ovlivnit
lze napøíklad poèet vytvoøených vláken (promìnná `OPM_NUM_THREADS`).

## [2.3.3 Standard ANSI X3H5]{#SECTION00433000000000000000}

Skupina []{#4137}[]{#4138}*PCF (Parallel Computing Forum)*
standardizovala roz¹íøení jazyka Fortran pro architektury se sdílenou
pamìtí. Tato standardizace vedla pozdìji k vzniku standardu
[]{#4144}[]{#4145}*ANSI X3H5*. Tímto standardem se také inspirovalo
paralelní roz¹íøení jazyka C, známe pod názvem []{#4149}*Parallel C*.

Paralelizace spoèívá ve vkládání direktiv pro øízení paralelizace
(obdobnì jako u OpenMP). Lze specifikovat tyto úseky: paralelní úsek,
paralelní cykl, jednoprocesorovou sekci a sekci kritickou. Jsou také
k dispozici prostøedky pro synchronizaci.

## [2.3.4 Preprocesor KAP]{#SECTION00434000000000000000}

[]{#4152}*KAP Fortran Optimalizer* a []{#4155}*KAP C Optimalizer* patøí
mezi typické prostøedky pro []{#4158}[]{#4159}*automatickou
paralelizaci*. Automatická paralelizace probíhá v tìchto etapách:

1.  Analýza programu.
2.  Detekce èasovì nároèných cyklù, vhodných pro paralelizaci.
3.  Koneèné rozhodnutí o mo¾nosti paralelizace vybraných cyklù. Je
    zva¾ováno, zda paralelní provedení cyklu nedává pro pøípadné datové
    závislosti jiné výsledky ne¾ provedení sériové.
4.  Zmìna programu v místech uplatnìní paralelizmu, vytvoøení a øízení
    bìhu vláken. KAP pøesune pøíkazy v paralelním úseku do samostatné
    procedury a zajistí správné vyvolání této procedury prostøedky
    podpùrné knihovny.
5.  Zaji¹tìní synchronizace vláken na potøebných místech programu.

Mimoto, KAP provádí je¹tì skalární optimalizaci zdrojového programu
vzhledem k vlastnostem cílového mikroprocesoru a optimalizaci vyu¾ívání
rychlých vyrovnávacích pamìti (cache).

Programátor má mo¾nost doplnit do programu dodateèné direktivy pro
øízení optimalizace a direktivy pro sdìlování doprovodných informaci.
Tyto direktivy napomáhají pouze paralelizovat pøeklad. Jedná se
o []{#4161}[]{#4162}*øízenou automatickou paralelizaci*.

Je v¹ak mo¾né pøímo do programu vyznaèit paralelní konstrukce (obdobnì
jako u OpenMP). V tomto pøípadì jde o []{#4164}[]{#4165}*paralelizaci
øízenou*. Pro vyjádøení pøímo øízeného paralelizmu je preprocesorem KAP
akceptovaná podmno¾ina ji¾ zmínìného roz¹íøení jazyka Fortran podle
doporuèení ANSI X3H5.

## [2.3.5 HPF - High Performance Fortran]{#SECTION00435000000000000000}

V roce 1993 uveøejnilo HPF Fórum první verzi standardu
[]{#4167}[]{#4168}*HPF (High Performance Fortran)* (viz
\[[31](http://home.zcu.cz/~mlazar/dpma/dpma-node41.html#hpf)\]). V lednu
1997 byla uvolnìna verze 2.0. HPF je prvním pokusem o standardizaci
vy¹¹ího programovacího jazyka. Hlavním zámìrem tvùrcù standardu bylo
zpøístupnìní prostøedkù pro pøenositelné vyjádøení a vyu¾ití paralelizmu
programátorùm bez nutnosti zacházení s podrobnostmi na úrovni
architektury cílového poèítaèe. Dále byla respektována poptávka po
mo¾nostech pøenosu stávajících, pøevá¾nì fortranských programù pro
nároèné vìdecké výpoèty do paralelního prostøedí.

Nevýhoda HPF je, ¾e kompilátory produkují programy nároèné na zdroje
(pamì», výkon CPU, rychlá komunikace). Výsledné programy nebývají v¾dy
efektivní a stabilní. Specifikace jazyka HPF je velmi rozsáhlá,
komplikovaná a nìkdy i nesrozumitelná. Zejména pro nepoèítaèového
specialistu zahrnuje pøíli¹ mnoho drobností. Zátì¾ dlouhodobé zpìtné
kompatibility je a¾ pøíli¹ citelná. HPF nemù¾e zatím zajistit
dostateènou podporu pro nestrukturovaný paralelizmus. Pro znaènou èást
aplikací je tedy nutné pou¾ít metodu zasílání zpráv. Pøesto se HPF
znaènì roz¹íøil a proto se na nìj podíváme podrobnìji.

### [2.3.5.1 Programový model HPF]{#SECTION00435100000000000000}

Programový model HPF má zejména tyto vlastnosti:

-   Výpoèetní postup je popisován jednovláknovým programem.
-   Promìnné programu jsou viditelné v rámci jednotného globálního
    prostoru jmen.
-   Promìnné lze distribuovat mezi více abstraktních procesorù. Koneèná
    distribuce a implementace pøístupu k promìnným je ponechána na
    kompilátoru.
-   Operace nad èástmi distribuovaných polí mohou být vykonávány
    souèasnì rùznými procesory.
-   Synchronizace procesorù je zabezpeèena pro programátora
    transparentním zpùsobem a plnì ponechána na kompilátoru.
-   Mapování abstraktních procesorù na fyzické je poèítaèovì závislé a
    není prostøedky modelu øe¹eno.

Návrh HPF je proveden jako roz¹íøení k jazyku Fortran 90. Pøi návrhu
syntaktických pravidel pro roz¹iøující specifikace a pøíkazy bylo
postupováno tak, aby byla co nejménì dotèena mo¾nost kompilace programu
obvyklým kompilátorem jazyka Fortran 90. Nìkterá roz¹íøení HPF byla
zahrnuta do standardu Fortran 95.

### [2.3.5.2 Distribuce dat]{#SECTION00435200000000000000}

Hlavní pøedstavu programového modelu HPF lze popsat ve dvou krocích.
Pøed paralelním zpracováním velkého mno¾ství dat jsou tato data nejdøíve
rozdìlena na disjunktní èásti a následnì je pro obvyklé sériovì
zpracování ka¾dé èásti urèen nìkterý z dostupných procesorù. Jednotlivé
procesory pøistupují ke svìøené èásti dat lokálnì, pokud potøebují jiná
data ne¾ lokální, musí si je vy¾ádat komunikací. Mechanismus dvojího
pøístupu k datùm je v¹ak pro programátora úplnì transparentní a plnì
ponechán na kompilátoru. Pøi nevhodném umístìní dat v¹ak mù¾e èasovì
nároèná meziprocesorová komunikace a synchronizace zmen¹it nebo zcela
znehodnotit úspory paralelním zpracováním. Proto má programátor
k dispozici prostøedky pro vyjádøení vhodné lokality dat. Pøi znalosti
detailù øe¹eného problému, lze navrhnout kompilátoru vhodné rozdìlení
dat s ohledem na co nejvìt¹í omezení komunikace. Zpùsoby distribuce
podporované HPF jsou tyto:

-   []{#4174}*Bloková distribuce dat*: Toto rozdìlení pøidìluje ka¾dému
    procesoru stejnì velkou, souvislou èást pole.
-   []{#4176}*Cyklická distribuce dat*: Pøi tomto zpùsobu jsou prvky
    pole pøidìlovaný po jednom na cyklicky uspoøádanou mno¾inu
    procesorù.

Je tøeba doplnit, ¾e urèení distribuce dat programátorem není pro
kompilátor závazné, je pouze návodem k jeho práci. Implicitní distribuce
jednoduchých promìnných a polí, která nebyla distribuována explicitnì,
není standardem HPF stanovena.

### [2.3.5.3 Paralelní konstrukce HPF]{#SECTION00435300000000000000}

HPF obsahuje jazykové konstrukce pro jednoduché vyjádøení operací, které
mohou být v pøípadì dostupnosti prostøedkù provádìny paralelnì. Pro
dosa¾ení co nejvìt¹í pøenositelnosti byly pøedev¹ím vyu¾ity velmi dobré
mo¾nosti, které pro tento pøípad nabízí ji¾ Fortran 90. Jedná se
o následující konstrukce:

-   Maticové operace: Podobnì jako tøeba
    v Matlabu[^26^](http://home.zcu.cz/~mlazar/dpma/dpma-node13.html#foot3635){#tex2html45},
    lze provádìt nìkteré jednodu¹¹í operace nad v¹emi prvky matice.
-   Pøíkaz `FORALL`: Tento pøíkaz pøedstavuje zobecnìný pøiøazovací
    pøíkaz pro podmno¾iny matic bez pøedem stanoveného poøadí pro
    zpracování jednotlivých prvkù.
-   Direktiva `INDEPENDENT`: Pomocí této direktivy pøedává programátor
    kompilátoru dodateèné informace o mo¾nostech paralelizace
    následujícího pøíkazu.
-   Atribut `PURE`: Oznaèuje funkci bezpeènì pou¾itelnou uvnitø pøíkazu
    `FORALL`. `PURE` funkce je funkce, která nevykazuje ¾ádné vedlej¹í
    efekty.

### [2.3.5.4 Mapování dat]{#SECTION00435400000000000000}

HPF zaji¹»uje prostøedky pro mapovaní dat, jejich¾ pou¾itím lze
navrhnout vhodné umístìní dat. Nejprve se formulují po¾adavky na
vzájemnou polohu dat. V ideálním pøípadì by mìla být související data
umístìna na stejných procesorech. Potom se umístí základní datové
struktury na mno¾inu abstraktních procesorù. Poèítaèovì závislou etapu
mapování abstraktních procesorù na fyzické ji¾ datový model HPF
nezahrnuje a k jejímu provedení lze pou¾ít specifické prostøedky cílové
poèítaèové architektury. HPF pou¾ívá pro mapování dat následující
direktivy:

-   `PROCESSORS` Umo¾òuje vytvoøit a pojmenovat pole abstraktních
    procesorù. Na toto pole lze následnì mapovat datové struktury.
-   `ALIGN` Direktiva umo¾òuje namapovat prvky matice na procesory tzv.
    pøidru¾ením, kdy je procesor pro ka¾dý prvek urèen nepøímo
    procesorem prvku referenèní matice.
-   `TEMPLATE` Direktiva oznaèuje abstraktní indexový prostor, jeho¾
    ¾ivotnost je omezena na dobu kompilace a kterému neodpovídá ¾ádné
    pamì»ové místo.
-   `REDISTRIBUTE` a `REALIGN` Umo¾òují dynamické pøemapování
    promìnných.

### [2.3.5.5 Vnitøní funkce]{#SECTION00435500000000000000}

Jeden z hlavních rozdílù mezi jazyky typu Fortran a ostatními jazyky
spoèívá v implementaci bì¾ných matematických, systémových a I/O funkcí.
Napø. jazyk C odsouvá øe¹ení tìchto otázek na úroveò knihovních funkcí.
Tím je dosa¾eno znaèného zjednodu¹ení jazyka. Na proti tomu jazyk
Fortran tyto funkce poskytuje ji¾ na úrovni kompilátoru a díky tomu je
umo¾nìna optimalizace generovaného kódu.

Vnitøní funkce HPF mù¾eme rozdìlit na tyto skupiny:

-   Vnitøní funkce jazyka Fortran 90: Zahrnují obvyklé numerické a
    konverzní funkce, paralelní implementace transformaèních funkcí
    optimalizovaných pro danou architekturu, dotazovací funkce na
    vlastnosti datových objektù a dal¹í vnitøní funkce Fortranu 90.
-   Dotazovací funkce HPF: Funkce vracející poèet procesorù buï celkovì,
    nebo pouze v uvedené dimenzi.
-   Vnitøní funkce HPF z knihovny []{#4180}*HPF_LIBRARY*: Zahrnuje
    funkce pro manipulaci s bity, redukèní funkce pro pole, dotazovací
    mapovací funkce, funkce pro kombinaci a rozmístìní prvkù polí,
    funkce pro prefixové a sufixové operace s poli a funkce pro øazení
    polí.

### [2.3.5.6 HPF verze 2.0]{#SECTION00435600000000000000}

Ve výkladu jsme se omezili na první verzi jazyka HPF 1.0. V následujícím
pøehledu budou struènì uvedeny nejdùle¾itìj¹í rysy HPF verze 2.0:

-   redukèní operace uvnitø smyèky,
-   neregulární mapování,
-   paralelizmus podle úloh,
-   asynchronní I/O operace.

## [2.3.6 Dal¹í prostøedky pro programování tìsnì vázaných systémù]{#SECTION00436000000000000000}

Podobnì jako u volnì vázaných systémù existuje i pro tìsnì vázané
systémy mnoho dal¹ích prostøedkù pro paralelizaci programu. Obvykle se
jedná o øe¹ení z dob, kdy je¹tì neexistovaly vhodné standardy, nebo
teprve vznikaly. Av¹ak i v dne¹ní dobì vznikají stále pokusy o vytvoøení
nových, lep¹ích øe¹ení. Nejèastìji se jedná o roz¹íøení standardního
jazyka C, C++, nebo Fortran. Jmenujme napøíklad pC++, Compositional C+,
HPC++, Fortran M (FM), CM Fortran, LWG Fortran, Fortran 90D a dal¹í.

Je tøeba se také zmínit o systémech pro automatickou paralelizaci. Kromì
ji¾ zmínìného preprocesoru KAP existují i dal¹í systémy provádìjící
automatikou paralelizaci. Oblíbené jsou napø. pøekladaèe jazyka C, C++,
Fortran 77, Fortran 90 a HPF od firmy Portland Group Inc. (PGI).

\

------------------------------------------------------------------------

#### Footnotes

[\... v Matlabu]{#foot3635}[^26^](http://home.zcu.cz/~mlazar/dpma/dpma-node13.html#tex2html45){#foot3635}
:   []{#4178}*MATLAB* *(MATrix LABoratory)* je interaktivní systém pro
    vìdecké a technické výpoèty zalo¾ený na maticovém kalkulu.

------------------------------------------------------------------------

[![\[ Title \]](vlakna2_soubory/title.gif){height="26" width="29"
align="bottom" border="0"}](http://home.zcu.cz/~mlazar/dpma/dpma.html)
  [![\[ « \]](vlakna2_soubory/prev.gif){height="26" width="29"
align="bottom"
border="0"}](http://home.zcu.cz/~mlazar/dpma/dpma-node12.html)   [![\[ »
\]](vlakna2_soubory/next.gif){height="26" width="29" align="bottom"
border="0"}](http://home.zcu.cz/~mlazar/dpma/dpma-node14.html)   [![\[
Index \]](vlakna2_soubory/index.gif){height="26" width="29"
align="bottom"
border="0"}](http://home.zcu.cz/~mlazar/dpma/dpma-node42.html)   [![\[
Download \]](vlakna2_soubory/download.gif){height="26" width="29"
align="bottom"
border="0"}](http://home.zcu.cz/~mlazar/dpma/download/index.php)

Autor: **Martin Lazar**
