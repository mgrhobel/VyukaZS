# Příprava na hodinu – Návrh databáze – evidence dat (8. ročník)

```
═══════════════════════════════════════════════════════
PŘÍPRAVA NA VYUČOVACÍ HODINU – INFORMATIKA
═══════════════════════════════════════════════════════

Datum:          _______________
Třída:          8.
Hodina č.:      H14  (celkové pořadí v tematickém plánu)
Časová dotace:  45 minut

NÁSTROJ:   ✓ Papír + tužka (ER diagram – první část)
           ✓ sqliteonline.com nebo DB Browser for SQLite (druhá část)
           ✓ Projektor pro demo

TEMATICKÝ CELEK: Blok 2 – Databáze
TÉMA HODINY:     Návrh databázové struktury – tabulky, atributy, primární klíč, ER diagram
```

---

## CÍLE HODINY

**Kognitivní:**
- Žák **vymezí problém** a určí, jaká data bude třeba evidovat
- Žák **navrhne strukturu tabulky** (sloupce, datové typy, primární klíč)
- Žák **sestaví jednoduchý ER diagram** pro systém evidence dat (min. 2 tabulky)

**Procesní:**
- Žák samostatně navrhne tabulku pro zadaný reálný problém a vyzkouší ji v SQL (I-9-3-03)
- Žák zhodnotí svůj návrh: co funguje, co by šlo zlepšit (I-9-3-04)

**Vazba na RVP ZV 2023:** I-9-3-03 (vymezení problému, sestavení tabulky pro evidenci dat, nastavení pravidel), I-9-3-04 (testování a zhodnocení funkčnosti evidence)

---

## VÝCHOZÍ ZNALOSTI

- Pojmy: tabulka (řádky, sloupce), databáze, SQL SELECT (z H13–H15)
- Datové typy: text (TEXT), celé číslo (INTEGER), datum (DATE)
- Excel: rozdíl seznam vs. tabulka s relacemi

**Ověření na začátku (2 min):** *„Co je primární klíč? Proč nemůže mít dvě stejné hodnoty?"*

---

## POMŮCKY A ZDROJE

- ✓ Počítačová učebna (PC pro každého nebo dvojice)
- ✓ Projektor pro demo
- ✓ sqliteonline.com (databáze v prohlížeči – bez instalace)
- ✓ Pracovní list – zadání tří scénářů (viz příloha)
- ✓ Sdílená složka: `H14_pujcovna.sql` (hotová struktura k inspiraci)

---

## PRŮBĚH HODINY

### 0–5 min: ZAHÁJENÍ

- Přivítání, sdělení cíle: *„Dnes navrhneme databázi od nuly – jako opraví databázoví architekti. Projdeme celý postup od nápadu po SQL CREATE TABLE."*
- Motivace: *„Kdy byste použili Excel a kdy databázi?"* → diskuse (Excel = 1 tabulka, málo dat; DB = relace, více uživatelů)

---

### 5–10 min: MOTIVACE / ZADÁNÍ

Příběh: *„Školní knihovna chce evidovat výpůjčky knih. Mají teď papírový sešit. Co všechno potřebují vědět?"*

Žáci navrhují nahlas – zapisuješ na tabuli:
- Kdo si půjčil? (jméno, třída)
- Jakou knihu? (název, autor, rok vydání)
- Kdy? (datum výpůjčky, datum vrácení)
- Je vrácena? (ANO/NE)

*„Kdybychom to dali do jedné tabulky – co by se opakovalo? Jméno autora pokaždé? To je špatně – navrhneme 2 tabulky."*

---

### 10–20 min: DEMO (učitel ukazuje, žáci sledují)

**Krok 1 – Identifikace entit a atributů**

Z příběhu o knihovně:

| Entita | Atributy |
|--------|----------|
| Kniha | id_knihy (PK), název, autor, rok_vydani, zanr |
| Žák | id_zaka (PK), jmeno, prijmeni, trida |
| Výpůjčka | id_vypujcky (PK), id_zaka (FK), id_knihy (FK), datum_od, datum_do, vraceno |

*„Proč je Výpůjčka samostatná tabulka? Protože jeden žák si může půjčit víc knih – to je vztah 1:N (nebo M:N)."*

**Krok 2 – ER diagram** (nakreslit na tabuli)

```
  ┌─────────┐         ┌──────────────┐         ┌─────────┐
  │  Žák    │─────────│  Výpůjčka   │─────────│  Kniha  │
  │  id (PK)│  1   N  │  id (PK)    │  N   1  │  id (PK)│
  │  jmeno  │         │  id_zaka FK │         │  název  │
  │  trida  │         │  id_knihy FK│         │  autor  │
  └─────────┘         │  datum_od   │         │  rok    │
                      │  vraceno    │         └─────────┘
                      └──────────────┘
```

**Krok 3 – SQL CREATE TABLE** (ukazuji v sqliteonline.com)

```sql
CREATE TABLE Kniha (
    id_knihy   INTEGER PRIMARY KEY,
    nazev      TEXT    NOT NULL,
    autor      TEXT    NOT NULL,
    rok        INTEGER,
    zanr       TEXT
);

CREATE TABLE Zak (
    id_zaka    INTEGER PRIMARY KEY,
    jmeno      TEXT    NOT NULL,
    prijmeni   TEXT    NOT NULL,
    trida      TEXT
);

CREATE TABLE Vypujcka (
    id_vypujcky INTEGER PRIMARY KEY,
    id_zaka     INTEGER NOT NULL REFERENCES Zak(id_zaka),
    id_knihy    INTEGER NOT NULL REFERENCES Kniha(id_knihy),
    datum_od    DATE    NOT NULL,
    datum_do    DATE,
    vraceno     INTEGER DEFAULT 0   -- 0 = ne, 1 = ano
);
```

Vložit testovací data:
```sql
INSERT INTO Kniha VALUES (1, 'Harry Potter', 'J.K. Rowling', 1997, 'Fantasy');
INSERT INTO Zak VALUES (1, 'Anna', 'Nováková', '8A');
INSERT INTO Vypujcka VALUES (1, 1, 1, '2024-01-10', NULL, 0);

SELECT z.jmeno, k.nazev, v.datum_od, v.vraceno
FROM Vypujcka v
JOIN Zak z ON v.id_zaka = z.id_zaka
JOIN Kniha k ON v.id_knihy = k.id_knihy;
```

---

### 20–38 min: SAMOSTATNÁ / PÁROVÁ PRÁCE

**Zadání (výběr 1 ze 3 scénářů):**

**Scénář A – Sportovní kroužky**
Škola eviduje žáky přihlášené do kroužků. Jeden žák může chodit do více kroužků.
Navrhni tabulky: Žák, Kroužek, Přihlášení.

**Scénář B – Inventář učebnic**
Škola půjčuje učebnice. Eviduje každou učebnici (stav: nová/poškozená), kdo ji má.
Navrhni tabulky: Učebnice, Žák, Výpůjčka.

**Scénář C – Třídní blog**
Třída píše příspěvky na školní blog. Příspěvek má autora, datum, tagy (témata).
Navrhni tabulky: Žák, Příspěvek, Tag, PříspěvekTag.

**Postup:**
1. Nakresli ER diagram na papír (entity, atributy, vztahy)
2. Urči primární klíče a cizí klíče
3. Napiš SQL CREATE TABLE pro min. 2 tabulky
4. Vlož 3–5 testovacích záznamů
5. Ověř: napiš SELECT dotaz, který data smysluplně vypíše

**Nápovědy:**
- Datové typy: TEXT (string), INTEGER (celé číslo), REAL (desetinné), DATE (datum YYYY-MM-DD)
- PK: PRIMARY KEY, FK: REFERENCES TabulkaNázev(sloupec)
- NOT NULL: povinné pole

**Cíl:** ER diagram na papíře + funkční SQL v sqliteonline.com

---

### 38–43 min: PREZENTACE / SDÍLENÍ

- 1 žák ukáže svůj ER diagram a SQL na projektoru
- Třída: *„Chybí tam nějaký atribut? Je vztah správně (1:N nebo M:N)?"*
- Sebereflexe: *„Co by ses musel/a vrátit a změnit, kdybys tabulku použil/a v praxi?"*

---

### 43–45 min: REFLEXE + EXIT TICKET

**Exit ticket** (lístek):
> *„Napiš: Co je primární klíč a proč ho databáze potřebuje? (1–2 věty)"*

**Uložení práce:**
- sqliteonline.com → Export → Save as .sql → `H14_databaze_JMENO.sql`
- Sdílená složka nebo školní cloud

---

## DIFERENCIACE

**Pomalejší žáci:**
- Dostanou předpřipravený SQL skript s kostrou (CREATE TABLE s komentáři TODO)
- Doplní jen atributy a typy, nevytvářejí ER diagram na papíře

**Nadaní žáci:**
- Přidají třetí tabulku a relaci M:N (junction table)
- Napíší SQL pohled (VIEW): `CREATE VIEW aktivni_vypujcky AS SELECT ...`
- Navrhnou pravidla pro integritu (UNIQUE, CHECK, DEFAULT)

---

## HODNOCENÍ V HODINĚ

- ✓ ER diagram na papíře (správné symboly, klíče)
- ✓ Funkční SQL CREATE TABLE + INSERT + SELECT
- ✓ Exit ticket

---

## REFLEXE PO HODINĚ

Co se povedlo:    _____________________________________
Co příště jinak:  _____________________________________
Tempo / nestihli: _____________________________________
Technické problémy: __________________________________

---

## PŘÍLOHA – Pracovní list: Návrh databáze

### Krok 1 – Identifikace entit

Z popisu scénáře podtrhni podstatná jména → každé může být entita nebo atribut.

Entita = věc, o které evidujeme data (má vlastní tabulku)
Atribut = vlastnost entity (sloupec v tabulce)

Vyber scénář: A / B / C

Moje entity: _______________________________, _______________________________, _______________________________

### Krok 2 – ER diagram (nakresli zde)

```
  ┌──────────┐              ┌──────────┐
  │          │              │          │
  │  Entita 1│──────────────│  Entita 2│
  │  id (PK) │              │  id (PK) │
  │          │              │  FK      │
  └──────────┘              └──────────┘
```

Typ vztahu (zakroužkuj): 1:1 / 1:N / M:N

### Krok 3 – SQL CREATE TABLE

```sql
CREATE TABLE ____________ (
    id        INTEGER PRIMARY KEY,
    _________ TEXT NOT NULL,
    _________ TEXT,
    _________ INTEGER
);
```

### Krok 4 – Sebehodnocení

| Kritérium | Splněno? |
|-----------|---------|
| ER diagram má min. 2 entity | ANO / NE |
| Každá tabulka má primární klíč | ANO / NE |
| Vztah je označen typem (1:N apod.) | ANO / NE |
| SQL CREATE TABLE funguje bez chyb | ANO / NE |
| INSERT vloží alespoň 3 záznamy | ANO / NE |
| SELECT zobrazí smysluplná data | ANO / NE |
