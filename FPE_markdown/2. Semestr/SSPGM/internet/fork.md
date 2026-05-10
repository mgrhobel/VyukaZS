---
title: "fork.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/internet/fork.doc"
date: 2009-05-02
type: DOC
---

**Výpočet v módu jádro**

\

\

v důsledku událostí

\

-   přerušení (od zařízení asynchronně)

-   výjimky

-   softvérové přerušení

\

\

řízení se předá na proceduru pro ošetření odpovídající události

\

část stavu přerušeného procesu potřebná pro obnovení jeho vykonávání po
skončení obsloužení události (počítadlo instrukcí, PSW) se uloží do
zásobníku jádra přerušeného procesu

\

\

**Sytémové volání**

\

[v standardní knihovně jazyka C je pro každé systémové volání obálková
procedura, řízení se předá softvérovým přerušením proceduře jádra, která
se nazývá ]{lang="en-US"}[**syscall( ), system_call,**
]{lang="en-US"}[protože je jedna pro všechny služby, požadovaná služba
je identifikována parametrem procedury, který se nazývá číslo
systémového volání]{lang="en-US"}

\

\

Linux

\

[uživatelský mód mód jádra]{lang="en-US"}

![DrawObject1](fork_html_b060055b.gif){#DrawObject1 align="left"
hspace="12" width="665" height="252"}\

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

[aplikační program volá službu ]{lang="en-US"}[**xyz**]{lang="en-US"}[
(např. ]{lang="en-US"}[**fork()**]{lang="en-US"}[)]{lang="en-US"}

\

[obálková procedura uloží číslo služby do registru
]{lang="en-US"}[**eax**]{lang="en-US"}[ ]{lang="en-US"}

[(5 pro ]{lang="en-US"}[**fork()**]{lang="en-US"}[) před vykonáním
]{lang="en-US"}[**int 0x080**]{lang="en-US"}

\

[**system_call:** ]{lang="en-US"}

-   [uloží obsah registrů (HW kontext)]{lang="en-US"}

-   [zavolá odpovídající funkci (v jazyku C)]{lang="en-US"}

-   [ukončí se voláním]{lang="en-US"}[
    **ret_from_sys_call()**]{lang="en-US"}

\

\

**Výjimky se spracují obdobně**

\

jsou synchronní s procesem (vznikají v důsledku událostí způsobených
vykonáváním procesu)

\

procedury pro jejich zpracování mají obdobnou strukturu jako

[procedura pro systémová volání
]{lang="en-US"}[**system_call**]{lang="en-US"}

Linux

\

[Procedura pro zpracování výjimky:]{lang="en-US"}

\

-   [uloží]{lang="en-US"}[ ]{lang="en-US"}[obsah
    registrů]{lang="en-US"}[ ]{lang="en-US"}

-   zpracuje výjimku (funkce v jazyku C)

    -   pošle signál procesu

    -   [zpracuje žádost o stránku]{lang="en-US"}

-   [ukončí se voláním funkce
    ]{lang="en-US"}[**ret_from_exception()**]{lang="en-US"}

\

[**Zpracování přerušení**]{lang="en-US"}

\

[přerušení je obecně asynchronní vzhledem k přerušenému
procesu]{lang="en-US"}

-   proces čeká na přenos dat, po dokončení přenosu je přerušen úplně
    jiný proces

\

[zpracování přerušení nesmí způsobit čekání, přerušený proces zůstává ve
stavu běžící]{lang="en-US"}

\

[čas zpracování přerušení je započítán přerušenému procesu, při
zpracování přerušení se tedy přistupuje do jeho záznamu
]{lang="en-US"}[**proc**]{lang="en-US"}

\

[obsloužení přerušení:]{lang="en-US"}

\

-   [uloží IRQ (]{lang="en-US"}[*Interrupt ReQuest)* ]{lang="en-US"}[a
    obsah registrů]{lang="en-US"}

-   [pošle potvrzení PIC (]{lang="en-US"}[*Programmable Interrupt
    Controller)*]{lang="en-US"}

-   vykoná obslužní proceduru přerušení

-   [ukončí se skokem na
    ]{lang="en-US"}[**ret_from_intr()**]{lang="en-US"}

\

**Vzájemné vnoření systémového volání, výjimek a přerušení**

\

\

Předpokládejme odladěné jádro

\

1.  zpracování systémového volání

[- může vzniknout výjimka žádost o stránku (výpadek
stránky)]{lang="en-US"}

\- může vzniknout přerušení

\

2.  zpracování výjimky (jakékoliv)

[- může vzniknout přerušení]{lang="en-US"}

\

3.  zpracování přerušení

[- může vzniknout přerušení]{lang="en-US"}

\

\

[při každém odkladu zpracování některé z uvedených událostí musíme
uložit odpovídající HW kontext ]{lang="en-US"}

\

-   vytváří se kontextové vrstvy v zásobníku jádra přerušeného procesu

-   existuje globální zásobník přerušení

\

\

přerušení nejsou všechna stejně naléhavá

\

-   prioritní schéma

-   [odložení vykonání nekritických akcí obsluhy]{lang="en-US"}

\

\

**prioritní schéma**

\

-   [přerušení mají přiřazené prioritní úrovně
    (]{lang="en-US"}[*interrupt priority level*
    ]{lang="en-US"}[)]{lang="en-US"}

\

![DrawObject2](fork_html_1d9787c8.gif){#DrawObject2 width="603"
height="253"}

\

\

-   [ve stavovém registru procesoru je nastavena okamžitá prioritní
    úroveň zpracovávaného přerušení ]{lang="en-US"}

-   vznikne-li přerušení s nižší nebo stejnou prioritní úrovní, je
    uloženo a jeho obsluha je odložena

-   [vznikne-li přerušení s vyšší prioritní úrovní, uloží se HW kontext,
    na tuto vyšší prioritní úroveň se nastaví hodnota okamžitého
    přerušení ve stavovém registru procesoru, zpracuje se přerušení
    ]{lang="en-US"}

-   [při skončení zpracování se z uloženého PSW obnoví okamžitá
    prioritní úroveň přerušení]{lang="en-US"}

\

\

\

\

**Příklad:**

\

\

[aplikační program ]{lang="en-US"}[→]{lang="en-US"}[
]{lang="en-US"}[**xyz**]{lang="en-US"}[
]{lang="en-US"}[→]{lang="en-US"}[ výpadek stránky
]{lang="en-US"}[→]{lang="en-US"}[ ]{lang="en-US"}

[přerušení od terminálu ]{lang="en-US"}[→]{lang="en-US"}[ diskové
přerušení ]{lang="en-US"}[→ ]{lang="en-US"}

[přerušení od hodin]{lang="en-US"}

![DrawObject3](fork_html_35fc1879.gif){#DrawObject3 width="603"
height="700"}

\

\

**odložení vykonání nekritických částí obsluhy přerušení**

(Linux)

\

\

akce při obsluze přerušení se dělí do tří tříd

\

-   [kritické, potvrzení přerušení, aktualizace dat používaných
    zařízením i procesorem, přerušení jsou zakázána
    (]{lang="en-US"}[*disabled*]{lang="en-US"}[)]{lang="en-US"}

\

-   [nekritické, data používána jenom procesorem, přerušení uvolněna
    (]{lang="en-US"}[*enabled*]{lang="en-US"}[)]{lang="en-US"}

\

-   [nekritické odložitelné, kopírování vyrovnávací paměti do adresového
    prostoru procesu, vykonávané funkcí jádra ]{lang="en-US"}[*bottom
    half*]{lang="en-US"}[, vykonají se však před
    ]{lang="en-US"}[**ret_from_intr()**]{lang="en-US"}[ ]{lang="en-US"}

\

\

\

[umožňuje prokládání
(]{lang="en-US"}[*interleaving*]{lang="en-US"}[)]{lang="en-US"}[
]{lang="en-US"}[vykonávání obsluh přerušení]{lang="en-US"}

\

-   [zlepšuje propustnost PIC a řadičů zařízení, nemusí čekat na
    dokončení obsluhy předcházejícího přerušení]{lang="en-US"}

-   zjednodušuje kód jádra a zlepšuje přenositelnost

\

\

\

\

[**Vytvoření procesu --** ]{lang="en-US"}[**fork()**]{lang="en-US"}

\

1.  [Přiděl nový PID a ]{lang="en-US"}[**proc**]{lang="en-US"}[
    záznam.]{lang="en-US"}

2.  [Inicializuj ]{lang="en-US"}[**proc**]{lang="en-US"}[ záznam
    potomka. ]{lang="en-US"}

\- UID a GID, maska signálů, \... se kopírují z rodiče

\- čas využití CPU, \... se nulují

[- PID, PID rodiče se nastaví pro potomka.]{lang="en-US"}

3.  [Zvyš počet odkazů na i-uzel okamžitého adresáře a]{lang="en-US"}

případně na i-uzel změněného kořenového adresáře\...

4.  Zvyš počet odkazů na otevřené soubory v tabulce

souborů.

5.  Přiděl potomkovi tabulku oblastí.

6.  Přiděl potomkovi u oblast a zkopíruj ji z rodiče.

7.  Přidej potomka k procesům sdílejícím oblast textu

(kódu), který vykonává rodič.

8.  [Zdvoj oblast dat a zásobníku.]{lang="en-US"}

9.  Inicializuj HW kontext potomka kopírováním registrů

rodiče.

[10. Nastav stav na ]{lang="en-US"}[**připraven na vykonání**
]{lang="en-US"}[a vlož ho]{lang="en-US"}

do fronty pro plánovač.

[11. Potomkovi vrať hodnotu 0.]{lang="en-US"}

12\. Rodiči vrať hodnotu PID potomka.

\

\

**optimalizace**

\

[**fork**]{lang="en-US"}[ vždycky vytvářel nový adresový prostor pro
potomka]{lang="en-US"}

\

-   [*copy-on-write*]{lang="en-US"}[ (kopíruj při zápisu), System V a
    další]{lang="en-US"}

    -   potomek dostane vlastní kopii tabulky oblastí

    -   [oblast dat a zásobníku (jejich stránky) jsou dočasně í
        ]{lang="en-US"}[*read-only*]{lang="en-US"}[ (přístup jenom pro
        čtení) a označené jako]{lang="en-US"}[
        *copy-on-write*]{lang="en-US"}

    -   [pokusí-li se rodič nebo potomek modifikovat stránku těchto
        oblastí vznikne výjimka]{lang="en-US"}

    -   výjimka se zpracuje tak, že se vytvoří zapisovatelná kopie
        stránky

    -   [zavolá-li potomek ]{lang="en-US"}[**exec**]{lang="en-US"}[ nebo
        ]{lang="en-US"}[**exit**]{lang="en-US"}[, stránkám rodiče se
        vrátí jejich původní ochrana ]{lang="en-US"}

\

-   [systémové volání ]{lang="en-US"}[**vfork()**]{lang="en-US"}[,
    BSD]{lang="en-US"}

    -   [jestli očekáváme po ]{lang="en-US"}[**fork**
        ]{lang="en-US"}[brzké volání
        ]{lang="en-US"}[**exec**]{lang="en-US"}[ můžeme použít nové
        systémové volání
        ]{lang="en-US"}[**vfork**]{lang="en-US"}[()]{lang="en-US"}

    -   [potomek je vykonáván v původním adresovém prostoru rodiče,
        který spí do jejich vrácení]{lang="en-US"}

    -   [když potomek vykoná ]{lang="en-US"}[**exec**]{lang="en-US"}[
        nebo ]{lang="en-US"}[**exit**]{lang="en-US"}[
        ]{lang="en-US"}[jádro adresový prostor rodiči a vzbudí
        ho]{lang="en-US"}

\

\

[**Vyvolání programu --** ]{lang="en-US"}[**exec()**]{lang="en-US"}

\

[program je ve vykonatelném souboru -- ]{lang="en-US"}[**a.out, coff,
elf**]{lang="en-US"}

\

\

1.  [Analyzuj cestu k souboru a zpřístupni soubor,
    i-uzel.]{lang="en-US"}

2.  Ověř, že volající má oprávnění na jeho na jeho vykonání.

3.  Přečti hlavičku souboru a ověř, že soubor je vykonatelný.

4.  Má-li soubor nastaven bit SUID nebo SGID, změň efektivní UID a
    uložený nastavovací UID na UID vlastníka souboru.

5.  [Zkopíruj argumenty a proměnné okolí do adresového prostoru
    jádra.]{lang="en-US"}

6.  [Uvolni paměťové oblasti procesu. Byl-li proces vytvořen službou
    ]{lang="en-US"}[**vfork**]{lang="en-US"}[, vrať adresový prostor
    rodiči.]{lang="en-US"}[ ]{lang="en-US"}

7.  [Vytvoř nový adresový prostor. Je-li oblast textu již aktivní bude
    sdílená, jinak se inicializuje ze souboru.]{lang="en-US"}

8.  Zkopíruj argumenty a proměnné okolí zpátky do uživatelského
    zásobníku.

9.  Inicializuj HW kontext. Počítadlo instrukcí je nastaveno na adresu
    vstupního bodu programu.

\

\

\

[**Ukončení procesu -** ]{lang="en-US"}[**exit()**]{lang="en-US"}[
]{lang="en-US"}

\

\

1.  Ignoruj všechny signály.

2.  Zavři všechny otevřené soubory.

3.  Uvolni okamžitý adresář

4.  Uvolni, je-li změněný kořenový adresář.

5.  Uvolni přidělené paměťové oblasti.

6.  [Zapiš statistiky o využívání prostředků a parametr
    ]{lang="en-US"}[**stav**]{lang="en-US"}[ ]{lang="en-US"}[do
    záznamu]{lang="en-US"}[ ]{lang="en-US"}[**proc.**]{lang="en-US"}

7.  [Změň stav na
    ]{lang="en-US"}[**mátoha**]{lang="en-US"}[.]{lang="en-US"}

8.  [PID rodiče všech potomků nastav na 1 -- proces
    ]{lang="en-US"}[**init**]{lang="en-US"}

9.  [Pošli signál skončení potomka SIGCHLD rodiči.]{lang="en-US"}

[10. Je-li rodič spící, vzbuď ho.]{lang="en-US"}

[11. Vykonej přepnutí kontextu pro nový naplánovaný
proces]{lang="en-US"}

[**swtch()**]{lang="en-US"}[.]{lang="en-US"}

\

[po skončení volání ]{lang="en-US"}[**exit()**]{lang="en-US"}[
]{lang="en-US"}[je proces ve stavu
]{lang="en-US"}[**mátoha**]{lang="en-US"}[ a obsazuje záznam
]{lang="en-US"}[**proc**]{lang="en-US"}

\

\

\

\

\

[**Očekávaní skončení potomka -**
]{lang="en-US"}[**wait()**]{lang="en-US"}

\

1.  [Chyba, nemá-li proces potomky.]{lang="en-US"}

2.  [Má-li potomka mátohu, vyber jednoho z nich, připočítej využití
    prostředků rodiči, uvolni záznam ]{lang="en-US"}[**proc**
    ]{lang="en-US"}[vrať PID potomka a stav skončení.]{lang="en-US"}

3.  Jinak přejdi do stavu spící do příchodu signálu SIGCHLD.

\

\

\

\

\

\

\

\

\
