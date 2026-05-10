---
title: "Bitmapová grafika na 2.st. Z.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/Praxe/Inf/Bitmapová grafika/Bitmapová grafika na 2.st. Z.doc"
date: 2009-11-20
type: DOC
---

::: {title="header"}
Autoři: Jan Hodinář, Petr Simbartl, Lukáš Štich
:::

# Analýza současného stavu výuky bitmapové grafiky na 2. stupni ZŠ a návrh vlastní podpory této oblasti výuky {#analýza-současného-stavu-výuky-bitmapové-grafiky-na-2.-stupni-zš-a-návrh-vlastní-podpory-této-oblasti-výuky .western lang="cs-CZ"}

Tento článek je teoretickým úvodem našeho projektu zabývajícím se výukou
bitmapové grafiky na základních školách v České Republice. V první části
bych rád analyzoval současný stav a přístupy k výuce tohoto tématu. Dále
pak popíši a rozeberu naší vlastní podporu v této oblasti a seznámím
čtenáře s naším projektem a jeho implementací do hodin Informatiky na
základních školách.

Prvním hlediskem na které jsme se soustředili je ročník, ve kterém se
toto téma vyučuje a pokud je jich více, ve kterém je na něj kladen
největší zřetel. Rámcově vzdělávací program pro základní vzdělávání
klade důraz na to, aby bylo toto téma zastoupeno v obou stupních
základní školy. Tento požadavek však popisuje z odborného hlediska dosti
neohrabaně. Pro první stupeň doporučuje jako učivo „základní funkce
textového a grafického editoru" , přičemž pro stupeň druhý je to
„počítačová grafika, rastrové a vektorové programy". Pokud se ovšem na
tyto dvě věty podívá odborník může nadhodit že rastrové a vektorové
programy jako takové je výraz neohrabaný a že toto označení se spíše
používá pro výše zmíněné grafické editory. Také pojem počítačová grafika
dnes zahrnuje také modelování 3D grafických objektů pomocí počítače, což
se pro výuku na základní škole nehodí.

Než se tedy vrátíme k problému zařazení do správného ročníku je třeba si
definovat co se na základních školách vůbec učí v hodinách informatiky
v souvislosti s grafikou. Po prostudování ŠVP dvanácti škol a porovnání
poznatků z našich pedagogických praxí jsme zjistili že se na základních
školách v drtivé většině probírá na úvod seznámení s bitmapovou a
vektorovou grafikou, přičemž se vyzdvihne jejich rozdíl a uplatnění
stejně jako formát souborů, které používají. Většina škol si potom zvolí
jeden bitmapový editor, kterému zasvětí další hodiny a tím je pro ně
toto téma vyčerpáno. Některé školy potom ve vyšších ročnících přidají
grafiku vektorovou v závislosti na tom zda mají pro podporu této výuky
prostředky.

Tímto si tedy odpovídáme na otázku vhodného ročníku k této výuce.
Z následující tabulky škol je patrné že většina škol pokud bitmapovou
grafiku vůbec učí, činí tak na prvním stupni většinou v 5. ročníku.
V tomto ročníku se s informatikou většinou začíná a proto rozhodně není
dost času na to, aby téma bitmapové grafiky bylo probráno dopodrobna.
Školy se k tomuto tématu většinou vracejí na začátku druhého stupně, kde
toto téma doberou důkladněji. A pokud mají k dispozici vhodný vektorový
editor zařadí práci s ním většinou do vyšších ročníků, ale to se
vzhledem k malé hodinové dotaci a velkému obsahu témat v informatice
většinou neděje. V následující tabulce je zobrazeno 12 škole, jejich
hodinová dotace informatiky na prvním a druhém stupni základní školy a
také ročník, ve kterém se bitmapová grafika učí.

\
\

**Tabulka [1]{style="background: #c0c0c0"}[: Výuka bitmapové grafiky na
základních školách]{lang="en-US"}**

  ------------------ ------------------- ------------ ------------------------------
  ZŠ                 Hodin Informatiky                Ročník s bitmapovou grafikou
                     2\. stupeň          1\. stupeň   
  Mšeno              2                   1            5\. ročník
  Chrastava          2                   1            5\. ročník
  22\. Plzeň         9                   1,5          5\. a 7. ročník
  28\. Plzeň         4                   2            nezveřejněno ŠVP
  Žatec              6                   0            6\. ročník
  Dobřany            1                   1            5\. a 6. ročník
  Slušov             4                   1            5\. a 8. ročník
  Chlumčany          4                   1            5\. a 6. ročník
  Praha - Kladská    1                   1            Neučí
  Žďár nad Sázavou   ?                   ?            4\. ročník
  Letovice           1                   1            5\. a 8. ročník
  Emy Destinové      4                   1            Neučí
  ------------------ ------------------- ------------ ------------------------------

Další otázkou, kterou je třeba zodpovědět je kolik hodin tomuto tématu
věnovat. ŠVP na druhý stupeň základní školy připouští v základu jednu
hodinu informatiky na celé 4 roky. Jak je patrné z tabulky výše některé
školy toto dodržují a mají proto tématický okruh celé informatiky značně
omezený. Jiné školy dávají informatice prostor větší díky disponibilním
hodinám. Jelikož je v dnešní společnosti kladen z hlediska informatiky
veliký důraz na textové editory, internet a prezentace tak na bitmapovou
grafiku nezbývá příliš času. Drtivá většina škol, které toto téma
vyučují mu věnují akorát tolik času na to, aby děti seznámila se všemi
funkcemi aplikace Malování, o kterém budu mluvit později. Pokud škola
využívá program jiný, náročnější, tak je samozřejmě možné tématu věnovat
času více. Abych se tedy dostal ke konkrétnímu číslu, většina škol u nás
tomuto tématu věnuje maximálně několik hodin ve svém rozvrhu. Na to, aby
se žáci seznámili se všemi funkcemi jednoduchého grafického editoru
bohatě stačí 5 hodin. Toto číslo se lehce liší v závislosti na
podmínkách na daných školách. Některé školy toto téma nevyučují vůbec a
některé mu věnují času více, zvláště pokud využívají složitější editory
a nebo pokud se tomuto tématu věnují ve více ročnících.

Když jsme si tedy ujasnili otázku hodinové dotace, bylo třeba se zeptat
jaký program se dnes na základních školách používá k výuce bitmapové
grafiky. Tato otázka byla zodpovězena velice rychle neboť drtivá většina
škol využívá program Malování, který je součástí základní instalace MS
Windows. Tento nástroj, ač nemá moc sofistikovaných funkcí je perfektní
pro to, aby se na něm úplným začátečníkům demonstrovaly možnosti úprav
bitmapových obrázků. Kromě toho že je zdarma a je to relativně mocný
nástroj, který zvládne veškeré základní úpravy má také příjemné
uživatelské rozhraní, na které jsou děti zvyklé z ostatních programů ve
Windows a proto se s ním dobře pracuje. Na některých školách se kromě
malování ještě používá program GIMP, který je také zdarma a obsahuje
mnohem větší kvantum funkcí než Malování, ovšem pro úplné začátečníky
podle našeho názoru není úplně vhodný. Jeho velké množství funkcí může
na děti působit matoucím dojmem a také ovládání není tak intuitivní. Jen
velice málo škol pak používá profesionální nástroj pro úpravu 2D grafiky
Photoshop. Tento nástroj se pro začátečníky opravdu nehodí už proto že
je placený a navíc jeho licence je relativně drahá. Můžeme ho doporučit
spíše do škol, které se grafikou zabývají do hloubky a nebo mají na toto
téma zájmové kroužky.

Poslední věc, která nás zajímala byla metodika výuky tohoto tématu. Pro
vhodnou podporu tohoto tématu je dobré mít na škole správné technické
pomůcky. Jelikož se jedná o grafické téma, tak je vizuální stránka pro
děti hodně důležitá. Většina škol tuto podporu realizuje pomocí
projektoru nebo interaktivní tabule. Zvláště pak v Plzni kde byl městem
na implementaci interaktivních tabulí do škol vypsán grant je situace
v tomto ohledu velice dobrá. Z hlediska didaktiky pak tyto hodiny
probíhají podobně jako většina jiné praktické informatiky. Jedná se o
frontální výuku, která se místy překlápí do individuální, jak žáci
začínají postupně sami pracovat poté co jim učitel látku právě pomocí
projektoru a nebo tabulce názorně předvede a vysvětlí. Učitel pak
postupně látku doplňuje jak děti sami pracují a individuálně je
kontroluje a poskytuje rady jak daný problém řešit.

## Podpora výuky bitmapové grafiky {#podpora-výuky-bitmapové-grafiky .western lang="cs-CZ"}

Dalším naším úkolem bylo navrhnout vlastní podporu výuky tohoto tématu.
Podpora to měla být komplexní, tudíž zaměřena jak na učitele tak na
žáky. Rozhodli jsme se pro tradiční formu výuky praktické informatiky na
základních školách. Bylo tedy nutné nejdřív rozhodnout několik kritérií
podle kterých se řídit. Pokud mám postupovat stejným způsobem jako při
naší analýze současné výuky tak to nejprve bylo rozhodnutí do jakého
ročníku výuku zařadit. Jelikož jsme se rozhodli výuku nerozdělovat mezi
více ročníků z důvodu ucelenosti látky tak jsme nalezli odpověď na tuto
otázku relativně snadno. Z důvodů nízké hodinové dotace a nenáročnosti
tématu na psychický vývoj dětí jsme se rozhodli zařadit naši výuku do
pátého nebo šestého ročníku. Postupovali jsme tedy jako vetšina škol a
doporučili naši výuku na první nebo začátek druhého stupně.

Co se týče hodinové dotace, tak jsme zvolili celkem 8 vyučovacích hodin.
Tento počet je více než dostatečný pro to, aby se toto téma na základní
škole dalo probrat včetně teoretického úvodu. Myslíme si že i školy,
které disponibilních hodin nevyužívají a mají tedy pro celou informatiku
nízkou hodinovou dotaci mohou naši podporu i tak do svých hodin
zahrnout. Poslední rozhodnutí spočívalo v tom jaký grafický editor
vybrat. Jelikož jsme chtěli naši podporu zpřístupnit všem školám,
vybrali jsme pro ni program Malování, o kterém jsem psal už výše. Důvod
pro výběr je tedy z naší analýzy celkem jasný.

Když tedy přistoupím k samotné podpoře výuky, tak jsme ji rozdělili do
dvou částí. Část pro učitele se celá nachází v adresáři učitel. Tato
část se skládá z příprav na hodiny, metodických pokynů a podkladů, které
učitel dá dětem k dispozici při hodinách. Každá hodina má svůj vlastní
dokument, ve kterém je podrobně popsána. Název tohoto dokumentu je
uveden u každé hodiny v seznamu připravených hodin, které se nachází
níže v tomto dokumentu. Každá hodina má také v adresáři učitel svůj
vlastní podadresář, ve kterém se nachází buď podklady pro děti a nebo
ukázka předpokládaného řešení úkolů z dané hodiny. Aneb to co děti budou
tvořit. Druhá hlavní část je část pro děti a nachází se proto v hlavním
adresáři s názvem děti. Tato podpora je tvořena pdf dokumenty s postupy
daných úkolů, které děti budou dostávat po dané hodině. Je to hlavně
z důvodu opakování a nebo nemoci dítěte, které tak o nic nepřijde, i
když na hodině chybělo.

## Seznam a témata námi připravených hodin {#seznam-a-témata-námi-připravených-hodin .western lang="cs-CZ"}

1\.

*[Téma hodiny:]{.underline}* Základní seznámení s  programem Malování.

*[Doporučený ročník:]{.underline}* 5. nebo 6.

*[Cíle:]{.underline}* Žáci dokáží vysvětlit rozdíl mezi bitmapovou a
vektorovou grafikou.

Žáci jsou schopni s úspěchem použít internetový grafický editor.

*[Pojmy:]{.underline}* Bitmapová a vektorová grafika, tvary, body,
internet, internetový grafický editor, grafické formáty souborů.

*[Soubory:]{.underline}* m00.doc

\

2\.

*[Téma hodiny:]{.underline}* Základní seznámení s  programem Malování.

*[Doporučený ročník:]{.underline}* 5. nebo 6.

*[Cíle:]{.underline}* Žáci dokáží použít základní negrafické funkce
programu Malování jako je ukládání, kopírování a vkládání.

Žáci jsou schopni při tvorbě obrázku použít funkce plechovka, lupa,
čára, tužka a kapátko.

*[Pojmy:]{.underline}* Malování, plechovka, lupa, čára, tužka, kapátko.

*[Soubory:]{.underline}* m01.doc, m01.bmp

\

3\.

*[Téma hodiny:]{.underline}* Seznámení s výběrem a průhledností.

*[Doporučený ročník:]{.underline}* 5. nebo 6.

*[Cíle:]{.underline}* Žáci umí do obrázků vložit text a použít nástroj
guma.

Žáci dokáží úspěšně použít kopírování, zmenšování objektů, výběr a
použití průhlednosti.

*[Pojmy:]{.underline}* Písmo, průhlednost, výběr, guma, text.

*[Soubory:]{.underline}* m02.doc, m02.pdf

\

4\.

*[Téma hodiny:]{.underline}* Křivky a tvorba pohlednice.

*[Doporučený ročník:]{.underline}* 5. nebo 6.

*[Cíle:]{.underline}* Žáci ovládají další grafické nástroje jako štětec
a sprej.

Žáci zvládají práci s křivkami, jinými tvary a vkládáním při tvorbě
obrázků.

*[Pojmy:]{.underline}* Křivky, guma, štětec, sprej, pozadí, ohraničení,
vkládání.

*[Soubory:]{.underline}* m03.doc, m03.pdf

\

5\.

*[Téma hodiny:]{.underline}* Tvorba graffiti.

*[Doporučený ročník:]{.underline}* 5. nebo 6.

*[Cíle:]{.underline}* Žáci si zopakují práci s nástroji, které už znají.

Žáci se vyzkouší použít jednotlivé nástroje k vytvoření uceleného
výsledku.

*[Pojmy:]{.underline}* Čáry, plechovka, výplň, přesun, průhlednost,
podklad, schránka.

*[Soubory:]{.underline}* m04.doc, m04.pdf

\

6\.

*[Téma hodiny:]{.underline}* Výroba hrocha.

*[Doporučený ročník:]{.underline}* 5. nebo 6.

*[Cíle:]{.underline}* Žáci budou schopni z jednoduchých obrazců složit
složitější obrázek.

Budou zvládat použít funkce typu otočit, překlopit a zmenšit.

Uvědomí si důležitost správného postupu a plánování.

*[Pojmy:]{.underline}* Křivky, otočení, překlopení, schránka, sprej,
plechovka, výběr, jiné tvary, guma, štětec, plechovka, ořez.

*[Soubory:]{.underline}* m05.doc, m05.pdf

\

7\.

*[Téma hodiny:]{.underline}* Výroba prasete.

*[Doporučený ročník:]{.underline}* 5. nebo 6.

*[Cíle:]{.underline}* Žáci budou schopni z jednoduchých obrazců složit
složitější obrázek.

Budou zvládat použít funkce typu otočit, překlopit a zmenšit.

Uvědomí si důležitost správného postupu a plánování.

*[Pojmy:]{.underline}* Křivky, otočení, překlopení, schránka, sprej,
plechovka, výběr, jiné tvary, guma, štětec, plechovka, ořez.

*[Soubory:]{.underline}* m06.doc, m06.pdf

\

8\.

*[Téma hodiny:]{.underline}* Koláž krajiny.

*[Doporučený ročník:]{.underline}* 5. nebo 6.

*[Cíle:]{.underline}* Žáci si zopakují práci s výběrem, kopírováním,
průhledností a zmenšováním.

Žáci budou schopni k úkolu vybrat vhodné nástroje, které už znají.

Žáci si rozvinou tvořivost a estetické cítění při tvorbě vlastní koláže.

*[Pojmy:]{.underline}* Výřez, vkládání, schránka, změna velikosti.

*[Soubory:]{.underline}* m07.doc, m07.pdf

\

\

\

::: {title="footer"}
[5]{style="background: #c0c0c0"}
:::
