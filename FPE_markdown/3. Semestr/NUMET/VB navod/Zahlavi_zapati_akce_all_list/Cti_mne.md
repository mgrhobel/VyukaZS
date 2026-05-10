---
title: "Cti_mne.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/3. Semestr/NUMET/VB navod/Zahlavi_zapati_akce_all_list/Cti_mne.doc"
date: 2004-08-05
type: DOC
---

**Výsledek**

\

Autor: Slezák Petr
[[www.slezak-petr.cz](http://www.slezak-petr.cz/)]{.underline}
[[info[@]{lang="en-US"}slezak-petr.cz]{.underline}](mailto:info@slezak-petr.cz)

\

Sešit kromě kódu pro každý list má také speciální místo, a to je:

„Tento sešit" („Thisworkbook")

V této části jsou akce, která spouští makra v rámci celého sešitu:

\

*Workbook_Open* -- Po otevření sešitu ...

*Workbook_BeforePrint* -- Před tiskem ...

*Workbook_BeforeSave* - Před uložením sešitu ...

*Workbook_BeforeClose* -- Před uložením ...

\

Na základě těchto událostí se dají dělat další akce ...

\

*Workbook_Open* -- Po otevření sešitu ...

nastavit parametry listu, seřadit listy, spustit vstupní formulář ...

\

*Workbook_BeforePrint* -- Před tiskem ...

nastavit vlastnosti tisku, záhlaví zápatí a jeho font ...

popř. zakázat tisk ...

\

*Workbook_BeforeSave* - Před uložením sešitu ...

zakázat uložení souboru (zachovat originál) ...

\

*Workbook_BeforeClose* -- Před uložením ...

uložit záložní kopii nějaké jméno, někam ...

\

Příklady na *Workbook_Open* a *Workbook_BeforePrint*

jsou v přiloženém souboru.

\

\
