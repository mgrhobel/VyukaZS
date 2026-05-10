---
title: "text.htm"
source: "/mnt/f/git/mgr/FPE_navazujici/3. Semestr/DV2ST/hotove projekty/Hobel_Knizak_Excel/HTML/33/text.htm"
date: 2009-11-20
type: HTML
---

::: {#module}
Funkce
:::

::: {#unit}
Kombinace funkcí KDYŽ, ZAOKROUHLIT - DPH
:::

::: important
\
[Cíle](goals.htm){target="nove_okno" onclick="Otevri_okno();"}
:::

::: {#print}
[![ Tisk](../img/tisk.gif){width="32"
height="29"}](javascript:window.print();)
:::

# Kombinace funkcí KDYŽ, ZAOKROUHLIT

## DPH

Pro výpočet DPH - daně z přidané hodnoty se používají v současné době 2
sazby. Daň 9% mají potraviny, ostatní zboží má daň 19%.

\

Otevřete si soubor \"**DPH**\".

Do sloupce D doplňte vzorec pro výpočet daně. Jestli má Excel použít daň
9% nebo 19% zjistí ze sloupce C, kde P značí potraviny - 9%, O znamená
ostatní - 19%.

Do sloupce E poté spočítejte celkovou cenu zboží zaokrouhlenou na
desetihaléře (např. 5,40).

Uložte změny v souboru \"**DPH**\".

\

*Pomůcka:*

*Vzorec ve sloupci D pro výpočet DPH:*

=KDYŽ(C2=\"P\";B2\*0,09;B2\*0,19)

*Vzorec ve sloupci E pro výpočet zaokrouhlené celkové ceny:*

=ZAOKROUHLIT(SUMA(B2;D2);1)

[DPH.xls](11.xls){target="_blank"}

[DPH.xlsx](68.xlsx){target="_blank"}

[DPH_reseni.xls](12.xls){target="_blank"}

[DPH_reseni.xlsx](69.xlsx){target="_blank"}
