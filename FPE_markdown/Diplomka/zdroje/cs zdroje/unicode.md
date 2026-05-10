---
title: "unicode.html"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/zdroje/cs zdroje/unicode.html"
date: 2010-01-31
type: HTML
---

[Nahlédnìte i do [Diskuse pod èarou](#diskuse_pod_carou)!]{.small}

# Unicode - cesta z chaosu kódování znakù {#unicode---cesta-z-chaosu-kódování-znakù align="Center"}

![](unicode_soubory/unicode.gif){align="right" border="0"} Na zaèátku
bylo slovo. Toto slovo bylo zapsáno v sedmibitovém ASCII

A slovo se ¹íøilo. Ze své vlasti Ameriky do ostatních èástí svìta.
Oblastí, kde písmem není latinka, oblastí, kde se písmena pou¾ívají
spoleènì s diakritickými znaménky, aby formovaly nová písmena.
Sedmibitový svìt (kde ka¾dé písmeno je v poèítaèi reprezentováno èíslem
0-127) ztrácel dech.

I pøi¹el ke slovu (do té doby opomíjený) osmý bit z jednoho Byte.
Pùvodnì zbyteèný a pou¾ívaný ke kontrole pøená¹ených dat pomocí parity,
nyní roz¹íøil znakovou sadu o 128 nových pozic.

Tato èísla byla pou¾ita k oznaèení znakù národních abeced, ale také k
oznaèení jiných grafických symbolùm jako je znak mìny nebo rámeèky. Brzy
bylo jasné, ¾e vzhledem k rozmanitosti rùzných jazykù a rozmanitosti
jednotlivých pou¾ívaných písmen ani 256 znakù nestaèí pro písmena v¹ech
abeced. Nejjednodu¹¹í a v té dobì postaèující øe¹ení bylo tedy pou¾ívat
pro ka¾dý konkrétní jazyk jeho vlastní *kódování znakù*, tak, ¾e ve¹keré
pou¾ité písmena jazyka se vejdou do sady o velikosti 256 znakù.

Bohu¾el tento systém má nìkolik základních nedostatkù. Je sice mo¾né
pøedávat si jednodu¹e dokumenty v prostøedí, které pou¾ívá stejnou
znakovou sadu, ale text napsaný pùvodnì v èe¹tinì se zobrazuje ¹patnì
tøeba ve francouz¹tinì - èíslo, oznaèující v èe¹tinì tøeba \"¹\" mù¾e ve
francouz¹tinì oznaèovat tøeba \"^1^\".

Navíc snad ka¾dá firma, která má jakýsi vliv na IT, pokládá za povinnost
vyvinout a prosazovat vlastní kódování znakù - napøíklad v na¹em malém
Èesku se více èi ménì pou¾ívá 6 (!) [rùzných kódování
èe¹tiny](http://www.cestina.cz/kodovani/index.html) - tj. ¹est rùzných
poèítaèových reprezentací reálných èeských písmen. Kromì ryze èeských
Kameníkù a na¹imi bývalými (zapla»pánbu, ¾e bývalými) bratry v
socialismu prosazovaným `KOI-8` to je Microsoft (`windows-1250`), IBM
(`CP852`) i Apple(`x-mac-ce`). Pøitom existuje platný mezinárodní
standard - `ISO-8859-2`. Tuto naprostou bezohlednost poèítaèových firem
zaplatí samozøejmì pouze u¾ivatelé. Jediná cesta z této svízelné situace
je cílené prosazování mezinárodních standardù, nezávislých na
poèítaèových firmách. I v Èesku se situace (snad i díky Inetu) pomalu
konsoliduje. Jasná je podpora `ISO-8859-2`, tomuto kódování musí rozumìt
jakýkoli e-mejlový nebo WWW klient, který si dìlá nárok na to, aby byl
kompatibilní s MIME (viz [dùvody pro pou¾ívání
ISO-8859-2](http://www.cestina.cz/whyISO.html)). Díky monopolnímu
postavení Microsoftu na poli operaèních systémù se bohu¾el asi je¹tì
dlouho nezbavíme `windows-1250`. Ostatní kódování pomalu vymírají, tak
jak se systémy pomalu nahrazují rychlej¹ím, stabilnìj¹ím a výkonnìj¹ím
Un\*xem, popøípadì na bì¾ného u¾ivatele zamìøenými MS Windows.

To, ¾e je mnohdy tì¾ké shodnout se na jednom kódování jediného jazyka
dává tu¹it, jaké jsou problémy s vymìnou dokumentù v rùzných jazycích.
Ka¾dý jazyk má svou znakovou sadu, nejlépe je¹tì v nìkolika variantách a
dokument napsaný v jiném jazyce se s nejvy¹¹í pravdìpodobností zobrazí
prostì ¹patnì. Stále se zvy¹ující potøeba výmìny dokumentù elekronickou
cestou zákonitì vede k potøebì nìjaké globální abecedy, která by
umo¾nila bezproblémovou výmìnu dokumentù. Vzhledem k tomu, ¾e pøechod na
angliètinu (a tím i zbavení se problému národních abeced) v dohledné
dobì nehrozí, bylo tøeba najít øe¹ení jiné.

## Unicode Consorcium {#unicode-consorcium align="center"}

Roku 1991 bylo oficiálnì, po nìkolika letech neformální spolupráce,
zalo¾eno Unicode Consorcium. Vzalo si za úkol postarat se o prosazení a
dal¹í vývoj 16 bitového kódování pro znaky nejdùle¾itìj¹ích svìtových
jazykù, spolu s mnoha historickými a archaickými znaky.

Consorcium se sna¾í spojit síly nejdùle¾itìj¹ích prùmyslových
spoleèností a vývojáøù ke standardizaci mezinárodní znakové sady.
Výsledkem jeho práce je standard Unicode, který je základem
internacionalizace a lokalizace software, který se stal také souèástí
¹ir¹ího standardu ISO/EIC 10646;1993.

Primární úlohou Consorcia je vyvíjet a podporovat standard Unicode;
pomáhat pøi jeho implementaci do software; a také zaji¹»ovat fundovanou
kontrolu nad budoucími revizemi standardu.

## Co je to Unicode? {#co-je-to-unicode align="center"}

Standard Unicode je 16 bitové kódovací schéma s nemìnnou ¹íøkou, urèené
pro zápis znakù v textu. Toto mezinárodní kódování obsahuje znaky
hlavních svìtových abeced a také èasto pou¾ívané technické znaky.
Kódování Unicode zachazí se znaky abeced i rùznými jinými symboly
stejným zpùsobem, tak¾e mohou být pou¾ívány spoleènì. Unicode vychází z
ASCII, pou¾ívá ale 16 bitù pro identifikaci znakù, aby bylo mo¾né
podporovat vícejazyèné texty. Pro ¾ádný znak z kteréhokoli jazyka nejsou
tøeba ¾ádné escape sekvence nebo jiný kontrolní kód.

Standard Unicode definuje numerickou hodnotu a název pro ka¾dý ze svých
znakù; v tomto ohledu je podobné jiným systémùm pro kódovávání znakù,
poèínaje ASCII a konèe mezinárodním standardem ISO/EIC 10646-1:1993.

Standard Unicode obsahuje, mimo pøiøazení kódù a názvù jednotlivým
znakùm, i dal¹í informace, které obvykle ve znakových sadách chybí, ale
jsou nezbytné pro implementaci kódování. Standard definuje vlastnosti
znakù a obsahuje také dal¹í aplikaèní data, jako jsou pøevodní tabulky
mezi malými/velkými písmeny a mapování Unicode do mnoha mezinárodních,
národních a prùmyslových znakových sad. Tyto informace jsou ¹íøeny pøímo
Unicode Consorciem proto, aby byla zaji¹tìna konzistence pøi výmìnì dat
v Unicode.

### Cíle návrhu

Vývoj Unicode si dává za úkol vyøe¹it dva základní problémy, bì¾né ve
vícejazyèných poèítaèových programech - dostupnost fontù pro rùzná
kódování znakù a problém existence nìkolika nìkonzistentních znakových
sad díky neshodì národních a prùmyslových znakových standardù.

V roce 1988, kdy projekt Unicode zaèal, byli neexistencí konzistentní
mezinárodní znakové sady nejvíce zasa¾eni vydavatelé vìdeckého a
informaèního software, vydavatelé novin a knih, knihovnické informaèní
slu¾bt a akademiètí vývojáøi. Od té doby stále sílila potøeba budovat
software tak, aby byl snadno pøizpùsobitelný lokálním jazykovým
podmínkám. Stále roste také potøeba volné výmìny dokumentù, bez
závislosti na zdrojovém nebo cílovém prostøedí. Explozivní rùst
Internetu dále podpoøil po¾adavek znakové sady, která by byla stejná
kdekoli na svìtì.

Vývojáøi standardu Unicode pøi¹li s my¹lenkou jednotné metody
identifikace znakù, která by byla efektivnìj¹í a snadnìji
pøizpùsobitelná ne¾ pøedchozí kódovací systémy. Nový systém by mìl být
dostateènì kompletní, aby zajistil potøebu vícejazyèné práce s poèítaèem
a mìl by kódovat ¹irokou paletu znakù pro profesionální zpracování textù
v jakémkoli moderním jazyce.

Pùvodní cíle standardu Unicode byly tyto:

*Univerzálnost.*
:   Kapacita znakové sady musí být dostateèná k zahrnutí v¹ech znakù,
    které by mohly být pou¾ity pøi výmìnì textù - zejména ty, které u¾
    byly definovány v hlavních mezinárodních, národních a prùmyslových
    znakových sadách.

*Efektivita.*
:   Text, poskládaný z posloupnosti znakù o konstantní ¹íøce, je velmi
    jednoduchý na zpracování; software nemusí uchovávat stav, dávat
    pozor na speciální escape sekvence nebo prohledávat text dopøedu èi
    zpìt kvùli identifikaci znakù.

*Jednotnost.*
:   Konstatní ¹íøka znakù dovoluje efektivní tøídìní, hledání,
    zobrazování a editaci textù.

*Jednoznaènost.*
:   Kterákoli 16 bitová hodnota reprezentuje v jakémkoli kontextu stejný
    znak.

### Pokrytí

Verze 2.0 standardu Unicode obsahuje 38.885 znakù svìtových abeced.
Postaèuje nejen pro více ne¾ dostateènì pro bì¾nou komunikaci, ale také
k vyjádøení nìkterých star¹ích forem mnoha jazykù. Jazyky, které je
mo¾no pomocí Unicde zakódovat jsou momentálnì ru¹tina, arab¹tina,
anglosa¹tina, øeètina, hebrej¹tina, Thai a Sanskrit. Sjednocená
podmno¾ina Han obsahuje 20.902 grafických symbolù definovaných jako
národní a prùmyslové standardy Èíny, Japonska, Korey a Taiwanu. Standard
Unicode navíc zahrnuje matematické operátory a technické symboly
(napøíklad nìkteré geometrické tvary) a nìkolik grafických symbolù.

Standard Unicode zahrnuje znaky v¹ech hlavních mezinárodních standardù
schválené a publikované pøed 31.prosincem 1990; pøedev¹ím rodiny
standardù ISO International Register of Character Sets, ISO/EIC 6937 a
ISO/IEC 8859, také ISO/IEC 8879 (SGML). Jiné primární zdroje zahrnují
bibliografické standardy pou¾ívané v knihovnách (napøíklad ISO/EIC 5426
a ANSI Z39.64), nejdùle¾itìj¹í národní standardy a rùzné èasto pou¾ívané
prùmyslové standardy (vèetnì znakových sad od Adobe, Apple, Fujitsu,
Hewlett-Packard, IBM, Lotus, Microsoft, NEC, WordPerfect a Xerox). Ve
verzi 2.0 byl pøidán obsah Hangul z korejského národního standardu KS C
5601.

Unicode není urèen pro kódování rùzných nesmyslných, osobních,
románových a málokdy pou¾ívaných znakù nebo znakù pro osobní potøebu,
ani log nebo grafiky. Umìlé znaky, pou¾ité pouze pro pøechodné vkládání
textu, jsou vynechány. Obrázky bez návaznosti k textu, jako jsou
napøíklad hudební nebo taneèní znaèky, nezasahují do oblasti zájmu
Unicode. Rùzné odli¹nosti v zobrazení znakù nejsou zachyceny. V rámci
Unicode je vyhra¾eno 6400 znakù pro potøeby aplikací; pou¾ití tìchto
kódù aplikacemi není nijak omezeno.

Standard Unicode je stále ve vývoji. Nové znaky budou postupnì
pøidávány, mohou se mìnit názvy znakù, které jsou èástí Unicode; jejich
konrétní kódy v¹ak zùstávají stejné i v dal¹ích verzích standardu.

## Implementace {#implementace align="center"}

My¹lenka Unicode jako sjednocujícího svìtového kódování znakù je jistì
výborná. 16 bitové kódování pøiná¹í v¹ak i nìkolik nevýhod:

*Vìt¹í délka textu.*
:   Text je po pøevodu z osmibitového kódování do Unicode dvojnásobnì
    del¹í, zdánlivì bez pøidání informaèní hodnoty. Výsledek zabere víc
    místa pøi ulo¾ení a také následné zpracování je pomalej¹í.

*256x vìt¹í znaková sada.*
:   Znaky na poèítaèi se zobrazují pomocí fontù, které pro Unicode musí
    obsahovat *256x* víc znakù ne¾ pro osmibitové znakové sady. Vzhledem
    k tomu, ¾e v mnoha jazycích se pou¾ije jen nepatrný zlomek celkového
    mno¾ství, znaky navíc zbyteènì zabírají místo. Microsoft tohle øe¹í
    tak, ¾e ani Unicode fonty neobsahují v¹echny znaky, ale pouze ty,
    které jsou pou¾ívané v daném prostøedí - a v pøípadì potøeby je
    mo¾no poøídit \"plné\" fonty.

*Nekompatibilita s osmibitovým prostøedím.*

:   Unicode text mù¾e \"legálnì\" obsahovat znaky, které v
    \"normálním\", osmibitovém textu obvykle nejsou a zpravidla mají
    speciální význam - jedná se zejména o binární nulu, kterou Unicode
    text mù¾e obsahovat jako vy¹¹í byte dvoubytového kódu. Nelze tedy
    pou¾ít stávající programový kód pro práci s textem a musí se od
    základu pøepsat.

    Nelze jednodu¹e zjistit, jestli daný text je v Unicode nebo ne,
    nelze proto jednodu¹e zároveò pou¾ívat Unicode a nìjaké osmibitové
    kódování. Není tedy mo¾né pøejít na Unicode èásteènì, je nutný
    globální pøechod, aby aplikace nejen dostaly text v Unicode, ale aby
    hlavnì Unicode text i oèekávaly. Fakt, ¾e to jde v rámci uzavøeného
    systému, pøedvádí názornì firma Sun s Javou, pracující internì v
    Unicode, a také produkty firmy Microsoft. Podporu Unicode v¹ak nelze
    zajistit obecnì a nelze poèítat s tím, ¾e mu druhá strana bude v¾dy
    rozumìt - nasazení v po¹tì nebo na WWW je tedy pøinejmen¹ím
    problematické. Alespoò v tomto bodì se v¹ak situace pomalu mìní k
    lep¹ímu.

V mnoha jazycích (i v èe¹tinì) netvoøí \"speciální\" znaky (napø. znaky
s diakritikou) ani zdaleka vìt¹inu písmen. Pro velké kvanta textu
postaèuje ASCII, sem tam prolo¾ené akcentovaným znakem. Pro takové texty
je naprosto zbyteèné pou¾ít dva byte na ulo¾ení ka¾dého písmene - jeden
byte plnì dostaèuje. Ne ka¾dé médium také podporuje binární pøenos a ne
v¾dy vyhovuje zápis Unicode znaku jako dva po sobì následující byty.
Postupem èasu vzniklo nìkolik rùzných jiných zápisù Unicode, které øe¹í
nìkteré problémy s pøenosem nebo pou¾íváním Unicode.

### UCS-2

UCS-2 je základní zpùsob zápisu Unicode znakù. Pro ulo¾ení dat se
pou¾ívá poslopnost dvoubytových polo¾ek. Konec textového øetìzce mù¾e
být oznaèen napøíklad 16 bitovým NULL, tedy `0x0000`; je tøeba dát
pozor, ¾e osmibitové NULL (`0x00`) se mù¾e objevit ve vy¹¹ím nebo ni¾¹ím
byte èísla Unicode znaku. Velkou výhodou UCS-2 oproti jiným formám je
konstantní délka znaku a snadné zji¹»ování poètu znakù v øetìzci, je
tedy vhodná zejména pro vnitøní reprezentaci Unicode znakù v programu.

### UTF-7

UTF-7 je forma popsaná pomocí RFC-1642. Jedná se o zápis Unicode znakù
primárnì urèený pro pou¾ití v elektronické po¹tì. Internetová po¹ta
momentálnì (podle definice RFC-822) podporuje pouze sedmibitové ASCII,
specifikace MIME (RFC-1521 a RFC-1522) pak roz¹iøuje podporu také na
vybraná osmibitová kódování (napøíklad rodinu standardù `ISO-8859-*`).
MIME v¹ak nezaøazuje Unicode mezi povolené znakové sady, ani
nespecifikuje, jak by mìlo být zakódováno, i pøesto, ¾e myslí na
pøidávání nových znakových sad.

UTF-7 je forma, která pou¾ívá pro zápis Unicode znakù pouze ASCII
hodnoty a je navr¾ena tak, aby zakódovaná data byla co nejlépe èitelná
èlovìkem; v¹echna podporovaná ASCII písmena nejsou tedy nijak kódováná a
reprezentují pøímo sebe. Je také akceptován fakt, ¾e nìkteré systémy
(napøíklad systémy pou¾ívající EBCDIC) nedoká¾í zpracovat dokonce ani
celé ASCII, tak¾e Unicode znaky jsou zapsány tak, aby výsledek byl
èitelný na jakémkoli systému. Pro zápis znakù se pou¾ívá algoritmus
velmi podobný base64, podrobný popis je v¹ak mimo zábìr tohoto èlánku,
dá se nalézt napøíklad [jinde](#formy).

### UTF-8

Jedná se o doporuèený zpùsob zápisu `ISO/EIC 10646` znakù pro UCS-2 i
UCS-4. Mù¾e tak poslou¾it i pro zápis Unicode.

Pro ukázku si mù¾ete pomocí [tohoto
skriptu](http://194.213.242.4/noconv/script/utf8.php?n=20ac) nechat
pøevést jeden kód UTF-8 na binárni i grafické vyjádøení. (To druhé jen v
pøípadì, ¾e vá¹ prohlí¾eè UTF-8 dovede.)

Pro prosazení `ISO/IEC 10646` (Unicode) jako mezinárodního standardu a
jeho roz¹íøení bylo tøeba pro softwarové systémy, historicky zalo¾ené na
ASCII, nalézt zpùsob, jak na nich pou¾ívat to velké mno¾ství znakù,
které byly pojmuty novým standardem.

S UCS souvisí nìkolik problémù, spojených s historií operaèních systémù
a prostøedím jazyka C. Nejvìt¹ím problémem je vícebytové kódovací
schéma, pou¾ité v UCS. Opravdu opbtí¾né je skloubit standard UCS s
existujícími programovacími jazyky a existujícími operaèními systémy a
programy. Je naprosto nezbytné, aby se existující software nemusel
pøíli¹ upravovat a pøitom bylo mo¾no pou¾ít velké mno¾ství znakù
definované v UCS.

Cíle UTF-8 jsou zejména:

1.  Kompatibilita se star¹ími souborovými systémy. Souborové systémy
    zpravidla nepovolují v názvech souborù nulový byte ani (zpìtné)
    lomítko.
2.  Kompatibilita s existujícími programy. Zápis jakéhokoli znaku by
    nemìl obsahovat ASCII, pokud znak pùvodnì v ASCII nebyl.
3.  Snadnost konverzí z/do UCS.
4.  První byte by mìl urèovat poèet bytù, které ve vícebytovém zápisu
    znaku následují.
5.  Transformaèní formát by nìmìl být zbyteènì rozmaøilý co do poètu
    bytù, pou¾itých pro zápis.
6.  Z kterékoli pozice v proudu dat by mìlo být mo¾né najít zaèátek
    dal¹í znakové jednotky.

UTF-8 zvládá zápis UCS hodnot v rozmezí 0-0x7ffffff za pou¾ití 1-6 bytù.
Úvodní byte v¾dy prozrazuje poèet pou¾itých bytù a následující èleny
vícebytové poslopnosti mají nastaven nejvy¹¹í bit. je nastaven. Jakýkoli
byte, který nezaèíná na 10xxxxxx je zaèátek zápisu dal¹ího znaku.

  ------- ---------- ---------- -----------------------------------------------
  bitù    hex min    hex max    zapsaná posloupnost bytù ve dvojkové soustavì
  0-7     00000000   0000007f   0vvvvvvv
  8-11    00000080   000007FF   110vvvvv 10vvvvvv
  12-16   00000800   0000FFFF   1110vvvv 10vvvvvv 10vvvvvv
  ------- ---------- ---------- -----------------------------------------------

\
*Tabulka 1: Zpùsob zápisu Unicode znakù pomocí UTF-8*

Velmi jednodu¹e se dá tento transformaèní formát zapamatovat tak, ¾e v
prvním bytu poslopnosti urèuje poèet bitù zleva po první nulu poèet
bytù, které následují.

Velmi sympatické je, ¾e na obyèejný ASCII text je potøeba pouze jeden
byte a kterýkoli znak Unicode lze zapsat maximálnì jako tøi znaky v
UTF-8. Èe¹tina má navíc to ¹tìstí, ¾e její akcentované znaky mají
pomìrnì dost malé Unicode hodnoty, tak¾e jakýkoli èeský Unicode znak lze
v UTF-8 zapsat maximálnì na dva byty.

S Unicode textem zapsaným v UTF-8 lze zacházet stejnì jako s obyèejným
osmibitovým, není tøeba nic speciálnì o¹etøovat ani psát ¾ádný speciální
programovací kód pro zacházení s Unicode (snad kromì kódy, starající se
o zobrazování znakù). Není divy, ¾e se UTF-8 prosazuje jako univerzální
formát pro výmìnu dokumentù v Unicode. Formát UTF-8 odstraòuje v¹echny
nevýhody nasazení Unicode - zachovává kompatibilitu se stávajícím kódem
a pøitom umo¾òuje aplikacím pou¾ít v¹ech výhod univerzální mezinárodní
znakové sady.

## Zhodnocení {#zhodnocení align="center"}

Unicode øe¹í nejvìt¹í problém globální výmìny informací - její
jednoznaèný zápis zpùsobem, který zajistí konzistenci a bezproblémové
u¾ívání kdekoli na svìtì. Je trochu cizí pro systémy, originálnì
zalo¾ené na ASCII, ale s pou¾itím vhodného formátu zápisu je mo¾no
docílit, aby Unicode pøinejmen¹ím bylo ignorováno, jeho nasazení
nezkazilo stávající programy a nebylo tøeba investovat pøíli¹ velké
úsilí na jeho podporu. Jednou a nav¾dy definuje, jaké vnitøní oznaèení
bude mít znak v poèítaèi, èím¾ eliminuje chaos nekompatibilních
znakových sad a standardù. Vìøím tomu, ¾e pøijde den a celý svìt se
sjednotí na Unicode. Bylo by výborné, kdyby se do té doby (aspoò u nás,
v Èesku) podaøilo sjednotit také na jednom osmibitovém kódování -
usnadnilo by to pozdìj¹í pøechod na Unicode. Ale to u¾ zní skoro jako
utopie ;-)

## Reference {#reference align="center"}

-   [`http://www.unicode.org/`](http://www.unicode.org/) - domácí
    stránka Unicode Consorcia
-   ` `[`http://www.unicode.org/unicode/standard/standard.html`](http://www.unicode.org/unicode/standard/standard.html) -
    specifikace Unicode, popis jednotlivých znakù, pou¾ité oblasti
    hodnot
-   []{#formy}` `[`http://www.unicode.org/unicode/standard/principles.html`](http://www.unicode.org/unicode/standard/principles.html) -
    technický úvod do Unicode
-   ` `[`http://www.stonehand.com/unicode/standard/`](http://www.stonehand.com/unicode/standard/) -
    mirror star¹í verze stránek Unicode Consorcia, na nových stránkách
    jsem nebyl schopen znovu nalézt popis UTF-7 a UTF-8
-   [`http://www.macroware.cz/software/unicode/`](http://www.macroware.cz/software/unicode/) -
    Unicode a Java, povídání pro programátory.

## Vysvìtlivky {#vysvìtlivky align="center"}

-   ASCII - American Standard Code for Information Interchange
-   UCS - Universal coded Character Set
-   UTF - Universal Transformation Format
