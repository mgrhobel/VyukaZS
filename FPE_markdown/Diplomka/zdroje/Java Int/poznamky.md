---
title: "poznamky.txt"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/zdroje/Java Int/poznamky.txt"
date: 2010-02-02
type: TXT
---

Celosvetove problemy pri internacionalizaci
- latinske (anglictina, nemcina, francoustina, span., atd.) a puvodem nelatinske-skripty-arabstina, cinstina, japonstina, atd.) jazyky se od sebe hodne lisi - maji znaky uplne odlisne. (symbolika)

- 2 latinske jazyky se take mohou lisit - napr. cestina a anglictina. (symbolika)
napr. diakritika

- merici jednotky jsou velmi odlisne, 
ruzne kalendare - Gregoriansky, Maysky, Islamsky,
dokonce i dane casy, kdy zacina tma a kdy den.

- ruzne barvy mohou v ruznych zemich pusobit jinak (barvy)
smrt = cerna v zapadnich zemich, = bila v asijskych zemich, purpurova = v latinsko-americkych zemich.

- ruzna cisla, ruzne symboli (symbolika)
nestesti = 13 v USA, 7 v HongKongu

-ruzne razeni slov (symbolika)
Spanelstina, - je ulozeno jako samostatne pismeno mezi c a d
cestina, - je ulozeno jako samostatne pismeno mezi h a i
Romanske jazyky - 2 ruzna pismena - tzn. sortovani mezi cg a ci

- fyzicka odlisnout lidi (ergonomie)
ne az tak moc zase.

- (pouzite uzivatelske rozhrani)
Napr. se cte text zleva doprava atd.
Lide jsou zvykli 


Planovani

* Vymezeni zemi, pro ktere bude aplikace pouzitelna je treba delat na zacatku navrhu.
- konretne napr. pro nelatinske a latinske jazyky jsou velke implementacni rozdily. Vubec nepodporuji znakovou sadu atd.
- zateze: novy design a implementace -> prekroceni odhadu pro release projektu, vetsi produkcni naklady

* Je mozne internacionalizovat pouze cast aplikace?
- je napr. mozne vynechat i18n japonskeho kalendare - bylo by to velmi narocne a zase tolik to neni potrebne.


Customizovana lokalizace
- alternativa k inernacionalizaci
- pri pridani nove featury, tato featura potrebuje byt dodana do vsech verzi, ktere se maji lokalizovat (ma byt internacionalizovana). 

pokud se pouzije: vsechny zdrojove kody a binarky podporuji jakekoliv jazyky - bez nutnosti kompilace. - spise popisuju I18N.

pokud se customizace nepouzije: urcity bug se mi zreplikuje na jednotlive lokalizacni verze aplikace - pro kazdou verzy musim, zvlast testovat a spravovat -> velka nevyhoda.

jak vypada cust, int v praxi??

I18N neni featura - je to jedna z hlavnich casti cele aplikace.
- zakaznici se nebudou ptat, zda je v programu internacionalizace, sou zvedavi pouze na svuj konkretni jazyk. Proto je to soucat aplikace ale neni to featura.

Lokalizace
- preklad textu
- oddeleni jazykove zav. dat od zdroj. kodu -> dulezite pro prekladatele, aby se dobre orientovali v tom, co maji prelozit.

multi-jazykove aplikace
- moznost zvolit vice nez 1 jazyk v runtimu, a prepinat se v nich.
- pr. server ve svicarsku (ma 4 oficialni jazyky) - server predem nemuze rozhodnout, ktery jazykovy klient jej bude vyuzivat.

Vyhody jazyka Java v internacionalizaci
- jiz od pocatku (ve verzi 1.0) je zahrnut Unicode.
- moznost prechaezet od ruznych znakovych sad na unicode.
- okolo 100 podporovanych lokalu
- podpora obou smerneho cteni znaku - napr. i Arabskeho.
- mnoho featur k podporu i18n zdarma.
- moznost pridavat nove jazyky a zeme - nove lokaly.



ResourceBUndles
- je mozne ulozit jakoukoliv kompoentu do PropertyListBUndlu. POte ji nahrat..tzn. mit napr. jiz prelozeny label s prelozenych abbrechen v nemcine a s prelozenym cancel v AJ. Nemusime jen ukladat objekt typu strig.








