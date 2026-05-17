# Příprava na hodinu – 3D modelování a 3D tisk (9. ročník)

```
═══════════════════════════════════════════════════════
PŘÍPRAVA NA VYUČOVACÍ HODINU – INFORMATIKA
═══════════════════════════════════════════════════════

Datum:          _______________
Třída:          9.
Hodina č.:      H55  (volitelná/rozšiřující hodina – Blok 4)
Časová dotace:  45 minut

NÁSTROJ:   ✓ Tinkercad (tinkercad.com) – online, zdarma, bez instalace
           □ 3D tiskárna (demo, pokud je k dispozici) nebo ukázka sliceru
           □ Alternativa: BlocksCAD, FreeCAD (složitější), Blender (pokročilý)

TEMATICKÝ CELEK: Blok 4 – Pokročilé digitální technologie (SVP)
TÉMA HODINY:     3D modelování v Tinkercad a principy 3D tisku
```

---

## CÍLE HODINY

**Kognitivní:**
- Žák **vysvětlí** princip 3D tisku (FDM/FFF – vrstva po vrstvě)
- Žák **rozlišuje** pojmy: model, slicer, filament, G-kód, infill, support
- Žák **pojmenuje** základní typy 3D tiskáren a jejich použití

**Procesní:**
- Žák vytvoří jednoduchý 3D model v prostředí Tinkercad (min. ze 3 tvarů)
- Žák exportuje model jako `.stl` soubor a popíše postup přípravy pro tisk

**Vazba na RVP ZV 2023 / ŠVP 4. ZŠ Plzeň:** I-9-4-02 (3D model a 3D tisk)

---

## VÝCHOZÍ ZNALOSTI

- Souřadnicový systém (X, Y, Z) z matematiky – 3D prostor
- Soubory a formáty (6. ročník H3) – export, přípony `.stl`, `.obj`
- Základní geometrické tvary – krychle, válec, koule (matematika)

**Ověření na začátku (2 min):** *„Co si představíte pod pojmem '3D tisk'? Kde jste se s ním setkali?"*

---

## POMŮCKY A ZDROJE

- ✓ Počítačová učebna – prohlížeč s přístupem na tinkercad.com
- ✓ Projektor – demo učitele v Tinkercad
- ✓ Ukázky 3D vytištěných předmětů (přinést z kabinetu nebo ukázat foto)
- ✓ (Volitelně) 3D tiskárna nebo video tisku
- 🔗 Tinkercad: tinkercad.com (registrace zdarma školním e-mailem)
- 🔗 Slicer demo: prusaslicer.com (zdarma), nebo Ultimaker Cura
- 🔗 Hotové modely: thingiverse.com (inspirace a stahování)
- 🔗 Video: *„How Does a 3D Printer Work?"* (YouTube, 3 min)

---

## PRŮBĚH HODINY

### 0–5 min: ZAHÁJENÍ

- Přivítání, sdělení cíle:
  *„Dnes se dotkneme technologie, která mění průmysl, medicínu, architekturu i vědu. 3D tisk umožňuje vyrobit téměř cokoliv – od náhradní části stroje po lidskou tkáň."*
- Ukáž 3–4 fotky na projektoru: 3D tištěná protéza ruky, architektonický model, díl pro auto, ozdoba

---

### 5–15 min: TEORIE – 3D tisk od modelu k předmětu

**Jak funguje 3D tisk (FDM – Fused Deposition Modeling):**

```
┌─────────────────────────────────────────────────────┐
│  KROKY 3D TISKU                                     │
│                                                     │
│  1. NÁVRH MODELU   →  software (Tinkercad, Blender) │
│  2. EXPORT          →  .STL soubor                  │
│  3. SLICER          →  rozdělí model na vrstvy      │
│                        nastaví: teplotu, rychlost,  │
│                        výplň (infill), podpory      │
│  4. G-KÓD           →  instrukce pro tiskárnu       │
│  5. TISK            →  vrstva po vrstvě (0,2 mm)    │
│  6. POST-PROCESSING →  odstranění podpor, broušení  │
└─────────────────────────────────────────────────────┘
```

**Klíčové pojmy:**

| Pojem | Vysvětlení |
|-------|-----------|
| **Filament** | Materiál tisku – vlákno plastu (PLA, ABS, PETG) |
| **Infill** | Výplň předmětu (20% = dutý, 100% = plný) |
| **Layer height** | Výška vrstvy – 0,1 mm (detailní) až 0,3 mm (rychlý) |
| **Support** | Podpora pro převisující části (pak se odstraní) |
| **Slicer** | Software, který připraví model pro tiskárnu |
| **STL** | Nejběžnější formát 3D modelů |

**Typy 3D tiskáren:**
- **FDM** (filament) – nejběžnější, levná, plastové předměty
- **SLA/MSLA** (resin) – velmi přesná, ale dražší a chemicky náročná
- **SLS** (prášek) – průmyslová, kov nebo nylon

---

### 15–35 min: DEMO + SAMOSTATNÁ PRÁCE – Tinkercad

**Registrace / přihlášení:**
- tinkercad.com → Přihlásit se (Google nebo e-mail)
- Nebo: učitel vytvoří třídní projekt (třídní přihlášení bez e-mailu žáků)

**Demo učitele (5 min):**

*Krok 1 – Prostředí Tinkercad:*
- Pracovní plocha (rovina XY) – zde stojí model
- Navigace: kolečko myši = zoom, pravé tlačítko = otočení
- Levý panel: Základní tvary → přetáhnout na plochu

*Krok 2 – Přidat tvar:*
- Přetáhni Krychli (Box) na plochu
- Vlevo: nastavit rozměry: 30 × 30 × 10 mm (základ klíčenky)
- Přetáhni Válec (Cylinder) → Hole → umísti na základ → Seskupit (Group) = otvor

*Krok 3 – Seskupit tvary:*
- Vyber více tvarů (Ctrl+klik) → Seskupit (Ctrl+G)
- Rozdíl: Union (sloučení) vs. Hole (odečtení)

**Samostatná práce (15 min) – Navrhni 1 předmět:**

Žáci si vyberou jedno z témat:
- 🔑 **Klíčenka s iniciálami** – základ + text 3D + otvor
- 🏠 **Miniaturní domek** – základ + stěny + střecha (prism)
- 🎮 **Stojánek na telefon** – L-tvar z obdélníků
- ⭐ **Vlastní nápad** (schválit s učitelem)

**Nápovědy:**
- Text 3D: levý panel → Text → přetáhnout → napsat iniciály → Seskupit se základem
- Otvor: jakýkoliv tvar označit jako „Hole" → Seskupit s plným tvarem
- Zrcadlit: vybrat → Zrcadlit (ikona v nástrojové liště)
- Vrátit zpět: Ctrl+Z (neomezeně!)

---

### 35–42 min: EXPORT A SLICER DEMO

**Export z Tinkercad:**
- Exportovat → `.STL` nebo `.OBJ`
- Pojmenovat: `H55_model_JMENO.stl`

**Demo sliceru (učitel ukazuje, 4 min):**
- Otevři PrusaSlicer nebo Ultimaker Cura (nebo online verzi)
- Importuj `.stl` soubor → model se zobrazí
- Ukáž nastavení:
  - Layer height: 0,2 mm
  - Infill: 20 % (hvězdicový vzor)
  - Support: zapnout/vypnout (ukázat rozdíl)
  - Estimated print time + material (např. 47 min, 3,2 g PLA)
- *„Tímto souborem by tiskárna začala tisknout. Kdyby tu tiskárna stála, trvalo by to ~47 minut."*

*Pokud je dostupná školní 3D tiskárna:*
- Ukázat zásobník filamentu, trysku, vyhřívanou podložku
- Vytisknout připravený vzorový model (nebo spustit tisk předem pro demo)

---

### 42–45 min: REFLEXE + EXIT TICKET

**Exit ticket** (ústně nebo lístek):
> a) *„Jaký je rozdíl mezi .STL souborem a G-kódem?"*
> b) *„Co je to infill a proč ho nenastavíme vždy na 100 %?"*
> c) *„Kde ve skutečném životě se využívá 3D tisk?"*

**Uložení:**
- Tinkercad: model automaticky uložen v účtu online
- STL soubor: složka `Informatika/H55`

---

## DIFERENCIACE

**Pomalejší žáci:**
- Klíčenka se jménem: základní tvar + text, bez otvoru
- Stačí 2 tvary (základ + 1 prvek)
- Slicer přeskočit – stačí export do STL

**Nadaní žáci:**
- Navrhnou složitější model: šachová figurka, miniatura robota, ozubené kolo
- Vyzkoušejí Tinkercad → Codeblocks (programování 3D tvarů v blocích)
- Prozkoumají thingiverse.com → importují cizí model do Tinkercad → upraví
- Bonus: spočítají objem modelu z rozměrů a odhadnou hmotnost tisku

---

## HODNOCENÍ V HODINĚ

- ✓ Pozorování při modelování (postup, použití min. 3 tvarů)
- ✓ Hotový STL model (exportován a uložen)
- ✓ Exit ticket (ústní nebo písemný)

---

## MEZIPŘEDMĚTOVÉ VZTAHY

- **Matematika:** 3D prostorové myšlení, objem a povrch těles, souřadnicový systém
- **Fyzika:** skupenství hmoty, teplota tání plastů, mechanické vlastnosti materiálů
- **Výtvarná výchova:** design, estetika, funkce vs. forma
- **Pracovní výchova:** práce s materiálem, postprocessing (broušení, barvení)

---

## REFLEXE PO HODINĚ

Co se povedlo:    _____________________________________
Co příště jinak:  _____________________________________
Tempo / nestihli: _____________________________________
Technické problémy: __________________________________

---

## PŘÍLOHA – Pracovní list: 3D modelování a tisk

### Kroky tvorby 3D modelu – doplň

Seřaď kroky ve správném pořadí (1–5):

| Krok | Popis |
|------|-------|
| ___ | Export modelu do formátu .STL |
| ___ | Navrhnout model v Tinkercad |
| ___ | Tiskárna vytiskne vrstvu po vrstvě |
| ___ | Slicer připraví G-kód |
| ___ | Odstranit podpory, upravit povrch |

### Moje dnešní téma

Navrhoval/a jsem: ________________________________

Použité tvary (zaškrtni):  ☐ Box  ☐ Cylinder  ☐ Sphere  ☐ Cone  ☐ Text 3D  ☐ Jiné: ___

Exportoval/a jsem STL: ☐ Ano  ☐ Ne

### Pojmy – spoj s definicí

| Pojem | Definice |
|-------|---------|
| Filament | Instrukce pro pohyb tiskové hlavy |
| Slicer | Výplň předmětu (v %) |
| G-kód | Software, který připraví model pro tisk |
| Infill | Plastové vlákno – materiál tisku |
| STL | Formát 3D modelu |

### Kde se 3D tisk využívá?

Napiš alespoň 3 příklady:

1. ________________________________________
2. ________________________________________
3. ________________________________________

```
┌────────────────────────────────────────────────────────┐
│  SHRNUTÍ – 3D TISK V KOSTCE                           │
│                                                        │
│  Model    →  Tinkercad / Blender / FreeCAD             │
│  Export   →  .STL soubor                               │
│  Slicer   →  G-kód + nastavení tisku                   │
│  Tisk     →  vrstva po vrstvě (FDM: filament)          │
│  Filament →  PLA (nejběžnější), ABS, PETG, flexibilní  │
│  Infill   →  15–20 % = funkční, 100 % = plný (těžký)  │
└────────────────────────────────────────────────────────┘
```
