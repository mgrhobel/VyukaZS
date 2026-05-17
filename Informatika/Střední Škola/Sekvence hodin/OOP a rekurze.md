# OOP a rekurze – Sekvence hodin (SŠ úroveň)

**Navazuje na:** Python základy (8.r. ZŠ – funkce, slovníky, soubory)  
**Doporučený ročník:** 1. ročník SŠ (SOŠ Informatika, Gymnázium)  
**Počet hodin:** 3 (H7–H9 dle původní sekvence 8.r.)

---

## H7 – Objektově orientované programování I

**Cíl:** Pochopit princip objektu, třídy, atributů a metod.

### Teorie – Co je OOP?
- Objekt = entita se **stavem** (atributy) a **chováním** (metody)
- Třída = šablona (blueprint) pro vytváření objektů
- Instance = konkrétní objekt vzniklý z třídy

### Syntaxe – základní třída

```python
class Auto:
    def __init__(self, znacka, rok):
        self.znacka = znacka    # atribut instance
        self.rok = rok

    def info(self):
        return f"{self.znacka} ({self.rok})"

    def vek(self):
        from datetime import date
        return date.today().year - self.rok

# Vytvoření instance
moje_auto = Auto("Škoda", 2018)
print(moje_auto.info())   # Škoda (2018)
print(moje_auto.vek())    # počet let od 2018
```

### Klíčové pojmy
| Pojem | Vysvětlení |
|-------|-----------|
| `class` | Definice třídy |
| `__init__` | Konstruktor – volá se při vytvoření objektu |
| `self` | Odkaz na aktuální instanci |
| atribut | Proměnná patřící objektu (`self.znacka`) |
| metoda | Funkce definovaná uvnitř třídy |

### Cvičení H7
1. Vytvoř třídu `Osoba` s atributy `jmeno`, `vek` a metodou `pozdrav()`, která vrátí `"Ahoj, jsem {jmeno}!"`.
2. Vytvoř třídu `Kruh` s atributem `polomer` a metodami `obvod()` a `obsah()`.
3. Vytvoř seznam 5 instancí `Auto` a vypiš přehlednou tabulku (znacka, rok, vek).

### Třídní proměnné vs. instanční proměnné

```python
class Banka:
    urokova_sazba = 0.03  # třídní proměnná (sdílená všemi instancemi)

    def __init__(self, majitel, zustatek):
        self.majitel = majitel      # instanční proměnná
        self.zustatek = zustatek

    def pripisUrok(self):
        self.zustatek *= (1 + Banka.urokova_sazba)

b1 = Banka("Petr", 10000)
b2 = Banka("Jana", 5000)
print(b1.urokova_sazba)  # 0.03 – z třídy
Banka.urokova_sazba = 0.05  # změní pro VŠECHNY instance
```

---

## H8 – Objektově orientované programování II – Dědičnost

**Cíl:** Pochopit dědičnost, polymorfismus a přepisování metod.

### Dědičnost – základ

```python
class Auto:
    def __init__(self, znacka, rok, spotreba):
        self.znacka = znacka
        self.rok = rok
        self.spotreba = spotreba   # l/100 km

    def info(self):
        return f"{self.znacka} ({self.rok}), {self.spotreba} l/100km"

    def cena_jizdy(self, km, cena_za_litr):
        return km / 100 * self.spotreba * cena_za_litr


class ElektrickeAuto(Auto):  # ElektrickeAuto DĚDÍ od Auto
    def __init__(self, znacka, rok, dojezd_km):
        super().__init__(znacka, rok, 0)  # volání konstruktoru rodiče
        self.dojezd_km = dojezd_km

    def info(self):  # přepsání (override) metody rodiče
        return f"{self.znacka} ({self.rok}), elektro, dojezd {self.dojezd_km} km"

    def cena_jizdy(self, km, cena_kwh=4.5):
        spotreba_kwh_100km = 18  # průměr elektrického auta
        return km / 100 * spotreba_kwh_100km * cena_kwh


# Použití
auta = [
    Auto("Škoda Octavia", 2018, 6.5),
    Auto("VW Golf", 2020, 5.8),
    ElektrickeAuto("Tesla Model 3", 2022, 550),
    ElektrickeAuto("Škoda Enyaq", 2023, 510),
]

for auto in auta:
    print(auto.info())
    print(f"  Jízda 100 km: {auto.cena_jizdy(100):.2f} Kč")
```

### Klíčové pojmy dědičnosti
| Pojem | Vysvětlení |
|-------|-----------|
| Dědičnost | Podtřída přebírá atributy a metody nadtřídy |
| `super()` | Odkaz na nadtřídu (rodiče) |
| Override | Podtřída přepíše metodu rodiče |
| Polymorfismus | Stejný kód funguje s různými typy objektů |

### Cvičení H8
1. Vytvoř hierarchii: `Zvire` → `Pes`, `Kocka`, `Ptak`. Každé zvíře má `jmeno`, `vek`, metodu `zvuk()` a `let()` (jen Ptak).
2. Rozšiř třídu `Osoba` → `Student(Osoba)` s atributem `studijni_obor` a metodou `studijni_info()`.
3. Vytvoř program, který spravuje seznam různých vozidel (`Auto`, `ElektrickeAuto`, `Motorka`) a seřadí je dle ceny jízdy na 200 km.

### Speciální metody (dunder/magic methods)
```python
class Zlomek:
    def __init__(self, citatel, jmenovatel):
        self.c = citatel
        self.j = jmenovatel

    def __str__(self):         # pro print()
        return f"{self.c}/{self.j}"

    def __repr__(self):        # pro debugger/REPL
        return f"Zlomek({self.c}, {self.j})"

    def __add__(self, other):  # pro operátor +
        return Zlomek(self.c * other.j + other.c * self.j, self.j * other.j)

    def __eq__(self, other):   # pro ==
        return self.c * other.j == other.c * self.j

a = Zlomek(1, 3)
b = Zlomek(1, 6)
print(a + b)   # 9/18
print(a == b)  # False
```

---

## H9 – Rekurze

**Cíl:** Pochopit princip rekurze, kdy ji použít a jaká jsou omezení.

### Co je rekurze?
Funkce, která **volá sama sebe**, dokud nedosáhne základního případu (base case).

### Faktoriál
```python
def faktorial(n):
    if n <= 1:          # base case
        return 1
    return n * faktorial(n - 1)  # rekurzivní případ

print(faktorial(5))  # 120 = 5 * 4 * 3 * 2 * 1
```

**Rekurzní strom pro faktorial(4):**
```
faktorial(4)
  └─ 4 * faktorial(3)
         └─ 3 * faktorial(2)
                └─ 2 * faktorial(1)
                       └─ 1  (base case)
```

### Fibonacciho posloupnost
```python
def fib(n):
    if n <= 1:
        return n
    return fib(n - 1) + fib(n - 2)

# Problém: exponenciální složitost O(2^n) – pro n=40 trvá sekundy
for i in range(10):
    print(fib(i), end=" ")  # 0 1 1 2 3 5 8 13 21 34
```

### Memoization – optimalizace rekurze
```python
from functools import lru_cache

@lru_cache(maxsize=None)
def fib_memo(n):
    if n <= 1:
        return n
    return fib_memo(n - 1) + fib_memo(n - 2)

# Nyní O(n) – výsledky se ukládají do cache
print(fib_memo(100))  # okamžitě
```

### Binární vyhledávání (iterativní i rekurzivní)

```python
def bin_search(seznam, cil, levy=0, pravy=None):
    """Rekurzivní binární vyhledávání – seznam musí být seřazený."""
    if pravy is None:
        pravy = len(seznam) - 1

    if levy > pravy:
        return -1  # nenalezeno

    stred = (levy + pravy) // 2

    if seznam[stred] == cil:
        return stred
    elif seznam[stred] < cil:
        return bin_search(seznam, cil, stred + 1, pravy)
    else:
        return bin_search(seznam, cil, levy, stred - 1)


data = [2, 5, 8, 12, 16, 23, 38, 56, 72, 91]
print(bin_search(data, 23))   # 5 (index)
print(bin_search(data, 100))  # -1 (nenalezeno)
```

**Složitost:** O(log n) – pro 1 000 000 prvků max 20 kroků.

### Quicksort – rekurzivní třídění
```python
def quicksort(lst):
    if len(lst) <= 1:
        return lst
    pivot = lst[len(lst) // 2]
    levy  = [x for x in lst if x < pivot]
    stred = [x for x in lst if x == pivot]
    pravy = [x for x in lst if x > pivot]
    return quicksort(levy) + stred + quicksort(pravy)

print(quicksort([3, 6, 8, 10, 1, 2, 1]))  # [1, 1, 2, 3, 6, 8, 10]
```

### Kdy NEPOUŽÍVAT rekurzi
- Hluboká rekurze → `RecursionError` (Python limit ~1000 volání)
- Velké n bez memoization → exponenciální čas
- Iterativní řešení je většinou efektivnější v Pythonu

### Cvičení H9
1. Napiš rekurzivní funkci `mocnina(base, exp)` bez použití `**`.
2. Napiš rekurzivní funkci `reverse_string(s)` → vrátí obrácený řetězec.
3. Napiš rekurzivní funkci `soucet_cisel(n)` → součet 1+2+...+n.
4. Optimalizuj Fibonacci pomocí `@lru_cache` a porovnej rychlost pro n=35.
5. Implementuj binární vyhledávání iterativně a porovnej s rekurzivní verzí.
