# Příprava na hodinu – Modelování pomocí grafů a schémat (7. ročník)

```
═══════════════════════════════════════════════════════
PŘÍPRAVA NA VYUČOVACÍ HODINU – INFORMATIKA
═══════════════════════════════════════════════════════

Datum:          _______________
Třída:          7.
Hodina č.:      H54  (celkové pořadí v tematickém plánu)
Časová dotace:  45 minut

NÁSTROJ:   ✓ Papír + tužka (práce s grafy – nepočítačová část)
           ✓ draw.io (diagrams.net) nebo Miro (volitelná digitální část)
           ✓ Projektor pro demo

TEMATICKÝ CELEK: Blok 3 – Web a data; modelování
TÉMA HODINY:     Modelování situací grafem – orientovaný graf, ohodnocení, základní grafové úlohy
```

---

## CÍLE HODINY

**Kognitivní:**
- Žák **vysvětlí**, co je graf jako matematický/informatický model (uzly a hrany)
- Žák **rozliší** neorientovaný, orientovaný a ohodnocený graf a uvede příklady z praxe
- Žák **vymezí problém** a navrhne jeho model pomocí grafu (I-9-1-03)
- Žák **zhodnotí** svůj model: obsahuje všechna potřebná data? (I-9-1-04)

**Procesní:**
- Žák navrhne graf pro reálnou situaci a najde v něm nejkratší cestu nebo propojení
- Žák porovná svůj model s modelem spolužáka

**Vazba na RVP ZV 2023:** I-9-1-03 (modelování pomocí grafů a schémat, výběr vhodnějšího modelu), I-9-1-04 (zhodnocení, zda model obsahuje vše potřebné, nalezení a oprava chyby v modelu)

---

## VÝCHOZÍ ZNALOSTI

- Vývojový diagram a jeho symboly (6. ročník, H13)
- Pojem algoritmus, sekvence (6. ročník)
- Základní orientace v souřadnicích (matematika)

**Ověření na začátku (2 min):** *„Co je vývojový diagram? Čím se liší od grafu?"*

---

## POMŮCKY A ZDROJE

- ✓ Papír A4 + tužka pro každého žáka
- ✓ Projektor pro demo
- ✓ Pracovní list – zadání modelovacích úloh (viz příloha)
- ✓ Volitelně: draw.io (diagrams.net) pro digitální verzi
- ✓ Mapa Plzně nebo jiného města (tisk nebo projekce) – pro úlohu o cestách

---

## PRŮBĚH HODINY

### 0–5 min: ZAHÁJENÍ

- Přivítání, sdělení cíle: *„Dnes se naučíme moci nakreslit mapu problému – grafem. Grafy jsou jeden z nejsilnějších nástrojů informatiky: používají je Google Maps, Facebook (sociální sítě), logistické firmy i GPS."*
- Motivace: *„Jak Google Maps najde nejrychlejší cestu z Plzně do Prahy, když existují stovky cest?"*

---

### 5–10 min: MOTIVACE / ZADÁNÍ

Nakresli na tabuli (nebo promítni) jednoduchý příklad:

**Sociální síť (neorientovaný graf):**
```
   Anna ─── Bořek
    │   ╲      │
    │    ╲     │
  Cyril   Diana─┘
```
*„Každý uzel je člověk. Hrana = jsou přátelé. Kdo je přáteli s kým? Jak mnoho propojení má každý?"*

*„Teď si představte, že hrany mají SMĚR (kdo koho sleduje na Instagramu) a VÁHU (jak moc spolu chatují). To jsou různé typy grafů."*

---

### 10–20 min: DEMO (učitel ukazuje, žáci sledují)

**Krok 1 – Typy grafů**

| Typ | Popis | Příklad |
|-----|-------|---------|
| **Neorientovaný** | Hrany bez směru (obousměrné) | Přátelství, silnice |
| **Orientovaný** | Hrany se směrem (jednosměrné) | Sledování na Instagramu, jednosměrná ulice |
| **Ohodnocený** | Hrany mají číslo (vzdálenost, čas, cena) | Mapa měst, silniční síť |
| **Strom** | Hierarchický graf (bez cyklů) | Organizační struktura, souborový systém |

**Krok 2 – Modelování trasy** (nakreslit na tabuli)

Mapa části Plzně (4 místa: Škola, Náměstí, Nádraží, Kino):

```
Škola ──5 min── Náměstí ──8 min── Nádraží
  │                │                  │
 3 min           4 min             6 min
  │                │                  │
  └─────────────── Kino ──────────────┘
```

Otázky pro třídu:
- *„Jak se dostanu ze Školy do Nádraží nejrychleji?"*
- *„Kolik cest vede z Kina do Náměstí?"*
- *„Pokud je cesta Náměstí–Nádraží uzavřená, co pak?"*

**Krok 3 – Myšlenková mapa jako orientovaný graf**

Téma: „Jak se šíří fake news?"

```
Fake news → sdílím na FB → vidí přátelé → 3× sdílí → více lidí
              ↓
            vidí kamarád → ověří zdroj → NEsdílí (konec)
```

*„I myšlenková mapa je graf – jen se méně přesně kreslí. Informatici mají formálnější značení."*

---

### 20–38 min: SAMOSTATNÁ / PÁROVÁ PRÁCE

**Zadání (výběr 1 ze 3 úloh):**

**Úloha A – Mapa školy**
Nakresli orientovaný ohodnocený graf budovy školy (alespoň 6 místností):
- Uzly = místnosti (třída, jídelna, tělocvična, chodba, WC, ředitelna)
- Hrany = chodby / dveře, ohodnocení = vzdálenost v krocích nebo čas v sekundách
- Najdi nejkratší cestu z třídy do jídelny

**Úloha B – Cestovní plán**
Máš navštívit 5 měst v ČR. Nakresli ohodnocený graf vzdáleností (km):
- Praha, Brno, Plzeň, Ostrava, Olomouc (vzdálenosti dohledat nebo odhadnout)
- Jaká je nejkratší trasa, která navštíví všechna města a vrátí se domů?
- Porovnej svou trasu s trasou spolužáka – kdo má kratší?

**Úloha C – Sociální síť třídy**
Nakresli neorientovaný graf: uzly = kamarádi (min. 6), hrany = přátelství
- Který uzel (člověk) má nejvíce propojení? (tzv. „stupeň uzlu")
- Existuje někdo, přes koho se dostanete ke každému jinému? (centrální uzel)
- Smaž jeden uzel – rozpadne se síť na části?

**Postup (pro všechny úlohy):**
1. Nakresli graf na papír
2. Pojmenuj uzly a označ hrany
3. Odpověz na otázky k úloze
4. Zhodnoť: chybí v grafu nějaká důležitá informace? (I-9-1-04)
5. Porovnej s modelem spolužáka – kdo zachytil víc informací?

**Nápovědy:**
- Uzel = kroužek s názvem
- Hrana = čára (nebo šipka pro orientovaný graf)
- Ohodnocení = číslo na hraně

---

### 38–43 min: PREZENTACE / SDÍLENÍ

- 2 dvojice ukáží svůj graf na projektoru (nebo naskenovaný)
- Třída: *„Je v grafu vše? Co byste přidali?"*
- Diskuse: *„Proč je pro GPS důležité, aby byl graf ohodnocený? Co by se stalo bez čísel?"*

---

### 43–45 min: REFLEXE + EXIT TICKET

**Exit ticket** (lístek nebo ústně):
> *„Napiš příklad z každodenního života, kde se skrývá orientovaný ohodnocený graf."*
> (Tip: dopravní síť, internet, potravinový řetězec, objednávkový systém…)

---

## DIFERENCIACE

**Pomalejší žáci:**
- Pracují jen s Úlohou A (nejkonkrétnější, prostorový – znají školu)
- Předpřipravené uzly na pracovním listu, dokreslit jen hrany a ohodnocení

**Nadaní žáci:**
- Naprogramují graf v Pythonu (slovník: `{"Praha": {"Brno": 210, "Plzen": 90}}`), vypíší sousedy
- Implementují jednoduché BFS (prohledávání do šířky) pro nalezení nejkratší cesty
- Navrhnou, jak by algoritmus Google Maps pracoval s takovým grafem

---

## HODNOCENÍ V HODINĚ

- ✓ Nakresleý graf (správné uzly, hrany, ohodnocení)
- ✓ Odpovědi na otázky k úloze
- ✓ Sebehodnocení modelu (I-9-1-04)
- ✓ Exit ticket

---

## REFLEXE PO HODINĚ

Co se povedlo:    _____________________________________
Co příště jinak:  _____________________________________
Tempo / nestihli: _____________________________________
Technické problémy: __________________________________

---

## PŘÍLOHA – Pracovní list: Modelování grafem

### Pojmy – doplň definici

**Uzel (vrchol):** ___________________________________

**Hrana:** ___________________________________

**Orientovaná hrana:** ___________________________________

**Ohodnocená hrana:** ___________________________________

---

### Přečti a analyzuj graf

Následující graf popisuje přátelství ve skupině:

```
    A ──── B
    │    ╱ │
    │   ╱  │
    │  ╱   │
    C ──── D ──── E
```

1. Kolik uzlů graf má? _____
2. Kolik hran graf má? _____
3. Kdo je přátel s D? _____
4. Existuje cesta z A do E? Jaká? _____
5. Pokud smaže uzel D – zůstane E propojené se zbytkem? _____

---

### Moje úloha (vyber A / B / C)

Nakresli graf zde: (volný prostor pro kresbu)

Počet uzlů: _____  |  Počet hran: _____  |  Typ grafu: _____________________

Odpovědi na otázky úlohy:
___________________________________________________
___________________________________________________

Chybí v mém grafu nějaká informace? ___________________

Co bych přidal/a: _____________________________________
