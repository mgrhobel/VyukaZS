---
title: "DP_Hobel_2011.docx"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/final/final/DP_Hobel_2011.docx"
date: 2011-05-25
type: DOCX
---

Západočeská univerzita v Plzni

[Fakulta pedagogická]{.smallcaps}

[[Katedra výpočetní a didaktické
techniky]{style="background: #c0c0c0"}]{.smallcaps}

[Grafický nástroj pro podporu internacionalizace a lokalizace aplikace
MPA (Medical Process Assistant)]{.smallcaps}

[[]{style="background: #c0c0c0"}]{.smallcaps}

Josef Hobel

[Učitelství pro 2. stupeň ZŠ, obor
INF-]{style="background: #c0c0c0"}*MAT*

*léta studia (2008 -2011)*

Vedoucí práce: *[Ing. Pavel Kocur, CSc.]{style="background: #c0c0c0"}*

Plzeň, [31 března 0201]{style="background: #c0c0c0"}1

\

Prohlašuji, že jsem diplomovou práci vypracoval samostatně s použitím
uvedené literatury a zdrojů informací.

Plzeň, [31 března 0201]{style="background: #c0c0c0"}1

...................................................

vlastnoruční podpis

**Obsah**

::: {#Table of Contents1 dir="ltr"}
[1[ ]{style="font-variant: normal"}Úvod 1](#_Toc289334273)

[2[ ]{style="font-variant: normal"}Seznam použitých odborných výrazů
3](#_Toc289334274)

[3[ ]{style="font-variant: normal"}Úvod k internacionalizaci
7](#_Toc289334275)

[3.1[ ]{style="font-variant: normal"}Internacionalizace, lokalizace,
globalizace 7](#_Toc289334276)

[3.1.1 Internacionalizace 8](#_Toc289334277)

[3.1.2 Lokalizace 9](#_Toc289334278)

[3.1.3 Globalizace 11](#_Toc289334279)

[3.2[ ]{style="font-variant: normal"}Průběh procesu internacionalizace
12](#_Toc289334280)

[3.2.1 Uživatelské rozhraní a tištěná dokumentace 12](#_Toc289334281)

[3.2.2 Problémy spojené s použitím znakové sady 13](#_Toc289334282)

[3.2.3 Geografické odlišnosti ve formátování 13](#_Toc289334283)

[3.3[ ]{style="font-variant: normal"}Průběh procesu lokalizace
14](#_Toc289334284)

[3.3.1 Nástrahy při provádění překladů 15](#_Toc289334285)

[3.3.2 Lokalizace netextových prvků 15](#_Toc289334286)

[4[ ]{style="font-variant: normal"}Java a internacionalizace
17](#_Toc289334287)

[4.1[ ]{style="font-variant: normal"}Locale 17](#_Toc289334288)

[4.1.1 Výchozí Locale 19](#_Toc289334289)

[4.2[ ]{style="font-variant: normal"}Oddělení jazykově závislých dat od
zdrojových kódů 19](#_Toc289334290)

[4.3[ ]{style="font-variant: normal"}Formátování textů v různých
jazycích 22](#_Toc289334291)

[4.3.1 Formátování data a času 23](#_Toc289334292)

[4.3.2 Vlastní formát data a času 24](#_Toc289334293)

[4.3.3 Kalendářní systém 24](#_Toc289334294)

[4.3.4 Časová pásma 25](#_Toc289334295)

[4.3.5 Formátování čísel 26](#_Toc289334296)

[4.3.6 Zavedené symboly pro měnu a jejich konkrétní umístění
26](#_Toc289334297)

[4.3.7 Speciální formátování čísel 27](#_Toc289334298)

[4.3.8 Formátování textů 27](#_Toc289334299)

[4.4[ ]{style="font-variant: normal"}Problematika speciálních znaků
30](#_Toc289334300)

[4.4.1 ASCII 30](#_Toc289334301)

[4.4.2 Cp1250 31](#_Toc289334302)

[4.4.3 Cp852 31](#_Toc289334303)

[4.4.4 ISO8859_2 31](#_Toc289334304)

[4.4.5 Unicode 32](#_Toc289334305)

[4.4.6 UTF-8 33](#_Toc289334306)

[4.5[ ]{style="font-variant: normal"}Problémy spojené s používáním
znakových sad 34](#_Toc289334307)

[4.5.1 Speciální znaky na konzoly 34](#_Toc289334308)

[4.5.2 Speciální znaky v souborech 35](#_Toc289334309)

[4.5.3 Speciální znaky v GUI 35](#_Toc289334310)

[5[ ]{style="font-variant: normal"}Aplikace MPA 37](#_Toc289334311)

[5.1[ ]{style="font-variant: normal"}Úložiště lokálně závislých textů
38](#_Toc289334312)

[5.1.1 Konfigurační soubory 38](#_Toc289334313)

[5.2[ ]{style="font-variant: normal"}Databázové objekty
39](#_Toc289334314)

[6[ ]{style="font-variant: normal"}Aplikace MITToolkit
40](#_Toc289334315)

[6.1[ ]{style="font-variant: normal"}Architektura 40](#_Toc289334316)

[6.2[ ]{style="font-variant: normal"}Role v procesu internacionalizace a
lokalizace 41](#_Toc289334317)

[6.2.1 Programátor 41](#_Toc289334318)

[6.2.2 Interní překladatel 41](#_Toc289334319)

[6.2.3 Externí překladatel 41](#_Toc289334320)

[6.2.4 Uživatel 41](#_Toc289334321)

[6.3[ ]{style="font-variant: normal"}Princip ovládání aplikace MITTookit
42](#_Toc289334322)

[6.4[ ]{style="font-variant: normal"}Administrace jednotlivých
lokalizačních projektů 42](#_Toc289334323)

[6.5[ ]{style="font-variant: normal"}[Export textů z MPA do databáze
]{lang="en-US"}dle zadaných parametrů 44](#_Toc289334324)

[6.5.1 RepoResourceBundles export 44](#_Toc289334325)

[6.5.2 MessageBundles export 45](#_Toc289334326)

[6.5.3 Export kontextuálních informací 46](#_Toc289334327)

[6.6[ ]{style="font-variant: normal"}Editace textů uložených v databázi
46](#_Toc289334328)

[6.6.1 Německé fráze 47](#_Toc289334329)

[6.6.2 Editace Překladů 47](#_Toc289334330)

[6.6.3 Filtrování frází 48](#_Toc289334331)

[6.6.4 Poznámky k frázím pro překladatele 49](#_Toc289334332)

[6.7[ ]{style="font-variant: normal"}Export z databáze do Excel souboru
pro překladatele 49](#_Toc289334333)

[6.7.1 Fráze určené pro export 49](#_Toc289334334)

[6.7.2 Exportovací parametry pro excel 51](#_Toc289334335)

[6.7.3 Výsledný Excel soubor a jeho výhody 51](#_Toc289334336)

[6.8[ ]{style="font-variant: normal"}Import do databáze ze souboru
přeloženého překladatelem 52](#_Toc289334337)

[6.8.1 Importovací parametry 52](#_Toc289334338)

[6.8.2 Fráze určené pro import 54](#_Toc289334339)

[6.9[ ]{style="font-variant: normal"}Import všech přeložených frází z
databáze do MPA dle zadaných parametrů 55](#_Toc289334340)

[6.9.1 RepoResourceBundles Import 55](#_Toc289334341)

[6.9.2 MessageBundles Import 55](#_Toc289334342)

[6.9.3 Import existujících překladů 56](#_Toc289334343)

[7[ ]{style="font-variant: normal"}Doplňkové nástroje Aplikace
MITToolkit 58](#_Toc289334344)

[7.1[ ]{style="font-variant: normal"}Editor pro MessageBundle soubory
58](#_Toc289334345)

[7.1.1 Výhody použití editoru oproti konfiguračním souborům
58](#_Toc289334346)

[7.2[ ]{style="font-variant: normal"}Editor objektové databáze
59](#_Toc289334347)

[7.3[ ]{style="font-variant: normal"}Editor grafických komponent
60](#_Toc289334348)

[7.4[ ]{style="font-variant: normal"}Slovník hlavních frází
60](#_Toc289334349)

[7.5[ ]{style="font-variant: normal"}Datumové formáty
61](#_Toc289334350)

[8[ ]{style="font-variant: normal"}Aplikace MITToolkit a její přínos
62](#_Toc289334351)

[9[ ]{style="font-variant: normal"}Závěr 63](#_Toc289334352)

[10[ ]{style="font-variant: normal"}Seznam obrázků a tabulek
I](#_Toc289334353)

[11[ ]{style="font-variant: normal"}Seznam literatury
II](#_Toc289334354)

[12[ ]{style="font-variant: normal"}Resumé III](#_Toc289334355)

[13[ ]{style="font-variant: normal"}Přílohy IV](#_Toc289334356)

[A.[ ]{style="font-variant: normal"}Obsah konkrétního MessageBundle
souboru IV](#_Toc289334357)

[B.[ ]{style="font-variant: normal"}Úprava německý textů pomocí
MessageBundle editoru V](#_Toc289334358)

[C.[ ]{style="font-variant: normal"}Obsah konkrétního ResourceBundle
objektu VI](#_Toc289334359)

[D.[ ]{style="font-variant: normal"}Úprava anglických textů v příslušné
grafické komponentě VII](#_Toc289334360)

[E.[ ]{style="font-variant: normal"}Možnosti filtrování frází z databáze
VIII](#_Toc289334361)

[F.[ ]{style="font-variant: normal"}Vyhledávání a třídění textů
IX](#_Toc289334362)

[G.[ ]{style="font-variant: normal"}Obsah konkrétního Excel souboru
X](#_Toc289334363)

[H.[ ]{style="font-variant: normal"}Možnosti filtrování frází z Excel
souboru XI](#_Toc289334364)

[I.[ ]{style="font-variant: normal"}Slovník hlavních frází
XII](#_Toc289334365)
:::

\

1.  []{#_Toc289334273}[]{#_Ref289288938}[]{#_Toc213915174} **Úvod**

V rámci svého profesního působení na pozici Java programátora mi byl
přiřazen projekt, ve kterém bylo třeba navrhnout a vytvořit grafický
nástroj, který bude usnadňovat a automatizovat veškeré procesy, které se
týkají softwarové internacionalizace a lokalizace. Zároveň mi tato
problematika přišla velmi zajímavá i z hlediska téma své diplomové
práce.

V jednotlivých kapitolách popisuji principy internacionalizace a
lokalizace nejdříve teoreticky, zobecněně pro libovolnou aplikaci. Tyto
informace poté rozvíjím o příklady, jak je možné danou problematiku
vyřešit z hlediska programovacího jazyka
Java[^1^](#sdfootnote1sym){#sdfootnote1anc .sdfootnoteanc}. V poslední
části pak popisuji funkce a schopnosti vytvořeného nástroje, který řeší
konkrétní reálné problémy týkající se internacionalizace a lokalizace.

První kapitola (číslování [3]{style="background: #c0c0c0"}) se zabývá
základními pojmy softwarové internacionalizace včetně toho, proč je
vlastně důležité se internacionalizací zabývat. Jsou zde uvedeny
definice internacionalizace, lokalizace a globalizace a společně s nimi
je zde velmi podrobně pospsán průběh činností, které je v jejich rámci
třeba provést. Dále je zde uvedeny také konkrétní nástrhy, které mohou
nastat během procesu internacionalizace nebo lokalizace.

Druhá kapitola (číslování [4]{style="background: #c0c0c0"}) pojednává o
konkrétních lokalizačních metodikách, které jsou vysvětleny pomocí
jazyka Java. Jsou zde objasněny důvody, proč oddělovat jazykově závislé
texty od zdrojových kódů a jakým způsobem pracovat se soubory, do
kterých byly tyto texty přesunuty. Dále je zde vysvětleno, jak se v Javě
řeší problematika těch textů, které obsahují číselné, textové nebo
časové proměnné. Poslední větší podkapitola pojednává o problémech,
které mohou nastat se speciálními znaky daného jazyka v závislosti na
použitém kódování a zvoleném výstupním zařízení (konzole, soubor nebo
GUI). Kromě lokalizačních metodik je v této rozsáhlé kapitole také
vysvětlen pojem (výchozí) „Locale" a jak pomocí něho získávat z objektů
lokálně závislé informace.

Třetí kapitola (číslování [5]{style="background: #c0c0c0"}) se zabývá
výhradně aplikací MPA. Je zde vysvětleno k jakým účelům aplikaci MPA
slouží a proč vlastně nastal požadavek tuto aplikaci
internacionalizovat.

Ve čtvrté kapitole (číslování [6]{style="background: #c0c0c0"}) je již
konkrétně představena vytvořená aplikace MITToolkit včetně popisu všech
důležitých nástrojů, kterých využívá. Nechybí zde ani ukázka celkové
práce s aplikací, jak na sebe jednotlivé nástroje navazují a jak se
navzájem ovlivňují.

2.  []{#_Toc289334274} **Seznam použitých odborných výrazů**

**Application Programming Ingerface (API)**

Označuje v informatice rozhraní pro programování aplikací. Jde o sbírku
metod či tříd, které může programátor využívat.

**Class**

Třída, základní konstrukční prvek objektově orientovaného programování
v jazyku Java. Je to „šablona" pro vytváření objektů. Obsahuje soubor
dat a podprogramů.

**Classpath**

Jedná se o konzolový parametr, který určuje místo na disku, kde má JVM
hledat zdrojové soubory pro běžící programy.

**Font**

Je počítačový soubor, který obsahuje informace o tom, jak se mají
jednotlivé znaky zobrazit na monitoru počítače. Fonty je možné definovat
pomocí kresebných variant.

**Fráze**

V rámci aplikace MITToolkit se jedná o německy psaný text, který je
určen k překladu do jiného jazyka (např. angličtiny, češtiny nebo
srbštiny).

**Grafické uživatelské rozhraní (GUI)**

Je uživatelské rozhraní, které umožňuje ovládat počítač pomocí
interaktivních grafických ovládacích prvků (menu, ikony, tlačítka,
posuvníky, formuláře a podobně).

**Input Method Editor (IME)**

Je nástroj, pomocí kterého je možné z klávesnice zadat jakýkoliv znak
z daného jazyka.

**Instance třídy**

V některých programovacích jazycích (včetně jazyka Java) alternativní
název k termínu objekt.

**JDK (Java Development Kit)**

Je soubor základních nástrojů pro vývoj aplikací pro platformu Java.

**JVM (Java Virtual Machine)**

Software, který umožňuje spouštění aplikací v jazyce Java.

**Latinka**

Je nejpoužívanější písmo na světe, původně vyvinuté pro latinu. Za
„standardní latinku" se v současné době považuje anglická abeceda.
Latinku používá většina germánských a románských jazyků, také všechny
keltské a baltské jazyky a více než polovina slovanských jazyků.

**Log**

Název pro záznam nebo soubor záznamů (často s příponou .log), které si
některé programy vytvářejí pro ukládání informací o své činnosti a běhu.
Logy slouží při zpětné analýze k rozpoznání, zda došlo k nějaké chybě a
pakliže ano, pak pomáhají určit, k jaké chybě došlo a proč.

**MVC (model-view-controller)**

Softwarová architektura, která rozděluje datový model aplikace,
uživatelské rozhraní a řídící logiku (komunikaci mezi modelem a GUI) do
tří nezávislých komponent tak, že modifikace některé z nich má minimální
vliv na ostatní. Zdrojový kód je pak tímto rozdělením více čitelný a
v případě potřeby lépe modifikovatelný.

**Objekt**

Je to datový prvek uložený v paměti, který je vytvořen podle vzoru
třídy. Každý objekt má své atributy a metody. Obvykle je vytvořen pomocí
tzv. konstruktoru a klíčového slova new.

**Objektová databáze**

Oproti relačnímu přístupu jsou zde namísto tabulek uloženy přímo
objekty, včetně svých vlastností (hodnot atributů) a namísto řádků se
ukládají samotné instance objektů. Každý takto vložený objekt je
jednoznačně identifikován svým OID, není tedy potřeba vytvářet primární
klíče na objektech ani normalizovat databázi. Tím je zaručeno rychlejší
ukládání a načítání objektů z databáze.

**Regulární výraz**

Je speciální řetězec znaků, který představuje určitý vzor (masku) pomocí
níž je možné vyhledávat a měnit jiné texty.

**Relační databáze**

Je založena na tabulkách, jejichž řádky obvykle chápeme jako záznamy a
eventuálně některé sloupce v nich (tzv. cizí klíče) chápeme tak, že
uchovávají informace o relacích mezi jednotlivými záznamy v matematickém
slova smyslu. Jednoznačný identifikátor záznamu (řádku tabulky) je
primární klíč, který může být jediný sloupec (kombinace více sloupců)
například katalogové číslo, identifikační číslo v seznamu podniků apod.
Díky jednoduchému použití tabulek, klíčů a indexů je vhodné používat
relační platformy na správu velkého objemu jednoduchých dat.

**Řez písma**

Konkrétní verze základního typu písma odlišující se sklonem (např.
kurzíva), tloušťkou tahu (slabé, polotučné, extra tučné) a šířkou znaků
(zúžené, rozšířené, dále podtržením, stínováním, aj.).

**Swing**

Knihovna pro grafické uživatelské rozhraní, která je součástí API od JDK
1.2.

**Verzovací systém**

Je software, který umožňuje uchovávat historie veškerých provedených
změn obecně u jakékoliv digitální informace. Během stádia vývoje
softwarového projektu se tento nástroj používá pro evidenci provedených
změn ve zdrojových kódech software. Důležitým prvkem verzování je
možnost spolupráce velkého množství programátorů nad jedním produktem.

**Vlákna**

Představují způsob, jak v rámci jednoho procesu provádět více činností
paralelně. Každá činnost je představována samostatným vláknem, kde je
vykonáván kód nezávisle na ostatních vláknech. Od procesů se vlákna liší
tím, že spolu sdílejí data procesu, v němž běží.

**Výjimky**

Zpracování chybových stavů, které vzniknou jako důsledky výjimečných, či
neočekávaných událostí v rámci vykonávání programu.

**XML (Extensible Markup Language)**

Rozšiřitelný značkovací jazyk, který je určen především pro výměnu dat
mezi aplikacemi nezávisle na použité platformě.

**Znaková sada (kódování)**

Je schéma číslování, podle kterého je každému textovému znaku ve znakové
sadě přiřazena číselná hodnota. Znaková sada může obsahovat abecední
znaky, číslice a další symboly. Různé jazyky často používají různé sady
znaků, proto existuje mnoho různých standardů kódování.

3.  []{#_Toc289334275}[]{#_Ref288398350} **Úvod k internacionalizaci**

V dnešním moderním a prakticky neomezeném trhu si softwarové společnosti
již nemohou dovolit brát v úvahu pouze domácí trhy a současně zvyšovat
výnosy a slavit úspěchy. Snaží se proto působit celosvětově a své
produkty, služby a ostatní dokumenty mít přístupné a srozumitelné pro co
největší okruh lidí.

Být připraven pouze pro anglicky mluvící trh neznamená být připraven pro
celosvětový trh. Mnoho cílových zákazníků umí anglicky velmi málo (nebo
vůbec), a tak nejsou schopni produkt používat. Tato situace často vede k
tomu, že se zákazníci poohlédnou po jiném produktu, který je dostupný v
jejich rodném jazyce. Problém nemusí být pouze s jazykem, ale i s
použitým uživatelským rozhraním, symbolikou, barvami a dalšími hledisky,
které ovlivňují vnímání a chápání lidí v odlišných zemích a kulturách.

Například „Kontrola překlepů a gramatiky" by byla v textových editorech
pro určité země nepoužitelná, kdyby editor neobsahoval požadovaný
jazykový slovník. Dalším příkladem by mohl být účetní software, který
nepodporuje měnovou a daňovou politiku dané země.

Pokud softwarové společnosti nechtějí přicházet o potencionální
uživatele je tedy nasnadě se procesem lokalizace a internacionalizace
zabývat, zahrnout jej do projektových plánů, nákladů a počítat s ním
jako s přínosem a konkurenční výhodou před ostatními.

1.  1.  []{#_Toc289334276} **Internacionalizace, lokalizace,
        globalizace**

Je-li potřeba vyvíjet vícejazyčné produkty je nutné upravit software
takovým způsobem, který usnadní a umožní překlad do jazyků potenciálních
zákazníků. Při těchto úpravách se můžeme setkat s třemi základními
pojmy, které je třeba od sebe rozlišovat a vymezit jejich pole
působnosti.

1.  1.  1.  []{#_Toc289334277} **Internacionalizace**

Internacionalizaci[^2^](#sdfootnote2sym){#sdfootnote2anc .sdfootnoteanc}
lze podle [(1)]{style="background: #c0c0c0"} popsat jako proces tvorby
softwaru, který předem počítá s mnoha jazyky a geografickými oblastmi,
takže se nemusíme znovu vracet a opravovat aplikaci pokaždé, když se
objeví požadavek na podporu dalšího jazyka nebo státu.

Je to zevšeobecnění, při kterém jsou programy používající pouze řetězce
v jedné řeči spojeny do obecných cest, jak provést to samé v jiných
jazycích. Jedná se tedy o jednorázovou operaci, která předchází procesu
lokalizace.

Aplikace, která podporuje internacionalizaci má následující vlastnosti:

-   Podpora dalších jazyků se obejde bez zásahu do kódu a rekompilace.

-   Textové elementy, zprávy a obrázky se ukládají mimo zdrojový kód.

-   Data vycházející z dané kultury jako je čas, datum, číslice a měna
    jsou formátovány správně vzhledem k uživatelově jazyku a geografické
    poloze.

-   Podporují se nestandardní znakové sady.

-   Aplikace je snadno rozšiřitelná o nové jazyky.

Při internacionalizaci aplikace si nemůžeme vybírat, které z výše
uvedených bodů chceme podporovat. Musí být podporovány všechny, jinak se
postup nezdaří. Jestliže například všechny texty, obrázky i tlačítka
mají správný formát, ale číslice a měna jsou formátovány špatně, pak
uživatel z dané aplikace nezíská dobrý dojem.

Cílem celé I18N je tedy software, který neobsahuje žádné kulturně
závislé informace a může být bez problémů nasazen do jakýchkoliv zemí,
podle preferencí cílových uživatelů.

\
\

1.  1.  2.  []{#_Toc289334278} **Lokalizace**

Lokalizace[^3^](#sdfootnote3sym){#sdfootnote3anc .sdfootnoteanc} je
nedílnou součástí globalizace software a následuje za procesem
internacionalizace. Lze ji podle [(2)]{style="background: #c0c0c0"}
popsat jako proces úpravy produktu pro specifickou geografickou lokaci.
Lokalizovaný program poté může provádět vstupy a výstupy ve tvaru, který
je správný pro daný jazyk a kulturní zvyklosti. V podstatě
internacionalizace je oblastí spíše programátorskou a lokalizace spíše
překladatelskou.

Lokalizace ovšem zahrnuje kromě překladu textů i další důležité
činnosti:

-   Nastavení rozměrů dialogů v případech, že je přeložený text delší
    než text původní.

-   Kulturní a místní odlišnosti, které vyžadují úpravu ikon, kurzorů,
    barev, navigací (logika posloupnosti příkazů a ergonomie) nebo
    symbolů (např. různé měrné jednotky, hodnota elektrického napětí).

-   Odlišnosti ve formátování. Například způsob zápisu telefonních
    čísel, adres, datumů, číslic, oddělovačů nebo odlišnosti ve
    způsobech oslovení.

-   Politické a ekonomické záležitosti typu nemožnost platit kreditní
    kartou online v některých zemích, pomalé nebo omezené připojení k
    internetu v rozvojových zemích, zakázané symboly (např. postavení
    muže a ženy v arabských zemích).

-   Právní záležitosti.

-   Použití klávesnice a rozdílné rozložení kláves.

-   Jazyky psané zprava doleva (hebrejština, arabština) nebo akcentované
    aj. specifické znaky některých jazyků (němčina, švédština, atd.).

Úkolem lokalizace je také určit způsob, jakým je produkt prodáván,
prezentován, jaký má design nebo prodejní obal pro patřičný trh, jakou
má technickou i obchodní podporu, jak jsou zhotovovány reporty o
prodejích atd. Jakékoliv nedostatky nedodržené důslednou lokalizací
mohou zákazníka odradit od koupi nebo užití daného produktu či služby.

![Shape1](DP_Hobel_2011_html_c286a75b.gif){#Shape1 align="left"
hspace="12" width="619" height="332"}\
\

\
\

\
\

\
\

\
\

\
\

\
\

\
\

Pokud by byl přeskočen proces internacionalizace, pak by bylo nutné
během lokalizace upravit texty, obrázky a zprávy, které jsou zakotvené
ve zdrojovém kódu. Nejen, že tyto úpravy s sebou nesou riziko zanesení
chyb, ale po provedení veškerých změn je třeba kód znovu kompilovat.
Největší nevýhodou je ale fakt, že by tyto kódové úpravy bylo třeba
provádět znovu s každým novým jazykem, který bude třeba v budoucnu v
aplikaci podporovat.

Zajímavostí je, že většina softwaru je lokalizována do ostatních jazyků
z angličtiny, popřípadě je většina prvně přeložena do angličtiny a tento
jazyk je brán jako výchozí pro ostatní překlady. Bert Esselink uvádí
[(3)]{style="background: #c0c0c0"}, že až 80 % veškerého softwaru
používá při překladech angličtinu jako výchozí jazyk do ostatních
jazyků.

Od 90. let minulého tisíciletí se dostávají do popředí počítačové
překladatelské nástroje, které pomáhají zefektivnit proces překladů,
následných kontrol a korektur, udržování slovníků, terminologií a tím
proces lokalizace velmi urychlují, šetří kapacity, čas a náklady.
Například se velmi osvědčily nástroje typu „Translation Memory", které
se využívají hlavně ve velkých projektech. Zde využívají již dříve
přeložené materiály a není tak nutné stejné (podobné) texty překládat
neustále znovu.

Je ale třeba poznamenat, že ať je software pro podporu lokalizací
sebelepší, nikdy nemůže nahradit lidský překlad.

1.  1.  3.  []{#_Toc289334279} **Globalizace**

Glabalizaci[^4^](#sdfootnote4sym){#sdfootnote4anc .sdfootnoteanc} lze
popsat dle organizace LISA (Localisation Industry Standards
Association), která ji definuje jako obchodní rozhodnutí a aktivity,
které dělají organizaci skutečně mezinárodní v celé její sféře
působnosti. Je to taková transformace obchodu a procesů, aby bez rozdílu
jazyka, země či kultury podpořila zákazníky po celém světě.

![Shape2](DP_Hobel_2011_html_33692e1d.gif){#Shape2 align="left"
hspace="12" width="511" height="366"}

\
\

Dalo by se říci, že globalizace je celopodnikový proces, který ovlivňuje
nejen překládání a úpravu produktů a služeb do daných jazyků, ale
zasahuje do firmy mnohem hlouběji. Dotýká se firemní kultury, přístupu
zaměstnanců k jednotlivým úkolům a obchodním jednáním. Nutí zaměstnance
k sebevzdělávání (ať už jazykovému nebo studii cizích kultur pro úspěšná
vyjednávání), zástupci firem jsou vysíláni na obchodní cesty do
zahraničí, navazují se styky s různými distributory a prodejci softwaru.

\

1.  2.  []{#_Toc289334280} **Průběh procesu internacionalizace**

Proces internacionalizace začíná již v počátcích vývoje projektu v době,
kdy vývojáři shromažďují nutné požadavky a předpoklady, aby mohl vůbec
vlastní vývoj začít. Proces internacionalizace je tedy stejně důležitý
jako ostatní procesy, které na počátku daného projektu přicházejí v
úvahu.

Protože platí zásada, že čím více chceme aplikaci lokalizovat, tím více
musíme internacionalizovat, je třeba určit odhad, do kterých jazyků bude
potřeba lokalizaci provést. Obecně je doporučeno internacionalizovat co
nejvíce je to možné nebo co dovolí finanční situace.

Již v počátcích je dobré zjistit, zda bude zapotřebí podporovat jazyky,
které nepoužívají latinku jako písmo. V těchto případech by bylo nutné
zvolit kódování Unicode*.* Příkladem může být požadavek lokalizovat
aplikaci do arabského jazyka. To znamená upravit celou aplikaci tak, aby
bylo možné pracovat s daty, které se čtou zprava doleva.

Následuje výčet jednotlivých položek nebo problémů, kterými je konkrétně
nutné se podle [(4)]{style="background: #c0c0c0"} v průběhu
internacionalizace zabývat, aby mohla začít vlastní lokalizace.

1.  1.  1.  []{#_Toc289334281} **Uživatelské rozhraní a tištěná
            dokumentace**

Jedná se o uložení textových elementů, chybových zpráv, videa, obrázků,
zvuků a dokumentace mimo zdrojový kód. V externích souborech by měly být
uloženy kromě klasických textových elementů (např. popisky tlačítek)
také chybové zprávy, které nastanou během práce s aplikací. Například,
když uživatel zadá desetinné číslo do formuláře, který povoluje práci
pouze s celými čísly apod. V tomto případě se jedná pouze o uložení
textů ve výchozím jazyce, zatím není proveden žádný překlad.

Kulturní odlišnosti daných zemích se mohou promítnout i do
multimediálního obsahu aplikace. Kromě gramatických odlišností (např.
členy) je třeba se zabývat tím, jaká se v daných zemích používají gesta
a třeba i mimika. Spojené ruce za hlavou mohou například symbolizovat,
že něco není v pořádku. V západních zemích je to zase symbol odpočinku
nebo naopak v Rusku toto gesto vyjadřuje nemocného člověka.

1.  1.  2.  []{#_Toc289334282} **Problémy spojené s použitím znakové
            sady**

Během internacionalizace je zapotřebí do aplikace zahrnout taková
schémata (znakové sady), která správně pokryjí veškeré znaky daného
jazyka.

Například americká abeceda rozeznává pouze 52 znaků. Jsou to [\[A-Z\] a
\[a-z\]. ]{lang="en-US"}Ostatní jazyky mají v abecedě často specifické
akcentované znaky. Například němčina má ä, ö nebo ü.

V případě, že znaková sada nepodporuje všechny znaky daného jazyka,
mohou nastat následující problémy:

-   Převod velkých a malých písmen.

-   Řazení a třídění - například ve Španělské abecedě se „ch" nachází
    mezi písmeny „c" a „d". V angličtině by toto spojení představovalo 2
    různá písmena „c" a „h".

-   Regulární výrazy.

-   Byte processing - kromě podpory správných znaků pro daný jazyk je
    třeba brát v úvahu to, že některá cizojazyčná slova mohou převýšit
    jednobajtovou velikost pro uložení.

-   Směr čtení a zápis textu - většina jazyků se čte zleva doprava,
    zatímco Hebrejština a Arabština podporují čtení zprava doleva,

-   Podpora IME - mnoho jazyků zvláště Asijské mají více znaků v
    abecedě, než kolik se vejde na klávesnici.

1.  1.  3.  []{#_Toc289334283} **Geografické odlišnosti ve formátování**

**Číslicový a měnový zápis**

Jedná se o odlišnosti v zobrazení peněžní hodnoty. V anglicky mluvících
zemích se pro oddělení jednotek používá tečka a pro oddělení tisíců
čárka (např. 1,234.56). V Německu se používá přesně opačný způsob
(1.234,56).

Kvůli neustále se měnícímu měnovému kurzu není možné v aplikaci provádět
převody mezi měnami. Tento problém se řeší přidáním měnového znaku na
konec nebo na začátek peněžní částky. Různé země používají různé znaky.
V Anglii se například používá zápis „£ 9,876,543.21", zatímco v Německu
nebo Francii „9.876.543,21 €".

**Datum a čas**

Anglický datumový formát zápisu je ve tvaru **mm/dd/yyyy**. V Německu
nebo v České republice se pak používá formát **dd.mm.yyy**.

Rozdíly jsou i v zobrazení času. Na jedné straně existuje 12 hodinový
systém (s použitím „am" a „pm") a na druhé straně 24 hodinový systém.

**Měrné jednotky**

Ve většině zemí se používá Metrický systém, zatímco například v USA se
používá Angloamerická měrná soustava. Tento problém se řeší tím, že se
společně s danou číselnou hodnotou objevují i její příslušné jednotky.
Tak není v aplikaci třeba mezi sebou jednotlivé jednotky přepočítávat.

**Poštovní adresy, telefonní čísla atd.**

V jednotlivých zemích se mohou lišit i způsoby zápisu poštovní adresy.
Například evropané budou mít problém zadávat svoji adresu do amerických
formulářů. V Evropě totiž nejsou země rozdělené na jednotlivé státy.
Pokud software vyžaduje vložení neprázdných dat, pak bude uživatel nucen
do těchto polí vkládat nesmyslné údaje.

1.  3.  []{#_Toc289334284} **Průběh procesu lokalizace**

Hlavní činností, která se provádí v průběhu lokalizace je vlastní
překlad textů. Překlad většinou vykonávají odborní překladatelé, někdy
tuto úlohu ale mohou přebírat i programátoři.

Výhodou zapojení programátorů do překladu je to, že vědí, které fráze je
třeba přeložit a které ponechat nepřeložené. Dále na rozdíl od
překladatelů dovede programátor přeložit kompletně celou frázi, i když
obsahuje proměnné.

Na druhou stranu překládání není u programátora hlavní pracovní
činností, a tak nemusejí být všechny fráze přeloženy tak precizně, jak
by to udělal profesionální překladatel. Kromě toho je programátor během
překládání vytížen a není možné jej použít pro jinou práci na projektu.

Další možností jak přeložit aplikaci je využít počítačového překladu,
který by mohl vlastní překlad velmi urychlit a zautomatizovat. Ale je
potřeba říci, že žádný takový překlad není úplně bez chyb a je většinou
zapotřebí jej ještě upravit. Někdy se dokonce stane, že se ztratí
celkový význam originálního překladu, a tak se může překlad pomocí
specializovaného softwaru někdy více prodražit, než kdyby se fráze
předaly rovnou překladateli.

1.  1.  1.  []{#_Toc289334285} **Nástrahy při provádění překladů**

Obecně je při návrhu popisků do uživatelského rozhraní třeba dávat pozor
na ty texty, které by bylo gramaticky těžké přeložit do ostatních
jazyků. Jedná se o určité slovní hříčky nebo spojení, která jsou
pochopitelná pouze v dané zemi nebo regionu.

Originální fráze a jejich překlady mohou mít rozdílnou velikost, což
působí problém při jejich zobrazování v nejrůznějších dialogových oknech
nebo tlačítkách. Při větší velikosti překladu by bylo zapotřebí rozšířit
grafické prvky tak, aby se tam jednotlivé překlady vešly a byly čitelné.
Například tlačítko s nápisem „Cancel" může být pro německý ekvivalent
„Abbrechen" příliš malé. Microsoft podle
[(5)]{style="background: #c0c0c0"} doporučuje ponechat o 30 procent více
volného místa, které může být využito v případě delšího překladu.

1.  1.  2.  []{#_Toc289334286} **Lokalizace netextových prvků**

Počítače nekomunikují s uživateli pouze psaným textem. Proto je třeba
přizpůsobit i ostatní prvky aplikace konkrétním požadavkům uživatele,
aby měl zajištěnu co nejpohodlnější práci.

Mezi jednotlivými zeměmi existují odlišnosti ve vnímání stejných značek,
ikon, barev nebo i směru čtení textu. Například americké uživatelské
prostředí, ve kterém se objevují dopravní značky, které nejsou všeobecně
známé budou dělat problémy i uživatelům z Velké Británie.

Překlady netextových prvků jsou tedy určeny pro člověka, který zná dobře
kulturní a jazykové specifikace dané země. V tomto případě to nemusí být
programátor ani překladatel.

4.  []{#_Toc289334287}[]{#_Ref288398365} **Java a internacionalizace**

Internacionalizace byla v počátcích vývoje důležitou součástí jazyka
Java. Již v první verzi 1.0 se objevila podpora kódování znaků v
Unicode, která velmi podpořila proces
internacionalizace[(6)]{style="background: #c0c0c0"}.

Díky spolupráci firmy Sun se společností
Taligen[^5^](#sdfootnote5sym){#sdfootnote5anc .sdfootnoteanc}, bylo do
JDK zabudováno mnoho tříd, které napomáhají v procesu
internacionalizace. Mnoho prvků, které dosud nebyly do JDK
zaimplementovány (a možná nikdy nebudou) jsou dostupné jako doplňky a je
možné je zdarma získat na www stránkách
ICU4J[^6^](#sdfootnote6sym){#sdfootnote6anc .sdfootnoteanc}.

Java sama o sobě je mezinárodní software a implicitně podporuje okolo
150 geografických lokalit[^7^](#sdfootnote7sym){#sdfootnote7anc
.sdfootnoteanc}. Pokud tedy použijeme vhodné třídy můžeme získat zdarma
mnoho údajů, které jsou již lokalizované. Například práce s velkým
množstvím fontů (arabské, čínské, atd.) dále datumové (jména dnů v týdnu
a jména měsíců), číselné a měnové údaje v jednotlivých jazycích.

V případě, že je potřeba program lokalizovat do jazyka, který se
nenachází mezi implicitně zabudovanými, je možné jej do JDK jednoduše
přidat jako externí modul. Ten se bude vždy načítat při inicializaci v
běhovém prostředí Javy.

Je třeba poznamenat, že kód nebyl vždy v I18N ideální. Například ve
třídě java.util.Date je mnoho tříd, které bylo třeba nahradit novými.
Kromě toho i v aktuální verzi JDK 1.6 jsou podporovány pouze dva
kalendářní systémy (Gregoriánský a Japonský).

1.  1.  []{#_Toc289334288} **Locale**

Objekty této třídy v sobě uchovávají informace o jazyku a oblasti (zemi,
státu). Jednoznačnost dané lokality je zajištěna pomocí následujících
tří parameterů:

-   zkratka jazyka,

-   zkratka země, státu (volitelně),

-   variant kód (volitelně).

Variantní záznam je určen k tomu, aby blíže specifikoval danou lokalitu.
Vždy se ale nemusí jednat pouze o geografická místa. Tímto údajem je
také možné například vymezit určitý typ internetového prohlížeče.

Stejné číslo, které se používá v německy mluvící části Švýcarska bude
vypadat například v rakouské verzi němčiny odlišně. V následující
tabulce jsou uvedeny další konkrétní příklady:

  ----------------------------- -------------------------------
  []{#pgfId-50789} **Locale**   **Zformátované číslo**
  Němčina (Rakousko)            []{#pgfId-50795} 123.456,789
  Němčina (Německo)             []{#pgfId-50799} 123.456,789
  Němčina (Švýcarsko)           []{#pgfId-50803} 123\'456.789
  Angličtina (Spojené státy)    []{#pgfId-50807} 123,456.789
  ----------------------------- -------------------------------

[]{#_Toc289334380} Tabulka [1]{style="background: #c0c0c0"} - Formát
čísla pro různé lokality

Objekty třídy java.util.Locale jsou pouze deskriptory (popisovače),
které samy o sobě nejsou schopny žádné činnosti. Neobsahují tedy samotné
lokalizované údaje, nýbrž se poskytují ostatním třídám jako parametry
jejich metod. Ty pak již dokáží konkrétní údaje zobrazit.

Následuje výčet možností, které můžeme pomocí identifikátoru Locale
konkrétně ovlivnit:

-   jména měsíců,

-   jména dnů v týdnu,

-   první den v měsíci,

-   (logiku) řazení,

-   informace o časovém pásmu.

Dále je třeba poznamenat, že tyto metody nemusejí podporovat veškeré
kombinace jazyků a zemí, např. takto není podporovaná španělština v USA.

1.  1.  1.  []{#_Toc289334289} **Výchozí Locale**

Pokud použijeme statickou metodu Locale.getDefault() dostaneme objekt,
který popisuje aktuální jazykové nastavení právě platné instance JVM.
Toto nastavení je možné uživatelsky změnit v operačním systému (Windows
XP):

Start/OvládacíPanely/Místní a jazykové nastavení

Pokud je jako výchozí jazyk nastavena například
Čeština[^8^](#sdfootnote8sym){#sdfootnote8anc .sdfootnoteanc} a aplikace
obsahuje příslušné české překlady, pak se všechny lokálně závislé texty
zobrazí v češtině.

Výchozí Locale má smysl měnit pouze před spuštěním celé aplikace. Za
běhu programu by se měnit nemělo, neboť jeho hodnotu sdílí mnoho lokálně
závislých komponent.

V případě, že je za běhu aplikace potřeba změnit pouze číselný formát
(např. na německý), je nutné uvést příslušnou lokalitu v parametru k
tomu určené třídy a nikoliv měnit výchozí Locale.

Ukázka správného použití:

NumberFormat.getNumberInstance(Locale.Germany)

1.  2.  []{#_Toc289334290}[]{#_Ref289279483}[]{#_Ref289279478}
        **Oddělení jazykově závislých dat od zdrojových kódů**

Aby mohl být proveden vlastní překlad lokálně závislých textů je
zapotřebí tyto texty separovat od zdrojových kódů a uložit je na
speciální místo, ze kterého je aplikace bude moci využívat.

Ukázka naprosto nevhodného řešení, jak podporovat v aplikaci více
jazyků:

if (jazyk == \"český\")

zobraz(\"Ahoj!\");

else if (jazyk == \"anglicky\")

zobraz(\"Hello!\");

else \...

V případě, že je třeba přidat nový jazyk, bylo by nutné upravit všechny
zdrojové soubory, které pracují s texty. Každý zásah do kódu sebou nese
riziko zanesení chyby a v tomto případě, kdy bude třeba upravit značnou
část kódu, je velmi pravděpodobné, že dřív nebo později k chybě dojde.
Navíc nejsou texty nijak pohromadě a jejich hledání a úprava by byla
složitá.

Otázka oddělení jazykově závislých dat je v Javě vyřešena použitím
tzv. RessourceBundle. Ty jsou často představovány konfiguračními
soubory[^9^](#sdfootnote9sym){#sdfootnote9anc .sdfootnoteanc} do kterých
je možné vkládat příslušné lokalizované texty. Pro každou geografickou
oblast, kterou je třeba v aplikaci podporovat je možné vytvořit vlastní
„property" soubor. Na základě nastaveného výchozího Locale se pak určí,
ze kterého souboru (jazykové verze) se budou získávat texty, které se
pak zobrazí v aplikaci například jako popisky tlačítek.

Další výhodou oddělení jazykově závislých textů do samostatných souborů
je to, že není potřeba aplikaci znovu rekompilovat. Pokud v budoucnu
přibude nutnost dalšího jazyka, pak se jednoduše přidá nový konfigurační
soubor.

Aby bylo možné v aplikaci zobrazit příslušný překlad k originální frázi,
je třeba se na tyto informace jednotně odkázat pomocí klíče, který musí
být pro příslušné jazykové překlady vždy stejný.

**Ukázka:**

**Originální** například **německý** „property" soubor:

salutation=Hallo Welt

Obsah **českého** souboru:

salutation=Ahoj světe

Obsah **anglického** souboru:

salutation=Hello World

Soubory s texty mají formát určený třídou java.util.Properties, tedy
**klíč=hodnota**, kde klíč i hodnota jsou řetězcového typu. V kódu se
tedy na jednotlivé texty odkazujeme (kromě názvu souboru) pomocí
**klíčů**, a konkrétní překlad se tedy dohledává podle specifikovaného
Locale.

**Ukázka:**

Locale cestina = new Locale(\"cs\", \"CZ\");

ResourceBundle csTexty = ResourceBundle.getBundle(\"Texty\",cestina);

System.out.println(csTexty.getString(\"salutation\"));

Metoda getBundle() se pokouší najít takový soubor, jehož jméno je
tvořeno zadaným řetězcem „Texty", českým Locale a příponou .properties.
Pokud jej nenalezne, zkouší hledat soubor s obecnějším Locale. Pokud v
některém z nich nalezne klíč salutation tak vrátí jeho hodnotu a ukončí
vyhledávání. Hledání příslušného klíče se v tomto případě bude provádět
v následujících souborech a vždy začne od shora.

-   Texty_cs_CZ.properties

-   Texty_cs.properties

-   Texty.properties

Aby bylo možné soubory vyhledat a získat lokalizované texty, je nutné,
aby jejich cesta k těmto souborům byla součástí classpath daného JVM.

**Poznámky**

Soubor Texty.properties obsahuje vždy texty podle používaného výchozího
Locale. V případě, že byla jako výchozí jazyk nastavena čeština byly by
soubory Texty_cs.properties a Texty_cs_CZ.properties zbytečné.

Budeme-li potřebovat více jazykových verzí, které se liší pouze Country
(nebo pouze Variant) příznakem, např. Rakousko (\_de_AT), Švýcarsko
(\_de_CH), Německo (\_de_DE), pak je vhodnější ty fráze, které jsou
společné všem třem verzím přesunout do jejich nadřazeného (\_de)
souboru. V případě, že se v podřízeném souboru nebude požadovaný klíč
vyskytovat bude se vždy automaticky prohledávat i jemu nadřazený. V
podřízených souborech je tedy užitečné uchovávat jen speciální fráze.

ResourceBundle nemusí být pouze soubor typu .properties, jednotlivé
překlady je také možné uchovávat v class souborech. Není to, ale příliš
běžný způsob, neboť je zapotřebí „zbytečně" zasahovat do kódu.

„Property" soubor, který nebyl vytvořený ve vývojovém prostředí používá
nativní 8 bitové kódování operačního systému a tudíž by se měly všechny
akcentované aj. specifické znaky daného jazyka zapisovat pomocí \\uXXXX
konvence (hexadecimálně číslo Unicode znaku).

**Ukázka (nahrazení ě sekvencí \\u011B):**

#Texty_cs_CZ.properties

salutation=Ahoj sv\\u011Bte

Pro převod speciálních znaků na unicode konvenci (i opačně) je možné
použít nástroj native2ASCII, který je od verze 1.1 součástí JDK. Soubory
pocházející z vývojového prostředí provádějí konverzi automaticky.

1.  3.  []{#_Toc289334291} **Formátování textů v různých jazycích**

Protože Java automaticky v JDK obsahuje informace ohledně formátování
datumových, časových a číslicových dat pro různé jazyky, je výhodné v
dané aplikaci používat právě tyto již předem připravené informace.
Hierarchie formátovacích tříd je v Javě umístěna v balíku java.text.

![Shape4](DP_Hobel_2011_html_6ada53b5.gif){#Shape4 align="left"
hspace="12" width="444" height="296"}\
\

\
\

\
\

\
\

\
\

\
\

\
\

\
\

1.  1.  1.  []{#_Toc289334292} **Formátování data a času**

Datumové a časové formáty pro různé geografické lokality jsou uvedeny ve
třídě java.text.DateFormat.

Ukázka datumového formátování dle [(7)]{style="background: #c0c0c0"}:

DateFormat dateFormatter =
DateFormat.getDateInstance(DateFormat.DEFAULT,

currentLocale);

Date today = new Date();

String dateOut = dateFormatter.format(today);

Konkrétní výstup bude záviset na zvoleném hodnotě currentLocale:

30 juin 2009 fr_FR

30.06.2009 de_DE

Jun 30, 2009 en_US

K úspěšnému formátování je tedy zapotřebí provést 2 kroky. Nejprve
pomocí meotdy getDateInstance() inicializovat tzv. „formátovač", kterému
je třeba předat dva parametry. První určuje množství vypisované
informace (**mód** výpisu) a druhý určuje, na základě jaké lokality se
vybere konkrétní formát. Jako druhý krok je třeba zavolat metodu
format(), která provede samotné formátování.

V uvedeném případě se používá výchozí (DEFAULT) mód výpisu. Dále ještě
existují SHORT, MEDIUM, LONG a FULL. Vzájemné rozdíly je možné porovnat
v následující tabulce:

+-----------------------+-----------------------+-----------------------+
| **Mód**               | **Locale = cs**       | **Locale = fr**       |
+-----------------------+-----------------------+-----------------------+
| DEFAULT               | 30.6.2009             | 30 juin 2009          |
+-----------------------+-----------------------+-----------------------+
| SHORT                 | 30.6.09               | 30/06/09              |
+-----------------------+-----------------------+-----------------------+
| MEDIUM                | 30.6.2009             | 30 juin 2009          |
+-----------------------+-----------------------+-----------------------+
| LONG                  | 30\. červen 2009      | 30 juin 2009          |
+-----------------------+-----------------------+-----------------------+
| FULL                  | úterý, 30. červen     | mardi 30 juin 2009    |
|                       | 2009                  |                       |
+-----------------------+-----------------------+-----------------------+

[]{#_Toc289334381} Tabulka [2]{style="background: #c0c0c0"} - České a
francouzské předdefinované datumové formáty

Pro výpis času platí stejná pravidla. Pouze instance třídy DateFormat se
získá pomocí metody getTimeInstance(). Jinak je vše stejné včetně módu
výpisu.

Pokud je zapotřebí zobrazit společně datumovou i časovou informaci lze
toho snadno dosáhnout použitím metody getDateTimeInstance(), které je
zapotřebí předat tři parametry. První a druhý určují mód data
(respektive času), třetím parametrem se zadává objekt Locale. V případě,
že se použije metoda bez parametrů, pak budou autmaticky dosazeny
výchozí hodnoty.

Výstupní společné datumové i časové informace může vypadat například
takto:

Úterý, 30. červen 2009 14:28:20 GMT+2:00

1.  1.  2.  []{#_Toc289334293} **Vlastní formát data a času**

V případě, že uživateli nevyhovuje žádná kombinace předdefinovaných
vzorů je možné pomocí třídy java.text.SimpleDateFormat vytvořit vzory
vlastní. Tyto vlastní formátovací vzory se definují pomocí speciálních,
k tomu určených symbolů, které je možné vidět v následující tabulce.

+-----------------------------------+-----------------------------------+
| **Vlastní formát**                | **Locale = Velká Británie**       |
+-----------------------------------+-----------------------------------+
| dd.MM.yy                          | 30.12.1899                        |
+-----------------------------------+-----------------------------------+
| yyyy.MM.dd G \'at\' hh:mm:ss z    | 2009.06.30 AD at 04:28:20 GMT     |
+-----------------------------------+-----------------------------------+
| EEE, MMM d, \'\'yy                | Tue, Jun 30, \'09                 |
+-----------------------------------+-----------------------------------+
| h:mm a                            | 4:28 PM                           |
+-----------------------------------+-----------------------------------+
| H:mm                              | 16:28                             |
+-----------------------------------+-----------------------------------+
| H:mm:ss:SSS                       | 16:28:20:515                      |
+-----------------------------------+-----------------------------------+
| K:mm a,z                          | 4:28 PM,GMT                       |
+-----------------------------------+-----------------------------------+
| yyyy.MMMMM.dd GGG hh:mm aaa       | 2009.June.30 AD 04:28 PM          |
+-----------------------------------+-----------------------------------+

[]{#_Toc289334382} Tabulka [3]{style="background: #c0c0c0"} -
Uživatelsky definované datumové formáty

1.  1.  3.  []{#_Toc289334294} **Kalendářní systém**

Gregoriánský kalendář který se používá v Evropě, USA a v celé světové
obchodní korespondenci není zdaleka jediným letopočtem. Na mnoha místech
světa se počítají roky jinak. Například v Číně, Izraeli či Indii.

Časové a datumové operace byly v Javě původně zabezpečovány pomocí třídy
java.util.Date. Ta ale obsahovala několik nedostatků, které znemožňovaly
správné zobrazení časových a datumových operací. Od verze JDK 1.1
existuje třída Calendar, respektive její potomek GregorianCalendar,
které vylepšily původní implementaci a opravily většinu nedostatků.

Třída Date představuje časový okamžik jako takový, vyjádřený v
milisekundách od začátku unixové epochy (1.1.1970 GMT). Interně používá
typ long, takže může reprezentovat čas zhruba v úseku několika stovek
milionů let. Pokud potřebujeme pracovat s časem, který je vyjádřený
lidským způsobem (tedy způsobem závislým na určité kultuře), použijeme
třídu Calendar. Ta zároveň bez problémů zvládá i operace s posunem času.

Ukázka:

Calendar c =Calendar.getInstance(TimeZone.getTimeZone(\"CET\"), new
Locale([\"]{lang="en-US"}cs[\"]{lang="en-US"}));

c.set(2008, Calendar.JANUARY, 31, 12, 0, 0);

//výpis: Čtvrtek, 31. leden 2008 12:00:00 CET

c.roll(Calendar.MONTH,1);

//výpis: Pátek, 29. únor 2008 12:00:00 CET

Nejprve se nastaví aktuální čas na poledne 31.1.2008 a poté se zjistí,
který okamžik je o měsíc později. Je zde dobře vidět, že třída Calendar
spolehlivě pracuje i s přestupnými roky.

1.  1.  4.  []{#_Toc289334295} **Časová pásma**

Pro převod času mezi časovými pásmy se používá třída java.util.TimeZone,
která řeší i problém posunu z letního na zimní čas. Tato otázka ovšem
není až tak jednoduchá, protože existují i země, které se mezi letním a
zimním časem vůbec nepřepínají.

1.  1.  5.  []{#_Toc289334296} **Formátování čísel**

Rozdílné číselné formáty, které se používají v jednotlivých zemích je
možné zjistit pomocí třídy java.text.NumberFormat. Je možné ji obecně
použít na formátování všech základní číselných datových typů.

Následuje výčet rozdílů formátování, na které můžeme narazit během
lokalizace číselných hodnot:

-   Rozdíl „americké" desetinné tečky a „naší" desetinné čárky.

-   Vyjádření záporných čísel - díky tomu, že se v arabském světě píše
    zprava doleva je znaménko mínus vždy na pravé straně. Z našeho
    pohledu vždy až za číslem.

Abychom získali požadovaný číselný formát je v obou výše zmíněných
případech možné použít metodu NumberFormat.getNumberInstance(Locale
loc)*.*

1.  1.  6.  []{#_Toc289334297} **Zavedené symboly pro měnu a jejich
            konkrétní umístění**

Označení měny může být provedeno buďto pomocí speciálního znaku (\$, €,
£) nebo příslušné zkratky (např. Kč), případně kombinací obojího. Pro
mezinárodní účely existuje tří písmenné označení definované standardem
ISO. Například USD pro americký dolar, GBP pro anglickou libru atd.

V evropských zemích, které zatím nepřešly na euro, musí být v současné
době software schopen zpracovávat jak vlastní měnu tak i měnu v eurech.
Tento požadavek je zapotřebí hlavně ve firmách, které komunikují se
zahraničními firmami (například software pro podporu kamionové dopravy).

V neposlední řadě je nutné si uvědomit, že Java nepodporuje žádné
kursové přepočty mezi jednotlivými měnami a není možné pouze zaměnit
symbol amerického dolaru za symbol české koruny (nebo naopak). Je
zapotřebí buďto explicitně podle aktuálního kurzu převádět částku z
jedné měny do druhé. Nebo druhým a snadnější řešení je nějakým způsobem
uživatele informovat, že daná hodnota je uvedena v amerických
dolarech[^10^](#sdfootnote10sym){#sdfootnote10anc .sdfootnoteanc}.
Výhodou je, že není třeba mít neustálý přístup k aktuálním měnovým
kurzům.

1.  1.  7.  []{#_Toc289334298} **Speciální formátování čísel**

Potřebujeme-li konkrétní číslo zformátovat tak, aby zobrazovalo
nevýznamové nuly, nebo pokud potřebujeme číslo vytisknout na určitý
počet míst, můžeme využít služeb třídy java.text.DecimalFormat. Ta pro
tyto případy obsahuje již předdefinované metody. Popřípadě je také možné
stanovit vlastní vzor, podle kterého se bude číslo formátovat.

Pro formátování reálných čísel ve formě mantisa-exponent platí jen druhá
možnost, tj. podle vzoru. Tímto způsobem ale nejdou formátovat čísla,
která nejsou uvedena v desítkovém číselném systému. Dále nelze
zformátovat „obrázková" čínská nebo japonská
čísla[^11^](#sdfootnote11sym){#sdfootnote11anc .sdfootnoteanc}.

1.  1.  8.  []{#_Toc289334299} **Formátování textů**

V případě, že by byly všechny texty statické, pak by jejich pouhé
oddělení od zdrojových kódů bylo postačující. Příkladem jsou
informativní, varovné nebo chybové hlášky, které mohou za běhu programu
měnit svoji podobu v závislosti na zadaných datech od uživatele.
Přeložený statický text pak není postačující a je třeba jej doplnit o
proměnné, které se načtou až za běhu aplikace.

**Například:**

The [printer]{.underline} is enabled.

The [modem]{.underline} is enabled.

The [network]{.underline} is enabled.

[String finalContext = "The" + varElement + "is
enabled.";]{lang="en-US"}

Proměnná varElement může obsahovat jednu z možností printer, modem nebo
network. Tento postup je velmi užitečný pro programátory (zamezuje
duplicitám), nicméně překladatelé s ní budou mít problém, neboť pro ně
bude obtížné najít celkový kontext. Bez znalosti celkového kontextu
nebude překladatel moci texty správně přeložit. Částečné řešení tohoto
problému je použití komentářů, které by chybějící kontext doplňovaly.
Tento způsob ale nelze použít u jazyků, které používají členy, protože
je potřeba časovat příslušná slovesa.

Výše uvedený příklad by se mohl do francouzštiny přeložit tímto
způsobem:

L[\'imprimante
]{lang="en-US"}[[activ]{.underline}]{lang="en-US"}[ée]{.underline}.

Le modem [activé]{.underline}.

Le réseau [activé]{.underline}.

V tomto případě tedy není jiná možnost, než do RessourceBundle uložit
všechna tři spojení, kde bude uvedeno pro každé podstatné jméno i
příslušné sloveso. Přiřazení podstatného jména do věty až za běhu
programu (pomocí proměnné) možné není, neboť francouzský ekvivalent
slovesa (enabled) se na rozdíl od anglického mění.

Existují i další gramatické odlišnosti, které v lokálně závislých
textech znemožňují používání proměnných. V následujícím příkladě je však
použití proměnných nevyhnutelné, neboť není předem znám počet chyb ani
soubor, ve kterém se bude provádět pravopisná kontrola.

+-----------------------------------+----------------------------------+
| **Angličtina**                    | **Němčina**                      |
+-----------------------------------+----------------------------------+
| There were 3 spelling mistakes in | Datei foo enth[ält 3             |
| file foo.                         | ]{lang="de-AT"}Rechtsreibfehler. |
+-----------------------------------+----------------------------------+

[]{#_Toc289334383} Tabulka [4]{style="background: #c0c0c0"} - Výstupní
informace o pravopisné kontrole ze souboru „foo"

Java řeší všechny gramatické odlišnosti jednotlivých jazyků použitím
třídy java.text.MessageFormat. Ta zároveň také umožňuje práci
s proměnnými.

**Ukázka:**

Soubor „texts_en.properties":

WarningMsg = There were [{0} spelling mistakes in file
{1}.]{lang="en-US"}

[Pou]{lang="en-US"}žití třídy „MessageFormat":

1: [int spellingMistakes = 3;]{lang="en-US"}

[2: String fileName = "foo";]{lang="en-US"}

[4: Object\[ \] arguments = {new Integer(spellingMistakes),
]{lang="en-US"}

[fileName};]{lang="en-US"}

[5: ResourceBundle resource =
RessourceBundle.getBundle("texts",Locale.UK);]{lang="en-US"}

[6: String out =
MessageFormat.format(resource.getString("WarningMsg"),arguments);]{lang="en-US"}

[7: System.out.println(out);]{lang="en-US"}

Řádky číslo 1 a 2 reprezentují proměnné hodnoty, které se mohou
vyskytovat v závislosti na použitém jazyku na různých místech textu. Ve
většině případů ovšem nejsou přímo takto inicializovány, ale jsou
dynamicky generovány až za běhu programu. Například aktuální datum pro
zadaný Locale apod.

Všechny proměnné, které je třeba připojit k textu na výstup je nutné
uložit do jednoho pole, což je provedeno na řádce číslo 4. Nezáleží na
tom, v jakém pořadí jednotlivé proměnné do pole uložíme, je pouze nutné
zachovat toto pořadí i pro odkazy v příslušném RessourceBundle souboru.

Konkrétně v tomto případě je proměnná spellingMistakes uložena na prvním
(nultém) indexu pole. Je tedy třeba se na hodnotu této proměnné
odkazovat v příslušném RessourceBundle souboru pomocí značky **{0}**. V
textu je také zároveň možné se vícekrát odkázat na tutéž proměnnou.

**Ukázka:**

File {1} had {0} mistakes. That\'s {0} spelling mistakes!

Na řádce číslo [6]{lang="de-DE"} je uvedena metoda:

format(String pattern, Object\[\] arguments),

do které je možné vložit vzor, který již obsahuje jednotlivé odkazy na
proměnné z druhého argumentu. Formátování v tomto případě tedy provádí
spojení statického textu a předložených proměnných.

Často se také může stát, že hodnoty proměnných mohou být objekty typu
Date nebo Number. V případě datumového formátování se automaticky zavolá
metoda DateFormat.getDateTimeInstance() a v případě formátování
číselných hodnot pak metoda NumberFormat.getInstance(). Obě metody se na
základě použitého Locale vrátí příslušný objekt a převedou jej na
řetězec. Přímo v RessourceBundle souboru je pak možné uvést ještě další
pravidla, jak detailněji zformátovat objekty typu Date a Number.

**Příklad:**

Obsah souboru „texts_en.properties":

InfoMsg = "{0} was born at {1, time, short} on {1, date, long}.

//time, short a date,long představují detailnější specifikaci
//nahrazované proměnné.

Použití třídy „MessageFormat":

Object\[ \] arguments = {"John", new Date() };

RessourceBundle resource = RessourceBundle.getBundle("texts");

MessageFormat formatter = resources.getString("InfoMsg",

arguments);

Výstup:

[John was born at 4:28 PM on June 30, 2009.]{lang="en-US"}

1.  4.  []{#_Toc289334300} **Problematika speciálních znaků**

Existuje několik způsobů jak v počítači zobrazit znaky daného jazyka.
Liší se tím, jaké znaky dokáží zobrazit (jaký používají znakový
repertoár) a kolik místa v paměti počítače zabírá jeden znak. Ve všech
případech je ale každému znaku vždy přiřazen jednoznačný číselný kód,
který počítače rozeznávají pomocí použité kódované znakové sady.

1.  1.  1.  []{#_Toc289334301} **ASCII**

Podle [(8)]{style="background: #c0c0c0"} jde o historicky
nejpoužívanější znakovou sadu, která definuje znaky anglické abecedy a
ze které vychází většina současných ostatních standardů.

Obsahuje:

-   Velká a malá písmena anglické abecedy (A-Z, a-z).

-   Číslice (0-9).

-   Interpunkční znaménka (, . : ; atd.) a další znaky (@ \$ \~ + - \* /
    % atd.).

-   Řídící (netisknutelné) kódy.

Kód ASCII je podle původní definice sedmibitový, a všechny kódy této
znakové sady mají přiřazené unikátní číslo v rozmezí 0 až 127. Pro
potřeby anglického jazyka je tedy ASCII ve většině případů postačující.
V určitých případech se však mohou najít výjimky. Například se v této
sadě používá pouze jediný symbol měny, a to americký dolar (\$).

Rozmezí 128 čísel je příliš malé na to, aby bylo možné zakódovat třeba
jen evropské národní abecedy, které často obsahují znaky s diakritikou.
Pro potřeby jednotlivých jazyků byly vytvořeny různé kódové tabulky,
význam kódů nad 127 tedy není jednoznačný.

Drtivá většina osmibitových znakových sad pouze rozšiřuje ASCII tím, že
přidávají významy kódům 128-255.

Dle [(9)]{style="background: #c0c0c0"} následuje výčet osmibitových
kódování, které podporují češtinu a zároveň jsou podporovány i v jazyku
Java:

1.  1.  2.  []{#_Toc289334302} **Cp1250**

Kódování používané firmou Microsoft. Výchozí kódování pro JDK, která se
používají na operačních systémech Windows.

1.  1.  3.  []{#_Toc289334303} **Cp852**

Kódování používané v MS-DOSu a také konzolovém oknu Windows.

1.  1.  4.  []{#_Toc289334304} **ISO8859_2**

Kódování dle mezinárodní normy používané výhradně v prostředí Unixů, je
známe též pod názvem ISO LATIN2.

Celkově existuje minimálně 110 různých kódování znaků. S rozvojem
Internetu se čím dál více vyměňují dokumenty, a tak nespočet těchto
kódování způsobuje problémy. Z toho důvodu vyvstal požadavek na jedinou
globální abecedu, jež by pokryla všechny dosud známé potřeby a byl
umožněn vývoj takového software, který bude snadno přizpůsobitelný
lokálním jazykovým podmínkám.

1.  1.  5.  []{#_Toc289334305} **Unicode**

Velmi obsáhlá znaková sada, která podporuje výměnu, zpracování a
zobrazení textů v různých současných a historických jazycích. V jednom
dokumentu je tedy možné zobrazit např. česká písmena i znaky azbuky.

Toto kódování zavedlo *[Unicode Consortium]{style="font-style: normal"}*
a nadále ho vyvíjí. V současné době je k dispozici verze 2.0. Prvních
127 znaků v Unicode má stejný kód jako v ASCII. Tím hned z počátku
odpadla velká část problémů, protože texty využívající jen anglické
abecedy jsou v podstatě stejné v obou kódováních.

Unicode podporuje 16 bitové kódování, což zajišťuje dostatečnou kapacitu
pro všechny známé jazyky. Například čínská nebo japonská abeceda
obsahuje okolo 10 tisíců znaků, z toho důvodu by nebylo možné použít
klasické osmibitové kódování, neboť to může zobrazit maximálně 256
znaků.

**Větší délka textu**

Text je po převodu z osmibitového kódování do Unicode dvojnásobně delší,
zdánlivě bez přidání informační hodnoty. Výsledek zabere víc místa při
uložení a také následné zpracování je pomalejší.

***[256 krát větší znaková sada]{style="font-style: normal"}***

Znaky na počítači se zobrazují pomocí fontů, které pro Unicode musí
obsahovat *[256 krát]{style="font-style: normal"}* více znaků než pro
osmibitové znakové sady. Vzhledem k tomu, že v mnoha jazycích se použije
jen nepatrný zlomek celkového množství, znaky navíc zbytečně zabírají
místo.

***[Nekompatibilita s osmibitovým
prostředím]{style="font-style: normal"}***

Naprostá většina současných operačních systémů používá pro ukládání a
reprezentaci znaků osmibitová kódování. Nastává tak problém, jak
přizpůsobit šestnáctibitové znaky Javy osmibitovým znakům jejího okolí.

V mnoha jazycích (i v češtině) netvoří specifické znaky (např. znaky s
diakritikou) ani zdaleka většinu písmen. I pro obsáhlé texty postačuje
ASCII, částečně proložené akcentovaným znakem. Pro takové texty je
naprosto zbytečné použít dva bajty na uložení každého písmene, jeden
bajt plně dostačuje. Ne každé médium také podporuje binární přenos a ne
vždy vyhovuje zápis Unicode znaku jako dva po sobě následující byty.
Postupem času vzniklo několik různých jiných zápisů Unicode, které řeší
některé problémy s přenosem nebo používáním Unicode.

1.  1.  6.  []{#_Toc289334306} **UTF-8**

Jedná se o kódování s proměnnou šířkou pro reprezentaci znaku. Jeden
znak tak může být kódován pomocí jednoho, dvou nebo tří bytů.

Základní myšlenkou UTF-8 je fakt, že velká část textů je psána latinkou
a z velké části je většina psána jen znaky anglické abecedy, tj.
neakcentovaně. Pokud jsou použity akcentované znaky, pak je jich
relativně málo co do počtu (v češtině je 15 akcentovaných znaků) i co do
četnosti (akcentované znaky mají v textu asi 10% výskyt). Za tohoto
předpokladu může UTF-8 kódovat znaky anglické abecedy jedním bajtem a
akcentované znaky latinky dvěma bajty. V neposlední řadě je zapotřebí
převést toto kódování na Unicode, neboli určit, které dvojice či trojice
bajtů po sobě jdoucích tvoří jeden znak.

S Unicode textem zapsaným v UTF-8 lze zacházet stejně jako s obyčejným
osmibitovým, není třeba nic speciálně ošetřovat ani psát žádný speciální
programovací kód pro kompatibilitu s Unicode.

Formát UTF-8 tak odstraňuje všechny nevýhody nasazení Unicode. Zachovává
kompatibilitu se stávajícím kódem, není tolik náročný na paměť a přitom
umožňuje aplikacím použít všech výhod univerzální mezinárodní znakové
sady. Proto se UTF-8 prosazuje jako univerzální formát pro výměnu
dokumentů v Unicode.

1.  5.  []{#_Toc289334307} **Problémy spojené s používáním znakových
        sad**

Nejjednodušším problémem je použití např. češtiny pro jména
identifikátorů. Zde se jedná pouze o to, aby byl program správně
přeložen. Používá-li se JDK pod Windows, je jako výchozí kódování
nastaveno Cp1250, a je tak možné použít češtinu bez jakýchkoli problémů.
Toto výchozí kódování je nastaveno jen tehdy, pokud je ve Windows
nastavena česká lokalita:

Start/OvládacíPanely/Místní a jazykové nastavení/Místní
nastavení/Čeština

Nastanou-li s překladem potíže, je možné použít přepínač -encoding,
který zabezpečí na všech platformách správný překlad zdrojového kódu
obsahujícího akcentované znaky. Jako parametr je mu možné předat jednu z
následujících možností: Cp1250, ISO8859_2, Unicode a UTF-8. Protože Java
vnitřně pracuje se znaky v kódování Unicode je také možné jakýkoliv
akcentovaný znak zapsat posloupností \\uXXXX, kde XXXX jsou šestnáctkové
číslice (\\u011B je znak „ě").

Pokud spuštění a překlad programu proběhl bez problémů a nenastala žádná
chyba, není ještě vyhráno. Dalším problémem může být, že vypisované
znaky nevidíme ať již na konzoly, v souborech nebo GUI správně.

1.  1.  1.  []{#_Toc289334308} **Speciální znaky na konzoly**

Podle [(9)]{style="background: #c0c0c0"} je nesprávné zobrazení znaků
způsobeno tím, že konzolové okno Windows očekává češtinu v kódování
Cp852, ale program mu ji posílá v Cp1250.

Základem veškerých změn kódování jsou třídy InputStreamReader a
OutputStreamReader, které představují spojení mezi osmibitovými znaky
operačního systému a šestnáctibitovými znaky Javy. Při čtení a při
zápisu probíhá překódování znaků podle výchozího nastaveného kódování.
Tím je pro vstup i výstup kódování češtiny ve Windows použito Cp1250.

Pokud je zapotřebí výchozí kódování změnit, je třeba do konstruktoru
požadované třídy uvést jako první parametr instanci třídy InputStream,
respektive OutputStream, které zajistí automatickou změnu kódování. Jako
druhý parametr je pak zapotřebí uvést jméno požadovaného kódování.
V případě češtiny je možné předložit kodování Cp1250, ISO8859_2 nebo
Cp852[^12^](#sdfootnote12sym){#sdfootnote12anc .sdfootnoteanc}.
Parametry Unicode či UTF8 lze také použít, ale nemá to zde smysl,
protože nepředstavují osmibitové kódování.

1.  1.  2.  []{#_Toc289334309} **Speciální znaky v souborech**

Práce se soubory je velmi podobná práci s konzolovým oknem, neboť jsou
zde také nejčastěji reprezentovány pomocí osmibitového kódování. Pro
práci s šestnáctibitovými znaky existuje v Javě třída InputStreamReader,
která načtené znaky konvertuje do požadovaného kódování. Totéž platí pro
třídu OutputStreamWriter, která sice zapisuje šestnáctibitové znaky, ale
v souboru se objeví jejich osmibitová náhrada, dle použitého kódování.

Alternativně je možné předem vytvořit soubor jako šestnáctibitový a
toto kódování uvést při čtení (zápisu) jako parametr konstruktoru třídy
InputStreamReader (nebo OutputStreamWriter) . Šestnáctibitový soubor je
možné vytvořit buďto použitím jazyka Java nebo např. pomocí známého
nástroje „Poznámkový blok", ve kterém je možné při ukládání zvolit
kódování Unicode.

1.  1.  3.  []{#_Toc289334310} **Speciální znaky v GUI**

Nutnou podmínkou pro správné zobrazení znaků je míti k dispozici fonty
s akcentovanými a dalšími specifickými znaky určitého jazyka, které jsou
již obsažené v běžné instalaci Windows nebo Linux. Tyto fonty se
nazývají fyzické, protože se skutečně v počítači vyskytují. Pokud je v
aplikaci použijeme, dostáváme se do problémů s přenositelností programů
na jinou platformu, protože tam tyto fonty nemusejí být nainstalovány.
MS Windows a Unix se ve jménech fyzických fontů velmi liší.

Z tohoto důvodu používá Java od verze JDK 1.1 systém tzv. symbolických
jmen (též logické fonty), kdy jsou namísto jmen fyzických fontů, jako
jsou např. Arial nebo Helvetica, používána symbolická jména. Tento
postup pak pomáhá k tomu, že je program nezávislý na platformě.

Konečné přiřazení symbolického jména konkrétnímu fyzickému fontu je pak
provedeno pomocí jejich mapování, které je uvedené v souboru
fontconfig.properties.src.

V jazyku Java je možné použít pět symbolických jmen rodin fontů. Ty jsou
v následující tabulce uvedeny v prvním sloupci. V druhém a třetím
sloupci uvádím názvy nejčastěji použitých rodin fyzických fontů.

+-----------------------+-----------------------+-----------------------+
| **Java**              | **Linux**             | **MS Windows**        |
+-----------------------+-----------------------+-----------------------+
| Serif                 | Times Roman           | Timew New Roman       |
+-----------------------+-----------------------+-----------------------+
| SansSerif             | Helvetica             | Arial                 |
+-----------------------+-----------------------+-----------------------+
| MonoSpaced            | Courier               | Courier New           |
+-----------------------+-----------------------+-----------------------+
| Dialog                | Helvetica             | Arial                 |
+-----------------------+-----------------------+-----------------------+
| Dialoginput           | Courier               | Courier New           |
+-----------------------+-----------------------+-----------------------+

[]{#_Toc289334384} Tabulka [5]{style="background: #c0c0c0"} - Rodiny
fyzických fontů

U všech uvedených rodin symbolických fontů můžeme použít libovolný ze
všech čtyř možných řezů, tj. plain, italic, bold a bolditalic.

Symbolická jména se pak ve zdrojovém kódu uvádí všude tam, kde by se
uváděla fyzická jména. Ukázka:

Font f = new Font(„SansSerif",Font.Italic,10)

\

5.  []{#_Toc289334311}[]{#_Ref288398382} **Aplikace MPA**

V současné době dle stojí všechny nemocnice před úkolem poskytovat
vysoce kvalitní lékařskou péči ve stále větším objemu a přitom efektivně
využívat dostupné finanční, lidské a také přístrojové zdroje. Nedílnou
součástí je i kvalitní softwarové zpracování veškerých informací o
pacientovi.

Nemocniční informační systémy pokrývají veškeré zpracování informací v
rámci nemocnic různého typu, ať již menších městských, či velkých
fakultních.

![Shape5](DP_Hobel_2011_html_88ea876c.gif){#Shape5 align="left"
hspace="12" width="590" height="309"}\
\

\
\

\
\

\

\

\

\

\
\

Dřívější vedení papírové dokumentace neumožňovalo shromáždit všechna
data týkající se pacienta do jednotného systému. Údaje o ambulantním
ošetření byly v kartotéce ambulance, údaje o hospitalizaci byly v
archivu lůžkového oddělení apod. V případě potřeby bylo obtížné
soustředit všechny informace o pacientovi.

Systém **MPA (Medical Process Assistant)** **[je dle
]{style="font-weight: normal"}[[(10)]{style="background: #c0c0c0"}]{style="font-weight: normal"}[
moderní klinický (nemocniční) informační systém,
který]{style="font-weight: normal"}[
]{style="font-weight: normal"}**řeší veškeré léčebné procesy v různých
typech nemocnic. Všechny subsystémy jsou vzájemně provázány, což
umožňuje absolutní a plně funkční komunikaci mezi jednotlivými
pracovišti.

Jedná se tedy o softwarový produkt, který je vyvíjen v programovacích
jazyku Java již od roku 1998. Původním tvůrcem je rakouská firma
Systema, která jej zprvu dodávala pouze do rakouských nemocnic. Postupem
času se ale program rozšířil i do ostatních
zemí[^13^](#sdfootnote13sym){#sdfootnote13anc .sdfootnoteanc} a nastal
požadavek aplikaci internacionalizovat. Nejen v České republice poté
vzniklo několik poboček, které se v současné době podílejí na vývoji
této rozsáhlé aplikace.

V rámci MPA je třeba rozlišovat rakouskou verzi němčiny (**de_AT**
Locale[^14^](#sdfootnote14sym){#sdfootnote14anc .sdfootnoteanc}) a
klasickou němčinu (**de_DE** Locale). Jako výchozí jazyk byla zvoleno
rakouská verze, neboť aplikace MPA pochází původně z Rakouska. Výchozí
jazyk aplikace se pak používá zároveň i jako výchozí jazyk (zdrojový),
ze kterého se provádí překlady do ostatních jazyků. Namísto pojmu
rakouská verze němčiny se bude dále v textu jednoduše používat pojem
němčina.

1.  1.  []{#_Toc289334312} **Úložiště lokálně závislých textů**

V případě, že by byla kromě němčiny podporována také angličtina, byl by
rozsah uživatelů, kteří budou schopni s aplikací pracovat mnohem větší.
Pořád je ale rozsah uživatelů omezen použitým jazykem. Je tedy dobré se
tohoto omezení zbavit, tzn. oddělit všechny lokálně závislé texty od
zdrojových kódů a uložit je do tzv.
RessourceBundle[^15^](#sdfootnote15sym){#sdfootnote15anc
.sdfootnoteanc}. V MPA se používají dva základní typy.

1.  1.  1.  []{#_Toc289334313} **Konfigurační soubory**

Jedná se o uložení textů v MessageBundle.properties souborech. Zde jsou
uloženy nejrůznější uživatelské výpisy a hlášky dialogových oken.
Zároveň je zde vhodné ukládat takové texty, které jsou zobrazeny v
několika komponentách stejného typu. Například texty jako „OK" nebo
„Cancel" které jsou velmi často použity na tlačítkách (instancích třídy
JButton) nejrůznějších dialogů.

Zvláštním typem konfiguračních souborů jsou ExceptionBundle. Jedná se
také o „property" soubory, které ale obsahují lokálně závislé chybové
hlášky, které mohou nastat kdykoliv během práce s aplikací. Běhový
systém jazyka Java je pak automaticky zobrazí na obrazovku.

Každá chybová hláška by měla obsahovat jednoduché vysvětlení a řešení
vzniklého problému. Aby je uživatel pochopil (věděl jak chybu odstranit
a co udělat, aby se chyba neopakovala), je tyto texty nutné přeložit do
jazyka daného uživatele. Konkrétním příkladem může být například operace
dělení nulou nebo obecně, pokud je parametru metody předán chybný
argument.

1.  2.  []{#_Toc289334314} **Databázové objekty**

Druhým způsobem jsou RepoResourceBundle, které jsou uloženy v objektové
databázi[^16^](#sdfootnote16sym){#sdfootnote16anc .sdfootnoteanc}. Zde
se ukládají se ty překlady, které se nějakým způsobem vážou k hodnotám
atributů daného objektu. Dále je zde vhodné ukládat texty, které se
zobrazují v různých komponentách na stejném místě v **různých**
obměnách. Například pokud instance JPanel, JFrame a dalších komponent
obsahují různý titulek.

Naopak v případě, že několik různých instancí obsahuje **stejný** text,
pak je vhodné tyto texty uvést na jednom místě v jednom „property"
souboru a zbytečně tak nezatěžovat operační paměť (použitím stejného
textu v několika objektech).

Dále se RepoResourceBundle dají s výhodou použít pokud je třeba přenést
část MPA (určité objekty) z jednoho prostředí (určité nemocnice) do
druhého nebo pokud je třeba použít určité objekty na jiném místě v rámci
jednoho prostředí. V případě transportu se s objekty totiž zároveň
přesouvají i lokálně závislé texty.

6.  []{#_Toc289334315}[]{#_Ref288398476} **Aplikace MITToolkit**

MIT (MPA Integrated Translation) Toolkit je nástroj, který je vytvořen
pomocí programovacího jazyku Java a v aplikaci MPA napomáhá a usnadňuje
proces internacionalizace i následný proces lokalizace. Nutnou podmínkou
pro spuštění aplikace je, aby na klientském systému bylo nainstalované
běhové prostředí aplikace MPA (tzv. „BaseRuntime environment").

1.  1.  []{#_Toc289334316}
        [![Shape6](DP_Hobel_2011_html_6126178c.gif){#Shape6 align="left"
        hspace="12" width="688" height="355"} ]{.sd-abs-pos
        style="position: absolute; top: 0.38in; left: -0.3in; width: 689px"}**Architektura**

\

\

\

\

\

\

\

\
\

Hlavní částí nástroje je vrstva aplikační logiky (API), která řídí
chování všech operací. Nad touto vrstvou je vytvořen grafický vzhled
(GUI), pomocí kterého uživatel zadává příkazy, které má aplikační logika
vykonat . Například export textů z RepoResourceBundle objektů, které se
nacházejí v objektové databázi MPA do databáze pro MITToolkit.

Z hlediska programátorského bylo při vytváření aplikaci snahou dodržovat
následující principy:

-   Rozdělení datového, grafického a řídícího modelu pomocí návrhového
    vzoru MVC.

-   Vícevláknové programování, kde operace s GUI komponentami musejí být
    spuštěny až poté co jiné vlákno (operace v aplikačně-logické vrstvě)
    dodá data.

-   Vhodné ošetření výjimek, schopnost programu se zotavit z chybového
    stavu (kontrolované vyjímky), případně dostatečně uživatele
    informovat o vzniklé chybě v případě, že není možné se z chyby
    zotavit (obvykle hardwarové a systémové chyby). V neposlední řadě
    předcházení a minimalizace programátorských chyb zapříčiněných
    nesprávným použitím API nebo logickými chybami.

-   Pokrytí kódu testy.

-   Vyvarování se duplicitám v kódu, znovupoužitelnost některých tříd.

-   Čitelnost kódu, používání smysluplných názvů tříd a proměnných a
    jeho udržitelnost i v dalších letech.

1.  2.  []{#_Toc289334317} **Role v procesu internacionalizace a
        lokalizace**

        1.  []{#_Toc289334318} **Programátor**

Tvůrce návrhu projektu a konkrétní implementace programu (aplikační i
grafické části).

1.  1.  2.  []{#_Toc289334319} **Interní překladatel**

Nejčastěji se jedná o jazykově znalého programátora, který se mimo jiné
dobře orientuje v celé struktuře aplikace MPA. Asi nejvíce je tato role
zapotřebí při překladu tzv. hlavních
frází[^17^](#sdfootnote17sym){#sdfootnote17anc .sdfootnoteanc} nebo při
provádění jednorázových
překladů[^18^](#sdfootnote18sym){#sdfootnote18anc .sdfootnoteanc}.

1.  1.  3.  []{#_Toc289334320} **Externí překladatel**

Jedná se o překladatele profesionála, který provádí drtivou část všech
překladů.

1.  1.  4.  []{#_Toc289334321} **Uživatel**

Osoba, která rozumí problematice softwarové internacionalizace a dokáže
používat nástroje, které aplikace MITToolkit obsahuje.

1.  3.  []{#_Toc289334322} **Princip ovládání aplikace MITTookit**

Nutnou podmínkou pro práci s aplikací je existence databáze (Hypersonic
databáze pro MITTookit), do které bude možné uložit požadované texty z
MPA. V rámci aplikace je možné vytvořit několik databází, se kterými je
možné pracovat odděleně. Více se o této problematice zmiňuji v
následující kapitole [6.4]{style="background: #c0c0c0"}.

**Posloupnost jednotlivých operací**

1.  Naplnění databáze -- export textů ze zvolených MessageBundle souborů
    nebo RepoResourceBundle objektů. Tuto operaci provádí nástroj
    „Export" (kapitola [6.5]{style="background: #c0c0c0"}).

2.  []{#_Ref288295430} Editace textů uložených v databázi -- Pomocí
    nástroje „Edit Phrases" (kapitola
    [6.6]{style="background: #c0c0c0"}) je možné provádět jednotlivé
    úpravy požadovaných překladů.

3.  Export textů z databáze do Excelu (kapitola
    [6.7]{style="background: #c0c0c0"}) -- V další části nástroje „Edit
    Phrases" je možné vybrat z databáze konkrétní fráze, které se
    poskytnou překladateli ve formě Excel souboru.

4.  Import přeložených frází zpět do databáze (kapitola
    [6.8]{style="background: #c0c0c0"}) -- Pomocí nástroje „Import
    Phrases" je možné aktualizovat v databázi ty fráze, které nám
    překladatel přeložil.

5.  Import textů zpět do MPA -- import (přeložených) textů z databáze
    do zvolených MessageBundle souborů nebo RepoResourceBundle objektů.
    Tuto operaci provádí nástroj „Import" (kapitola
    [6.9]{style="background: #c0c0c0"}).

```{=html}
<!-- -->
```
1.  4.  []{#_Toc289334323}[]{#_Ref288295224}[]{#_Ref288295100}
        **Administrace jednotlivých lokalizačních projektů**

Celkově je aplikace MPA značně rozsáhlá, cca 30 tisíc textů. Většinou
ale není třeba pracovat se všemi texty najednou, protože by byla práce
pomalá a nepřehledná. Dále je většinou třeba přeložit pouze určité části
aplikaci (např. pouze laboratoře), a tak by překlad textů pro lůžkové
oddělení nebyl vůbec zapotřebí. Z tohto důvodu je zapotřebí práci
rozdělit na určité části - tzv. projekty. Každý projekt obsahuje vlastní
databázi, a je tak možné pracovat odděleně s různými částmi MPA. Pomocí
hlavního menu „Project" je možné vytvořit, otevřít, uložit nebo smazat
určitý projekt.

**Základní informace** o aktuálním zvoleném projektu jsou uvedeny
v hlavičce aplikace. Je zde vidět jméno projektu (Application Name),
jeho popis (Description), číslo verze (Version) a zvolený výchozí jazyk
(Development Language), který má sloužit jako podklad pro překlady do
jiných jazyků.

![](DP_Hobel_2011_html_7c036bfd.png){#Picture 7 align="bottom"
width="586" height="377" border="0"}

[]{#_Toc289334371} Obrázek [6]{style="background: #c0c0c0"} - Záhlaví
aplikace MITToolkit

Speciální částí hlavičky jsou zaškrtávací tlačítka Available Languages,
které umožňují zvolit právě ty jazyky, se kterými je třeba v aplikaci
pracovat. Jinými slovi je takto možné vyloučit práci s těmi jazyky,
které jsou v daném projektu zbytečné. V projektu MPA z obrázku 6 jsou
podporovány všechny jazyky.

Do hlavičky projektu byly zakomponovány i přesto, že nejsou přímo
závislé na zvoleném projektu. Jejich pomocí je totiž možné ovlivnit
mnoho dalších nástrojů, kterých aplikace MITToolkit využívá.

**Detailnější informace o projektu** jsou uvedeny na záložce „Project
Info", ve které jsou kromě informací z hlavičky dále uvedeny určité
statistiky o projektu. Například kolik je v projektu uloženo frází,
datum založení projektu nebo datum poslední změny v databázi. Konkrétně
z obrázku je patrné, že například celkový počet frází v databázi
projektu MPA je 1837 a do srbštiny je jich zatím přeloženo 1001.

Aby uživatel nebyl nucen při každém spuštění aplikace MITToolkit vybírat
určitý projekt, je vždy před ukončením aplikace uloženo jméno projektu
do zvláštního souboru. Při dalším spuštění se tak automaticky načte
poslední projekt. Stejným způsobem jsou při ukončení práce s aplikací
uloženy i další prvky jako například vybrané podporované jazyky nebo
importovací a exportovací parametry. Výhodou tohoto mechanismu je tedy
to, že jsou v uloženém souboru uchovány informace z poslední spuštěné
instance aplikace MITToolkit. Uživatel tak není nucen při každém
spuštění opakovaně nastavovat jednotlivé parametry.

1.  5.  []{#_Toc289334324}[]{#_Ref288295486} **[Export textů z MPA do
        databáze ]{lang="en-US"}dle zadaných parametrů**

Tento nástroj umožňuje vložit z MPA do databáze projektu konkrétní data,
přesněji řečeno lokálně závislé texty jako jsou například popisky
tlačítek, titulky dialogových oken nebo varovné zprávy. Většinou ale
není potřeba pracovat se všemi texty najednou, ale jen s určitou částí,
proto je možné výběr textů omezit pomocí tzv. exportovacích parametrů.
Například vybrat pouze anglické texty (kromě americké angličtiny), které
se nacházejí v odděleních určené pro laboratoře. Ukázka:

1.  1.  1.  []{#_Toc289334325} **RepoResourceBundles export**

Pokud je zapotřebí nahrát do databáze texty, které jsou uloženy
v objektové databázi, je třeba zvolit první možnost Repository. Poté se
automaticky aktivují příslušné parametry RepoDirectory a RepoOwner s
jejichž pomocí je možné vymezit konkrétní oblast, ze které bude možné
texty do databáze nahrát. Specifikace konrétních jazykových verzí se
provede pomocí parametru
Locales[^19^](#sdfootnote19sym){#sdfootnote19anc .sdfootnoteanc}.
V příloze [C]{style="background: #c0c0c0"} je uveden obsah konkrétního
RepoResourceBundle objektu na základě zvolených parametrů RepoDir a
RepoOwner.

![](DP_Hobel_2011_html_bec3a7d2.gif){#Picture 10 align="bottom"
width="565" height="531" border="0"}

[]{#_Toc289334372} Obrázek [7]{style="background: #c0c0c0"} - Parametry
exportu z MPA do databáze

1.  1.  2.  []{#_Toc289334326} **MessageBundles export**

Dále pomocí tlačítka MessageBundles je do databáze možné nahrát obsah
„property" souborů. V tomto případě je nutné uvést pouze jeden parametr
Root Directory s jehož pomocí se definuje na souborovém systému oblast,
ze které budou texty vybírány. Druhý parametr Export keys if no value
určuje, zda se mají do databáze vyexportovat namísto německých frází
jejich příslušné klíče, v případě že německá fráze zatím neexistuje. I
zde se specifikace konkrétních jazykových verzí provede pomocí parametru
Locales. V příloze [A]{style="background: #c0c0c0"} je uveden obsah
konkrétního MessageBundle souboru včetně zvýraznění frází, které
ovlivňuje parametr Export keys if no value.

1.  1.  3.  []{#_Toc289334327} **Export kontextuálních informací**

Pomocí tlačítka Do context info je možné k vyexportované frázi připojit
kontextuální informaci (cestu), ze které části MPA daná fráze pochází.
Takovouto  informaci pak využije hlavně interní překladatel (jazykově
znalý programátor) v případě, že je zapotřebí provést překlad té fráze,
která se nachází na několika místech v odlišných částech MPA (např.
fráze jako Aufenthalt, Patient nebo Anforderung).

Ukázka kontextuální informace pro frázi
Anforderungsdatum[^20^](#sdfootnote20sym){#sdfootnote20anc
.sdfootnoteanc}:

RepoDirectory: views.readonly.records.I18N

RepoOwner: syex (Systema/Explizit)

RepoObject(RepoResourceBundle): LaborAnforderung.mon

RB-key: label_anfoZeitpunkt.textProperty

V závislosti na tom může být překlad výše uvedené fráze v různých
částech MPA jiný. Anglický překlad tak může být například Order date
nebo také Request date. Pokud interní překladatel kontextuální informaci
zná, může provést správný překlad i těchto obecných frází.

1.  6.  []{#_Toc289334328}[]{#_Ref288295464} **Editace textů uložených v
        databázi**

Poté co se do databáze aktuálního projektu vyexportují požadované texty
je zapotřebí tyto texty z databáze načíst, přehledně zobrazit a umožnit
jejich editaci v tabulce na záložce Edit Phrases. Každý řádek tabulky
představuje jednu konkrétní německou frázi včetně příslušných překladů,
komentářů a dalších doplňujících informací.

![](DP_Hobel_2011_html_19af0854.gif){#Picture 37 align="bottom"
width="586" height="422" border="0"}

[]{#_Toc289334373} Obrázek [8]{style="background: #c0c0c0"} - Záložka
editace frází

1.  1.  1.  []{#_Toc289334329} **Německé fráze**

Jsou uvedeny ve sloupci none, ve kterém je zakázáno měnit obsah. Slouží
jednak jako zdrojový jazyk, ze kterého se provádí překlad do jiných
jazyků a dále se pomocí nich provádí zpětný import do MPA. Pokud by se
tedy fráze změnila, pak by nebylo možné naimportovat daný překlad zpět
na původní místo.

1.  1.  2.  []{#_Toc289334330} **Editace Překladů**

V současné době aplikace MITToolkit podporuje osm lokalit, do kterých je
třeba provádět překlady. Každý je v tabulce reprezentován vlastním
sloupcem (například angličtina prostřednictvím sloupce en). Ke každému
zvolenému sloupci s překlady se navíc do tabulky automaticky přidává i
příslušný sloupec pro komentáře k překladům (například pro angličtinu je
to sloupec en comment).

V případě zvolení všech osmi lokalit je pro provádění překladů v tabulce
zapotřebí zobrazit 16 sloupců, což činí tabulku velmi nepřehlednou a tím
také snižuje efektivitu práce. Většinou ovšem není třeba pracovat se
všemi jazykovými překlady naráz. Díky tlačítku Customize Table
Content\... má uživatel možnost zvolit právě ty jazykové překlady se
kterými chce v aktuálním projektu pracovat a vyřešit tak problém
nepřehledné tabulky.

1.  1.  3.  []{#_Toc289334331}[]{#_Ref288912953}[]{#_Ref288912952}[]{#_Ref288912939}[]{#_Ref288912913}
            **Filtrování frází**

Databáze projektu může často obsahovat velký počet frází (cca. několik
tisíc). Bylo by opět velmi neefektivní pracovat se všemi najednou
v případech, kdy uživatele zajímají například pouze fráze, které zatím
nemají příslušný jazykový překlad. Užitečnou pomůckou je proto možnost
zobrazení pouze těch frází, které odpovídají zvolenému filtru z
rozbalovacího menu.

Podporovány jsou následující filtry:

-   All Translations (No Filter) -- výchozí mód po spuštění aplikace,
    který zobrazí všechny fráze. Nejedná se tedy o filtr v pravém slova
    smyslu.

-   Not Translated Phrases -- filtr, který zobrazí pouze ty fráze, které
    zatím nemají žádný překlad (tzv. nepřeložené fráze).

-   Longer Phrases Then German -- jedná se o filtr, který zobrazí ty
    fráze, které mají příliš dlouhý
    překlad[^21^](#sdfootnote21sym){#sdfootnote21anc .sdfootnoteanc}
    (tzv. problematické fráze), který by v místě svého použití (např.
    popisky tlačítek) nemusel být kvůli své délce vůbec čitelný.
    V tabulce jsou zvýrazněny odstínem červené barvy (čím delší překlad
    tím tmavší odstín).

-   One/Two/Three letters -- jedná se o filtry, které umožňují
    v libovolně zvoleném jazyku zobrazit pouze jedno/dvou/tří písmenné
    texty, které představují pouze mnemotechnické znaky (tzv.
    „mnemonics") [^22^](#sdfootnote22sym){#sdfootnote22anc
    .sdfootnoteanc}.

-   To Translation / Postponed Status -- položky, které umožňují vybrat
    pouze ty fráze, které je možné předat překladateli (je povolen
    jejich překlad) nebo naopak zobrazit ty, kterým v současné chvíli
    není povolen překlád do jiných jazyků (jsou pozastaveny).

-   Dictionary Phrases -- použitím tohoto filtru budou vybrány fráze,
    které jsou určeny jako hlavní, tzv. „slovníkové fráze". Více o této
    problematice kapitola [7.4]{style="background: #c0c0c0"}

Dále je možné ke zvolenému filtru zároveň využít možnost vyhledávání
pomocí klíčového slova a abecední třídění (vzestupné/sestupné) položek
aktuálního sloupce tabulky. Tento postup je naznačen v příloze
[F]{style="background: #c0c0c0"}. Příslušná grafická znázornění výše
uvedených filtrů jsou pak uvedeny v příloze
[E]{style="background: #c0c0c0"}.

1.  1.  4.  []{#_Toc289334332} **Poznámky k frázím pro překladatele**

Do sloupce Extraction comment je možné vložit doplňující informaci,
která bude sloužit překladateli, aby lépe pochopil smysl celé fráze.
Například je vhodné frázi vždy doplnit o hodnoty proměnných v případě,
že nějaké obsahuje. Komentář je dále vhodné uvést v případech, kdy je
možné určitou frázi přeložit vícero způsoby. Tzn. vhodně překladateli
popsat v jakém smyslu (kontextu) má frázi chápat.

1.  7.  []{#_Toc289334333}[]{#_Ref288295387} **Export z databáze do
        Excel souboru pro překladatele**

Pomocí tlačítka Do Export to Excel ze záložky Edit Phrases je možné
vytvořit seznam frází, které je třeba přeložit do zvoleného jazyka. Tyto
fráze se pak poskytnou překladateli ve formě Excel souboru.

1.  1.  1.  []{#_Toc289334334} **Fráze určené pro export**

Zda daná fráze bude při exportu zahrnuta do Excel souboru ovlivňuje
sloupec Status, který může nabývat následujících hodnot:

-   To Translation -- výchozí stav, který určuje, že daná fráze má být
    přeložena a bude tak do exportu zahrnuta.

-   Not To Translate -- daná fráze není v tomto okamžiku (krátkodobě)
    určena pro export.

-   Postponed -- daná fráze byla dlouhodobě odložena a nebude se tak
    zahrnovat do exportu.

Pokud je třeba vyexportovat z databáze určitou část (např. pouze
nepřeložené fráze) má zde uživatel možnost nepotřebné fráze odfiltrovat
a svůj výběr potvrdit zaškrtnutím tlačítka „Filter Phrases Only", které
je součástí tzv. „exportovacích parametrů pro Excel". V případě, že toto
tlačítko není zaškrtlé, pak se budou exportovat všechny fráze, které
spadají do stavu To Translation nezávisle na použitém filtru.

![](DP_Hobel_2011_html_3d681f72.gif){#Picture 15 align="bottom"
width="409" height="561" border="0"}

[]{#_Toc289334374} Obrázek [9]{style="background: #c0c0c0"} - Výběr
parametrů pro export

1.  1.  2.  []{#_Toc289334335} **Exportovací parametry pro excel**

Po spuštění exportu je zobrazeno dialogové okno, ve kterém je třeba
jednotlivě specifikovat následující parametry:

-   Locales for Export - volba jazyků do kterých je třeba přeložit
    německé fráze.

-   Supporting Language -- bude sloužit překladateli jako druhý zdrojový
    jazyk (tzv. podpůrný), ze kterého se budou provádět překlady.
    Vhodnou volbou je například angličtina, která v MPA pokrývá velké
    procento přeložených textů.

-   Select Excel file -- cílový adresář, do kterého se uloží výsledný
    Excel soubor. Zároveň je zde možné modifikovat výchozí jméno
    souboru, které se skládá ze jmen projektu a zvolených jazyků pro
    export.

-   Fitler Phrases Only -- jeho zaškrtnutím se aktivuje možnost exportu
    frází, které jsou zobrazeny podle aktuálně zvoleného filtru.

-   Add context Info -- umožňuje připojit kontextuální informaci
    (cestu), odkud daná fráze pochází.

1.  1.  3.  []{#_Toc289334336}[]{#_Ref288914358}[]{#_Ref288914350}
            **Výsledný Excel soubor a jeho výhody**

Výstupem exportu z databáze je samostatný „excelový" soubor, přesněji
řečeno textový soubor, ve kterém jsou texty od sebe odděleny tabelátory.
Tento soubor pak jde bez problémů zobrazit v libovolném tabulkovém
kalkulátoru[^23^](#sdfootnote23sym){#sdfootnote23anc .sdfootnoteanc}.
Každý řádek editoru pak představuje jednu frázi s příslušnými
(provedenými/neprovedenými) překlady (podobně jako v tabulce Edit
Phrases).

Struktura sloupečků je ve výsledném souboru následující:

-   výchozí německá fráze,

-   jeden nebo více zvolených jazyků pro překlad,

-   volitelně jeden podpůrný jazyk pro překlad a kontextuální informace,

-   komentáře k překladům dle zvolených jazyků,

-   komentář k německé frázi, tzv. „Extraction Comment",

-   kontextuální informace, odkud fráze pochází.

Hlavní výhodou použití Excel souboru je pro překladatele to, že jsou
všechny informace potřebné k překladu uvedeny společně v jednom souboru,
ve kterém se překladatel zároveň dokáže bez problémů orientovat. Může
tak provádět překlady z pohodlí domova, bez nutnosti instalace editoru
pro soubory s uloženými lokálně závislými
texty[^24^](#sdfootnote24sym){#sdfootnote24anc .sdfootnoteanc}. Z tohoto
pohledu by tak byl stížený již samotný transport textů směrem k
překladateli a poté zpět do firmy.

Konkrétní obsah výsledného Excel souboru s nastavenými parametry (dle
obrázku č. 9) je možné shlédnout v příloze
[0]{style="background: #c0c0c0"}.

1.  8.  []{#_Toc289334337}[]{#_Ref288295521} **Import do databáze ze
        souboru přeloženého překladatelem**

Poté, co je proveden překlad vyexportovaných frází je třeba tyto nové
texty nahrát zpět do MPA. Import do konkrétních RepoResourceBundle
objektů nebo MessageBundle souborů neprobíhá napřímo, ale texty je třeba
nejprve nahrát do databáze (aktualizovat) zvoleného projektu a až poté
je možné provedené změny promítnout do MPA.

1.  1.  1.  []{#_Toc289334338} **Importovací parametry**

Nejprve je tedy nutné obsah Excel souboru načíst do tabulky, což se
provede kliknutím na tlačítko Read Import File. Následně nato je
zobrazeno dialogové okno, ve kterém musí uživatel uvést následující
parametry:

Select Excel File -- jméno souboru s přeloženými frázemi, který je třeba
naimportovat do databáze projektu. Pokud uživatel při exportu ponechal
výchozí název, pak by měl obsahovat jméno aktuálně zvoleného projektu.

Select Locale for Import -- výběr jednoho jazyku, který se načte
do tabulky. V případě, že je zapotřebí nahrát všechny přeložené jazyky
z daného souboru, pak je třeba spustit proces čtení jednotlivě pro každý
zvolený jazyk.

![](DP_Hobel_2011_html_87f8e4f6.png){#Picture 18 align="bottom"
width="550" height="300" border="0"}

[]{#_Toc289334375} Obrázek [10]{style="background: #c0c0c0"} - Výběr
parametrů pro import

\
\

![](DP_Hobel_2011_html_cb1810c3.gif){#Picture 38 align="bottom"
width="586" height="419" border="0"}

[]{#_Toc289334376} Obrázek [11]{style="background: #c0c0c0"} - Načtené
překlady z Excel souboru

Mezikrok načtení překladů do tabulky slouží k tomu, aby uživatel mohl
zkontrolovat, případně poopravit nevyhovující překlady. Může tak učinit
například na základě porovnání nového a původního překladu (sloupec
Original Translation). Ve stejném smyslu je zde možné poupravit i
komentářové překlady. Originální hodnoty mohou být zobrazeny pomocí
kontextové nabídky. Je to z toho důvodu, aby tabulka nebyla příliš
rozsáhlá a nepřehledná.

Po provedené kontrole je možné zvolené překlady a jejich komentáře
naimportovat do databáze zvoleného projektu.

1.  1.  2.  []{#_Toc289334339} **Fráze určené pro import**

Pomocí sloupečku Select, se uživatel aplikace může při kontrole překladů
rozhodnout, že daný překlad během importu do databáze nezahrne. Ať již
z důvodu nevhodnosti provedeného překladu nebo z toho důvodu, že frázi
není třeba aktuálně překládat.

Často je ovšem zapotřebí vybrat určité typy překladů. Pokud by Excel
soubor obsahoval několik tisíc přeložených frází, pak by ruční
označování nebylo příliš efektivní. Z tohoto důvodu je možné v tabulce
rozlišit (filtrovat) tři typy překladů.

Filtrování tabulky je zde umožněno pomocí přepínacích tlačítek:

-   New Translations -- nově přeložené fráze od překladatele, které
    v databázi zatím žádný překlad neobsahují.

-   Changed Translations -- změněné překlady frází od překladatele,
    které v databázi již nějaký překlad obsahují. Původní překlady
    v databázi budou po provedení importu těmito změněnými překlady
    nahrazeny.

-   All Translations - výchozí mód, který zobrazí všechny překlady,
    které překladatel provedl. Jedná se o sjednocení obou předchozích
    typů.

1.  9.  []{#_Toc289334340}[]{#_Ref288295533}[]{#_Ref288295311}[]{#_Ref288295294}[]{#_Ref288295287}[]{#_Ref288295261}[]{#_Ref288295246}
        **Import všech přeložených frází z databáze do MPA dle zadaných
        parametrů**

Tento nástroj má za úkol zpětné uložení přeložených textů do původního
umístění v MPA. Jako v případě exportu, tak i zde je třeba určit pomocí
parametrů konkrétní místo v MPA, kam se naimportují přeložené texty.

Pomocí tohoto nástroje však není možné změnit výchozí (německé) fráze,
které zde slouží jako tzv. klíče. Pomocí nich je zabezpečeno, že se
změněné překlady nahrají zpět do původního umístění v MPA. Pokud by se
tedy tento klíč změnil, nebylo by možné zjistit, ke které frázi náleží
jaký překlad.

1.  1.  1.  []{#_Toc289334341} **RepoResourceBundles Import**

V případě zaškrtnutého tlačítka Repository se z databáze aktuálního
projektu vyberou ty fráze, které pocházejí z objektové databáze MPA a
vyhovují zvoleným parametrům RepoDirectory, RepoOwner a Locales.
Například volba icz_plzen_ifx v parametru RepoOwner zabezpečí, že bude
možné naimportovat objekty, jež náleží pouze vlastníkům, kteří vyhovují
této podmínce.

1.  1.  2.  []{#_Toc289334342} **MessageBundles Import**

Tlačítko MessageBundles představuje způsob, jak z aktuální projektové
databáze vybrat ty fráze, které pocházejí ze souborového kořenového
adresáře a které zvoleným jazykovým verzím.. Cesta ke kořenovému
adresáři se uvede do parametru RootDir a volba jazyků v parametru
Locales.

Po provedení importu je třeba vytvořit tzv. „changelist", což je souhrn
všech všech změn, které se udály v daném
souboru[^25^](#sdfootnote25sym){#sdfootnote25anc .sdfootnoteanc}.
Výhodou je, že je možné zkontrolovat každou změnu ještě před její
samotnou archivací do verzovacího systému.

![](DP_Hobel_2011_html_a3c68630.gif){#Picture 27 align="bottom"
width="506" height="463" border="0"}

[]{#_Toc289334377} Obrázek [12]{style="background: #c0c0c0"} - Parametry
importu z databáze do MPA

1.  1.  3.  []{#_Toc289334343} **Import existujících překladů**

Parametr Overwrite Existing Translations označuje, zda se má pro každý
provedený překlad zobrazit dialog, který před vlastním přepsáním
rekapituluje provedené změny. Tímto způsobem lze ještě změny
zkontrolovat a popřípadě zamítnout ty nevhodné.

Toto kontrolní okno je možné ovládat pomocí přidruženého parametru
Overwrite Modus. V případě, že je třeba toto kontrolní okno během
importu zobrazovat, pak je nutné nastavit jeho hodnotu na Manual. Pokud
by se nastavila hodnota na Auto, pak by se kontrolní dialog během
importu nezobrazil a všechny původní překlady by se tak automaticky
přepsaly.

![](DP_Hobel_2011_html_d7bb3d7d.png){#Picture 28 align="bottom"
width="584" height="242" border="0"}

[]{#_Toc289334378} Obrázek [13]{style="background: #c0c0c0"} - Potvrzení
pro přepis existujícího překladu novým

7.  []{#_Toc289334344}[]{#_Ref289023756} **Doplňkové nástroje Aplikace
    MITToolkit**

-   Editor MessageBundle souborů

-   Editor RepoResourceBundle souborů

-   Export/Import datumových formátů

-   Slovník hlavních frází

1.  1.  []{#_Toc289334345}[]{#_Ref288756744}[]{#_Ref288756699} **Editor
        pro MessageBundle soubory**

Jedná se o nástroj který bude prakticky ulehčovat provádění překladů
pouze interním překladatelům (programátorům) na jednorázové překlady
nebo opravy. Z hlediska externích překladatelů je nejlepší volbou
samostatný excelový soubor[^26^](#sdfootnote26sym){#sdfootnote26anc
.sdfootnoteanc}.

Java programy, které podporují internacionalizaci používají nejčastěji
pro uložení lokálně závislých textů konfigurační soubory (viz příloha
[A]{style="background: #c0c0c0"} [Obsah konkrétního MessageBundle
souboru]{style="background: #c0c0c0"}). Editace těchto souborů je
umožněna pomocí nástroje, který byl
převzat[^27^](#sdfootnote27sym){#sdfootnote27anc .sdfootnoteanc} jako
open source a poté do aplikace MITToolkit integrován. Konkrétní ukázka
práce s editorem je naznačena na obrázku v příloze
[B]{style="background: #c0c0c0"}.

V levé části je vidět stromová adresářová s konfiguračními soubory.
V pravé části je pak zobrazen obsah zvoleného souboru, který má vždy
podobu klíč=hodnota. Seznam klíčů je zobrazen v tabulce Schlüssel.
Příslušná hodnota zvoleného klíče je pak zobrazena v textovém poli
Standardtext[^28^](#sdfootnote28sym){#sdfootnote28anc .sdfootnoteanc},
kde je možná její editace. Kromě úprav jednotlivých překladů či
komentářů je také pomocí tohoto nástroje možné zakládat nové fráze (nové
klíče) nebo zcela nové soubory (nové jazykové verze).

1.  1.  1.  []{#_Toc289334346} **Výhody použití editoru oproti
            konfiguračním souborům**

Konfigurační soubory jsou uloženy v kódování ISO 8859-1 (méně formálně
Latin-1), které nepodporuje akcentované aj. specifické znaky daného
jazyka (např.: ü, ß, š atd.). Tyto znaky je možné zapsat pouze ve formě
unicode sekvence (\\uXXXX). Prostřednictvím editoru je však možné výše
zmiňované znaky vkládat přímo, po uložení se pak provede jejich
automatický převod do unicode formy.

Jednotlivé jazykové překlady jsou na souborovém systému uloženy
v samostatných souborech. Bylo by tak potřeba se neustále přepínat mezi
souborem s originálním jazykem a právě překládaným souborem. V případě
použití editoru, je pak možné originální a překládaný jazyk zobrazit v
jednom umístění. Na obrázku je společně s anglickou frází Selected
target bundle ID vidět zároveň i německá Zielbundle ID.

V editoru je navíc díky barevnému odlišení na prvním pohled vidět, které
fráze dosud nemají překlad a které fráze byly nově přidány nebo změněny.
Tímto způsobem je částečně vyřešena otázka filtrování frází.

1.  2.  []{#_Toc289334347} **Editor objektové databáze**

Některé lokálně závislé texty jsou v MPA uloženy v objektové databázi.
Aby bylo možné tyto texty upravovat je opět zapotřebí vytvořit vlastní
editor. Tento nástroj v MPA již existoval, a tak byl do aplikace
MITToolkit pouze zintegrován. Aplikace MITToolkit se ovšem omezuje pouze
na editaci objektů, které obsahují lokálně závislé
texty[^29^](#sdfootnote29sym){#sdfootnote29anc .sdfootnoteanc}. Editor
je dostupný prostřednictvím záložky Repository. V příloze
[C]{style="background: #c0c0c0"} je uvedena ukázka editace konkrétního
objektu pomocí editoru.

Základní struktura je podobná souborovému editoru. Na levé straně je
zobrazena stromová struktura, ve které je možné vybrat příslušný objekt.
Jeho obsah bude ihned zobrazen v pravé části (editoru), která má podobu
tabulky. V prvním sloupci je zobrazen „klíč" k překladům, který není
možné z definice internacionalizace měnit. V jednom zobrazení je vždy
společně s německými texty (sloupec none) viditelný jeden sloupec, do
kterého je třeba provést překlad (např. angličtna - en). V případě, že
je třeba provést překlady do jiného jazyka (např. češtiny), pak je
pomocí tohoto nástroje zapotřebí vytvořit nový objekt s
nastavenou českou lokalitou (cs).

Editor objektů je vytvořen tak, aby se stromová struktura nenačítala
celá naráz, ale postupně až poté co uživatel označí určitou složku. To
znamená, že se vždy načítají pouze ty objekty, které uživatel v danou
chvíli potřebuje a nikoliv všechny najednou, což by velmi zpomalovalo
spouštění obou aplikací.

Hlavní nevýhodou oproti excelovému souboru je nutnost instalace
objektové databáze přímo u překladatele, případně by bylo zapotřebí, aby
překladatel pracoval na překladech přímo ve firmě. Proto editor pro I18N
objekty budou používat nejčastěji interní překladatelé firmy pro
jednorázové úpravy spíše, než pro rozsáhlejší překlady.

1.  3.  []{#_Toc289334348} **Editor grafických komponent**

Veškeré lokálně závislé texty je v aplikaci MPA třeba zobrazit v  nějaké
grafické komponentě. Překlady k originálním textům mohou mít i
několikanásobně větší délku. Z tohoto pohledu je velmi užitečným
nástrojem editor, který dovoluje měnit velikost a umístění grafických
komponent na základě délky přeloženého textu. Tento editor se nachází na
záložce Views Overview a do aplikace MITToolkit byl opět integrován,
přepracováno bylo pouze jeho ovládání.

V příloze [D]{style="background: #c0c0c0"} je ukázka konkrétního
grafického výstupu, v příloze [C]{style="background: #c0c0c0"} pak
příslušný objekt se zdrojovými texty.

1.  4.  []{#_Toc289334349}[]{#_Ref288913938}[]{#_Ref288913865} **Slovník
        hlavních frází**

Prostřednictvím záložky Dictionary je možné samostatně zobrazit ty
fráze, které byly určeny jako tzv. „slovníkové fráze". Většinou se jedná
o jednoslovné fráze, které je možné přeložit vícero způsoby. Například
je třeba určit, zda německé slovo „Bett" přeložit do češtiny jako
„postel" nebo jako „lůžko". Dalším příkladem může být slovo
„Aufenthalt", které se může podle použití přeložit jako pobyt, zastavení
nebo také hospitalizace. Tyto „sporné" fráze musejí být na začátku
přeloženy interním překladatelem, který ví, ve kterých částech aplikace
MPA se daná fráze používá (má pojem o celkovém kontextu). Slovník tedy
slouží k ujasnění pojmů, aby externí překladatel neměl problém
s nejednoznačností překladů.

Dále je zde také možné specifikovat fráze, které se do ostatních jazyků
nepřekládají. Například slova jako „server" nebo „internet". Příklad
konkrétního obsahu slovníku je zobrazen v příloze
[I]{style="background: #c0c0c0"}.

1.  5.  []{#_Toc289334350} **Datumové formáty**

V objektové databázi jsou uloženy veškeré jazykové verze datumových
formátů, které se používají v MPA. Pomocí nástroje DateFormatExport ze
záložky Export je možné tyto formáty vyhledat a uložit do XML souboru.

Aplikace MITToolkit dovoluje tento soubor přehledně zobrazit v tabulce
na záložce DateFormats. Uživatel tak má možnost přehledně a lehce měnit
příslušné datumové formáty[^30^](#sdfootnote30sym){#sdfootnote30anc
.sdfootnoteanc}. Provedené změny je pak možné pomocí nástroje
DateFormatImport ze záložky Import vložit do objektové databáze. Původní
hodnoty v MPA hodnoty jsou pak automaticky přepsány novými.

![](DP_Hobel_2011_html_77596e61.gif){#Picture 31 align="bottom"
width="616" height="258" border="0"}

[]{#_Toc289334379} Obrázek [14]{style="background: #c0c0c0"} - Přehled
podporovaných datumových formátů

8.  []{#_Toc289334351} **Aplikace MITToolkit a její přínos**

Pro potřeby internacionalizace je třeba z kódu oddělit lokálně závislé
texty. V aplikaci MPA je největší část těchto textů uložena v „property"
souborech. Původně bylo možné každou změnu provést pouze přímo v daném
souboru. Výhodou bylo, že k editaci nebylo potřeba žádný další nástroj.
Ovšem jednou z hlavních nevýhod byl fakt, že bylo třeba psát všechny
akcentované aj. specifické znaky daného jazyka (např. ö, ü, ž atd.) v
unicode formě, což bylo velmi nepraktické. Tuto nevýhodu včetně několika
méně podstatných odstraňuje integrovaný MessageBundle editor.

V editoru se pracuje se všemi „property" soubory a vždy s celým obsahem
konkrétního souboru. Tento způsob je sice komplexní, ale z hlediska
provádění překladů není praktický a tak jej bude nejčastěji používat
interní překladatele na jednorázové překlady a úpravy. Většinou je spíše
zapotřebí přeložit pouze určitý sektor MPA (např. laboratoře) a třeba
jen určitý typ textů (např. pouze nepřeložené fráze). Pokud se zároveň
pracuje i s ostatními soubory (nebo texty), pak je práce překladatele
vždy časově náročnější. Aplikace MITToolkit umožňuje výstup
pro překladatele v jednom samostatném souboru, do kterého je možné
nahrát přesně ty fráze, které je třeba v danou chvíli přeložit.

Vyřešena je i problematická otázka transportu textů směrem k
překladateli a transport přeložených textů zpět do firmy, neboť jeden
samostatný soubor není problém kamkoliv přenést. Protože se jedná o
soubor, který je možné otevřít v libovolném tabulkovém kalkulátoru,
nečiní jeho ovládání většině překladatelů žádné problémy.

Využitelnost aplikace MITToolkit jako nástroje pro podporu
internacionalizace a lokalizace i v jiných firmách je možná, avšak by
bylo třeba odstranit veškeré závislosti na MPA. Například volbu
výchozího (klíčového) jazyka nebo uložení některých textů v objektové
databázi pomocí RepoResourceBundle objektů.

\

9.  []{#_Toc289334352} **Závěr**

Celá práce je rozdělena na dvě hlavní části. V první se rozebírá
internacionalizace a lokalizace ryze teoreticky, doplněná o konkrétní
příklady jak lze danou problematiku vyřešit v jazyku Java. Ve druhé,
praktické části je popsáno jak byla vyřešena implementace všech
nejdůležitějších vlastností a nástrojů aplikace MITToolkit včetně
navržení grafického rozhraní. V závislosti na tom byl kladen důraz na
dodržování vhodných programátorské zvyklostí.

Výsledkem práce je tedy grafický počítačový program „MITToolkit", který
podporuje lokalizaci aplikace MPA v tom smyslu, že dokáže efektivně
spravovat velké množství lokálně závislých textů. Zároveň je tyto texty
možné jednoduše předat překladateli a vést s ním o provedených
překladech komunikaci. Program navíc obsahuje ještě několik doprovodných
nástrojů, které dále zjednodušují dané prvky lokalizačního procesu a
zvyšují použitelnost celé aplikace.

Počet souborů (a objektů) s lokálně závislými texty je v aplikaci MPA
již tak rozsáhlý, že téměř není možné udržovat jazykové překlady
v konzistentním stavu. Takto je například téměř nemožné určit, které
německé fráze zatím nemají překlad v jednom z podporovaných jazyků.
Tento a jemu podobné požadavky jsou nyní díky aplikaci MITToolkit
zjištěny téměř okamžitě, což velmi usnadňuje kontrolu a udržovatelnost
těchto souborů (a objektů).

Jelikož je aplikace MITToolkit velmi spjata s aplikací MPA (instalace
běhového prostředí, existence příslušné relační a objektové databáze,
existence souborů s lokálně závislými texty), tak není možné ji
samostatně uložit na CD. Tuto nevýhodu jsem ovšem dostatečně kompenzoval
použitými obrázky v textu a v příloze. Posloupnost grafických komponent
v [6]{style="background: #c0c0c0"}. kapitole představuje ukázku celého
komplexního postupu lokalizace aplikace MPA. Ve stejné podobě by se
s těmito komponentami setkal i uživatel aplikace MITToolkit.

10. []{#_Toc289334353} **Seznam obrázků a tabulek**

::: {#Table of Figures1 dir="ltr"}
[Obrázek 1 - Průběh internacionalizace a lokalizace
10](/C:/Documents%20and%20Settings/jhobel/Plocha/DP_Hobel.docx#_Toc289334366)

[Obrázek 2 - Průběh globalizace
11](/C:/Documents%20and%20Settings/jhobel/Plocha/DP_Hobel.docx#_Toc289334367)

[Obrázek 3 - Hierarchie formátovacích tříd v Javě
22](/C:/Documents%20and%20Settings/jhobel/Plocha/DP_Hobel.docx#_Toc289334368)

[Obrázek 4 - Orientační blokové schéma nemocničního informačního systému
37](/C:/Documents%20and%20Settings/jhobel/Plocha/DP_Hobel.docx#_Toc289334369)

[Obrázek 5 - Model aplikace MITToolkit
40](/C:/Documents%20and%20Settings/jhobel/Plocha/DP_Hobel.docx#_Toc289334370)

[Obrázek 6 - Záhlaví aplikace MITToolkit 43](#_Toc289334371)

[Obrázek 7 - Parametry exportu z MPA do databáze 45](#_Toc289334372)

[Obrázek 8 - Záložka editace frází 47](#_Toc289334373)

[Obrázek 9 - Výběr parametrů pro export 50](#_Toc289334374)

[Obrázek 10 - Výběr parametrů pro import 53](#_Toc289334375)

[Obrázek 11 - Načtené překlady z Excel souboru 53](#_Toc289334376)

[Obrázek 12 - Parametry importu z databáze do MPA 56](#_Toc289334377)

[Obrázek 13 - Potvrzení pro přepis existujícího překladu novým
57](#_Toc289334378)

[Obrázek 14 - Přehled podporovaných datumových formátů
61](#_Toc289334379)
:::

\
\

::: {#Table of Figures2 dir="ltr"}
[Tabulka 1 - Formát čísla pro různé lokality 18](#_Toc289334380)

[Tabulka 2 - České a francouzské předdefinované datumové formáty
23](#_Toc289334381)

[Tabulka 3 - Uživatelsky definované datumové formáty 24](#_Toc289334382)

[Tabulka 4 - Výstupní informace o pravopisné kontrole ze souboru „foo"
28](#_Toc289334383)

[Tabulka 5 - Rodiny fyzických fontů 36](#_Toc289334384)
:::

\
\

11. []{#_Toc289334354}[]{#_Toc213915179} **Seznam literatury**

::: {#Bibliography1 dir="ltr"}
1\. Internacionalizace a lokalizace. *Wikipedie.* \[Online\] 6. březen
2011. \[Citace: 18. březen 2011.\]
<http://en.wikipedia.org/wiki/Internationalization_and_localization>.

2\. **Shirah, Joe Sam.** Java internationalization basics. \[Online\]
23. duben 2002. \[Citace: 28. březen 2010.\]
<http://www.ibm.com/developerworks/java/tutorials/j-i18n/j-i18n-pdf.pdf>.

3\. **Esselink, Bert.** *A Practical Guide to Localization.* USA : John
Benjamins Publishing Company, 2000. str. 488. ISBN 90-2721-956-7.

4\. **Luong, Tuoc V., Lok, James S. H. a Driscoll, Kevin.**
*Internationalization - Developing Software for Global Markets.* USA :
John Wiley & Sons, 1995. str. 293. 978-0471076612.

5\. **Corporation, Microsoft.** *Globalization Step-by-Step.* \[Online\]
Microsoft Corporation, 2010. \[Citace: 28. březen 2010.\]
<http://msdn.microsoft.com/en-us/goglobal/bb688110.aspx>.

6\. **Deitsch, Andrew a Czarnecki, David.** *Java Internationalization.*
USA : O\'Reilly & Associates, Inc., 2001. str. 427. 0-596-00019-7.

7\. **Oracle.** The Java Tutorials. *Using Predefined Formats.*
\[Online\] 2011. \[Citace: 21. březen 2011.\]
<http://java.sun.com/docs/books/tutorial/i18n/format/dateFormat.html>.

8\. Wikipedie. *ASCII.* \[Online\] 2. březen 2011. \[Citace: 20. březen
2011.\] <http://cs.wikipedia.org/wiki/ASCII>.

9\. **Herout, Pavel.** *Java grafické uživatelské prostředí a čeština.*
České Budějovice : Kopp, 2007. str. 316. 978-80-7232-328-9.

10\. Procesní klinický informační systém mpa. \[Online\] ICZ, 2011.
\[Citace: 19. únor 2011.\]
<http://www.i.cz/co-delame/oblasti-reseni/aplikacni-software/zdravotnictvi/zdravotnicka-zarizeni/>.

11\. Unicode - cesta z chaosu kódování znaků. *Přehled kódování
češtiny.* \[Online\] \[Citace: 21. březen 2011.\]
<http://www.cestina.cz/kodovani/unicode.html>.
:::

\
\

12. []{#_Toc289334355} **Resumé**

This thesis describes Java application MITToolkit which supports all
necessary segments of localization proces in the application MPA. The
thesis consists of two main parts.

The first part (chapters [3]{style="background: #c0c0c0"},
[4]{style="background: #c0c0c0"}, [5]{style="background: #c0c0c0"})
contains teoretical information about how to develop the java
internationalization software. In the second, practical part (chapter
[6]{style="background: #c0c0c0"}) describes all tools that are
implemented in the MITToolkit application. There are also several
additional tools, which make the localization process easier and improve
usability of the application.

The main contribution of this application is that it effectively allows
to control large amounts of local-sensitive texts. For translator these
texts can be provided in a simple way (by Excel Sheet).

\
\

13. []{#_Toc289334356} **Přílohy**

```{=html}
<!-- -->
```
A.  []{#_Toc289334357}[]{#_Ref289112964}
    [![](DP_Hobel_2011_html_7b95d070.gif){#Image2 width="586"
    height="357" border="0"} ]{.sd-abs-pos
    style="position: absolute; top: 1.19in; left: 0.06in; width: 586px"}**Obsah
    konkrétního MessageBundle souboru**

\
\

\
\

B.  []{#_Toc289334358}[]{#_Ref289155797} **Úprava německý textů pomocí
    MessageBundle editoru**

![](DP_Hobel_2011_html_a2be3301.gif){#Picture 19 align="bottom"
width="433" height="863" border="0"}

C.  []{#_Ref289156205}[]{#_Toc289334359}[]{#_Ref289116343} **Obsah
    konkrétního ResourceBundle objektu**

\

![](DP_Hobel_2011_html_30546353.gif){#Picture 43 align="bottom"
width="581" height="821" border="0"}

\

D.  []{#_Toc289334360}[]{#_Ref289161913} **Úprava anglických textů
    v příslušné grafické komponentě**

![](DP_Hobel_2011_html_a1980204.gif){#Picture 30 align="bottom"
width="423" height="841" border="0"}

\

E.  []{#_Toc289334361}[]{#_Ref289169543} **Možnosti filtrování frází z
    databáze**

![](DP_Hobel_2011_html_ef19bdf6.gif){#Picture 56 align="bottom"
width="467" height="265" border="0"}

\

![](DP_Hobel_2011_html_723c5655.gif){#Picture 57 align="bottom"
width="457" height="265" border="0"}

\

\

![](DP_Hobel_2011_html_7d27c9f1.gif){#Picture 59 align="bottom"
width="456" height="265" border="0"}

F.  []{#_Toc289334362}[]{#_Ref289172074} **Vyhledávání a třídění textů**

![](DP_Hobel_2011_html_a0823487.gif){#Picture 65 align="bottom"
width="586" height="251" border="0"}

\

\

![](DP_Hobel_2011_html_d5caf985.gif){#Picture 66 align="bottom"
width="586" height="228" border="0"}

\

\

[]{#_Ref289150351}\
\

G.  []{#_Toc289334363} **Obsah konkrétního Excel souboru**

[![](DP_Hobel_2011_html_3537bf16.gif){#Picture 17 width="541"
height="881" border="0"} ]{.sd-abs-pos
style="position: absolute; top: 0.46in; left: 0.48in; width: 541px"}\

\
\

H.  []{#_Toc289334364} **Možnosti filtrování frází z Excel souboru**

![](DP_Hobel_2011_html_c176f108.gif){#Picture 16 align="bottom"
width="578" height="207" border="0"}

\

![](DP_Hobel_2011_html_cc95543f.gif){#Image3 align="bottom" width="586"
height="207" border="0"}

\

\

![](DP_Hobel_2011_html_36a81db.gif){#Image4 align="bottom" width="586"
height="233" border="0"}

\

\

\
\

I.  []{#_Toc289334365}[]{#_Ref289157942} **Slovník hlavních frází**

![](DP_Hobel_2011_html_549c2ba6.gif){#Picture 24 align="bottom"
width="586" height="248" border="0"}

![](DP_Hobel_2011_html_dca3c3e2.gif){#Picture 25 align="bottom"
width="586" height="246" border="0"}

![](DP_Hobel_2011_html_760c1f20.gif){#Picture 26 align="bottom"
width="586" height="225" border="0"}

::: {#sdfootnote1}
[1](#sdfootnote1anc){#sdfootnote1sym .sdfootnotesym} V této části jsem
nejvíce informací čerpal z knihy [(6)]{style="background: #c0c0c0"}.
:::

::: {#sdfootnote2}
[2](#sdfootnote2anc){#sdfootnote2sym .sdfootnotesym} Též označována jako
I18N, kde číslo 18 je počet písmen mezi „I" a „N" v anglickém
ekvivalentu tohoto slova. *(W3C, 2006)*

\
:::

::: {#sdfootnote3}
[3](#sdfootnote3anc){#sdfootnote3sym .sdfootnotesym} Též označována jako
L10N, kde číslo 10 je počet písmen mezi „L" a „N" v anglickém
ekvivalentu tohoto slova. *(W3C, 2006)*

\
:::

::: {#sdfootnote4}
[4](#sdfootnote4anc){#sdfootnote4sym .sdfootnotesym} Též označována jako
G11N, kde číslo 11 je počet písmen mezi „G" a „N" v anglickém
ekvivalentu tohoto slova. *(W3C, 2006)*

\
:::

::: {#sdfootnote5}
[5](#sdfootnote5anc){#sdfootnote5sym .sdfootnotesym} Dnes je součástí
firmy IBM.
:::

::: {#sdfootnote6}
[6](#sdfootnote6anc){#sdfootnote6sym .sdfootnotesym} International
Components for Unicode,
[[http://site.icu-project.org](http://site.icu-project.org/)]{.underline}.
:::

::: {#sdfootnote7}
[7](#sdfootnote7anc){#sdfootnote7sym .sdfootnotesym} V jazyku Java se
používá častěji pojem Locale.
:::

::: {#sdfootnote8}
[8](#sdfootnote8anc){#sdfootnote8sym .sdfootnotesym} Čeština je
nastavena jako výchozí jazyk, pokud je použit český operační systém.
:::

::: {#sdfootnote9}
[9](#sdfootnote9anc){#sdfootnote9sym .sdfootnotesym}Soubory s příponou
.properties (tzv. „property" soubory).
:::

::: {#sdfootnote10}
[10](#sdfootnote10anc){#sdfootnote10sym .sdfootnotesym} Pravděpodobně
použitím ISO kódu. V případě amerického dolaru tedy USD.
:::

::: {#sdfootnote11}
[11](#sdfootnote11anc){#sdfootnote11sym .sdfootnotesym} Pro tyto účely
je zapotřebí použít třídu RuleBasedNumberFormat, která je součástí
balíku ICU4J.
:::

::: {#sdfootnote12}
[12](#sdfootnote12anc){#sdfootnote12sym .sdfootnotesym}Ve Windows
použijeme Cp852 a v Unixu ISO8859_2
:::

::: {#sdfootnote13}
[13](#sdfootnote13anc){#sdfootnote13sym .sdfootnotesym} Zde je uveden
konkrétní výčet nemocnic:
[<http://www.systema.info/loesungen/mpa/referenzen>]{.underline}.
:::

::: {#sdfootnote14}
[14](#sdfootnote14anc){#sdfootnote14sym .sdfootnotesym} Uvnitř firmy
Systema se ale častěji používá název none Locale.
:::

::: {#sdfootnote15}
[15](#sdfootnote15anc){#sdfootnote15sym .sdfootnotesym} Více o této
problematice pojednává kapitola [4.2]{style="background: #c0c0c0"}
[Oddělení jazykově závislých dat od zdrojových
kódů]{style="background: #c0c0c0"}
:::

::: {#sdfootnote16}
[16](#sdfootnote16anc){#sdfootnote16sym .sdfootnotesym} Uvnitř firmy
Systema se ale častěji používá název Repository.
:::

::: {#sdfootnote17}
[17](#sdfootnote17anc){#sdfootnote17sym .sdfootnotesym} Kapitola
[7.4]{style="background: #c0c0c0"} [Slovník hlavních
frází]{style="background: #c0c0c0"}.
:::

::: {#sdfootnote18}
[18](#sdfootnote18anc){#sdfootnote18sym .sdfootnotesym} Kapitola
[7.1]{style="background: #c0c0c0"} [Editor pro MessageBundle
soubory]{style="background: #c0c0c0"}.
:::

::: {#sdfootnote19}
[19](#sdfootnote19anc){#sdfootnote19sym .sdfootnotesym} Výchozí jazyk
aplikace (němčina) se exportuje vždy automaticky, neboť slouží jako
zdrojový jazyk, ze kterého se provádí překlad. Také se pomocí něho poté
provádí zpětný import přeložených textů do MPA.
:::

::: {#sdfootnote20}
[20](#sdfootnote20anc){#sdfootnote20sym .sdfootnotesym} Vizuální
reprezentace viz. příloha [C]{style="background: #c0c0c0"}.
:::

::: {#sdfootnote21}
[21](#sdfootnote21anc){#sdfootnote21sym .sdfootnotesym} Konkrétně více
jak 30 %. To je standard o který se doporučuje komponenty zvětšovat, aby
byla při překladu zajištěna jistá rezerva.
:::

::: {#sdfootnote22}
[22](#sdfootnote22anc){#sdfootnote22sym .sdfootnotesym} Například pro
frázi &Abfragen je to znak A, který je uveden před ampersandem.
Stisknutí klávesové zkratky ALT + A pak v konkrétní aplikaci způsobí
automatické vybrání položky [A]{.underline}bfragen.
:::

::: {#sdfootnote23}
[23](#sdfootnote23anc){#sdfootnote23sym .sdfootnotesym} Například
aplikace Calc z balíku Open Office. Překladatel tak není omezen pouze na
použití aplikace MS Excel.
:::

::: {#sdfootnote24}
[24](#sdfootnote24anc){#sdfootnote24sym .sdfootnotesym} Více o této
problematice pojednává kapitola [7.1]{style="background: #c0c0c0"}
[Editor pro MessageBundle soubory]{style="background: #c0c0c0"}.
:::

::: {#sdfootnote25}
[25](#sdfootnote25anc){#sdfootnote25sym .sdfootnotesym} Pomocí
„changelistů" se do MPA obecně zavádí každá změna.
:::

::: {#sdfootnote26}
[26](#sdfootnote26anc){#sdfootnote26sym .sdfootnotesym} O výhodách
excelového souboru více v kapitole [6.7.3]{style="background: #c0c0c0"}
[Výsledný Excel soubor a jeho výhody]{style="background: #c0c0c0"}.
:::

::: {#sdfootnote27}
[27](#sdfootnote27anc){#sdfootnote27sym .sdfootnotesym} Konkrétně byl
převzat ze stránek [<http://attesoro.org/>]{.underline}.
:::

::: {#sdfootnote28}
[28](#sdfootnote28anc){#sdfootnote28sym .sdfootnotesym} V případě
komentářů Standardkomentar.
:::

::: {#sdfootnote29}
[29](#sdfootnote29anc){#sdfootnote29sym .sdfootnotesym} V objektové
databázi jsou uloženy vždy ve složce s příponou I18N (např.:
gf.dict.types.I18N).
:::

::: {#sdfootnote30}
[30](#sdfootnote30anc){#sdfootnote30sym .sdfootnotesym} Kromě německé
veze (de_AT), která slouží jako klíč pro zpětný import datumových
formátů do databáze.
:::
