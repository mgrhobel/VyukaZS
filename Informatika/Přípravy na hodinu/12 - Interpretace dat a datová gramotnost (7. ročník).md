# Příprava na hodinu – Interpretace dat a datová gramotnost (7. ročník)

```
═══════════════════════════════════════════════════════
PŘÍPRAVA NA VYUČOVACÍ HODINU – INFORMATIKA
═══════════════════════════════════════════════════════

Datum:          _______________
Třída:          7.
Hodina č.:      H56  (celkové pořadí v tematickém plánu)
Časová dotace:  45 minut

NÁSTROJ:   ✓ Excel / LibreOffice Calc  (tabulky a grafy)
           ✓ Projektor pro ukázku grafů a diskusi

TEMATICKÝ CELEK: Blok 4 – Data, mediální gramotnost a kritické myšlení
TÉMA HODINY:     Interpretace dat – čtení grafů, odhalování chyb a manipulace s daty
```

---

## CÍLE HODINY

**Kognitivní:**
- Žák **přečte** data z tabulky nebo grafu a **formuluje** závěr vlastními slovy
- Žák **identifikuje** chybu nebo manipulaci v prezentaci dat (zkrácená osa, chybějící kontext, cherry-picking)
- Žák **porovná** různé způsoby zobrazení stejných dat a zhodnotí, který je vhodnější

**Procesní:**
- Žák pracuje s reálnými daty v tabulce, vytvoří alternativní (korektní) graf
- Žák prezentuje vlastní závěr ze dat (I-9-1-01, I-9-1-04)

**Vazba na RVP ZV 2023:** I-9-1-01 (získání informací z dat, interpretace, odhalování chyb v interpretacích), I-9-1-04 (zhodnocení, zda model obsahuje vše potřebné)

---

## VÝCHOZÍ ZNALOSTI

- Tabulkový procesor: buňky, vzorce, základní funkce (SUM, AVERAGE)
- Typy grafů: sloupcový, spojnicový, koláčový (z 6. ročníku)
- Pojem průměr

**Ověření na začátku (2 min):** *„Kdy je vhodný koláčový graf? A kdy spojnicový?"*

---

## POMŮCKY A ZDROJE

- ✓ Počítačová učebna (PC pro každého nebo dvojice)
- ✓ Projektor – ukázka manipulovaných grafů
- ✓ Sdílená složka: `H56_data_teploty.xlsx` a `H56_data_prodeje.xlsx`
- ✓ Pracovní list s vytištěnými grafy k analýze (viz příloha)
- ✓ Online zdroj: ourworldindata.org (reálná data – pro motivaci)

---

## PRŮBĚH HODINY

### 0–5 min: ZAHÁJENÍ

- Přivítání, sdělení cíle: *„Dnes budeme datovými detektivy. Naučíme se číst data, ale také odhalit, kdy nás někdo grafem klame."*
- Ukáž jeden zmanipulovaný graf (viz Demo níže) – bez komentáře. *„Co si myslíte, co tento graf říká?"*

---

### 5–10 min: MOTIVACE / ZADÁNÍ

Promítni dva grafy ze stejných dat:

**Graf A** – osa Y začíná na 95 % (vypadá dramaticky)
```
100% |████████
 99% |███████
 98% |██████
 97% |████
 96% |███
 95% |
      Jan Feb Mar Apr May
```

**Graf B** – osa Y začíná na 0 %
```
100% |████████████████████
  0% |
      Jan Feb Mar Apr May
```

*„Oba grafy ukazují STEJNÁ DATA. Proč vypadají tak různě?"*
→ Diskuse: Osa Y, výchozí hodnota, proč to dělají reklamy/politici

---

### 10–20 min: DEMO (učitel ukazuje, žáci sledují)

**Krok 1 – Jak číst tabulku systematicky**

Otevři `H56_data_teploty.xlsx` (průměrné měsíční teploty v Praze, 2015–2023):

| Rok | Leden | Červenec | Průměr roku |
|-----|-------|----------|-------------|
| 2015 | -2,1 | 21,3 | 10,2 |
| 2018 | 0,5 | 24,8 | 12,1 |
| 2023 | 3,2 | 23,5 | 13,0 |

*„Co chceme vědět? Jde o teploty v čase nahoru nebo dolů? Jak to zjistíme?"*
- Vzorec AVERAGE pro každý rok
- Spojnicový graf → trend je vidět

**Krok 2 – Odhalování chyb v interpretaci**

Příklady manipulace s daty (každý ukázat a pojmenovat):

1. **Zkrácená osa Y** – dramatizuje malé změny
2. **Cherry-picking** – vyber jen roky, které potvrzují tvou tezi
3. **Chybějící kontext** – „Naše firma vzrostla o 200 %" (z 1 na 3 zákazníky)
4. **Záměna korelace za kauzalitu** – „Prodej zmrzliny roste → roste i počet utopených" (oba rostou v létě)

**Krok 3 – Jak ověřit závěr**

*„Dobrý závěr z dat:"*
- Popisuje, co data ŘÍKAJÍ (ne co chceme slyšet)
- Uvádí zdroj a časový rozsah
- Nezapomíná na výjimky a odchylky

---

### 20–38 min: SAMOSTATNÁ / PÁROVÁ PRÁCE

**Zadání:**

Otevřete soubor `H56_data_prodeje.xlsx` (prodeje oblíbených filmů, 3 kina, 3 roky).

**Úkol 1 – Popište data (5 min):**
- Které kino mělo nejvyšší tržby v 2022?
- Který rok byl celkově nejlepší?
- Vzorec: celkové tržby za každý rok (SUM)

**Úkol 2 – Vytvořte graf (8 min):**
- Vytvořte sloupcový graf pro srovnání kin za rok 2022
- Pak vytvořte tentýž graf se zkrácenou osou Y (min = 80 % maxima)
- Uložte oba grafy vedle sebe

**Úkol 3 – Napište závěr (5 min):**
Napište 3–4 věty: *Co data říkají? Co NELZE z dat říct? Jaký by byl manipulativní závěr vs. správný závěr?*

**Nápovědy:**
- Sloupcový graf: Vybrat data → Vložit → Graf → Sloupcový
- Osa Y: Pravé tlačítko na osu → Formátovat osu → Minimum

**Cíl:** 2 grafy (správný a manipulovaný), písemný závěr

---

### 38–43 min: PREZENTACE / SDÍLENÍ

- 1–2 dvojice ukáží oba grafy na projektoru
- *„Kde vidíte rozdíl? Proč manipulovaný graf působí jinak?"*
- Diskuse: *„Kde v reálném životě se setkáváte s podobnými grafy?"* (reklamy, zprávy, sociální sítě)

---

### 43–45 min: REFLEXE + EXIT TICKET

**Exit ticket** (lístek nebo formulář):
> *„Napiš jednu věc, na kterou se teď podíváš jinak, když uvidíš graf v reklamě nebo na sociálních sítích."*

**Uložení práce:**
- `H56_data_JMENO.xlsx` → sdílená složka nebo Google Drive

---

## DIFERENCIACE

**Pomalejší žáci:**
- Pracovní list s předpřipravenou tabulkou (menší rozsah dat, méně sloupců)
- Vytvořit jen jeden graf, napsat 2 věty závěru

**Nadaní žáci:**
- Najít reálná data na internetu (CZSO, Eurostat, Our World in Data) a provést vlastní analýzu
- Porovnat 2 různé grafy stejného jevu z různých zdrojů – kdo a proč je zobrazuje jinak?
- Napsat stručnou „datovou zprávu" (půl stránky) jako novinář

---

## HODNOCENÍ V HODINĚ

- ✓ Pozorování a obcházení (správnost vzorců a interpretace)
- ✓ Exit ticket (reflexe datové gramotnosti)
- ✓ Sdílení grafů na projektoru

---

## REFLEXE PO HODINĚ

Co se povedlo:    _____________________________________
Co příště jinak:  _____________________________________
Tempo / nestihli: _____________________________________
Technické problémy: __________________________________

---

## PŘÍLOHA – Pracovní list: Datový detektiv

### Graf k analýze č. 1

*Výsledky voleb pro dvě strany (v %):*

| Strana | 2018 | 2022 |
|--------|------|------|
| A | 32 % | 34 % |
| B | 28 % | 26 % |

Graf ukazuje strana A „skáče dramaticky nahoru" – osa Y začíná na 25 %.

**Otázky:**
1. Jak velký je skutečný nárůst strany A? _______%
2. Proč graf vypadá dramaticky? ___________________________
3. Jak bys graf udělal/a správně? _________________________

---

### Graf k analýze č. 2

*Tvrzení: „Prodej zmrzliny způsobuje utonutí!"*

| Měsíc | Prodej zmrzliny (tis. ks) | Počet utopených |
|-------|--------------------------|-----------------|
| Leden | 50 | 3 |
| Červenec | 500 | 25 |
| Srpen | 480 | 22 |

**Otázky:**
1. Je tvrzení správné? Proč? ___________________________
2. Co je skutečná příčina obou jevů? ___________________
3. Jak se jmenuje tento typ chyby v interpretaci dat? ___________
