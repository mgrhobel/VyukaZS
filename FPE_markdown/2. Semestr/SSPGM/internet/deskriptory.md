---
title: "deskriptory.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/internet/deskriptory.pdf"
date: 2009-05-02
type: PDF (text-based)
---

Vilém Vychodil

Operačnı́ systém Linux
Přı́ručka českého uživatele

Computer Press, Brno, 2003.
Ukázková kapitola zveřejněna se souhlasem vydavatele.

ix

Obsah
Úvod

xi

1. Základnı́ pojmy, historie systémů
1.1. Operačnı́ systém . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
1.2. Historie systému Unix . . . . . . . . . . . . . . . . . . . . . . . . . . . .
1.3. Základnı́ rysy Unixu . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
1.4. Vývoj systému Linux . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
1.5. Linux a softwarové distribuce . . . . . . . . . . . . . . . . . . . . . . . .

1
1
3
5
8
9

2. Základy práce v systému
2.1. Vstup uživatele do systému . . . . . . . . . . . . . . . . . . . . . . . . .
2.2. Prvnı́ kroky v systému . . . . . . . . . . . . . . . . . . . . . . . . . . . .
2.3. Základnı́ přı́kazy a obslužné programy . . . . . . . . . . . . . . . . . .
2.4. Systémová dokumentace . . . . . . . . . . . . . . . . . . . . . . . . . . .

13
13
16
18
21

3. Souborový systém
3.1. Architektura souborového systému v Unixu . . . . . . . . . . . . . . .
3.2. Obyčejné soubory a adresáře . . . . . . . . . . . . . . . . . . . . . . . .
3.3. Speciálnı́ adresáře a relativnı́ cesta . . . . . . . . . . . . . . . . . . . . .
3.4. Speciálnı́ soubory . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
3.5. Odkazy . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
3.6. Tradičnı́ přı́stupová práva . . . . . . . . . . . . . . . . . . . . . . . . . .
3.7. Řı́zenı́ přı́stupu pomocı́ ACL . . . . . . . . . . . . . . . . . . . . . . . .
3.8. Sdı́lenı́ diskového prostoru . . . . . . . . . . . . . . . . . . . . . . . . .
3.9. Základnı́ adresářová struktura systému . . . . . . . . . . . . . . . . . .

25
27
28
31
41
45
47
56
61
62

4. Systém procesů
4.1. Vznik procesů a jejich organizace . . . . . . . . . . . . . . . . . . . . . .
4.2. Ze života procesu . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
4.3. Ukončenı́ života procesu . . . . . . . . . . . . . . . . . . . . . . . . . . .
4.4. Plánované spouštěnı́ procesů . . . . . . . . . . . . . . . . . . . . . . . .

67
68
69
76
81

5. Základy přı́kazového interpretu
85
5.1. Vykonávánı́ přı́kazů . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 86
5.2. Přesměrovánı́ a roury . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 92
5.3. Expanze jmen souborů . . . . . . . . . . . . . . . . . . . . . . . . . . . . 99
5.4. Proměnné . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 105
5.5. Řı́dı́cı́ struktury a zabudovaná aritmetika . . . . . . . . . . . . . . . . . 113
5.6. Vytvářenı́ skriptů . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 121
5.7. Počátečnı́ nastavenı́ shellu . . . . . . . . . . . . . . . . . . . . . . . . . . 128

x
6. Zpracovánı́ textu
131
6.1. Základnı́ nástroje . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 133
6.2. Filtry a proudové editory . . . . . . . . . . . . . . . . . . . . . . . . . . . 140
6.3. Celoobrazovkový editor vi . . . . . . . . . . . . . . . . . . . . . . . . . . 150
6.4. Celoobrazovkový editor GNU Emacs . . . . . . . . . . . . . . . . . . . 156
6.5. Podpora národnı́ho prostředı́ . . . . . . . . . . . . . . . . . . . . . . . . 167
6.6. Archivace a komprese dat . . . . . . . . . . . . . . . . . . . . . . . . . . 172
7. Sı́t’ové prostředı́
177
7.1. Protokoly TCP/IP . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 178
7.2. Základnı́ sı́t’ové služby . . . . . . . . . . . . . . . . . . . . . . . . . . . . 187
7.3. Sdı́lenı́ uživatelských účtů a vzdálené souborové systémy . . . . . . . . 193
7.4. Elektronická pošta a Network News . . . . . . . . . . . . . . . . . . . . 196
7.5. Služby vzdáleného přihlášenı́ a přenosu dat . . . . . . . . . . . . . . . . 207
7.6. Komunikačnı́ a informačnı́ služby . . . . . . . . . . . . . . . . . . . . . 215
8. Grafické sı́t’ové rozhranı́
221
8.1. Architektura X . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 222
8.2. Spuštěnı́ X serveru a lokálnı́ přihlášenı́ . . . . . . . . . . . . . . . . . . . 225
8.3. Práce se vzdálenými klienty . . . . . . . . . . . . . . . . . . . . . . . . . 230
8.4. Atributy X klientů . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 234
8.5. Standardnı́ X klienti . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 242
Literatura

247

Rejstřı́k souborů

249

Rejstřı́k pojmů

251

xi

Úvod
Operačnı́ systém GNU/Linux je v současnosti velmi populárnı́, soudě nejen podle
počtu různých polemik, které se každým dnem objevujı́ v rozličných diskusnı́ch
klubech i na stránkách elektronických časopisů. I skalnı́ pesimisté musı́ v současnosti
připustit, že si GNU/Linux ve světě operačnı́ch systémů vydobyl své pevné mı́sto.
S GNU/Linuxem se lze setkat od kapesnı́ch počı́tačů, přes pracovnı́ stanice a servery,
až k počı́tačům třı́dy mainframe. Pro GNU/Linux a konec konců i pro ostatnı́ volně
šiřitelné operačnı́ systémy existuje nesčı́slně aplikacı́ pokrývajı́cı́ch v současnosti
snad všechny nejdůležitějšı́ oblasti nasazenı́ výpočetnı́ techniky. Zdá se, že ve světě
operačnı́ho systému GNU/Linux nás čeká velmi slibná budoucnost.
Co s sebou nese tato popularita? Předevšı́m stále většı́ přı́liv nových a nadšených uživatelů z řad odbornı́ků, profesionálů, ale i laické veřejnosti. Bohužel, řadu uživatelů
po chvı́li počátečnı́ nadšenı́ přejde a operačnı́ systém GNU/Linux přestanou úplně
použı́vat. Někteřı́ nanejvýš zklamanı́ uživatelé dokonce začı́najı́ proti GNU/Linuxu
intenzivně zbrojit. Důvod ztráty zájmu o systém je téměř ve všech přı́padech stejný –
– absolutnı́ nepochopenı́ filosofie systému, jeho základnı́ch principů a uživatelských
návyků. Zvládnutı́ práce se systémem GNU/Linux na uživatelské úrovni nenı́ v žádném přı́padě triviálnı́ a vyžaduje jistou časovou investici a uživatelskou sebekázeň.
Řada začátečnı́ků ale s tı́mto faktem nenı́ seznámena a při pokusu o bližšı́ seznámenı́
s operačnı́m systémem jsou zklamáni leckdy jen proto, že nevědı́, kde začı́t.
Nebezpečı́m pro začı́najı́cı́ uživatele mohou být paradoxně rozvinutá grafická prostředı́ KDE a GNOME, která uživatelům umožňujı́ pracovat v systému pouze „s myšı́
v ruce“. Orientacı́ výhradně na grafické prostředı́ nelze obecně nic zkazit. Na druhou stranu, uživatel pracujı́cı́ pouze s intuitivnı́m grafickým prostředı́m využı́vá jen
zlomek potenciálu celého systému, jeho styl práce se stává mnohdy neefektivnı́m
a operačnı́ systém GNU/Linux je tak degradován pouze na grafické rozhranı́ pro několik oblı́bených aplikacı́. A to je bez pochyby škoda. Aktivnı́ uživatel GNU/Linuxu
musı́ umět řešit i problémy, které jsou za hranicı́ práce s intuitivnı́m grafickým rozhranı́m.
Start nováčkům leckdy neulehčujı́ ani zkušenı́ uživatelé systému. Zdaleka ne každý
uživatel je totiž ochoten odpovı́dat na dotazy, které mu často připadajı́ naprosto
naivistické nebo jako z úplně jiného světa. Rozdı́l mezi zkušeným uživatelem a začátečnı́kem je obvykle naprosto propastný. Nezřı́dka se stává, že se mezi oběma typy
uživatelů nacházı́ komunikačnı́ vakuum – uživatelé spolu nejsou schopni nalézt společnou řeč. Co tedy doporučit začı́najı́cı́mu uživateli? Rozhodně nenı́ vhodné hned
zpočátku začı́t čı́st tisı́cistránkové referenčnı́ přı́ručky a objemná kompendia. Jejich
obsah je leckdy jen shrnutı́m dokumentace, kterou lze nalézt ve standardnı́ instalaci
GNU/Linuxu. Jako prvnı́ potřebuje uživatel nahlédnout do stylu práce a předevšı́m
si potřebuje osvojit běžné metody řešenı́ různých problémů. Jedině tak bude schopen dále rozvı́jet své schopnosti a naplno využı́vat vskutku mocný operačnı́ systém,
kterým GNU/Linux bezesporu je.

xii
Čtenářům předkládám průvodce problematikami práce s operačnı́m systémem
GNU/Linux. Text je orientován výlučně uživatelsky, nenı́ v něm napřı́klad rozebı́rána instalace nebo správa systému. Důvod je prostý – dobrý správce systému
musı́ být v prvnı́ řadě dobrým uživatelem. Správu systému GNU/Linux lze navı́c
jen velmi obtı́žně popsat, jelikož z velké části závisı́ na použité softwarové distribuci.
Při psanı́ textu jsem se snažil vyhnout jakýmkoli pevným vazbám na tu či onu distribuci, text by měl být přı́nosný i pro uživatele jiných operačnı́ch systémů založených
na filosofii Unixu, lze jej tedy považovat za obecnou učebnici práce v systému. Kniha
u čtenáře nepředpokládá téměř žádné znalosti, snad vyjma znalostı́ základnı́ho ovládánı́ počı́tače. V obsahu knihy jsem se snažil koncentrovat své zkušenosti s výukou
práce v systému GNU/Linux na univerzitě včetně výuky u neinformatických oborů.
Kniha by měla být přı́stupná široké čtenářské veřejnosti. Inspiraci a poučenı́ v nı́
mohou nalézt jak úplnı́ začátečnı́ci, tak i pokročilı́ uživatelé.
Pro koho je kniha určena? Jsou to předevšı́m, ale nikoli jen, začı́najı́cı́ uživatelé
GNU/Linuxu. Kniha je koncipována jako systematická učebnice probı́rajı́cı́ na sebe
navazujı́cı́ problematiky. Úvodnı́ kapitoly jsou psány co možná nejpřı́stupnějšı́m způsobem, v dalšı́m textu se obtı́žnost mı́rně stupňuje. Knihu jsem napsal jako protipól
k dosavadnı́ dostupné literatuře, která se mi pro začátečnı́ky nejevı́ přı́liš vhodná.
Při pronikánı́ do základů systému uživatel zdaleka nepotřebuje kompletnı́ popis
všech přepı́načů nějakého obslužného programu či přeložené manuálové stránky.
Stěžejnı́ je pochopenı́ stylu práce, který je potřeba demonstrovat přı́klady. Stejně tak
podstatné je zdůvodnit všechny aspekty práce včetně jejich motivace a historického
vývoje. Jedině tak bude uživatel s to pochopit, proč se dané činnosti provádějı́ právě
vyloženým způsobem, a ne jiným. Kniha se tedy nesnažı́ suplovat referenčnı́ přı́ručku, jednotlivé problémy jsou rozebı́rány do hloubky, jež se mi jevı́ dostačujı́cı́
pro solidnı́ práci v systému. Je samozřejmé, že zvı́davı́ čtenáři půjdou ve zkoumánı́
systému daleko za mnou vyznačené hranice.
Kniha je rozdělena do tematicky navazujı́cı́ch kapitol. Prvnı́ dvě kapitoly jsou seznamovacı́ – věnujı́ se elementárnı́m pojmům a úvodu do práce s operačnı́m systémem.
Některé pasáže obsažené v prvnı́ch dvou kapitolách jsou dále rozebrány v dalšı́ch
částech knihy. Všem čtenářům v každém přı́padě doporučuji přečı́st i tyto dvě úvodnı́
kapitoly, jsou užitečné minimálně z důvodu seznámenı́ se s použı́vaným značenı́m
a názvoslovı́m. Dalšı́ch šest kapitol se věnuje dı́lčı́m problematikám práce v systému.
Součástı́ každé kapitoly je jednak úvod do problematiky, jednak praktické přı́klady
použitı́ obslužných programů. Vřele doporučuji věnovat se oběma částem kapitol.
Přı́klady nemohou dát smysl bez pochopenı́ podstaty problémů, na druhou stranu samotné pochopenı́ problému je potřeba podpořit přı́klady. Pro čtenáře bude užitečné,
pokud si po přečtenı́ každé kapitoly všechny přı́klady znovu projdou a vyzkoušı́
na běžı́cı́m GNU/Linuxu. Sled kapitol a navazujı́cı́ problematiky tvořı́ dohromady
přirozený pojmotvorný proces a knihu lze mimo jiné bez problémů použı́t k přı́pravě základnı́ho kursu práce s operačnı́mi systémy vycházejı́cı́mi z filosofie Unixu
a dodržujı́cı́mi alespoň část normy POSIX.

xiii
Následujı́cı́ přehled obsahuje stručný obsah kapitol.
1. Základnı́ pojmy, historie systémů.
V úvodnı́ kapitole se snažı́m sjednotit se čtenářem řeč. Velký důraz je kladen na vysvětlenı́ základnı́ch pojmů, sem patřı́ zejména operačnı́ systém, jádro
systému, softwarová distribuce a jejich vzájemný vztah. Součástı́ kapitoly je
i jemný úvod do historie operačnı́ch systémů. Jeho účelem rozhodně nenı́ nudit
čtenáře nezajı́mavými historickými fakty. Při práci se systémem je ale dobré
vědět, že některé jeho projevy jsou podmı́něny historickým vývojem. Čtenář
se v úvodnı́ kapitole napřı́klad dozvı́, proč jsou operačnı́ systémy vzešlé z filosofie Unixu implicitně „tiché“.
2. Základy práce v systému.
Druhá kapitola obsahuje úvod do základů práce se systémem. Jedná se pouze
o nezbytné minimum, stěžejnı́ je přihlášenı́ do systému a základy práce s přı́kazovým interpretem. Přı́kazový interpret je rozebı́rán pouze na úrovni jeho
ovládánı́ a vkládánı́ přı́kazů. Podrobněji je přı́kazový interpret popsán v kapitole 5. V závěru kapitoly je čtenář seznámen s „uměnı́m hledat nápovědu“.
Při práci v systému je velmi důležité umět hledat dodatečnou dokumentaci,
pracovat s manuálovými stránkami a vědět, kam se obrátit v přı́padě nesnázı́.
3. Souborový systém.
Úkolem kapitoly o souborovém systému je nejprve seznámit uživatele s koncepcı́ souboru. Pojem soubor je v operačnı́m systému naprosto základnı́ a jedná
se v podstatě o jednotku organizace dat. V kapitole jsou rovněž soustředěny
informace o běžných typech souborů a hierarchické struktuře souborů. Vysvětleny jsou pojmy absolutnı́ a relativnı́ cesta, které jsou nezbytné pro dalšı́ práci
v systému. Samozřejmě nechybı́ ani informace o přı́stupových právech. Kromě
tradičnı́ch přı́stupových práv je čtenář informován také o POSIX ACL. Informace o POSIX ACL nebyly dosud v české literatuře dostupné. Závěr kapitoly
se věnuje připojovánı́ diskových oblastı́, diskové kvótě a náhledu na standardnı́
strukturu adresářů operačnı́ho systému GNU/Linux.
4. Systém procesů.
Na kapitolu o souborovém systému plynule navazuje kapitola o systému procesů. Proces hraje v operačnı́m systému úlohu jednotky vykonávánı́ – procesy
jsou nutné z hlediska modifikace dat. Struktura kapitoly kopı́ruje životnı́ cyklus procesu. Z uživatelského pohledu je důležité zvládnout správu vlastnı́ch
procesů, to jest napřı́klad pozastavit a znovu rozběhnout proces nebo spustit
proces na pozadı́. Část kapitoly je věnována komunikaci pomocı́ signálů, jelikož se jedná o základnı́ princip meziprocesové komunikace, který je navı́c
použitelný při každodennı́ práci. Závěr kapitoly je vyhrazen pro plánované
a periodické spouštěnı́ procesů.
5. Základy přı́kazového interpretu.
S přı́kazovým interpretem se lze setkat bezprostředně po přihlášenı́ do systému. I když uživatel pracuje převážně s grafickým rozhranı́m, stále potřebuje

xiv
mı́t alespoň základnı́ znalosti práce s přı́kazovým interpretem. V opačném přı́padě se ochuzuje o celou škálu efektivnı́ch pracovnı́ch postupů. V kapitole
o přı́kazovém interpretu jsou postupně rozebrány jeho běžné vnitřnı́ přı́kazy,
expanze neúplných jmen souborů a uživatelské proměnné. Pozornost je věnována i podmı́něným přı́kazům, substituci přı́kazů a vytvářenı́ skriptů. V závěru
kapitoly je uveden přehled nejpoužı́vanějšı́ch proměnných přı́kazového interpretu s krátkým popisem jejich významu.
6. Zpracovánı́ textu.
Práce s textovými soubory je v operačnı́m systému klı́čová. Veškeré konfiguračnı́ soubory, ale i většina datových souborů je v GNU/Linuxu v textovém
tvaru. V úvodu kapitoly je čtenářům objasněn samotný pojem „textový soubor“, dalšı́m diskutovaným pojmem je „textový editor“. K úpravě textových
dat lze použı́t v podstatě tři druhy nástrojů. V prvnı́ řadě jsou to jednoduché obslužné programy. Druhou kategorii tvořı́ proudové editory a filtry. Konečně pro
interaktivnı́ úpravu souborů lze použı́t celoobrazovkové textové editory. Každé
kategorii je v textu věnována patřičná pozornost. Při použitı́ filtrů a proudových
editorů hrajı́ důležitou roli regulárnı́ výrazy. I jim je tedy vyhrazena samostatná
sekce.
Závěr kapitoly je věnován problematikám přı́buzným zpracovánı́ textu. Jedná
se o lokalizaci systému a práci s dokumenty obsahujı́cı́mi diakritiku. Tato pasáž
je jako jedna z mála těsně vázána na operačnı́ systém GNU/Linux. Čtenář zde
nalezne základnı́ metody přizpůsobenı́ systému národnı́mu prostředı́, ale napřı́klad i informace o transformaci dokumentu mezi různými kódovými stránkami a přenosu dokumentu mezi nejčastěji použı́vanými operačnı́mi systémy.
Závěr kapitoly popisuje základy archivace a komprese dat.
7. Sı́t’ové prostředı́.
Kapitola o sı́t’ovém prostředı́ systému Unix se mı́rně vymyká ostatnı́m kapitolám. Uživatel zde nalezne základnı́ pojednánı́ o IP sı́tı́ch a komunikačnı́ch
protokolech rodiny TCP/IP. Součástı́ textu je i popis základnı́ch sı́t’ových služeb
včetně DNS, elektronické pošty, komunikačnı́ch služeb, služeb vzdáleného přihlášenı́ a přenosu dat. Jedna z podkapitol se věnuje sdı́lenı́ uživatelských účtů
a diskového prostoru prostřednictvı́m služeb NIS a NFS, diskutována je rovněž problematika práce v heterogennı́m sı́t’ovém prostředı́. Kapitolu o sı́t’ovém
prostředı́ je možné s vynechánı́m některých odstavců přečı́st hned po úvodnı́ch
dvou kapitolách. Pokud nemá uživatel vůbec žádné zkušenosti s pracı́ v rozlehlých počı́tačových sı́tı́ch, lze tento postup jen doporučit. Alespoň základnı́
znalosti o sı́t’ovém prostředı́ systému jsou potřeba i v přı́padě, kdy uživatel
použı́vá samostatný počı́tač bez připojenı́ k počı́tačové sı́ti.
8. Grafické sı́t’ové rozhranı́.
Kapitola o grafickém rozhranı́ je do textu zařazena pro úplnost. Čtenář v nı́ nenalezne dokumentaci ke konkrétnı́m správcům oken nebo k dı́lčı́m problémům
týkajı́cı́m se jejich ovládánı́ či nastavenı́. Kapitola je psána velmi obecně a je-

xv
jı́m úkolem je předevšı́m seznámit čtenáře s architekturou grafického sı́t’ového
rozhranı́ X Window System. Úvod kapitoly se zaměřuje na základnı́ pojmy
X klient, X server a X protokol. Většı́ pozornost je věnována možnostem spouštěnı́ vzdálených aplikacı́ a vzdálenému přihlašovánı́ vůbec. V závěru kapitoly
je čtenář seznámen s možnostmi upravovánı́ vzhledu a chovánı́ standardnı́ch
X klientů pomocı́ atributů zdrojů.
Kniha je kromě jiného vybavena velmi podrobným rejstřı́kem, v němž se většina
pojmů vyskytuje pod různými hesly. Tento způsob organizace rejstřı́ku je sice poněkud neúsporný, ale je volen zcela záměrně – usnadnı́ vám pozdějšı́ vyhledávánı́
v textu. Samotný text doplňuje 18 obrázků, 31 schémat, okolo 50 tabulek a přes
250 ukázkových přı́kladů. V celém textu je rozebráno 25 přı́kazů standardnı́ho přı́kazového interpretu, přes 175 obslužných programů a uvedeno je přes 60 významných systémových souborů a adresářů. Věřı́m, že časová investice, kterou jsem vložil
do práce na této knize, nebyla marná. Pokud se mi touto knihou podařı́ zvětšit množinu spokojených uživatelů GNU/Linuxu, můj záměr bude dosažen.
I přes veškerou péči, kterou jsem textu během vývoje věnoval, se v něm mohou
nacházet nepřesnosti. Chtěl bych tı́mto poprosit laskavé čtenáře, aby mi jakékoliv
nejasnosti zası́lali prostřednictvı́m elektronické pošty na adresu
vilem.vychodil@upol.cz.
Jedině tak budu moci na problematické pasáže reagovat a postupně vydávat errata. Jakékoliv konstruktivnı́ připomı́nky k textu jsou rovněž vı́tány. Dalšı́ informace o textu
naleznete na
http://vychodil.inf.upol.cz/errata/linux-pcu.html.
Na závěr bych chtěl poděkovat všem svým kolegům a přátelům, kteřı́ mě během
psanı́ textu zahrnovali podnětnými připomı́nkami. V prvnı́ řadě si mé dı́ky zasloužı́
Vladimı́r Michl a Roman Szturc, kteřı́ celý text velmi pečlivě přečetli. Speciálnı́ poděkovánı́ patřı́ Janu Outratovi, jenž měl odvahu čı́st tento text hned několikrát. Dalšı́
poděkovánı́ patřı́ Miroslavu Ježkovi za připomı́nky k mému literárnı́mu projevu.
V neposlednı́ řadě se o zkvalitněnı́ knihy zasloužil i Miroslav Kuře, dı́ky němuž byly
zpřesněny informace o historickém vývoji volně šiřitelných operačnı́ch systémů.
Osobně musı́m poděkovat také Ivanu Bı́brovi, který mi s laskavostı́ jemu vlastnı́
upravil náhled na akademické a komerčnı́ nasazenı́ GNU/Linuxu.
Knihu jsem vytvořil v operačnı́m systému Debian GNU/Linux pomocı́ textového
editoru GNU Emacs, typografického systému TEX a jazyka METAPOST.
V Olomouci, dne 30. března 2003

Autor

Co je shell? Shell je přı́kazový interpret, to ovšem samo o sobě nevysvětluje, jaký je úkol shellu. Shell sloužı́ k načı́tánı́ uživatelského
vstupu a komunikuje s počı́tačem mı́sto toho, aby s nı́m komunikoval přı́mo uživatel. Kdyby uživatelé museli komunikovat s počı́tačem
přı́mo, nastaly by jim krušné časy, protože počı́tače rozumějı́ pouze
sekvencı́m jedniček a nul. I když se ted’ záměrně dopouštı́me zjednodušenı́ (úplně jsme pominuli úlohu operačnı́ho systému), je myslı́m
patrné, že každý uživatel by měl být rád, že na světě existuje tak
báječná věc, jako je shell.
N. J. Buchanan, D. M. Gingrich: The Unix Shell Guide.

5

Základy přı́kazového interpretu
Již rané verze operačnı́ho systému Unix byly vybaveny přı́kazovým interpretem –
– shellem. Nejinak je tomu u volně šiřitelných operačnı́ch systémů vzešlých z filosofie
Unixu. Přı́kazový interpret však nenı́ součástı́ jádra systému, jedná se o samostatný
uživatelský program. Oddělenı́ přı́kazového interpretu od jádra operačnı́ho systému
je výhodné. Vývoj jádra systému může běžet nezávisle na vývoji přı́kazového interpretu a obráceně. Uživatelé se s přı́kazovým interpretem setkávajı́ bezprostředně
po svém přihlášenı́ do systému. Účet každého uživatele obsahuje informaci o přihlašovacı́m shellu. Přihlašovacı́ shell je spuštěn po uživatelově vstupu do systému,
opuštěnı́m shellu uživatel rovněž ukončuje i aktuálnı́ sezenı́.
Hlavnı́m úkolem shellu je zprostředkovat interakci mezi uživatelem a počı́tačem.
Shell ale nesloužı́ pouze k jednoduchému spuštěnı́ programů, je to kompletnı́ programovacı́ jazyk. Pomocı́ shellu můžeme snadno řešit problémy propojovánı́m obslužných programů. Soubory obsahujı́cı́ přı́kazy pro shell se nazývajı́ skripty. Ve skriptech
mohou uživatelé definovat „vlastnı́ přı́kazy“ odvozené z existujı́cı́ch a trvale je uložit
na disku. Uložené skripty mohou být podle potřeby vykonávány. Shell se výborně
hodı́ k automatizaci některých rutinnı́ch pracovnı́ch postupů.
Začı́najı́cı́ uživatelé někdy přesně nechápou, které typy problémů by měli řešit pomocı́ shellu. Při řešenı́ jakýchkoliv problémů pomocı́ počı́tače je vždy řešitel postaven
před zásadnı́ rozhodnutı́: „Jaký aparát zvolit pro řešenı́ problému?“ Použitý aparát
by měl být vždy adekvátnı́. To jest malé problémy by měly být řešeny způsobem,
který zaručı́ jejich snadné a rychlé řešenı́. Naopak pokud se jedná o velký problém vyžadujı́cı́ si většı́ časovou investici, uživatel by měl vždy předvı́dat a zvolit dostatečně
silný a komplexnı́ nástroj. Shell je velmi vhodný nástroj pro řešenı́ problémů malého
a střednı́ho rozsahu, které nevyžadujı́ přı́liš velkou interakci s uživatelem. Sem patřı́
napřı́klad automatická manipulace se soubory a jejich obsahem, práce s adresářovou strukturou, periodické zálohovánı́ dat a podobně. Na druhou stranu napřı́klad
databázovou aplikaci s grafickým rozhranı́m bychom v shellu naprogramovali jen
stěžı́.

86

Kapitola 5. Základy přı́kazového interpretu

Obsahem dalšı́ho textu je stručné seznámenı́ se základnı́mi vlastnostmi shellu
GNU Bash, což je volně šiřitelná a vylepšená verze Bourne shellu. Shell GNU Bash,
zkráceně bash, je zřejmě nejčastěji použı́vaným přı́kazovým interpretem ve volně
šiřitelných operačnı́ch systémech. V operačnı́m systému může být samozřejmě hned
několik přı́kazových interpretů. Mezi dalšı́ oblı́bené shelly patřı́ napřı́klad C Shell,
Korn Shell, Z Shell, TclSh a jiné.

5.1.

Vykonávánı́ přı́kazů

Přı́kazový interpret je program sloužı́cı́ k přehlednému a cı́lenému spouštěnı́ dalšı́ch programů. Některé obslužné programy bývajı́ samy označovány jako „přı́kazy“.
Ačkoliv je toto označenı́ velmi rozšı́řené, je nutné si uvědomit, že přı́kazem nenı́
samotný program. Přı́kaz shellu je sdělenı́, kterým je požadována nějaká činnost, asi
nejčastěji spuštěnı́ programu. Program je fyzická entita. Jedná se o spustitelný soubor
fyzicky umı́stěný na souborovém systému. V předchozı́m textu již byly některé přı́kazy shellu představeny. Jednalo se o přı́kazy cd, bg, fg, exit, logout a umask.
Jelikož jsou přı́kazy zabudovány přı́mo v shellu, budou fungovat v jakékoliv situaci – nejsou nijak vázány ke konkrétnı́mu souborovému systému a jeho obsahu. Na
druhou stranu napřı́klad program ls je fyzicky umı́stěn v adresáři /bin. Pokud
nebude v systému přı́tomen nebo pokud na něj nebude mı́t uživatel právo spouštěnı́,
nebude jej moci použı́vat.
Spuštěnı́ externı́ho programu je zvláštnı́m přı́kazem pro shell, kde prvnı́ vstupnı́
slovo označuje jméno programu. Dalšı́ slova jsou chápána jako argumenty a shell je
předává volanému programu. Principiálně nenı́ rozdı́l mezi spuštěnı́m obslužného programu nebo libovolného jiného programu. Spuštěnı́ již bylo částečně rozebráno v minulé kapitole. Poněkud odlišná situace je u spouštěnı́ skriptů, viz kapitolu 5.6. Každý
přı́kaz shellu musı́ být ukončen klávesou ENTER , až poté je přı́kaz přijat a zpracován
interpretem. Základnı́m přı́kazem shellu je přı́kaz spuštěnı́ externı́ho programu. Jeho
syntaxe je
/jméno . /argument1 . · · · /argumentn .
kde / jméno . je povinné a označuje jméno externı́ho programu. Argumenty jsou
nepovinné. Jméno a argumenty musı́ být odděleny vždy alespoň jednou mezerou,
jinak by je shell nebyl schopen rozlišit. Podle jména programu se hledá konkrétnı́
program, který bude spuštěn. Argumenty sloužı́ jako dodatečná informace. Dodatečnou
informacı́ lze ovlivnit chovánı́ programu.
Hledánı́ programu je podmı́něno prohledávacı́ cestou. Prohledávacı́ cesta je tvořena
uspořádaným seznamem absolutnı́ch či relativnı́ch cest k adresářům. Obdržı́-li shell přı́kaz
spuštěnı́ programu, postupně prohledává všechny cesty uvedené v tomto seznamu.
Pro každou z nich zkoušı́, zdali se v daném adresáři nenacházı́ soubor zadaného
jména. Je-li požadovaný soubor nalezen, shell jej spustı́ a předá volanému programu
argumenty. Toto chovánı́ shellu má několik důsledků. Adresáře, které jsou uvedeny
v prohledávacı́ cestě dřı́ve, majı́ vyššı́ prioritu. Nenajde-li shell ani v jednom přı́padě
spustitelný soubor, ohlásı́ chybu.

5.1.

Vykonávánı́ přı́kazů

87

Nastavenı́ prohledávacı́ cesty je plně v režii uživatele. Prohledávacı́ cestu lze
měnit pomocı́ proměnných shellu. Problematika je popsána v kapitole 5.4. V tuto
chvı́li je dobré zmı́nit se o několika začátečnických chybách. Předpokládejme, že
uživatel novakj má v pracovnı́m adresáři spustitelný program udelej. Při pokusu
o jeho spuštěnı́
$ udelej
bash: udelej: command not found

však obdržel chybové hlášenı́. Pokud uživatel rozebere situaci, je přı́čina chyby
jasná. Pracovnı́ adresář obecně nenı́ součástı́ prohledávacı́ cesty. To je veliký rozdı́l
napřı́klad proti MS–DOSu, který implicitně hledá spustitelné soubory i v pracovnı́m
adresáři. V Unixu si lze tuto vlastnost vynutit přidánı́m symbolu tečka „.“ do prohledávacı́ cesty. Tı́m uživatel přinutı́ shell hledat spustitelné soubory daného jména
i v aktuálnı́m adresáři. Jiným způsobem řešenı́ problému je uvedenı́ absolutnı́ cesty
nebo relativnı́ cesty začı́najı́cı́ znakem „.“ nebo „..“ mı́sto jména spuštěného souboru,
problematikou cest jsme se zabývali v kapitole 3.2. Uvažujme jednoduchý přı́klad.
$ /home/student/inf97/novakj/udelej
$ ./udelej

V obou přı́padech uživatel provedl jednoznačnou specifikaci souboru, proto se
nevyužı́vá prohledávacı́ cesta. Záměrné přidánı́ symbolu „.“ do prohledávacı́ cesty
nenı́ přı́liš časté a nelze jej přı́liš doporučit. Uživatel si rozšı́řenı́m prohledávacı́ cesty
o aktuálnı́ adresář může přichystat nemilá překvapenı́. Pro ukázku předpokládejme,
že uživatel novakj napı́še jednoduchý program v jazyku C, který pouze vypı́še
pozdrav na obrazovku. Uživatel uložı́ zdrojový kód programu do souboru test.c.
Poté, co je program úspěšně sestaven, je vytvořen spustitelný program test. Uživatel
se jej pokusı́ spustit.
$ test

Mı́sto očekávaného pozdravu ale neobdržı́ zhola nic. Ani chybové hlášenı́. To uživatele zmate natolik, že začne houževnatě opravovat program, který je „evidentně
špatný“. Pozornı́ čtenáři ale jistě vytušili, že chyba bude úplně jinde. Uživatel novakj
napsal svůj prvnı́ program dobře, pouze zapomněl, že má prohledávacı́ cestu na aktuálnı́ adresář uvedenu v seznamu jako poslednı́. Při pokusu otestovat svůj program
proto ve skutečnosti spouštěl program /usr/bin/test, který sloužı́ k testovánı́
typu souborů.
Opačný extrém je uvést aktuálnı́ adresář v prohledávacı́ cestě jako prvnı́. Tı́mto
tahem si může uživatel „překrýt“ některé důležité systémové programy a skripty
v systému mohou začı́t vykazovat „zvláštnı́ chovánı́ “. Obecně lze doporučit nenastavovat vůbec „.“ do prohledávacı́ cesty. Mnohem lepšı́ řešenı́ je vytvořit adresář
~/bin a shromažd’ovat v něm potřebné spustitelné programy. V dalšı́ch kapitolách
je popsáno, jak modifikovat údaje o prohledávacı́ cestě. Na závěr k této poznámce
uved’me užitečné programy, které mohou pomoci při hledánı́ souborů.

88

Kapitola 5. Základy přı́kazového interpretu

Hledánı́ souborů
Program which dokáže lokalizovat spustitelný program podle jeho jména a aktuálnı́ho nastavenı́ prohledávacı́ cesty. Jako argumenty jsou programu which předány
jména souborů. Program pro každý předaný argument uvede absolutnı́ cestu k přı́slušnému spustitelnému souboru. Pokud nenı́ cesta nalezena, výstup programu bude
prázdný. Viz přı́klad.
$ which ls man xeyes mitscheme
/bin/ls
/usr/bin/man
/usr/bin/X11/xeyes
/usr/local/bin/mitscheme

V předchozı́ ukázce byly jednotlivé spustitelné soubory umı́stěny v typických
systémových adresářı́ch. Kromě hledánı́ spustitelných souborů přı́stupných pomocı́
cesty lze hledat i zdrojové kódy a manuálové stránky. K tomu sloužı́ program
whereis. Jeho syntaxe je obdobná jako u programu which. Ke každému heslu
vypı́še whereis seznam spustitelných souborů, manuálových stránek a zdrojových
kódů, jsou-li k dispozici.
$ whereis print talk
print: /usr/bin/print /usr/man/man1/print.1.gz
talk: /usr/bin/talk /usr/man/man1/talk.1.gz

Unix disponuje velmi mocným programem find. Program find lze použı́t ke
hledánı́ souborů podle jejich jména, vlastnı́ka, typu a podobně. Z jednotlivých podmı́nek prohledávánı́ lze vzájemnou kombinacı́ vytvářet složitějšı́ podmı́nky. Program
find je zcela obecný prohledávacı́ nástroj pracujı́cı́ hrubou silou. Podle zadaných
podmı́nek prohledává specifikovanou adresářovou strukturu. Základnı́ syntaxe programu je jednoduchá. Programu find lze zadat seznam prohledávaných cest a prohledávacı́ podmı́nky. Seznam cest musı́ vždy předcházet definici podmı́nek, ale může být
i vynechán. V tom přı́padě prohledávánı́ začı́ná v pracovnı́m adresáři. Úplný popis
všech podmı́nek programu find je zbytečný, uživatel může kdykoliv nahlédnout
do jeho manuálových stránek. V následujı́cı́ tabulce jsou uvedeny pouze nejčastěji
použı́vané přepı́nače a argumenty vyskytujı́cı́ se v dalšı́ch částech textu.
argument

význam

-links /n .
-mtime / n.
-name / vzor.
-newer / soubor.
-type / typ.
-user/-group / jméno .

na soubor existuje právě n odkazů
obsah byl za uplynulých n dnı́ změněn
jméno souboru odpovı́dá zadanému vzoru
soubor je novějšı́ než / soubor.
soubor je daného typu
omezuje vlastnı́ka a vlastnickou skupinu

Asi nejčastěji použı́vaným argumentem je -name. Argument umožňuje vyhledávat soubory podle jejich neúplného jména. Problematika neúplných jmen souborů je

5.1.

Vykonávánı́ přı́kazů

89

podrobně rozebrána v kapitole 5.3. Při vytvářenı́ podmı́nek lze použı́t i několik přepı́načů nepotřebujı́cı́ch dodatečné hodnoty. Přepı́nač -not má význam negace následujı́cı́ podmı́nky. Při prohledávánı́ stromové struktury obsahujı́cı́ několik připojených
souborových systémů lze přepı́načem -mount zakázat zpracovánı́ dat v adresářı́ch
vyskytujı́cı́ch se na jiných reálných souborových systémech. Použitı́ programu find
demonstruje následujı́cı́ přı́klad.
$ find /var/log /tmp -not -user root -type d
/var/log/news
/var/log/exim
/tmp/ssh-MhDLE195

V přı́kladu byly hledány soubory v adresářı́ch /var/log a /tmp. Hledané soubory měly být adresáře a zároveň jejich vlastnı́kem neměl být superuživatel root.
V přı́kladu byl použit argument -type d. Typ d určuje adresářový soubor. Označenı́
obyčejného souboru je f, označenı́ symbolického odkazu je l a tak dále. Pro označenı́
dalšı́ch typů souborů viz manuálovou stránku. V předcházejı́cı́m přı́padě je výsledkem volánı́ programu zobrazenı́ seznamu třı́ adresářů splňujı́cı́ch obě dvě podmı́nky
současně. Pro úplnost dodejme, že program find umožňuje vytvářet i disjunktivnı́
vazby pomocı́ přepı́nače -or, rovněž je možné stanovit prioritu podmı́nek pomocı́
závorek.
Program find může s nalezenými soubory provádět různé akce. Implicitnı́ akcı́
je vypsánı́ cesty k nalezenému souboru. Je-li použit argument -exec, program find
může pro každý nalezený soubor vykonat zadaný přı́kaz. V přı́kazu je vždy řetězec
„{}“ nahrazen jménem aktuálnı́ho souboru. Přı́kaz uvedený za argumentem -exec
musı́ být ukončen sekvencı́1 „\;“. V následujı́cı́m přı́kladu jsou nalezené adresáře
mı́sto vypsánı́ na obrazovku přesunuty do adresáře ~/backup.
$ find /var/log -not -user root -type d -exec mv {} ~/backup \;

Použitı́ programu find nenı́ přı́liš vhodné při prohledávánı́ rozsáhlé struktury
adresářů. Hierarchická struktura souborů na většı́ch systémech obsahuje stovky tisı́c
souborů, jejı́ úplné prohledánı́ je časově náročné, navı́c dost zatěžuje počı́tač. Ke hledánı́ souborů lze využı́t i databázi všech souborů. Databáze se pravidelně každý den
znovu aktualizuje a indexuje. Jelikož je vnitřnı́ organizace databáze volena s ohledem
na vysokou efektivitu vyhledávánı́, při jejı́m použitı́ má uživatel takřka okamžitou
odezvu. K prohledávánı́ databáze sloužı́ program locate. Jeho syntaxe je opět stejná
jako v předchozı́ch přı́padech. Je však možné uvádět i neúplné názvy.
$ locate blah
/usr/lib/bitchx/help/5_Programming/blah
/usr/share/fvwm95/mini-icons/mini.blah.xpm
/usr/X11R6/include/X11/pixmaps/mini.blah.xpm

Při prohledávánı́ je potřeba vhodně volit frázi, která je programu locate předána. Je dost dobře možné, že napřı́klad řetězec „source“ se bude na běžı́cı́m serveru
1 Význam této sekvence je prozatı́m ponechán bez komentáře. V kapitole 5.3. se čtenář dozvı́, že jde
o speciálnı́ konstrukci potlačujı́cı́ význam metaznaku „;“.

90

Kapitola 5. Základy přı́kazového interpretu

vyskytovat v názvu i několika tisı́c souborů. Počet souborů obsahujı́cı́ch řetězec „src“
se může lehce vyšplhat přes sto tisı́c. Uživatel by měl při hledánı́ souboru vždy kalkulovat s velikostı́ běžı́cı́ho systému. V přı́padě použitı́ programu find by také mělo
být bráno v úvahu možné diskové vytı́ženı́ spojené s rekurzivnı́m prohledávánı́m
adresářové struktury.

Oddělovánı́ přı́kazů
V předchozı́m textu byl představen přı́kaz spuštěnı́ programu. Shell disponuje i dalšı́mi přı́kazy. Zadávánı́ přı́kazů shellu je podobné, každý přı́kaz je shellem vykonán
až po ukončenı́ vstupnı́ho řádku klávesou ENTER . Na jeden řádek je ale možné uvést
vı́c přı́kazů vedle sebe. K jejich vzájemnému oddělenı́ sloužı́ metaznak střednı́k „;“.
Přı́kazy oddělené střednı́kem jsou provedeny, jako by byly uvedeny na samostatných
řádcı́ch za sebou. Problematiku demonstruje přı́klad.
$ who am i; ls -F; uptime
phoenix!novakj pts/2
Jul 3 08:59 (titan.inf.upol.cz)
bin/ data/ etc/ mail/ nohup.out todo
9:59am up 20 days, 1:21, 3 users, load avg: 0.00, 0.00, 0.00

Za střednı́ky nenı́ nutné dělat mezery, je to ale vhodné kvůli přehlednosti. V ukázkovém přı́kladu byly spuštěny tři programy po sobě. Program ls byl spuštěn až po
ukončenı́ programu who. Stejně tak program uptime byl spuštěn až po ukončenı́ ls.
Metaznaky jsou speciálnı́ znaky interpretované shellem. V předchozı́m textu jsme se již
se dvěma metaznaky setkali – s metaznakem mezera a s metaznakem ampersand „&“.
Podstatné je uvědomit si, že metaznak se při přı́kazu spuštěnı́ programu nepředává
jako argument. Metaznaky sloužı́ v shellu ke specifikaci přı́kazů.
Metaznak „&“ má v shellu vyššı́ prioritu než metaznak „;“. To jest, jsou-li napřı́klad uvedeny přı́kazy oddělené střednı́kem a pokud jsou ukončeny znakem ampersand „&“, přı́kazy budou postupně provedeny a poslednı́ z nich bude spuštěn na
pozadı́. Viz přı́klad.
$ sleep 3; ls -F &
[1] 31691
bin/ data/ etc/ mail/
[1]+ Done

nohup.out
ls -F

todo

V tomto přı́padě nejprve došlo k třı́sekundové prodlevě dı́ky spuštěnı́ programu
sleep. Potom byl spuštěn na pozadı́ program ls, který bezprostředně po výpisu
skončil. Na poslednı́m řádku je jasně vidět, že na pozadı́ byl spuštěn pouze program ls. Za pozornost stojı́ i samotný program sleep. Je-li program spuštěn s daným počtem sekund, pozastavı́ svoji činnost pomocı́ alarmu. Alarm je aparát jádra
systému, který po zadaném časovém intervalu probudı́ proces signálem SIGALRM.
K nastavenı́ alarmu sloužı́ volánı́ jádra alarm(), pomocı́ volánı́ jádra pause() proces čeká na přı́chozı́ signál SIGALRM. Na prvnı́ pohled se program sleep může jevit
poněkud neužitečný, je ale nepostradatelný při psanı́ skriptů.

5.1.

Vykonávánı́ přı́kazů

91

Oba metaznaky, „&“ i „;“, sloužı́ jako oddělovače a použı́vajı́ se identickým způsobem – ukončujı́ přı́kaz. Kdykoliv uživatel vložı́ přı́kaz shellu a neukončı́ jej žádným
metaznakem, lze jej chápat jako „přı́kaz ukončený střednı́kem“, který nebyl pro přehlednost uveden. V předchozı́m přı́kladu byl pro oddělenı́ použit nejprve střednı́k,
až potom ampersand. Mohli bychom však použı́t i jiné kombinace, viz ukázku.
$ sleep 3 & ls -F &
[1] 1040
[2] 1041
bin/ data/ etc/ mail/
[2]+ Done
[1]+ Done

nohup.out todo
ls -F
sleep 3

Přı́klad je opět jasný, oba programy byly spuštěny na pozadı́. Z ukázky je rovněž
vidět, že program ls ukončil svou činnost jako prvnı́, i když byl spuštěn jako druhý.
Je to tı́m, že program ls proběhl takřka okamžitě a program sleep čekal celé tři
sekundy.

Agregace přı́kazů
Předchozı́ tvrzenı́ o prioritě metaznaků vede k nutnosti mı́t k dispozici aparát,
kterým lze seskupovat přı́kazy. Shell takovým aparátem disponuje, navı́c jsou k tomuto
účelu voleny dvojice metaznaků „(“, „)“ a „{“, „}“, což je velmi intuitivnı́. Přı́kazy
je možné seskupovat dvojı́m způsobem.
(/seznam přı́kazů.)
{ / seznam přı́kazů.;}
Oba tvary se kromě různých závorek odlišujı́ ve dvou zásadnı́ch věcech. Seznam
přı́kazů musı́ být v druhém přı́padě bezpodmı́nečně ukončen metaznakem střednı́k.
Rovněž musı́ být za otevı́racı́ závorkou „{“ vždy alespoň jedna mezera. Mezera před
ukončovacı́ závorkou „}“ již nutná nenı́. V obou přı́padech seskupenı́ přı́kazů vede
k vytvořenı́ „agregovaného přı́kazu“, který je dále možno chápat jako jeden atomický
přı́kaz.
Rozdı́l mezi oběma předchozı́mi notacemi nenı́ jen syntaktický. V prvnı́m přı́padě
jsou jednotlivé přı́kazy provedeny v podřı́zeném shellu. To znamená, že jakákoliv nastavenı́ shellu provedená mezi kulatými závorkami budou po dokončenı́ poslednı́ho
přı́kazu zapomenuta. V druhém přı́padě se přı́kazy vykonávajı́ v aktuálnı́m shellu,
to jest změny v chovánı́ shellu se projevı́ i dále. Rozdı́l v těchto dvou přı́stupech je
markantnı́ zejména, ale nikoli jen, při použitı́ proměnných shellu. Viz kapitolu 5.4.
Na závěr kapitoly bude uvedeno několik praktických přı́kladů kombinujı́cı́ch
seskupovánı́ a oddělovánı́ přı́kazů. Následujı́cı́ přı́klady jsou uvedeny bez svých
výstupů, o jejich tvaru si jistě čtenář udělá představu sám.
$ (date; who); ls
$ (date; who); ls &
$ (date; who)& ls
$ (date; who)& ls &

92

Kapitola 5. Základy přı́kazového interpretu

U prvnı́ch dvou přı́kladů nebylo uvedenı́ závorek nutné. Ve třetı́m přı́kladu byl
nejprve spuštěn prvnı́ proces na pozadı́ a poté byl spuštěn program ls. Procesem
spouštěným na pozadı́ byl podřı́zený shell, který vykonal posloupnost dvou přı́kazů.
Čtvrtý přı́pad je analogický s tı́m rozdı́lem, že i program ls byl spuštěn na pozadı́.
Zajı́mavá situace může vzniknout napřı́klad při vloženı́ následujı́cı́ho přı́kazu.
$ (date & who); ls -F
novakj
pts/0
Jul 3 08:20 (titan.inf.upol.cz)
Tue Jul 3 12:02:38 CEST 2001
pes
pts/1
Jul 3 08:49 (linux.mfservis.cz)
windsort pts/2
Jul 3 11:36 (158.194.92.111)
bin/ data/ etc/ mail/ nohup.out todo

V předcházejı́cı́ ukázce se „slily výstupy“ dvou programů, date a who. Program
date byl spuštěn na pozadı́, program who na popředı́. Oba programy majı́ informativnı́ charakter, vypisujı́ údaje „na obrazovku“, a jelikož pracujı́ souběžně, může dojı́t
k proloženı́ jejich výstupu. Této patologické situaci lze předejı́t vhodným přesměrovánı́m výstupu. Problematikou se zabývá následujı́cı́ kapitola.

5.2.

Přesměrovánı́ a roury

Téměř všechny obslužné programy jsou v systému Unix koncipovány jako filtry.
Programy při práci přetvářejı́ vstupnı́ data na výstup. Vstupnı́ data jsou obvykle zadávána pomocı́ terminálu, výstup je obvykle tisknut na obrazovku. V Unixu existujı́
ustálená označenı́ pro standardnı́ vstup – klávesnici terminálu, standardnı́ výstup –
– obrazovku terminálu a standardnı́ chybový výstup. Standardnı́ výstup a standardnı́
chybový výstup jsou zobrazovány na stejném fyzickém zařı́zenı́ – obrazovce terminálu. Jedná se však o logicky odlišné výstupy. Standardnı́ výstup obsahuje výstupnı́
data vytvořená programem, chybový výstup je určen pro informaci o chybách během
zpracovávánı́ vstupnı́ch dat.
Aby si čtenář mohl o jednotlivých pojmech udělat přesnějšı́ představu, musı́me se
vrátit opět k pojmu proces. Jádro systému pro každý proces udržuje tabulku deskriptorů, jedná se o tabulku identifikátorů otevřených souborů. Při volánı́ jádra fork()
dědı́ synovský proces tabulku deskriptorů po svém rodiči. To napřı́klad umožňuje
meziprocesovou komunikaci mezi rodičovským a synovským procesem pomocı́ otevřených souborů. Prvnı́ tři záznamy v tabulce deskriptorů jsou vyhrazeny pro komunikaci s terminálem. Prvnı́ záznam je standardnı́ vstup, druhý standardnı́ výstup, třetı́ je
standardnı́ chybový výstup. Záznamy v tabulce deskriptorů jsou čı́slovány vzestupně
od 0, trojici standardnı́ch záznamů odpovı́dajı́ čı́sla 0, 1 a 2. Čı́selné označenı́ vstupu
a výstupů je použı́váno i v dalšı́m textu.
Deskriptory pro práci se soubory jsou důležité zejména pro přı́kazový interpret.
Shell při spouštěnı́ programů umožňuje přesměrovat vstup a výstupy do jiných otevřených souborů. Tı́mto způsobem lze velmi jednoduše řešit situace podobné těm
z předchozı́ úlohy – slitı́ vı́ce výstupů. V různých přı́padech je vhodné některý z výstupů potlačit. Napřı́klad při vyhledávánı́ souborů nenı́ nutné vypisovat chybová

5.2.

Přesměrovánı́ a roury

93

hlášenı́ způsobená neadekvátnı́mi právy. Potlačenı́ chybového výstupu lze dosáhnout jeho přesměrovánı́m do speciálnı́ho souboru /dev/null. V takové situaci shell
nejprve vytvořı́ nový proces, změnı́ deskriptor čı́slo 2 tak, aby ukazoval na otevřený
soubor /dev/null, a překryje svůj obraz novým programem. Na následujı́cı́m obrázku je zachyceno výsledné přesměrovánı́.
tabulka
deskriptorů
proces

0 stdin
1 stdout
/dev/null
2

..
.

Přesměrovánı́ vstupu a výstupu
Pro přesměrovánı́ vstupu a výstupů lze použı́t metaznaky „<“, „<<“ a „>“, „>>“.
Tyto metaznaky se uvádějı́ vesměs na konci přı́kazu, i když je možné vložit je mezi
argumenty nebo na začátek přı́kazu. Metaznaky musı́ být použity spolu s definicı́
vstupnı́ch přı́padně výstupnı́ch souborů. Význam metaznaku „<<“ bude rozebrán
až v kapitole 5.6. Metaznak „<“ sloužı́ k přesměrovánı́ vstupu, na své pravé straně
očekává cestu ke vstupnı́mu souboru. Metaznaky „>“ a „>>“ sloužı́ k přesměrovánı́
výstupů. Oba metaznaky musı́ mı́t na pravé straně definován výstupnı́ soubor. Na
levé straně může být uveden dalšı́ metaznak určujı́cı́ typ výstupu. Možné varianty
zápisu přesměrovánı́ jsou uvedeny v následujı́cı́ tabulce.
notace

význam

</ soubor.
>/ soubor.
2>/soubor.
&>/soubor.
>>/soubor.
2>>/ soubor.

standardnı́ vstup je přesměrován ze souboru
standardnı́ výstup je přesměrován do souboru
standardnı́ chybový výstup je přesměrován do souboru
oba standardnı́ výstupy jsou přesměrovány do souboru
standardnı́ výstup je připojen na konec souboru
standardnı́ chybový výstup je připojen na konec souboru

Soubor může být charakterizován jednak cestou, jednak čı́slem deskriptoru. Pokud je
potřeba zadat soubor pomocı́ deskriptoru otevřeného souboru, je možné použı́t označenı́ ve tvaru &/čı́slo., kde /čı́slo. označuje konkrétnı́ deskriptor. Potlačenı́ výstupu
programu demonstruje následujı́cı́ přı́klad.
$ find /etc/ssl -type f
/etc/ssl/openssl.cnf
find: /etc/ssl/private: Permission denied
$ find /etc/ssl -type f >/dev/null
find: /etc/ssl/private: Permission denied
$ find /etc/ssl -type f 2>/dev/null
/etc/ssl/openssl.cnf

94

Kapitola 5. Základy přı́kazového interpretu

V ukázce je použit program find, pomocı́ nějž uživatel hledá obyčejné soubory
v adresáři /etc/ssl. V druhém přı́padě byl potlačen výstup programu, v třetı́m
přı́padě chybový výstup. V předchozı́ tabulce chybı́ možnost „připojit oba výstupy
na konec souboru“. Shell takové připojenı́ přı́mo neumožňuje, nezbývá tedy nic
jiného, než nejprve přesměrovat standardnı́ chybový výstup na standardnı́ výstup, ten
dále připojit na konec souboru pomocı́ metaznaku „>>“. Pokud by uživatel chtěl
připojit oba výstupy na konec souboru, musel by uvést přı́kaz ve tvaru
$ cat soubor
In the Beginning Was the Word.
$ find /etc/ssl -type f >>soubor 2>&1; cat soubor
In the Beginning Was the Word.
/etc/ssl/openssl.cnf
find: /etc/ssl/private: Permission denied

Přesměrovánı́ lze využı́t i k primitivnı́m manipulacı́m se soubory. Program cat
provádı́ zřetězenı́ souborů, které jsou mu předány jako argumenty. Nenı́-li uveden
ani jeden soubor nebo v přı́padě, že jednı́m z argumentů je znak2 pomlčka „-“,
program cat čte data ze standardnı́ho vstupu. Tak se chová drtivá většina obslužných
programů v Unixu. Pokud přesměrujeme výstup programu cat do jiného souboru,
zı́skáme nástroj na primitivnı́ editaci a manipulaci se soubory.
$ cat >novy
vytvarim obsah prvniho souboru
CTRL-D

$ cat <novy >kopie
$ cat kopie
vytvarim obsah prvniho souboru

Uživatel nejprve vytvořil nový soubor spuštěnı́m programu cat a přesměrovánı́m jeho výstupu do souboru požadovaného jména. Po ukončenı́ vstupu stiskl
klávesu C-d, kterou uzavřel vstupnı́ soubor. Dı́ky přesměrovanému výstupu se data
uložila na disk. Druhým přı́kazem uživatel provedl kopii dat. Tentokrát musel přesměrovat vstup i výstup, činnost programu cat jinak zůstává stejná. Pokud se uživatel rozhodne připojit na konec souboru dalšı́ informaci, může tak učinit pomocı́
metaznaku „>>“.
$ cat >>kopie
pripojim na konec
CTRL-D

$ cat kopie
vytvarim obsah prvniho souboru
pripojim na konec

Vloženı́ dat na začátek nebo na jinou pozici v programu je rovněž možné, ale
vyžaduje již spolupráci několika programů, napřı́klad head a tail. Za prvé je nutné
2 V tomto přı́padě se jedná skutečně o znak, nikoliv o metaznak. Význam pomlčky je interpretován až
samotným obslužným programem cat.

5.2.

Přesměrovánı́ a roury

95

upozornit na fakt, že nenı́ možné zároveň přesměrovat vstup i výstup z/do identického souboru. Textový soubor může být při přesměrovánı́ otevřen bud’to pro čtenı́,
nebo pro zápis. Nikdy ne současně pro obě operace. Napřı́klad spuštěnı́ programu
$ cat kopie dalsi >kopie

povede jedině ke ztrátě dat ze souboru kopie, nikoliv k připojenı́ souboru dalsi
na jeho konec, jak by se na prvnı́ pohled mohlo zdát. Obdobná situace je napřı́klad
u vkládánı́ dat na začátek souboru. Řešenı́ demonstruje následujı́cı́ přı́klad.
$ cat <kopie >nova; cat - nova >kopie; rm nova
a jeste neco na zacatek
CTRL-D

$ cat kopie
a jeste neco na zacatek
vytvarim obsah prvniho souboru
pripojim na konec

Nynı́ jsme si k řešenı́ pomohli uvedenı́m pomlčky. Nejprve byla provedena záložnı́ kopie souboru. Bezprostředně poté byl zřetězen vstup s kopiı́ sebe sama a vše
bylo zapsáno do původnı́ho souboru. Pomocı́ metaznaku „>“ lze vytvořit i prázdný
soubor nebo vymazat obsah existujı́cı́ho souboru. Stačı́ jednoduše použı́t metaznak
„>“ v prázdném přı́kazu.
$ >novy-soubor.txt

Na závěr úvah o přesměrovánı́ uved’me přı́klad z předchozı́ kapitoly řešı́cı́ problém slitı́ výstupů. Jak již bylo naznačeno, u souběžně vykonávaných procesů může
dojı́t ke slitı́ jejich výstupů. Tomuto patologickému jevu lze zabránit vhodným přesměrovánı́m výstupu jednoho nebo vı́ce procesů.
$ (who & date &>soubor.txt); cat soubor.txt; ls; rm soubor.txt

Druhý uvedený metaznak ampersand nemá samozřejmě význam „spuštěnı́ procesu na pozadı́ “, jelikož je následován metaznakem pro přesměrovánı́. Hlavnı́ myšlenkou předchozı́ho přı́kazu je vypsat obsah souboru až poté, co nehrozı́ jeho slitı́
s jiným výstupem. Přesměrovánı́ výstupu procesu spuštěného na pozadı́ lze obecně
vřele doporučit. Napřı́klad program nohup obstarává implicitnı́ přesměrovánı́ do
souboru nohup.out, pokud uživatel neuvede explicitně jiné přesměrovánı́.

Zřetězenı́ obslužných programů pomocı́ roury
Jednou ze základnı́ch potřeb vı́ceúlohového operačnı́ho systému je vzájemná
meziprocesová komunikace. Obslužné programy v Unixu jsou velmi jednoduché. Platı́
úzus, že každý obslužný program by měl vykonávat pouze jednu činnost a měl by
ji dělat dobře a efektivně. Přı́kladem je třeba program cat, který pouze zřetězuje
soubory. Složitějšı́ problémy se řešı́ spojovánı́m těchto malých „dı́lů stavebnice“ do
většı́ch celků. Účastnı́-li se několik programů řešenı́ většı́ho problému, obvykle si
mezi sebou vyměňujı́ data.

96

Kapitola 5. Základy přı́kazového interpretu

Obslužné programy jsou navrženy zpravidla jako filtry, pracujı́ se svým standardnı́m vstupem a standardnı́m výstupem. Ve vzájemném předávánı́ dat mezi programy
tedy nenı́ žádný problém – programy si mohou data předávat pomocı́ datových souborů. Souborový přı́stup k meziprocesové komunikaci je však velmi neefektivnı́.
Jednak neúměrně vytěžuje diskové jednotky počı́tače, navı́c se nejedná o přı́liš čisté
řešenı́.
Tvůrci operačnı́ho systému Unix již v jeho raných verzı́ch přišli s aparátem umožňujı́cı́m komunikaci mezi dvěma procesy. Hlavnı́ myšlenkou je vytvořenı́ datového
toku zpravidla mezi rodičem a synovským procesem. Datový tok mezi přı́buznými
procesy je umožněn dı́ky tabulce deskriptorů zděděné od jejich společného předka.
Jelikož může být do datového toku jednou stranou pouze zapisováno a druhou stranou
pouze čteno, dostal tento mechanismus meziprocesové komunikace výstižný název
roura – pipe. Pomocı́ roury mohou komunikovat i dva synovské procesy. Roura řešı́
problém komunikace mezi producentem a konzumentem. Producent je proces, jehož výstup je pomocı́ roury přenášen na vstup konzumenta. Roura funguje jako fronta. Vznik
roury je podmı́něn volánı́m jádra pipe(), na uživatelské úrovni lze jejı́ vytvořenı́
podmı́nit metaznakem „|“. Syntaxe přı́kazu využı́vajı́cı́ho rouru je
/producent. | / konzument.
kde / producent. je přı́kaz pro spuštěnı́ programu, jehož standardnı́ výstup je zapisován do roury a /konzument. je přı́kaz pro spuštěnı́ programu, který svůj standardnı́
vstup čte z roury. Na následujı́cı́m obrázku je zobrazen princip komunikace dvou
procesů pomocı́ roury.
tabulka
deskriptorů
producent

tabulka
deskriptorů

0 stdin
0
1
stdout 1
2
2

..
.

konzument

..
.

Při použitı́ roury docházı́ opět k přesměrovánı́. Na rozdı́l od souborové komunikace při použitı́ roury nedocházı́ k vytvářenı́ nežádoucı́ch souborů na disku. Identického výsledku, ale s vytvořenı́m pomocného souboru, lze dosáhnout následujı́cı́m
kódem:
/producent. >/ soubor.; / konzument. </ soubor.; rm /soubor.
Přı́kaz pro shell, v němž se vyskytuje metaznak „|“, se nazývá kolona. Metaznak „|“
má vyššı́ prioritu než ostatnı́ metaznaky. Prioritu demonstruje přı́klad.
$ date; who | wc &
Thu Jul 5 10:37:40 CEST 2001
[1] 473
3
15
93
[1]+ Done
who | wc

5.2.

Přesměrovánı́ a roury

97

Nejprve byl spuštěn program date. Poté byl rourou propojen výstup programu
who na vstup programu wc. Tato kolona dvou procesů byla spuštěna na pozadı́. Propojenı́ obou přı́kazů způsobilo výpis počtu všech přihlášených uživatelů, respektive
celkového počtu použı́vaných terminálů. V tomto přı́padě došlo při použitı́ roury
ke komunikaci dvou synovských procesů shellu.
Kolona musı́ být vždy uzavřená. Roura nemůže být „přetržena“, na pravé straně
roury musı́ být vždy proces, který čte výstup z roury. V přı́padě, že tomu tak nenı́,
jádro zası́lá procesu na levé straně roury signál SIGPIPE. Roura je v Unixu využı́vána
velmi často. Prakticky nahrazuje přesměrovánı́ vstupu. Následujı́cı́ dva přı́kazy majı́
identický význam.
$ program <cisla
$ cat cisla | program

Kolonu lze v přı́kazu použı́t i vı́cekrát. Neformálně lze kolonu chápat jako aparát
umožňujı́cı́ zřetězovat obslužné programy řešı́cı́ dı́lčı́ problémy. Při použitı́ roury je
v některých situacı́ch vhodné průběžně ukládat výstup některého procesu, ale zároveň jej poskytovat dalšı́mu konzumentovi. K tomuto jednoduchému větvenı́ roury
sloužı́ program tee. Program tee čte standardnı́ vstup a předává jej na standardnı́
výstup podobně jako program cat, navı́c může data průběžně zapisovat do souboru
na disku. Jméno souboru je programu tee předáno jako argument. Použitı́ přı́kazu
demonstruje následujı́cı́ přı́klad.
$ (date; who) | tee zaznam.txt | tail +2 | less

Předchozı́ kolonou uživatel nejprve spustil programy who a date, jejich výstup
je předán programu tee, ten provede jeho zápis na disk a dále jej předá programu
tail. Program tail odstranı́ ze vstupu prvnı́ řádek – datum a zbytek poskytne
stránkovači less. Stránkovač umožnı́ uživateli pohodlně prohlı́žet přihlášené uživatele. V souboru zaznam.txt bude ale zachováno i datum, protože program tee
provedl uloženı́ obsahu vstupu na disk a program tail následuje až za nı́m.
Na závěr kapitoly o přesměrovánı́ a rourách uvedeme dva trochu komplikovanějšı́ přı́klady. V přı́kladech se vyskytujı́ nástroje popsané až v dalšı́ch kapitolách.
Cı́lem přı́kladů je ale ukázat variabilitu, předevšı́m sı́lu aparátu, již nám Unix a shell
zpřı́stupňujı́. Přı́klady jsou uvedeny bez výstupů.
$ who | grep novakj | wc -l
$ cat cisla.txt | sed s/,/+/g | calc | sort -nr

Na prvnı́m řádku byl použit program grep filtrujı́cı́ vstupnı́ data podle jistého
vzoru. V tomto přı́padě program grep převedl na výstup pouze řádky obsahujı́cı́
posloupnost novakj. Prvnı́ přı́kaz vypı́še, kolikrát je uživatel novakj přihlášen.
V druhém přı́kladu je pro změnu použit proudový editor sed. Program je určen k prováděnı́ náhrad v textu podle vzorů. Předpokládejme, že ve vstupnı́m souboru cisla.txt jsou na řádcı́ch zapsána čı́sla oddělená čárkou. Uživatel tı́mto
přı́kazem provede součet čı́sel v řádcı́ch a jednotlivé součty vypı́še sestupně. Idea
je vcelku jednoduchá. Nejprve byly symboly čárka nahrazeny symboly plus „+“.

98

Kapitola 5. Základy přı́kazového interpretu

Výstup v tomto tvaru byl předán programu calc, který každý řádek vyhodnotil.
Součty byly dále postoupeny programu sort třı́dı́cı́mu vstupnı́ řádky. Jelikož byl
použit přepı́nač -r, výsledné řádky byly setřı́děny sestupně. Argument -n zajišt’uje,
že sort bude se vstupnı́mi daty zacházet jako s čı́sly.

Pojmenovaná roura
Spojovánı́ obslužných programů do vyššı́ch celků patřı́ ke zcela běžným praktikám vyspělého uživatele systému Unix. Doposud uvažovanou meziprocesovou komunikaci pomocı́ roury umožňovala společná tabulka deskriptorů otevřených souborů.
Vytvářenı́ datových toků ve formě rour jinými slovy vyžaduje vzájemnou „přı́buznost
propojovaných procesů“. Roury rovněž nelze použı́t při manipulaci s interaktivnı́mi
programy. Interakce si vyžaduje přı́mou práci se standardnı́m vstupem a výstupem.
Přı́má práce se v tomto přı́padě vylučuje s přesměrovánı́m.
Částečným východiskem ze situace je použitı́ speciálnı́ho mechanismu – pojmenované roury. Pojmenovaná roura funguje na principu speciálnı́ho souboru, jenž může
být jednı́m procesem otevřen pro vstup a druhým procesem může být současně otevřen pro výstup. Proti klasickým datovým souborům mohou s pojmenovanou rourou
efektivně pracovat dva procesy současně a mohou si tak pomocı́ nı́ předávat data.
Jelikož je pojmenovaná roura reprezentována speciálnı́m souborem, lze ji vytvořit
programem mknod využı́vajı́cı́m volánı́ jádra mknod().
Na uživatelské úrovni je pojmenovaná roura zpravidla vytvářena obslužným programem mkfifo. Jediný povinný argument programu mkfifo je cesta k nově vytvořenému speciálnı́mu souboru. Cesta reprezentuje umı́stěnı́ pojmenované roury v souborovém systému. Program může být dále spuštěn s argumentem --mode=/práva..
V tomto přı́padě jsou přı́stupová práva k pojmenované rouře nastavena na hodnotu
/práva.. Uživatel může pomocı́ argumentu --mode omezit dostupnost pojmenované
roury pro ostatnı́ uživatele v systému.
Pokud je pojmenovaná roura vytvořena, lze s nı́ zacházet v podstatě jako s libovolným souborem. Napřı́klad je možné přesměrovat výstup programu do pojmenované
roury, samozřejmě je možné i přesměrovat vstup z pojmenované roury. Proces čtenı́
a zápisu se chová vesměs jednosměrně. Proces, jenž má otevřenu pojmenovanou
rouru pro čtenı́, do nı́ nemůže ve stejném okamžiku zapisovat, a obráceně. Pokud
jeden či vı́ce programů do pojmenované roury zapisuje, „na druhém konci“ musı́
nějaký proces pojmenovanou rouru čı́st. V opačném přı́padě dojde k zablokovánı́
zapisujı́cı́ch procesů. Analogicky dojde k zablokovánı́ čtecı́ho procesu, pokud do
pojmenované roury žádný proces nezapisuje.
Použitı́ pojmenované roury demonstruje následujı́cı́ přı́klad. I když jde o velmi
jednoduchý problém, který nenı́ potřeba řešit pomocı́ pojmenované roury, je z něj
vidět jednoduchost a předevšı́m sı́la pojmenované roury. V přı́kladu jsou spojeny
programy cat, find, grep a wc pomocı́ pojmenované roury a zároveň pomocı́
kolony.
$ mkfifo --mode=600 /tmp/moje-roura
$ find /usr/share -type d >/tmp/moje-roura

5.3.

Expanze jmen souborů

99

· · · na jiném terminálu · · ·
$ cat /tmp/moje-roura | grep html | wc -l
12
$ rm /tmp/moje-roura

V přı́kladu byla nejprve vytvořena pojmenovaná roura /tmp/moje-roura. Dále
byl do právě vytvořené roury přesměrován výstup vytvořený programem find. Výstupem byl seznam podadresářů nacházejı́cı́ch se v adresáři /usr/share. Pojmenovaná roura je dále čtena programem cat zřetězeným kolonou s programy grep
a wc. Smyslem třetı́ho přı́kazu je vypsat počet podadresářů, jejichž jméno obsahuje
řetězec html. Třetı́ přı́kaz může být bez újmy proveden napřı́klad v úplně jiném
terminálu – dı́ky pojmenované rouře nepotřebuje mı́t přı́mou přı́buzenskou vazbu
na proces zapisujı́cı́ do pojmenované roury. Soubor /tmp/moje-roura byl na konci
práce smazán.
S využitı́m pojmenované roury se lze setkat napřı́klad při práci s FTP klientem.
FTP klient sloužı́ k přenosu datových souborů ze vzdálených hostitelů na lokálnı́
systém a obráceně. V drtivé většině se jedná o interaktivnı́ program. Pokud uživatel
nechce přenesená data ukládat na disk, ale chce je rovnou zpracovávat, může data
„ukládat do pojmenované roury“. Na druhou stranu pojmenované roury stačı́ umı́stit
vhodný proces zpracovávajı́cı́ přijı́maná data. Detaily o službě FTP jsou uvedeny
v kapitole 7.5. Ještě obecnějšı́m mechanismem meziprocesové komunikace je zásuvka –
– socket. Pomocı́ zásuvky je možné zřetězovat i nelokálnı́ procesy, to jest procesy
běžı́cı́ na různých hostitelských počı́tačı́ch. V přı́padě zásuvky jsou data mezi procesy
přenášena prostřednictvı́m počı́tačové sı́tě. Pro detaily viz kapitolu 7.1.
Na ukázkových přı́kladech v této kapitole byste si měli uvědomit, že kromě zajištěnı́ meziprocesové komunikace je velmi nutné zajistit „kompatibilitu dat“. Obslužné
programy systému Unix jsou schopny pracovat s různě reprezentovanými daty. Před
propojenı́m programů je leckdy nutné provést úpravu či transformaci dat. K těmto
účelům sloužı́ napřı́klad filtry a proudové editory. Jelikož jde o velmi důležité nástroje, jsou jim věnovány samostatné kapitoly 6.1. a 6.2.

5.3. Expanze jmen souborů
Téměř všechny obslužné programy v systému Unix čtou vstupnı́ data ze standardnı́ho vstupu nebo ze souborů předaných programu jako argumenty. Obě dvě
možnosti se jen málokdy vylučujı́. Soubory jsou jednoznačně určeny pomocı́ cesty.
V praxi se však uživatel velmi často setká s potřebou kvantifikovat jména souborů.
Kvantifikované jméno souboru zastupuje obecně vı́c souborů. Požadavek kvantifikovat jména souborů je zcela přirozený. Denně se uživatel může setkat s nutnostı́
manipulovat s několika soubory, které majı́ společné prvky ve svých jménech, napřı́klad stejné zakončenı́. Kvantifikovaná jména souborů se rovněž nazývajı́ neúplná
jména. Uvedenı́m neúplného jména souboru uživatel definuje „vzor jména“. Vzor je
posléze shellem expandován na lexikograficky setřı́děný seznam jmen existujı́cı́ch
souborů odpovı́dajı́cı́ch zadanému vzoru.

100

Kapitola 5. Základy přı́kazového interpretu

V shellu lze použı́t několik speciálnı́ch metaznaků zastupujı́cı́ch jeden nebo vı́ce
znaků ve jménu souboru. Akceptuje-li program soubory jako vstupnı́ argumenty, uživatel je může specifikovat pomocı́ jména, ve kterém se vyskytujı́ zástupné symboly.
Následujı́cı́ tabulka obsahuje základnı́ zástupné metaznaky.
metaznak

význam

~
~/ jméno .
?
*
[/ množina.]
\/ znak.

domovský adresář
domovský adresář uživatele / jméno .
libovolný znak
posloupnost libovolných znaků
libovolný znak z množiny
jeden konkrétnı́ / znak.

Použitı́ metaznaku „~“ jako zástupného symbolu pro domovský adresář uživatele
jsme již diskutovali. Je-li jméno uživatele vynecháno, je výskyt „~“ nahrazen domovským adresářem aktuálnı́ho uživatele. Podotkněme, že metaznak „~“ je expandován
pouze v přı́padě, pokud se nacházı́ na začátku slova. Jinými slovy, „~“ je expandován, pouze jsou-li bezprostředně před nı́m oddělovače mezera, tabulátor nebo nový
řádek. Napřı́klad ve výrazu ~/data bude metaznak „~“ nahrazen absolutnı́ cestou
k domovskému adresáři, ale ve výrazu soubor.txt~ nikoliv.
Metaznak otaznı́k „?“ zastupuje jeden libovolný znak. Metaznak hvězdička „*“
zastupuje libovolnou posloupnost znaků včetně prázdné posloupnosti. Pokud je
potřeba specifikovat množinu znaků, použı́vajı́ se metaznaky „[“ a „]“ obklopujı́cı́
definici množiny znaků.
Množinu znaků lze definovat různým způsobem. Prvnı́ možnostı́ je výčet, mezi
závorky je uveden seznam znaků, napřı́klad [abcd] znamená „jeden ze znaků a, b,
c nebo d“. Druhou možnostı́ je specifikovat množinu jako posloupnost znaků ve tvaru
[/ prvnı́.-/poslednı́.], kde / prvnı́. je prvnı́ znak, / poslednı́. je poslednı́ znak, obě
hodnoty jsou odděleny metaznakem pomlčka „-“. Napřı́klad [a-d] reprezentuje
stejnou množinu jako [abcd]. Oba přı́stupy lze kombinovat, navı́c je možné definovat několik posloupnostı́, napřı́klad [a-ch-kz] reprezentuje sjednocenı́ množin
[a-c], [h-k] a [z]. Symbol „-“ má význam jako metaznak pouze uprostřed hranatých závorek. Pokud uživatel chce specifikovat znak „-“, musı́ jej uvést v seznamu
jako prvnı́. V tom přı́padě nenı́ symbol interpretován jako metaznak, jelikož by definovaná posloupnost „postrádala počátek“. Napřı́klad [-a-c] reprezentuje znaky
a, b, c, a navı́c znak „-“.
Při specifikaci množiny znaků lze použı́t i množinový doplněk. Pokud je za závorku
„[“ uveden metaznak „^“, je následujı́cı́ specifikace množiny brána jako doplněk
do množiny všech znaků. Napřı́klad [^a-c] definuje „libovolný znak vyjma a, b
a c“. Pokud stojı́ „^“ na jiném mı́stě než bezprostředně za otevı́racı́ závorkou, je
interpretován jako znak „^“.
Poslednı́m metaznakem umožňujı́cı́m specifikovat znaky je zpětné lomı́tko „\“.
Svým způsobem nepatřı́ do této množiny metaznaků, protože je to zástupný symbol pouze pro jediný symbol. Za metaznakem „\“ musı́ následovat libovolný znak,

5.3.

Expanze jmen souborů

101

který zastupuje. Metaznak „\“ se použı́vá k potlačenı́ expanze, jak bude vidět dále.
V následujı́cı́ tabulce jsou uvedeny možné tvary specifikacı́ množin znaků.
množina

význam

množina

význam

[abcd]
[a-cd]
[a-d]
[a-bc-d]
[abc-d]

znaky a, b, c, d
znaky a, b, c, d
znaky a, b, c, d
znaky a, b, c, d
znaky a, b, c, d

[-ab]
[^a-c]
[^a-cz]
[a-c^]
[-a-c^z]

znaky a, b, libovolný znak vyjma a, b, c
libovolný znak vyjma a, b, c, z
znaky a, b, c, ^
znaky a, b, c, z, -, ^

Ještě před uvedenı́m přı́kladů kvantifikace jmen souborů pomocı́ speciálnı́ch metaznaků je dobré objasnit, jak probı́há samotná expanze jmen souborů. Při uvedenı́ přı́kazu pro spuštěnı́ programu shell mimo jiné analyzuje argumenty předané spouštěnému programu. Nalezne-li v nich metaznaky zastupujı́cı́ množiny znaků nebo jejich
sekvence, provede expanzi – nahrazenı́ neúplného jména souboru seznamem existujı́cı́ch souborů. Řečeno jinými slovy, na mı́sto původnı́ho argumentu jsou vloženy
nové argumenty, každý z nich reprezentuje jeden skutečný soubor odpovı́dajı́cı́ vzoru.
Pokud by byl seznam prázdný, shell ponechá argument neexpandovaný. Podstatné je
uvědomit si, že expanze probı́há na úrovni shellu. Některé jiné systémy, disponujı́cı́ podobným byt’omezeným aparátem kvantifikace jmen souborů, přenechávajı́ expanzi
až na spuštěném programu. V Unixu volaný program v zásadě nepozná, jestli byly
jeho argumenty zadány přı́mo uživatelem, nebo jestli byly expandovány shellem.

Použı́vánı́ neúplných jmen souborů
Pro demonstraci expanze je výhodné použı́t obslužný program echo, jenž je standardnı́ součástı́ všech systémů. Program echo vypı́še předané argumenty na standardnı́ výstup a ukončı́ svou činnost. Pokud se mezi vstupnı́mi argumenty vyskytujı́
expandovatelné metaznaky, shell je před předánı́m programu expanduje. Uživatel
může pomocı́ programu echo sledovat, jak expanze proběhla. Viz následujı́cı́ přı́klady.
$ echo *
bin data etc mail
$ echo .*
. .. .bash_history .forward .fvwmrc .profile
$ echo .* *
. .. .bash_history .forward .fvwmrc .profile bin data etc mail

V prvnı́m přı́padě shell metaznak „*“ expandoval na jména všech viditelných
souborů. Soubory začı́najı́cı́ tečkou jsou neviditelné, jejich expanzi lze vynutit použitı́m
tečky na začátku neúplného názvu. V třetı́m přı́padě byly vypsány všechny soubory
v adresáři. Předávané argumenty byly dva, „.*“ a „*“, shell je postupně expandoval
nejprve na neviditelné soubory, potom na viditelné. Program echo lze v přı́padě
nouze použı́t v systému k částečnému nahrazenı́ programu ls. Dalšı́ přı́klad ukazuje
použitı́ zástupného metaznaku „?“.

102

Kapitola 5. Základy přı́kazového interpretu
$ echo .*r?
.bash_history .forward .fvwmrc

Vypsány byly skryté soubory, jejichž předposlednı́ pı́smeno je r. Tečka na začátku
byla opět nutná ze stejného důvodu jako v předchozı́m přı́padě. V ukázce jsou
uvedena typická použitı́ metaznaků „[“ a „]“.
$ echo [a-d]*
bin data
$ echo [a-d]a*
data
$ echo ?[^a-d]*
bin etc todo

Nejprve byly vypsány viditelné soubory začı́najı́cı́ pı́smeny a až d. V druhém
přı́padě byla podmı́nka dále zesı́lena pevnou volbou druhého znaku – a. Neúplnému
jménu [a-d]a* již odpovı́dá pouze adresář data. V třetı́m přı́pade byly vypsány
soubory, jejichž druhé pı́smeno v názvu nepatřı́ mezi a, b, c nebo d. Neúplných jmen
souborů se použı́vá často při hromadném kopı́rovánı́, přesouvánı́ nebo zřetězenı́. Viz
přı́klad použitı́.
$ cat *.tex | wc -l >delka.txt
$ cp *-2000[01][0-9].dat ~/data
$ mv diploma.* ~/data/backup

Prvnı́ přı́kaz zapı́še do souboru delka.txt celkový počet řádků souborů zakončených .tex. V druhém přı́padě dojde ke zkopı́rovánı́ souborů z roku 2000 do
adresáře ~/data. V třetı́m přı́padě se přesunou soubory začı́najı́cı́ diploma. do
adresáře ~/data/backup.

Potlačenı́ expanze jmen
Pozorného čtenáře jistě napadlo, že expanze řı́zená shellem může mı́t kromě
výhod i své nevýhody. Základnı́ otázka znı́: „Jak přinutit shell, aby některé metaznaky
neexpandoval?“ Řada filtrů a proudových editorů pracuje s regulárnı́mi výrazy. V nich
má symbol „*“ speciálnı́ význam – vytvářı́ uzávěr regulárnı́ho výrazu. Pokud uživatel
volá program a jako argument mu předává regulárnı́ výraz, v některých přı́padech
musı́ explicitně shellu oznámit, aby neprováděl expanzi metaznaků. To lze učinit
několika způsoby. Jednı́m z nich je použitı́ metaznaku zpětné lomı́tko „\“. Narazı́-li
shell na tento metaznak, dosadı́ na jeho mı́sto znak, který se nacházı́ bezprostředně
za nı́m, jeho expanzi však již neprovádı́.
$ echo *
bin data etc mail todo
$ echo \*
*

5.3.

Expanze jmen souborů

103

Pomocı́ metaznaku „\“ je možné vytvářet argumenty, v nichž jsou mezery. Mezera
byla doposud chápána také jako metaznak, protože ji shell interpretuje jako oddělovač argumentů na přı́kazovém řádku. Jelikož „\“ zabraňuje jakékoliv interpretaci
metaznaku, uživatel může předávat argumenty, ve kterých jsou mezery. Rozdı́l mezi
jednı́m argumentem s mezerami a několika argumenty lze nejlépe demonstrovat
následujı́cı́m přı́kladem.
$ cat jeden\ argument
cat: jeden argument: No such file or directory
$ cat vice argumentu
cat: vice: No such file or directory
cat: argumentu: No such file or directory

V prvnı́m přı́padě vzniklo jen jedno chybové hlášenı́, protože soubor jménem
„jeden argument“ nebyl nalezen. V druhém přı́padě vznikla chybová hlášenı́ dvě,
ani jeden ze souborů „vice“ a „argumentu“ nebyl nalezen.
Dalšı́ možnostı́ potlačenı́ expanze je uzavřenı́ posloupnosti znaků mezi uvozovky
nebo apostrofy. Z pohledu expanze se uvozovky i apostrofy chovajı́ identicky, rozdı́l v jejich chovánı́ lze nalézt při dereferenci proměnných a substituci přı́kazů, viz
kapitolu 5.4. Uzavřenı́ mezi uvozovky nebo apostrofy je vhodné použı́t, pokud se
v posloupnosti znaků vyskytuje hodně speciálnı́ch symbolů a jejich potlačovánı́ pomocı́ „\“ by bylo nepřehledné. Je-li posloupnost uzavřená do uvozovek či apostrofů,
nelze v nı́ již použı́t „\“ jako metaznak. Z tohoto důvodu se obtı́žně vyjadřujı́ napřı́klad „uvozovky v uvozovkách“. Viz ukázku.
$ echo ’ahoj svete’
ahoj svete
$ echo ’ahoj’\’’ svete’
ahoj’ svete
$ echo ”ahoj’ svete”
ahoj’ svete

V druhém přı́padě nebylo možné vložit apostrof do posloupnosti přı́mo. Posloupnost znaků se musela nejprve rozdělit na zřetězenı́ dvou částı́ a mezi ně byl vložen
apostrof pomocı́ metaznaku „\“. V třetı́m přı́padě lze napsat apostrof přı́mo, protože
je posloupnost uzavřena do uvozovek.
Předcházejı́cı́ kapitola ukázala, jakým způsobem lze navazovat výstup jednoho
procesu na vstup jiného. Obdobným požadavkem je možnost předávat argumenty
mezi procesy – výstup jednoho procesu je brán jako vstupnı́ argument spouštěného
procesu. Proces může být spuštěn až poté, co jsou vygenerovány všechny jeho argumenty. To znamená, že proces využı́vajı́cı́ výstup jiného procesu jako argument
může být spuštěn až po jeho dokončenı́ a předánı́ vstupnı́ho argumentu. Tento způsob generovánı́ argumentů se nazývá substituce přı́kazů. Substituce přı́kazu má dvojı́
syntaxi:
‘/přı́kaz.‘
$(/ přı́kaz.)

104

Kapitola 5. Základy přı́kazového interpretu

Druhá notace funguje pouze v shellu GNU Bash, prvnı́ notace funguje i v jeho
předchůdci Bourne Shellu. Druhý styl zápisu přı́kazu je výhodný, zejména pokud
je potřeba substituci přı́kazů vnořovat. Vnořenı́ lze provést i v prvnı́m přı́padě, ale
často se při tom lze setkat se skřı́pánı́m zubů – uživatel se může rychle ztratit ve
změti apostrofů.
Problematiku demonstrujme jednoduchým přı́kladem. Předpokládejme, že uživatel novakj si chce pomocı́ programu echo zobrazit informace o počı́tači, na kterém
je přihlášen, a o svém pracovnı́m adresáři.
$ echo Jsi na stroji ‘hostname‘ v adresari ‘pwd‘.
Jsi na stroji phoenix v adresari /home/student/inf97/novakj.
$ echo Jsi na stroji $(hostname) v adresari $(pwd).
Jsi na stroji phoenix v adresari /home/student/inf97/novakj.

Oba přı́kazy jsou identické, lišı́ se pouze v použité notaci. Program hostname
vypı́še jméno hostitelského počı́tače. Při substituci přı́kazů lze využı́t vlastnosti závorek. V předchozı́ ukázce byl výsledný argument zı́skaný z výstupu programu vždy
jeden – jednalo se bud’to o jméno počı́tače, nebo o cestu k souboru. Obecně mohou
být výstupnı́ data rozložena na vı́c řádků a oddělena mezerami. V takovém přı́padě
by byla každá posloupnost znaků bez mezer dosazena jako jeden separovaný argument.
V některých přı́padech je to ale nežádoucı́ – výstup je potřeba předat jako jeden argument s mezerami. V tom přı́padě je nutné uzavřı́t substituci přı́kazu do uvozovek.
$ echo ‘ls -1F‘
bin/ data/ etc/ mail/
$ echo ”‘ls -1F‘”
bin/
data/
etc/
mail/
$ echo ’‘ls -1F‘’
‘ls -1F‘

Z přı́kladu je vidět, že i když ls -1F zajistil výpis souborů do jednoho sloupce,
v prvnı́m přı́padě jsou vypsány do řádku. Každý řádek výpisu je totiž chápán jako
samostatný argument programu echo. Prvnı́ přı́kaz echo byl volán se čtyřmi argumenty, každý název souboru byl jednı́m argumentem. V druhém přı́padě byla
substituce vnořena do uvozovek – uvozovky potlačily dalšı́ expanzi metaznaků mezera a nový řádek. Ve svém důsledku byl program echo volán s jednı́m argumentem.
V poslednı́m přı́padě nedošlo k expanzi vůbec. Apostrofy na rozdı́l od uvozovek
potlačujı́ interpretaci všech metaznaků, tedy i obrácených apostrofů. Na závěr jsou
uvedeny přı́klady typického použitı́ substituce přı́kazu.
$ cd; mkdir backup
$ cp $(find . -type f) ~/backup
$ mv $(find . -type f | grep -v scm) ~/zaloha
$ cat $(find -name ”*.txt”) | wc -l
18

5.4.

Proměnné

105

Na druhém a třetı́m řádku došlo ke zkopı́rovánı́ a přesunutı́ souborů do adresářů backup a zaloha. Argument -type f programu find definuje typ hledaného souboru na obyčejný soubor. V druhém přı́padě byly z výstupu programu find
odstraněny řádky neobsahujı́cı́ podřetězec scm. Na poslednı́m řádku byl zobrazen
celkový počet řádků souborů se zakončenı́m .txt. Jistým úskalı́m při použı́vánı́
substituce přı́kazů je omezená velikost přı́kazu. Shell zpravidla omezuje maximálnı́ počet argumentů volaného programu. Pokud by substitucı́ přı́kazu došlo k přesáhnutı́
tohoto limitu, přı́kaz nebude správně proveden. Východiskem ze situace je použitı́
programu xargs. Program xargs čte data ze standardnı́ho vstupu a po jejich načtenı́ spustı́ zadaný program s argumenty, které právě načetl ze standardnı́ho vstupu.
Pro detaily viz manuálovou stránku programu xargs.

5.4. Proměnné
Proměnné sloužı́ shellu k uchovánı́ informacı́ měnı́cı́ch se během práce nebo
svázaných s přihlášeným uživatelem. Každá proměnná má svoje jméno, atributy a svůj
obsah neboli hodnotu. Na rozdı́l od většiny programovacı́ch jazyků shell podporuje
pouze jeden datový typ – řetězec znaků. V praxi to napřı́klad znamená, že čı́slo 123
bude reprezentováno řetězcem třı́ znaků, 1, 2, 3. Tento fakt může dále působit jisté
obtı́že. Má-li řetězec význam čı́sla, nelze jej jednoduše porovnávat lexikografickým
uspořádánı́m, protože napřı́klad 10<9, jelikož 1<9. Lexikografické uspořádánı́ nenı́
vhodné napřı́klad při porovnávánı́ velikosti souborů nebo jiných čı́selných údajů.
Tento zápor je vykoupen mnoha klady. Systém proměnných je dostatečně jednoduchý
a nenı́ potřeba proměnné deklarovat – explicitně předurčovat jejich datový typ.
Proměnné v systému lze rozdělit do třı́ skupin. Prvnı́ skupinou jsou vnitřnı́ proměnné shellu, o jejichž inicializaci, to jest naplněnı́ hodnotami, se stará shell sám. Druhou skupinou jsou uživatelské proměnné, ty mohou být definovány uživatelem podle
potřeby. Do třetı́ skupiny patřı́ proměnné speciálnı́ho významu uchovávajı́cı́ informace
o běžı́cı́ch procesech, předávaných argumentech a podobně. Názvy proměnných
speciálnı́ho významu jsou sestavené ze speciálnı́ch znaků, kdežto názvy uživatelských
a vnitřnı́ch proměnných shellu sestávajı́ z alfanumerických znaků, to jest pouze z pı́smen a čı́sel.
Dalšı́m kritériem rozdı́lnosti proměnných je možnost změny jejich obsahu. Uživatelé nemohou modifikovat všechny proměnné. Napřı́klad proměnné speciálnı́ho
významu jsou vesměs pouze pro čtenı́ – uživatel může jejich obsah čı́st, ale nemůže jej
měnit. Rovněž některé vnitřnı́ proměnné shellu jsou pouze pro čtenı́. Shell poskytuje
uživateli přı́kazy, pomocı́ nichž může také svým proměnným přiřadit status „pouze
pro čtenı́“. Problematika bude rozebrána dále v textu.

Přiřazenı́ a dereference
Při práci s proměnnou uživatel použı́vá dva základnı́ typy přı́kazů, přiřazenı́
a dereferenci. Přı́kaz přiřazenı́ sloužı́ k definovánı́ obsahu proměnné. Ve většině imperativnı́ch jazyků, ke kterým patřı́ i shell, má přiřazenı́ tvar L = R. Výraz L na levé

106

Kapitola 5. Základy přı́kazového interpretu

straně přı́kazu přiřazenı́ reprezentuje referenci na proměnnou. V shellu je to název
proměnné. Pravá strana přı́kazu přiřazenı́ R představuje výraz, jehož hodnota je uložena v proměnné daného jména. Nenı́-li pravá strana uvedena, shell tuto konstrukci
chápe jako požadavek na zrušenı́ proměnné daného jména3 . Na úvod je dobré upozornit na fakt, že pravá strana obsahuje výraz zpracovávaný shellem. Může napřı́klad
obsahovat metaznaky expandovatelné shellem. Do proměnných se ale data ukládajı́
v neexpandovaném tvaru.
Přı́kaz dereference je v shellu uvozen metaznakem „$“, bezprostředně za nı́m
následuje jméno proměnné. Shell dereferenci expanduje na hodnotu proměnné. Expanze
samozřejmě neproběhne, pokud je výraz uzavřen do apostrofů nebo je expanze potlačena metaznakem „\“. Při dereferenci dosud nedefinované proměnné obdržı́me
„prázdnou hodnotu“. Viz přı́klad.
$ PRVNI=obsah
$ echo $PRVNI
obsah
$ PRVNI=
$ echo $PRVNI

Uživatel nejprve definoval proměnnou PRVNI s obsahem obsah. Poté provedl
jejı́ dereferenci, dı́ky přı́kazu echo byla vypsána hodnota na výstup. Dále byla proměnná odstraněna přı́kazem prázdného přiřazenı́. Během přiřazenı́ může proměnná
na pravé straně dereferencovat i sebe samu. Dereference se však v žádném přı́padě
nemůže vyskytovat na levé straně rovnosti. Typickým přı́padem, kdy proměnná dereferencuje sebe samu při přiřazenı́, je připojenı́ nového údaje do prohledávacı́ cesty
reprezentované proměnnou PATH. Viz přı́klad.
$ echo $PATH
~/bin:/usr/local/bin:/usr/bin:/bin:/usr/bin/X11:/usr/games
$ PATH=$PATH:.
$ echo $PATH
~/bin:/usr/local/bin:/usr/bin:/bin:/usr/bin/X11:/usr/games:.

Proměnná PATH obsahuje prohledávacı́ cestu, jednotlivé adresáře jsou odděleny
znakem „:“. Předchozı́ přı́klad ukazuje, jak lze do prohledávacı́ cesty přidat i pracovnı́ adresář. V přı́kladu je dobré všimnout si dvou věcı́. Jednak bylo nutné oddělit
pracovnı́ adresář „.“ dvojtečkou, jednak na levé straně přiřazenı́ se nevyskytuje
metaznak „$“. Při přiřazenı́ hodnoty proměnné je možné použı́vat všech doposud
uvedených konstrukcı́. Následujı́cı́ přı́klad demonstruje využitı́ expanze a substituce
přı́kazu.
$ DRUHA=data/scheme/*
$ TRETI=$(date ’+%d %m %Y’)
$ echo $DRUHA $TRETI
data/scheme/faktorial.scm data/scheme/fibonacci.scm 06 07 2001
3 Stejného efektu lze dosáhnout použitı́m přı́kazu unset.

5.4.

Proměnné

107

Začátečnı́ci se při použitı́ proměnných dopouštějı́ častých chyb. Jedna z nich
pramenı́ z neúplného pochopenı́ pořadı́ dereferencı́ a expanzı́, které provádı́ shell.
Uvažujme proměnnou DRUHA, která byla vytvořena v předchozı́m přı́kladu. Za pozornost stojı́ výstup následujı́cı́ch přı́kazů.
$ echo $DRUHA
data/scheme/faktorial.scm data/scheme/fibonacci.scm
$ echo ”$DRUHA”
data/scheme/*
$ echo ’$DRUHA’
$DRUHA
$ echo $DRUHA,
data/scheme/*,

V prvnı́m přı́padě došlo po dereferenci k expanzi. V druhém přı́padě se proměnná
dereferencovala, ale k expanzi nedošlo, jelikož výraz byl uzavřen mezi uvozovky. Ve
třetı́m přı́padě nedošlo ani k dereferenci, protože apostrofy potlačujı́ význam metaznaku „$“. V poslednı́ ukázce je možná výsledek poněkud zarážejı́cı́. Uživatel by
intuitivně očekával seznam souborů zakončený čárkou. Jelikož ale prvnı́ proběhne
dereference a zřetězenı́ s čárkou, při expanzi nenı́ nalezen žádný soubor, kterému odpovı́dá neúplné jméno ~/data/scheme/*,. Jak ale dosáhnout očekávaného efektu?
Problém lze vyřešit napřı́klad substitucı́ vnořeného přı́kazu.
$ echo $(echo $DRUHA),
data/scheme/faktorial.scm data/scheme/fibonacci.scm,

Doposud uváděná dereference byla pouze jednou z několika možných. Shell
umožňuje zapisovat dereferenci v různých tvarech s odlišným významem. Souhrn základnı́ch způsobů zápisu dereference nalezne čtenář v následujı́cm přehledu. Úplný
popis je k dispozici v manuálové stránce programu bash.
Výraz je expandován na hodnotu proměnné / proměnná..
Výraz je expandován na hodnotu proměnné. Složené závorky sloužı́ k oddělenı́ názvu proměnné od jejı́ho okolı́.
Tento tvar zápisu se použı́vá v přı́padě obklopenı́ názvu proměnné alfanumerickými znaky. Napřı́klad mı́sto
$(echo $PRVNI)X lze jednoduše psát ${PRVNI}X.
${/ proměnná.-/ výraz.} Je-li /proměnná. definována, je výsledkem jejı́ hodnota.
V opačném přı́padě je vrácen / výraz. a proměnná zůstává
nadále nedefinovaná.
${/ proměnná.=/ výraz.} Je-li /proměnná. definována, je výsledkem jejı́ hodnota.
V opačném přı́padě je proměnná definována na hodnotu
/ výraz. a potom je vrácena. Uvedená / proměnná. bude
mı́t po interpretaci výrazu vždy definovánu hodnotu, což
je výrazný rozdı́l proti předcházejı́cı́mu přı́padu.
${/ proměnná.+/ výraz.} Je-li / proměnná. definována, je vrácena hodnota / výraz..
Nenı́-li / proměnná. definována, nenı́ vrácena žádná hodnota.
$/proměnná.
${/ proměnná.}

108

Kapitola 5. Základy přı́kazového interpretu

Základnı́ atributy proměnných
Při práci s několika postupně spouštěnými shelly je výhodné předávat vnořeným shellům hodnoty proměnných. Jednı́m z významných atributů proměnné je
jejı́ export. Exportem rozumı́me přenesenı́ hodnoty proměnné i do vnořených shellů.
Problematiku demonstrujme přı́kladem.
$ PRVNI=ahoj
$ sh
$ echo ${PRVNI-nedefinovana}
nedefinovana
$ PRVNI=svete
$ echo $PRVNI
svete
$ exit; echo $PRVNI
ahoj

Z přı́kladu je jasně vidět, že po spuštěnı́ vnořeného shellu byla hodnota proměnné
PRVNI zapomenuta. Při ukončenı́ shellu byla k dispozici opět původnı́ hodnota proměnné. V některých přı́padech je ale vhodné přenášet hodnotu proměnné i do podřı́zených shellů. S tı́mto požadavkem se lze nejčastěji setkat při vytvářenı́ proměnných
v inicializačnı́ch skriptech. Při startu přihlašovacı́ho shellu se inicializujı́ základnı́ proměnné provedenı́m skriptů uložených v inicializačnı́ch souborech /etc/profile,
~/.profile, přı́padně ~/.bash_profile. Skript /etc/profile je systémový
a správce v něm může definovat proměnné potřebné pro práci všech uživatelů. Dalšı́
dva uvedené soubory jsou uloženy v uživatelském adresáři a uživatel si do nich může
zapsat potřebná nastavenı́. Přesnějšı́ popis inicializace proměnných čtenář nalezne
v kapitole 5.7.
Základnı́m požadavkem na všechna systémová i uživatelská nastavenı́ proměnných je jejich dědičnost do dalšı́ch shellů. Atribut exportu lze proměnné nastavit
pomocı́ vnitřnı́ho přı́kazu shellu export. Přı́kaz lze použı́vat bud’to se seznamem
proměnných, nebo také na levé straně přiřazovacı́ho přı́kazu. Viz přı́klad.
$ export PRVNI=ahoj
$ sh
$ echo $PRVNI
ahoj
$ exit

V uživatelském souboru ~/.profile je zpravidla definováno několik proměnných, proto je vhodné uvést přı́kaz export až úplně na konec se seznamem exportovaných proměnných. Poslednı́ řádek souboru může mı́t napřı́klad následujı́cı́
tvar.
export CLASSPATH EDITOR PATH LD_LIBRARY_PATH

Proměnné lze exportovat pouze z nadřı́zeného shellu do podřı́zeného shellu, opačně
exportovat proměnné nelze. Seznam aktuálně exportovaných proměnných lze zı́skat
zadánı́m přı́kazu export bez argumentu.

5.4.

Proměnné

109

Dalšı́m významným atributem proměnné je jejı́ neměnitelnost. Proměnné, které
lze pouze dereferencovat, ale jejich hodnotu nelze měnit pomocı́ přı́kazu přiřazenı́,
se nazývajı́ proměnné pouze pro čtenı́. V shellu je k nastavenı́ tohoto atributu určen
vnitřnı́ přı́kaz readonly.
$ PRVNI=ahoj
$ readonly PRVNI
$ PRVNI=svete
bash: PRVNI: readonly variable

Přı́kaz readonly uvedený bez argumentů vypı́še seznam všech proměnných
použitelných pouze pro čtenı́. Nastavenı́ proměnné pouze pro čtenı́ funguje pouze
na lokálnı́ úrovni, nepřenášı́ se do vnořených shellů. Je-li jednou proměnná nastavena
pouze pro čtenı́, nenı́ možné jı́ tento atribut odebrat.

Proměnné speciálnı́ho významu
Mezi proměnné speciálnı́ho významu patřı́ skupina třı́ proměnných nesoucı́ch informaci o hodnotě PID shellu, dále o hodnotě PID poslednı́ho procesu spuštěného na
pozadı́ a o návratové hodnotě poslednı́ho procesu. Všechny tři proměnné jsou pouze
pro čtenı́, jejich hodnoty měnı́ během práce samotný shell. Jmenované proměnné jsou
shrnuty v tabulce.
proměnná

význam

$$
$!
$?

PID shellu
PID poslednı́ho procesu spuštěného na pozadı́
návratová hodnota poslednı́ho dokončeného procesu

Již v předchozı́m textu bylo řečeno, že návratová hodnota procesu je celočı́selná. Nulová návratová hodnota signalizuje úspěšné dokončenı́ programu. Nenulové hodnoty znamenajı́ chybu v běhu programu. Význam jednotlivých čı́sel je k nalezenı́
zpravidla v manuálových stránkách konkrétnı́ch programů.
$ ls datata >/dev/null
ls: datata: No such file or directory
$ echo $?
1
$ ls data >/dev/null
$ echo $?
0

V prvnı́m přı́padě došlo k chybě, protože adresář datata neexistoval. Návratová hodnota přı́kazu ls byla 1. V druhém přı́padě byl přı́kaz úspěšný a návratová
hodnota je 0.
Proměnnou $! lze s výhodou použı́t napřı́klad k ukončenı́ dlouho běžı́cı́ho procesu. Předpokládejme, že uživatel chce spustit dlouho běžı́cı́ proces, ale nechce, aby
běžel déle než 2 hodiny. Uživatel chce zajistit, aby byl proces automaticky ukončen,
pokud překročı́ maximálnı́ stanovenou dobu svého běhu.

110

Kapitola 5. Základy přı́kazového interpretu
$ ~/data/archivuj & echo $! >~/.running.pid
[1] 1239
$ (sleep 7200; kill -9 ‘cat ~/.running.pid‘) &
[2] 1240
· · · po dvou hodinách · · ·
[1]- Killed
~/data/archivuj
[2]+ Done
( sleep 7200; kill -9 ‘cat ~/.running.pid‘)

Přı́kazy na prvnı́m řádku nejprve spustily program archivuj na pozadı́, bezprostředně potom byl zapsán jeho PID do souboru ~/.running.pid. Jako dalšı́
byl spuštěn na pozadı́ složený přı́kaz, který nejprve pozdržı́ své vykonávánı́ na dvě
hodiny a následně ukončı́ běh procesu, jehož PID vyzvedne ze souboru pomocı́
substituce přı́kazu cat. Výše uvedené řešenı́ je pro Unix typické. Problém terminovaného ukončenı́ procesu byl rychle vyřešen několika jednoduchými programy.
Uvažte, jak těžké by bylo řešenı́ podobného problému v jiných operačnı́ch systémech.

Oddělovače podmı́něného vykonávánı́ přı́kazů
O návratovou hodnotu procesu se opı́rajı́ dalšı́ dva oddělovače přı́kazů. Metaznaky
„&&“ a „||“ sloužı́ k jednoduchému podmı́něnému provedenı́ přı́kazu. Oba majı́
shodnou syntaxi:
/přı́kaz1 . && /přı́kaz2 .
/přı́kaz1 . || /přı́kaz2 .
V obou přı́padech je nejprve proveden /přı́kaz1 .. Provedenı́ přı́kazu / přı́kaz2 . je
podmı́něno návratovou hodnotou prvnı́ho přı́kazu. Je-li použit oddělovač „&&“,
druhý přı́kaz je vykonán, pokud je návratová hodnota prvnı́ho přı́kazu rovna 0. Je-li použit oddělovač „||“, druhý přı́kaz je vykonán, pokud je návratová hodnota
prvnı́ho přı́kazu nenulová.
Oddělovač „&&“ se chová jako logický součin, oddělovač „||“ se chová jako
logický součet. Čtenáře by nemělo poplést, že úspěch je značen poněkud nezvykle
čı́slem 0 a neúspěch nenulovými hodnotami. Toto značenı́ má opět opodstatněnı́.
V přı́padě, že program skončı́ korektně, nenı́ potřeba zjišt’ovat „v jakém korektnı́m
stavu skončil“. V opačném přı́padě je chybu dobré lokalizovat, program má možnost
na každou výjimečnou situaci použı́t jinou návratovou hodnotu.
V systému existujı́ dva programy s předem definovanou návratovou hodnotou,
false a true. Program false končı́ vždy s chybou čı́slo 1, program true je vždy
úspěšný a jeho návratová hodnota je 0. Program false se tedy chová neutrálně
k oddělovači „||“, na druhou stranu program true se chová neutrálně k oddělovači „&&“. Rozdı́lnost obou oddělovačů demonstruje přiložený přı́klad.
$ cd datata && pwd
bash: cd: datata: No such file or directory
$ cd datata || pwd
bash: cd: datata: No such file or directory
/home/vilem/tmp/novakj

5.4.

Proměnné

111

Oddělovačů „&&“ a „||“ lze uvést v přı́kazu samozřejmě vı́c, jednotlivé přı́kazy
jsou potom podmı́něně vyhodnocovány zleva doprava.

Často použı́vané proměnné
Na závěr kapitoly o proměnných je uveden soupis nejčastěji použı́vaných proměnných. Nı́že uvedené proměnné majı́ v shellu zvláštnı́ význam nebo ovlivňujı́
chovánı́ spouštěných programů. Výpis aktuálně definovaných proměnných a jejich
hodnot je možné zı́skat přı́kazem set spuštěným bez argumentu.
Seznam adresářů oddělených dvojtečkami, v nichž shell zkoušı́
hledat adresáře, pokud selže přı́kaz cd. Tı́mto způsobem se lze
přesouvat mezi adresáři pouze pomocı́ uvedenı́ jejich částečných
jmen.
EDITOR
Implicitnı́ textový editor.
HISTFILE
Název souboru s historiı́ přı́kazů shellu. Implicitnı́ hodnotou je
jméno souboru ~/.bash_history.
HISTFILESIZE Počet řádků historie uložené na disku.
HISTSIZE
Počet řádků historie, kterou si shell udržuje v paměti.
HOME
Absolutnı́ cesta k domovskému adresáři uživatele.
HOSTNAME
Jméno hostitelského počı́tače.
HOSTTYPE
Architektura počı́tače, třeba i386, alpha a podobně.
LC_ALL
Specifikuje národnı́ prostředı́. Proměnná může mı́t napřı́klad hodnotu cs_CZ.ISO-8859-2. To znamená, že je nastaveno české národnı́ prostředı́ a je použı́váno standardnı́ kódovánı́ pro centrálnı́
Evropu – ISO Latin 2. Nastavenı́ této proměnné překrývá ostatnı́
proměnné s názvy LC_/ kategorie.. Pomocı́ lokalizačnı́ch proměnných je možné nastavit jazykové mutace systému a přizpůsobit jej
lokálnı́m zvyklostem. Sem patřı́ napřı́klad styl výpisu času, data
a podobně. Pro podrobnosti viz kapitolu 6.5.
MAIL
Absolutnı́ cesta k souboru s uživatelskou poštou, soubor bývá obvykle umı́stěn v adresáři /var/spool/mail a má jméno shodné
s uživatelským jménem.
MAILCHECK
Shell periodicky kontroluje novou přı́chozı́ poštu. Pomocı́ proměnné MAILCHECK lze nastavit časovou periodu kontroly, časové
jednotky jsou sekundy.
MAILPATH
Proměnná obsahuje seznam souborů, které jsou shellem testovány
na přı́chozı́ poštu. Proměnná může obsahovat seznam souborů oddělených dvojtečkami.
OSTYPE
Typ operačnı́ho systému, napřı́klad linux-gnu.
PAGER
Proměnná obsahuje název programu, jenž je použı́ván pro stránkovánı́ výpisů přesahujı́cı́ch počet řádků na terminálu. Pokud nenı́
CDPATH

112

Kapitola 5. Základy přı́kazového interpretu
proměnná nastavena, je použit implicitnı́ stránkovač pager, což je
obvykle symbolický odkaz napřı́klad na program more.

PATH

Prohledávacı́ cesta. Jednotlivé cesty jsou odděleny dvojtečkami.
Standardně je cesta nastavena alespoň do adresářů /usr/bin,
/bin, /usr/bin/X11 a /usr/local/bin.

PWD

Pracovnı́ adresář.

RUNLEVEL

Čı́slo runlevelu, v němž se systém nacházı́.

RANDOM

Proměnná generujı́cı́ pseudonáhodná čı́sla. Proměnná sice nenı́
pouze pro čtenı́, ale použitı́ přı́kazu přiřazenı́ nemá v jejı́m přı́padě
smysl. Při každé dereferenci je vráceno vygenerované pseudonáhodné čı́slo.

SHLVL

Čı́slo označujı́cı́ úroveň vnořenı́ shellu. Po přihlášenı́ do systému je
úroveň 1. Každý nový shell hodnotu SHLVL inkrementuje.

TERM

Nastavenı́ emulace terminálu. S hodnotou vt100 by měla většina
terminálů fungovat dobře.

UID

Identifikačnı́ čı́slo uživatele.

USER

Uživatelské jméno.

Proměnné tvaru PS/n . si zasloužı́ delšı́ komentář. Jedná se o proměnné definujı́cı́
tvar n-árnı́ho promptu, n nabývá hodnot 1, 2, 3 a 4. Tvar primárnı́ho promptu je uložen
v proměnné PS1. Primárnı́m promptem shell ohlašuje, že čeká na vstup. Ve všech
předchozı́ch ukázkách byla hodnota primárnı́ho promptu nastavena na „$ “. Tvar
sekundárnı́ho promptu je uložen v proměnné PS2, obvykle má tvar „> “. Sekundárnı́m
promptem shell oznamuje, že čeká na dokončenı́ přı́kazu. Viz přı́klad.
$ echo ’tento text
> dokoncim az zde’
tento text
dokoncim az zde

ENTER

Jelikož byl na prvnı́m řádku uveden pouze jeden znak apostrof, shell vyžaduje
dokončenı́ přı́kazu. Sekundárnı́m promptem uživateli oznamuje, že musı́ dokončit
přı́kaz nebo přerušit jeho zadávánı́ stiskem C-c. Rozdělenı́ přı́kazů na vı́ce řádků je
někdy vhodné z důvodu přehledného zápisu. Pokud při psanı́ přı́kazu uvedeme na
konci řádku metaznak „\“ a stiskneme ENTER , shell opět zobrazı́ sekundárnı́ prompt
a bude čekat na dokončenı́ přı́kazu. Uved’me přı́klad analogický předchozı́mu.
$ echo tento text \ ENTER
> dokoncim az zde
tento text dokoncim az zde

V tomto přı́padě nebyl stisk klávesy ENTER chápán jako přechod na nový řádek.
Výsledný text byl proto zobrazen na jednom řádku.

5.5.

Řı́dı́cı́ struktury a zabudovaná aritmetika

113

Prompt PS3 zobrazuje přı́kaz select, když po uživateli požaduje výběr z několika
možnostı́. Přı́kaz select sloužı́ v shellu ke zprostředkovánı́ jednoduchých menu. Implicitnı́ tvar promptu je „#?“. Prompt PS4 je určen pro výpis ladicı́ch informacı́. Pokud
je shell spuštěn s parametrem -x, je zapnut v ladicı́m režimu. Každý spuštěný přı́kaz
je před spuštěnı́m zobrazen ve své expandované podobě a je uvozen promptem PS4.
Implicitnı́ hodnota je „+“.
Při definici tvaru shellu lze použı́t speciálnı́ sekvence expandovatelné shellem.
Následujı́cı́ tabulka obsahuje souhrn nejpoužı́vanějšı́ch sekvencı́.
sekvence

význam

\h
\H
\t
\u
\w
\W
\!
\$

jméno počı́tače
úplné jméno počı́tače včetně domény
systémový čas ve formátu HH:MM:SS
uživatelské jméno
cesta k pracovnı́mu adresáři
název pracovnı́ho adresáře
čı́slo aktuálnı́ho přı́kazu v historii
pokud je efektivnı́ UID rovno 0, pak je symbol #, jinak $

Následujı́cı́ přı́klad ukazuje nastavenı́ přehledných primárnı́ch promptů.
$ PS1=’[\u@\h \W]\$ ’
[novakj@phoenix novakj]$ PS1=’\h:\w\$ ’
phoenix:~$ PS1=’\u\$ ’
novakj$

Uživatel by při volbě svého promptu měl vycházet z několika skutečnostı́. Je dobré
mı́t vždy přehled, na kterém počı́tači je uživatel přihlášen. Součástı́ promptu by mělo
být minimálně hostitelské jméno počı́tače. Pokud uživatel vlastnı́ vı́c účtů, je rovněž
vhodné připojit informaci o přihlášeném uživateli. Třetı́ důležitou informacı́ je informace o pracovnı́m adresáři. Délka absolutnı́ cesty k adresáři však může být dlouhá,
prompt by měl zabı́rat jen nezbytně nutnou část řádku. Rozumným kompromisem
je zobrazenı́ pouze jména pracovnı́ho adresáře mı́sto jeho plné cesty.

5.5. Řı́dı́cı́ struktury a zabudovaná aritmetika
Shell je plnohodnotný programovacı́ jazyk zahrnujı́cı́ standardnı́ přı́kazy cyklu
a podmı́něné přı́kazy. V obou přı́padech je nutné pracovat s pravdivostnı́mi hodnotami. U cyklu musı́ být dána limitnı́ podmı́nka, po jejı́mž dosaženı́ se cyklus ukončı́.
Podmı́něný přı́kaz potřebuje pravdivostnı́ hodnotu k rozhodnutı́ o dalšı́m prováděném přı́kazu.
Každý spuštěný program vracı́ celočı́selnou hodnotu. Návratová hodnota má
mimo jiné význam pravdivostnı́ hodnoty. Shell má navı́c k dispozici jednoduché relačnı́ predikáty a logické spojky, pomocı́ nichž lze vytvářet složitějšı́ logické výrazy.
V předchozı́ kapitole byly představeny oddělovače „&&“ a „||“ vykazujı́cı́ stejné

114

Kapitola 5. Základy přı́kazového interpretu

chovánı́ jako logická konjunkce a disjunkce. V shellu je rovněž zabudovaný unárnı́
oddělovač „!“ reprezentujı́cı́ negaci. Jeho syntaxe je ! / výraz.. Je-li návratová hodnota výrazu nulová, jejı́ negacı́ je 1. Je-li návratová hodnota nenulová, jejı́ negacı́ je 0.
Pro spojovánı́ logických hodnot jsou v shellu k dispozici tři logické spojky, „&&“,
„||“ a „!“.

Vytvářenı́ podmı́nek
Ke klasifikaci typu souboru a k porovnávánı́ hodnot sloužı́ program test. V systému zpravidla existuje pevný odkaz /usr/bin/[ ukazujı́cı́ na program test. Při
psanı́ výrazů se častěji použı́vá jméno [. Program test umožňuje porovnávat dvě
řetězcové hodnoty, dvě celočı́selné hodnoty a porovnávat vzájemné stářı́ souborů.
Obecné tvary volánı́ programu jsou:
test /výraz.
[ /výraz. ]
V druhém přı́padě je vyžadována i ukončovacı́ hranatá závorka, ta je programu
předávána jako poslednı́ argument. Hranaté závorky ale nejsou metaznaky, použitı́m
přı́kazu v druhém tvaru uživatel zadává přı́kaz pro spuštěnı́ programu. Z tohoto
důvodu je nutné / výraz. oddělit mezerami z obou stran. V následujı́cı́ tabulce jsou
shrnuty základnı́ predikáty sloužı́cı́ k porovnávánı́ hodnot řetězců.
výraz

význam

/str.
-z / str.
/str1 . = /str2 .
/str1 . != /str2 .

délka řetězce / str. je nenulová
délka řetězce / str. je nulová
řetězce /str1 . a /str2 . jsou shodné
řetězce /str1 . a /str2 . jsou různé

Pomocı́ programu test lze porovnávat i celočı́selné hodnoty. Shell sice pracuje
pouze z řetězcovými proměnnými, ale může jejich obsah interpretovat jako čı́slo.
výraz

význam

/n1 . -eq /n2 .
/ n1 . -le / n2 .
/ n1 . -lt / n2 .
/ n1 . -ge / n2 .
/ n1 . -gt / n2 .
/ n1 . -ne / n2 .

řetězce jsou shodné
/n .1 je menšı́ nebo rovno / n2 .
/n .1 je menšı́ než /n2 .
/n .1 je většı́ nebo rovno / n2 .
/n .1 je většı́ než / n2 .
řetězce jsou různé

Při použitı́ programu test je možné využı́t již popsaných vlastnostı́ shellu,
zejména expanze a substituce programu. Rovněž je možné skládat složitějšı́ výrazy
z jednoduššı́ch použitı́m logických spojek. Viz přı́klad.

5.5.

Řı́dı́cı́ struktury a zabudovaná aritmetika

115

$ [ ‘pwd‘ ]; echo $?
0
$ [ ‘pwd‘ = $PWD ]; echo $?
0
$ [ ‘pwd‘ != $HOME ]; echo $?
0
$ [ ~ != $HOME ]; echo $?
1

Každý řádek představuje použitı́ programu test a vytištěnı́ jeho návratové hodnoty. V prvnı́m přı́padě byl jako argument dosazen pracovnı́ adresář vzniklý substitucı́ přı́kazu. Řetězec je neprázdný, proto je výraz pravdivý. V druhém přı́padě je
výsledek rovněž pravdivý, protože substituce přı́kazu pwd byla v ukázce porovnána
s obsahem proměnné PWD, to jest obě strany rovnosti byly identické. Jelikož je v třetı́m
přı́padě výraz opět pravdivý, uživatelův pracovnı́ adresář nemohl být nastaven na
domovský adresář. V poslednı́ ukázce je výsledek nenulový – vlnka je expandována
na cestu k domovskému adresář, proměnná HOME se dereferencuje na týž řetězec.
Jelikož byl použit predikát „!=“, výraz je nepravdivý.
Při porovnávánı́ čı́sel se použı́vá obdobný způsob zápisu. Následujı́cı́ přı́klad
ponecháme bez komentáře.
$ [ 99 -lt 100 ]; echo $?
0
$ [ 999 -lt 100 ]; echo $?
1

Program test sloužı́ rovněž k testovánı́ typů souborů a jejich stářı́. K testovánı́
typu se použı́vajı́ unárnı́ predikáty, porovnávánı́ stářı́ souborů má stejnou syntaxi
jako porovnávánı́ čı́sel.
výraz

význam

/ f1 . -ef / f2 .
/ f1 . -nt / f2 .
/ f1 . -ot / f2 .
-e /f.
-d /f.
-f /f.
-L /f.
-r /f.
-s /f.
-w /f.
-x /f.

oba soubory sdı́lejı́ stejný i-uzel
soubor / f1 . je novějšı́ než soubor /f2 .
soubor / f1 . je staršı́ než soubor / f2 .
soubor / f. existuje
soubor / f. je adresář
soubor / f. je obyčejný soubor
soubor / f. je symbolický odkaz
soubor / f. je čitelný
soubor / f. je neprázdný
soubor / f. je zapisovatelný
soubor / f. je spustitelný

Následujı́cı́ přı́klad ukazuje jednoduché testovánı́ vlastnostı́ souborů. Prvnı́ přı́klad ukazuje, že programy test a [ jsou skutečně svázány pevným odkazem, sdı́lejı́
totiž stejný i-uzel.

116

Kapitola 5. Základy přı́kazového interpretu
$ [ /usr/bin/test -ef /usr/bin/\[ ]; echo $?
0
$ [ -d ~/data ]; echo $?
0
$ [ -L ~/data ]; echo $?
1
$ >novy; [ -f novy ] && [ novy -nt ~/data ]; echo $?
0

V druhém a třetı́m přı́padě byl testován adresář ~/data, v třetı́m přı́padě byl výraz nepravdivý, protože ~/data nenı́ symbolický odkaz. Jako poslednı́ byl vytvořen
nový soubor novy, jehož stářı́ bylo porovnáno s adresářem ~/data. Na přı́kladu je
vidět složenı́ podmı́nky pomocı́ „&&“.
Při použitı́ predikátů -nt, -ot je někdy vhodné účelově změnit čas modifikace
souboru. Pokud chce uživatel aktualizovat čas souboru, aniž by byl měněn jeho obsah,
lze k tomu použı́t program touch /soubor.. Je-li program použit bez dodatečných
argumentů, změnı́ informaci o modifikaci souboru na aktuálnı́ čas. Při použı́vánı́
programu touch je dobré dbát obezřetnosti, aby nedocházelo k nežádoucı́m časovým
posunům – některé programy by mohly začı́t vykazovat zvláštnı́ch chovánı́.

Podmı́něné přı́kazy
Základnı́ řı́dı́cı́ konstrukce shellu lze rozdělit do dvou skupin. Prvnı́ skupinu
tvořı́ podmı́něný přı́kaz. Podmı́něný přı́kaz sloužı́ k podmı́něnému vykonánı́ dalšı́ch
přı́kazů. Mezi základnı́ podmı́něné přı́kazy patřı́ konstrukce
if · · · then · · · else.
Jejı́ syntaxe je v shellu následujı́cı́:
if / výraz.; then / přı́kazy.; fi
if / výraz.; then / přı́kazy.; else / alternativa.; fi
if / výraz.; then / přı́kazy.; / podmı́nky. /alternativa.; fi
kde /podmı́nky. jsou libovolná posloupnost alternativnı́ch podmı́nek tvaru
elif /výraz.; then / přı́kazy.; · · ·
Přı́kaz if lze použı́vat ve třech variantách. V prvnı́m přı́padě je vyhodnocen / výraz.,
a je-li pravdivý, jsou provedeny /přı́kazy.. Po jejich dokončenı́ pokračuje shell dalšı́m
přı́kazem v řadě. Druhá varianta konstrukce if přidává alternativnı́ větev, přı́kazy
v alternativnı́ větvi jsou provedeny, právě když je / výraz. nepravdivý. Třetı́ přı́pad
použitı́ je nejkomplikovanějšı́. Mezi přı́kazy a alternativnı́ větev se vsouvá seznam
dodatečných podmı́nek a přı́kazů. Shell vyhodnocuje postupně podmı́nky, a když narazı́
na pravdivý / výraz., provede adekvátnı́ /přı́kazy.. Po dokončenı́ všech přı́kazů
je vykonávánı́ podmı́něného výrazu ukončeno. V přı́padě, že nenı́ pravdivý ani jeden
/výraz. a podmı́něný výraz obsahuje alternativnı́ větev, tato větev bude vykonána.
Nenı́-li alternativnı́ větev přı́tomna, vykonávánı́ podmı́něného výrazu je ukončeno.
Výsledná hodnota přı́kazu if záležı́ na vyhodnocenı́ poslednı́ho přı́kazu v aktivnı́
větvi. Následujı́cı́ přı́klad ukazuje větvenı́ programu.

5.5.

Řı́dı́cı́ struktury a zabudovaná aritmetika

117

$ if [ -d ~/data ]; then echo je to adresar; fi
je to adresar
$ if [ -L ~/data ]; then
>
echo je to odkaz;
> else
>
echo neni to odkaz;
> fi
neni to odkaz

V prvnı́m přı́padě byl testován adresář, v druhém přı́padě odkaz. Zápis podmı́něného výrazu může být delšı́, proto je dobré rozdělit jej na několik řádků. V tomto
přı́padě shell opět indikuje sekundárnı́m promptem „>“ nutnost dokončenı́ přı́kazu.
Druhým významným podmı́něným přı́kazem je case. Přı́kaz case umožňuje
vykonat přı́kazy podmı́něné shodou vstupnı́ho slova s požadovanými vzory. Při porovnávánı́ vzorů se použı́vajı́ naprosto stejná pravidla jako při expanzi neúplného názvu
souboru. Přı́kaz case má syntaxi
case / slovo. in /větve. esac
kde / větve. tvořı́ neprázdnou posloupnost tvaru
/ vzory.) / přı́kazy.;; · · ·
a / vzory. reprezentujı́ seznam možných vzorů oddělených metaznakem „|“.
Při vyhodnocenı́ přı́kazu case se nejprve vyhodnotı́ argument /slovo.. Dále jsou
testovány všechny větve a / slovo. se porovnává s jednotlivými vzory. Odpovı́dá-li
v dané větvi alespoň jeden vzor, jsou vykonány / přı́kazy. a poté je tělo přı́kazu opuštěno a shell pokračuje dalšı́m přı́kazem. Jelikož se porovnává slovo se vzorem, nenı́
problém uměle vytvořit alternativnı́ větev pomocı́ vzoru *), jemuž odpovı́dá libovolné
slovo. Alternativnı́ podmı́nka však musı́ být uvedena jako poslednı́, všechny větve
uvedené za vzorem *) by byly nedosažitelné. Použitı́ přı́kazu case demonstruje
přı́klad.
$ SLOVO=tucnak
$ case $SLOVO in
>
ahoj|svete) echo cast pozdravu;;
>
t*) echo slovo zacina na \’t\’;;
>
*) echo cokoliv jineho;;
> esac
slovo zacina na ’t’

Vstupnı́ slovo tucnak se shoduje s druhým vzorem t*. Oba podmı́něné přı́kazy
if i case jsou ukončeny obráceným klı́čovým slovem, to jest fi a esac.

Přı́kazy cyklu
Přı́kazy cyklu sloužı́ k iterativnı́mu zpracovánı́ posloupnosti přı́kazů. Iterace je
zpravidla zastavena, je-li dosaženo limitnı́ podmı́nky. Shell umožňuje psát i cykly bez

118

Kapitola 5. Základy přı́kazového interpretu

limitnı́ podmı́nky, jejich využitı́ ale nenı́ tak široké – hodı́ se pro cyklickou obsluhu
nebo neustálé zpracovánı́ dat. V shellu jsou k dispozici přı́kazy for, while a until.
Přı́kaz for sloužı́ k iteraci přes množinu, dalšı́ dva přı́kazy sloužı́ k iteraci limitované
podmı́nkou. Přı́kazy majı́ následujı́cı́ syntaxi:
for / proměnná. in / seznam.; do / přı́kazy.; done
while / výraz.; do / přı́kazy.; done
until / výraz.; do / přı́kazy.; done
Nejdřı́v rozebereme přı́kaz for. Jako prvnı́ se expanduje /seznam.. Přı́kaz for s expandovaným seznamem zacházı́ podobným způsobem jako shell s argumenty přı́kazu, jednotlivé hodnoty jsou odděleny metaznakem mezera. Pro každý prvek ze
seznamu / seznam. je provedeno tělo cyklu, to jest /přı́kazy.. Pokud je / seznam.
prázdný, tělo nikdy neproběhne. Vnitřnı́ přı́kazy se mohou odkazovat na aktuálnı́ hodnotu, pro kterou je aktuálnı́ fáze iterace prováděna. K tomuto účelu sloužı́
/proměnná.. Před vykonávánı́m přı́kazů cyklu je vždy /proměnná. nastavena na
hodnotu prvnı́ho prvku ze seznamu. Při dalšı́m průchodu je proměnná navázána na
následujı́cı́ hodnotu.
Při volbě jména proměnné je dobré mı́t na paměti, že přı́kaz for probı́há v aktuálnı́m shellu. Z hlediska rozsahu platnosti jsou v shellu všechny proměnné globálnı́. Při
započetı́ průchodu cyklem bude na proměnnou navázána hodnota a jejı́ původnı́
obsah bude ztracen. Proměnná bude po dokončenı́ cyklu obsahovat hodnotu poslednı́ho prvku ze seznamu. Pro proměnné v cyklu je vhodné volit jméno skládajı́cı́ se
z malých pı́smen, většina proměnných shellu se skládá z velkých pı́smen, proto s největšı́ pravděpodobnostı́ nedojde ke ztrátě žádné hodnoty. Základnı́ chovánı́ přı́kazu
demonstruje jednoduchý přı́klad.
$ for i in 1 2 3; do echo aktualni cislo: $i; done
aktualni cislo: 1
aktualni cislo: 2
aktualni cislo: 3

V této ukázce seznam hodnot sestává ze třı́ čı́sel. V těle cyklu je prováděn přı́kaz
spouštějı́cı́ program echo. Při každém průchodu cyklem byla proměnná i dereferencována pomocı́ metaznaku „$“. Cykly lze samozřejmě vnořovat. V takovém přı́padě
je nutné, aby všechny proměnné použité v cyklech byly navzájem různé. Obzvlášt’
výhodné je kombinovat cykly s podmı́něnými přı́kazy.
Pro ilustraci je uveden přı́klad, ve kterém jsou postupně testována čı́sla ze souboru. Během cyklu se iteruje přes hodnoty uložené v souboru, to lze zajistit substitucı́
přı́kazu cat. Každé čı́slo je otestováno na prvočı́selnost, k tomu byl použit program
calc a jeho vnitřnı́ funkce isprime(). Funkce isprime() vypı́še na výstup 1
v přı́padě úspěchu, 0 v přı́padě neúspěchu. Nejedná se však o návratovou hodnotu,
ale o výstup. Pomocı́ přı́kazu if je výstup porovnán s čı́slem 0 a program vypı́še
informace, zdali je zkoumané čı́slo prvočı́slem.
$ for i in ‘cat cisla.txt‘; do
>
RESULT=‘echo ”isprime ($i)” | calc‘;

5.5.

Řı́dı́cı́ struktury a zabudovaná aritmetika

119

>
if [ $RESULT -gt 0 ]; then
>
echo $i je prvocislo;
>
fi;
> done
2 je prvocislo
3 je prvocislo
5 je prvocislo
7 je prvocislo

Použitı́ shellovského přı́kazu při řešenı́ „matematické úlohy“ nenı́ přı́liš typické,
i když je to možné. Výsledný kód však bude výrazně pomalejšı́, než kdyby jej autor
napsal napřı́klad v jazyku C. Cı́lem předcházejı́cı́ho přı́kladu však bylo ukázat možný
způsob využitı́ cyklu v kombinaci s dalšı́mi obslužnými programy.
V předchozı́m přı́kladu byla uprostřed bloku použita dalšı́ proměnná jménem
RESULT. Platı́ pro ni stejná poučka jako pro proměnnou uvedenou za klı́čovým
slovem for. Jejı́ hodnota bude zachována i po opuštěnı́ cyklu. Toto pravidlo platı́
i pro proměnné definované uprostřed přı́kazů v podmı́něných výrazech. Hodnota
proměnné RESULT může být samozřejmě změněna přı́kazem přiřazenı́.
Dalšı́m zajı́mavým a typickým použitı́m přı́kazu for je napřı́klad hromadné
přejmenovánı́ souborů. Uvažujme napřı́klad soubory zakončené -YYMM, kde YY reprezentuje dvojciferné označenı́ roku a MM dvojciferné označenı́ měsı́ce. Jelikož je
dvojciferné čı́slovánı́ roku neprozı́ravé, můžeme se rozhodnou všechny soubory přejmenovat do tvaru zakončeného -YYYYMM. To jest budeme chtı́t označovat údaj o roku
čtyřciferným čı́slem. Problém lze vyřešit napřı́klad takto:
$ for i in *-[0-9][0-9][01][0-9]; do
>
NEWNAME=‘echo $i | sed ’s/-\([^-]*\)$/-19\1/’‘;
>
mv $i $NEWNAME;
> done

Ačkoliv vypadá druhý řádek přı́kazu poněkud bizarně, ve skutečnosti je mnohem méně imponujı́cı́, než jak na prvnı́ pohled vypadá. Jedná se o substituci pomocı́
regulárnı́ho výrazu. Zjednodušeně řečeno, pomocı́ volánı́ programu sed bylo mezi
poslednı́ pomlčku v názvu každého souboru vložené dvojčı́slı́ 19. Bližšı́ popis regulárnı́ch výrazů a programu sed je k nalezenı́ v kapitole 6.2. Ačkoliv předchozı́ přı́klad
vypadá komplikovaně, jeho vytvořenı́ autorovi zabralo necelou minutu i s otestovánı́m funkčnosti. Zvažte, jak dlouho by vyřešenı́ podobného problému trvalo v jiných
systémech.
Přı́kazy cyklu while a until fungujı́ analogicky. Odlišné jsou pouze v chápánı́
limitnı́ podmı́nky cyklu. Na začátku přı́kazu while je testována limitnı́ podmı́nka,
kterou reprezentuje /výraz.. Je-li /výraz. pravdivý, jsou vykonány přı́kazy a iterace
se opakuje. Opět je testována limitnı́ podmı́nka a tak dále. Pokud je /výraz. vždy
pravdivý, přı́kaz může uvı́znout v nekonečném cyklu. K okamžitému opuštěnı́ cyklu
sloužı́ přı́kaz break. Pomocı́ přı́kazu continue lze přeskočit zbytek těla cyklu
a pokračovat dalšı́ iteracı́. Přı́kaz until se lišı́ od přı́kazu while pouze v interpretaci
limitnı́ podmı́nky. Tělo cyklu until je vykonáváno, dokud je /výraz. nepravdivý.

120

Kapitola 5. Základy přı́kazového interpretu

Použitı́ přı́kazu while demonstruje přı́klad.
$ ~/data/archivuj & echo $! >~/.running.pid
[1] 9221
$ while kill -SIGCONT ‘cat ~/.running.pid‘ &>/dev/null; do
>
echo ’proces stale bezi’ | mail novakj@phoenix.inf.upol.cz;
>
sleep 600;
> done &
[1] 9222

V přı́kladu byl nejprve spuštěn proces archivuj, jehož PID byl uložen do souboru na disk. Cyklus while byl rovněž spuštěn na pozadı́. Cyklus probı́há, dokud
proces archivuj běžı́. Existence procesu je testována zası́lánı́m signálu SIGCONT.
Tento signál nezpůsobı́ přerušenı́ běhu programu. Na druhou stranu, pokud by již
proces neběžel, program kill skončı́ neúspěchem a celý cyklus se zastavı́. V těle
cyklu je nejprve zaslán dopis uživateli pomocı́ obslužného programu mail, který
oznamuje, že proces pořád běžı́. Na dalšı́m řádku je proces pozdržen o deset minut.
Tento přı́klad opět ukazuje jednoduchý problém jednoduše vyřešený pomocı́ shellu.

Zabudovaná aritmetika
V předchozı́ch programech byl pro výpočet jednoduchých aritmetických výrazů
použit program calc. Jedná se o poměrně mocný program umožňujı́cı́ provádět výpočty se stanovenou přesnostı́. Nenı́ vázaný na implementaci datových typů zabudovanou v procesoru. Pro jednoduššı́ výpočty lze využı́t vyhodnocovánı́ aritmetických
výrazů zabudované v shellu. Shell podporuje pouze celočı́selnou aritmetiku, k dispozici jsou základnı́ aritmetické operace, operace pro bitové posuvy, logické a bitové
operace a ternárnı́ podmı́něný operátor. Syntaxe operacı́ je převzata z jazyka C.
Každý aritmetický výraz v shellu má syntaxi $[/výraz.], kde /výraz. může být
složen z konstant, dereferencı́ a přı́pustných operacı́. Pokud je /výraz. syntakticky
správný, je vyhodnocen a výsledek je předán na výstup. Dalšı́ přı́kaz umožňujı́cı́ vyhodnotit aritmetický výraz je let. Přı́kaz let však na výstup nevypisuje výslednou
hodnotu. Vypočtenou hodnotu je možné přiřadit proměnné pomocı́ přiřazovacı́ho
přı́kazu. Viz přı́klad.
$ N=12345
$ N=$[$N*2]
$ M=12345
$ let M*=2

Druhý tvar zápisu je kratšı́, je v něm použit operátor přiřazenı́ násobku „*=“. Stejného efektu by bylo dosaženo použitı́m přı́kazu let M=$M*2. Prvnı́ tvar je vhodné
použı́vat v přı́padě, kdy je potřeba vytisknout pouze výsledek výrazu, ale nenı́ potřeba měnit obsah žádné proměnné. Soupis všech operacı́ včetně jejich priorit a popisu lze najı́t v zabudované nápovědě shellu, pro detaily viz nápovědu zobrazenou
přı́kazem help let.

5.6.

Vytvářenı́ skriptů

121

5.6. Vytvářenı́ skriptů
Při vytvářenı́ složitějšı́ch přı́kazů v shellu uživatel dřı́ve či později narazı́ na potřebu uchovat je pro dalšı́ použitı́. I při psanı́ přı́kazů řešı́cı́ch jednorázové problémy
může být výhodné uložit je na disk a dále je použı́vat jednoduchým způsobem. Mı́sto
opakovaného vypisovánı́ přı́kazů může dát uživatel shellu pokyn k vykonánı́ přı́kazů uložených v externı́m souboru. Přı́kazy pro shell mohou být uloženy bud’to ve
spustitelném souboru, nebo souboru bez práva spouštěnı́. Zahájenı́ vykonávánı́ přı́kazů
uložených v souboru se v těchto dvou přı́padech lišı́.
V předchozı́ch kapitolách byl uveden základnı́ přı́kaz pro spuštěnı́ programu.
Pod pojmem program byl doposud uvažován soubor obsahujı́cı́ instrukce pro procesor. Soubor s instrukcemi pro procesor je na prvnı́ pohled nečitelný a zpravidla je
vytvořen překladem ze zdrojových kódů ve vyššı́m programovacı́m jazyku, napřı́klad
v jazyku C. Naproti tomu soubor obsahujı́cı́ přı́kazy pro shell je dobře čitelný. Jedná
se o textový souboru obsahujı́cı́ přı́kazy ve stejné podobě, jako jsou zadávány přı́mo
v přı́kazovém řádku shellu. Spustitelné soubory tedy dělı́me do dvou skupin – programy a skripty.
Skripty jsou obyčejné soubory obsahujı́cı́ přı́kazy pro shell. Pojem skript nenı́ těsně
vázaný jen k shellu. V prostředı́ Unixu se obecně mluvı́ o skriptech jako o souborech
obsahujı́cı́ch přı́kazy interpretované jiným programem. Nejčastěji však shellem. Jelikož mohou být skripty interpretovány různými programy, dělı́ se jejich obsah na dvě
části – hlavičku a tělo. Hlavička skriptu je nepovinná, lze pomocı́ nı́ deklarovat program, jenž bude skript interpretovat. Nenı́-li hlavička uvedena, skript je implicitně
interpretován aktuálnı́m shellem. Tělo skriptu obsahuje vlastnı́ přı́kazy.
Má-li skript nastavené právo spouštěnı́, uživatel jej může spustit stejným způsobem jako program. To jest, ležı́-li skript v adresáři, na nějž je nastavena prohledávacı́
cesta, stačı́ uvést jméno skriptu. Nenacházı́-li se skript v prohledávacı́ cestě, je nutné
odkázat se na něj pomocı́ relativnı́ nebo absolutnı́ cesty. Při požadavku na spuštěnı́
souboru shell nejprve analyzuje, zdali se jedná o program nebo skript. Pokud je soubor skript, shell analyzuje jeho hlavičku a najde přı́slušný interpret skriptu. Poté je
vytvořen nový proces – interpret a skript je mu předán jako vstupnı́ argument. Nenı́-li
hlavička uvedena, skript je interpretován vnořeným shellem.
Hlavička skriptu má tvar
#!/ interpret. /argumenty.
kde /interpret. je absolutnı́ cesta k interpretu skriptu. Metaznak hash „#“ má v shellu
speciálnı́ význam. Jedná se o metaznak oddělujı́cı́ komentář. Narazı́-li shell při interpretaci přı́kazu na metaznak „#“, zbytek řádku ignoruje a pokračuje zpracovánı́m
dalšı́ho řádku. Je-li na prvnı́m řádku skriptu dvojice „#!“ těsně následovaná absolutnı́ cestou k interpretu, jedná se o hlavičku skriptu. Za cestou k interpretu mohou
být uvedeny i argumenty, se kterými má být interpret spuštěn.
Proč musı́ být pro identifikaci interpretu uvedena absolutnı́ cesta? Odpověd’ na
tuto otázku může být poněkud překvapujı́cı́. Pojmy relativnı́ cesta a prohledávacı́ cesta
jsou těsně vázány k shellu. Bez existence shellu nemajı́ význam. Prohledávacı́ cesta

122

Kapitola 5. Základy přı́kazového interpretu

i pracovnı́ adresář jsou v shellu reprezentovány pouze dvěma proměnnými – PATH
a PWD. Na druhou stranu, absolutnı́ cesta je pojem nezávislý na shellu, jejı́ existence vyplývá z architektury souborového systému. V Unixu mohou být programy
spouštěny i jinak než z shellu, napřı́klad pomocı́ správce oken v grafickém rozhranı́
X Window System. Z tohoto důvodu by nebylo dobré skripty těsně vázat na konkrétnı́
prostředı́, z kterého mohou být spouštěny.
Uživatel může vytvořit skript napřı́klad pomocı́ programu cat.
$ cat >sklerotik
echo Jsi na stroji ‘hostname‘
echo Jmenujes se $USER
echo Jsi v adresari ‘pwd‘
CTRL-D

$ cat >dog
#!/usr/bin/perl
print while (<>);
CTRL-D

V praxi se pro vytvářenı́ skriptů použı́vajı́ speciálnı́ programy pro úpravu obsahu
textových souborů – textové editory. Zpracovánı́ textu bude věnována samostatná kapitola. V ukázce uživatel vytvořil dva skripty. Prvnı́ skript sklerotik je určen pro
shell, nemá hlavičku a sloužı́ k výpisu základnı́ch informacı́ na obrazovku. Absence
hlavičky má v shellu stejný efekt, jako by ji uživatel uvedl ve tvaru #!/bin/sh.
Druhý skript dog obsahuje hlavičku s interpretem /usr/bin/perl. Jazyk PERL
vyvinul Larry Wall a původně byl určen pro zpracovánı́ textových4 souborů. PERL
je velmi silný jazyk, výše uvedený jednořádkový skript může sloužit jako náhrada
programu cat. V praxi je dobré jednotlivé skripty zakončovat „přı́ponou“, charakterizujı́cı́ interpret skriptu. Napřı́klad skripty shellu bývajı́ zakončeny .sh, skripty
jazyka PERL .pl, skripty jazyka Python .py, skripty jazyka Tcl/Tk .tcl a podobně5 .
Dalšı́m krokem je nastavenı́ práv a spuštěnı́ skriptů.
$ chmod 755 sklerotik dog
$ ./sklerotik
Jsi na stroji phoenix
Jmenujes se novakj
Jsi v adresari /home/student/inf97/novakj
$ ./dog .fvwmrc | wc -l
291

Předchozı́ metoda spuštěnı́ skriptu s sebou nese významný rys. Shellový skript
je vždy spuštěn v podřı́zeném shellu. To mimo jiné znamená, že hodnoty proměnných, které nebyly exportovány, nebudou ve spuštěném skriptu dosažitelné. Rovněž
4 PERL znamená Practical Extraction and Report Language.
5 Pokud vás udivuje množstvı́ různých programovacı́ch jazyků, pak vězte, že vyjmenované jazyky tvořı́

jen zlomek dostupného softwarového vybavenı́. Obecně platı́ zásada, že volba jazyka by měla následovat
až po analýze problému, nikoliv předem. Součástı́ softwarového vybavenı́ GNU je množstvı́ interpretů
a překladačů různých jazyků, z nichž některé jsou úzce specializované.

5.6.

Vytvářenı́ skriptů

123

změny v nastavenı́ proměnných budou po dokončenı́ skriptu zapomenuty. Skripty
pro shell lze spouštět i jiným způsobem. Použijeme-li speciálnı́ přı́kaz shellu ve tvaru
. / soubor., shell bude čı́st postupně všechny řádky z daného souboru a každý provede v aktuálnı́m shellu.
Rozdı́l obou přı́stupů je jasný. Při spuštěnı́ skriptu pomocı́ tečkové notace se
jakékoliv změny ve stavu proměnných promı́tnou do aktuálnı́ho shellu. Následujı́cı́
přı́klad názorně ukazuje rozdı́l.
$ cat >prvni && chmod 755 prvni
echo -n $A’, ’; let A*=10; echo $A
CTRL-D

$ A=10 && ./prvni
, 0
$ . prvni && echo $A
10, 100
100
$ export A && ./prvni && echo $A
100, 1000
100

Při prvnı́m spuštěnı́ skriptu nebyla předána hodnota, jelikož proměnná nebyla
exportována. Dalšı́ spuštěnı́ již proběhlo pomocı́ tečkového přı́kazu, z přı́kladu je
vidět, že se změnila hodnota proměnné A na 100. Při třetı́m spuštěnı́ byla proměnná
exportována, skript načetl jejı́ hodnotu, ale po jeho ukončenı́ nebyla hodnota proměnné změněna. Změna proběhla pouze na lokálnı́ úrovni v podřı́zeném shellu.
K přı́kladu dodejme, že argument -n programu echo potlačuje přechod na nový
řádek, proto jsou na výstupu hodnoty tisknuty vedle sebe.

Předávánı́ argumentů
Skriptům lze stejně jako programům předávat argumenty. Uvnitř skriptu pro
shell lze předané argumenty čı́st pomocı́ proměnných speciálnı́ho významu. Tyto
proměnné jsou samozřejmě pouze pro čtenı́. K argumentům je možné přistupovat
dvojı́m způsobem. Bud’to jsou zpracovány jednotlivě, nebo jako celek. Následujı́cı́
tabulka obsahuje proměnné speciálnı́ho významu, pomocı́ kterých lze čı́st argumenty
skriptu.
proměnná

význam

$0
$n
${n}
$#
$*
$@

jméno skriptu
n-tý argument, n nabývá hodnot 1, . . . , 9
libovolný n-tý argument
čı́slo poslednı́ho argumentu
seznam všech argumentů
seznam všech argumentů

Proměnná $0 reprezentuje nultý argument, to jest samotný název programu v podobě,
ve které byl spuštěn. Nultý argument tedy obsahuje i přı́padnou absolutnı́ nebo relativnı́ cestu zadanou uživatelem na přı́kazovém řádku. Pomocı́ proměnné $# lze zjistit

124

Kapitola 5. Základy přı́kazového interpretu

aktuálnı́ počet argumentů. Proměnné $n odkazujı́ na prvnı́ch devět argumentů, proměnnými ve tvaru ${n} se lze odkazovat i na dalšı́ proměnné, napřı́klad ${13} vracı́
hodnotu třináctého argumentu. Pokud by čı́slo nebylo uzavřeno ve složených závorkách, shell by výraz interpretoval jako dereferenci prvnı́ho argumentu a zřetězenı́ se
znakem „3“.
Pokud chce uživatel pracovat se všemi argumenty současně, může použı́t proměnné $*, $@. Tyto dvě proměnné se odlišujı́ svou interpretacı́ v uzávorkovaném
výrazu.
”$*” je ekvivalentnı́ ”$1 $2 $3 . . . ”
”$@” je ekvivalentnı́ ”$1” ”$2” ”$3” . . .
V přı́padě proměnné $* všechny mezery reprezentujı́ znaky, kdežto v přı́padě $@
mezery figurujı́ v roli metaznaků. Z toto plyne, že pokud bude ve skriptu volán
program, kterému budou dále předávány všechny argumenty, měly by být předány
pomocı́ proměnné $@. Viz přı́klad.
$ cat >prvni && chmod 755 prvni
echo $0 $#; echo $1 $3; echo $@
CTRL-D

$ ./prvni ab cd ef
./prvni 3
ab ef
ab cd ef

Dereferenci ve tvaru ${n} lze použı́t pouze v shellu GNU Bash. V Bourne Shellu
lze při většı́m množstvı́ argumentů použı́t přı́kaz shift / n., kde / n. je přirozené
čı́slo reprezentujı́cı́ počet odstraněných argumentů. Přı́kaz shift sloužı́ k odstraňovánı́ prvnı́ch / n. argumentů. Jsou-li prvnı́ argumenty odstraněny, lze se pomocı́
proměnné $n odkazovat na předtı́m nedostupné argumenty. Pokud je napřı́klad použit přı́kaz shift 2, potom bude $1 ukazovat na třetı́ argument. Čı́selný argument
může být u přı́kazu shift vynechán úplně, v tom přı́padě je odebrán pouze prvnı́
argument. Viz přı́klad.
$ cat >odstran && chmod 755 odstran
echo $@; shift; echo $@; shift 3; echo $@
CTRL-D

$ ./odstran a b c d e f g h
a b c d e f g h
b c d e f g h
e f g h

Při použı́vánı́ přı́kazu shift je nutné dávat pozor na jednu okolnost. Argumenty
odstraněné pomocı́ shift již nelze nijak „vrátit zpět“.

Interaktivnı́ skripty
Občas je dobré poskytnout uživateli možnost vkládat hodnoty přı́mo při běhu
skriptu. Instalačnı́ skripty dodávané s některými programy se napřı́klad uživatele

5.6.

Vytvářenı́ skriptů

125

ptajı́ na cı́lový adresář nebo na informace o rozsahu instalace. K interaktivnı́mu
nastavenı́ obsahu proměnné sloužı́ přı́kaz read. Argumentem přı́kazu read je proměnná, do které se má uživatelský vstup uložit. Při zadávánı́ citlivých informacı́
může skript vhodným volánı́m programu stty potlačit výpis znaků na terminál.
Následujı́cı́ ukázkový skript požádal uživatele o zadánı́ jména a hesla. Viz přı́klad.
$ cat >prover && chmod 755 prover
echo -n ’Vlozte jmeno: ’ && read NAME
stty -echo
echo -n ’Vlozte heslo: ’ && read PASS
stty echo
echo; echo ’Vlozene udaje:’ $NAME $PASS
CTRL-D

$ ./prover
Vlozte jmeno: zizalka
Vlozte heslo: · · · tady heslo nenı́ vidět · · ·
Vlozene udaje: zizalka aklaziz

Na poslednı́m řádku skriptu je použit program echo bez argumentů. V tomto
tvaru provede echo pouze přechod na nový řádek. Přechod na nový řádek je potřeba
udělat, jelikož dočasné vypnutı́ výpisu na terminál pomocı́ stty -echo způsobı́
potlačenı́ výpisu všech znaků, tedy i ukončovacı́ho znaku „nový řádek“. Pomocı́
stty echo je opět obnoveno původnı́ nastavenı́ terminálu.
V kapitole 5.4. byl citován speciálnı́ přı́kaz shellu select. Přı́kaz sloužı́ ke zjednodušenı́ vytvářenı́ interaktivnı́ch skriptů. Jeho syntaxe je částečně podobná syntaxi
cyklu for. Uživatel při použitı́ přı́kazu specifikuje seznam nabı́dek. Seznam nabı́dek
je při vykonávánı́ přı́kazu zobrazen a uživatel je vyzván k výběru. V těle přı́kazu
select lze kontrolovat průběh výběru – napřı́klad lze dodatečně testovat zakázané
volby a vyžádat si novou volbu. Syntaxe přı́kazu select je následujı́cı́.
select / proměnná. in /nabı́dky.; do / přı́kazy.; done
Nabı́dky jsou definovány seznamem slov / nabı́dky.. Slova v seznamu jsou oddělena
metaznakem mezera. Při provedenı́ přı́kazu je nejprve shellem zobrazen jednoduchý
uživatelský výběr obsahujı́cı́ slova z nabı́dky. Každé slovo je umı́stěno na samostatném očı́slovaném řádku. Za seznamem všech slov je zobrazen prompt přı́kazu
select, tvar promptu je uložen v proměnné PS3. Prompt uživatele vyzývá k odpovědi. Uživatel může zadat bud’to čı́slo uvedené ve výběru, nebo může zadat zcela
jinou hodnotu. V obou přı́padech je hodnota vložená uživatelem uschována do proměnné REPLY a poté jsou vykonány / přı́kazy.. Pokud je vložená hodnota čı́slem
existujı́cı́ položky z nabı́dky, / proměnná. je navázána na čı́selnou hodnotu výběru.
Pokud nenı́ mezi / přı́kazy. proveden přı́kaz break nebo return, výběr se opět
opakuje. Dı́ky opakovánı́ výběru lze v těle přı́kazu select ošetřovat nevhodné
volby.
Možnosti řı́zenı́ výběru demonstruje přiložený přı́klad. V přı́kladu je tělo přı́kazu opuštěno pouze v přı́padě volby jedné se zobrazených alternativ. Pokud nenı́
alternativa správně zadána, přı́kaz opět zobrazı́ nabı́dku a čeká na dalšı́ vstup.

126

Kapitola 5. Základy přı́kazového interpretu
$ select i in pivo vino; do
>
echo ”odpoved: $REPLY, hodnota: $i”
>
if [ -n ”$i” ]; then
>
break;
>
fi
> done

V těle přı́kazu select je proměnná REPLY vždy navázána na hodnotu uživatelského vstupu, a to i v přı́padě, že vstupem nenı́ čı́slo žádné z voleb. Naopak
proměnná i bude navázána na hodnotu pouze v přı́padě, kdy uživatel zadá čı́slo
existujı́cı́ alternativy. Na základě hodnoty proměnné i lze jednoduše rozhodnout,
zdali volbu zopakovat, či ne. Obsah proměnných REPLY a i zůstane definován samozřejmě i po opuštěnı́ přı́kazu výběru. Vykonánı́m uvedeného přı́kazu uživatel
obdržı́ následujı́cı́ nabı́dku a odezvu.
1) pivo
2) vino
# blahblah
odpoved: blahblah, hodnota:
1) pivo
2) vino
# 2
odpoved: 2, hodnota: vino

Uživatelské funkce
Shell umožňuje vytvářet uživatelské funkce. Uživatelská funkce je znovupoužitelná
sekvence přı́kazů, které lze v shellu předávat argumenty. Funkce může explicitně určit
svou návratovou hodnotu. Oproti vykonávánı́ skriptů jsou funkce mnohem efektivnějšı́. Shell si funkce udržuje předzpracované v paměti a jejich provedenı́ je znatelně
rychlejšı́. Syntaxe funkce v shellu je podobná funkci v jazyku C.
/název.() {
· · · tělo funkce · · ·
}
Za názvem funkce musı́ být uveden metaznak „()“. Pomocı́ něj shell zjistı́, že se jedná
o funkci, a dále si uchová tělo funkce ve svých internı́ch strukturách. Tělo funkce sestává z přı́kazů pro shell. Funkce je vždy vyhodnocována v aktuálnı́m shellu, proto
veškeré změny hodnot proměnných provedené v těle funkce se okamžitě promı́tnou.
Funkce může vracet hodnotu pomocı́ přı́kazu return /n ., kde /n . je návratová
hodnota. Přı́kaz return způsobı́ okamžitý návrat z funkce a nastavı́ obsah proměnné
$? na / n.. Nenı́-li přı́kaz return uveden, je návratová hodnota funkce rovna návratové hodnotě poslednı́ho přı́kazu. Pokud by byl pro návrat z funkce použit přı́kaz
exit, došlo by k ukončenı́ celého shellu.
Funkci lze předat vstupnı́ argumenty. V těle funkce se na ně lze odkazovat pomocı́
formálnı́ch argumentů identickým způsobem jako v přı́padě argumentů předávaných skriptu. Viz předchozı́ text. Následujı́cı́ přı́klad ukazuje definici jednoduché
funkce zobrazujı́cı́ velikost souborů.

5.6.

Vytvářenı́ skriptů

127

$ velikost() {
>
for i in $@; do
>
if [ -f $i ]; then
>
echo Soubor $i ma velikost $(cat $i | wc -c)
>
else
>
return 1;
>
fi
>
done
>
return 0;
> }

Nynı́ zbývá provést volánı́ funkce. Volánı́ funkce je syntakticky stejné jako přı́kaz
pro spuštěnı́ programu nebo skriptu. Nejprve je uvedeno jméno funkce, za nı́m
mohou následovat argumenty.
$ velikost ~/.fvwmrc ~/.bash_history
Soubor /home/student/inf97/novakj/.fvwmrc ma velikost 8515
Soubor /home/student/inf97/novakj/.bash_history ma velikost 6330

Definice funkce je opět lokálnı́, pro jejı́ přenesenı́ do vnořených shellů je potřeba
použı́t přı́kaz export.

Standardnı́ vstup z těla skriptu
Poslednı́m zastavenı́m u tématu vytvářenı́ skriptů je přesměrovánı́ standardnı́ho
vstupu programu z těla skriptu. Ačkoliv může tento typ přesměrovánı́ vypadat podivně, jedná se o velmi často použı́vanou programátorskou techniku. Metaznak „<<“
sloužı́ pro přesměrovánı́ vstupu z těla skriptu. Je-li metaznak „<<“ použit, vstupnı́
data pro volaný program nejsou zadávána ani z terminálu, ani ze souboru, nýbrž
přı́mo z části těla skriptu. Syntaxe při tomto druhu přesměrovánı́ je trochu jiná, než je
zvykem.
/ přı́kaz. <</omezovač.
· · · vstupnı́ data · · ·
/ omezovač.
Přı́kaz může mı́t samozřejmě dalšı́ argumenty nebo může být napřı́klad spojen rourou s dalšı́mi programy. Zvláštnı́ roli při specifikaci přesměrovánı́ hraje /omezovač..
Omezovač je libovolná sekvence znaků stojı́cı́ bezprostředně za metaznakem „<<“.
Pomocı́ omezovače shell pozná, kde vstupnı́ data končı́. Po spuštěnı́ procesu shell
předává na jeho standardnı́ vstup data, která se nacházejı́ mezi následujı́cı́m řádkem
a prvnı́m výskytem omezovače. Omezovač musı́ být uveden na samostatném řádku
ve stejném tvaru jako za metaznakem „<<“.
Je-li omezovač definován v uvozovkách, to jest ve tvaru ”/ omezovač.”, shell neprovádı́ dereferenci proměnných ve vstupnı́ch datech. V jiném přı́padě je dereference
provedena. Expanze se neprovádı́ nikdy. Přesměrovánı́ vstupu z těla skriptu se použı́vá napřı́klad ve skriptech generujı́cı́ch konfiguračnı́ soubory. Při psanı́ skriptu
se konfiguračnı́ soubor pı́še přı́mo do jeho těla a měnı́cı́ se hodnoty jsou zı́skávány
dereferencı́ z proměnných. Pro ilustraci je uveden přı́klad.

128

Kapitola 5. Základy přı́kazového interpretu
$ cat >zobraz-info && chmod 755 zobraz-info
cat <<EOF
Jmenuji se $USER, muj UID je $UID.
Jsem v adresari $PWD.
EOF
CTRL-D

$ ./zobraz-info
Jmenuji se novakj, muj UID je 1045.
Jsem v adresari /home/student/inf97/novakj.

Jelikož byl omezovač EOF definován bez uvozovek, došlo k dereferenci proměnných USER, UID a PWD. Použitı́ přesměrovánı́ standardnı́ho vstupu z těla skriptu bylo
v předchozı́m přı́kladu v podstatě neúčelné. Téhož efektu bychom mohli dosáhnout
kombinacı́ dvou přı́kazů spuštěnı́ echo. Efekt přesměrovánı́ z těla skriptu je zřejmý,
jsou-li vstupnı́ data vı́c strukturovaná nebo pokud jsou dále skriptem zpracovávána.
Viz přı́klad.
$ cat >vstup && chmod 755 vstup
cat <<EOF | tee zalohuj.txt
Jsem v $PWD
EOF
CTRL-D

$ ./vstup
Jsem v /home/student/inf97/novakj

V předchozı́ ukázce byl standardnı́ vstup pro program cat přesměrován z těla
skriptu. Navı́c byla vytvořena kolona mezi producentem cat a konzumentem tee.
To jest kromě vypsánı́ hlášenı́ na obrazovku bylo totéž hlášenı́ uloženo i do souboru
zalohuj.txt.

5.7.

Počátečnı́ nastavenı́ shellu

Shell bash při svém startu vykonává přı́kazy v inicializačnı́ch skriptech. Úkolem
inicializačnı́ch skriptů je nastavit proměnné prostředı́ na vhodné hodnoty a provést základnı́ přizpůsobenı́ shellu lokálnı́m účelům. Inicializačnı́ skripty mohou
být bud’to systémové, nebo uživatelské. Hlavnı́m inicializačnı́m skriptem shellu je
/etc/profile. Jednotlivı́ uživatelé si rovněž mohou ve svých domovských adresářı́ch definovat vlastnı́ startovacı́ skripty. Inicializačnı́ skripty jsou vykonávány
v pevně daném pořadı́. Pořadı́ vykonávánı́ skriptů je dáno režimem spuštěnı́ shellu.
Shell může být spuštěn ve třech základnı́ch režimech.
• Přihlašovacı́ shell je spuštěn po přihlášenı́ uživatele do systému. Explicitně lze
spustit shell jako přihlašovacı́ pomocı́ argumentu --login. Přihlašovacı́ shell
nejprve vykoná přı́kazy ze souboru /etc/profile. Po dokončenı́ poslednı́ho přı́kazu nebo v přı́padě nenalezenı́ souboru shell vykonává uživatelské inicializačnı́ skripty. Shell postupně zkoušı́ vykonávat přı́kazy ze souborů
~/.bash_profile, ~/.bash_login a souboru ~/.profile. Přı́kazy v prvnı́m nalezeném souboru jsou provedeny, obsah ostatnı́ch souborů je ignoro-

5.7.

Počátečnı́ nastavenı́ shellu

129

ván. Před odhlášenı́m uživatele ze systému se provedou přı́kazy ze skriptu
~/.bash_logout, pokud je skript nalezen.
• Interaktivnı́ shell má standardnı́ vstup a výstup spojen s terminálem. Interaktivnı́
shell, který nenı́ přihlašovacı́, nejprve zdědı́ exportované proměnné po svých
rodičı́ch. Potom vykoná přı́kazy ze souboru ~/.bashrc. Vykonánı́ přı́kazů
z tohoto souboru lze potlačit pomocı́ přepı́nače --norc. Alternativnı́ název
pro inicializačnı́ soubor lze definovat argumentem --rcfile /soubor..
• Neinteraktivnı́ shell je shell bez spojenı́ s terminálem. Neinteraktivnı́ shell nepoužı́vá ani systémové, ani uživatelské inicializačnı́ skripty. Shell podědı́ proměnné
z rodičovského shellu, poté se snažı́ dereferencovat proměnnou BASH_ENV.
Obsah této proměnné je chápán jako inicializačnı́ soubor, je-li nalezen, začne se
vykonávat. Při hledánı́ inicializačnı́ho souboru ale nenı́ použita cesta.
Přihlašovacı́ shell je speciálnı́m přı́padem interaktivnı́ho shellu. Zde je přihlašovacı́
shell uveden jako speciálnı́ kategorie, protože při startu provádı́ inicializačnı́ skripty
odlišným způsobem.

Uživatelské limity
Přı́kaz ulimit sloužı́ v shellu k nastavenı́ uživatelských limitů. Vhodným nastavenı́m limitů lze omezovat procesy spouštěné ze shellu. Napřı́klad při programovánı́
paralelnı́ch programů je možné předcházet přehlcenı́ systému nastavenı́m limitu maximálnı́ho počtu procesů spustitelných z shellu. Systémové limity lze vypsat pomocı́
přı́kazu ulimit -a.
Z uživatelského hlediska je zajı́mavé nastavit maximálnı́ velikost souboru core.
Pokud uživatel systému neprovádı́ laděnı́ programů, je praktické, aby systém nevytvářel soubory core vůbec. Naopak při laděnı́ je jejich vytvářenı́ takřka nepostradatelné. Přı́kazem ulimit -c / velikost. lze nastavit maximálnı́ velikost souboru
core v blocı́ch. Jeden blok odpovı́dá 512 B.

Použı́vánı́ aliasů
V inicializačnı́ch skriptech bývajı́ často nastavovány aliasy. Alias je aparát umožňujı́cı́ zavádět přı́kazům shellu nová jména. Nejčastěji se aliasy použı́vajı́ k zastoupenı́
přı́kazu spuštěnı́ programu. Pokud alias definuje přı́kaz spuštěnı́ programu, je samozřejmě možné u volaného programu použı́vat i argumenty. Alias lze zavést přı́kazem
alias, zrušenı́ aliasu se provádı́ pomocı́ unalias.
alias /název.=/ výraz.
unalias /název.
kde /název. je název pro alias, / výraz. je libovolný řetězec znaků. Pokud je v přı́kazu
pro shell na prvnı́m mı́stě uvedeno jméno aliasu, shell jej expanduje na / výraz..
Na ostatnı́ch mı́stech přı́kazu expanze aliasů neprobı́há. Aliasy si uživatelé definujı́

130

Kapitola 5. Základy přı́kazového interpretu

zpravidla v souboru ~/.bashrc. Mezi často nastavované aliasy patřı́ napřı́klad
použı́vánı́ barev v programu ls a syrový výpis binárnı́ch dat v programu less. Viz
ukázku.
$ cat ~/.bashrc
alias ls=’ls --color -F’
alias less=’less -r’

Barevný výpis souborů sloužı́ k jednoduššı́ orientaci. Barvy jednotlivým souborům lze přidělovat i na uživatelské úrovni napřı́klad uvedenı́m požadované barvy
pro neúplné jméno souboru. Informace o stylu vypisovánı́ souborů jsou uloženy
v proměnné LS_COLORS. Obsah proměnné LS_COLORS zpravidla nenı́ nutné měnit
přı́mo, v systému sloužı́ k pohodlnému nastavenı́ barev program dircolors. Pro
detaily viz jeho manuálovou stránku.

Literatura

245

Literatura
[AWK88] Aho, A. V. — Kernighan, B. W. — Weinburger, P. J. The AWK Programming Language.
Addison Wesley Longman, Inc., 1988.
[Bac86]

Bach, M. J. The Design of the Unix Operating System.
Prentice Hall Software Series, 1986.

[Bou82]

Bourne, S. R. The Unix System.
Addison Wesley Longman, Inc., 1982.

[DR97]

Dougherty, D. — Robbins, A. Sed & Awk.
2nd Edition, O’Reilly & Associates, Inc., 1997.

[Kau96]

Kaufman, L. — Welsh, M. Running Linux.
2nd Edition, O’Reilly & Associates, Inc., 1996.

[Ker84]

Kernighan, B. W. — Pike, R. The Unix Programming Environment.
Prentice Hall Software Series, 1984.

[LLS88]

Lewis, B. — LaLiberte, D. — Stallman, R. M. GNU Emacs Lisp Reference Manual.
Edition 2.5, Free Software Foundation, 1998.
ftp://ftp.linux.cz/pub/gnu/manuals/elisp/index.html.

[Mik92]

Mikes, S. X Window System. Program Design and Development.
Addison Wesley Longman, Inc., 1992.

[New92] Newham, C. — Rosenblatt, B. Learning the Bash Shell
2nd Edition, O’Reilly & Associates, Inc., 1992.
[Ope99]

Bradner, S. — DiBona, C. — Hamerly, J. — McKusick, M. K. — Ockman S. —
O’Reilly, T. — Paquin, T. — Perens, B. — Raymond, E. S. — Stallman, R. M. —
Stone, M. — Tiemann, R. — Torvalds, L. — Vixie, P. — Wall, L. — Walton, S. —
Young, R. — Voices from the Open Source Revolution.
O’Reilly & Associates, Inc., 1999.

[Que89]

Quercia, V. — O’Reilly, T. X Window System — User’s Guide.
O’Reilly & Associates, Inc., 1989.

[Sat02]

Satrapa, P. IPv6.
Neocortex, Praha, 2002.

[Sko98]

Skočovský, L. Unix, POSIX, Plan 9.
Vydal Luděk Skočovský, Brno, 1998.

[Sob97]

Sobell, M. G. A Practical Guide to Linux.
Addison Wesley Longman, Inc., 1997.

[Sta81]

Stallman, R. M. The Extensible, Customizable, Self-Documenting Display Editor.
MIT AI Memo, 519a. 1981.
ftp://publications.ai.mit.edu/classic-hits/aim-519a.ps.

[Sta88]

Stallman, R. M. GNU Emacs Manual.
13th Edition, Free Software Foundation, 1998.
ftp://ftp.linux.cz/pub/gnu/manuals/emacs/index.html.

246

Literatura

Rejstřı́k souborů

247

Rejstřı́k souborů
Následujı́cı́ přehled souborů sloužı́ ke snazšı́ orientaci a vyhledávánı́ informacı́ o důležitých souborech a adresářı́ch v systému GNU/Linux. Jména systémových souborů
jsou uvedena včetně absolutnı́ cesty. V některých distribucı́ch GNU/Linuxu se může
umı́stěnı́ souborů mı́rně odlišovat. Pokud jméno souboru začı́ná dvojicı́ znaků „~/“,
předpokládáme, že soubor může být umı́stěn v domovském adresáři každého uživatele. Je-li na týž soubor uvedeno vı́ce odkazů, tučným pı́smem je zvýrazněna hlavnı́
strana, na které je popsán jeho význam a účel.
/bin, 62, 86, 112
/boot, 62, 62
/dev/full, 42, 42
/dev/null, 42, 42, 93
/dev/random, 42
/dev/zero, 42, 42
/dev, 42, 62, 62
/etc/environment, 169
/etc/exports, 194
/etc/fstab, 43, 63, 63
/etc/group, 49, 64, 194
/etc/host.conf, 190
/etc/hostname, 64
/etc/hosts, 64, 187, 190, 219
/etc/init.d, 64, 64
/etc/inittab, 64, 64, 229
/etc/issue, 64
/etc/locale.alias, 169
/etc/mime.types, 197
/etc/motd, 64
/etc/mtab, 64
/etc/network/interfaces, 182
/etc/nsswitch.conf, 194
/etc/passwd, 49, 51, 64, 147, 194
/etc/profile, 64, 108, 128, 195
/etc/rcS.d, 64
/etc/rcn.d, 64, 64
/etc/resolv.conf, 190
/etc/services, 64, 64, 184, 218
/etc/shadow, 49, 64
/etc/shells, 65
/etc/terminfo, 65
/etc/X11/app-defaults, 240
/etc/X11/rgb.txt, 236, 236, 237
/etc/X11/XF86Config, 227
/etc/X11, 65
/etc, 62, 63

/home, 42, 62, 62
/lib/modules, 63
/lib, 63
/mnt, 63
/opt, 63, 63
/proc, 44, 63
/root, 63
/sbin, 63
/tmp, 63, 63
/usr/bin/X11/X, 226, 226
/usr/bin/X11, 112
/usr/bin, 65, 112
/usr/doc, 43
/usr/include/netdb.h, 184
/usr/include, 65
/usr/info, 65
/usr/lib/ispell, 171
/usr/lib, 65, 65
/usr/local/bin, 112
/usr/local, 65, 65
/usr/man/mann, 65, 65
/usr/man, 65, 65
/usr/sbin, 65, 193
/usr/share/dict, 144
/usr/share/doc, 65
/usr/share/locale, 169
/usr/share, 65, 65
/usr/X11R6, 65
/usr, 63, 63, 65
/var/lib, 65, 65
/var/lock, 65
/var/log, 66
/var/run, 66
/var/spool/mail, 111, 199
/var/spool, 66, 66
/var/tmp, 63
/var, 43, 63, 63, 65

248
~/.bash_history, 111
~/.bash_login, 128
~/.bash_logout, 129
~/.bash_profile, 108, 128, 169, 195
~/.bashrc, 129, 130
~/.calendar, 84, 84
~/.emacs-user, 165, 165
~/.emacs, 165, 165, 167
~/.forward, 201, 201, 202
~/.gnome/gdm, 228, 228
~/.gnupg, 203
~/.netrc, 211
~/.plan, 215
~/.procmailrc, 202, 202
~/.profile, 108, 195
~/.signature, 200
~/.ssh/authorized_keys, 213
~/.ssh/identity.pub, 213, 213
~/.ssh/known_hosts, 213
~/.Xauthority, 233, 233
~/.Xdefaults, 241
~/.xinitrc, 227, 227
~/.xkbsel/xkbsel.conf, 245, 245
~/.Xresources, 241
~/.xserverrc, 226
~/.xsession, 226, 226–228, 241
~/bin, 87
~/mail, 201
~/public_html, 220, 220
core, 77, 77, 78, 129
index.html, 220
nohup.out, 81, 81, 95
welcome.html, 220

Rejstřı́k souborů

Rejstřı́k pojmů

249

Rejstřı́k pojmů
V tomto rejstřı́ku jsou uvedeny odkazy na důležité pojmy. Některé fráze zde naleznete hned v několika tvarech, tato organizace rejstřı́ku umožňuje snazšı́ vyhledávánı́
v knize. Rejstřı́k obsahuje i seznam zdokumentovaných obslužných programů, přı́kazů a proměnných shellu, známých volánı́ jádra a běžně použı́vaných signálů.

A
absolutnı́ cesta, 30, 87, 121
account, 14
ACL, 56
aditivnı́ skládánı́, 236
adresa, 145, 183
— podsı́tě, 181
— poštovnı́, 196
— rozhranı́, 180
— sı́tě, 180
adresář, 29
— domovský, 32
— exportovaný, 194
— pracovnı́, 31, 32
— prázdný, 36
— rodičovský, 30
— speciálnı́, 32
adresát, 196
agregovaný přı́kaz, 91
aktivnı́ režim, 211
aktuálnı́ shell, 91
alias, 129, 239
alternativa, 141
alternativnı́ větev, 116, 117
analyzátor, 140
anonymnı́ FTP, 209
aplikačnı́ log, 66
apostrofy, 103
argument, 19, 86, 123, 126
— přepı́nač, 19
— vstupnı́, 126
archivace, 172
ASCII kód, 132
atomický přı́kaz, 91
atribut, 234
— barva, 236
— font, 237
— geometrie, 239
— hodnota, 234
— pixmapa, 239

— proměnné, 105
— translace, 239
— vymezenı́, 234
— zdroje, 234
autentizace, 6, 14, 209
autoritativnı́ odpověd’, 189
autorizace, 231, 232
autorizačnı́ klı́č, 233

B
background, 73
backtrace, 77
balı́ček, 10
balı́k, 10
bang notace, 196
barva, 236
běžı́cı́ proces, 72–74
běžný uživatel, 14
binárnı́ režim, 210
bitová rovina, 227
blok, 41
blokové zařı́zenı́, 41
boolean, 236
bootloader, 42
broken link, 45
buffer, 157

C
cache server, 189
celoobrazovkový editor, 133,
151
cesta
— absolutnı́, 30, 87, 121
— prohledávacı́, 86, 106, 121
— prohledávaná, 88
— relativnı́, 32, 87, 121
— sı́t’ová, 195
— vzdálená, 214

clipboard, 234, 242
cyklus, 113, 117

Č
časové pásmo, 20
časový
— drift, 192
— posun, 81
česká klávesnice, 244
čı́slo
— displaye, 226
— GID, 48
— jádra, 8
— obrazovky, 226
— PID, 68, 72, 109
— PPID, 72
— řádku, 145
— signálu, 77
— UID, 48
člen skupiny, 50

D
daemon, 16, 69
data
— binárnı́, 132
— textová, 132
— vstupnı́, 92
— výstupnı́, 92
databáze
— atributů, 240
— map, 244
datagram, 179, 183
datový
— soubor, 26, 27
— tok, 96
— typ, 236
— — barva, 236

250
— — boolean, 236
— — font, 237
debugger, 77
decentralizace, 177
deklarace, 105
dekomprese, 175
dereference proměnné, 105
deskriptor, 92
desktop, 225
diakritika, 197
diferenciace dat, 25
digitálnı́ podpis, 203
disková
— kvóta, 27, 61
— oblast, 26
— — disková, 26
— — statická, 26
diskusnı́ listy, 205
— moderované, 205
— nemoderované, 205
— otevřené, 205
— uzavřené, 205
display, 222, 226
— manager, 226, 227, 230
distribuce, 10
— nativnı́, 11
— nestabilnı́, 11
— stabilnı́, 11
— testovacı́, 11
— zmrazená, 11
doba odezvy, 182
dodatečná informace, 86
dokončenı́ spojenı́, 186
doména
— generická, 188, 191
— kořenová, 188
— prvnı́ho řádu, 188, 191
— reverznı́, 190
— státnı́ho územı́, 188
doménové jméno, 187
domovský adresář, 32
dopis, 196
doplněk, 100
download, 209
— rekurzivnı́, 219
drift, 192
driver, 2

Rejstřı́k pojmů

E
editor, 122, 131
— celoobrazovkový, 133, 151
— proudový, 133
efekt
— frustrace, 4
— zakrytı́, 42
efektivnı́ uživatel, 69, 71
elektronická
— konference, 205
— pošta, 196
elektronický dopis, 196
emulátor terminálu, 6, 228
escape character, 208
expanze jmen, 99
expirace, 233
export
— adresáře, 194
— proměnné, 108

— stı́nové, 49, 64
heterogennı́ prostředı́, 195
hierarchická struktura, 28, 68,
187
hlavička
— dopisu, 196
— skriptu, 121
hlavnı́ mód, 157
hledánı́ souborů, 88
hodnota
— atributu, 234
— proměnné, 106
horizontálnı́ rozdělenı́, 161
hostitel, 16, 177
— lokálnı́, 181, 221
— vzdálený, 221
hostitelské jméno, 187
hostitelský uzel, 177

CH
F
fileserver, 194
filtr, 92
fingerprint, 213
font, 237
— server, 237
foreground, 73
formát XPM, 239
frame, 157
funkce, 126

G
generace jádra, 8
generická doména, 188, 191
geometrie, 239
— oken, 224
globálnı́ proměnná, 118
grafické rozlišenı́, 229
group, 50

H
hard link, 45
heslo, 14, 203

charakter
— přı́lohy, 198
— změny, 136
chyba, 223

I
i-node, 27
identifikace
— displaye, 226
— procesu, 68
identifikátor
— procesu, 74
— úlohy, 82
inbox, 198
indexový soubor, 220
informace dodatečná, 86
inicializačnı́ skript, 128
— systémový, 128
— uživatelský, 128
instance programu, 242
instrukce, 145
interaktivnı́
— program, 98
— režim, 40
— shell, 129

Rejstřı́k pojmů
interpret
— přı́kazů, 6
— skriptu, 121
IP adresa, 180
— privátnı́, 181
— speciálnı́, 181
iterace, 118

J
jádro, 6, 7
— generace, 8
— nestabilnı́, 8
— pořadové čı́slo, 8
— stabilnı́, 8
— subgenerace, 8
jazyk, 169
jazykové prostředı́, 228
jednorázové spuštěnı́, 82
jednotka vykonávánı́, 68
jméno
— atributu, 235, 236
— displaye, 233
— doménové, 187
— hostitelské, 187
— módu, 158
— neúplné, 99
— objektu, 234
— prázdné, 188
— proměnné, 105, 106
— souboru, 27
— symbolické, 187
journaling, 27

K
katalog zpráv, 168
kategorie, 168
— lokalizačnı́, 168
— uživatelů, 50, 56
— — ostatnı́, 50
— — skupina, 50
— — vlastnı́k, 50
— znaků, 142
kernel, 6
— thread, 69
kill-ring, 162

251
klávesa
— úniková, 208
klávesnicové makro, 164
klávesová mapa, 244
klı́č, 233
— privátnı́, 203
— veřejný, 203
klient, 187, 194, 223
klientský požadavek, 223
kódová stránka, 132, 167, 169,
170
kódovánı́, 158, 167, 197
— přı́lohy, 197
kolona, 96
— uzavřená, 97
komentář, 121
komprese, 172
— dat, 174
— neztrátová, 174
— ztrátová, 174
komunikace, 222
— lokálnı́, 223
— meziprocesová, 185
— nelokálnı́, 185
— vzdálená, 223
komunikačnı́ podsı́t’, 177
konec řádku, 144
konkatenace, 141
kontext, 67, 68, 150
kontextový režim, 136
konzument, 96, 185
kopı́rovánı́ souborů, 39
korekturnı́ program, 171
kořen, 28–30
kořenová doména, 188
kořenové okno, 224
kořenový
— adresář, 30
— souborový systém, 42
kryptografie, 203
kurzor, 239
kvantifikace jmen, 99
kvóta, 27, 61

L
ladicı́ režim, 113
lhůta, 62

libovolná posloupnost, 144
limit, 62, 78, 129
limitnı́ podmı́nka, 117
link, 34
list, 29
local
— broadcast, 181
— login, 14
log, 66
— aplikačnı́, 66
— systémový, 66
logický
— popis, 237, 239
— součet, 110
— součin, 57, 59, 110
login shell, 17, 85, 128
lokalizace, 168
lokalizačnı́ kategorie, 168
lokálnı́
— hostitel, 221
— oznámenı́, 181
— přihlášenı́, 14
loopback, 181

M
major
— mode, 157
— number, 42
makro, 164
— klávesnicové, 164
— pojmenované, 165
manuálová stránka, 21
mapa klávesová, 244
mark, 154
maska, 55, 60
— podsı́tě, 181
mátoha, 78
merge, 134
metadata, 27
meziprocesová komunikace,
95
minibuffer, 158
minor
— mode, 158
— number, 42
mı́ra komprese, 174
množina znaků, 100

252
množinový doplněk, 100
mód přı́stupu, 52
modifikace textu, 154
modul, 63
— jádra, 63

N
nabı́dka, 125, 224
náhodný přı́stup, 41
nahrazovánı́, 155
narušený odkaz, 45
následnı́k, 29
naslouchánı́, 186
návratová hodnota, 126
název
— bufferu, 158
— zástupný, 245
neautoritativnı́ odpověd’, 189
neinteraktivnı́ shell, 129
nepravda, 236
nerekurzivnı́ překlad, 189
nestabilnı́ série, 8
nestavový charakter, 218
network
— address, 181
— broadcast, 181
— mask, 181
neúplné jméno, 99
neveřejné FTP, 209
neviditelný soubor, 31
neztrátová komprese, 174
nosič dat, 25
notace
— modernı́, 141
— staršı́, 141

O
objekt, 234, 235
— aplikace, 235, 242
oblast, 163
obrazovka, 222
obsah proměnné, 105
obslužný program, 6, 86
oddělovač, 91, 137
— přı́kazů, 110

Rejstřı́k pojmů
odesı́latel dopisu, 197
odkaz, 34
— pevný, 45
— symbolický, 45, 56
odpověd’
— autoritativnı́, 189
— neautoritativnı́, 189
— serveru, 223
odstavec, 153
okno, 157, 221, 224
opakované provedenı́ přı́kazu, 165
operačnı́ systém, 1
oprava textu, 154
opravný soubor, 136
organizace dat, 67
ostatnı́, 50, 57
otevřený soubor, 92
others, 50, 57
otisk, 213
ovladač, 2
owner, 50

P
package, 10
pager, 224
pamět’sdı́lená, 78
pasivnı́ režim, 211
patch, 136
periodické spuštěnı́, 83
pevný odkaz, 45
pipe, 96
pixel, 222
pixmapa, 239
plain text, 132
plán, 215
plánovač, 67
plánované spouštěnı́, 81
počet
— bloků, 61
— souborů, 61
počı́tačová sı́t’, 15
podadresář, 30
podmı́něný přı́kaz, 113, 116
podobjekt, 234
podpis, 200, 203
podřı́zený shell, 91

podsı́t’, 181
pojmenovaná roura, 98, 185
pojmenované makro, 165
popis fontů, 237
port, 179, 184, 185
pořadı́ oken, 224
posloupnost znaků, 100, 132
pošta, 196
poštovnı́
— adresa, 196
— klient, 198
— server, 198
potlačenı́
— expanze, 101, 143
— výstupu, 92
pozastavený proces, 72–74
pozice změny, 136
požadavek klientský, 223
pracovnı́ adresář, 31, 32
pravda, 236
právo
— čtenı́, 50
— execute, 50–52
— maska, 55
— read, 50, 51
— SGID, 51
— spouštěnı́, 50
— SUID, 51
— write, 50, 51
— zápisu, 50
prázdný
— adresář, 36
— přı́kaz, 151
— řádek, 144
— řetězec, 132, 141
primárnı́
— prompt, 112
— server, 189
— skupina, 48, 49
primitivum, 222
priorita, 76, 90, 235
— procesu, 76
— snı́žená, 76
privátnı́ klı́č, 203
privilegovaný režim, 2
proces, 2, 5, 67
— identifikátor, 74
— na popředı́, 73

Rejstřı́k pojmů
— na pozadı́, 73
— nezávislý, 80
— priorita, 76
— přesunutý, 74
— rodičovský, 68
— stavy, 72
— — běžı́cı́, 72–74
— — pozastavený, 72–74
— — spı́cı́, 72
— synovský, 68
— systémový, 69
— uživatelský, 69
— vedoucı́ skupiny, 71, 80
procesorový čas, 5
producent, 96, 185
program, 67, 86, 121
program obslužný, 86
programy
— /sbin/init, 42, 42, 64,
70, 76, 79, 229
— apropos, 21, 21
— arj, 176
— atd, 81, 82
— atq, 82
— atrm, 82
— at, 81, 81, 82, 219
— awk, 148, 148–150
— bash, 68, 69, 71, 80, 86,
107, 128
— bitmap, 244
— bzip2, 174, 174–176
— calc, 98, 118, 120
— calendar, 84, 84
— cal, 84, 84
— cat, 38, 38, 94, 95, 97–99,
110, 118, 122, 128, 133,
138
— cftp, 211
— cmp, 135, 135
— comm, 135, 135
— compress, 174
— convert, 244
— cp, 39, 39, 40, 46, 56, 214
— crontab, 83, 83
— cron, 83, 83, 84
— cstocs, 170, 170
— cut, 137, 137, 138, 149
— date, 20, 20, 92, 97

253
— dd, 42, 138, 138, 139
— decompress, 174
— df, 61, 64
— diff, 136, 136, 167
— dircolors, 130
— dos2unix, 170
— du, 36, 36, 37
— ed, 136, 145, 150, 150, 151
— egrep, 143, 143, 144, 146
— echo, 101, 101, 104, 106,
118, 123, 125, 128, 200,
217
— elm, 199, 199
— ex, 151, 151
— false, 110, 110
— fetchmail, 201, 201, 202
— file, 37, 37, 46
— find, 88, 88–90, 94, 98, 99,
105, 174
— finger, 20, 20, 215
— ftp, 209, 210, 211
— fvwm2, 224, 228
— fvwm95, 224
— fvwm, 224, 224, 228
— gdm, 228, 228, 229
— getfacl, 57, 57
— getty, 229
— gpg, 203, 203
— grep, 97–99, 143, 143, 146
— groups, 49
— gzip, 31, 73, 80, 174, 175,
176
— head, 38, 94, 133
— hostname, 104
— host, 191, 191
— chgrp, 50, 50, 55
— chmod, 52, 52, 53, 55
— chown, 50, 50, 55
— inetd, 207
— info, 23, 23, 24, 167
— ispell, 171, 171, 172
— kdm, 228, 228
— killall, 78, 79
— kill, 78, 78, 120, 229
— less, 38, 38, 97, 130
— lftp, 211
— lha, 176
— links, 219

— ln, 45, 45, 46
— locale, 169
— locate, 89, 89
— ls, 31, 34, 34, 35, 47, 51, 54,
55, 57, 67–69, 86, 90–92,
101, 109, 130, 214
— mail, 120, 199, 199
— make, 166
— man, 21, 21, 65, 80
— mesg, 216, 216
— mkdir, 35, 35, 36
— mkfifo, 98, 98
— mknod, 42, 98
— more, 38, 38, 112
— most, 38, 38
— mount, 43, 43, 44
— mutt, 75, 199, 199, 200
— mv, 39, 39, 40
— nice, 76, 76
— nn, 206
— nohup, 80, 80, 81, 95
— nslookup, 191, 191
— ntpdate, 192, 193
— pager, 80, 112
— passwd, 21, 21, 51
— paste, 137, 138, 144
— patch, 136, 136, 137
— pax, 174
— pine, 206
— ping, 182, 182
— procmail, 202, 202
— ps, 70, 70–72, 80
— pwd, 33, 33, 115
— quota, 61
— rar, 176
— recode, 171, 171
— renice, 76, 76
— rmdir, 36, 36
— rm, 39, 40, 46
— rxvt, 242, 242, 243
— scp, 214, 214
— sed, 97, 119, 141, 145, 145–
150, 156, 214
— setfacl, 58, 58, 60
— sleep, 90, 90, 91
— socket, 185, 185, 186
— sort, 98, 134, 134, 135
— split, 139, 139

254
— ssh-keygen, 213
— ssh, 212, 212–214, 231
— startx, 226, 226, 227, 233
— stty, 125
— symlinks, 46, 47
— tail, 38, 38, 94, 97, 134
— talkd, 216
— talk, 216, 216
— tar, 31, 61, 172, 172–176,
186
— tee, 97, 97, 128
— telnetd, 207, 207
— telnet, 207, 207–209,
212, 213, 231
— test, 114, 114, 115
— time, 71
— top, 72, 73
— touch, 116, 116
— tracepath, 182, 183
— traceroute, 183
— tree, 35, 35
— trn, 206
— true, 110, 110
— tr, 148, 148
— twm, 227, 228
— umount, 43, 44
— uniq, 134, 134, 135
— unix2dos, 170
— uptime, 20, 90
— vim, 152, 156
— vi, 151, 151, 152, 154, 156,
163
— wc, 39, 97–99, 134
— wget, 219, 219, 220
— whatis, 21, 21
— whereis, 88, 88
— which, 88, 88
— whoami, 19, 19
— who, 19, 19, 22, 90, 92, 97
— wmaker, 228
— write, 216, 217
— w, 19
— xargs, 105, 105
— xauth, 232, 232, 233
— xbiff, 246
— xclock, 246
— xcolorsel, 246
— xdm, 228, 228

Rejstřı́k pojmů
— xedit, 240, 246
— xev, 246
— xfontsel, 239, 240, 246
— xgamma, 244
— xhost, 232, 232
— xinit, 226, 226, 227, 233
— xkbsel-aw, 245
— xkbseldb, 244, 244
— xkbsel, 244, 244, 245
— xkill, 246
— xload, 246
— xmag, 246
— xman, 231, 235, 240, 241,
246
— xrdb, 240, 241
— xsetroot, 243, 244
— xset, 243, 243
— xterm, 227, 235, 242, 242,
243
— ypcat, 193, 194, 194
— yppasswd, 21, 193, 194
— zip, 176
— zoo, 176
prohledávacı́
— cesta, 86, 106, 121
— podmı́nky, 88
proměnná, 105, 168
— atributy, 105
— exportovaná, 108
— globálnı́, 118
— hodnota, 106
— jméno, 105, 106
— obsah, 105
— pro čtenı́, 105, 109
— speciálnı́, 105
— uživatelská, 105
— vnitřnı́, 105
proměnná shellu, 91, 105
proměnné shellu
— DISPLAY, 231
— HOME, 115
— HOSTNAME, 195
— HOSTTYPE, 195
— LANG, 168, 169
— LC_ALL, 168, 169
— LC_CTYPE, 168, 244
— LS_COLORS, 130
— MAILCHECK, 111

— PATH, 106, 122, 195
— PS3, 125
— PS4, 113
— PWD, 115, 122, 128
— REPLY, 126
— RESULT, 119
— SHLVL, 112
— TERM, 18
— UID, 128
— USER, 128
— BASH_ENV, 129
— CDPATH, 111
— DISPLAY, 231
— EDITOR, 111
— HISTFILESIZE, 111
— HISTFILE, 111
— HISTSIZE, 111
— HOME, 111
— HOSTNAME, 111
— HOSTTYPE, 111
— LANG, 168
— LC_ALL, 111
— LC_COLLATE, 168
— LC_CTYPE, 168
— LC_MESSAGES, 168
— LC_MONETARY, 168
— LC_NUMERIC, 168
— LC_TIME, 168
— LD_LIBRARY_PATH, 195
— LS_COLORS, 130
— MAILCHECK, 111
— MAILPATH, 111
— MAIL, 111
— OSTYPE, 111
— PAGER, 111
— PATH, 112
— PS1, 112
— PS2, 112
— PS3, 113
— PS4, 113
— PWD, 112
— RANDOM, 112
— REPLY, 125
— RESULT, 119
— RUNLEVEL, 112
— SHLVL, 112
— TERM, 112
— UID, 112

Rejstřı́k pojmů
— USER, 112
prompt, 17, 112
— primárnı́, 112
— pro laděnı́, 113
— přı́kazu select, 113
— sekundárnı́, 112
propojovacı́ prvky, 177
prostý text, 132
protokol, 179
— FTP, 209
— HTTP, 179, 208, 217
— ICMP, 182
— IMAP, 199
— IP, 179
— IPng, 183
— IPv4, 183
— IPv6, 183
— NNTP, 206
— NTP, 192
— POP, 199
— přihlašovacı́, 16
— přı́stupový, 233
— SMTP, 179, 196
— SSH, 16, 212
— SSL, 219
— TCP, 179, 185
— TCP/IP, 178, 184
— Telnet, 16, 234
— UDP, 179, 184
— UUCP, 178, 196
— X, 223
— XDMCP, 230
— XLFD, 237
proudový editor, 133
předánı́ argumentů, 86
předchůdce, 28, 29
přejmenovánı́ souboru, 40
překlad
— adres, 182
— nerekurzivnı́, 189
— rekurzivnı́, 189
— znaků, 148
překrývánı́ oken, 224
přenos, 170
— dat, 186
— nespojovaný, 183
— nespolehlivý, 183
— spojovaný, 185

255
— spolehlivý, 185
přenositelnost, 4
přepı́nač, 19
přepnutı́ kontextu, 68
přesměrovánı́, 73, 92, 127
— výstupu, 92
přesunutı́
— na pozadı́, 74
— souboru, 40
přidělovánı́
— dynamické, 182
— statické, 182
přihlášenı́, 207
— lokálnı́, 14
— vzdálené, 14
přihlašovacı́
— protokol, 16
— shell, 128
přı́kaz, 86
— agregovaný, 91
— atomický, 91
— cyklu, 113
— kolona, 96
— podmı́něný, 113, 116
— prázdný, 151
— přesunu, 154
— spuštěnı́, 18
přı́kazový
— interpret, 6, 85
— — proměnné, 105
— režim, 7, 151, 152
přı́kazy shellu
— alias, 129
— bg, 74, 74, 75, 79, 86
— break, 119, 125
— case, 117, 117
— cd, 33, 33, 34, 36, 86, 111
— continue, 119
— exit, 18, 18, 86, 126
— export, 108, 108, 127
— fg, 75, 75, 86
— for, 118, 118, 119, 125,
148, 149
— if, 116, 116–118
— let, 120, 120
— logout, 18, 18, 86
— readonly, 109, 109
— read, 125, 125

— return, 125, 126, 126
— select, 113, 125, 125, 126
— set, 111
— shift, 124, 124
— ulimit, 129
— umask, 56, 56, 57, 86
— unalias, 129
— unset, 106
— until, 118, 119
— while, 118, 119, 120
přı́loha, 197
přiřazenı́ hodnoty, 105
přı́stup náhodný, 41
přı́stupová práva, 27
přı́stupový protokol, 233

R
rámec, 157
rastrové zařı́zenı́, 221
reakce
— na kontext, 150
— na signál, 77
region, 163
registr, 162, 163
regulárnı́ výraz, 38, 102, 119,
140, 145, 154, 202
— modernı́, 141
— rozšı́řený, 140
— staršı́, 141
rekurzivnı́
— download, 219
— překlad, 189
— režim, 214
— výpis, 35
relativnı́ cesta, 32, 87, 121
remote login, 14
resolver, 189
resource, 1
reverznı́
— doména, 190
— překlad, 190
režim
— aktivnı́, 211
— binárnı́, 210
— interaktivnı́, 40
— jednouživatelský, 13, 70
— ladicı́, 113

256
— pasivnı́, 211
— poslednı́ho řádku, 151
— přı́kazový, 7, 151, 152
— rekurzivnı́, 214
— řádkový, 208
— spuštěnı́ shellu, 128
— textový, 210
— vı́ceuživatelský, 13, 70
— vkládacı́, 151, 152
— znakový, 208
rodičovský proces, 68
root, 14, 30
roura, 78, 96, 98, 185, 201
— pojmenovaná, 98, 185
— uzavřená, 97
rozdělenı́, 161
rozhranı́, 1, 3, 225
— sı́t’ové, 185
— uživatelské, 3, 225
rozlišenı́, 229
runlevel, 64
— halt, 64
— reboot, 64

Ř
řádek, 132
— stavový, 158
— ukončovánı́, 170
řádkový režim, 208
řešitel, 189
řetězec, 132
— znaků, 105
řı́zenı́ přı́stupu, 56

S
screen, 222
sdı́lená pamět’, 78
sdı́lenı́ účtů, 193
sekce dokumentace, 21
sekundárnı́
— prompt, 112
— server, 189
separátor, 91
serializace, 138
server, 187

Rejstřı́k pojmů
— cache, 189
— primárnı́, 189
— sekundárnı́, 189
— souborový, 194
session, 5, 228
sezenı́, 5, 228
— souběžné, 5
seznam
— argumentů, 145
— nabı́dek, 125
— řı́zenı́ přı́stupu, 56
shell, 6, 7, 85
— interaktivnı́, 129
— nadřı́zený, 108
— neinteraktivnı́, 129
— podřı́zený, 108
— přihlašovacı́, 128
— režim spuštěnı́, 128
shutdown, 79
scheduler, 67
schránka, 234, 242
signál, 75, 77
signály
— SIGABRT, 77
— SIGALRM, 77, 90
— SIGCONT, 77, 79, 120
— SIGFPE, 77
— SIGHUP, 77
— SIGCHLD, 77, 78
— SIGILL, 77
— SIGINT, 77
— SIGKILL, 77, 78, 79
— SIGPIPE, 77, 97
— SIGQUIT, 77
— SIGSEGV, 77
— SIGSTOP, 77, 78, 79, 162
— SIGTERM, 77, 79
— SIGTRAP, 77
— SIGUSR1, 77
— SIGUSR2, 77
signatura, 200
sı́t’
— počı́tačová, 177
— terminálová, 177
sı́t’ová cesta, 195
sı́t’ové
— oznámenı́, 181
— rozhranı́, 185

skládánı́ barev, 236
skript, 85, 121, 147
— hlavička, 121
— inicializačnı́, 128
— tělo, 121
skupina, 48, 57
— primárnı́, 48
— procesů, 80
slitı́, 134
sloučenı́ řádků, 154
služba
— BBS, 217
— DNS, 187
— nešifrovaná, 16
— NFS, 194
— NIS, 193, 194
— šifrovaná, 16
— WWW, 217
směrovánı́, 177
snı́ženı́ priority, 76
socket, 78, 99, 185
softwarové rozhranı́, 1
souběžné sezenı́, 5
soubor, 4, 26, 27
— adm. informace, 27
— adresářový, 29
— binárnı́, 38
— data, 27
— datový, 26, 27
— hard link, 45
— jméno, 27
— kvantifikovaný, 99
— link, 34, 45, 56
— metadata, 27
— neviditelný, 31
— obsah, 27
— opravný, 136
— otevřený, 92
— reference, 32
— sdı́lenı́
— — metadat, 45
— — obsahu, 45
— speciálnı́, 26, 41, 98
— spustitelný, 34, 86
— symbolický link, 45, 56
— textový, 37, 132
— vlastnı́k, 27
— vstupnı́, 93

Rejstřı́k pojmů
— výstupnı́, 93
souborový
— server, 194
— systém, 26, 27
— — kořenový, 42
— — reálný, 28
— — virtuálnı́, 28
součin logický, 57, 59
speciálnı́
— adresář, 32
— buffer, 155
— soubor, 26, 41, 98
spı́cı́ proces, 72
spoje, 177
spojenı́, 186, 230
správa
— událostı́, 222
— zdrojů, 222
správce oken, 122, 224, 245
spuštěnı́ programu, 18
stabilnı́ série, 8
standard
— ACL, 56
— ISO, 132
— MIME, 196, 197
— POSIX, 4, 48
— SVID, 4
— UTF, 132
— XPG3, 4
standardnı́
— chybový výstup, 92
— vstup, 92, 127
— výstup, 92
stavový řádek, 158
stı́nové heslo, 49, 64
stránka kódová, 167, 169, 170
stratum, 192
strom, 29
— adresářů, 29
struktura adresářů, 29
subdoména, 188
subgenerace jádra, 8
substituce
— podle vzoru, 146
— řetězce, 146
superuživatel, 14
symbolická práva, 52
symbolické jméno, 187

257
symbolický
— link, 45, 56
— název, 236
— odkaz, 45, 56
synchronizace času, 192
synovský proces, 68
systém, 7
— distribuovaný, 4
— interaktivnı́, 3
— maker, 164
— makrojádrový, 3
— mikrojádrový, 3
— monolitický, 3
— multiprocesový, 3, 5
— multiuživatelský, 3, 5
— neinteraktivnı́, 3
— operačnı́, 1
— procesů, 67
— souborový, 26
— vı́ceúlohový, 4, 5
— vı́ceuživatelský, 4, 5
— zdroje, 1
systémové zdroje, 1
systémový
— čas, 20
— log, 66
— proces, 69
— šum, 42
— uživatel, 14

Š
šifrovánı́, 203
šifrovaný kanál, 214

T
tabulka deskriptorů, 92, 98
tělo
— dopisu, 196, 197
— skriptu, 121
terminál, 3, 5, 6
— emulátor, 6
— hard-copy, 7
text, 132
— prostý, 132
— slitı́, 134

— třı́děnı́, 134
textový
— editor, 122, 131, 133
— — celoobrazovkový, 131
— režim, 210
— soubor, 132
thread, 68
timesharing, 5
tok datový, 96
translace, 239
třı́da objektů, 234, 235
třı́děnı́, 167
— řádků, 134
třı́dy adres, 180
typ
— adresy, 183
— přı́lohy, 197
— sezenı́, 228

U
účet, 14
— sdı́lenı́, 193
událost, 222, 223
— chyba, 223
úloha, 5
uniformnı́ lokátor, 218
unikátnı́ řádky, 134
úniková klávesa, 208
upload, 209
upovı́daný režim, 41
úroveň startu, 64
utilities, 6
uvozovky, 103
uzavřená
— kolona, 97
— roura, 97
uzel, 29
— vnitřnı́, 29
uživatel
— běžný, 14
— efektivnı́, 69, 71
— root, 14
— systémový, 14
uživatelská
— funkce, 126
— maska, 55, 60
— nabı́dka, 224

258
uživatelské
— jméno, 14, 48
— rozhranı́, 3, 225
uživatelský
— limit, 78, 129
— proces, 69
— účet, 49

V
vedlejšı́ mód, 158
vedoucı́ skupiny, 71
verbose mode, 41
vertikálnı́ rozdělenı́, 161
veřejný klı́č, 203
věta, 153
virtuálnı́ plocha, 224
vkládacı́ režim, 151, 152
vlákno, 68
— jádra, 69
vlastnická skupina, 57
vlastnı́k, 48, 50, 57
— souboru, 27, 50, 57
vnitřnı́ uzel, 29
volánı́
— funkce, 127
— jádra, 7, 70
— — __clone(), 68
— — alarm(), 90
— — execve(), 68, 69, 80
— — exit(), 74
— — fork(), 68, 68, 69, 80,
92
— — mknod(), 98
— — pause(), 90
— — pipe(), 96
— — setpgrp(), 80, 80
— — wait(), 78, 78
vrstevná architektura, 25, 179,
222
vrstva
— aplikačnı́, 179
— sı́t’ová, 179
— sı́t’ového rozhranı́, 179
— transportnı́, 179, 184
vstupnı́
— data, 92
— soubor, 93

Rejstřı́k pojmů
vyhledávánı́, 154
výmaz souboru, 40
výměna dat, 177
vymezenı́ atributu, 234
výpis rekurzivnı́, 35
vypršenı́ klı́če, 233
výraz regulárnı́, 38, 102, 119,
140, 145, 154, 202
výřez textu, 242
výstupnı́
— data, 92
— soubor, 93
vytvořenı́ záplaty, 136
využité jednotky, 62
vzdálená cesta, 214
vzdálené přihlášenı́, 14, 207
vzdálený
— hostitel, 221
— přı́stup, 177
vzor, 117, 143

W
whitespace, 18
window, 157
— manager, 224

zavaděč, 42
záznam, 56
— implicitnı́, 60
— nastavenı́, 58
— odejmutı́, 58
— operace, 58
— změna, 58
zdroje, 1, 222
zdrojový kód, 9
zkratka, 245
změna obsahu, 105
značka, 154, 155
znak, 131
— návrat vozı́ku, 170
— nový řádek, 132, 170
— okrajový, 137
— tabulátor, 132
znakové zařı́zenı́, 41
znakový režim, 208
zobrazovacı́ zařı́zenı́, 222
zombie, 78
zpětná smyčka, 181
zpracovánı́ sloupců, 137
zřetězenı́, 141
ztrátová komprese, 174

Ž
X
X, 222
— klient, 223
— protokol, 223
— server, 222

Z
začátek řádku, 144
zakrytı́, 42
záplata, 136
zarovnávánı́, 159
zařı́zenı́
— blokové, 41
— rastrové, 221
— znakové, 41
zası́lánı́ zpráv, 78
zástupný název, 245
zásuvka, 78, 99, 185

žádost, 230
životnı́ cyklus, 2

