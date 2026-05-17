# SŠ témata – Projekty a testy

**Obsah:** Testové otázky a projekty z Informatiky přesunuté z ZŠ příprav  
**Původ:** 8. ročník (Test č. 1, Závěrečný test, Projekt č. 1) + 9. ročník (Mediální gramotnost test, Projekt č. 1 Datový průzkum)  
**Doporučená úroveň:** 1.–2. ročník SŠ (SOŠ Informatika, Gymnázium)

---

## 9. ROČNÍK – Projekt č. 1: Datový průzkum (Python + API/CSV + matplotlib)

*Původně Projekt č. 1 v 9.r., nahrazen Excel/Sheets analýzou pro ZŠ. Tento projekt vyžaduje SŠ znalosti: requests, CSV, try/except, matplotlib.*

### Zadání pro žáky

Stáhni reálná data z internetu (API nebo CSV soubor) a zpracuj je v Pythonu.

**Povinné součásti:**
- ✓ Stažení dat (`requests.get` nebo načtení CSV) + zpracování JSON nebo CSV
- ✓ Aspoň 3 statistické výpočty (průměr, max, min, počet, …)
- ✓ Aspoň 2 grafy v matplotlib (různé typy)
- ✓ Interpretace: komentář v kódu + 5 vět co data říkají
- ✓ Ošetření výjimek (sítě, chybný formát dat)

**Doporučené zdroje dat:**
- Počasí: `api.open-meteo.com` (teploty, srážky)
- Kurzy: `api.frankfurter.app` (měnové kurzy)
- Sporty: football-data.org nebo csv ze kaggle.com

**Prezentace:** 5 minut – grafy na obrazovce + interpretace

### Rubrika hodnocení

| Kritérium | Body |
|---|---|
| Stažení a zpracování dat (funkční kód) | 3 |
| Statistické výpočty (správně, min 3) | 2 |
| Grafy (2 různé typy, správně popsané) | 3 |
| Interpretace a prezentace | 2 |
| **Max** | **10** |

### Příklad kódu (matplotlib + API)

```python
import requests
import matplotlib.pyplot as plt

url = "https://api.open-meteo.com/v1/forecast?latitude=50.08&longitude=14.44&daily=temperature_2m_max&timezone=Europe/Prague&past_days=30"
try:
    odpoved = requests.get(url, timeout=10)
    data = odpoved.json()
    teploty = data["daily"]["temperature_2m_max"]
    dny = list(range(1, len(teploty) + 1))
    prumer = sum(teploty) / len(teploty)
    print(f"Průměr: {prumer:.1f} °C, Max: {max(teploty)} °C")

    plt.figure(figsize=(10, 4))
    plt.plot(dny, teploty, marker="o", label="Max. teplota")
    plt.axhline(prumer, color="red", linestyle="--", label=f"Průměr {prumer:.1f}°C")
    plt.xlabel("Den"); plt.ylabel("°C"); plt.title("Denní max. teplota – Praha")
    plt.legend(); plt.tight_layout(); plt.show()
except Exception as e:
    print(f"Chyba: {e}")
```

---

## 8. ROČNÍK – Test č. 1 (SŠ části: soubory, lambda, sorted)

*Původně součást Testu č. 1 z 8.r., nahrazen ZŠ variantami.*

### Otázka: Čtení souboru a try/except (4 body)

**Zadání:** Popiš, co dělá tato funkce (aspoň 3 věty). Co vrátí při volání `spocitej("poznamky.txt")`?

```python
def spocitej(nazev_souboru):
    pocet = 0
    try:
        with open(nazev_souboru, "r", encoding="utf-8") as f:
            for radek in f:
                if radek.startswith("#"):
                    pocet += 1
    except FileNotFoundError:
        return -1
    return pocet
```

**Vzorové řešení:** Funkce otevře soubor (čtení) a spočítá řádky začínající `#`. Pokud soubor neexistuje, vrátí -1 (ošetřeno přes `except FileNotFoundError`). Jinak vrátí počet komentářových řádků.

---

### Otázka: top_troje s sorted a lambda (4 body)

**Zadání:** Napiš funkci `top_troje(slovnik)`, která:
- Přijme slovník `{jmeno: body}` (jméno = string, body = číslo)
- Vrátí seznam 3 jmen s nejvyšším počtem bodů (sestupně dle bodů)
- Příklad: `top_troje({"Anna":85,"Bořek":62,"Cyril":91,"Dana":74})` → `["Cyril","Anna","Dana"]`

**Vzorové řešení:**
```python
def top_troje(slovnik):
    serazene = sorted(slovnik.items(), key=lambda x: x[1], reverse=True)
    return [jmeno for jmeno, _ in serazene[:3]]

print(top_troje({"Anna":85,"Bořek":62,"Cyril":91,"Dana":74}))
# → ["Cyril", "Anna", "Dana"]
```

---

### Otázka: CSV DictReader (3 body)

**Zadání:** Co dělá tento Python kód? Napiš, co vypíše výstup (přibližně).

```python
import csv

with open("teploty.csv", newline="", encoding="utf-8") as f:
    ctecka = csv.DictReader(f)
    data = list(ctecka)

teploty = [float(r["teplota"]) for r in data]
prumer = sum(teploty) / len(teploty)
maximum = max(teploty)

print(f"Průměr: {prumer:.1f} °C")
print(f"Maximum: {maximum} °C")
tepla = [r["mesic"] for r in data if float(r["teplota"]) > prumer]
print("Teplejší než průměr:", tepla)
```

**Vzorové řešení:** Kód čte CSV soubor s měsíci a teplotami. Přes `csv.DictReader` každý řádek stane slovníkem (`{"mesic": ..., "teplota": ...}`). Kód vypočítá průměr a maximum. `tepla` = seznam měsíců, kde teplota > průměr. Výstup závisí na datech v souboru – žák popíše logiku.

---

## 8. ROČNÍK – Test č. 1 (OOP část)

*Původně součást Testu č. 1 z 8.r., nahrazen dict/list variantou pro ZŠ.*

### ČÁST B – Otázka 3: Objektově orientované programování (8 bodů)

**Zadání:**
```python
class Kniha:
    celkem_knih = 0  # třídní proměnná

    def __init__(self, nazev, autor, rok):
        self.nazev = nazev
        self.autor = autor
        self.rok = rok
        Kniha.celkem_knih += 1

    def info(self):
        return f'"{self.nazev}" – {self.autor} ({self.rok})'

    @classmethod
    def pocet(cls):
        return cls.celkem_knih
```

**(a)** Co je `celkem_knih`? Jaký je rozdíl mezi třídní a instanční proměnnou? (2 body)

**(b)** Napiš kód, který vytvoří 3 instance třídy `Kniha` a vypíše jejich `info()`. (2 body)

**(c)** Kolik bude `Kniha.pocet()` po vytvoření 3 knih? Proč? (2 body)

**(d)** Rozšiř třídu `Kniha` o metodu `vek()`, která vrátí, kolik let uplynulo od vydání. (2 body)

### Klíč – Otázka 3

**(a)** `celkem_knih` je **třídní proměnná** – sdílená všemi instancemi třídy. Instanční proměnné (`self.nazev`) patří konkrétní instanci.

**(b)**
```python
k1 = Kniha("Malý princ", "Antoine de Saint-Exupéry", 1943)
k2 = Kniha("1984", "George Orwell", 1949)
k3 = Kniha("Babička", "Božena Němcová", 1855)
for k in [k1, k2, k3]:
    print(k.info())
```

**(c)** `Kniha.pocet()` vrátí `3`. Každý `__init__` inkrementuje `Kniha.celkem_knih += 1`.

**(d)**
```python
def vek(self):
    from datetime import date
    return date.today().year - self.rok
```

---

## 8. ROČNÍK – Závěrečný test (SŠ části)

*Původně součást Závěrečného testu 8.r., nahrazen ZŠ variantami.*

### ČÁST A – Otázka 1: OOP čtení kódu (10 bodů)

**Zadání – přečti kód a odpověz na otázky:**
```python
class Pocitadlo:
    def __init__(self, pocatecni=0):
        self.hodnota = pocatecni

    def zvys(self, o=1):
        self.hodnota += o
        return self  # umožňuje method chaining

    def vynuluj(self):
        self.hodnota = 0
        return self

    def __str__(self):
        return f"Pocitadlo({self.hodnota})"

p = Pocitadlo(10)
p.zvys().zvys(5).zvys()
print(p)
```

**(a)** Co se vytiskne? Zdůvodni. (3 body)

**(b)** Co znamená `return self`? Jak se tomu říká? (2 body)

**(c)** Přidej metodu `sniz(self, o=1)` se stejným chováním. (3 body)

**(d)** Vytvoř podtřídu `OmezenyPocitac(Pocitadlo)` s atributem `maximum`. Přepiš `zvys()` tak, aby hodnota nepřekročila `maximum`. (2 body)

### Klíč – ČÁST A Otázka 1

**(a)** Vytiskne se: `Pocitadlo(17)`  
Postup: `p = Pocitadlo(10)` → hodnota=10; `.zvys()` → 11; `.zvys(5)` → 16; `.zvys()` → 17

**(b)** `return self` vrátí objekt sám; umožňuje **method chaining** (řetězení metod) – volání více metod za sebou na jednom objektu.

**(c)**
```python
def sniz(self, o=1):
    self.hodnota -= o
    return self
```

**(d)**
```python
class OmezenyPocitac(Pocitadlo):
    def __init__(self, pocatecni=0, maximum=100):
        super().__init__(pocatecni)
        self.maximum = maximum

    def zvys(self, o=1):
        self.hodnota = min(self.hodnota + o, self.maximum)
        return self
```

---

### ČÁST B – SQL dotaz a bezpečnost (20 bodů)

**(Otázka 5) SQL dotaz (10 bodů)**

Máš tabulky:
```
zaci (id, jmeno, trida, prumer_znamek)
skoly (id, nazev, mesto)
zapis (zak_id, skola_id, rok)
```

Napiš SQL dotaz, který vrátí **jméno, třídu a název školy** pro všechny žáky z roku 2024, seřazené dle průměru (nejlepší první):

```sql
-- VZOROVÉ ŘEŠENÍ:
SELECT z.jmeno, z.trida, s.nazev AS skola
FROM zaci z
JOIN zapis zp ON z.id = zp.zak_id
JOIN skoly s  ON zp.skola_id = s.id
WHERE zp.rok = 2024
ORDER BY z.prumer_znamek ASC;
```

**(Otázka 6) SQL Injection (10 bodů)**

**(a)** Vysvětli, co je SQL injection. Uveď příklad útočného vstupu. (4 body)

**(b)** Proč je tento kód nebezpečný? (3 body)
```python
dotaz = f"SELECT * FROM zaci WHERE jmeno = '{uzivatelsky_vstup}'"
```

**(c)** Jak kód opravit? Napiš bezpečnou verzi. (3 body)

### Klíč – ČÁST B

**(Otázka 6a)** SQL injection = útok, kdy útočník vloží SQL kód do vstupního pole a manipuluje s databázovým dotazem.  
Příklad: vstup `' OR '1'='1` způsobí, že podmínka je vždy splněna → útočník se přihlásí bez hesla.

**(Otázka 6b)** Kód je nebezpečný, protože `uzivatelsky_vstup` je přímo vložen do SQL stringu. Pokud vstup obsahuje SQL, databáze ho vykoná.

**(Otázka 6c)**
```python
cursor.execute("SELECT * FROM zaci WHERE jmeno = ?", (uzivatelsky_vstup,))
```
Parametrizovaný dotaz – vstup je vždy data, nikdy SQL kód.

---

## 8. ROČNÍK – Projekt č. 1: Python + SQLite

*Původně jako Projekt č. 1 v 8.r., nahrazen Python+CSV variantou pro ZŠ.*

### Zadání: Databázová aplikace v Pythonu

Vytvoř konzolovou aplikaci s SQLite databází. Zvol si téma:

**Varianta A – Osobní adresář**
- Tabulka: `kontakty (id, jmeno, telefon, email, skupina)`
- Menu: [1] Přidat kontakt [2] Vyhledat [3] Upravit [4] Smazat [5] Výpis všech [6] Konec
- Bonus: export do CSV, import ze CSV

**Varianta B – E-shop systém**
- Tabulky: `produkty (id, nazev, cena, kategorie, sklad_ks)`, `objednavky (id, datum, celkem)`
- Menu: CRUD produktů + evidence objednávek
- Bonus: automatické snižování skladu

**Varianta C – Školní deník**
- Tabulky: `zaci (id, jmeno, trida)`, `predmety (id, nazev)`, `znamky (zak_id, predmet_id, znamka, datum)`
- Menu: přidat žáka, zadat známku, průměr, nejlepší žák
- Bonus: export výpisu, váhované průměry

### Požadavky (povinné)
1. ER diagram před implementací (nakresli na papír nebo v draw.io)
2. Alespoň 2 propojené tabulky s PK a FK
3. CRUD operace (Create, Read, Update, Delete)
4. Parametrizované SQL dotazy (bezpečnost!)
5. Uživatelské menu s validací vstupu
6. README.md s popisem aplikace

### Hodnocení
| Kritérium | Body |
|-----------|------|
| ER diagram | 15 |
| DB schéma (tabulky, PK, FK) | 20 |
| CRUD funkčnost | 25 |
| Alespoň 1 JOIN nebo GROUP BY | 15 |
| Parametrizované dotazy | 10 |
| Uživatelské rozhraní | 10 |
| README + komentáře | 5 |
| **Celkem** | **100** |

---

## 9. ROČNÍK – Mediální gramotnost – Test (SŠ části)

*Původně součást mediálního testu 9.r., nahrazen ZŠ variantami.*

### ČÁST A – Otázka 1: SQL Injection (5 bodů)

**Zadání:** Vysvětli, co je SQL injection útok. Uveď:
- (a) jak funguje (2 body)
- (b) příklad útočného vstupu do přihlašovacího formuláře (1 bod)
- (c) jak se mu bránit (2 body)

**Vzorové řešení:**

**(a)** SQL injection je útok, kdy útočník vloží SQL kód do vstupního pole webové aplikace. Pokud aplikace tento vstup přímo vloží do SQL dotazu (bez ošetření), databáze útočníkův kód vykoná.

**(b)** Přihlašovací pole heslo: `' OR '1'='1`  
Výsledný dotaz: `SELECT * FROM users WHERE password = '' OR '1'='1'` → podmínka je vždy splněna.

**(c)** Obrana: **parametrizované dotazy** (prepared statements) – vstup se předá databázi odděleně od SQL kódu, takže nemůže být interpretován jako SQL příkaz.

---

### ČÁST C – Otázka 7: SQL dotaz (5 bodů)

**Zadání:** Máš tabulku `zpravy (id, titulek, autor, datum, kategorie, zobrazeni)`.

Napiš SQL dotaz, který vrátí `titulek` a `autor` pro všechny zprávy z kategorie `"sport"`, seřazené dle počtu zobrazení od největšího.

**Vzorové řešení:**
```sql
SELECT titulek, autor
FROM zpravy
WHERE kategorie = 'sport'
ORDER BY zobrazeni DESC;
```

**Rozšiřující varianta (pro rychlé žáky):**
```sql
-- Top 5 autorů dle celkového počtu zobrazení ve sportu
SELECT autor, SUM(zobrazeni) AS celkem_zobrazeni
FROM zpravy
WHERE kategorie = 'sport'
GROUP BY autor
ORDER BY celkem_zobrazeni DESC
LIMIT 5;
```
