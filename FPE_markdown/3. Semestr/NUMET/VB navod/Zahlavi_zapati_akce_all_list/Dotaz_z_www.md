---
title: "Dotaz_z_www.txt"
source: "/mnt/f/git/mgr/FPE_navazujici/3. Semestr/NUMET/VB navod/Zahlavi_zapati_akce_all_list/Dotaz_z_www.txt"
date: 2004-08-05
type: TXT
---

Datum: ...
Od: ...
Pøedmìt: Dotaz VB x VBA x EXCEL 



Vážený pane, 
pøi vyhledávání øešení jistého problému jsem narazil na vaše stránky. 
Odpovìï jsem tam nenalezl, ale dost možná, 
že jste se s nìèím podobným setkal a budete mi moc poradit. 

Když programuji ve VISUAL BASICU výstup do EXCELu používám kod z VBA pro EXCEL. 
Pøestože kod pro EXCEL z OFFICE 2000 a z OFFICE 97 je shodný 
a pøi tvorbì maker pøímo v EXCELu funguje, 
tak pøi formátování tabulky 
z programového prostøedí VISUAL BASICU to 100% funguje pouze u verze 2000. 

U verze 97 se neprovede napøíklad vytvoøení záhlaví a zápatí:
With WorkBook
     .CenterHeader = "&""Times New Roman CE,tuèné""&Záhlaví"
     .CenterFooter = "&""Times New Roman CE,tuèné""&Zápatí"
End With

nebo slouèení bunìk:
WorkBook.range("A3:X3").MergeCels=True


  Nevíte v èem by mohl být zakopaný pes?

S pozdravem ...