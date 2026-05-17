# Příprava na hodinu – Excel vzorce a grafy (8. ročník)

```
═══════════════════════════════════════════════════════
PŘÍPRAVA NA VYUČOVACÍ HODINU – INFORMATIKA
═══════════════════════════════════════════════════════

Datum:          _______________
Třída:          8.
Hodina č.:      H6–H7  (celkové pořadí v tematickém plánu; blok IS)
Časová dotace:  45 minut × 2 (nebo 1 × 45 min – základní vzorce)

NÁSTROJ:   ✓ LibreOffice Calc (nebo MS Excel / Google Sheets)
           ✓ Školní soubor: tridy_data.ods / .xlsx (připravený učitelem)

TEMATICKÝ CELEK: Blok IS – Informační systémy a práce s daty
TÉMA HODINY:     Tabulkový procesor – vzorce, funkce SUM/IF/AVERAGE, grafy
```

---

## CÍLE HODINY

**Kognitivní:**
- Žák **vysvětlí**, co je vzorec a funkce v tabulkovém procesoru
- Žák **rozliší** absolutní a relativní adresaci buněk (`A1` vs. `$A$1`)
- Žák **popíše** postup při tvorbě grafu z tabulkových dat

**Procesní:**
- Žák napíše funkce `SUM`, `AVERAGE`, `MAX`, `MIN` a `IF` na reálných datech
- Žák vytvoří sloupcový a koláčový graf a přizpůsobí jeho formátování
- Žák zformuluje odpověď na datovou otázku pomocí výsledků vzorců

---

## VÝCHOZÍ ZNALOSTI

- Základy tabulkového procesoru z nižší třídy (buňka, sloupec, řádek, tabulka)
- Ručně vepsané vzorce typu `=A1+B1`
- (Výhodou) filtry a řazení dat z předchozích hodin

**Ověření na začátku (2 min):**
*„Co napíšeš do buňky C1, aby zobrazovala součet A1 a B1?"* → `=A1+B1`

---

## POMŮCKY A ZDROJE

- ✓ Počítačová učebna (LibreOffice nebo Excel)
- ✓ Projektor pro demo
- ✓ Soubor `tridy_data.ods` na sdílené složce (tabulka se známkami 30 žáků)
- ✓ Pracovní list `H06_excel_vzorce.pdf` – popis funkcí + úkoly

---

## PRŮBĚH HODINY

### 0–5 min: ZAHÁJENÍ

- Cíl: *„Dnes se naučíme dělat věci, které by ručně trvaly hodiny – Excel to zvládne za sekundu."*
- Motivační otázka: *„Jak byste spočítali průměrnou známku třídy ze 120 čísel? A maximum?"*
  → Excel to udělá jedním vzorcem.

---

### 5–20 min: DEMO – Základní funkce

**Žáci otevřou soubor `tridy_data.ods` (nebo kopírují z promítaného vzoru)**

```
Sloupce: Jméno | Matematika | Čeština | Angličtina | Informatika | Průměr
```

**Krok 1 – Automatická suma a průměr:**

```
=SUM(B2:E2)       → součet všech předmětů jednoho žáka
=AVERAGE(B2:E2)   → průměr předmětů
=MAX(B2:B31)      → nejlepší zn. z matiky
=MIN(B2:B31)      → nejhorší zn. z matiky
```

**Krok 2 – Podmíněná funkce IF:**

```
=IF(F2<=2; "Výborný"; IF(F2<=3; "Průměr"; "Problém"))
```

- Vysvětlit logiku: IF(podmínka; co když TRUE; co když FALSE)
- Vnořené IF: hodnocení ve 3 kategoriích

**Krok 3 – Absolutní vs. relativní adresace:**

```
=B2*$H$1    → $H$1 se při kopírování nemění (např. koeficient)
=B2*H1      → H1 se posune při kopírování dolů (H2, H3…) – CHYBA!
```

- Zkus zkopírovat vzorec dolů – žáci uvidí rozdíl.

---

### 20–32 min: PRAKTICKÁ PRÁCE – Žáci sami

**Úkoly (žáci plní samostatně nebo ve dvojicích):**

```
1. Vyplň sloupec "Průměr" pro všechny žáky pomocí AVERAGE a zkopíruj vzorec.
2. Přidej sloupec "Hodnocení" s funkcí IF (výborný / průměr / problém).
3. Zjisti: Kdo má nejlepší průměr? Kdo nejhorší? (MIN/MAX na sloupec Průměr)
4. Spočítej průměr celé třídy z každého předmětu (řádek pod tabulkou).
5. Označ buňky podmíněným formátováním:
      Průměr < 2 → zelená, > 3.5 → červená.
```

---

### 32–42 min: GRAFY

**Demo – Tvorba grafu:**

1. Označ sloupec Jméno + sloupec Průměr (Ctrl+klik pro nespojité oblasti)
2. Vložit → Graf → Sloupcový
3. Přidej: název grafu, popis os, legenda
4. Změň typ na Koláčový → porovnej, kdy který typ grafu dávat smysl

**Pravidlo:**
```
Sloupcový / pruhový → porovnání hodnot mezi kategoriemi
Koláčový           → podíly z celku (max 5–7 segmentů)
Liniový            → vývoj v čase
```

**Žáci samostatně:**
- Vytvoř sloupcový graf průměrů za jednotlivé předměty (ne za žáky)
- Přizpůsob barvy a nadpis grafu

---

### 42–45 min: REFLEXE

- *„Kdy použiješ AVERAGE a kdy SUM?"*
- *„Jaký je rozdíl mezi relativní a absolutní adresací?"*
- *„Proč je koláčový graf špatnou volbou pro 30 žáků?"*
- Domácí úkol: Zkus zjistit, co dělá funkce `COUNTIF` – přines příklad na příští hodinu.

---

## DIFERENCIACE

| Úroveň | Aktivita |
|---|---|
| **Základní** | SUM, AVERAGE, MAX, MIN – vzorce předepsány, žáci doplňují |
| **Střední** | IF, podmíněné formátování, sloupcový graf |
| **Rozšíření** | COUNTIF, VLOOKUP (vyhledávání v tabulce), kontingenční tabulka |

---

## NAVAZUJÍCÍ TÉMATA

- **Příští hodina:** Řazení a filtrování dat, tvorba evidence (IS)
- **9. ročník:** SQL SELECT – databázové dotazy jako náhrada za filtry v Excelu
- **Přesah:** Datová analýza v Pythonu (pandas, matplotlib) – stejná logika, jiný nástroj

---

## ZDROJE A LITERATURA

- RVP ZV 2021 – výstupy **I-9-3-02** (řazení, filtrování, funkce), **I-9-3-03** (evidence dat)
- ŠVP 4. ZŠ Plzeň – IS, 8. ročník (tabulky pro evidenci, funkce a vzorce, tvorba grafů)
- LibreOffice Calc dokumentace: https://help.libreoffice.org/latest/cs/Calc/
- Výuka Excelu (česky): https://www.jaknaexcel.cz/
