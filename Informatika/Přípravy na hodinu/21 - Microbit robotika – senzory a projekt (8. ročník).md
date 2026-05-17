# Příprava č. 21 – Micro:bit robotika: senzory, rádio a projekt (8. ročník)

## Základní informace

| Položka | Hodnota |
|---------|---------|
| **Předmět** | Informatika |
| **Ročník** | 8. ročník ZŠ |
| **Délka** | 45 minut (nebo 2× 45 min pro projekt) |
| **Blok v sekvenci** | BLOK 4 – H32 + H33 |
| **Typ hodiny** | Praktická – programování HW/simulátor + projekt |
| **Navazuje na** | Příprava 20 – Micro:bit základy |

## Cíle hodiny

Po hodině žák:
- čte hodnoty ze senzorů Micro:bitu (teplota, akcelerometr, kompas)
- používá proměnné a podmínky ke zpracování senzorových dat
- propojí (nebo simuluje propojení) dvou Micro:bit desek přes rádio
- navrhne a realizuje vlastní projekt využívající min. 1 senzor

## Výchozí znalosti žáků

- Příprava 20 – LED displej, tlačítka, animace v MakeCode
- Scratch: proměnné, podmínky (6.–7.r.)
- Python: proměnné, podmínky, smyčky (8.r. BLOK 1)

---

## Průběh hodiny (45 min)

### 1. Opakování a přechod (5 min)

**Učitel:** *Minule jsme ovládali LED a tlačítka. Co ještě Micro:bit umí?*

Výčet senzorů (ukáž na fyzické desce nebo obrázku):

| Senzor | Co měří | Kategorie v MakeCode |
|--------|---------|---------------------|
| Teploměr | Teplota čipu (≈ teplota vzduchu ±2°C) | Vstup |
| Akcelerometr | Pohyb, náklon, zatřepání, pád | Vstup |
| Kompas (magnetometr) | Světová strana (stupně 0–360) | Vstup |
| Mikrofon (v2) | Hlasitost, detekce tlesknutí | Vstup |
| Světelný senzor | Okolní osvětlení (0–255) | Vstup |

---

### 2. Senzory – praktická ukázka (15 min)

#### A) Teploměr (3 min)
```
při spuštění:
  opakuj stále:
    zobraz číslo (teplota °C)
    pauza (ms) 1000
```
*Uchopit desku v dlani → teplota roste. Proč? (CPU generuje teplo)*

#### B) Akcelerometr – detekce zatřepání (5 min)
```
při zatřepání:
  zobraz obrázek [hvězda]
  přehraj melodii [ba ding]
```
*Simulátor: klikni na ikonu "shake" na bočním panelu*

Pokročilejší – digitální kostka:
```
při zatřepání:
  zobraz číslo (vyber náhodně od 1 do 6)
```

#### C) Náklon – akcelerometr X/Y (4 min)
```
opakuj stále:
  pokud (náklon vpravo > 300):
    zobraz šipku [vpravo]
  jinak pokud (náklon vlevo > 300):
    zobraz šipku [vlevo]
  jinak:
    zobraz obrázek [čtverec – rovně]
```
*Simulátor: pohybuj nakresleným Micro:bitem myší*

#### D) Kompas (2 min)
```
při spuštění:
  opakuj stále:
    zobraz číslo (kompas)
    pauza (ms) 500
```
*Při fyzické desce: nejprve kalibrace (rotace desky), pak zobrazí 0–360°*

---

### 3. Proměnné + podmínky + senzory – krokoměr (7 min)

```
nastaví kroky na 0

při zatřepání:
  změn kroky o 1
  zobraz číslo kroky

když je stisknuto A:
  zobraz číslo kroky

když je stisknuto B:
  nastaví kroky na 0
  zobraz řetězec "Reset!"
```

**Žáci:** Zkopíruj krokoměr a přidej:
- Podmínku: pokud kroky > 20 → zobraz hvězdu "Splněno!"
- Tlačítko A+B: zobraz "Gratuluji!" a resetuj

---

### 4. Bezdrátová komunikace – Radio (8 min)

> 💡 **Bez fyzických desek:** Otevři MakeCode ve 2 záložkách prohlížeče. Nebo simuluj jednosměrně: odesílač pošle → příjemce zobrazí.

**Odesílač (Micro:bit A):**
```
radio nastavit skupinu 7

při stisknutí A:
  radio odeslat řetězec "POMOC"

při stisknutí B:
  radio odeslat číslo teplota
```

**Příjemce (Micro:bit B):**
```
radio nastavit skupinu 7

při přijetí řetězce receivedString:
  zobraz řetězec receivedString

při přijetí čísla receivedNumber:
  zobraz číslo receivedNumber
```

**Aktivita:** Dvojice – jeden programuje odesílač, druhý příjemce.  
Výsledek: digitální walkie-talkie nebo teplotní monitor

---

### 5. Projekt – výběr a zadání (5 min)

Žáci si vyberou 1 projekt (nebo navrhnou vlastní):

| Projekt | Senzory | Výstup |
|---------|---------|--------|
| **A) Meteostanice** | Teplota, světlo | LED zobrazuje teplotu + semafor (studeno/teplo) |
| **B) Krokoměr** | Akcelerometr (zatřepání) | LED čítač kroků, melodie při splnění cíle |
| **C) Kompasová hra** | Kompas | „Ukaž na sever" – LED svítí plně jen při správném směru |
| **D) Bezdrátový souboj** | Tlačítka + radio | Dva hráči – kdo rychleji stiskne tlačítko po signálu? |
| **E) Vlastní návrh** | Libovolné | Žák navrhuje – schválí učitel |

**Zbývající čas + příští hodina:** realizace projektu.

---

### 6. Závěr (5 min)

- Co nového jsme použili? (senzory, proměnné + podmínky, rádio)
- Jak se Micro:bit liší od Scratche? (fyzický svět vs. virtuální)
- Příště: závěrečná prezentace projektů

---

## Hodnocení projektu (H33 – příští hodina)

| Kritérium | Body |
|-----------|------|
| Program funguje (splňuje zadání) | 3 b |
| Použití min. 1 senzoru nebo rádia | 3 b |
| Prezentace a vysvětlení kódu | 2 b |
| **Celkem** | **8 b** |

---

## Diferenciace

| Skupina | Zadání |
|---------|--------|
| **Rychlejší** | Projekt D (bezdrátový souboj) + zvukové efekty; kombinace více senzorů |
| **Pomalejší** | Projekt A (meteostanice) – jednodušší; učitel asistuje |
| **Bez fyzické desky** | Vše funguje v simulátoru; rádio simuluj ve dvou záložkách |

---

## Propojení s RVP ZV a ŠVP

| Dokument | Oblast |
|----------|--------|
| **RVP ZV 2023** | AP – Algoritmy a programování; DIM – Data, informace, modely (senzorová data) |
| **ŠVP Starkov** | 8.r. – Micro:bit robotická stavebnice (robot Photon); Micro:bit programovatelná deska |
| **Průřezová témata** | VDO – Žák diskutuje o dopadu IoT na soukromí; OSV – spolupráce ve dvojicích |

---

## Zdroje a rozšíření

- [makecode.microbit.org](https://makecode.microbit.org/) – IDE (simulátor + fyzická deska)
- [microbit.org/projects](https://microbit.org/projects/) – stovky hotových projektů s návody
- [imysleni.cz – Fyzické programování](https://imysleni.cz/ucebnice/zaklady-informatiky-pro-zakladni-skoly) – česky
- [microbit.org/teach](https://microbit.org/teach/) – pedagogické materiály (EN)
- Robot Photon: [photon-robot.eu](https://photon-robot.eu/) – zákaznická podpora + návody CZ
