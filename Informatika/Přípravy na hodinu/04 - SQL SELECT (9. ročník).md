# Příprava na hodinu – SQL SELECT (9. ročník)

```
═══════════════════════════════════════════════════════
PŘÍPRAVA NA VYUČOVACÍ HODINU – INFORMATIKA
═══════════════════════════════════════════════════════

Datum:          _______________
Třída:          9.
Hodina č.:      H45  (celkové pořadí v tematickém plánu; v rámci bloku SQL)
Časová dotace:  45 minut

NÁSTROJ:   ✓ sqliteonline.com (v prohlížeči, bez instalace)
           ✓ Připravená školní databáze v souboru skola.db (nebo SQL skript)

TEMATICKÝ CELEK: Blok 2 – Databáze a SQL
TÉMA HODINY:     SQL SELECT – dotazy, filtrování (WHERE), řazení (ORDER BY)
```

---

## CÍLE HODINY

**Kognitivní:**
- Žák **přečte** a **napíše** základní SQL SELECT dotaz
- Žák **použije** klauzule `WHERE`, `ORDER BY`, `LIMIT`
- Žák **vysvětlí** strukturu databázové tabulky (řádky, sloupce, typy)

**Procesní:**
- Žák zodpoví konkrétní otázky o datech pomocí SQL dotazů
- Žák interpretuje výsledky dotazu (ne jen napíše SQL, ale řekne, co znamenají)

---

## VÝCHOZÍ ZNALOSTI

- Obecná představa o databázi (tabulka = excelovský list)
- Python: seznamy a slovníky (analogie s DB)
- (Výhodou) základy Excelu nebo filtry v tabulkovém procesoru

**Ověření na začátku (2 min):**  
Promítnout tabulku `zaci` (viz níže) a zeptat se: *„Jak bychom v Excelu vybrali jen žáky z třídy 9A? Co kdyby tabulka měla 10 000 řádků?"*

---

## POMŮCKY A ZDROJE

- ✓ Počítačová učebna s přístupem na internet (sqliteonline.com)
- ✓ Projektor pro demo
- ✓ SQL skript `skola.sql` na sdílené složce (nebo zkopírovat příkaz CREATE níže)
- ✓ Pracovní list `H45_ukoly.pdf` s úkoly (nebo promítnout)

---

## DATABÁZE PRO HODINU

Jednoduchá školní databáze (SQL skript – spustit v sqliteonline.com):

```sql
CREATE TABLE zaci (
    id       INTEGER PRIMARY KEY,
    jmeno    TEXT,
    prijmeni TEXT,
    trida    TEXT,
    prumer   REAL,
    mesto    TEXT
);

INSERT INTO zaci VALUES
(1,  'Jana',    'Nováková',  '9A', 1.5, 'Praha'),
(2,  'Tomáš',   'Dvořák',    '9B', 2.3, 'Brno'),
(3,  'Petra',   'Horáková',  '9A', 1.2, 'Praha'),
(4,  'Martin',  'Novák',     '9C', 3.1, 'Ostrava'),
(5,  'Lucie',   'Svobodová', '9B', 1.8, 'Praha'),
(6,  'Ondřej',  'Procházka', '9A', 2.7, 'Brno'),
(7,  'Eva',     'Kučerová',  '9C', 1.1, 'Praha'),
(8,  'Jakub',   'Veselý',    '9B', 2.0, 'Ostrava'),
(9,  'Tereza',  'Marková',   '9A', 1.6, 'Brno'),
(10, 'Filip',   'Jelínek',   '9C', 2.9, 'Praha');

CREATE TABLE predmety (
    id      INTEGER PRIMARY KEY,
    nazev   TEXT,
    ucitel  TEXT
);

INSERT INTO predmety VALUES
(1, 'Matematika', 'Ing. Kratochvíl'),
(2, 'Čeština',    'Mgr. Horáčková'),
(3, 'Informatika', 'Mgr. Procházka'),
(4, 'Angličtina', 'Mgr. Svoboda');
```

---

## PRŮBĚH HODINY

### 0–5 min: ZAHÁJENÍ / MOTIVACE

Spusť prohlížeč, otevři sqliteonline.com.  
Promítnout tabulku žáků (v Excelu nebo obrázek).

*„Google, Facebook, banky – vše běží na databázích. Programátor musí umět se na data zeptat. Databáze se dotazujeme jazykem SQL. Dnes se naučíme základy – a skutečně vyzkoušíme na datech."*

---

### 5–10 min: NASTAVENÍ PROSTŘEDÍ

- Žáci otevřou sqliteonline.com
- Spustí SQL skript (přepíšou demo databázi): vložit `CREATE TABLE` + `INSERT INTO` do editoru → Run
- Ověření: levý panel zobrazí tabulky `zaci` a `predmety`
- Pokud není internet: záložní plán – SQLite soubor přes USB, nebo papírová cvičení

---

### 10–25 min: DEMO (učitel ukazuje, žáci sledují)

**Krok 1 – SELECT vše**

```sql
SELECT * FROM zaci;
```
→ Zobrazí všechny sloupce a řádky.  
*„Hvězdička = všechny sloupce."*

**Krok 2 – SELECT konkrétní sloupce**

```sql
SELECT jmeno, prijmeni, trida FROM zaci;
```
*„Vybereme jen to, co potřebujeme."*

**Krok 3 – WHERE (filtrování)**

```sql
-- Jen žáci z 9A
SELECT * FROM zaci WHERE trida = '9A';

-- Jen žáci s průměrem lepším než 2.0
SELECT jmeno, prijmeni, prumer FROM zaci WHERE prumer < 2.0;

-- Žáci z Prahy
SELECT jmeno, prijmeni FROM zaci WHERE mesto = 'Praha';
```

**Krok 4 – ORDER BY (řazení)**

```sql
-- Seřadit podle průměru (nejlepší první)
SELECT jmeno, prijmeni, prumer FROM zaci ORDER BY prumer ASC;

-- Nejhorší průměr první
SELECT jmeno, prijmeni, prumer FROM zaci ORDER BY prumer DESC;
```

**Krok 5 – LIMIT (omezení počtu výsledků)**

```sql
-- Top 3 nejlepší žáci
SELECT jmeno, prijmeni, prumer FROM zaci ORDER BY prumer ASC LIMIT 3;
```

---

### 25–42 min: SAMOSTATNÁ PRÁCE

**Úkoly (promítnout nebo pracovní list):**

Pomocí SQL dotazů odpověz na otázky:

1. Vypiš všechny žáky z třídy `9C`.  
   *(výsledek: 3 žáci)*

2. Kdo má průměr horší než 2.5?  
   *(výsledek: Martin Novák 3.1, Filip Jelínek 2.9, Ondřej Procházka 2.7)*

3. Seřaď všechny žáky podle příjmení abecedně.

4. Vypiš jen jméno a příjmení 5 nejlepších žáků školy.

5. Kolik žáků bydlí v Praze? *(napřed vypiš, pak spočítej sám/a)*

**Rozšíření (pro rychlejší):**

```sql
-- Počet žáků v každé třídě
SELECT trida, COUNT(*) AS pocet_zaku FROM zaci GROUP BY trida;

-- Průměrný prospěch třídy
SELECT trida, AVG(prumer) AS prumer_tridy FROM zaci GROUP BY trida;

-- Žáci z Prahy s průměrem < 2.0
SELECT jmeno, prijmeni, prumer FROM zaci
WHERE mesto = 'Praha' AND prumer < 2.0;
```

---

### 42–44 min: SDÍLENÍ / PREZENTACE

- 1–2 žáci ukáží zajímavý dotaz (např. kombinaci WHERE + ORDER BY)
- Třída: *„Co dotaz říká? Co jsme zjistili o datech?"*

---

### 44–45 min: EXIT TICKET + ULOŽENÍ

**Exit ticket:**
> *„Napiš SQL dotaz, který vypíše jméno a příjmení všech žáků z Brna."*  
> (Správná odpověď: `SELECT jmeno, prijmeni FROM zaci WHERE mesto = 'Brno';`)

**Uložení:** sqliteonline.com umí exportovat SQL skript (File → Export) nebo zkopírovat hotové dotazy do `H45_dotazy.sql`

---

## DIFERENCIACE

**Pomalejší žáci:**
- Připravit „SQL tahák" na lístku:
  ```
  SELECT sloupce FROM tabulka
  WHERE podminka
  ORDER BY sloupec ASC/DESC
  LIMIT pocet;
  ```
- Zaměřit se jen na kroky 1–3, ne ORDER BY + LIMIT

**Nadaní žáci:**
- `GROUP BY` s `COUNT()` a `AVG()` (viz rozšíření)
- `JOIN` – propojení tabulek žáci + předměty (pokud je čas)
- Dobrovolný úkol: navrhnout vlastní tabulku a napsat k ní 5 dotazů

---

## HODNOCENÍ V HODINĚ

- ✓ Pozorování – správnost dotazů, interpretace výsledků
- ✓ Exit ticket (konkrétní SQL dotaz)
- ✓ Sdílení na projektoru

---

## REFLEXE PO HODINĚ

Co se povedlo:    _____________________________________
Co příště jinak:  _____________________________________
Tempo / nestihli: _____________________________________
Technické problémy: __________________________________
