# Příprava na hodinu – Vývojové diagramy a algoritmizace (6. ročník)

```
═══════════════════════════════════════════════════════
PŘÍPRAVA NA VYUČOVACÍ HODINU – INFORMATIKA
═══════════════════════════════════════════════════════

Datum:          _______________
Třída:          6.
Hodina č.:      H13  (celkové pořadí v tematickém plánu)
Časová dotace:  45 minut

NÁSTROJ:   □ Papír + tužka (první část – nepočítačová)
           ✓ draw.io (diagrams.net) – v prohlížeči, bez instalace (druhá část)

TEMATICKÝ CELEK: Blok 2 – Algoritmy a programování v Scratch
TÉMA HODINY:     Vývojové diagramy – symboly, tvorba, přechod do Scratch
```

---

## CÍLE HODINY

**Kognitivní:**
- Žák **pojmenuje a použije** základní symboly vývojového diagramu (start/konec, operace, podmínka, šipka)
- Žák **přečte** hotový vývojový diagram a vysvětlí, co popisuje
- Žák **navrhne** vývojový diagram pro jednoduchý algoritmus z každodenního života

**Procesní:**
- Žák samostatně nakreslí vývojový diagram na papír i v nástroji draw.io
- Žák propojí vývojový diagram se Scratchovým skriptem (I-9-1-03, I-9-2-01)

**Vazba na RVP ZV 2023:** I-9-1-03 (modelování pomocí grafů a schémat), I-9-2-01 (přečtení a vysvětlení algoritmu)

---

## VÝCHOZÍ ZNALOSTI

- Pojem algoritmus – postup krok po kroku (H1)
- Smyčka a podmínka v Scratch (H8–H9)
- Pojem proměnná (H11)

**Ověření na začátku (2 min):** Otázka: *„Co je algoritmus? Uveď jeden příklad z každodenního života."*

---

## POMŮCKY A ZDROJE

- ✓ Papír A4 + tužka + pravítko pro každého žáka
- ✓ Projektor pro demo (draw.io nebo tabule)
- ✓ Počítačová učebna – prohlížeč s draw.io (diagrams.net)
- ✓ Pracovní list – předkreslené tvary k popsání (viz níže)
- ✓ Sdílená složka: `H13_diagram_start.drawio` (prázdná šablona s legendou symbolů)

---

## PRŮBĚH HODINY

### 0–5 min: ZAHÁJENÍ

- Přivítání, sdělení cíle: *„Dnes se naučíme vizuálně zapsat algoritmus – vývojovým diagramem. Je to jazyk, kterému rozumí programátoři na celém světě."*
- Rychlé opakování: Co je algoritmus? (žáci říkají příklady)

---

### 5–10 min: MOTIVACE / ZADÁNÍ

Ukáž na projektoru vývojový diagram pro „Vstávám ráno do školy":

```
    ◯ START
    ↓
  ▭ Zazvoní budík
    ↓
  ◇ Je venku zima?
   ↙ ANO         ↘ NE
▭ Obléknu si   ▭ Obléknu si
  svetr a        tričko
  bundu
    ↘           ↙
  ▭ Najím se
    ↓
  ◯ KONEC
```

*„Toto je vývojový diagram. Každý tvar má svůj smysl – naučíme se je dnes."*

---

### 10–20 min: DEMO (učitel ukazuje, žáci sledují)

**Krok 1 – Symboly vývojového diagramu** (vysvětlit + nakreslit na tabuli/projektoru)

| Symbol | Tvar | Použití |
|--------|------|---------|
| Start / Konec | Ovál / zaoblený obdélník | Začátek a konec algoritmu |
| Operace / Příkaz | Obdélník | Co se provede (výpočet, akce) |
| Podmínka | Kosočtverec | Rozhodnutí: ANO / NE |
| Šipka | → | Tok řízení (co následuje) |

**Krok 2 – Demo v draw.io**

- Otevři diagrams.net → Nový diagram → Blank
- Přidej ovál „START", obdélník „Zadej dvě čísla", kosočtverec „Je A > B?", dvě větve (ANO/NE) → výpis většího čísla, ovál „KONEC"
- Ukaž: jak propojit šipkami, jak popsat větve ANO/NE

**Krok 3 – Přečtení hotového diagramu** (žáci jen sledují a odpovídají)

- Promítni diagram pro algoritmus „Hledám v ledničce jogurt":
  1. Otevři ledničku
  2. Je tam jogurt? → ANO: vezmi jogurt → KONEC; NE: Jdi do obchodu → koupit jogurt → KONEC
- *„Co dělá tento algoritmus? Kde je větvení?"* (žáci odpovídají)

---

### 20–38 min: SAMOSTATNÁ / PÁROVÁ PRÁCE

**Část 1 – papír (10 min, individuálně):**

Nakresli vývojový diagram pro jeden z těchto algoritmů (dle výběru):
- a) **Přechod přes přechod pro chodce** (svítí zelená? → jdi / počkej)
- b) **Hra: Hádej číslo** (mysli si číslo 1–10 → hráč hádá → je to ono? ANO → výhra; NE → zkus znovu)
- c) **Výběr oblečení** (je déšť? ANO → deštník; NE → bez deštníku → jdu ven)

Pravidla: musí obsahovat START, KONEC, min. 1 podmínku, min. 1 operaci.

**Část 2 – draw.io (8 min, ve dvojici):**

Přenes diagram z papíru do draw.io (diagrams.net). Použijte šablonu z sdílené složky.

- Jeden diktuje, druhý kliká
- Uložit jako: `H13_diagram_JMENO.drawio`

**Nápovědy:**
- Symboly v draw.io: záložka „General" nebo vyhledat „diamond" (podmínka), „rectangle" (operace), „rounded" (start/konec)
- Větve pojmenovat: napsat „ANO" a „NE" na šipky

**Cíl:** Hotový diagram v draw.io, správně použité symboly

---

### 38–43 min: PREZENTACE / SDÍLENÍ

- 2 dobrovolníci ukáží diagram na projektoru
- Třída: *„Rozumíte tomu diagramu? Co dělá? Máte jiné řešení?"*
- Porovnej: stejný algoritmus – různé diagramy (různé cesty jsou OK)

---

### 43–45 min: REFLEXE + EXIT TICKET

**Exit ticket** (ústně nebo na lístek):
> *„Nakresli symbol pro podmínku a napiš, co v diagramu znamená ANO/NE."*

**Uložení práce:**
- draw.io: Soubor → Uložit do počítače → složka `Informatika/H13`
- Nebo: sdílená složka třídy

---

## DIFERENCIACE

**Pomalejší žáci:**
- Dostanou předtištěný pracovní list s prázdnými boxy (tvary jsou předkresleny, žáci jen píší text dovnitř)
- Část v draw.io přeskočit – dokončit papírový diagram

**Nadaní žáci:**
- Přidej do diagramu smyčku (příklad: „opakuj dokud nenajdeš jogurt")
- Zápis diagramu jako Scratch skript – přelož svůj diagram do Scratch bloků
- Bonus: najdi na internetu vývojový diagram pro reálný software (ATM, přihlašování)

---

## HODNOCENÍ V HODINĚ

- ✓ Pozorování při kreslení (správnost symbolů)
- ✓ Exit ticket (slovní nebo kresbou)
- ✓ Sdílení na projektoru

---

## REFLEXE PO HODINĚ

Co se povedlo:    _____________________________________
Co příště jinak:  _____________________________________
Tempo / nestihli: _____________________________________
Technické problémy: __________________________________

---

## PŘÍLOHA – Pracovní list

### Symboly vývojového diagramu – doplň popis

| Symbol (nakreslen) | Název | Co znamená |
|--------------------|-------|------------|
| ◯ | ______________ | ______________ |
| ▭ | ______________ | ______________ |
| ◇ | ______________ | ______________ |
| → | ______________ | ______________ |

### Přečti a vysvětli tento diagram:

```
◯ START
  ↓
▭ Uživatel zadá číslo N
  ↓
◇ Je N > 0?
 ↙ ANO        ↘ NE
▭ Vypíš        ▭ Vypíš
 "Kladné"       "Záporné nebo nula"
    ↘          ↙
  ◯ KONEC
```

Co dělá tento algoritmus? ___________________________

Kde je podmínka? ___________________________________

Jaké jsou dvě možné cesty? _________________________
