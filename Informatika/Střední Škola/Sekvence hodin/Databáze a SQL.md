# Databáze a SQL – Sekvence hodin (SŠ úroveň)

**Navazuje na:** Datová analýza (8.r. ZŠ – CSV, Excel, Python základy)  
**Doporučený ročník:** 1.–2. ročník SŠ (SOŠ Informatika, Gymnázium IT)  
**Počet hodin:** 8 (H13–H20 dle původní sekvence 8.r.)

---

## H13 – Úvod do relačních databází

**Cíl:** Porozumět, proč existují databáze a jaký je rozdíl oproti tabulkám/CSV.

### Proč databáze?
| Problém s CSV/Excel | Řešení v DB |
|--------------------|-------------|
| Duplicitní data | Normalizace – data na jednom místě |
| Nekonzistence (různé názvy města) | Cizí klíče |
| Pomalé hledání v milionech záznamů | Indexy |
| Více uživatelů najednou | Transakce, ACID |

### Základní pojmy
| Pojem | Vysvětlení | Příklad |
|-------|-----------|---------|
| **Tabulka** (relace) | Soubor dat stejného typu | `zakaznici`, `objednavky` |
| **Řádek** (záznam) | Jeden konkrétní objekt | Zákazník Jan Novák |
| **Sloupec** (atribut) | Vlastnost objektů | `jmeno`, `email`, `datum_narozeni` |
| **Primární klíč (PK)** | Jedinečný identifikátor záznamu | `id` – číslo automaticky rostoucí |
| **Cizí klíč (FK)** | Odkaz na PK v jiné tabulce | `zakaznik_id` v tabulce `objednavky` |
| **Relace** | Vztah mezi tabulkami | Zákazník má mnoho objednávek |

### Typy relací
- **1:N** (jeden k mnoha) – zákazník → objednávky
- **N:M** (mnoho k mnoha) – student ↔ kurzy (přes vazební tabulku)
- **1:1** – osoba → pas

---

## H14 – ER Diagram (Entity-Relationship)

**Cíl:** Nakreslit databázové schéma před implementací.

### Notace ER diagramu

```
[ZÁKAZNÍK]          [OBJEDNÁVKA]         [PRODUKT]
├── id (PK)         ├── id (PK)          ├── id (PK)
├── jmeno           ├── datum            ├── nazev
├── email           ├── zakaznik_id (FK) ├── cena
└── telefon         └── celkova_cena     └── sklad_ks
        1               N  M                 N
        └───────────────┘  └─────────────────┘
                           [POLOZKA_OBJEDNAVKY]
                           ├── objednavka_id (FK)
                           ├── produkt_id (FK)
                           └── pocet_ks
```

### Cvičení H14 – navrhni ER diagram pro:
1. **Knihovnu:** Knihy, Čtenáři, Výpůjčky
2. **Školu:** Žáci, Třídy, Učitelé, Předměty, Známky
3. **E-shop:** Zákazníci, Produkty, Objednávky, Kategorie

### Pravidla normalizace (základní)
- **1NF:** Každá buňka obsahuje jednu hodnotu (ne seznam)
- **2NF:** Neexistuje částečná závislost na PK
- **3NF:** Neexistují tranzitivní závislosti

---

## H15 – SQL SELECT – Dotazování

**Cíl:** Naučit se číst data z databáze pomocí SELECT.

### Základní syntaxe

```sql
SELECT sloupce
FROM tabulka
WHERE podmínka
ORDER BY sloupec ASC/DESC
LIMIT pocet;
```

### Příklady – tabulka `zakaznici`

```sql
-- Všichni zákazníci
SELECT * FROM zakaznici;

-- Pouze jméno a email
SELECT jmeno, email FROM zakaznici;

-- Zákazníci z Prahy, seřazení dle jména
SELECT jmeno, mesto FROM zakaznici
WHERE mesto = 'Praha'
ORDER BY jmeno ASC;

-- Prvních 5 zákazníků
SELECT * FROM zakaznici LIMIT 5;

-- Zákazníci jejichž jméno začíná na "Nov"
SELECT * FROM zakaznici WHERE jmeno LIKE 'Nov%';

-- Počet zákazníků z každého města
SELECT mesto, COUNT(*) AS pocet
FROM zakaznici
GROUP BY mesto
ORDER BY pocet DESC;
```

### Agregační funkce
| Funkce | Popis |
|--------|-------|
| `COUNT(*)` | Počet záznamů |
| `SUM(sloupec)` | Součet hodnot |
| `AVG(sloupec)` | Průměr |
| `MAX(sloupec)` | Maximum |
| `MIN(sloupec)` | Minimum |

---

## H16 – SQL INSERT, UPDATE, DELETE

**Cíl:** Naučit se přidávat, měnit a mazat data.

```sql
-- Přidání záznamu
INSERT INTO zakaznici (jmeno, email, mesto)
VALUES ('Eva Dvořáčková', 'eva@example.com', 'Brno');

-- Úprava záznamu
UPDATE zakaznici
SET email = 'nova.eva@example.com'
WHERE id = 5;

-- Smazání záznamu
DELETE FROM zakaznici
WHERE id = 5;

-- POZOR: bez WHERE smaže VSE!
-- DELETE FROM zakaznici;  ← NEBEZPEČNÉ
```

### Vytvoření tabulky (DDL)
```sql
CREATE TABLE zakaznici (
    id      INTEGER PRIMARY KEY AUTOINCREMENT,
    jmeno   TEXT NOT NULL,
    email   TEXT UNIQUE,
    mesto   TEXT DEFAULT 'neuvedeno'
);
```

---

## H17 – SQL JOIN – Spojování tabulek

**Cíl:** Získat data z více propojených tabulek.

### Schéma pro cvičení
```
zakaznici (id, jmeno, email)
objednavky (id, datum, zakaznik_id, celkova_cena)
```

### INNER JOIN – pouze záznamy s vazbou v obou tabulkách
```sql
SELECT z.jmeno, o.datum, o.celkova_cena
FROM zakaznici z
INNER JOIN objednavky o ON z.id = o.zakaznik_id
ORDER BY o.datum DESC;
```

### LEFT JOIN – všichni zákazníci, i bez objednávek
```sql
SELECT z.jmeno, COUNT(o.id) AS pocet_objednavek
FROM zakaznici z
LEFT JOIN objednavky o ON z.id = o.zakaznik_id
GROUP BY z.id, z.jmeno
ORDER BY pocet_objednavek DESC;
```

### Komplexnější dotaz – top zákazníci
```sql
SELECT
    z.jmeno,
    z.mesto,
    COUNT(o.id)           AS pocet_objednavek,
    SUM(o.celkova_cena)   AS celkem_utraceno,
    AVG(o.celkova_cena)   AS prumerna_objednavka
FROM zakaznici z
LEFT JOIN objednavky o ON z.id = o.zakaznik_id
GROUP BY z.id
HAVING celkem_utraceno > 5000
ORDER BY celkem_utraceno DESC;
```

---

## H18 – Python + SQLite

**Cíl:** Pracovat s SQLite databází přímo z Pythonu pomocí modulu `sqlite3`.

### Připojení a vytvoření tabulky
```python
import sqlite3

# Připojení (vytvoří soubor db.sqlite3 pokud neexistuje)
conn = sqlite3.connect("adresar.db")
cursor = conn.cursor()

# Vytvoření tabulky
cursor.execute("""
    CREATE TABLE IF NOT EXISTS kontakty (
        id      INTEGER PRIMARY KEY AUTOINCREMENT,
        jmeno   TEXT NOT NULL,
        telefon TEXT,
        email   TEXT
    )
""")
conn.commit()
```

### CRUD operace v Pythonu
```python
# CREATE – přidání záznamu (parametrizovaný dotaz – bezpečné!)
def pridat_kontakt(jmeno, telefon, email):
    cursor.execute(
        "INSERT INTO kontakty (jmeno, telefon, email) VALUES (?, ?, ?)",
        (jmeno, telefon, email)
    )
    conn.commit()
    print(f"Přidán kontakt: {jmeno}")

# READ – výpis všech kontaktů
def vypsat_kontakty():
    cursor.execute("SELECT * FROM kontakty ORDER BY jmeno")
    radky = cursor.fetchall()
    for radek in radky:
        print(f"[{radek[0]}] {radek[1]} | {radek[2]} | {radek[3]}")

# UPDATE – úprava telefonního čísla
def upravit_telefon(kontakt_id, novy_telefon):
    cursor.execute(
        "UPDATE kontakty SET telefon = ? WHERE id = ?",
        (novy_telefon, kontakt_id)
    )
    conn.commit()

# DELETE – smazání kontaktu
def smazat_kontakt(kontakt_id):
    cursor.execute("DELETE FROM kontakty WHERE id = ?", (kontakt_id,))
    conn.commit()

# Vyhledávání
def hledat(dotaz):
    cursor.execute(
        "SELECT * FROM kontakty WHERE jmeno LIKE ?",
        (f"%{dotaz}%",)
    )
    return cursor.fetchall()

# Ukázka použití
pridat_kontakt("Jan Novák", "603 111 222", "jan@example.com")
pridat_kontakt("Eva Dvořáčková", "777 333 444", "eva@example.com")
vypsat_kontakty()
```

### Uzavření spojení
```python
conn.close()
# Nebo lépe – context manager:
with sqlite3.connect("adresar.db") as conn:
    cursor = conn.cursor()
    # ... operace ...
```

---

## H19–H20 – Projekt: Databázová aplikace

**Cíl:** Navrhnout a implementovat kompletní Python aplikaci s SQLite backendem.

### Výběr projektu (žák si vybere 1)

#### Varianta A: Digitální adresář
- Tabulky: `kontakty` (id, jmeno, telefon, email, skupina)
- Funkce: CRUD, hledání, třídění, export do CSV
- Bonus: skupiny kontaktů, import z CSV

#### Varianta B: E-shop skladový systém
- Tabulky: `produkty` (id, nazev, cena, kategorie, sklad_ks), `prodeje` (id, produkt_id, pocet, datum)
- Funkce: CRUD produktů, evidovat prodeje, statistiky prodeje
- Bonus: automatické snižování skladu, upozornění na nízký sklad

#### Varianta C: Školní deník
- Tabulky: `zaci` (id, jmeno, trida), `predmety` (id, nazev), `znamky` (id, zak_id, predmet_id, znamka, datum)
- Funkce: přidat žáka, zadat známku, průměr žáka, nejlepší/nejhorší žák
- Bonus: váhovaný průměr, export výpisu

### Hodnotící kritéria
| Kritérium | Body |
|-----------|------|
| Funkční databázové schéma (alespoň 2 tabulky, PK, FK) | 20 |
| CRUD operace implementovány | 30 |
| Alespoň 1 JOIN dotaz nebo agregace | 20 |
| Parametrizované dotazy (bezpečnost) | 10 |
| Uživatelské rozhraní (menu) | 10 |
| Komentáře v kódu + README | 10 |
| **Celkem** | **100** |
