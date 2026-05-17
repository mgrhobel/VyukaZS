# Příprava na hodinu – Kódování dat a binární soustava (6. ročník)

```
═══════════════════════════════════════════════════════
PŘÍPRAVA NA VYUČOVACÍ HODINU – INFORMATIKA
═══════════════════════════════════════════════════════

Datum:          _______________
Třída:          6.
Hodina č.:      H4–H5  (celkové pořadí v tematickém plánu; blok DIM)
Časová dotace:  45 minut × 2 (nebo 1 × 45 min pro zkrácený úvod)

NÁSTROJ:   ✓ Papír a tužka (binární karty)
           ✓ Binární kalkulačka: https://binary.numbermonk.com/
           ✓ Volitelně: CS Unplugged – aktivita s kartami

TEMATICKÝ CELEK: Blok 3 – Data, informace a modelování (DIM)
TÉMA HODINY:     Kódování dat – bit, bajt, binární soustava
```

---

## CÍLE HODINY

**Kognitivní:**
- Žák **vysvětlí**, co je bit a bajt, a uvede jejich vztah
- Žák **převede** malé celé číslo (0–15) z binární soustavy do desítkové a zpět
- Žák **popíše** princip, jak počítač ukládá text (ASCII) a obrázky (pixel = bajt)

**Procesní:**
- Žák pomocí binárních karet sestaví libovolné číslo do 31
- Žák zakóduje svůj věk do binárního čísla a ověří výsledek

---

## VÝCHOZÍ ZNALOSTI

- Obecná představa o počítači (umí přijímat a zpracovávat data)
- Desítková soustava – žák ví, co je číslice, řád (jednotky, desítky, stovky)

**Ověření na začátku (2 min):**
*„Co je podle vás informace? Jak ji uchovává počítač – jako text? Jako elektřinu?"*

---

## POMŮCKY A ZDROJE

- ✓ Binární karty (papírové – viz příloha nebo stáhnout z csunplugged.org)
- ✓ Projektor pro demo
- ✓ Pracovní list `H04_binarni_soustava.pdf` (viz sdílená složka)
- ✓ Volitelně: https://classic.csunplugged.org/binary-numbers/ (aktivity bez PC)
- ✓ Volitelně: https://hourofcode.com/cz – aktivity o kódování

---

## PRŮBĚH HODINY

### 0–5 min: ZAHÁJENÍ

- Přivítání, sdělení cíle: *„Dnes pochopíme, jak počítač ukládá čísla, text i obrázky – vše jako jedničky a nuly."*
- Záhadná otázka: *„Kolik informace uloží jedno bliknutí žárovky?"*
  - → 1 bit: žárovka je buď ON nebo OFF

---

### 5–12 min: MOTIVACE / MINI PŘEDNÁŠKA

**Bit = nejmenší jednotka informace**

```
BIT:  0 nebo 1 (vypnuto / zapnuto)
BAJT: 8 bitů = 2^8 = 256 různých hodnot
```

- Analogie: BIT je jako světlo v místnosti (zapnuto/vypnuto)
- 1 bajt = 1 písmeno v ASCII (A = 65 = 01000001₂)
- 1 pixel obrázku (256 úrovní šedé) = 1 bajt
- 1 MP3 sekunda ≈ 16 000 bajtů (16 KB)

**Binární soustava – základní princip:**

```
Desítková:   1    2    4    8    16  ... (mocniny 10: 1, 10, 100...)
Binární:     1    2    4    8    16  ... (mocniny 2: 2^0, 2^1, 2^2...)
```

Rozdíl: v desítkové soustavě jsou číslice 0–9, v binární jen 0 a 1.

---

### 12–25 min: DEMO + AKTIVITA S KARTAMI

**Binární karty (papírové nebo promítané):**

```
[ 16 ]  [ 8 ]  [ 4 ]  [ 2 ]  [ 1 ]
```

- Karta je otočena OBRAZEM (= 1) nebo BÍLOU stranou (= 0)
- Hodnota = součet hodnot otočených karet

**Příklady (učitel ukazuje, žáci hádají číslo):**

```
[ 16 ]  [  8 ]  [  4 ]  [  2 ]  [  1 ]
   0        1       0       1       1    = 8 + 2 + 1 = 11
```

**Úkoly pro žáky (papír nebo karty):**
1. Zakóduj číslo 5 do binárního (0 1 0 1)
2. Zakóduj číslo 13
3. Jaké číslo je 1 0 1 1 0?
4. Jak vyjádřit číslo 19?

> 🎯 **Soutěž:** Kdo první ukáže správně číslo, které učitel řekne?

---

### 25–35 min: ROZŠÍŘENÍ – TEXT A ASCII

**Jak počítač ukládá písmena?**

```
A = 65 = 01000001
B = 66 = 01000010
a = 97 = 01100001
```

- Tabulka ASCII: každý znak má přiřazené číslo
- „AHOJ" = 4 bajty = 32 bitů

**Aktivita – Dekóduj vzkaz:**

```
72 101 108 108 111 = ?
(použij ASCII tabulku na tabuli nebo na pracovním listu)
```

→ Odpověď: „Hello"

---

### 35–42 min: SAMOSTATNÁ PRÁCE / OVĚŘENÍ

**Žáci samostatně (nebo ve dvojicích):**

```
1. Převeď do binárního:
   a) svůj věk: ___  →  _________________
   b) počet písmen ve svém jménu: ___ → ________________

2. Převeď z binárního do desítkového:
   a) 10110 = ?
   b) 11001 = ?
   c) 01111 = ?

3. Kolik bitů potřebuješ pro číslo 255? A pro číslo 256?
```

---

### 42–45 min: REFLEXE A SHRNUTÍ

- *„Jaký je rozdíl mezi bitem a bajtem?"*
- *„Proč počítače pracují s jedničkami a nulami a ne s desítkovou soustavou?"*
  - → elektromagnetické stavy, spolehlivost, jednoduchost
- Domácí úkol: Zakóduj 3 písmena svého jména do binárního (ASCII tabulka v pracovním listu)

---

## DIFERENCIACE

| Úroveň | Aktivita |
|---|---|
| **Základní** | Převody čísel 0–15, binární karty s pomocí |
| **Střední** | Převody 0–31, zakódování slova do ASCII |
| **Rozšíření** | Hexadecimální soustava – proč se používá? (#FF0000 = červená) |

---

## NAVAZUJÍCÍ TÉMATA

- **Příští hodina:** Modelování dat – vývojové diagramy a grafy (DIM)
- **7. ročník:** Datové formáty souborů (DT: uložení textu vs. obrázku vs. videa)
- **Přesah:** Barvy v HTML (#RGB), komprese dat (proč jsou MP3 menší než WAV)

---

## ZDROJE A LITERATURA

- CS Unplugged – Binary Numbers: https://classic.csunplugged.org/binary-numbers/
- ASCII tabulka: https://www.asciitable.com/
- RVP ZV 2021 – výstup **I-9-1-01** (kódování a dekódování dat v binární soustavě)
- ŠVP 4. ZŠ Plzeň – DIM, 6. ročník (kódování a dekódování informace)
- ŠVP Bolevecká ZŠ – DIM, 6. ročník (bit, bajt, binární čísla, standardizované kódy)
