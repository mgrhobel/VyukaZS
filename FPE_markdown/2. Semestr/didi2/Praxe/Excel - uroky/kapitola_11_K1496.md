---
title: "kapitola_11_K1496.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/didi2/Praxe/Excel - uroky/kapitola_11_K1496.pdf"
date: 2009-04-29
type: PDF (text-based)
---

KAPITOLA 11
Vzorce pro půjčky a investice
V této kapitole jsou následující témata:


Představení základního principu časové hodnoty peněz



Vysvětlení finančních pojmů



Použití základních finančních funkcí



Výpočet úroků a základních složek platby



Převod mezi různými typy úrokových sazeb



Omezení finančních funkcí Excelu



Výpočet ceny a zisku z dluhopisů

Je celkem bezpečné se vsadit, že nejčastější použití Excelu se týká peněžních kalkulací.
Každý den dělají lidé statisíce finančních rozhodnutí, která počítají v tabulkových procesorech. Tato rozhodnutí sahají od nejprostších (Mohu si dovolit koupi nového auta?) až
po složité (Povede nákup společnosti XYZ ke kladnému cash flow v následujících osmnácti
měsících?). Toto je první ze tří kapitol týkajících se peněžních výpočtů, které lze provádět
pomocí Excelu.

Finanční principy
Než začnete používat finanční funkce v Excelu, musíte znát některé základní principy.
Tyto principy nejsou výsadou Excelu, ale jejich znalost je nutnou podmínkou pro konstrukci finančních vzorců. Jestliže jste v peněžnictví a v souvisejících pojmech zběhlí,

K1496.indb 283

6.2.2008 16:07:28

284

Část III – Finanční výpočty

můžete tyto pasáže projít jen zběžně. Pokud je pro vás tvorba finančních vzorců novinkou, ujistěte se, že dobře chápete následující pojmy.

Časová hodnota peněz
Princip Časové hodnoty peněz jednoduše znamená, že peníze mají různou hodnotu
v závislosti na čase. Nejde o čas během dne, ale o čas relativní vůči tomuto okamžiku
(nebo vůči jinému definovanému času). Pokud vám dám v tuto chvíli 1 000 korun, mají
hodnotu přesně 1 000 korun. Jestliže vám dám 1 000 korun za rok, budou tyto peníze mít
hodnotu 1 000 v okamžiku, kdy vám je dám, avšak dnes bude jejich hodnota jiná.
Kdybyste měli těch 1 000 korun dnes, mohli byste je dát na spořicí účet, investovat do
akcií a dluhopisů nebo se vydat na flám. Měli byste nad danými penězi kontrolu a mohli
byste je nechat pro vás pracovat. Vzhledem k tomu, že ty peníze nedostanete dříve než
za rok, mají pro vás nyní menší hodnotu. Ve skutečnosti bude pro vás patrně lepší dostat
méně, ale již dnes.
Praktické důsledky zavedení Časové hodnoty peněz jsou:


Banky si počítají a vyplácejí úroky.



Loterie vám vyplatí méně, když si vyzvednete celou částku naráz.



Obchodníci vám dají slevu, když zaplatíte před termínem.

Cash in a cash out
Všechny finanční vzorce stojí na cash flow: tok peněz od vás (cash out – platby) a tok
peněz k vám (cash in – příjmy). Dokonce i ty finanční transakce, u nichž se zdá, že se jich
cash flow netýká, je ve skutečnosti obsahují. Koupíte-li auto na kreditní kartu, dostanete
auto a banka záruku. Kde jsou zde ty peníze? Z finanční perspektivy vám banka dává
peníze na koupi auta (kladný cash flow vzhledem k vám) a vy v budoucnu tyto peníze
splatíte (záporný cash flow vzhledem k vám). Skutečnost, že peníze byly použity na koupi
auta, nemění finanční transakci na pozadí. Vždy uvažujte v pojmech cash in a cash out.
První rozhodnutí, které děláte při tvorbě finančního vzorce, je, kdo se vlastně ptá.
Protože musíte přiřadit cash flow kladné či záporné znaménko, musíte vědět, čí kapsy se
bude tok peněz týkat:




Když kupujete dům a počítáte své splátky hypotéky, cash flow se týká vás:


Když si půjčíte peníze na dům, jde o kladný cash flow.



Když splácíte hypotéku, jde o záporný cash flow.

Provádí-li kalkulaci banka, jsou toky peněz opačné.

Ve finančních vzorcích Excelu jsou kladné cash flow zobrazeny jako kladná čísla a záporné cash flow jako záporná čísla.
Tip: Když vzorec vrací výsledek, o němž jste si jisti, že je špatně, podívejte se nejprve na znaménka před hodnotami cash flow.

K1496.indb 284

6.2.2008 16:07:28

Kapitola 11 – Vzorce pro půjčky a investice

285

Odpovídající časové úseky
Běžným problémem, na nějž můžete narazit při práci s finančními funkcemi v Excelu,
je nesoulad časových intervalů. Princip je prostý, ale často jej lidé přehlížejí. Jednoduše
řečeno musí časový úsek, který pokrývá vaše splátka, odpovídat časovému úseku vaší
úrokové sazby. Jestliže do finanční funkce zadáváte měsíční splátku a roční úrokovou
sazbu, bude výsledek chybný. V tomto případě musíte převést úrok na měsíční sazbu, aby
odpovídala frekvenci splátek.
Příklady v této kapitole se s problémem sladění časových úseků vyrovnávají explicitně.
Když uvidíte úrokovou sazbu dělenou 12, jde pravděpodobně o roční úrok převáděný na
měsíční sazbu.

Načasování první splátky
Poslední skutečnost, kterou musíte mít na paměti při finančních výpočtech, je načasování první splátky. Někdy se první splátka provádí okamžitě. Obyčejně se však první splátka
posílá po uplynutí prvního měsíce (nebo po nějakém jiném sjednaném období). Jestliže
například dostanete půjčku na auto 15. května, pravděpodobně nebudete muset platit
poprvé dříve než 15. června.
Ve vzorcích v Excelu je v mnoha funkcích načasování první splátky v parametru Typ:


Platíte-li první splátku pozadu (po prvním období), použijte pro Typ hodnotu 0 (nula),
což je většinou výchozí nastavení.



Platíte-li první splátku dopředu, použijte pro Typ hodnotu 1.

Základní finanční funkce v Excelu
Excel má pět základních finančních funkcí: SOUČHODNOTA, BUDHODNOTA,
PLATBA, ÚROKOVÁ.MÍRA a POČET.OBDOBÍ. Nyní si rozebereme každou z nich
a ukážeme si příklady.
Poznámka: Všechny tyto funkce mají společné to, že poskytují různé pohledy na tutéž situaci.
Mnoho parametrů těchto funkcí je stejných.

KAPITOLA 11
Vzorce půjček a investic

Poznámka: Záloha se nebere jako pravidelná splátka, takže neovlivňuje to, jakou hodnotu
pro parametr Typ zadáte. Mnoho příkladů v této kapitole používá zálohy a rozebírá práci
s nimi.

Výpočet současné hodnoty
Funkce SOUČHODNOTA vrací současnou hodnotu budoucích financí. Víme, že peníze
v budoucnosti mají jinou hodnotu než v tuto chvíli. Tato funkce nám řekne, jakou hodnotu mají peníze v budoucnosti dnes. Syntaxe funkce vypadá takto (povinné parametry
jsou tučně):
SOUČHODNOTA(sazba;pper;splátka;bud_hod;typ)

K1496_03.indd 285

6.2.2008 16:25:50

286

Část III – Finanční výpočty

Příklad nám ukáže současnou hodnotu pravidelných budoucích příjmů, kterým se někdy
říká anuita. Každý rok dostanete jednu splátku ve výši 24 000 Kč. Hodnota těchto splátek
v tuto chvíli činí 135 605,35 Kč.
=SOUČHODNOTA(0,12;10;24000;0;0)

Jinými slovy, kdyby vám plátce nabídl v tuto chvíli více než 136 000 Kč (aby vám nemusel
platit v budoucnosti), vzali byste to. Kdyby nabídl méně, odmítli byste a brali pravidelné
splátky.
Na CD: Soubor se všemi ukázkami z tohoto oddílu naleznete na doprovodném CD pod
názvem základní finanční vzorce.xlsx.

Možná jste si všimli, že v předchozím vzorci se odkudsi vzal úrok (12%). Funkce
SOUČHODNOTA se obvykle používá na zjištění, jakou má konkrétní částka v budoucnosti hodnotu dnes. V takových situacích není přesná úroková sazba k dispozici.
Poznámka: Je mnoho možností, jak určit úrok, a velmi to závisí na vaší osobnosti. Někdo vám
řekne, abyste použili úrokovou sazbu, jakou by vám dala vaše banka, kdybyste si bez zástavy
půjčili peníze. Jiný napoví, abyste úrokovou sazbu určili podle toho, kolik byste vytěžili z nerizikové investice, například do amerických státních dluhopisů. V tomto příkladě používám
úrokovou sazbu, které byste dosáhli při investici do akcií – protože vím, že jste inteligentní
investoři.

Parametry finančních funkcí
Pět základních finančních funkcí v Excelu má mnoho společných parametrů. Zde máte
jejich seznam a popis:


Sazba: Úroková sazba vyjádřená v procentech, kterou platíte za půjčku nebo používáte na přepočítání budoucích cash flow.
Období úroku musí odpovídat období Pper a Splátky.



Pper: Počet období. Může jít o počet splátek půjčky nebo o počet roků, po které máte
peníze na spořícím účtu.
Počet období musí být vyjádřen ve stejných jednotkách jako Sazba a Splátka.
Například 30letá hypotéka s měsíčními splátkami bude mít Pper 360. Počet období je
360 měsíců, nikoli 30 roků.



Splátka: Výše splátky. U těchto finančních funkcí musí být splátky konstantní a v pravidelných intervalech.
Splátka se obvykle skládá ze splátky jistiny a z úroku.



Bud_hodn: Hodnota v budoucnosti. Poslední cash flow, které vyrovná celou transakci.
V mnoha případech transakci ukončí platby (například doplacení půjčky), takže žádná
budoucí hodnota neexistuje.



Souč_hodn: Současná hodnota. První cash flow, které zahajuje transakci, například
půjčka peněz nebo uložení úspor na spořící účet.
Je-li transakce tvořena pouze splátkami, patrně žádná současná hodnota neexistuje.



K1496_03.indd 286

Typ: Závisí na tom, zdali jsou splátky placeny pozadu (0 nebo výchozí) nebo dopředu (1).

6.2.2008 16:26:02

Kapitola 11 – Vzorce pro půjčky a investice

287

Viz předchozí pasáž „Finanční principy“, kde jsou podrobné informace o Typu.


Odhad: Aproximace výsledku. Když počítáte úrokovou sazbu, Excel musí provést
mnoho iterací, aby získal odpověď.
Můžete Excelu pomoci tak, že zadáte parametr Odhad, který je blízko očekávanému
výsledku.

Volbou 12% v předchozím příkladě říkáme, že můžete vzít 136 000 Kč, investovat je tak,
abyste získali 12% výnos, a budete ve stejné situaci, jako kdybyste prostě jen čekali na
splátky po 24 000 Kč.
Poznámka překladatele: A ty opět postupně investovali na zmíněný úrok!
Jestliže vám plátce nabídne 140 000 Kč, můžete je investovat a budete na tom lépe.
Obraťme list a podívejme se na situaci, kdy máte někomu po deset roků platit 24 000 Kč
ročně. Vzorec vypadá takto:
=SOUČHODNOTA(0,12;10;-24000;0;0)

Místo kladného cash flow je v tomto vzorci záporné cash flow. Výsledek 135 605,35 Kč
má také opačné znaménko než předchozí výsledek. V obou příkladech souhrn všech
splátek dokončuje transakci a není zde proto žádná budoucí hodnota. Používáme výchozí
parametr Typ (0). Parametry Bud_hodn a Typ jsou nepovinné, ale zařazujeme je kvůli
srozumitelnosti výkladu. Na obrázku 11.1 máte tyto příklady v sešitě.

KAPITOLA 11
Vzorce půjček a investic

Poznámka: Pro zjednodušení vám vzorce v této kapitole předkládám s přímo zadanými hodnotami. Ve většině případů byste jako parametry použili odkazy na buňky.

Obrázek 11.1 Některé výpočty současné hodnoty
Upozornění: Když vkládáte do parametrů funkcí číselná data, nedávejte mezi tisíce mezeru.
Nepište například 1 000, ale 1000. V opačném případě může docházet k chybě.

K1496_03.indd 287

6.2.2008 16:26:03

288

Část III – Finanční výpočty

Současná hodnota jednorázové částky
Předchozí příklady se týkaly řady budoucích splátek, ale někdy dochází k jediné velké
platbě v budoucnu.
Pro další příklad předpokládejme, že vám bohatý strýček chce dát 2 000 000 Kč, ale
nemůžete si je vybrat, dokud vám nebude 40 roků. Jestliže je vám nyní 25 let, je hodnota
tohoto budoucího daru v tuto chvíli 630 483,41 Kč a vypočtete ji tímto vzorcem:
=SOUČHODNOTA(0,08;15;0;2000000)

Celá platba směřuje k vám (kladná hodnota 2 000 000 Kč) a dojde k ní od nynějška za 15
let. Předpokládáte, že kdybyste měli nějaké peníze nyní, mohli byste investovat a vydělat
8%. Vzhledem k tomu, že nedochází k žádným splátkám, nemá parametr Typ smysl.
Výsledkem vzorce je, že kdybyste měli 630 000 Kč a investovali je s úrokem 8%, měly by
za 15 let hodnotu 2 000 000 Kč. Viz obrázek 11.2.

Obrázek 11.2 Výpočet současné hodnoty jednorázové částky

Současná hodnota anuitních plateb s následnou jednorázovou částkou
V některých případech po pravidelných budoucích platbách následuje velká platba.
Předpokládejme, že váš švagr chce, abyste investovali do jeho společnosti zabývající se
čištěním koberců. Když nyní vložíte do firmy 1 000 000 Kč, bude vám po pět roků platit
4 000 Kč měsíčně a na konci pátého roku vám zaplatí 1 200 000 Kč. Chcete-li zjistit, jestli
je to výhodný obchod, určete současnou hodnotu všech těchto budoucích příjmů:
=SOUČHODNOTA(0,1/12;60;4000;1200000;1)

Podívejme se na každý z těchto parametrů (viz obrázek 11.3):

K1496_03.indd 288



Zjistili jste, že jinde můžete vydělat 10 %, takže úroková sazba bude 10%.



Všechny parametry musí být pro stejný časový úsek. Vzhledem k tomu, že splátka je
4 000 Kč měsíčně, všechny parametry je potřeba převést na měsíce:

6.2.2008 16:26:04

Kapitola 11 – Vzorce pro půjčky a investice



Parametr Sazba dělíme 12 (kvůli 12 měsícům).



Parametr Pper vyjádříme jako 60 (60 měsíců – nikoli 5 jako 5 let).

289



Velikost splátky a jednorázová částka byly domluveny při dojednávání podmínek.



Parametr Typ je 1, protože předpokládáme, že první splátka bude ihned (dopředu).

Obrázek 11.3 Výpočet současné hodnoty anuitních splátek s jednorázovým doplatkem

Tip: Můžete vkládat jiné hodnoty parametrů, dokud nenajdete řešení, které bude výhodné,
a pak dát svému švagrovi protinávrh. Můžete dokonce využít Hledání řešení v Excelu (Data →
Datové nástroje → Analýza hypotéz → Hledání řešení) a vyhledat hodnotu parametru, která
povede k požadované současné hodnotě.

Výpočet budoucí hodnoty
Budoucí hodnota je opačná strana mince při práci s časovou hodnotou peněz. Říká,
jakou bude mít hodnotu známé množství peněz (nebo známá série plateb) v určitém
okamžiku v budoucnosti. Syntaxe funkce BUDHODNOTA je uvedena níže. Parametry
vypsané tučně jsou povinné.

KAPITOLA 11
Vzorce půjček a investic

Vzorec nám říká, že hodnota všech budoucích plateb je 919 176,63 Kč. Podle podmínek
dohody a za předpokladů, které jste provedli, je vidět, že když svůj milion investujete
jinam, vyděláte víc.

BUDHODNOTA(sazba;pper;splátka;souč_hod;typ)

Budoucí hodnota splátek
Pro tento příklad předpokládejme, že začnete na spořicím účtu střádat dítěti na studia.
Počínaje dalším měsícem budete každý měsíc ukládat 1 000 Kč a dostanete úrok 3%.
Následující vzorec říká, že za 18 let bude na účtu 285 940,35 Kč (viz obrázek 11.4).
=BUDHODNOTA(0,03/12;18*12;-1000;0;0)

K1496_03.indd 289

6.2.2008 16:26:04

290

Část III – Finanční výpočty

Obrázek 11.4 Výpočet budoucí hodnoty splátek
Úrok 3 % ročně převedeme na měsíční sazbu a 18 roků na měsíce. Současná hodnota
žádná není, protože jste účet právě otevřeli, a Typ je 0, protože začnete platit od příštího
měsíce (pozadu).

Budoucí hodnota jednorázové částky
Další příklad počítá budoucí hodnotu peněz, k nimž nehodláte nic přidávat ani z nich
nic vybírat.
Předpokládejme, že převedete své úspory na penzi na účet, kde vám dají lepší výnos,
a nehodláte už dále nic přidávat. Následující vzorec vypočítá, jakou hodnotu bude mít
vašich 400 000 Kč za 15 let, kdy hodláte odejít do důchodu (viz obrázek 11.5):
=BUDHODNOTA(0,08;15;0;-400000;0)

Obrázek 11.5 Výpočet budoucí hodnoty jednorázové částky

K1496_03.indd 290

6.2.2008 16:26:05

Kapitola 11 – Vzorce pro půjčky a investice

291

Zaokrouhlování ve finančních vzorcích
Když pracujete s finančními vzorci, určitě narazíte na problém se zaokrouhlováním.
Excel nabízí několik funkcí pro zaokrouhlování, mezi něž patří ZAOKROUHLIT, ROUNDUP
a ROUNDDOWN.
Aby se chyby nesčítaly, zaokrouhlete pouze výslednou vypočtenou hodnotu. Jinými slovy,
nezaokrouhlujte žádný mezivýsledek, který nepotřebujete do výstupu.
Obecně platí, že při finančních výpočtech se jen málokdy zobrazují více než dvě desetinná
místa a často se zaokrouhluje na celé koruny. Pro mezivýsledky to znamená zformátování
na haléře (nebo na koruny či jinak dle potřeby), čímž zůstane číslo zcela přesné pro následné výpočty.
V některých případech budou výpočty závislé na aproximovaných datech nebo na datech
závislých na subjektivním názoru či upravených datech (například hodnoty nájmů).
V profesionální praxi je běžné psát zaokrouhlená čísla, aby nedocházelo k matení čtenářů.
Můžete mít například nájem 4371,96 Kč za čtvereční metr, což je místní průměr. Když tuto
cenu aplikujete na plochu 142,8 m2, dostanete celkový nájem ve výši 624 315,89 Kč. Ale
cena pronájmu za metr čtvereční je ve skutečnosti aproximace (může být od 4 000 do
5 000 Kč/m2). Abyste nedávali mylný dojem velké přesnosti, patrně zaokrouhlíte výslednou částku za pronájem na nejbližších tisíc, nebo dokonce deset tisíc korun.
Jedním z problémů přesnosti, kterou nabízejí moderní technologie, je nebezpečí, že
u odhadů sklouznete do příliš velkého rozlišení.

Tento příklad předpokládá, že dosáhnete výnosu 8 % ročně. Hodnota –400 000 Kč jsou
vaše úspory, které uložíte. Výsledkem je 1 268 867,65 Kč, což je částka, kterou na závěr
dostanete.

Budoucí hodnota splátek a jednorázové částky

V následujícím příkladu budete měsíčně splácet 18 000 Kč za svou hypotéku na
3 000 000 Kč. Je-li úrok 5,75%, vypočítá vzorec, kolik budete za svůj dům dlužit po pěti
letech (viz obrázek 11.6):
=BUDHODNOTA(0,0575/12;5*12;-18000;3000000;0)

Splátky jsou měsíční, takže ostatní parametry je třeba převést rovněž na měsíce – roční
úrok je vydělen 12 a Pper je v létech vynásobených 12. Aktuální stav hypotéky je v tomto
příkladu vyjádřen jako příjem, ačkoliv ve skutečnosti žádný příjem nemáte. Ten jste měli
ve chvíli, když jste koupili dům. Tedy, někdo vám zaplatil velkou částku peněz za slib, že
mu je vrátíte, a vy jste šli a koupili si za ty peníze dům. Vzhledem k tomu, že váš problém
se týká doby od této chvíle do okamžiku za pět let, nebere v potaz čas, kdy jste skutečně
obdrželi peníze.

K1496_03.indd 291

KAPITOLA 11
Vzorce půjček a investic

Je také možné vypočíst budoucí hodnotu, máte-li již nějakou částku a hodláte k ní přidávat nebo z ní čerpat.

6.2.2008 16:26:05

292

Část III – Finanční výpočty

Obrázek 11.6 Výpočet budoucí hodnoty splátek a jednorázové částky
Tip: Jeden ze způsobů, jak na problém nahlížet, spočívá v tom, že vám někdo nyní půjčil
3 000 000 Kč, abyste umořili svou hypotéku, ačkoliv ve skutečnosti se nic takového nestalo.
Částka –2 748 701,94 Kč je vypočítaný zbytek k doplacení po pěti létech.

Výpočet splátek
Funkce PLATBA počítá splátky, které jsou potřeba k tomu, abyste snížili postupně určitou částku (souč_hod) na nulu nebo na nějakou jinou částku (bud_hodn). Syntaxe je
následující:
PLATBA(sazba;pper;souč_hod;bud_hod;typ)

Výpočet splátek půjčky
Když si půjčujete peníze, klíčová je velikost měsíční splátky.
V našem příkladě si chcete koupit auto za 640 000 Kč a potřebujete vypočítat, jaké budou
měsíční splátky. Máte vlastní prostředky 80 000 Kč a prodejce vám nabízí splátkový prodej na 4 roky a úrok 2,1% (viz obrázek 11.7).
=PLATBA(0,021/12;4*12;560000;0;0)

Vzorec vrací 12 173,73 Kč. Takže pokud utáhnete takovou splátku každý měsíc, můžete
vypůjčených 560 000 Kč vrátit v 48 splátkách.
Upozornění: Dostanete-li při použití kterékoliv z těchto finančních funkcí chybu #NUM!
nebo výsledek, který je na první pohled špatně, projděte si nejprve směry cash flow. Pečlivě
zkoumejte, kam částky v uváděných příkladech tečou, abyste lépe pochopili, jaká dávat parametrům znaménka.

K1496_03.indd 292

6.2.2008 16:26:05

Kapitola 11 – Vzorce pro půjčky a investice

293

Obrázek 11.7 Výpočet splátky půjčky

Výpočet plateb v důchodu
Do některých výpočtů plateb je nutné zahrnout budoucí hodnotu.
V tomto příkladě předpokládejme, že máte na důchodovém účtu 1 400 000 Kč. Jestliže
potřebujete vybírat měsíční splátky na živobytí po dalších 20 let – a přesto chcete nechat
250 000 Kč svým dědicům – pak vám následující vzorec vrátí, kolik můžete každý měsíc
vybrat (viz obrázek 11.8):
=PLATBA(0,06/12;20*12;-1400000;250000;0)

Jestliže je váš odhad ročního výnosu ve výši 6 % přesný, tak můžete každý měsíc vybrat
9 488,96 Kč a po dvaceti letech budete mít stále ještě na účtu 250 000 Kč.

Funkce ÚROKOVÁ.MÍRA počítá úrok nebo diskontní sazbu budoucích cash flow.
U transakcí, kde není úrok konkrétně dán, může funkce ÚROKOVÁ.MÍRA vypočítat
nevyjádřenou úrokovou sazbu (úrok, který byl použit, ať už jste o tom byli informováni,
nebo ne). Jeho syntaxe je:
ÚROKOVÁ.MÍRA(pper;splátka;souč_hodn;bud_hodn;typ;odhad)

KAPITOLA 11
Vzorce půjček a investic

Výpočet úroků

Obrázek 11.8 Výpočet plateb v penzi

K1496_03.indd 293

6.2.2008 16:26:06

294

Část III – Finanční výpočty

Krátkodobé půjčky
Tyto půjčky mají velmi malou dobu trvání. Obecně je lidé splácí do 14 dní (po výplatě)
a věřitelé si účtují až 300 Kč na každých 2 000 Kč půjčky.
Poznámka překladatele: Tento typ půjček zatím v ČR není naštěstí příliš rozšířen, jde patrně o americkou specialitu. Výsledek připomíná spíše lichvu.
Půjčíte-li si 4 000 Kč a souhlasíte s tím, že za 14 dní vrátíte 4 600 Kč, vypočtete úrokovou
sazbu následujícím vzorcem (viz obrázek 11.9):
=ÚROKOVÁ.MÍRA(1;0;4000;-4600;0;0,01)*365/14

Období je nastaveno na 1, protože je pouze jedna splátka. Období s hodnotu 1 ve skutečnosti reprezentuje 14denní období, takže úrok převedeme na roční sazbu vydělením
14 a vynásobením 365. Výsledek 391% je tak vysoký kvůli tomu, že půjčka je na velmi
krátkou dobu.

Obrázek 11.9 Výpočet úroku při krátkodobé půjčce
Poznámka: Úrokové sazby se často (a v ČR povinně) vyjadřují jako roční procentní sazba nákladů
(RPSN), i když je období půjčky kratší nebo delší než jeden rok. Převod sazeb na RPSN bez ohledu
na délku půjčky vám umožňuje porovnávat různé půjčky. Když budete srovnávat měsíční úroky
s ročními, bude měsíční úrok vypadat mnohem nižší, ale ve skutečnosti tomu tak nemusí být.

Míra výnosů
Běžným použitím funkce ÚROKOVÁ.MÍRA je výpočet míry výnosů na důchodovém
účtu.
Předpokládejme v tomto příkladě, že máte na svém důchodovém účtu na začátku roku
40 000 Kč a na konci roku 62 000 Kč. Každých 14 dní posíláte na účet 200 Kč (za rok 26
splátek). Následující vzorec počítá, jak si vaše investice vede (viz obrázek 11.10):
=ÚROKOVÁ.MÍRA(26;-200;-40000;62000;0;0,01)*26

Funkce ÚROKOVÁ.MÍRA vrací míru výnosu pro jedno z 26 období, a proto je potřeba
ji vynásobit 26, abychom dostali roční míru výnosů 33,62 %.

K1496_03.indd 294

6.2.2008 16:26:06

Kapitola 11 – Vzorce pro půjčky a investice

295

Obrázek 11.10 Výpočet míry výnosů
Poznámka: V několika finančních funkcích je parametr Odhad. Můžete jej vynechat a nechat
Excel, aby použil jeho výchozí hodnotu, nebo jej můžete zadat explicitně. Jestliže je výsledek
daleko od očekávání, zkuste do parametru Odhad vložit jinou hodnotu.

Bezúročné půjčky

KAPITOLA 11
Vzorce půjček a investic

Bezúročné půjčky jsou jen stěží opravdu bezúročné, protože úrok, který by obchodník
dostal za půjčení peněz, započítá do ceny.

Obrázek 11.11 Splátkový kalendář ověří výsledky funkce ÚROKOVÁ.MÍRA

K1496_03.indd 295

6.2.2008 16:26:06

296

Část III – Finanční výpočty

Předpokládejme, že si chcete koupit kožený gauč za 60 000 Kč a máte jej platit ve 12
měsíčních splátkách bez úroků. Malá procházka po obchodech vám však odhalí fakt, že
tentýž gauč můžete pořídit za 50 000 Kč, když jej zaplatíte hotově. Takže v podstatě zaplatíte na úrocích 10 000 Kč za půjčku ve výši 50 000 Kč, neboli úrok 35,07%.
=ÚROKOVÁ.MÍRA(12;-60000/12;50000;0;0;0,01)*12

Výpočet počtu období
Funkce POČET.OBDOBÍ vrací informaci, kolik splátek je potřeba na umoření dluhu
nebo na navýšení účtu na potřebnou velikost. Její syntaxe má tvar:
POČET.OBDOBÍ(sazba;splátka;souč_hodn;bud_hodn;typ)

Počet roků do penze
Jestliže víte, kolik peněz budete v penzi potřebovat, a na svůj důchodový účet si pravidelně spoříte, lze pomocí funkce POČET.OBDOBÍ určit, v jakém věku si můžete dovolit
odejít na odpočinek.
Řekněme, že na penzi potřebujete 1 000 000 Kč a odkládáte si měsíčně 200 Kč. Dále předpokládejme, že na účtu již máte 700 000 Kč. Následující vzorec vrátí počet let, po které
musíte ještě vydržet v práci:
=POČET.OBDOBÍ(0,1/12;-200;-700000;1000000;0)

Za předpokladu, že své úspory hodnotíte úrokem 10%, vrátí funkce POČET.OBDOBÍ
hodnotu 41,8 měsíců (neboli tři a půl roku). Pokud víte, kolik potřebujete na týden, můžete
zkombinovat funkce POČET.OBDOBÍ a SOUČHODNOTA, jako v tomto vzorci:
=POČET.OBDOBÍ(0,1/12;-200;-700000;SOUČHODNOTA(0,1/52;20*52;-2000;0;0);0)

Funkce SOUČHODNOTA se zde používá v parametrech funkce POČET.OBDOBÍ
a předpokládá, že máte úrok 10% (převedený na týdny), že peníze budete vybírat po 20
let (převedeno na týdny), že vystačíte s 2 000 Kč týdně a že vám poté nic nezbude. Pokud
vyžijete ze dvou tisícovek týdně, můžete odejít do penze za 2,4 roku.
Oba vzorce z tohoto oddílu vidíte na obrázku 11.12.

Obrázek 11.12 Funkce POČET.OBDOBÍ při výpočtech penze

K1496_03.indd 296

6.2.2008 16:26:07

Kapitola 11 – Vzorce pro půjčky a investice

297

Předčasné splacení půjčky
V nedávné době mnoho lidí přefinancovalo své hypotéky na bydlení, aby využilo poklesu
úrokových sazeb. Funkce POČET.OBDOBÍ vám může říci, o kolik splátek budete mít
méně, když svou půjčku přefinancujete.
V tomto příkladě předpokládáme hypotéku na 20 let ve výši 2 000 000 Kč na úrok 7,5%
a měsíční splátku 16 111,90 Kč. Jestliže přefinancujete na 5,75 %, ale splátku ponecháte
v původní výši, můžete následujícím vzorcem zjistit, o kolik let se vám splácení zkrátí
(viz obrázek 11.13):
=(20*12)-POČET.OBDOBÍ(0,0575/
12;PLATBA(0,075/12;20*12;2000000;0);2000000;0;0)

V parametru splátka je funkce PLATBA, jež počítá hodnotu 16 111,90 Kč, kterou platíte
na základě existující hypotéky. Odečtením výsledku od 240 (20 let po 12 měsících) zjišťujete, že touto změnou úrokové sazby ušetříte 51 měsíců ze své hypotéky.

Poznámka: Ačkoliv může funkce POČET.OBDOBÍ vracet čísla s desetinami (například 4,26
měsíců), pravděpodobně nebudete platit v okamžiku, kdy uplyne 26 % z měsíce. Místo toho
provedete v pátém měsíci platbu, která bude nižší než předchozí platby.

Výpočet úroku a jistiny

KAPITOLA 11
Vzorce půjček a investic

Obrázek 11.13 Výpočet dopadu předčasného splacení dluhu

V této části kapitoly rozebereme čtyři funkce Excelu, které vám umožňují:


Vypočítat, kolik z určité splátky tvoří úrok a kolik splátka jistiny.



Vypočítat úhrn úroků a jistiny mezi dvěma okamžiky.

Na CD: Soubor s příklady z tohoto výkladu naleznete na doprovodném CD pod názvem úrok
a jistina.xlsx.

K1496_03.indd 297

6.2.2008 16:26:07

298

Část III – Finanční výpočty

Funkce PLATBA.ÚROK a PLATBA.ZÁKLAD
Předpokládejme, že potřebujete znát (nebo vás to prostě jen zajímá), kolik z určité splátky
tvoří úrok a kolik jde na umoření dluhu samotného (jistina). Splátka jistiny, kterou umořujete dluh, je na začátku nižší, protože úrok je vyšší (neboť dlužíte více).
Poznámka: Jestliže máte splátkový kalendář, jsou tyto funkce celkem zbytečné, protože se
můžete prostě podívat do tohoto kalendáře. Funkce PLATBA.ÚROK a PLATBA.ZÁKLAD se nejvíce hodí, když potřebujete zjistit poměr úrok/jistina pro jedinou konkrétní splátku.

Syntaxe těchto dvou funkcí je následující (parametry uvedené tučně jsou povinné):
PLATBA.ÚROK(sazba;za;pper;souč_hodn;bud_hodn;typ)
PLATBA.ZÁKLAD(sazba;za;pper;souč_hodn;bud_hodn;typ)

Stejně jako u všech amortizačních funkcí i zde musí být parametry Sazba, Za a Pper
uvedeny ve stejných časových intervalech. Jestliže je délka půjčky v měsících, parametr
Sazba musí být uveden v měsíční sazbě úroku a v parametru Za (což je období, pro něž
zjišťujete informace) musí být konkrétní měsíc.
Příklad na obrázku 11.14 ukazuje výpočty pro tři splátky v průběhu 30leté hypotéky: pro
první splátku, pro 180. splátku a pro poslední splátku (360. měsíc). Vzorce, které počítají
skladbu splátky č. 1, jsou:
=PLATBA.ÚROK(0,055/12;1;30*12;3500000)
=PLATBA.ZÁKLAD(0,055/12;1;30*12;3500000)

Obrázek 11.14: Výpočet splátky jistiny a úroku pro zvolenou splátku
Vzorce pro ostatní splátky jsou stejné s výjimkou parametru Za, který obsahuje číslo
splátky. Součet výsledků ze funkcí PLATBA.ÚROK a PLATBA.ZÁKLAD je vždy stejný
a odpovídá výsledku funkce PLATBA.
Poznámka: Je zajímavé (a poněkud skličující) si uvědomit, jak malá část první splátky jde na
umořování jistiny.

K1496_03.indd 298

6.2.2008 16:26:08

Kapitola 11 – Vzorce pro půjčky a investice

299

Funkce CUMIPMT a CUMPRINC
Funkce PLATBA.ÚROK a PLATBA.ZÁKLAD vracejí složky úroku a splátky jistiny pro
určitou konkrétní platbu. Funkce CUMIPMT a CUMPRINC poskytují tytéž informace,
ale pro zadanou množinu plateb.
Syntaxe těchto funkcí je následující (všechny parametry jsou povinné):
CUMIPMT(úrok;období;půjčka;začátek;konec;typ)
CUMPRINC(úrok;období;půjčka;začátek;konec;typ)

Následující příklad počítá velikost úroku zaplaceného za hypotéku během roku 2006.
Předpokládá, že hypotéka ve výši 2 200 000 Kč byla uzavřena v říjnu 2004 a její úroková
sazba je 6%.
=CUMIPMT(0,06/12;30*12;2200000;16;27;0)

Leden 2006 reprezentuje 16. splátka a prosinec 2006 je 27. splátka. Úrok zaplacený mezi
těmito dvěma splátkami (včetně), činí 129 166,38 Kč.
Další vzorec počítá, o kolik se za stejné období snížila jistina (29 114,95 Kč):
=CUMPRINC(0,06/12;30*12;2200000;16;27;0)

Na obrázku 11.15 je sešit, který je připraven na výpočet úhrnu úroků a zaplacené jistiny
za libovolný počet splátek. První splátku vložte do buňky B4 a poslední do buňky B5.
Buňka E4 používá funkci CUMIPMT a počítá úhrn úroků, buňka E5 vrací pomocí funkce CUMPRINC zaplacenou jistinu.

KAPITOLA 11
Vzorce půjček a investic

Tip: V tomto listu je splátkový kalendář, takže si můžete výpočty ověřit.

Obrázek 11.15 Funkce CUMIPMT a CUMPRINC

K1496_03.indd 299

6.2.2008 16:26:09

300

Část III – Finanční výpočty

Převod úrokových sazeb
Předchozí příklady v této kapitole používaly zjednodušenou metodu převodu úrokových
sazeb. Používaly buď nominální sazbu, která pěkně odpovídala podmínkám platby, nebo
jsme je odhadli. Předpokládali jsme, že nominální sazby mají stejnou frekvenci jako platby – řekněme měsíční. V takovém případě nebylo potřeba nic převádět.
V příkladech s výnosy, kdy jsme míru výnosů odhadovali (například 8% v penzijním
fondu), nedává přepočet těchto sazeb smysl. Převod odhadu úrokové sazby v těchto
příkladech dává pocit, že odhad je do určité míry přesný, ale on není přesný. Nicméně
v některých případech je potřeba sazbu převést. V tomto oddíle je popis různých typů
sazeb a způsobů jejich převádění.

Typy úrokových sazeb
Existují tři používané názvy úrokových sazeb:


Nominální sazba: Toto je stanovená sazba. Uvádí se v roční sazbě a frekvenci aplikace
během roku – například 6% po měsících.



Roční efektivní sazba: To je skutečná sazba, kterou za rok vyděláte nebo vydáte.
Například nominální sazba 6 % aplikovaná po měsících dává úrok 616,80 Kč z půjčky
10 000 Kč. Efektivní sazba je pak 6,168 %.



Efektivní sazba za období: Tato sazba se aplikuje na jistinu během jednoho aplikačního
období, které je obyčejně méně než rok. Například 6% sazba po měsících dává sazbu za
období 0,5%.

Převodní vzorce
Úrokovou sazbu vyjádřenou některým z těchto tří způsobů lze převést na kterýkoli ze
dvou zbývajících způsobů. Excel nabízí dvě funkce, EFFECT a NOMINAL, které slouží
na převody. Sazba za období je jednoduše podíl nominální sazby a počtu aplikačních
období, takže na ni není potřeba speciální funkce. Syntaxe funkcí NOMINAL a EFFECT je:
EFFECT(nominální_úrok;období)
NOMINAL(efektivní_úrok;období)

Poznámka: Většina bank a finančních institucí (v USA) vyhlašuje úroky nominálně s měsíční
periodou. Ale když se mluví o výnosech z investic nebo se srovnávají úrokové sazby, je běžné
uvádět efektivní sazbu, což usnadňuje porovnávání sazeb. Je vám například jasné, že 12 %
ročně úročeno po měsících je víc než 12 % ročně úročeno po čtvrtletích – ale nevíte (bez
pokročilejší převodní kalkulace) o kolik.

Nominální sazba 12 % po měsících se na sazbu za období převede takto:
=0,12/12

Výsledkem je 0,01, což je 1 % za měsíc. Chcete-li převést tuto sazbu na efektivní, použijte
vzorec:
=EFFECT(0,12;12)

K1496_03.indd 300

6.2.2008 16:26:09

Kapitola 11 – Vzorce pro půjčky a investice

301

Na CD: Soubor s názvem převod úrokových sazeb.xlsx obsahuje příklady z této části kapitoly a naleznete jej na doprovodném CD.

Výsledek 12,6825% reprezentuje skutečný úrok zaplacený nebo vydělaný za rok. Efektivní
sazbu můžete také zjistit pomocí funkce BUDHODNOTA, do níž vložíte současnou
hodnotu –1:
=BUDHODNOTA(0,12/12;12;0;-1)-1

Jestliže víte, že jste minulý rok zaplatili na úrocích 564,10 Kč za půjčku ve výši 10 000 Kč,
můžete vypočítat nominální sazbu následujícím vzorcem:
=NOMINAL(564,1/10000;12)

Výpočet vede k hodnotě 5,5% nominální roční sazby aplikované v měsíčních intervalech.

Omezení finančních funkcí Excelu
Základní finanční funkce Excelu (SOUČHODNOTA, BUDHODNOTA, PLATBA,
ÚROKOVÁ.MÍRA, POČET.OBDOBÍ, CUMIPMT a CUMPRINC) jsou velmi užitečné,
ale mají dvě typická omezení:


Umějí pracovat pouze s jednou úrokovou sazbou.



Umějí pracovat pouze s jednou výší splátky.

Například funkce POČET.OBDOBÍ si neporadí s odchylkami v platbách, které vyplývají
z kalkulací na kreditní kartě. V takových kalkulacích je měsíční splátka založena na omezování nevyrovnané bilance a může pro ni také platit pravidlo minimální splátky.



FVSCHEDULE počítá budoucí hodnotu pro proměnnou úrokovou sazbu.



MÍRA.VÝNOSNOSTI počítá výnosové procento z různých příjmů došlých v pravidelných intervalech.



ČISTÁ.SOUČHODNOTA počítá součet současných hodnot z různých příjmů došlých
v pravidelných intervalech.



MOD.MÍRA.VÝNOSNOSTI, což je upravená funkce MÍRA.VÝNOSNOSTI, bere
v potaz reinvestované prostředky.



XIRR počítá výnosové procento z nepravidelných příjmů.



XNPV počítá čistou současnou hodnotu nepravidelných příjmů.

KAPITOLA 11
Vzorce půjček a investic

Běžným řešením problému proměnných splátek je vytvoření rozvrhu cash flow a další
finanční funkce, které umí zpracovat různé splátky a sazby. Příklady tohoto procesu jsou
v následujících dvou kapitolách. Jen stručně zmiňme funkce, které sem patří:

V situacích, které obnášejí pouze malé změny, můžete finanční funkce Excelu kombinovat a zanořovat.
Na CD: Příklady z této části kapitoly je možné nalézt v souboru rozšíření základních
vzorců.xlsx na doprovodném CD.

K1496_03.indd 301

6.2.2008 16:26:10

302

Část III – Finanční výpočty

Odložený začátek řady pravidelných plateb
V některých případech mohou mít pravidelné platby opožděný začátek. Současnou
hodnotu běžné řady plateb s odloženým začátkem můžete vypočítat zanořením funkcí
SOUČHODNOTA.
V následujícím příkladě dostanete půjčku na podnikání. Můžete si dovolit splácet
7 000 Kč měsíčně a vyjednáte si s bankou odložení první splátky o 12 měsíců. Jestliže
banka dává na 10letou půjčku úrok 8%, vrátí vám následující vzorec částku, kterou si
můžete půjčit (viz obrázek 11.16):

Obrázek 11.16 Výpočet současné hodnoty pravidelných splátek s odloženým začátkem splácení probíhá ve
dvou krocích
Nejprve vypočítáme současnou hodnotu, což je 576 950 Kč. Tuto hodnotu použijeme
jako parametr budoucí hodnoty ve vnější funkci. Vnější funkce sníží dále tuto částku
během odkladného období a vrátí 532 733 Kč. Jinými slovy, když si půjčíte 532 733 Kč
nyní, částka během jednoho roku bez plateb naroste na 576 950 Kč a během deseti let
s měsíčními splátkami 7 000 Kč klesne na nulu.

Ohodnocení řady proměnných plateb
V dalším příkladě vypočítáme současnou hodnotu, když se platby v čase mění.
Předpokládejme, že se chcete vyplatit z leasingu a potřebujete vědět jeho hodnotu.
Leasing je ještě na devět let a splátky jsou rozvrženy takto:


Roky 1-3: 5 000 Kč/měsíc.



Roky 4-6: 6 500 Kč/měsíc.



Roky 7-9: 8 500 Kč/měsíc.

Následující vzorec vypočítá hodnotu leasingu pro úrokovou sazbu 10%:
=SOUČHODNOTA(0,1/12;36;-5000)+SOUČHODNOTA(0,1/12;3*12;0;SOUČHODNOTA(0,1/12;36;-6500))+SOUČHODNOTA(0,1/12;6*12;0;SOUČHODNOTA(0,1/12;36;-8500))

K1496_03.indd 302

6.2.2008 16:26:10

Kapitola 11 – Vzorce pro půjčky a investice

303

Výsledkem je 449 305 Kč, k němuž jsme došli ve třech krocích:


Výpočet současné hodnoty tří let splátek pronájmu.



Další tři roky jsou totožné s předchozím příkladem s odloženým zahájením splátek. Vypočtená současná hodnota splátek se stává budoucí hodnotou další funkce
SOUČHODNOTA. Tato budoucí hodnota je snížena během tříletého období (během
něhož platíte 5 000 Kč).



Poslední tři roky se počítají stejně, ale tentokrát je doba odkladu šest let.

Výpočty s dluhopisy
Excel nabízí v listu funkce, které se používají na výpočty různých aspektů dluhopisů.
Dluhopis je finanční nástroj, kterým jeho kupec půjčuje peníze emitentovi dluhopisu
– obvykle nějaké korporaci nebo vládě. Mnoho z funkcí, které se týkají cenných papírů
(například dluhopisů), je nad rámec této knihy. Ale ukažme si alespoň některé běžnější
funkce z této oblasti.
Na CD: Ukázky z tohoto výkladu jsou v souboru výpočty s dluhopisy.xlsx na doprovodném CD.



Vypořádání: Datum, kdy je cenný papír převeden kupci.



Splatnost: Datum, kdy je půjčka (představovaná dluhopisem) proplacena kupci zpět.



Sazba: Také známá pod pojmem kuponová sazba; úroková sazba, kterou emitent za
dluhopis platí.



Výnos: Úroveň návratnosti, včetně úroků a diskontu (slevy na nákup).



Zaručená cena: Cena, kterou kupec dostane v okamžiku splatnosti cenného papíru
o nominální hodnotě 100 Kč. V běžných případech dostane kupec nominální hodnotu,
takže tento parametr je 100.



Počet plateb: Počet výplat úroků během roku.

Oceňování dluhopisů
Emitenti dluhopisů nastavují jejich parametry před vydáním podle aktuálních podmínek
na trhu. Když se změní podmínky na trhu, cena dluhopisů se také změní.

KAPITOLA 11
Vzorce půjček a investic

Dluhopisy mají některé vlastnosti, které stojí za ujasnění, už proto, že do mnoha funkcí
týkajících se dluhopisů vstupují jako parametry:

Například firma X vydá dluhopisy se zaručenou cenou 100 Kč, 10letou splatností a 6%
úrokovou sazbou připisovanou dvakrát do roka:

K1496_03.indd 303



Když se úrokové sazby zvýší: Výdělek 6% už není tak atraktivní a kupci nebudou chtít
platit 100 Kč. Ale budou ochotni zaplatit o něco méně.



Když se úrokové sazby sníží: Kupónová sazba 6% vypadá lákavě a po dluhopisech bude
poptávka. V takovém případě zaplatí kupci více než zaručenou cenu.

6.2.2008 16:26:10

304

Část III – Finanční výpočty

Funkce PRICE počítá cenu, kterou by měl investor za dluhopis zaplatit, aby docílil určité
návratnosti svých prostředků. Syntaxe funkce PRICE je následující (povinné parametry
jsou tučně):
PRICE(vypořádání;splatnost;sazba;výnos;zaruč_cena;počet_plateb;základna)

Pro uvedené parametry použije investor, který chce návratnost svých peněz ve výši 7,5 %,
následující vzorec, aby zjistil, jakou cenu má zaplatit za dluhopis, který bude splatný za
8 let:
=PRICE(DNES();DNES()+DATUM(8;1;0);0,06;0,075;100;2)

Výsledek je 91,10 Kč, které by měl investor zaplatit, aby jeho výnos byl 7,5%. Dostane
úrok 6 % ročně (6 % × 100 Kč) a dalších 8,90 Kč vydělá při splatnosti dluhopisu, kdy
dostane nominální hodnotu 100 Kč. Tyto dvě složky – úrok a diskont – tvoří výnos.
Skutečná data použitá pro vypořádání a splatnost nehrají roli, důležitý je čas mezi nimi.
V našem příkladě vydala firma X dluhopisy před dvěma roky, ale investor je koupil až
dnes. Protože byly vydány jako desetileté, vyprší za osm let ode dne, kdy je investor
koupil.
Pokud by namísto toho od okamžiku vydání dluhopisů úrokové sazby spadly a investor
by požadoval pouze 5,2% návratnost svých prostředků, vzorec by se trochu změnil:
=PRICE(DNES();DNES()+DATUM(8;1;0);0,06;0,052;100;2)

Za těchto okolností by byl investor ochoten zaplatit 105,18 Kč za dluhopisy o nominální
hodnotě 100 Kč.
Na obrázku 11.17 máte tyto výpočty v listu.

Obrázek 11.17 Použití funkce PRICE

Výpočet výnosu
V předchozích pasážích věděl investor, jaký výnos požaduje, a vypočítal si cenu, kterou
musí pro dosažení tohoto výnosu zaplatit. Pokud namísto toho ví, kolik je ochoten zaplatit,
řekne mu funkce YIELD, jaká bude výnosnost jeho investice. Syntaxe funkce YIELD je:
YIELD(vypořádání;splatnost;sazba;cena;zaruč_cena;počet_plateb;základna)

K1496_03.indd 304

6.2.2008 16:26:11

Kapitola 11 – Vzorce pro půjčky a investice

305

Investor se stále zajímá o 10leté dluhopisy s 6% kuponovou sazbou placenou dvakrát
ročně, ale tentokrát je ochoten zaplatit za každý dluhopis s nominální hodnotou 100 Kč
pouze 93,95 Kč. Následující vzorec počítá jeho míru výnosu za 8 let, které zbývají do
splatnosti dluhopisu:
=YIELD(DNES();DNES()+DATUM(8;1;0);0,06;93,95;100;2)

Investor vydělá 7 %, pokud zaplatí za tyto dluhopisy 93,95 Kč. Kdyby byl ochoten zaplatit
více než je nominální hodnota (100 Kč), jeho výnos by byl menší než 6% kuponové sazby,
což je vidět na obrázku 11.18.

KAPITOLA 11
Vzorce půjček a investic

Obrázek 11.18 Je-li cena vyšší než nominální hodnota, je výnos menší než kuponová sazba

K1496_03.indd 305

6.2.2008 16:26:11

