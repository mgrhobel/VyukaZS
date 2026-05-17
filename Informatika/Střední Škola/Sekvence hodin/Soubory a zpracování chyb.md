# SŠ Informatika – Python: Práce se soubory a zpracování chyb

> **Úroveň:** Střední škola (1. ročník oboru Informatika / gymnázium)  
> **Navazuje na:** Python funkce, slovníky, moduly – ZŠ 8. ročník  
> **RVP:** Nad rámec RVP ZV 2023; odpovídá RVP SOŠ Informatika a RVP G

---

## Část 1 – Práce se soubory (H4: 45 min)

### Proč programy potřebují soubory?

Programy bez souborů „zapomínají" – po ukončení jsou data pryč. Soubory zajistí trvalost dat.

### Zápis do souboru

```python
# Otevři soubor pro zápis (w = write, přepisuje existující)
with open("poznamky.txt", "w", encoding="utf-8") as f:
    f.write("První řádek\n")
    f.write("Druhý řádek\n")

print("Soubor uložen.")
```

> `with` zajistí automatické zavření souboru – vždy preferujeme tuto formu.

### Čtení souboru

```python
# Čtení celého souboru najednou
with open("poznamky.txt", "r", encoding="utf-8") as f:
    obsah = f.read()
print(obsah)

# Čtení po řádcích
with open("poznamky.txt", "r", encoding="utf-8") as f:
    for radek in f:
        print(radek.strip())  # strip() odstraní \n na konci
```

### Přidání záznamu (append)

```python
# "a" = append – přidá na konec, nepřepisuje
with open("poznamky.txt", "a", encoding="utf-8") as f:
    f.write("Nový záznam\n")
```

### Projekt: Textový deník

Napiš program `denik.py`, který:
1. Zeptá se uživatele: *„Co chceš zapsat?"*
2. Přidá záznam s aktuálním datem (`import datetime`) do souboru `denik.txt`
3. Po uložení vypíše celý obsah deníku

---

## Část 2 – Zpracování chyb: try/except (H5: 45 min)

### Proč programy padají?

```python
# Tento program spadne, pokud uživatel zadá text místo čísla:
cislo = int(input("Zadej číslo: "))
print(f"Dvojnásobek je {cislo * 2}")
# → ValueError: invalid literal for int() with base 10: 'abc'
```

### Základní try/except

```python
try:
    cislo = int(input("Zadej číslo: "))
    print(f"Dvojnásobek je {cislo * 2}")
except ValueError:
    print("Chyba: to není číslo!")
```

### Opakování dokud je vstup správný

```python
while True:
    try:
        cislo = int(input("Zadej číslo: "))
        break  # vyjde ze smyčky při úspěchu
    except ValueError:
        print("To není číslo, zkus to znovu.")

print(f"Zadal/a jsi: {cislo}")
```

### Zachycení chyby souboru

```python
try:
    with open("neexistuje.txt", "r") as f:
        print(f.read())
except FileNotFoundError:
    print("Soubor nenalezen. Bude vytvořen nový.")
    with open("neexistuje.txt", "w") as f:
        f.write("")
```

### Více typů výjimek + finally

```python
try:
    cislo = int(input("Zadej číslo: "))
    print(10 / cislo)
except ValueError:
    print("To není číslo!")
except ZeroDivisionError:
    print("Nulou dělit nelze!")
finally:
    print("Hotovo.")  # spustí se vždy, i při chybě
```

### Projekt: Odolný deník

Vylepši `denik.py`:
1. Pokud `denik.txt` neexistuje → vytvoř ho (ošetři FileNotFoundError)
2. Funkce `pridej_zaznam()` – odmítne prázdný vstup
3. Funkce `zobraz_denik()` – číslované záznamy; pokud prázdný → „Deník je prázdný"

---

## Proč je toto téma pro SŠ?

- RVP ZV 2023 pro ZŠ: programy s proměnnými, podmínkami, smyčkami, funkcemi → **bez file I/O a výjimek**
- `try/except` vyžaduje pochopení toku výjimek a typů chyb → abstraktní myšlení SŠ úrovně
- Práce se soubory (`open`, `with`) zavádí nový kontext (OS, cesty, kódování) → SŠ 1.r.
- Na ZŠ ošetřujeme špatný vstup pomocí `if` podmínek, ne výjimkami
