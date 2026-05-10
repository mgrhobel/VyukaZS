---
title: "cti_mne.txt"
source: "/mnt/f/git/mgr/FPE_navazujici/3. Semestr/NUMET/VB navod/Run_action/cti_mne.txt"
date: 2004-05-14
type: TXT
---


Pro spouštìní souborù, je tøeba znát jejich adresu a název, aby hypertextový odkaz byl platný !!!


Adresa kde je uložen mùj Winamp je:

C:\Program Files\Winamp\winamp.exe



Adresa kde je uložena kalkulaèka je:

calc.exe

(je ve stejné složce jako xls sešit)


Pokud máte hypertextové odkazy v poøádku,
musíte ještì nastavit èas, v kolik hodin chcete tyto soubory spouštìt,
stejnì tak lze i sešit *.xlsv daný èas zavøít (bohužel jen ten *.xls sešit)

Èas je tøeba nastavit v modulu "mod_Time" - makro "On_Time_Pulnoc" ...



Application.OnTime Pulnoc + TimeValue("13:40:00"), "Moje_makro"

Application.OnTime Pulnoc + TimeValue("13:40:30"), "Spustit_kalkulacku"

Application.OnTime Pulnoc + TimeValue("13:41:00"), "Spustit_Winamp"

Application.OnTime Pulnoc + TimeValue("13:42:00"), "Zav_sesit"


fantazii se meze nejkladou :-)



Makro "On_Time_Pulnoc" a makro "On_Time_Od_otevreni_sesitu"

jsou spouštìny událostí v sektoru kódu pro 

"Tento sešit" událost "Workbook_Open"

kde se pomocí fce "Call" volá dané makro.


"On_Time_Od_otevreni_sesitu" využívá nastavení výchozí hodnoty fci Now()

kdy èas se poèítá od spuštìní samotného makra.


Slezák Petr	info@slezak-petr.cz	www.slezak-petr.cz