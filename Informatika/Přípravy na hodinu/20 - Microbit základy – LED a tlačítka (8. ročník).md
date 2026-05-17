# Příprava č. 20 – Micro:bit základy: LED displej a tlačítka (8. ročník)

## Základní informace

| Položka | Hodnota |
|---------|---------|
| **Předmět** | Informatika |
| **Ročník** | 8. ročník ZŠ |
| **Délka** | 45 minut |
| **Blok v sekvenci** | BLOK 4 – H31 |
| **Typ hodiny** | Praktická – programování HW/simulátor |

## Cíle hodiny

Po hodině žák:
- otevře prostředí MakeCode a rozumí jeho rozvržení (bloky, simulátor, stažení .hex)
- napíše program, který zobrazí text nebo obrázek na LED displeji
- naprogramuje reakci na stisk tlačítek A a B
- vytvoří jednoduchou animaci (opakující se sekvence snímků)

## Výchozí znalosti žáků

- Zkušenost se Scratch (6.–7. ročník) – bloková editace, smyčky, podmínky
- Znalost základů Pythonu (8.r. BLOK 1) – proměnné, podmínky, smyčky

## Pomůcky a technika

| Potřeba | Alternativa |
|---------|-------------|
| Micro:bit v1 nebo v2 (1 ks na žáka nebo dvojici) | Simulátor na [makecode.microbit.org](https://makecode.microbit.org/) zcela postačí |
| USB kabel micro-USB | – |
| Počítač nebo tablet s prohlížečem | – |
| Dataprojektor | – |

> 💡 **Bez fyzické desky:** Simulátor v MakeCode funguje plně v prohlížeči – klikáním na LED displej a tlačítka A/B. Hodinu lze absolvovat bez jediného Micro:bitu.

---

## Průběh hodiny (45 min)

### 1. Úvod – Co je Micro:bit? (5 min)

**Učitel:**
- Ukáže fyzický Micro:bit (nebo fotografii) – co vidíme?
  - LED displej 5×5 = 25 LED
  - Dvě tlačítka: A a B
  - USB konektor a zlaté pady (vstupy/výstupy)
  - Procesor ARM (jako v mobilu, jen mnohem slabší)
- Kde se Micro:bit používá?
  - BBC ho zdarma rozdal 1 milion britským žákům (2016)
  - Robotické sady, meteostanice, hry, chytré zahrady

**Diskuse (2 min):** *Co bys vymyslel s malým počítačem a 25 LED? → žáci navrhují nápady*

---

### 2. Prostředí MakeCode – orientace (7 min)

**Učitel promítá, žáci otevírají na svých zařízeních: [makecode.microbit.org](https://makecode.microbit.org/)**

Části obrazovky:

| Oblast | Co je | Analogie |
|--------|--------|---------|
| Levý panel – simulátor | Micro:bit v prohlížeči | Scratch Stage |
| Střed – paleta bloků | Kategorie: Základní, Vstup, Smyčky... | Scratch kategorie |
| Pravý panel – kód | Sem táhneme bloky | Scratch skripty |
| Tlačítko „Stáhnout" | Vygeneruje .hex soubor pro fyzický Micro:bit | Scratch „Export" |

**Aktivita:** Klikni na Základní → najdi „zobraz obrázek" → přetáhni do „při spuštění" → ✅ Simulátor reaguje ihned!

---

### 3. Programování LED displeje (10 min)

**Žáci programují – krok za krokem:**

#### Krok 1: Zobraz svůj oblíbený emoji
```
při spuštění:
  zobraz obrázek [srdce / hvězda / šipka / ...]
```
*Zkus různé obrázky. Jaký se zobrazí na simulátoru?*

#### Krok 2: Scrollující text
```
při spuštění:
  zobraz řetězec "Ahoj 8B!"
```
*Pozoruj, jak text „projíždí" displejem. Jak ho zrychlíš/zpomalíš? (interval parameter)*

#### Krok 3: Zobraz číslo
```
při spuštění:
  zobraz číslo 2024
```
*Proč se číslo scrolluje, ale krátký text skoro ne? (závisí na délce)*

**Diskuse:** Jak je na 5×5 LED uložen obrázek? → každá LED = 1 bit (0 = zhasnuto, 1 = svítí) → 25 bitů = ~3 bajty. Odkaz na BLOK 0 (H0a–H0b z 6. ročníku)

---

### 4. Tlačítka A a B – podmínky v HW (10 min)

**Ukázka (učitel live-kóduje):**
```
když je stisknuto A:
  zobraz řetězec "Ahoj!"

když je stisknuto B:
  zobraz číslo 42

když je stisknuto A+B:
  zobraz obrázek [srdce]
```

**Žáci samostatně (6 min):**

Naprogramuj:
- Tlačítko A → zobraz první písmeno svého jména
- Tlačítko B → zobraz emoji dle výběru
- A+B → zobraz celé jméno (scrollující text)

*Tip: Na simulátoru klikej myší na tlačítka A a B.*

---

### 5. Animace – smyčka snímků (8 min)

**Cíl:** Vytvořit animaci alespoň 4 snímků → postavička, odpočítávání, blikání

**Vzor kódu:**
```
opakuj stále:
  zobraz obrázek [LED1 – tvář s úsměvem]
  pauza (ms) 500
  zobraz obrázek [LED2 – tvář bez úsměvu]
  pauza (ms) 500
  zobraz obrázek [LED3 – smutná tvář]
  pauza (ms) 500
  zobraz obrázek [LED4 – otazník]
  pauza (ms) 300
```

**Žáci:** Vytvořte vlastní animaci (téma: sport, zvíře, počasí, emoji). Min. 4 snímky.

*Bonus: Kombinuj animaci + tlačítko: tlačítko A přeruší animaci a zobraz jiný obrázek.*

---

### 6. Závěr a ukázky (5 min)

- 2–3 dobrovolníci ukáží svou animaci (přes projektor nebo fyzický Micro:bit)
- Shrnutí: Co jsme se naučili?
  - MakeCode IDE (bloky → simulátor)
  - LED displej (text, číslo, obrázek)
  - Tlačítka jako vstup
  - Smyčky a pauzy pro animace
- Příště: proměnné, podmínky, senzory

---

## Domácí úkol (volitelné)

Vymysli a nakresli (na papír) svůj projekt na Micro:bit:
- Co by tvůj Micro:bit dělal?
- Které vstupy by používal? (tlačítka, náklon, teplota?)
- Jak by vypadal výstup? (LED, zvuk, barva?)

---

## Diferenciace

| Skupina | Zadání |
|---------|--------|
| **Rychlejší žáci** | Přidají zvuk (Micro:bit v2); propojí animaci s tlačítky; vytvoří "mini hru" (čekej na správný obrázek a zmáčkni A) |
| **Pomalejší žáci** | Dokončí animaci 3 snímků; učitel asistuje při drag-and-drop |
| **Bez fyzické desky** | Vše stejné – simulátor je plnohodnotná alternativa |

---

## Hodnocení

Formativní – učitel obchází a kontroluje:
- ✅ Program funguje v simulátoru
- ✅ Animace má min. 4 snímky
- ✅ Tlačítka A a B reagují různě

---

## Propojení s RVP ZV a ŠVP

| Dokument | Oblast |
|----------|--------|
| **RVP ZV 2023** | Algoritmy a programování (AP): žák navrhuje a testuje algoritmy |
| **ŠVP Starkov** | 8.r. – Micro:bit programovatelná deska (makecode.microbit.org) |
| **Průřezová témata** | OSV – Žák spolupracuje ve dvojici, reflektuje svůj postup |
