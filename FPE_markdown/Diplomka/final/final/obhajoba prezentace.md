---
title: "obhajoba prezentace.docx"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/final/final/obhajoba prezentace.docx"
date: 2011-05-25
type: DOCX
---

**Obsah práce -- zásady**[ ]{style="display: none"}

-   **Implementace grafického nástroje pro podporu I18N a L10N**

**AWT/SWING**

Grafická část je navržena v jazyku Java, konkrétně pomocí komponent z
knihovny Swing.

Výhody Swing

-   Všechny komponenty vypadají stejně na všech platformách (každá
    komponenta měla svůj nativní protějšek)

-   Plně využívá objektových vlastností Javy

-   Umožňuje oddělit funkcionalitu od vzhledu (tzv.
    look[&feel]{lang="en-US"} - témat vzhledu je několik k dispozici
    přímo ve standardní knihovně, další si lze vytvořit a použít)

-   Oddělení dat od složitějších grafických objektů (tabulka, strom nebo
    i seznam).

-   Dále v AWT chybí některé důležité komponenty (např. MenuBar, ..).

**Layout manager (rozmisťování komponent)**

-   Umístění jednotlivých komponent v kontejnerové komponentě.

-   Několik managerů -- každý má své specifické vlastnosti

-   Např. FlowLayout -- nová komponenta je přidána na konec všech
    komponent

-   V případě většiho množství komponent -- nevystačíme pouze s jedním,
    pak je třeba kombinace některých

-   Alternativa -- existuje jeden univerzální GridBagLayout -- avšak je
    nejsložitější.

-   Moje praxe -- pokud šlo použít lehčí manager (bez nutnosti
    kombinovat několik), pak byl použit tento. V opačném případě byl
    vždy použit GridBagLayout -- s tím že hodnoty rozmístění vždy
    převezmu z editoru.

**Eclipse / Netbeans**

-   Grafiku jsem nejprve vytvářel ve vývojovém prostředí NetBeans, jež
    obsahuje editor pomocí kterého lze jednotlivé komponenty rozmístit
    bez znalosti Layout Managerů. Takto vytvořená část, lze snadno
    zkopírovat do prostředí eclipse.

-   Postupem času jsem ale od návrhů v NetBeans prostředí odešel, neboť
    je vždy třeba vygenerovaný kód v Eclipse manuálně doupravit, což
    zabere čas navíc. Díky znalosti layout manažerů si nyní navrhnu
    grafickou část na papíře a ihned zimplementuji do Eclipse.

**Ukázka**

![](obhajoba%20prezentace_html_7c036bfd.png){#Picture 7 align="bottom"
width="586" height="377" border="0"}

-   Zmínit aplikaci Layout managerů.

Panely - Hlavička, záložky; hlavní menu a status bar.

Projekt je soubor frází, které byly vyexportované z MPA a se kterými se
má pracovat jako jeden celek. Vyexportované fráze jsou uloženy
v (Hypersonic) databázi, ze které je nutné je vždy při otevření projektu
načíst.

Jednotlivé nástroje jsou popsány v 6. části.

**Základní informace** o aktuálním zvoleném projektu jsou uvedeny
v hlavičce aplikace. Je zde vidět jméno projektu (Application Name),
jeho popis (Description), číslo verze (Version) a zvolený výchozí jazyk
(Development Language), který má sloužit jako podklad pro překlady do
jiných jazyků.

**Detailnější informace o projektu** jsou uvedeny na záložce „Project
Info", ve které jsou kromě informací z hlavičky dále uvedeny určité
statistiky o projektu. Například kolik je v projektu uloženo frází,
datum založení projektu nebo datum poslední změny v databázi. Konkrétně
z obrázku je patrné, že například celkový počet frází v databázi
projektu MPA je 1837 a do srbštiny je jich zatím přeloženo 1001.

\
\

\
\

**MVC**

-   Původně jsem vytvářel veškerou grafiku a společně s aplikační částí
    (vše v jedné třídě). Takto vznikly záložky jako -- export, import a
    nebo hlavička. Tento způsob ale není z hlediska přehlednosti,
    znovupoužitelnosti a případné možnosti rozšíření vhodný. Všechny
    tyto komponenty tedy byly předělány do struktury MVC
    (model-view-controller), která rozděluje datový, grafický a řídící
    model.

-   Příklad jak funguje

    -   Uživatel provede akci -- klikne na tlačítko (např. load)

    -   Controller předá informaci do modelu, aby načetl aktuální stav
        z databáze (aktualizoval původní hodnoty)

    -   Poté předá řadič data komonentě (tabulce), která data zobrazí.

    -   Grafika je tak nezávislá na datech -- takovýto panel může byt
        použit kdekoliv jinde v MPA, dá se lépe otestovat, udržovat
        (např. přidat vícevláknovou podporu)

**Vlákna**

-   Dále bylo třeba vyřešit problematiku vláken.

-   Všechny grafické komponenty je třeba spouštět v jednom vlákně zvaném
    EDT (Event-Dispatch-Thread), protože mnohé grafické třídy neobsahují
    (z výkonostních důvodů) žádnou synchronizaci (neboli bezpečné
    ošetření, spuštění vláken). EDT tedy dokáže obsluhovat frontu
    událostí - zaregistrovat přijatou zprávu, uložit ji do fronty a
    vykonat v pořadí ve kterém do fronty přišla a zároveň - během
    provádění tedy přímo nereaguje na podněty uživatele (okno zamrzne).

\
\

-   Časově náročné operace jako načtení z databáze, načtení souboru
    s přeloženými frázemi, procházení souborového systému, uložení změn
    do databáte, do souborů atd. je vhodné spustit na pozadí v jiném
    vlákně (uživatel může dále s aplikaci pracovat -- GUI nezatuhne).

Tomuto vícevláknovému přístupu velmi pomohl MVC, tím že veškerá grafika
dané komponenty je uložena v jedné třídě.

\
\

-   **Internacionalizace**

Internacionalizovaný software (cíl internacionalizace)

Cílem celé I18N je tedy software, který neobsahuje žádné kulturně
závislé informace a může být bez problémů nasazen do jakýchkoliv zemí,
podle preferencí cílových uživatelů.

-   Jazykově závislá data (Textové elementy, zprávy, chybové hlášky a
    obrázky) se ukládají mimo zdrojový kód.

    -   V opačném případě -- velké riziko zanesení chyby, složitá úprava
        a hledání textů.

    -   V Javě ResourceBundles (nejčastěji property soubor, který
        obsahuje klíč=hodnota, klíč (výchozí jazyk) je stejný pro
        jednotlivé soubory -- mění se pouze hodnoty).

    -   Aparát v Javě třída MessageFormat -- získá hodnotu (překlad) na
        základě předloženého klíče a zvoleného jazyku.

-   Podpora číselných a časových datových typů:

    -   Jedná se o to, jaký má programovací jazyk aparát pro formátování
        těchto typů.

    -   Datumy -- třída DateFormat (předdefinované), SimpleDateFormat
        (vytváření vlastní formátů)

    -   Číselné údaje (včetně měnových údajů) -- třída NumberFormat,
        speciálně DecimalFormat (umožňuje zobrazování nevýznamových nul,
        zobrazení na určitý počet míst)

-   Podporují se nestandardní znakové sady. -- ty které nejsou založeny
    na latince (ASCII) -- například ruština, čínština a arabština.

    -   V javě implicitně zabudovaná podpora Unicode

-   Aplikace je snadno rozšiřitelná o nové jazyky.

    -   není potřeba rekompilace[ ]{style="display: none"}

    -   pouhé přidání jar souboru (se všemi lokalizovanými vlastnostmi
        -- jména měsíců, dnů, formáty atd.) do složky, která je k tomu
        určena.

Musí být podporovány všechny jinak uživatel s aplikace nezíská dobrý
dojem

\
\

-   **Lokalizace**

\
\

Hlavně překlad textů!

1.  Nastavení rozměrů dialogů v případech, že je přeložený text delší
    než text původní.

\
\

2.  Kulturní a místní odlišnosti, které vyžadují úpravu ikon, kurzorů,
    barev, navigací (logika posloupnosti příkazů a ergonomie) nebo
    symbolů (např. různé měrné jednotky, hodnota elektrického napětí).

\
\

Data vycházející z dané kultury jako je čas, datum, číslice (americka a
nase desetinna tecky) a měna jsou formátovány správně vzhledem k
uživatelově jazyku a geografické poloze (v Javě se o toto starají
specializované třídy -- spíše starost I18N).

1.  -   Dále co uvádím v práci jsou:

        -   kalendářní systémy -- ne všude se roky počítají stejně
            (například izrael).

        -   Časová pásma -- ne všude je přepínání mezi letním a zimním
            časem.

\
\

3.  Odlišnosti ve formátování. Například způsob zápisu telefonních
    čísel, adres, datumů, číslic, oddělovačů nebo odlišnosti ve
    způsobech oslovení.

\
\

4.  Politické a ekonomické záležitosti typu nemožnost platit kreditní
    kartou online v některých zemích, pomalé nebo omezené připojení k
    internetu v rozvojových zemích, zakázané symboly (např. postavení
    muže a ženy v arabských zemích).

5.  Právní záležitosti.

6.  Použití klávesnice a rozdílné rozložení kláves.

7.  Jazyky psané zprava doleva (hebrejština, arabština) nebo akcentované
    aj. specifické znaky některých jazyků (němčina, švédština, atd.).

V neposlední řadě také určit způsob jakým se bude program prodávat,
prezentovat, design, prodejní obal a technickou i obchodní podporu
(jinak hrozí odrazení zákazníka od koupi).

\
\

-   **Popis jednotlivých nástrojů aplikace**

1.  Naplnění databáze -- export textů ze zvolených konfiguracních
    souborů. Tuto operaci provádí nástroj „Export" (kapitola
    [6.5]{style="background: #c0c0c0"}).

-   -   -   Tato záložka obsahuje parametry pro výběr požadovaných
            konfiguračních souborů -- ze souborového systému (root
            adresář) nebo z objektové databáze.

        -   Export projde všechny soubory a zjišťuje zda jsou to
            property soubory, pak načte jejich obsah a postupně vkládá
            do databáze, pokud již  databáze obsahuje stejnou německou
            frází, přidá se pouze do odkazu kontextuální informace.

2.  []{#_Ref288295430} Editace textů uložených v databázi -- Pomocí
    nástroje „Edit Phrases" (kapitola
    [6.6]{style="background: #c0c0c0"}) je možné provádět jednotlivé
    úpravy požadovaných překladů.

-   -   -   Přehledné zobrazení (ve formě tabulky) všech jazykových
            překladů dané fráze.

        -   Možnost provádět filtrování tabulky -- např. zobrazit pouze
            nepřeložené fráze z daného jazyku.

        -   Uživatel může samozdřejmě provést překlad, popř. poupravit a
            popřípadě k provedenému překladu připojit komentář.

        -   V tabulce je možné vyhledávání a řazení podle zvoleného
            sloupce.

3.  Export textů z databáze do Excelu (kapitola
    [6.7]{style="background: #c0c0c0"}) -- V další části nástroje „Edit
    Phrases" je možné vybrat z databáze konkrétní fráze, které se
    poskytnou překladateli ve formě Excel souboru.

-   -   -   Možnost určit přesně ty fráze, které je třeba přeložit
            (defaultně se exportuje celá databáze).

        -   Dále uvést komentář k německé frázi pro překladatele,
            v jakém kontextu má frázi přeložit. Například připojit
            komentář, že fráze je příliš dlouhá a je třeba pouze její
            vhodnější zkrácení, a ...

        -   Pomocí filtru a pomocí sloupečku status kde je určeno, zda
            je fráze určena k překladu nebo nebude vyexportována.

        -   Jedná se o textový soubor, který má podobu tabulky a
            jednotlivé texty jsou od sebe odděleny tabelátory, Excel
            tento soubor pak dokáže otebřít a správně zobrazit.

4.  Import přeložených frází zpět do databáze (kapitola
    [6.8]{style="background: #c0c0c0"}) -- Pomocí nástroje „Import
    Phrases" je možné aktualizovat v databázi ty fráze, které nám
    překladatel přeložil.

-   -   -   Poté, co je proveden překlad vyexportovaných frází je třeba
            tyto nové texty nahrát zpět do MPA. Import do konkrétních
            konfiguračních souborů neprobíhá napřímo, ale texty je třeba
            nejprve nahrát do databáze (aktualizovat) zvoleného projektu
            a až poté je možné provedené změny promítnout do MPA.

        -   Mezikrok načtení překladů do tabulky slouží k tomu, aby
            uživatel mohl zkontrolovat, případně poopravit nevyhovující
            překlady.

        -   Fráze určené pro import

5.  Import textů zpět do MPA -- import (přeložených) textů z databáze
    do zvolených konfiguračních souborů. Tuto operaci provádí nástroj
    „Import" (kapitola [6.9]{style="background: #c0c0c0"}).

-   -   -   Opět za pomoci parametrů (root adresář). Prochází se všechny
            property soubory a vyhledává se daná německá fráze, pokud se
            nalezne -- automaticky se k tomuto klíči připojí přeložená
            hodnota.

        -   Důležitost výběru správného adresáře -- je možné, že v jiném
            adresáři se bude nacházet stejná německá fráze, pak by se
            automaticky i její hodnota přepsala -- fráze mohou mít
            v různých kontextech různé překlady.

        -   Německé překlady tedy musejí zůstat bezezměny (změna je
            zakázaná), aby bylo možné naimportovat zpět na správné místo
            přeložené fráze.

\
\

-   **Přínos aplikace**

```{=html}
<!-- -->
```
-   Správa velkého množství dat

    -   -   Několik souborů je možné nahrát do databáze a se všemi pak
            pracovat jednotně v jedné tabulce -- filtrovat, řadir,
            vyhledávat.

        -   Takto je například jednoduché zjistit všechny fráze, které
            zatím nemají překlad a vyexportovat je k překladateli.

-   Výstup pro překladatele

Hlavní výhodou použití Excel souboru je pro překladatele to, že jsou
všechny informace potřebné k překladu uvedeny společně v jednom souboru,
ve kterém se překladatel zároveň dokáže bez problémů orientovat. Může
tak provádět překlady z pohodlí domova, bez nutnosti instalace editoru
pro soubory s uloženými lokálně závislými
texty[^1^](#sdfootnote1sym){#sdfootnote1anc .sdfootnoteanc}. Z tohoto
pohledu by tak byl stížený již samotný transport textů směrem k
překladateli a poté zpět do firmy.

-   Srovnání změněných překladů s předchozí verzí

-   Zjednodušená práce s datumovými formáty

    -   -   V nástroji Export se nachází možnost vyhledání všech
            datumových formátů, které jsou uloženy v objektové databázi.

        -   Celá databáze se automaticky prohledá a vráti jen datum.
            Formáty, které jsou zobrazeny opět v jedné tabulce (neboli
            XML souboru).

        -   V tabulce je možný jejich edit a změny opět automaticky
            promítnou do MPA.

-   Možnost zobrazení přeloženého textu v příslušné grafické komponentě.

```{=html}
<!-- -->
```
-   **Reakce na posudky**

```{=html}
<!-- -->
```
-   Nemohla byt overena funkcnost

    -   V 6. Kapitole jsem popsal kolobeh krok po kroku, jak by mel
        uzivatel aplikace MITToolkit postupovat -- každý krok je doplnen
        prislusnym obrazkem.

-   Proces vzniku grafickeho navrhu

    -   Zde bylo nejdůlezitejsi bylo naucit se manipulovat s layout
        managery a naucit se pracovat ve vyvojovem prostredi NetBeans -
        popisovat managery nebo vyvojove prostredi NetBeans me prislo
        zbytecne.

    -   S tím souvisí bod v zadání -- implementuje ve Swingu, což je
        udělané..jen mě po delší době tento bod přišel zbytečný.

-   Titulni list a zapis zdroju

    -   Pouzil jsem formular ze stranek kvd, který je ve formatu Word
        2007.

-   Zastarale informace o zdrojich

    -   Cerpal jsem ze starsich kvalitnich zdroju, bohuzel jsem zapomnel
        pozmenit verzi z 2.0 na 5.2

-   Prinos autora

    -   Veskere graficke komponenty (krome pouziteho messagebundle a
        reporesourbundle editoru). Ty ale také bylo třeba pochopit,
        neboť jsem je obě ještě rozšiřoval o některé funkce (například
        aplikace exportovacích a importovacích pravidel)

    -   Aplikacni část jiz byla z pocatku před mym prichodem vytvorena

        -   Export / import / cteni ze souboru / cteni z databaze / atd.

    -   Pozdeji (po povyseni) již i úpravy a vytváreni aplikacni casti

        -   Manipulace s XML souborem.

        -   Kontextové informace,

        -   Filtry pro edit phrases / import phrases tab.

        -   Ukladani a nacitani posledniho stavu aplikace
            (MITProperties).

    -   Psani testu, které navozuji nejakou chybu

        -   **Vycet nalezenych a opravenych bugu:**

    -   Cca. 10 tisic radek kodu napsaneho mou rukou, priblizne 2/3
        veskereho kodu.

\
\

Vetsina pouzitych zdroju byla psana v anglictine - například Java
Tutorial.

\
\

-   Reakce na otázky

1.  Zkušenosti s využíváním vytvořené aplikace

-   -   -   Aplikace je zatím přeložena do -- angličtiny, češtiny a
            srbštiny.

        -   V současné době se plánuje překlad do švýcarštiny a řečtiny.

        -   Zatím byl použit pouze nástroj Export a Import.

        -   Nevým o žádfném problému, který by překladatel s Excel
            souborem měl.

2.  Unicode a UTF-8

Unicode reprezentuje každý znak pomocí tří (dvou ??) bajtů

UTF -- dokáže znaky reprezentovat pomocí 1,2, 3, 4 nebo i 5 bajtů podle
potřeby

-   -   -   zpracování je rychlejší

        -   Šetří místo

        -   Např. akcentované znaky kodovat 2 bajtově a neakcentované
            (ASCII) jednobajtově.

        -   UTF-8 a Unicode jsou kompatibilní -- UTF převádí automaticky
            na Uncidoe.

UTF8 odstraňuje všechny nevýhody Unicode -- zachováva kompatibilitu,
není tolik náročný na paměť, umožňuje aplikacím použít všech výhod
univerzální znakové sady.

3.  Blokové schéma

-   -   -   Prvky jsou zobrazeny pomocí jednoduchých obrazců -- zde
            kvádr

        -   Chybí zde orientace, jak na sebe jednotlivé prvky působí --
            směr informačního toku od jednoho prvku k druhému.

        -   Chybí závislosti

::: {#sdfootnote1}
[1](#sdfootnote1anc){#sdfootnote1sym .sdfootnotesym} Více o této
problematice pojednává kapitola [7.1]{style="background: #c0c0c0"}
[Editor pro MessageBundle soubory]{style="background: #c0c0c0"}.
:::
