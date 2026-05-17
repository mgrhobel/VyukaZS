# Příprava na hodinu – Python funkce (7. ročník)

> ⚠️ **Rozšiřující téma – blíže k SŠ úrovni**  
> Základní funkce (`def`, `return`) jsou dle RVP ZV 2023 pro 7.–9. ročník ZŠ OK, ale Python textové programování je náročnější.  
> **Doporučení:** Použít jen pro třídy se silnějším zájmem o programování nebo po jistém Scratch základu. Na SŠ se Python probírá systematicky s OOP, moduly, knihovnami.

```
═══════════════════════════════════════════════════════
PŘÍPRAVA NA VYUČOVACÍ HODINU – INFORMATIKA
═══════════════════════════════════════════════════════

Datum:          _______________
Třída:          7.
Hodina č.:      H41  (celkové pořadí v tematickém plánu)
Časová dotace:  45 minut

NÁSTROJ:   ✓ Python – Thonny IDE (nainstalováno na PC)

TEMATICKÝ CELEK: Blok 3 – Python pokročile
TÉMA HODINY:     Funkce – def, parametry, návratová hodnota (return)
```

---

## CÍLE HODINY

**Kognitivní:**
- Žák **vysvětlí**, k čemu slouží funkce (znovupoužitelnost, přehlednost)
- Žák **napíše** vlastní funkci s parametry a hodnotou return
- Žák **zavolá** funkci s různými argumenty a přečte výsledek

**Procesní:**
- Žák refaktoruje opakující se kód do funkce
- Žák testuje funkci s různými vstupy

---

## VÝCHOZÍ ZNALOSTI

- Python: proměnné, `input()`, `print()`, `int()`, `float()`
- Podmínky (`if/elif/else`), smyčka `for`/`while`
- Základy matematiky: obsah a obvod geometrických tvarů

**Ověření na začátku (2 min):**
```python
vysledek = 4 * 5
print(vysledek)
```
*„Co program vypíše?"* → `20`

---

## POMŮCKY A ZDROJE

- ✓ Počítačová učebna, Thonny IDE
- ✓ Projektor pro demo
- ✓ Startovní soubor `H41_start.py` na sdílené složce (obsahuje opakující se kód, který budeme refaktorovat)

---

## PRŮBĚH HODINY

### 0–5 min: ZAHÁJENÍ

- *„Minule jste počítali obsah čtverce, kruhu a trojúhelníku – ale museli jste pořád opakovat vzorec. Co kdybychom ten vzorec pojmenovali a mohli ho volat?"*
- Sdělení cíle: *„Dnes se naučíme funkce – pojmenované bloky kódu, které můžeme volat vícekrát."*

---

### 5–10 min: MOTIVACE / ZADÁNÍ

Ukaž problém bez funkce – opakující se kód (promítnout):

```python
# Opakující se kód – bez funkce
a = 5
obsah1 = a * a
print(f"Obsah čtverce se stranou {a} cm je {obsah1} cm²")

b = 8
obsah2 = b * b
print(f"Obsah čtverce se stranou {b} cm je {obsah2} cm²")

c = 12
obsah3 = c * c
print(f"Obsah čtverce se stranou {c} cm je {obsah3} cm²")
```

*„Co je špatně? Opakujeme ten samý vzorec 3×. Kdybychom chtěli změnit vzorec, musíme to opravit na 3 místech. Funkce tento problém řeší."*

---

### 10–22 min: DEMO (učitel ukazuje, žáci sledují)

**Krok 1 – Základní funkce bez parametrů**

```python
def pozdrav():
    print("Ahoj, jsem funkce!")

pozdrav()   # volání funkce
pozdrav()   # opakované volání
```

- Zdůraznit: `def` = definice; `pozdrav()` = volání; odsazení je povinné!

**Krok 2 – Funkce s parametry**

```python
def obsah_ctverce(strana):
    obsah = strana * strana
    print(f"Obsah čtverce se stranou {strana} cm je {obsah} cm²")

obsah_ctverce(5)
obsah_ctverce(8)
obsah_ctverce(12)
```

- *„Teď to funguje pro libovolnou stranu. Vzorec je jen na jednom místě."*

**Krok 3 – Funkce s `return` (vrátí hodnotu)**

```python
def obsah_ctverce(strana):
    return strana * strana

a = obsah_ctverce(5)
b = obsah_ctverce(8)
soucet = a + b
print(f"Součet dvou ploch: {soucet} cm²")
```

- *„Rozdíl: `print` jen vypíše, `return` vrátí hodnotu, se kterou můžeme dál počítat."*

**Krok 4 – Více parametrů**

```python
def obsah_obdelniku(a, b):
    return a * b

print(obsah_obdelniku(4, 7))    # → 28
print(obsah_obdelniku(10, 3))   # → 30
```

---

### 22–40 min: SAMOSTATNÁ / PÁROVÁ PRÁCE

**Zadání:**

Otevři `H41_start.py` a napiš funkce pro výpočet geometrických tvarů:

1. `obvod_ctverce(strana)` → vrátí obvod čtverce (`4 * strana`)
2. `obsah_trojuhelniku(zakladna, vyska)` → vrátí `0.5 * zakladna * vyska`
3. `obsah_kruhu(polomer)` → vrátí `3.14159 * polomer * polomer`
4. Zavolej každou funkci **alespoň 3×** s různými hodnotami a výsledky vypiš

**Rozšíření (pro rychlejší):**
- Přidej funkci `porovnej(a, b)`, která vrátí `True` pokud `a > b`, jinak `False`
- Vytvoř funkci `nejvetsi(a, b, c)`, která vrátí největší ze tří čísel
- Napiš funkci `bmi(hmotnost, vyska)` → vrátí BMI (`hmotnost / (vyska**2)`)

**Nápovědy:**
- `def nazev(parametry):` pak odsadit tělo
- `return hodnota` (bez závorek)
- Volání: `vysledek = nazev(argumenty)`

---

### 40–44 min: PREZENTACE / SDÍLENÍ

- 1–2 žáci ukáží svou funkci na projektoru
- Třída: *„Jak to máš jinak? Funguje to?"*
- Ukáž variantu s `import math` a `math.pi` (rychlý bonus pro nadané)

---

### 44–45 min: REFLEXE + EXIT TICKET

**Exit ticket** (ústně nebo lístek):
> *„Jaký je rozdíl mezi `print()` uvnitř funkce a `return`?"*

**Uložení:** `Soubor → Uložit` → složka `Informatika/H41`  
Název souboru: `H41_funkce_jmeno.py`

---

## DIFERENCIACE

**Pomalejší žáci:**
- Kostra funkce připravena, žák doplní jen vzorec:
  ```python
  def obsah_ctverce(strana):
      return ___________   # doplň vzorec
  ```
- Soustředit se jen na úkoly 1–3, ne rozšíření

**Nadaní žáci:**
- Funkce s výchozí hodnotou parametru:
  ```python
  def pozdrav(jmeno="kamaráde"):
      return f"Ahoj, {jmeno}!"
  ```
- Rekurzivní funkce: faktoriál nebo Fibonacci (pokud znají)

---

## HODNOCENÍ V HODINĚ

- ✓ Pozorování – obcházení a kontrola hotových funkcí
- ✓ Exit ticket
- ✓ Sdílení na projektoru

---

## REFLEXE PO HODINĚ

Co se povedlo:    _____________________________________
Co příště jinak:  _____________________________________
Tempo / nestihli: _____________________________________
Technické problémy: __________________________________
