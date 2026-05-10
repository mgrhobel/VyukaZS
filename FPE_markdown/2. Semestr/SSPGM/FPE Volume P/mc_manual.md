---
title: "mc_manual.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/FPE Volume P/mc_manual.pdf"
date: 2009-01-27
type: PDF (text-based)
---

1

Midnight Commander Meta+c – Rychlé vkládání cesty.

1.1

Klávesové zkratky

Klávesové zkratky v mc jsou tvořeny kombinací Ctrl a něco nebo META a následně něco.
Klávesa META v tomto případě závisí na typu
terminálu. Pokud je váš terminál (viz příkaz
shellu „echo $TERMÿ) Linux, potom metaklávesou je ESC nebo ALT.
Klávesové kombinace mohou na nového
uživatele působit poněkud zvláštně, neboť
mnohé nefungují obvyklým způsobem. Vždy
se nemusí jednat pouze o jeden jediný stisk,
ale o sekvenci, tedy např. zkratka pro vyhledávání známá z DOSu ALT+F7 (držím ALT
a současně stisknu F7) v mc není, ale rychlé
vyvolání dialogu pro vyhledávání se provede
stiskem ESC, puštěním ESC a poté stiskem klávesy ?, tedy vzhledem k rozložení americké či
české klávesnice přesněji Shift+odpovídající
klávesa :) Aby to nebylo zase tak úplně jednoduché podobnou sekvencí se vkládají i další
příkazy, ale tentokráte mohou být sekvence
startovány nějakou jinou klávesovou kombinací.
V následujícím textu jsou kombinace kláves vždy spojeny plusem a sekvence mezerou,
u kombinací s Meta si musíte vyzkoušet zda
na terminálu je povel volaný sekvencí ESC a
klávesy nebo kombinací ALT+klávesa.

1.2

+ – Označení souborů, pokud se před filtr
vloží znak / potom lze označit adresáře.
\ – Odznačí skupinu (opačný povel k předchozímu).
F10, Shift+F10 – Ukončení Midnight Commanderu. Při ukončení F10 se v shellu
objevíte v adresáři ze kterého byl mc
vyvolán. Při Shift+F10 to bude poslední aktuální adresář.

1.3

Adresářové panely

TAB, Ctrl+i – Přepínání mezi panely.

1.5

Meta+g, Meta+r, Meta+j – Skok na první,
prostření nebo poslední soubor v panelu.

Ctrl+h, Backspace – Vymaže předcházející
znak.

Ctrl+\ – Vyvolání hot-listu adresářů.
Pohyb v adresáři

Ctrl+d, Del – Vymaže znak na kterém stojí
kurzor.

• ↑, Ctrl+p – Přesune kurzor o řádek výše v panelu souborů.

F3, Shift+F3 – Zobrazení obsahu vybraného souboru. Pokud se stiskne
Shift+F3 je soubor zobrazen bez jakéhokoli formátování.

• End, Meta+> – Přesune kurzor na
poslední řádek.
• PageUp, Ctrl+v – Přesune kurzor
o stránku dolů.

Meta ! – Filtrovaný pohled, zajímavý příkaz, protože se mi jeho význam nepodařilo objevit :)

F7 – Vytvoření adresáře.
F8 – Mazání souborů nebo adresářů.

Ctrl+e – Jde na konec řádky za vložený text.

Meta+t – Přepíná mezi různými prohlížecími
módy.

• Home, Meta+< – Přesune kurzor
na první řádek v panelu.

F6 – Přejmenování nebo přesun. Akci lze
kdykoliv zrušit stiskem Ctrl+c nebo
ESC.

Ctrl+a – Jde na začátek řádky.
Ctrl+b, Ctrl+f nebo ← a → –
Slouží
k pohybu v zad nebo před o jeden
znak.

F2 – Vyvolá uživatelské menu, kde mohou
být předdefinovány různé příkazy.

Ctrl+x s – Vytvoří symbolický odkaz na
daný soubor či adresář. Název souboru
začíná znakem „@ÿ a název adresáře
„~ÿ .
Rozdíl mezi pevným a symbolickým odkazem je ten, že symbolický odkaz je jenom linka, která se tváří jako soubor a
ukazuje na cíl a pevný odkaz je samostatný soubor, ale pokud např. obsah
jednoho ze souborů spojených pevnou
linkou změníte změní se i obsah toho
druhého.

Pohyb po příkazové řádce

Ctrl+s, Meta+s – Rychlý pohyb v adresáři
podle názvu souboru.

• ↓, Ctrl+n – Přesune kurzor o řádek dolů.

Ctrl+x l – Vytvoří pevný odkaz na daný
soubor či adresář.

Meta+p, Meta+n – Slouží pro pohyb v historii příkazové řádky. Je to ekvivalent
kurzoru v bashi nebo Ctrl+E v DOSovských commandrech.

Insert, Ctrl+t – O(d)značení vybraného
souboru.

F1 – Vyvolání helpu.

F5 – Dialog pro kopírování, filtr pro soubory
má stejné zákonitosti jako v bashi.

Ctrl+x p, Ctrl+x Ctrl+p – Zkopíruje název cesty na řádek. Kombinace fungují
podobně jako v předchozím případě.

Meta+h – Zobrazí historii příkazové řádky
nebo menu

Souborové menu

F4 – Vyvolá editor s označeným souborem
a to buď vi, jiný nadefinovaný editor
nebo interní editor.

Ctrl+x t, Ctrl+x Ctrl+t – Zkopíruje název označeného souboru nebo souboru
na kterém byl naposled kurzor na řádek a to v prvním případě z právě
použitého panelu nebo z předchozího
v druhém.

• PageDown, Meta+v – Přesune kurzor o stránku nahoru.
Meta+o – Zobrazí obsah vybraného adresáře
ve vedlejším panelu.
Ctrl+PageUp, Ctrl+PageDown –
Funguje
pouze v Linuxové konzoly a provede
změnu adresáře na „. .ÿ.
Meta+y – Vrátí se o jednu zpět v historii pohybu adresáři. Ekvivalentní ke stisku
znaku > v pravém rohu panelu.

Meta+w – Uloží napsaný text do bufferu.
Ctrl+y – Vloží napsaný text z bufferu na příkazovou řádku.
Ctrl+k – Přesune text od kurzoru včetně do
konce řádku do bufferu.
Meta+Ctrl+h, Meta+Backspace –
slovo před kurzorem.

1.6

Vymaže

Ostatní klávesové zkratky

Enter – Provádí změnu adresáře, vložení povelu z příkazové řádky a nebo pokud daný soubor určitou příponu nebo
vlastnost. Např. může být spouštěcí
nebo třeba vyvolá nějaký externí prohlížeč, atd.
Ctrl+r – Překreslí panely a všechny informace.
Ctrl+x c – Spustí obdobu příkazu chmod
(změna práv souboru) daného nebo
označeného souboru.
Ctrl+x o – Spustí o obdobu příkazu chown
(změna vlastníka).

Meta+u – Jde na následující hodnotu v historii pohybu adresáři.
Historii pohyby adresáři lze zobrazit
klepnutím myši na znak V umístěném
v vpravo nahoře obou panelů.

Ctrl+x i – Nastaví opačný panel do informačního módu.

1.4

Ctrl+x ! – Nastaví opačný panel tak, že
zobrazuje výstup z externího programu.

Příkazová řádka

Meta+Enter – Zkopíruje název souboru na
příkazovou řádku.
Ctrl+Enter – Jako předtím, ale funguje
pouze v Linuxové konzoly.
Meta+Tab – Doplňování názvů souborů, adresářů, příkazů, proměnných a host
jmen. Funguje podobně jako tabelátor
v bashi.

Ctrl+x q – Nastaví opačný panel do módu
k rychlému prohlížení.

Ctrl+x h – Přidání aktuálního adresáře adresáře do hot-listu.
Meta+? – Vyhledávání souboru případně
souboru s určitým obsahem.
Ctrl+o – Vypne panely mc a zobrazí shell,
ve kterém mohou být vidět výstupy
z předcházejících programů.

