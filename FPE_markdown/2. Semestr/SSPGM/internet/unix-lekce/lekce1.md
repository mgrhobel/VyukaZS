---
title: "lekce1.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/internet/unix-lekce/lekce1.doc"
date: 2009-05-02
type: DOC
---

[**Prvky ochrany uživatelů v multiuživatelském OS UNIX**]{lang="cs-CZ"}[
]{lang="cs-CZ"}

**[Účet uživatele:]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

přihlášení\
práce v sezení (relaci)\
odhlášení

**[Účet obsahuje:]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

**[Uživatelské jméno]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

login name, 3-8 znaků, začíná písmenem, jedinečné v systému, záleží na
velikosti písmen

**[Heslo]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

**[Primární skupina:]{lang="cs-CZ"}**[ group ]{lang="cs-CZ"}

**[Uživatelské číslo:]{lang="cs-CZ"}**[ user identification UID
]{lang="cs-CZ"}

**[Doplňující identifikace uživatele]{lang="cs-CZ"}**[ : jméno,
příjmení, \... ]{lang="cs-CZ"}

**[Domácí adresář]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

**[Shell (interpret příkazů)]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

/bin/sh, /bin/ksh, /bin/bash, \...

**[Další informace]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

čas posledního přihlášení, doba platnosti hesla, \... (záleží na
implementaci)

[**Prvky ochrany uživatelů v multiuživatelském OS UNIX
(2)**]{lang="cs-CZ"}[ ]{lang="cs-CZ"}

**[Práva pro přístup k souborům a adresářům:]{lang="cs-CZ"}**[
]{lang="cs-CZ"}

**[určují se zvlášť pro]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

majitele souboru (u - user)\
skupinu uživatelů (g - group)\
ostatní, svět (o - other)

**[zvlášť pro]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

\
čtení/zápis/provedení (soubor)\
výpis/modifikace/vstup (adresář)

**[Speciální uživatel root (superuživatel)]{lang="cs-CZ"}**[
]{lang="cs-CZ"}

\
Jediný uživatel v systému, kterému se přístupová práva nekontrolují.

\
\

**[Při úspěšném přihlášení:]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

[vypíší se systémové zprávy\
vypíše se případné sdělení správce systému\
domovský adresář se nastaví jako běžný (pracovní)\
spustí se požadovaný shell\
vypíše se výzva shellu (prompt)\
]{lang="cs-CZ"}[\$]{lang="cs-CZ"}[\
Prompt závisí na nastavení shellu (proměnná PS1)\
]{lang="cs-CZ"}[set\|grep PS1]{lang="cs-CZ"}[\
]{lang="cs-CZ"}[exit]{lang="cs-CZ"}[ nebo
]{lang="cs-CZ"}[\^D]{lang="cs-CZ"}[ (může být potlačeno) ]{lang="cs-CZ"}

[**Zadávání příkazů shellu**]{lang="cs-CZ"}[ ]{lang="cs-CZ"}

-   [Dělají se rozdíly mezi malými a velkými písmeny ]{lang="cs-CZ"}

-   Shell interpretuje příkazy po stisku Enter

-   Příkazy lze zadávat \"do zásoby\"

-   Některé shelly si pamatují historii příkazů s možností editace a
    opětovného použití

-   Dokud řádek není ukončen stiskem Enter, lze

-   [smazat poslední znak stiskem znaku
    ]{lang="cs-CZ"}[**erase**]{lang="cs-CZ"}[ ]{lang="cs-CZ"}

-   [zrušit celý řádek stiskem znaku
    ]{lang="cs-CZ"}[**kill**]{lang="cs-CZ"}[ ]{lang="cs-CZ"}

Nastavení speciálních znaků zjistíme příkazem:

[stty -a]{lang="cs-CZ"}[ ]{lang="cs-CZ"}

Nezobrazitelné znaky se v UNIXu vypisují:

-   [jako ]{lang="cs-CZ"}[\^C]{lang="cs-CZ"}[ \... ctrl-C (ordinální
    hodnota 3) ]{lang="cs-CZ"}

-   [nebo ]{lang="cs-CZ"}[\\012]{lang="cs-CZ"}[ \... tři číslice
    oktalově ]{lang="cs-CZ"}

[**Zadávání příkazů shellu (2)**]{lang="cs-CZ"}[ ]{lang="cs-CZ"}

bash\$ stty -a

intr = \^C; quit = \^\\; erase = \^?; kill = \^U;

eof = \^D; eol = \<undef\>; eol2 = \<undef\>;

start = \^Q; stop = \^S; susp = \^Z; rprnt = \^R;

werase = \^W; lnext = \^V; flush = \^O; min = 1;

time = 0;

**[intr]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

[\
Násilně ukončí běžící proces (]{lang="cs-CZ"}[\^C]{lang="cs-CZ"}[)
]{lang="cs-CZ"}

**[eof]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

[\
Ukončení vstupu (např. z klávesnice;
]{lang="cs-CZ"}[\^D]{lang="cs-CZ"}[; End of File; EOF) ]{lang="cs-CZ"}

**[stop]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

[\
Pozastavení výpisu (např. na obrazovku;
]{lang="cs-CZ"}[\^S]{lang="cs-CZ"}[; X-off) ]{lang="cs-CZ"}

**[start]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

[\
Pokračování ve výpisu (]{lang="cs-CZ"}[\^Q]{lang="cs-CZ"}[; X-on)
]{lang="cs-CZ"}

**[susp]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

[\
Pozastavení procesu (resp. jeho převedení pod job control;
]{lang="cs-CZ"}[\^Z]{lang="cs-CZ"}[). Používejte uvážlivě - je
nebezpečné zapomínati procesy ]{lang="cs-CZ"}

Příklad:

yes

\^Z

ps

kill -9 \...

[**Nápověda -- man (**]{lang="cs-CZ"}[on-line manual
pages)]{lang="cs-CZ"}

**[Nápověda k určitému příkazu:]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

man passwd\
man stty\
man man

**[Reference ve tvaru:]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

man(1)\
jméno příkazu (sekce manuálu UNIXu)

**[Sekce]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

1.  Příkazy uživatelské úrovně

2.  Systémová volání

3.  Knihovní funkce

4.  Zařízení a ovladače zařízení

5.  Formáty (konfiguračních) souborů

6.  Hry

7.  Různé (ASCII), popisy maker

8.  Nástroje pro údržbu systému

**[Sekce se zadává:]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

**[man passwd]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

[vypíše nápovědu k příkazu ]{lang="cs-CZ"}[**passwd(1)**]{lang="cs-CZ"}[
pro změnu hesla ]{lang="cs-CZ"}

**[man 4 passwd]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

[Vypíše nápovědu k ]{lang="cs-CZ"}[**passwd(4) -**
]{lang="cs-CZ"}[formátu souboru /etc/passwd ]{lang="cs-CZ"}

**[Zadávání sekce v jiných implementacích:]{lang="cs-CZ"}**[
]{lang="cs-CZ"}

[**man -s 3 tzset**]{lang="cs-CZ"}[\
]{lang="cs-CZ"}[**man -S 3 tzset**]{lang="cs-CZ"}[ ]{lang="cs-CZ"}

**Systémy souborů**

**[Různé systémy souborů:]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

**[Základní pro UNIX:]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

[ufs (Solaris), efs (IRIX), ext2fs (Linux) a další ]{lang="cs-CZ"}

**[Doplňující:]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

msdos, vfat, nfs (Network fs), iso9660, swap, tmpfs a další

**[Vyrovnávání diskových operací:]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

[\"Špinavé\" bloky zapisuje na disk každých 30 vteřin démon
]{lang="cs-CZ"}[**bdflush**]{lang="cs-CZ"}[,
]{lang="cs-CZ"}[**update**]{lang="cs-CZ"}[,
]{lang="cs-CZ"}[**fsflush**]{lang="cs-CZ"}[ apod. jmen. ]{lang="cs-CZ"}

**[Systém souborů:]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

-   Zaváděcí blok

-   [Superblok ]{lang="cs-CZ"}

-   Seznam i-uzlů

-   Seznam datových bloků

[**Jméno souboru a adresáře**]{lang="cs-CZ"}[ ]{lang="cs-CZ"}

-   [Jméno souboru smí být dlouhé nejvýše ]{lang="cs-CZ"}[**255
    znaků**]{lang="cs-CZ"}[. Na tuto délku je zkracováno bez varování.
    ]{lang="cs-CZ"}

-   Může obsahovat libovolné znaky. Komplikace způsobují řídicí znaky
    shellu. Výjimka: v kořenovém adresáři nesmí být soubor jména \"/\".

-   Rozlišují se malá a velká písmena.

-   [Zvláštní význam mají jména souborů začínající znakem \".\" (tečka),
    např. \"]{lang="cs-CZ"}[.profile]{lang="cs-CZ"}[\". Při expanzi
    nahrazovacího znaku \"\*\" se taková jména nepoužijí. Vyzkoušejte
    též \"]{lang="cs-CZ"}[**ls**]{lang="cs-CZ"}[\" a
    \"]{lang="cs-CZ"}[**ls -a**]{lang="cs-CZ"}[\". ]{lang="cs-CZ"}

[**Adresáře**]{lang="cs-CZ"}[ ]{lang="cs-CZ"}

-   Oddělovačem jmen adresářů je znak \"/\" (lomítko).

-   [**Kořenový adresář**]{lang="cs-CZ"}[ (root) \"/\" ]{lang="cs-CZ"}

-   [**Běžný**]{lang="cs-CZ"}[ (pracovní)
    ]{lang="cs-CZ"}[**adresář**]{lang="cs-CZ"}[ ]{lang="cs-CZ"}

-   [Rozlišujeme cestu ]{lang="cs-CZ"}[**absolutní**]{lang="cs-CZ"}[
    \"/\.../\.../\...\" a ]{lang="cs-CZ"}[**relativní**]{lang="cs-CZ"}[
    \"\.../\.../\...\". ]{lang="cs-CZ"}

-   [Každý adresář obsahuje položky
    \"]{lang="cs-CZ"}[**.**]{lang="cs-CZ"}[\" (tento adresář) a
    \"]{lang="cs-CZ"}[**..**]{lang="cs-CZ"}[\" (nadřazený adresář)
    ]{lang="cs-CZ"}

[**Příklady**]{lang="cs-CZ"}[ ]{lang="cs-CZ"}

**[pwd]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

Print Working Directory (zjištění cesty k běžnému adresáři)

**[cd adresář]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

[Change Current Directory (bez parametru nastaví domovský)\
]{lang="cs-CZ"}[**cd ..**]{lang="cs-CZ"}[\
]{lang="cs-CZ"}[**./program**]{lang="cs-CZ"}[ ]{lang="cs-CZ"}

**[mkdir adresář \...]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

**[rmdir adresář \...]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

\

**Reprezentace souboru na disku**

**[Obsah souboru:]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

\
Z pohledu UNIXu je soubor posloupností bajtů. Systém obsah souboru
neinterpretuje.

Poznámka: V textovém souboru se řádky oddělují znakem LF (vs. MS-\*
odděluje řádky znaky CR LF).

-   [Informace o souborech jsou soustředěny do jednoho místa na
    paměťovém médiu - do ]{lang="cs-CZ"}[**seznamu
    i-uzlů**]{lang="cs-CZ"}[ (i-node). ]{lang="cs-CZ"}

-   Jeden soubor (nebo adresář) je popsán právě jedním i-uzlem.

-   i-uzly neobsahují jméno souboru.

-   [\"]{lang="cs-CZ"}[**ls -il**]{lang="cs-CZ"}[\" vypíše obsah
    adresáře vč. čísla i-uzlu. ]{lang="cs-CZ"}

-   i-uzel číslo 2 ukazuje vždy na kořenový adresář.

[**ls -l**]{lang="cs-CZ"}[ ]{lang="cs-CZ"}

[-rw-r\--r\-- 2 brandejs users 5 Mar 10 21:25 jméno1]{lang="cs-CZ"}

-rw-r\--r\-- 2 brandejs users 5 Mar 10 21:25 jméno3

-   Hodnota \"2\" je počet odkazů na soubor.

-   Úvodní \"-\" (minus) znamená, že jde o obyčejný soubor.

-   Položky \"jméno1\" a \"jméno3\" jsou rovnocenné.

\

[**rm jméno1**]{lang="cs-CZ"}[ ]{lang="cs-CZ"}

\

[**ls -l**]{lang="cs-CZ"}[ ]{lang="cs-CZ"}

-rw-r\--r\-- 1 brandejs users 5 Mar 10 21:25 jméno3

-   Nelze vytvářet tvrdé odkazy na adresáře.

-   Tvrdé odkazy lze dělat pouze uvnitř systému souborů.

\

**Symbolické odkazy**

[**Symbolické odkazy umožňují:**]{lang="cs-CZ"}[ ]{lang="cs-CZ"}

-   Odkazy na adresáře

-   Odkazy mimo jeden systém souborů

\

[Situace: máme soubor ]{lang="cs-CZ"}[**jméno3**]{lang="cs-CZ"}[
]{lang="cs-CZ"}

\

[**ln -s jméno3 jméno9**]{lang="cs-CZ"}[ ]{lang="cs-CZ"}

\

[**ls -l**]{lang="cs-CZ"}[ ]{lang="cs-CZ"}

-rw-r\--r\-- 1 brandejs users 5 Mar 10 22:46 jméno3

lrwxrwxrwx 1 brandejs users 6 Mar 10 22:48 jméno9 -\> jméno3

-   Úvodní \"l\" (písmeno malé L) znamená, že jde o symbolický odkaz.

-   [Hodnota 6 je velikost souboru, tj. počet písmen
    \"]{lang="cs-CZ"}[**jméno3**]{lang="cs-CZ"}[\". ]{lang="cs-CZ"}

-   [Položky \"]{lang="cs-CZ"}[**jméno3**]{lang="cs-CZ"}[\" a
    \"]{lang="cs-CZ"}[**jméno9**]{lang="cs-CZ"}[\" nejsou v žádném
    vztahu.]{lang="cs-CZ"}

\
\

[**Speciální soubory**]{lang="cs-CZ"}[ ]{lang="cs-CZ"}

-   Rozlišujeme:

-   Znakový speciální soubor

-   Blokový speciální soubor

-   Součástí jádra jsou \"ovladače zařízení\"

-   Uživatelské rozhraní vůči zařízením se realizuje prostřednictvím
    systému souborů

-   [**Speciální soubor**]{lang="cs-CZ"}[ je odkaz na i-uzel, který
    ukazuje na ovladač ]{lang="cs-CZ"}

[Příkaz pro vytvoření speciálního souboru:\
]{lang="cs-CZ"}[**mknod jméno typ hlavní_číslo
vedlejší_číslo**]{lang="cs-CZ"}[ ]{lang="cs-CZ"}

**[typ]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

[je \"]{lang="cs-CZ"}[**b**]{lang="cs-CZ"}[\" (blokové zařízení) nebo
\"]{lang="cs-CZ"}[**c**]{lang="cs-CZ"}[\" (znakové zařízení)
]{lang="cs-CZ"}

**[hlavní_číslo]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

je číslo udávající typ zařízení - ukazuje do tabulky zařízení

**[vedlejší_číslo]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

je číslo jednotky

-   Znakový a blokový speciální soubor vytváří superuživatel

-   [Zpravidla uloženy v adresáři
    ]{lang="cs-CZ"}[**/dev**]{lang="cs-CZ"}[ ]{lang="cs-CZ"}

-   [Ve výpise příkazu ]{lang="cs-CZ"}[**ls -l**]{lang="cs-CZ"}[ se
    objeví (údaje v pořadí hlavní číslo, vedlejší číslo) např.:
    ]{lang="cs-CZ"}

\

crw-rw-rw- 1 root sys 14, 4 Apr 25 1995 audio

brw-rw-r\-- 1 root mail 2, 0 Jan 1 1980 fd0

[**Příklady speciálních souborů:**]{lang="cs-CZ"}[ ]{lang="cs-CZ"}

**[/dev/console]{lang="cs-CZ"}**[ konzola počítače (obrazovka a
klávesnice), ]{lang="cs-CZ"}

**[/dev/fd0]{lang="cs-CZ"}**[ disketa číslo 0, ]{lang="cs-CZ"}

**[/dev/hda1]{lang="cs-CZ"}**[ první IDE disk a jeho první oblast,
]{lang="cs-CZ"}

**[/dev/sda1]{lang="cs-CZ"}**[ první SCSI disk a jeho první oblast,
]{lang="cs-CZ"}

**[/dev/lp1]{lang="cs-CZ"}**[ paralelní rozhraní Centronics odpovídající
LPT1:, ]{lang="cs-CZ"}

**[/dev/cua0]{lang="cs-CZ"}**[ sériové rozhraní RS-232 odpovídající
COM1:, ]{lang="cs-CZ"}

**[/dev/tty1]{lang="cs-CZ"}**[ první virtuální konzola, ]{lang="cs-CZ"}

**[/dev/null]{lang="cs-CZ"}**[ prázdné zařízení, které přijme všechna
data a které při čtení předá ihned
]{lang="cs-CZ"}[**eof**]{lang="cs-CZ"}[ (konec souboru). ]{lang="cs-CZ"}

\

[**Příklady ze Systému V:**]{lang="cs-CZ"}[ ]{lang="cs-CZ"}

**[/dev/dsk/c0t2d0s6]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

SCSI zařízení - disk z čísla řadiče 0, SCSI adresy 2, SCSI LUN 0 a
oblasti 6

**[/dev/pty/78]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

pseudo terminal driver (pty, pts)

**[/dev/rst12]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

magnetická páska (před zápisem souboru se vždy převine na začátek)

[**Speciální soubory (2)**]{lang="cs-CZ"}[ ]{lang="cs-CZ"}

**[FIFO - pojmenovaná roura]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

[\
Vytváří se příkazem:\
]{lang="cs-CZ"}[**mknod jméno p**]{lang="cs-CZ"}[ ]{lang="cs-CZ"}

-   p (pipe) roura

-   Pro přenos dat mezi procesy

-   Při zápisu do roury se data ukládají na disk téměř stejně jako při
    zápisu do souboru

-   i-uzel obsahuje ukazatel pro čtení a ukazatel pro zápis

-   Ukazatele nelze měnit jinak než čtením/zápisem - důsledně FIFO

Příklad:

**[mknod trubka p]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

**[ls -l]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

prw-r\--r\-- 1 brandejs users 0 Mar 18 22:12 trubka

**[man mknod \> trubka &]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

Přesměrováním \> výstup nepůjde na obrazovku, ale do souboru
\"trubka\".\
Ukončením příkazu znakem & jej spustíme na pozadí.

**[more trubka]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

Výpis obsahu souboru po obrazovkách.

**[rm trubka]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

Zrušení položky \"trubka\" v adresáři a zrušení i-uzlu.

**Typický adresářový strom**

/ Jádro OS

**[/bin/ls, cp, sh]{lang="cs-CZ"}**[ Základní systémové programy a
příkazy ]{lang="cs-CZ"}

**[/dev]{lang="cs-CZ"}**[ Adresář speciálních souborů ]{lang="cs-CZ"}

**[/etc]{lang="cs-CZ"}**[ Adresář většinou konfiguračních souborů
systému ]{lang="cs-CZ"}

**[/lib]{lang="cs-CZ"}**[ Adresář knihoven ]{lang="cs-CZ"}

**[/mnt]{lang="cs-CZ"}**[ Pomocný adresář pro připojování dočasných
systémů souborů ]{lang="cs-CZ"}

**[/tmp]{lang="cs-CZ"}**[ Veřejný adresář pro pomocné a dočasné soubory
]{lang="cs-CZ"}

**[/home]{lang="cs-CZ"}**[ Adresář s domovskými adresáři uživatelů
]{lang="cs-CZ"}

**[/usr/bin, etc, lib, tmp]{lang="cs-CZ"}**[ Adresáře se soubory, které
typicky z kapacitních důvodů nejsou v kořenovém adresáři.
]{lang="cs-CZ"}

**[/usr/include]{lang="cs-CZ"}**[ .h soubory pro překladač jazyka C
]{lang="cs-CZ"}

**[/usr/man]{lang="cs-CZ"}**[ Manuálové stránky ]{lang="cs-CZ"}

**[/usr/local/bin, man, etc, lib, \...]{lang="cs-CZ"}**[ Programy
lokálně instalované]{lang="cs-CZ"}

[**Typický adresářový strom (2)**]{lang="cs-CZ"}[ ]{lang="cs-CZ"}

**[/usr/sbin]{lang="cs-CZ"}**[ Systémové programy určené zpravidla
superuživateli ]{lang="cs-CZ"}

**[/usr/X11, openwin]{lang="cs-CZ"}**[ windows systém ]{lang="cs-CZ"}

**[/var]{lang="cs-CZ"}**[ Adresář pracovních/administrativních/\...
souborů systému ]{lang="cs-CZ"}

**[/var/mail]{lang="cs-CZ"}**[ Poštovní schránky uživatelů
]{lang="cs-CZ"}

**[/var/spool]{lang="cs-CZ"}**[ Dočasné soubory systémových operací
]{lang="cs-CZ"}

**[/var/adm]{lang="cs-CZ"}**[ Záznamy o činnosti systému a uživatelů
]{lang="cs-CZ"}

**[/var/tmp]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

**[/var/preserve]{lang="cs-CZ"}**[ Pracovní soubory editoru
]{lang="cs-CZ"}[**vi**]{lang="cs-CZ"}[, které zůstávají při násilném
ukončení editoru. ]{lang="cs-CZ"}

**Přístupová práva**

V i-uzlu pro vyhodnocení přístupových práv jsou:

**[vlastník souboru]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

Číselné UID toho uživatele, který soubor vytvořil nebo kterému jej
superuživatel věnoval.

**[skupina vlastníka]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

Číselné GID skupiny, do které byl uživatel v okamžiku vytváření souboru
přihlášen nebo na kterou bylo GID změněno.

**[přístupová práva]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

Přístupová práva jsou v objektu uložena ve 12 bitech.

[Ve výpisu ]{lang="cs-CZ"}[**ls -l**]{lang="cs-CZ"}[\
]{lang="cs-CZ"}[-rwxr-xr-x 1 novák student \...]{lang="cs-CZ"}[
]{lang="cs-CZ"}

**[vlastník (označuje se ]{lang="cs-CZ"}**[**u**]{lang="cs-CZ"}**[ jako
\'user\')]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

Vlastníkem je ten, jehož UID je zapsáno v i-uzlu.

**[skupina (označuje se ]{lang="cs-CZ"}**[**g**]{lang="cs-CZ"}**[ jako
\'group\')]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

**[ostatní (označuje se ]{lang="cs-CZ"}**[**o**]{lang="cs-CZ"}**[ jako
\'others\')]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

Touto kategorií určujeme, co s tímto objektem mohou provádět všichni.

[Přístupová práva se vyhodnocují v pořadí
]{lang="cs-CZ"}[ugo]{lang="cs-CZ"}[.]{lang="cs-CZ"}

[**Přístupová práva (3)**]{lang="cs-CZ"}[ ]{lang="cs-CZ"}

-   Číst soubor mohu, pokud mám právo vstupu do adresáře (x) a právo
    čtení souboru (r).

-   Zapisovat do souboru mohu, pokud mám právo vstupu do adresáře a
    právo zápisu do souboru (w).

-   Spustit soubor mohu, pokud mám právo vstupu do adresáře a právo
    provedení souboru (x).

[**Soubor běží pod UID toho, kdo jej spustil.**]{lang="cs-CZ"}[
]{lang="cs-CZ"}

Jiné možnosti:

-   [Chci, aby soubor běžel pod UID vlastníka souboru bez ohledu na to,
    kdo jej spustil: použiji ]{lang="cs-CZ"}[**Set User ID
    (SUID)**]{lang="cs-CZ"}[ bit\
    ]{lang="cs-CZ"}[**rwsr-xr-x**]{lang="cs-CZ"}[ ]{lang="cs-CZ"}

-   [Totéž pro skupinu: použiji ]{lang="cs-CZ"}[**Set Group ID
    (SGID)**]{lang="cs-CZ"}[ bit\
    ]{lang="cs-CZ"}[**rwxr-sr-x**]{lang="cs-CZ"}[ ]{lang="cs-CZ"}

[**Přístupová práva jsou uložena ve 12 bitech**]{lang="cs-CZ"} a
popisují se osmičkově následovně:

  ------ ---------------------------
  4000   SUID
  2000   SGID
  1000   sticky bit
  0400   r pro vlastníka
  0200   w pro vlastníka
  0100   x pro vlastníka
  0070   rwx pro skupinu vlastníků
  0007   rwx pro ostatní
  ------ ---------------------------

Všechny kombinace jsou možné, ne však významné.

[**Přístupová práva (4)**]{lang="cs-CZ"}[ ]{lang="cs-CZ"}

**[Příklady symbolického zápisu příst. práv:]{lang="cs-CZ"}**[
]{lang="cs-CZ"}

[rwsr-sr-x]{lang="cs-CZ"}[ (6755)\
]{lang="cs-CZ"}[rwxrwxrwt]{lang="cs-CZ"}[ (1777)\
]{lang="cs-CZ"}[rwxrwxrwT]{lang="cs-CZ"}[ (1776)\
]{lang="cs-CZ"}[rwSr\--r\--]{lang="cs-CZ"}[ (4644) ]{lang="cs-CZ"}

**[Příkaz umask]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

-   Zadávání implicitních přístupových práv pro vytváření souborů a
    adresářů.

-   Interní příkaz shellu.

-   [**umask nnn**]{lang="cs-CZ"}[ ]{lang="cs-CZ"}

-   Zadává se zpravidla numericky třemi osmičkovými číslicemi (nejvýše
    třemi)

-   Maska se zadává inverzně

-   [**umask 022**]{lang="cs-CZ"}[\
    touch soubor (]{lang="cs-CZ"}[rw-r\--r\--]{lang="cs-CZ"}[)\
    mkdir adresář (]{lang="cs-CZ"}[rwxr-xr-x]{lang="cs-CZ"}[)
    ]{lang="cs-CZ"}

-   [**umask 027**]{lang="cs-CZ"}[\
    touch soubor (]{lang="cs-CZ"}[rw-r\-\-\-\--]{lang="cs-CZ"}[)\
    mkdir adresář
    (]{lang="cs-CZ"}[rwxr-x\-\--]{lang="cs-CZ"}[)]{lang="cs-CZ"}

[**Příkaz chmod**]{lang="cs-CZ"}[ ]{lang="cs-CZ"}

**[chmod mode soubor]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

Nastavení přístupových práv.\
Kdo smí přístupová práva nastavovat?

**[mode]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

-   absolutně vyjádřeno 1-4 osmičkovými číslicemi

-   symbolicky - lze popsat následující gramatikou:

mode ::= clause\[,clause \...\]

clause ::= \[who \...\]\[action \...\]last_action

action ::= op\[perm \...\]

last_action ::= op\[perm \...\]

who ::= a\|u\|g\|o

op ::= +\|-\|=

perm ::= r\|s\|t\|w\|x\|X\|u\|g\|o

**[who:]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

[\'u\' (user), \'g\' (group), \'o\' (other); \'a\' (all) je totéž co
\'ugo\'\
Je-li who nezadáno, potom je to totéž co \'a\' (all), ale nenastaví se
bity označené příkazem ]{lang="cs-CZ"}[**umask**]{lang="cs-CZ"}[.
]{lang="cs-CZ"}

**[perm:]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

\'X\' je totéž co \'x\', ale aplikuje se pouze na adresáře nebo na
soubory, které mají alespoň jeden bit \'x\' nastavený.\
\'u\', \'g\', \'o\' použije se současné nastavení příst. práv uživatele,
skupiny, ostatních.

**[op:]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

\'+\' přidávají se práva, \'-\' ubírají se práva, \'=\' absolutní
nastavení.

**Příkazy pro nastavování příst. práv**

**[Příklady použití příkazu chmod]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

**[chmod go-w soubor]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

zakáže zápis pro skupinu a ostatní

**[644]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

[nastaví ]{lang="cs-CZ"}[rw-r\--r\--]{lang="cs-CZ"}[ ]{lang="cs-CZ"}

**[=rw,+X]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

[nastaví \'rw\' podle ]{lang="cs-CZ"}[**umask**]{lang="cs-CZ"}[ a \'x\'
pro všechny (\'ugo\') tehdy, je-li soubor proveditelný alespoň pro
jednoho z \'ugo\' nebo jde o adresář. ]{lang="cs-CZ"}

**[go=]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

smaže všechny bity pro \'go\'

**[a+rwxt]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

typické nastavení pro veřejný pracovní adresář

**[u+s]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

nastavení SUID

**[g+s]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

nastavení SGID (majitel souboru musí být členem skupiny)

[**Příkazy pro nastavování příst. práv (2)**]{lang="cs-CZ"}[
]{lang="cs-CZ"}

**[chown vlastník soubor \...]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

Změna vlastníka souboru nebo adresáře.\
Vlastník se zadává buď už. jménem, nebo číselně UID.\
Jak zjistím svoje UID?\
Vlastníka souboru smí měnit pouze superuživatel.\
POSIX 1003.2 povoluje syntaxi:

chown vlastník:skupina soubor \...

pro současnou změnu vlastníka i skupiny.

**[newgrp skupina]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

Přihlášení do jiné skupiny.\
Příkazem se mění aktuální GID přihlášeného uživatele.\
Uživateli je přihlášením do systému nastaveno jisté GID (zaznamenáno v
účtě) a tímto příkazem může uživatel svoje GID měnit na jedno z těch,
které má povoleno v /etc/group.\
Příkaz bez uvedení skupiny nastaví GID podle účtu.

**[chgrp skupina soubor \...]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

Změna skupiny souboru nebo adresáře.\
Skupinu smí měnit vlastník souboru nebo superuživatel. Vlastník souboru
však pouze tehdy, pokud náleží do cílové skupiny.

**Uživatelské rozhraní**

**[Známé:]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

-   [Bourne shell (]{lang="cs-CZ"}[**sh**]{lang="cs-CZ"}[)
    ]{lang="cs-CZ"}

-   [C-shell (]{lang="cs-CZ"}[**csh**]{lang="cs-CZ"}[) ]{lang="cs-CZ"}

-   [Korn shell (]{lang="cs-CZ"}[**ksh**]{lang="cs-CZ"}[)
    ]{lang="cs-CZ"}

-   [Bourne-again shell (]{lang="cs-CZ"}[**bash**]{lang="cs-CZ"}[)
    ]{lang="cs-CZ"}

**[Co je shell?]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

Shell je interpretační program. jazyk. Čte příkazy a provádí z terminálu
nebo ze souboru.

**[Obecný formát příkazového řádku:]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

arg0 arg1 arg2 \...\
Řetězec arg0 je vždy jméno příkazu.

**[Příkazy:]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

-   vnitřní

-   vnější

arg0 se nejprve hledá v seznamu vnitřních příkazů a potom podle seznamu
cest proměnné PATH

**[Ukončovací kód (exit status):]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

Každý příkaz při svém ukončení vrací numerický stav. Hodnota 0 znamená
OK. Nenulová hodnota značí chybu.

**[Lexikální analýza příkazového řádku]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}

Shell čte ze vstupu \"slova\" vzájemně oddělená \"bílým místem\"
(mezera, tabulátor) a operátory:

**[Řídicí operátory:]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}[& && ( ) ; ;; \|
\|\| ]{lang="cs-CZ"}[nový řádek ]{lang="cs-CZ"}

**[Operátory přesměrování:]{lang="cs-CZ"}**[ ]{lang="cs-CZ"}[\< \> \>\|
\<\< \>\> \<& \>& \<\<- \<\>]{lang="cs-CZ"}

\
\

::: {title="footer"}
[21]{style="background: #c0c0c0"}
:::
