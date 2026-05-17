# Příprava na hodinu – Python soubory a chyby (8. ročník)

```
═══════════════════════════════════════════════════════
PŘÍPRAVA NA VYUČOVACÍ HODINU – INFORMATIKA
═══════════════════════════════════════════════════════

Datum:          _______________
Třída:          8.
Hodiny č.:      H4–H5  (dvouhodinový blok nebo dvě navazující hodiny)
Časová dotace:  2 × 45 minut (nebo 1 × 45 min – viz poznámka)
                → Při jedné hodině: jen H4 (soubory), H5 příště

NÁSTROJ:   ✓ Python – Thonny IDE

TEMATICKÝ CELEK: Blok 1 – Python pokročile
TÉMA HODINY:     Práce se soubory (open, with) + ošetření chyb (try/except)
```

---

## CÍLE HODINY

**Kognitivní:**
- Žák **vysvětlí**, proč programy potřebují číst a zapisovat soubory
- Žák **napíše** kód pro čtení a zápis textového souboru
- Žák **použije** `try/except` k zachycení chyby, aby program nespadl

**Procesní:**
- Žák odladí program, který „přežije" špatný vstup od uživatele
- Žák vytvoří jednoduchý textový deník

---

## VÝCHOZÍ ZNALOSTI

- Python: funkce, smyčky, podmínky, `input()`, `print()`
- Chápání, co je soubor a složka v systému
- (Výhodou) základy práce s řetězci: `.strip()`, `.split()`

**Ověření na začátku (2 min):**
```python
cislo = int(input("Zadej číslo: "))
print(cislo * 2)
```
*„Co se stane, pokud uživatel napíše ‚abc' místo čísla?"* → Program spadne s chybou. Proč? A jak to opravit?

---

## POMŮCKY A ZDROJE

- ✓ Počítačová učebna, Thonny IDE
- ✓ Projektor pro demo
- ✓ Startovní soubor `H04_start.py` (prázdný nebo s kostrou) na sdílené složce

---

## PRŮBĚH – HODINA H4: SOUBORY (45 min)

### 0–5 min: ZAHÁJENÍ / MOTIVACE

*„Naše programy zatím zapomínají – po skončení jsou data pryč. Jak to řeší aplikace jako zápisník nebo kontakty? Ukládají data do souboru. Dnes se to naučíme."*

---

### 5–20 min: DEMO – Čtení a zápis souborů

**Krok 1 – Zápis do souboru**

```python
# Otevři soubor pro zápis (w = write, přepisuje)
with open("poznamky.txt", "w", encoding="utf-8") as f:
    f.write("První řádek\n")
    f.write("Druhý řádek\n")

print("Soubor uložen.")
```

- Spusť → otevři `poznamky.txt` v Poznámkovém bloku → ukáž obsah
- *„`with` se postará o zavření souboru – vždy preferujeme tuto formu."*

**Krok 2 – Čtení souboru**

```python
with open("poznamky.txt", "r", encoding="utf-8") as f:
    obsah = f.read()

print(obsah)
```

**Krok 3 – Přidání záznamu (append)**

```python
# "a" = append – přidá na konec, nepřepisuje
with open("poznamky.txt", "a", encoding="utf-8") as f:
    f.write("Nový záznam\n")
```

**Krok 4 – Čtení po řádcích**

```python
with open("poznamky.txt", "r", encoding="utf-8") as f:
    for radek in f:
        print(radek.strip())  # strip odstraní \n na konci
```

---

### 20–40 min: SAMOSTATNÁ PRÁCE – Textový deník

**Zadání:**

Napiš program `denik.py`, který:

1. Zeptá se uživatele: *„Co chceš zapsat do deníku?"*
2. Přidá záznam do souboru `denik.txt` (ne přepsat – append!)
3. Po uložení vypíše celý obsah deníku

```
Výstup v terminálu:
>>> Co chceš zapsat? Dnes byl dobrý den.
Uloženo!

Celý deník:
Dnes byl dobrý den.
```

**Rozšíření:**
- Přidej datum a čas k záznamu (`import datetime`)
- Umožni výběr: 1 = přidat, 2 = zobrazit, 3 = konec

---

### 40–45 min: EXIT TICKET + ULOŽENÍ

**Exit ticket:** *„Co dělá `with open(...) as f:`?"*  
**Uložení:** složka `Informatika/H04`, soubor `denik.py`

---

## PRŮBĚH – HODINA H5: TRY/EXCEPT (45 min)

### 0–5 min: ZAHÁJENÍ / MOTIVACE

- Spusť záměrně program ze start souboru, který spadne:
  ```python
  cislo = int(input("Zadej číslo: "))
  print(f"Dvojnásobek je {cislo * 2}")
  ```
  → zadej `abc` → `ValueError: invalid literal for int()`

*„Uživatelé nejsou programátoři – vždy zadají špatný vstup. Program nesmí spadnout. Jak to opravit?"*

---

### 5–22 min: DEMO – try/except

**Krok 1 – Základní try/except**

```python
try:
    cislo = int(input("Zadej číslo: "))
    print(f"Dvojnásobek je {cislo * 2}")
except ValueError:
    print("Chyba: to není číslo!")
```

- *„`try` = zkus spustit tenhle blok. `except ValueError` = pokud vznikla chyba tohoto typu, spusť tenhle blok."*

**Krok 2 – Opakování dokud je vstup správný**

```python
while True:
    try:
        cislo = int(input("Zadej číslo: "))
        break  # exit smyčky při úspěchu
    except ValueError:
        print("To není číslo, zkus to znovu.")

print(f"Zadal/a jsi: {cislo}")
```

**Krok 3 – Chyba při otevírání souboru**

```python
try:
    with open("neexistuje.txt", "r") as f:
        print(f.read())
except FileNotFoundError:
    print("Soubor nenalezen. Bude vytvořen nový.")
    with open("neexistuje.txt", "w") as f:
        f.write("")
```

- *„Tohle je typický vzor: zkus otevřít, pokud neexistuje – vytvoř prázdný."*

---

### 22–40 min: SAMOSTATNÁ PRÁCE – Odolný deník

**Zadání:**

Vylepši program `denik.py` z předchozí hodiny:

1. Při spuštění: pokud `denik.txt` neexistuje, vytvoř ho (FileNotFoundError)
2. Přidej funkci `pridej_zaznam()`:
   - Zeptá se uživatele
   - Pokud zadá prázdný řetězec → upozorní a nepřidá
3. Přidej funkci `zobraz_denik()`:
   - Zobrazí číslované záznamy
   - Pokud je soubor prázdný → vypíše „Deník je prázdný"

**Bonus:**
- Přidej `except Exception as e: print(f"Neočekávaná chyba: {e}")` – zachytí cokoliv

---

### 40–44 min: SDÍLENÍ + PREZENTACE

- 1–2 žáci ukáží svůj deník + záměrně způsobí chybu → program přežije

---

### 44–45 min: EXIT TICKET

**Exit ticket:** *„Napiš dva různé typy chyb, které try/except může zachytit."*  
**Uložení:** `denik.py` ve složce `Informatika/H05`

---

## DIFERENCIACE

**Pomalejší žáci:**
- Kostra deníku připravena, doplnit jen `open()` a `try/except`
- Zaměřit se jen na základní try/except bez smyčky

**Nadaní žáci:**
- `except (ValueError, TypeError) as e:` – pojmenování chyby
- Zápis a čtení JSON souboru (`import json`)
- Deník s více záznamy a vyhledáváním klíčového slova

---

## HODNOCENÍ V HODINĚ

- ✓ Pozorování – funguje program při špatném vstupu?
- ✓ Exit ticket (2 typy chyb)
- ✓ Sdílení a záměrné vyvolání chyby

---

## REFLEXE PO HODINĚ

Co se povedlo:    _____________________________________
Co příště jinak:  _____________________________________
Tempo / nestihli: _____________________________________
Technické problémy: __________________________________
