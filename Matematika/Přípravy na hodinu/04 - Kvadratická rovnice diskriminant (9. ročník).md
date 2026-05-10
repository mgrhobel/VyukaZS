# Příprava na hodinu – Kvadratická rovnice: diskriminant
## Matematika 9. ročník | Příprava č. 04

---

| Položka | Hodnota |
|---|---|
| **Předmět** | Matematika |
| **Ročník** | 9. |
| **Téma hodiny** | Kvadratická rovnice – diskriminant, vzorec pro kořeny |
| **Číslo hodiny v sekvenci** | H8 (ze Sekvence 9. ročník) |
| **Časová dotace** | 45 minut |
| **Cíle hodiny** | Žák vypočítá diskriminant a kořeny kvadratické rovnice; správně rozliší počet řešení; ověří výsledek dosazením |
| **Výstup RVP ZV** | M-9-3-02 Kvadratické rovnice |
| **Metody** | Výklad s odvozením, frontální procvičování, diferenciovaná samostatná práce |
| **Pomůcky** | Tabule, pracovní list |
| **Návaznost** | Minulá hodina: neúplné kvadratické rovnice. Příští: Viètovy vzorce, slovní úlohy. |

---

## PRŮBĚH HODINY

### 1. ÚVOD – Opakování neúplných typů (5 min)

**Ústní kvíz (rychlý fire-round):**
- 4x² − 36 = 0 → ? (x = ±3)
- 5x² + 5x = 0 → ? (x = 0 nebo x = −1)
- x² + 4 = 0 → ? (žádné reálné řešení)

**Přechod:**
> „Co když máme všechny tři členy? Třeba 2x² − 5x + 3 = 0?"
> „Neumíme to rozložit 'odhadem' – potřebujeme univerzální vzorec."

---

### 2. VÝKLAD – Diskriminant a vzorec (15 min)

**Na tabuli – postupné odvozování (ne jen mechanický vzorec!):**

```
Máme: ax² + bx + c = 0  (a ≠ 0)

Vytkni a: a(x² + b/a × x + c/a) = 0

Doplníme na čtverec:
  x² + (b/a)x + (b/2a)² − (b/2a)² + c/a = 0
  (x + b/2a)² = (b/2a)² − c/a
  (x + b/2a)² = (b² − 4ac) / 4a²

Označíme: D = b² − 4ac   ← DISKRIMINANT

Pak: (x + b/2a)² = D / 4a²

Umocníme-li: x + b/2a = ± √D / 2a

Výsledek:
         −b ± √D
  x₁,₂ = ————————
              2a
```

**Tři případy dle D:**
```
D > 0:  dva různé reálné kořeny (√D existuje, + a − dávají různé výsledky)
D = 0:  jeden dvojnásobný kořen (√0 = 0, oba kořeny stejné)
D < 0:  žádný reálný kořen (√záporné číslo neexistuje v ℝ)
```

**Vzorový příklad – DETAILNĚ, krok po kroku:**
```
2x² − 5x + 3 = 0

Identifikace: a = 2, b = −5, c = 3

Diskriminant: D = (−5)² − 4 × 2 × 3 = 25 − 24 = 1

D > 0 → dva různé kořeny

       −(−5) ± √1     5 ± 1
x₁,₂ = ————————————  = ———————
             2×2           4

x₁ = (5 + 1) / 4 = 6/4 = 3/2
x₂ = (5 − 1) / 4 = 4/4 = 1

OVĚŘENÍ (VŽDY!):
  x = 3/2: 2×(9/4) − 5×(3/2) + 3 = 18/4 − 15/2 + 3 = 4,5 − 7,5 + 3 = 0 ✓
  x = 1:   2×1 − 5×1 + 3 = 2 − 5 + 3 = 0 ✓
```

---

### 3. FRONTÁLNÍ PROCVIČOVÁNÍ (10 min)

Žáci řeší samostatně, jeden jde k tabuli po 2 minutách.

**Příklady (vzestupná obtížnost):**

1. x² − 5x + 6 = 0  (a=1, b=−5, c=6; D=25−24=1; x=3, x=2)
2. 3x² + 6x + 3 = 0  (D=36−36=0; x₁=x₂=−1)
3. x² + 2x + 5 = 0  (D=4−20=−16 < 0; ∅)
4. 2x² − 7x + 3 = 0  (D=49−24=25; x=3, x=1/2)

**U příkladu 3:** Zdůraznit: „Neděláme √záporného čísla – rovnice nemá řešení v reálných číslech."

---

### 4. SAMOSTATNÁ PRÁCE – DIFERENCIOVANÁ (10 min)

**Varianta A (žáci s obtížemi):**
```
1. x² − 7x + 10 = 0  (D=9; x=5, x=2)
2. x² + 4x + 4 = 0  (D=0; x=−2)
3. x² + 1 = 0  (D=−4; ∅)
```

**Varianta B (standardní):**
```
1. 3x² − 11x + 6 = 0  (D=49; x=3, x=2/3)
2. 2x² + 5x − 3 = 0  (D=25+24=49; x=1/2, x=−3)
3. x² − 6x + 10 = 0  (D=36−40 < 0; ∅)
4. 4x² − 4x + 1 = 0  (D=16−16=0; x=1/2)
```

**Varianta C (rychlí žáci):**
```
1. 0,5x² − x − 4,5 = 0  (× 2: x²−2x−9=0; D=4+36=40; x=1±√10)
2. (x+1)(x−3) = −4  → x²−2x−3=−4 → x²−2x+1=0 → D=0; x=1
3. Pro jakou hodnotu k má rovnice x²+kx+9=0 právě jedno řešení?
   D=0: k²−36=0 → k=±6
```

---

### 5. ZÁVĚR + DÚ (5 min)

**Shrnutí na tabuli (žáci doplňují):**
```
Kvadratická rovnice ax²+bx+c=0:
1. Urči a, b, c
2. D = b²−4ac
3. D > 0: x = (−b ± √D) / 2a
   D = 0: x = −b / 2a
   D < 0: žádné řešení
4. VŽDY ověř dosazením!
```

**DÚ:** SÚ str. 21, č. 21–30

**Exit ticket:**
> „x² − 6x + 9 = 0. Vypočítej D a řekni kolik kořenů má rovnice."
> (D = 36 − 36 = 0; jeden dvojnásobný kořen x = 3)

---

## DIFERENCIACE A POZNÁMKY

**Typické chyby žáků – předem upozorni:**
1. Zapomenout znaménko: b = −5 → b² = 25, ne −25
2. Špatná závorka: 4ac počítat jako (4)(a)(c), ne 4+a+c
3. Netvoří oba kořeny – zastaví se u x₁

**Poznámky pro DFP (dyslektici/dysgrafici):**
- Vzorec na kartičce k dispozici (neplatí při písemce – musí znát)
- Větší papír pro přehledné zapsání kroků

---

## REFLEXE PO HODINĚ

**Co fungovalo:**

**Co příště změním:**

**Chyby, které se opakovaly:**
