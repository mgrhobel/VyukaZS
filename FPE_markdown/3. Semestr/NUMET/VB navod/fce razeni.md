---
title: "fce razeni.txt"
source: "/mnt/f/git/mgr/FPE_navazujici/3. Semestr/NUMET/VB navod/fce razeni.txt"
date: 2010-01-09
type: TXT
---

sloupec, radek ktery je pojmenovany hh
- jde to udelat pres rozsah napr. G1:G5

Sub Serad_vzestupne()
Range("G3").Select
Selection.Sort Key1:=Range("hh"), Order1:=xlAscending, Header:=xlGuess, _
OrderCustom:=1, MatchCase:=False, Orientation:=xlTopToBottom
End Sub