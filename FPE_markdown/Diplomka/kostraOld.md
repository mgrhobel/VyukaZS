---
title: "kostraOld.txt"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/kostraOld.txt"
date: 2010-03-20
type: TXT
---

doplnit obzory
- jake jsou zvlastnosti v uzivatelskych rozhranich odlisnych zemi/narodu.
- jakou znakvou sadu pouziva MPA, pokud by se pouzil UNICODE, pak by srbske lokali nebyli problem?
- Aplikace musi komunikovat s ostatnimi aplikace, ktere mohou pracovat s jinym typem kodova. Proto musi nase aplikace umet prevest tyto znaky (rozpoznat je) z jednoh kodovani do druheho. Neni toto uz vyreseno pomoci XML? - mozna to xml resi az dnes, ale stale jsou tu jeste starsi aplikace, ktere pouzivaji ISO.
- Pokud se nepouzije xml, pak Input/OutputStreamReader tutuo konverzi narozdil od Readeru/Writeru umi?
-co je classloader
- vice pochpöpit vyznam promennych v resource bundlech a pouziti {0} - jsou to totozne pripady, nebo pro resourceBunldy zadne promenne neexistuji?


Prakticka cast
* Administrace projektu
- Development language urcuje klicovou frazi? Napriklad pro volbe cestiny by bylo namisto none jazyku cestina?


*ExportToDB
- Rozdíl oproti MessageBundle a RepoResourceBundle souborech.
- Proc neni mozne do jedne databaze vyexportovat stejne klice, ktere pochazji z ruzneho kontextu? - K cemu pak tedy contextInfo je?
- export Keys if no value -> je to spravne, co jsem napsal v casti exportToDB?
- DateFormat tab tedy slouzi jenom k lepsi a celkove uprave vsech datumovych vzoru?
	- jak se pozna, kam vlozit nove definovany vzor???

*ImportToDB
- co se stane, pokud se provede import do jine repoDir nez ze ktere byl exportovan.	
- dateFormat import a Common parametry - pracuje snimi nejak?

*Edit phrases
- co je to fráze - jeden text nebo vice veci dohromady?
- jakto e none locale obsahuje anglické texty??
- jak je možné editovat none locale?
- bude možné smazat frázi?

*MessageBundle editor
- pokud je zapotrebi novy jazyk - jak se pridaji nove MessageBundly?

*Repository editor
- pokud by bylo stejne textu v repository a v MessageBundlech -> nacitaly by se stejne oba taby stejne rychle nebo by se repository nacetla rychleji?

- co to znamená, že objekt náleží vlastníkovi? co to znamená, že jsou pod pluginem AS=LAB?

- pokud se provede repoInit, pak mi to prepise moje preklady - nahraji se mi pouze defaultni none locale resourcebundly. Je nejaka moznost jak ty preklady neztratit?


- jdou pøidávat klíèe?


*Filtrovani zobrazovanych polozek v RessourceBundle editorech
- je hlavni myslenou to, ze dane objekty nechci v ediotru zobrazit - zprehledneni zobrazeni?
- je mozne includovat vsechny polozky, ktere byli excludovany pomoci regularnich vyrazu??
- neni podporovan filtr repository klicu.
- proc se tento filtr dela az za behu, proc se neda nejaky if pri vytvoreni stromu, ze tam nesmi byt test-calsses soubory atd??


* Export do Excel souboru
- v exportu zatím chybí
- jakto ze v repoObjektech jsou casto ulozeny obecne fraze typu Aufenthalt?? V messagebundlech jsou pouzity texty, ktere jsou pouzity vetsinou na jednom miste??
- distionary se neexportuje, ten sloouzi jen programatorovi, aby mohl prelozit cast textu nez se daji prekladateli. Ve forme komentare mu pak napsat, ze muze pouzit tyto preklady pro dalsi fraze ano?

*Import z excelu do databaze
- jak funguje context info - jak s nim muze v import tabu programator konkretne pracovat?

- jaky maji prepinace smysl, maji jenom informativni charakter, nebo se skutecne mohou pri praci vyuzit - pokud ano, kdy - uvest konkretni priklad.


Pismo viz brucker
Psat to obecne, pote udelat jednu kapitolu o Jazyku Java.
- png obrazky


Co jsou Locale-Sensitive Sevices SPI , popripade Locale - Sensitive String operations??
- zahrnout je take do diplomky?
- scope of Locale

Mam popisovat, jak funguje v Jave napr. getBundle - to ze musi byt MessageBundly na classpath?

---------------------------------------------------------------
Seznam pouzitych odbornych vyrazu
Aplikacni logika

Plugin

Uzivatelske rozhrani

Znaková sada (kódování)
- illustrates the one-to-one mapping between a character and the computer’s
bit representation

Regulární výraz
- Pøedstavuje vzor (masku), pomocí níž mùžeme vyhledávat a mìnit text. (øeèeno laikem)

IME
Editor or mechanism that enable the typing of all character sets by using a limited number of keys.

Softwarová lokalizace

Deprecated

locale-sensitive

GUI

znakovy repertoar, znakova sada - wiki

font, rodina fontù.

latinka

endianita

customer

repository

repoOwner

verzovací systém.

log

??fráze??

objektová databáze


Úvod DP
- proc jsem si praci vybral.???
- cil prace
- popis kapitol. 

1. Uvod k internacionalizaci
Úvod (Introduction)
- Duvody pro internacion. (v textu)
- Internacionalizace, Lokalizace, Globalizace
- Proces Int., Proces Lokalizace

Zdroje
- i18n - Introduction
- Steffen gross - Introduction
- Java Int - Introduction


2. Jazyk Java a Internacionalizace
- duvody pro vuber javy (v textu)
- vyhoda jazyka java oproti ostatnim jazykum pri intrenacionalizaci.


Obecne lokalizacni metodiky

(A)Vysvetleni pojmu Locale (Nastaveni Locale)

zdroje
- Sun Developer Network
- Understanding Locale

Implementacni veci
- Java Int
- java.sun.com

B)

Oddeleni jazykove zavyslich dat od zdrojovych kodu (pomoci Ressource Bundlu)
- i18n - Providing localized resources
- Sun Developer Network - Localization with ResourceBundles

- java.sun.com
- Java Internationalization chapter 4
- !! hlavne pospat neco podobneho co je v zaverecne praci.pdf v uvodu v I18N.

C)
Formtáovaní textù v rùzných jazycích

*Formátování data a èasu
- Java Int.
- java.sun.com
- i18n

* Formátování èíselných typù


* Formátování textù


E)
Problematika specialnich znaku
- Unicode
- Java Int.  chapter 6


F)
Novinky v Java Internacionalizaci
- Java Int. - chapter 12
 


3. Obecne o aplikaci MITToolkit, ktera je soucasti MPA

A) Aplikace MPA - na co se ptal ucitel.
- co dela MPA
- proc je zapotrebi internaconalizovat MPA, protoze se z puvodniho pouze nemecka rozrostla dale do dalsich zemi.
- spojitos s MITem, napr. (zduraznit rozdil, ze muj MIT je pro jakoukoliv oblast XX Medical v nazvu MPA)
- vychozi none jazyk:
V aplikaci MPA se vychází z nìmeckého pøekladu (sloupec none locale), tzn. že všechny texty musí být nejdøíve pøeloženy do nìmèiny a až poté jsou tyto texty pøeloženy do dalších jazykù.

*v apliakce MPA se vsechny texty ulozeny ve dvou mistech. 1. je messgeBundle.proeprties soubory. Druhe je RepoResourceBundle objekty z objektove databaze.

Proc nejsou vsechny texty ulozeny v RepoResourceBundlech?
- texty ktere se npoj s zadnym objektem neni treba ukladat do objektove databaze. Techto textu je vsak velke mnozstvi a tak by zbytecne zahlcovali databaazi. Pro tyto texty je tedy vyhodnejsi pouzit MessageBundle soubory.

- vlastník a plugin.



MPA specialne:
- jak pracuje s resourceBundlama - MPAResourceBundle.
- srbske locale.
- none locale, aplikace MPA vychází z nìmeckého jazykového pøekladu.
- weekdays - DefaultSettings


B)
Spusteni, minimalni konfigurace

4.
Popis funkcionality MITToolkitu
- Administrace jednotlivych lokalizacnich projektu 
!!!!!!!!!!!!!!!!!!!!!Co je mozna treba doplnit:!!!!!!!!!!!!!
	- databazovy pristup. - nemecka fraze a te jsou prirazeny ostatni 	vyexportovane preklady.	

	- popis jednotlivych prvku kazdeho projektu - hsqldb.skript, vsechny xml 	
	soubory, ktere kazdy projekt obsahuje.
	- ktere soubory jsou spolecne vsem projektum
	- databazovy model - kdyz zbyde cas.	

- Export vsech textu z MPA do databaze dle zadanych parametru
	- co to vlastne je - zadani
	- reseni:
	- rozdeleni na export MessageBundlu a RepoResourceBundlu, dale DateFormat 		export.
	- popis jednotlivych parametru, spolecne a specialni.
	- vyhody, nevyhody
	+ DateFormat tab
	
- Import vsech prelozenych frazi z databaze do MPA dle zadanych parametru
	- zadani

- editace frazi v databazi
	
- MessageBundle a repository tab - popsat jak pracuji a k cemu vlastne slouzi.
	- file a repo filtr.!!!!!!!!!!!!!

- export z databaze do souboru ve formatu Excel pro prekladatele

- Import do databaze ze souboru prelozeneho prekladatelem.

- Dalsi nastroje aplikace MITToolkit

- Editace exportovacich/importovacich pravidel, pouzitych pro automaticke filtrovani frazi behem exportu/importu.
 -> to jeste nemam.

5. Graficky navrh a implementace
- popis jak jsem navrhoval grafiku
- nejaky GUI tutorial.
- mozna vubec nezarazovat - udelat az na konci. Podle rozshalost a kvality se rozhodnout, zda tuto cast zaradit do diplomky nebo ne.

- Java Int. chapter 9

- Rozdil mezi Swing a AWT, dobre pospane v Understanding Locale in the Java, Enabled Script Support.

6.
Srovnani s postupy pred a po. - Zhodnoceni aplikace MITToolkit a jeji prinos.
- porovnani teorie - pouzivani resource bundlu XX muj MITToolkit.
- jeho vyhody databazoveho pristupu, proc jsem ho vlastne pouzil.
- ??nevyhody databazoveho pristupu??


- Ucelena prace, ktera se da omezit pouze na pozadovane casti.
- pokud je v urcite casti aplikace MPA vice stejnych frazi (pod ruznymi klici), pak neni treba prekladat fraze znovu a znovu stejne. V databazi je vzdy kazda takova fraze obsazena pouze jedenkrat a je k ni pripojena cesta na vsechny vyskyty. 
- moznosti filtrovani frazi podle uzivatelovych preferenci.
	- neni treba davat prelozene fraze, ktere akorat zneprehlednuji soubor a zvysuji jeho velikost. - v mitu pak predam pouze ty fraze ktere chci.


- ve frazich je mozne efektivne editovat MB - nemusim se prepinat mezi soubory, vse je videt v jednom umisteni. Imoprtem pote vsechny zmeny naraz ulozit.

	- nemusi rucne prepisovat texty - pokud byl prekladateli predan zvalstni soubor (napr. excel)
	- pokud byl prekladateli predany resourcebundle soubory, pak neni nutne prekladatele nic ucit, dale jsou zde vsechny nevyhody oproti editoru

	- v pripade editoru Nevyhody editoru oproti nasemu pristupu v prekladu??
		- je nutne prekladatele ucit v editoru
		- import se neprovadi automaticky do MPA ale do databaze, takze je 			mozne napr. spustit jeste jednou.
		- mozne zjistit hlavni fraze a ty pak prelozit jednou pri importu se automaticky naleznou vsechny prislusne fraze a neni tak nutne ty stejne fraze delat znovu a znovu.


- Poznamenat, ze zvoleny jazyk je v MPA vzdy nemcina. Tzn. je uplne jedno co zvolym. Toto by bylo treba rozlisit v pripade, ze by se MITTolkit stal vice obecnejsi - tzn. byl by pripraven pro jakykoliv program a tedy i pro jakykoliv vychozi jazyk, ktery poutiva.


- vykonnost PC XX MIT - jak urychlit praci s MITem, napr. priradit mene zatizene jadro? - mozna uz to java pouziva a ani o tom nevim. - zjistit to (vlakna).
- mozne problemy (neni uplne blbu vzdorny)
-> synchronni prenos - aby nebylo mozno zmenit bundle, behem prace s MITem.
-> naimportuje se spatny excel file. 
-atd.



K Testu:

Pokud zadám rootDir (vsechno), pak mi to najde nebo nenajde správnou RepoResourceBundle pri importu? Ucel, je to pomale prochazet vsechny repoDir a tedy nutne specifikovat urcitou cestu?


Výhoda exportu??
 - nemusi rucne prepisovat texty??


RepoRsourceBundle XX MessageBundle pouziti
- pro ruzne hodnoty instance ruzne hodnoty -> pouziju repoResourceBundle
- pro stejne hodnoty a ruzne ruzne nebo stejne instance -> messageBundle

Pamet
- pokud bych mel stejne hodnoty napr. titulek, ktery je spolecny 100 prvkum - pak by tyto hodnoty zabirali zbytecne misto -> lepsi je je pouzit v messageBundlech.

- naopak ruzny hodnoty je treba 
