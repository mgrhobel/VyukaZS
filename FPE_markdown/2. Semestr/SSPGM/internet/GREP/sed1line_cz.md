---
title: "sed1line_cz.html"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/internet/GREP/sed1line_cz.html"
date: 2009-04-27
type: HTML
---

    -------------------------------------------------------------------------
    UZITEČNÉ JEDNOŘÁDKOVÉ SKRIPTY PRO SED (Unixový stream editor)  29.12.2005

    Sestavil Eric Pement - pemente[at]northpark[dot]edu             verze 5.5 
    Přeložil Josef Moudřík - j.moudrik[at]seznam[dot]cz

    Nejnovější verze tohoto souboru (v Angličtině) je obvykle na:
       http://sed.sourceforge.net/sed1line.txt
       http://www.pement.org/sed/sed1line.txt

    Tento soubor je také dostupný v ostatních jazycích:
      Čínsky      - http://sed.sourceforge.net/sed1line_zh-CN.html
      Czechsky    - http://sed.sourceforge.net/sed1line_cz.html       
      Holandsky   - http://sed.sourceforge.net/sed1line_nl.html
      Francouzsky - http://sed.sourceforge.net/sed1line_fr.html
      Německy     - http://sed.sourceforge.net/sed1line_de.html

      Portugalsky - http://sed.sourceforge.net/sed1line_pt-BR.html


    MEZERY V SOUBORU:

     # za každý řádek přidá volný řádek
     sed G

     # za každý řádek přidá volný řádek a navíc zajistí, že nikde
     # nebudou dva volné řádky za sebou
     sed '/^$/d;G'

     # za každý řádek přidá dva volné řádky
     sed 'G;G'

     # odstraní každý druhý řádek
     sed 'n;d'

     # vloží prázdný řádek před každý řádek, který obsahuje "regex"
     sed '/regex/{x;p;x;}'

     # vloží prázdný řádek za každý řádek, který obsahuje "regex"
     sed '/regex/G'

     # vloží prázdný řádek před i za každý řádek, který obsahuje "regex"
     sed '/regex/{x;p;x;G;}'

    ČISLOVÁNÍ:

     # očísluje všechny řádky v souboru (zarovnání vlevo). Použití tabulátorů
     # (viz. poznámka o \t níže) zajistí odsazení.
     sed = filename | sed 'N;s/\n/\t/'

     # očísluje řádky v souboru (čísla vlevo, zarovnání vpravo)
     sed = filename | sed 'N; s/^/     /; s/ *\(.\{6,\}\)\n/\1  /'

     # očísluje řádky v souboru jen pokud řádek není prázdný
     sed '/./=' filename | sed '/./N; s/\n/ /'

     # spočte řádky (namísto "wc -l")
     sed -n '$='

    PŘEVODY TEXTU A NAHRAZOVÁNÍ:

     # V UNIXu: převede DOSové nové řádky (CR/LF) na Unixový formát.
     sed 's/.$//'               # předpokladá že řádky konči CR/LF
     sed 's/^M$//'              # v bash a v tcsh stiskni Ctrl-V, poté Ctrl-M
     sed 's/\x0D$//'            # pracuje s ssed, gsed 3.02.80 a vyšší

     # V UNIXu: převede Unixové nové řádky (LF) na DOSový formát.
     sed "s/$/`echo -e \\\r`/"            # příkazová řádka v ksh
     sed 's/$'"/`echo \\\r`/"             # příkazová řádka v bash
     sed "s/$/`echo \\\r`/"               # příkazová řádka v zsh
     sed 's/$/\r/'                        # gsed 3.02.80 a vyšší

     # V DOSu: převede Unixové nové řádky (LF) na DOSový formát.
     sed "s/$//"                          # 1. způsob
     sed -n p                             # 2. způsob

     # V DOSu: převede DOSové konce řádek (CR/LF) na Unixový formát.
     # Funguje pouze s editorem sed z UnxUtils, verze 4.0.7 a vyšší. Verze
     # UnxUtils lze zjistit přepínačem "--text", viz. tez přepínač "--help".
     # Jinak převod DOSového nového řádku na Unix pomocí sedu nejde. Užijte "tr".
     sed "s/\r//" infile >outfile         # UnxUtils sed verze 4.0.7 ci vyšší 
     tr -d \r < infile >outfile            # GNU tr verze 1.22 nebo vyšší

     # smaže prázdné místo (mezery, tabulátory) na začátku každé řádky
     # zarovná celý text vlevo
     sed 's/^[ \t]*//'                    # viz. poznámka '\t' níže
     
     # smaže prázdné místo (mezery, tabulátory) na konci řádky
     sed 's/[ \t]*$//'                    # viz. poznámka '\t' níže

     # smaže prázdné místo (mezery, tabulátory) ze začátku i z konce
     sed 's/^[ \t]*//;s/[ \t]*$//'

     # vloží 5 mezer na začátek každé řádky
     sed 's/^/     /'

     # zarovná celý text vpravo, na celkovou šířku 79 znaků ve sloupci
     sed -e :a -e 's/^.\{1,78\}$/ &/;ta'  # zarovná na 78 znaků + 1 mezera

     # vycentruje celý text do středu 79 znakového sloupce. První způsob
     # počítá mezery na začátku a na konci jako normální znak, druhým
     # jsou mezery na začátku odstraněny.
     sed  -e :a -e 's/^.\{1,77\}$/ & /;ta'                     # 1. způsob
     sed  -e :a -e 's/^.\{1,77\}$/ &/;ta' -e 's/\( *\)\1/\1/'  # 2. způsob

     # prohodí (najde a nahradí) "foo" a "bar" na každé řádce
     sed 's/foo/bar/'             # nahradí jen první výskyt na řádce
     sed 's/foo/bar/4'            # nahradí jen čtvrtý výskyt na řádce
     sed 's/foo/bar/g'            # nahradí všechny výskyty na řádce
     sed 's/\(.*\)foo\(.*foo\)/\1bar\2/' # nahradí předposlední výskyt
     sed 's/\(.*\)foo/\1bar/'            # nahradí poslední výskyt

     # nahradí "foo" výrazem "bar" JEN na řádkách, které obsahují "baz"
     sed '/baz/s/foo/bar/g'

     # nahradí "foo" vy$razem "bar" JEN na řádkách, které neobsahují "baz"
     sed '/baz/!s/foo/bar/g'

     # nahradí "scarlet", nebo "ruby", nebo "puce" výrazem "red"
     sed 's/scarlet/red/g;s/ruby/red/g;s/puce/red/g'   # větsina sedů
     gsed 's/scarlet\|ruby\|puce/red/g'                # pouze GNU sed

     # vypíše soubor od konce (namísto "tac")
     # chyba (vlastnost) v editoru HHsed verze 1.5 smaže prázdné řádky
     sed '1!G;h;$!d'               # 1. způsob
     sed -n '1!G;h;$p'             # 2. způsob

     # vypíše řádky od konce (namísto "rev")
     sed '/\n/!G;s/\(.\)\(.*\n\)/&\2\1/;//D;s/.//'

     # spojí každé dvě řádky (jako "paste")
     sed '$!N;s/\n/ /'

     # pokud řádka končí zpětným lomítkem připojí následující řádku
     sed -e :a -e '/\\$/N; s/\\\n//; ta'

     # pokud řádka začíná rovnítkem připojí ji k předchozí řádce
     # a nahradí "=" mezerou
     sed -e :a -e '$!N;s/\n=/ /;ta' -e 'P;D'

     # přidá čárky k číslům - změní "1234567" na "1,234,567"
     gsed ':a;s/\B[0-9]\{3\}\>/,&/;ta'                     # GNU sed
     sed -e :a -e 's/\(.*[0-9]\)\([0-9]\{3\}\)/\1,\2/;ta'  # ostatní sedy

     # přidá mezery k čislům - změní "1234567" na "1 234 567"
     gsed ':a;s/\B[0-9]\{3\}\>/ &/;ta'                     # GNU sed
     sed -e :a -e 's/\(.*[0-9]\)\([0-9]\{3\}\)/\1 \2/;ta'  # ostatní sedy
     
     # přidá čárku k čislům s desetinnou čárkou a znaménkem mínus (GNU sed)
     gsed -r ':a;s/(^|[^0-9.])([0-9]+)([0-9]{3})/\1\2,\3/g;ta'

     # přidá prázdnou řádku po každé páté řádce (po 5, 10, atd.)
     gsed '0~5G'                  # pouze GNU sed
     sed 'n;n;n;n;G;'             # ostatní sedy

    VYPSÁNÍ URČITÝCH ŘÁDEK:

     # vypíše prvních 10 řádek v souboru (namísto "head -n 10")
     sed 10q

     # vypíše první řádku souboru (namísto "head -n 1"
     sed q

     # vypíše posledních 10 řádek v souboru (namísto "tail")
     sed -e :a -e '$q;N;11,$D;ba'

     # vypíše poslední 2 řádky souboru (namísto "tail -n 2")
     sed '$!N;$!D'

     # vypíše poslední řádku souboru (namísto "tail -n 1")
     sed '$!d'                    # 1. způsob
     sed -n '$p'                  # 2. způsob

     # vypíše předposlední řádku v souboru
     sed -e '$!{h;d;}' -e x             # pro 1-řádkový soubor vypíše prázdnou řádku
     sed -e '1{$q;}' -e '$!{h;d;}' -e x # pro 1-řádkový soubor vypíše řádku
     sed -e '1{$d;}' -e '$!{h;d;}' -e x # pro 1-řádkový soubor nevypíše nic
            
     # vypíše pouze řádky, které obsahují "regexp" (namísto "grep")
     sed -n '/regexp/p'           # 1. způsob
     sed '/regexp/!d'             # 2. způsob

     # vypíše pouze řádky, které NEobsahují "regexp" (namísto "grep -v")
     sed -n '/regexp/!p'          # 1. způsob, viz. zadání
     sed '/regexp/d'              # 2. způsob, kratší kod

     # vytiskne řádku před tou, která obsahuje "regexp"
     sed -n '/regexp/{g;1!p;};h'

     # vytiskne řádku po té, co obsahuje "regexp"
     sed -n '/regexp/{n;p;}'

     # vytiskne číslo řádky obsahující "regexp", řádku před ní, jí samotnou
     # a řádku po ní (podobně "grep -A1 -B1")
     sed -n -e '/regexp/{=;x;1!p;g;$!N;p;D;}' -e h

     # grep pro AAA, BBB a CCC (v libovolném  pořadí)
     sed '/AAA/!d; /BBB/!d; /CCC/!d'

     # grep pro AAA, BBB a CCC (v tomto pořadí)
     sed '/AAA.*BBB.*CCC/!d'

     # grep pro AAA, nebo BBB, nebo CCC (namísto "egrep")
     sed -e '/AAA/b' -e '/BBB/b' -e '/CCC/b' -e d    # větsina sedů
     gsed '/AAA\|BBB\|CCC/!d'                        # pouze GNU sed

     # vypíše odstavec obsahující AAA (odstavce jsou odděleny prázdnými řádkami)
     # HHsed verze 1.5 musí mit 'G;' po 'x;' v následujících třech skriptech
     sed -e '/./{H;$!d;}' -e 'x;/AAA/!d;'

     # vypíše odstavec obsahující AAA, BBB a CCC (v libovolném pořadí)
     sed -e '/./{H;$!d;}' -e 'x;/AAA/!d;/BBB/!d;/CCC/!d'

     # vypíše odstavec obsahující AAA, nebo BBB, nebo CCC
     sed -e '/./{H;$!d;}' -e 'x;/AAA/b' -e '/BBB/b' -e '/CCC/b' -e d
     gsed '/./{H;$!d;};x;/AAA\|BBB\|CCC/b;d'         # pouze GNU sed

     # vypíše jen řádky s 65 znaky, nebo víc
     sed -n '/^.\{65\}/p'

     # vypíše jen řádky s méně než 65 znaky
     sed -n '/^.\{65\}/!p'        # 1. způsob, viz. zadání
     sed '/^.\{65\}/d'            # 2. způsob, kratší zápis

     # vypíše soubor od "regexp" do konce
     sed -n '/regexp/,$p'

     # vypíše část souboru dle čísla řádek (řádky 8-12, včetně)
     sed -n '8,12p'               # 1. způsob
     sed '8,12!d'                 # 2. způsob

     # vypíše řádku číslo 52
     sed -n '52p'                 # 1. způsob
     sed '52!d'                   # 2. způsob
     sed '52q;d'                  # 3. způsob, rychlé i na velkých souborech
     
     # počínaje 3-tí, vypíše každou sedmou řádku
     gsed -n '3~7p'               # pouze GNU sed
     sed -n '3,${p;n;n;n;n;n;n;}' # ostatní sedy

     # vypíše část souboru mezi dvěma výrazy (včetně)
     sed -n '/Iowa/,/Montana/p'             # pozor na VELKÁ a malá písmena

    MAZÁNÍ VYBRANÝCH ŘÁDEK:

     # vypíše vše AŽ na oblast mezi "Iowa" a "Montana"
     sed '/Iowa/,/Montana/d'

     # smaže duplicitní, po sobě jdoucí řádky ze souboru (namísto "uniq").
     # První řádka v řade duplicitních zůstane, ostatní jsou smazány.
     sed '$!N; /^\(.*\)\n\1$/!P; D'

     # smaže duplicitní řádky nejdoucí po sobě. Pozor na přetečení bufferu,
     # jinak užijte GNU sed.
     sed -n 'G; s/\n/&&/; /^\([ -~]*\n\).*\n\1/d; s/\n//; h; P'

     # smaže všechny řádky výskytující se jednou (namísto "uniq -d")
     # (soubor musí být seřazen)
     sed '$!N; s/^\(.*\)\n\1$/\1/; t; D'

     # smaže prvních 10 řádek v souboru
     sed '1,10d'

     # smaže poslední řádku
     sed '$d'

     # smaže poslední dvě řádky
     sed 'N;$!P;$!D;$d'

     # smaže posledních deset řádek
     sed -e :a -e '$d;N;2,10ba' -e 'P;D'   # 1. způsob
     sed -n -e :a -e '1,10!{P;N;D;};N;ba'  # 2. způsob

     # smaže každou osmou řádku
     gsed '0~8d'                           # pouze GNU sed
     sed 'n;n;n;n;n;n;n;d;'                # ostatní sedy

     # smaže řádky obsahující "pattern"
     sed '/pattern/d'

     # smaže všechny prázdné řádky ze souboru (jako "grep '.' ""
     sed '/^$/d'                           # 1. způsob
     sed '/./!d'                           # 2. způsob

     # pokud je víc prázdných řádek po sobě, smaže je až na první
     # smaže prázdné řádky ze začátku souboru (namísto "cat -s")
     sed '/./,/^$/!d'          # 1. způsob, nenechá mezeru na začátku, 1 u EOF
     sed '/^$/N;/\n$/D'        # 2. způsob, nechá 1 mezeru na začátku, 0 u EOF
     
     # smaže všechny po sobě jdoucí prázdné řádky až na první dvě
     sed '/^$/N;/\n$/N;//D'

     # smaže prázdné řádky na začátku souboru
     sed '/./,$!d'

     # smaže všechny prázdné řádky na konci souboru
     sed -e :a -e '/^\n*$/{$d;N;ba' -e '}'  # běží na všech sedech
     sed -e :a -e '/^\n*$/N;/\n$/ba'        # taktéž, až na gsed 3.02.*

     # smaže poslední řádku všech odstavců
     sed -n '/^$/{p;h;};/./{x;/./p;}'

    SPECIÁLNÍ POUŽITÍ:

     # odstraní formátováni nroff (znak, backspace - pro ztučnění písma)
     # z manuálových stránek.  Příkaz 'echo' může v Unix System V shellu
     # a v bash shellu vyžadovat přepínač -e.
     sed "s/.`echo \\\b`//g"    # dvojité uvozovky jsou v Unixu nutností
     sed 's/.^H//g'             # v bash/tcsh, stiskni Ctrl-V a pak Ctrl-H
     sed 's/.\x08//g'           # hex výraz pro sed 1.5, GNU sed, ssed

     # vypíše hlavičku zprávy pro Usenet/e-mail
     sed '/^$/q'                # smaže vše po první prázdné řádce

     # vypíše tělo zprávy Usenet/e-mail
     sed '1,/^$/d'              # smaže všechno do první prázdné řádky

     # vypíše pole Předmět, ale odstraní úvodní část "Subject: "
     sed '/^Subject: */!d; s///;q'

     # vypíše hlavičku pro návrat zprávy
     sed '/^Reply-To:/q; /^From:/h; /./d;g;q'

     # oddělí hlavičku s e-mailovou adresou 
     # (viz předchozí skript)
     sed 's/ *(.*)//; s/>.*//; s/.*[:<] *//'

     # přidá znak "> " na začátek každé řádky - citace zprávy
     sed 's/^/> /'

     # smaže úvodní "> " ze začátku každé řádky - zrušení citace
     sed 's/^> //'

     # odstraní většinu HTML tagů
     sed -e :a -e 's/<[^>]*>//g;/zipup.bat
     dir /b *.txt | sed "s/^\(.*\)\.TXT/pkzip -mo \1 \1.TXT/" >>zipup.bat

    TYPICKÉ POUŽITÍ: Sed na vstupu příjímá jeden nebo více přikazů a aplikuje
    je postupně na každou řádku vstupu. Poté co je řádka zpracována je
    předána na standartní výstup. Předchozí přiklady předpokládají vstup ze 
    standartního vstupního zařízení (roura, apod...). Jeden, nebo více
    souborů mohou být specifikovány na přikazové řádce, pokud vstup není ze
    stdinu. Výstup je odeslán na stdout.

     cat filename | sed '10q'        # na vstupu roura
     sed '10q' filename              # to samé, bez cat
     sed '10q' filename > newfile    # výstup přesměrován na disk

    Pro dalši informace o syntaxi doporučujeme knihy: 
    sed & awk, 2nd Edition - Dale Dougherty and Arnold Robbins (O'Reilly,1997)
    UNIX Text Processing - Dale Dougherty and Tim O'Reilly (Hayden Books, 1987)
    nebo tutoriály od Mika Arsta viz - U-SEDIT2.ZIP. (všude možně)
    Pro ovládnuti mocného nástroje sed musíte znát Regulárni výrazy:
    Mastering Regular Expressions" by Jeffrey Friedl (O'Reilly, 1997)
    Manuálové stránky jsou také užitečné. Nikoliv sice pro laika, poslouží
    však skvěle jako reference. Zkuste "man sed", "man regexp", nebo
    podsekci "man ed".

    SYNTAXE UVOZOVEK: Předchozí příklady užívají jednoduché uvozovky ('...')
    namísto uvozovek dvojitých ("..."), protože je sed doma především na
    Unixových systémech. Jednoduché úvozovky zabrání shellu aby bral v potaz
    znak ($). Také pozor na kombinaci (`...') uvnitř ("..."). Uživatelé "csh"
    shellu a jemu podobných budou muset ke správnému běhu příkladů zauvozovkovat
    také (!) se zpětným lomítkem (\!). DOSové verze sedu vyžadují ("...").

    POUŽITÍ '\t' VE SKRIPTECH: Pro přehlednost jsme v příkladech používali
    výraz '\t' pro vyjádření tabulátoru (0x09) ve skriptech. Nicméně,
    většina verzí sedu zkratku '\t' nepozná, raději tedy používejte klávesu TAB.
    '\t' je podporován jako regulární znak v awku, perlu a HHsedu, sedmodu
    a GNU sedu verze3.02.80.

    VERZE SEDU: Verze sedu se liší a drobné rozdíly mezi nimi jsou patrné.
    Většina nepodporuje značky (:name) nebo skokové přikazy (b,t) uvnitř
    příkazu, pokud nejsou na konci. Když se používá co nejpřenosnější
    syntaxe příkazy mohou být i poněkud kostrbaté:
       sed -e '/AAA/b' -e '/BBB/b' -e '/CCC/b' -e d

    v porovnání s rešením v GNU sedu:

       sed '/AAA/b;/BBB/b;/CCC/b;d'      # nebo dokonce
       sed '/AAA\|BBB\|CCC/b;d'

    Navíc pamatujte, že zatímco mnoho sedů podporuje příkaz "/one/ s/re1/re2"
    mnoho NEpodporuje příkaz "/one/! s/re1/re2/" s mezerou před "s". Snažte
    se onu mezeru nepoužívat.

    OPTIMALIZACE PRO RYCHLOST: Pokud je nutné zvýšit výkonnost (velké
    soubory, apod.) je vhodné dát před příkaz "s" výraz "/hledej/" :

       sed 's/foo/bar/g' filename         # standartní substituce
       sed '/foo/ s/foo/bar/g' filename   # mnohem rychlejší
       sed '/foo/ s//bar/g' filename      # zkrácená syntaxe

    Pokud chcete vypsat jen kus souboru, je velmi vhodné použít příkaz "q".
    Ten velmi urychlí práci s velkými soubory.

       sed -n '45,50p' filename           # vypíše řádky 45 - 50
       sed -n '51q;45,50p' filename       # to samé, jen o dost rychleji

    Máte-li nějaké další skripty, které byste rádi publikovali, nebo
    objevili-li jste chybu v tomto dokumentu, kontaktujte prosím autora.
    Připojte vaší verzi sedu, operační systém a podstatu problému.
    Aby mohl být Váš skript prohlášen za "one-liner" (jednořádkáč :-) musí
    být kratší (nebo roven) 65 znaků.
    Naše díky patří:
     
     Al Aab                   # zakladatel "seders list"u
     Edgar Allen              # všelicos
     Yiorgos Adamopoulos      # leccos
     Dale Dougherty           # autor "sed & awk"
     Carlos Duarte            # autor "do it with sed"
     Eric Pement              # autor tohoto dokumentu
     Ken Pizzini              # autor GNU sedu verze 3.02
     S.G. Ravenhall           # skvělý "de-html" skript
     Greg Ubben               # příklady a  pomoc
    -------------------------------------------------------------------------

[![Valid XHTML 1.0
Strict](sed1line_cz_soubory/valid-xhtml10.png){style="border-style: none;"
width="88"
height="31"}](http://validator.w3.org/check?uri=http%3A%2F%2Fsed.sourceforge.net%2Fsed1line_cz.html)
