# Příprava na hodinu – Čtení a analýza kódu – Sekvence a debugging (6. ročník)

```
═══════════════════════════════════════════════════════
PŘÍPRAVA NA VYUČOVACÍ HODINU – INFORMATIKA
═══════════════════════════════════════════════════════

Datum:          _______________
Třída:          6.
Hodina č.:      H7  (celkové pořadí v tematickém plánu)
Časová dotace:  45 minut

NÁSTROJ:   ✓ Scratch (scratch.mit.edu) – v prohlížeči, bez instalace

TEMATICKÝ CELEK: Blok 2 – Algoritmy a programování v Scratch
TÉMA HODINY:     Sekvence příkazů – čtení, vysvětlování a oprava kódu (debugging)
```

---

## CÍLE HODINY

**Kognitivní:**
- Žák **přečte** hotový Scratch skript a **vysvětlí** (vlastními slovy), co dělá krok za krokem
- Žák **identifikuje chybu** v kódu a navrhne opravu
- Žák **rozliší** sekvenci příkazů od smyčky a podmínky

**Procesní:**
- Žák pracuje ve dvojici metodou „navigátor/řidič" – jeden čte kód, druhý jej vysvětluje
- Žák záměrně vloží chybu do hotového kódu a nechá spolužáka ji najít (I-9-2-01, I-9-2-02)

**Vazba na RVP ZV 2023:** I-9-2-01 (přečtení a vysvětlení algoritmu), I-9-2-02 (dekompozice – rozložení skriptu na části)

---

## VÝCHOZÍ ZNALOSTI

- Scratch prostředí: sprite, scéna, bloky, kategorie
- Základní pohybové bloky: `jdi`, `otoč se`, `jdi na x: y:`
- Spuštění skriptu: zelená vlajka

**Ověření na začátku (2 min):** Ukáž žákům 3 bloky Scratch – ať řeknou, co každý dělá.

---

## POMŮCKY A ZDROJE

- ✓ Počítačová učebna (PC pro každého nebo dvojice)
- ✓ Projektor pro demo
- ✓ scratch.mit.edu – připravené sdílené projekty k analýze
- ✓ Pracovní list s výtisky Scratch skriptů (viz příloha)
- ✓ Sdílená složka: `H07_debug_start.sb3` (projekt se 3 záměrnými chybami)

---

## PRŮBĚH HODINY

### 0–5 min: ZAHÁJENÍ

- Přivítání, sdělení cíle: *„Dnes se naučíme číst cizí kód. Programátor tráví víc času čtením kódu než psaním. Kdo umí číst kód, umí i opravit chyby."*
- Motivace: *„Zkuste mi říct, co udělá postava, když spustím tento skript"* (promítnout jednoduchý skript na tabuli)

---

### 5–10 min: MOTIVACE / ZADÁNÍ

Promítni na projektor tento Scratch skript:

```
Když je stisknuta [zelená vlajka]:
  jdi na x: 0, y: 0
  opakuj 4 krát:
    jdi 100 kroků
    otoč se o 90 stupňů doprava
```

*„Co tato postava udělá? Zkuste si to říct nahlas."* → Žáci hádají → Spusť ukázku.

Vysvětli princip **krok-za-krokem čtení kódu**:
1. Najdi spouštěcí blok (zelená vlajka, klávesa, ...)
2. Čti bloky shora dolů
3. Smyčka = opakování obsahu N-krát
4. Podmínka = větev ANO/NE

---

### 10–20 min: DEMO (učitel ukazuje, žáci sledují)

**Krok 1 – Čtení skriptu nahlas (technika „code reading")**

Načti skript z projektu `H07_debug_start.sb3` (verze BEZ chyb):

```
Když je stisknuta [zelená vlajka]:
  nastav barvu pera na [modrá]
  nastav velikost pera na 2
  jdi na x: -100, y: 0
  pero dolů
  opakuj 4 krát:
    jdi 100 kroků
    otoč se o 90 stupňů doprava
  pero nahoru
```

Přečti nahlas: *„Postava jde na pozici x:-100, y:0. Spustí pero. Opakuje 4×: jde 100 kroků, otočí se o 90°. Na konci zvedne pero. Výsledek: nakreslí čtverec 100×100."*

**Krok 2 – Záměrná chyba a debugging**

Změň `90°` na `45°` a spusť:
- *„Co se stalo? Proč se nenakreslil čtverec?"*
- *„Jak hledáme chybu? Čteme kód znovu, krok za krokem."*
- Oprav a spusť znovu.

**Krok 3 – Druhý skript: podmínka**

```
Když je stisknuta [zelená vlajka]:
  opakuj vždy:
    pokud <klávesa mezerník stisknuta?>:
      řekni [Stisknuto!] po dobu 1 sekund
    jinak:
      řekni [Čekám...] po dobu 0.5 sekund
```

*„Přečtěte mi to. Co dělá postava, pokud nestisknu mezerník? A pokud stisknu?"*

---

### 20–38 min: SAMOSTATNÁ / PÁROVÁ PRÁCE

**Metoda: Navigátor / Řidič** (párová práce, role se prostřídají po 9 minutách)

Otevřete projekt `H07_debug_start.sb3`. Obsahuje **3 záměrné chyby**:

**Chyba 1:** Skript kreslí trojúhelník místo čtverce
```
opakuj 4 krát:
  jdi 100 kroků
  otoč se o 120 stupňů doprava   ← chyba! (120 je pro trojúhelník)
```

**Chyba 2:** Postava nevychází z bodu [0, 0]
```
jdi na x: 100, y: 100   ← chyba! (startovní bod je špatně)
```

**Chyba 3:** Podmínka nikdy nezareaguje na mezerník
```
pokud <klávesa [A] stisknuta?>:   ← chyba! (má být [mezerník])
  skoč na 5 sekund
```

**Úkol:**
1. Přečtěte každý skript nahlas (navigátor čte, řidič naslouchá)
2. Identifikujte, kde je chyba a **proč** to nefunguje správně
3. Opravte chybu
4. Spusťte a ověřte, zda je opravena

**Zapiš na papír:** Pro každou chybu: co bylo špatně, jak jsi ji opravil/a.

**Nápovědy:**
- Čtverec: 4 rohy → 360° / 4 = 90° na každém rohu
- Trojúhelník: 3 rohy → 360° / 3 = 120°
- Podmínka: kategorie Snímání → blok `klávesa [] stisknuta?`

**Cíl (zvládnout za hodinu):** Opravit všechny 3 chyby a zapsat vysvětlení

---

### 38–43 min: PREZENTACE / SDÍLENÍ

- Dvojice popíše jednu chybu, co bylo špatně, jak ji opravila
- *„Jak jste chybu poznali? Četli jste kód, nebo jste to viděli při spuštění?"*
- Diskuse: Debuggovat = číst kód nebo testovat? (obojí!)

**Bonus aktivita (pokud zbyde čas):**
> *„Teď vy vložte záměrnou chybu do kódu a vyměňte počítače se sousedy."*

---

### 43–45 min: REFLEXE + EXIT TICKET

**Exit ticket** (lístek nebo ústně):
> *„Napiš: Jaký je rozdíl mezi tím, co skript DĚLÁ a co MĚL dělat? Jak to zjistíš?"*

**Uložení práce:**
- Soubor → Uložit do počítače → `H07_opraveno_JMENO.sb3`
- Sdílená složka třídy

---

## DIFERENCIACE

**Pomalejší žáci:**
- Dostanou pracovní list s vytištěnými skripty a podtrhnou podezřelé řádky tužkou
- Opraví jen Chybu 1 (nejjednodušší – čtverec vs. trojúhelník)

**Nadaní žáci:**
- Sami napíší nový skript (min. 8 bloků) a záměrně vloží 2 chyby
- Předají sousedovi k debuggování
- Bonus: Napište skript, který nakreslí pravidelný šestiúhelník (kolik stupňů?)

---

## HODNOCENÍ V HODINĚ

- ✓ Pozorování při párové práci (čtou kód nahlas? hledají systematicky?)
- ✓ Zápisek oprav (co bylo špatně, jak opraveno)
- ✓ Exit ticket

---

## REFLEXE PO HODINĚ

Co se povedlo:    _____________________________________
Co příště jinak:  _____________________________________
Tempo / nestihli: _____________________________________
Technické problémy: __________________________________

---

## PŘÍLOHA – Pracovní list pro debugging

### Analýza skriptu č. 1

```
Když je stisknuta [zelená vlajka]:
  jdi na x: 0, y: 0
  pero dolů
  opakuj 3 krát:
    jdi 80 kroků
    otoč se o 90 stupňů doprava
  pero nahoru
```

**Co skript dělá?** ___________________________

**Jaký tvar se nakreslí?** ___________________

**Je tam chyba? Jaká?** ______________________

**Opravený skript:** _________________________

---

### Analýza skriptu č. 2

```
Když je stisknuta [zelená vlajka]:
  nastav [skóre] na 0
  opakuj vždy:
    pokud <dotýkáš se [hvězda]?>:
      nastav [skóre] na (skóre + 10)
```

**Co skript dělá?** ___________________________

**Co se stane, když se postava NEDOTKNE hvězdy?** _____

**Je tam chyba? Jaká?** ______________________
