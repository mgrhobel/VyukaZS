---
title: "text.htm"
source: "/mnt/f/git/mgr/FPE_navazujici/3. Semestr/DV2ST/hotove projekty/Hobel_Knizak_Excel/HTML/35/text.htm"
date: 2009-11-20
type: HTML
---

::: {#module}
Funkce
:::

::: {#unit}
Vícenásobné použití funkce KDYŽ - PSČ
:::

::: important
\
[Cíle](goals.htm){target="nove_okno" onclick="Otevri_okno();"}
:::

::: {#print}
[![ Tisk](../img/tisk.gif){width="32"
height="29"}](javascript:window.print();)
:::

# Funkce - Vícenásobné použití KDYŽ

## PSČ

V České republice se používají pro snadné rozpoznání pošt tzv. poštovní
směrovací čísla (PSČ). Jedná se o pěticiferné číslo, jehož poslední
dvojčíslí je odděleno mezerou. Podle první číslice lze poznat, ve kterém
regionu se daná pošta nachází:

\

::: {align="center"}
  -------- -----------------------
  100 00   Praha
  200 00   Střední Čechy
  300 00   Západní a Jižní Čechy
  400 00   Severní Čechy
  500 00   Východní Čechy
  600 00   Jižní Morava
  700 00   Severní Morava
  -------- -----------------------
:::

\

Otevřete si soubor \"**PSČ**\" a připravte tabulku, která po zadání
libovolného PSČ, do vedlejšího sloupce doplní správný region, do kterého
PSČ patří.

Ověřte si správnost vzorce pohledem do tabulky.

Uložte změny v souboru \"**PSČ**\".

\

*Pomůcka:*

*Vzorec pro určení regionu PSČ:*

=KDYŽ(A4&lt20000; \"Praha\"; KDYŽ(A4&lt30000; \"Střední Čechy\";
KDYŽ(A4&lt40000; \"Západní a Jižní Čechy\"; KDYŽ(A4&lt50000; \"Severní
Čechy\"; KDYŽ(A4&lt60000; \"Východní Čechy\"; KDYŽ(A4&lt70000; \"Jižní
Morava\"; \"Severní Morava\"))))))

[PSČ.xls](42.xls){target="_blank"}

[PSČ.xlsx](99.xlsx){target="_blank"}

[PSČ_reseni.xls](43.xls){target="_blank"}

[PSČ_reseni.xlsx](100.xlsx){target="_blank"}
