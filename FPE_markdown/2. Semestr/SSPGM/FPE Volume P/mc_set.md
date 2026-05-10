---
title: "mc_set.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/FPE Volume P/mc_set.pdf"
date: 2009-01-27
type: PDF (text-based)
---

Úvod:
Midnight Commander je skvělý správce souborů ve stylu Norton Commander známého z M$
DOSu. Pokud jej nainstalujete na svůj UNIX, pak můžete zapomenout na "děsivý" příkazový
řádek. Pro začátečníka na UNIXU je MC maximální zmenšení počátečního šoku, při
přechodu z M$ platformy nebo z Novellu a defakto možnost začít se ihned rozhlížet po disku.
MC je velmi mocný nástroj, avšak nesmíme zapomínat na UNIXové základní kameny, jako je
vi, cp, rm, ls, cd, chmod, chown, ..... V případě absence MC je pak člověk na něj spoléhající
zcela ztracen!

Shell alredy running!
Nepříjemnému hlášení Shell alredy running!, lze předejít spuštěním MC s volbou -u. To
nám zajistí spuštění MC jako "Linux console" a dokonce můžete pouštět z MC SVGA
programy jako DOOM, které jinak hlásí nekompatibilní terminál a nejdou spustit !!!

MC a čeština:
Aby Midnight Comander dále jen MC, správně zobrazoval české fonty, je nutné spustit MC s
parametrem -m mc -m a nastavit v Options/Display bits volbu (*) Full 8 bits. Spouštění mc
-m lze automatizovat dopsáním alias mc='mc -m' do souboru ~/.bashrc nebo
~/.cshrc, podle toho jaký shell používáte.

MC + čeština = nečitelné rámečky:
Vzhledem k tomu že programy používající čárovu grafiku jako MC nebo MenuConfig jádra,
jsou po nainstalování českých fontů na textovou konzolu Linuxu nečitelné, je nutno upravit
nastavení databází termcap a terminfo.
Již upravené databáze jsou zde ke stažení na těchto URL:
upravený http://cs.felk.cvut.cz/~xsauer/linux/TERMCAP.GZ pro čárovou grafiku
upravený http://cs.felk.cvut.cz/~xsauer/linux/LINUXTI.GZ pro čárovou grafiku
Tyto databáze je nutno zkopírovat termcap do /etc/termcap a terminfo do
/usr/lib/terminfo/l/linux a znovu se přihlásit.

MC a editor:
Vzhledem k tomu že MC standardně používá jako editor VI, je možno jej nahradit za jinný
editor pomocí systémové proměnné EDITOR. Například pro editor JOE napište do svého
~/.bash_profile
export EDITOR='joe -asis'. Pokud navíc vyexportujete proměnou EDITOR i v
souboru ~/.Xclients např.: export EDITOR='nedit', pak se vám v X-Windows při
editaci z MC spostí X-ový editor nedit a po ukončení X-Windows, opět editor joe

MC a virtuální souborové systémy:

MC a emulátory terminálu z jiných OS:

Užitečné "rychlé klávesy"
ALT+P Listuje historií příkazů zpět
ALT+N Listuje historií příkazů vpřed
ALT+T Přepíná zobrazení Full/Long/Default

