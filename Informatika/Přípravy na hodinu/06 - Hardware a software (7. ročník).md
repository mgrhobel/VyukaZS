# Příprava na hodinu – Hardware a software (7. ročník)

```
═══════════════════════════════════════════════════════
PŘÍPRAVA NA VYUČOVACÍ HODINU – INFORMATIKA
═══════════════════════════════════════════════════════

Datum:          _______________
Třída:          7.
Hodina č.:      H36  (celkové pořadí v tematickém plánu; blok DT)
Časová dotace:  45 minut

NÁSTROJ:   ✓ Prohlížeč (Google, Speccy online nebo CPU-Z screenshot)
           ✓ Volitelně: skutečný HW (vyřazená základní deska, RAM, HDD)
           ✓ Prezentace učitele (klíčové pojmy + schéma PC)

TEMATICKÝ CELEK: Blok 4 – Digitální technologie (DT)
TÉMA HODINY:     Hardware a software – součásti počítače, operační systém
```

---

## CÍLE HODINY

**Kognitivní:**
- Žák **pojmenuje** hlavní hardwarové součásti PC a popíše jejich funkci
- Žák **vysvětlí** rozdíl mezi hardwarem, softwaarem a operačním systémem
- Žák **uvede** příklady aplikačního softwaru a porovná OS (Windows, Linux, macOS)

**Procesní:**
- Žák zobrazí a zaznamená parametry vlastního školního počítače (procesor, RAM)
- Žák přiřadí konkrétní úlohu ke správné součásti PC

---

## VÝCHOZÍ ZNALOSTI

- Základní práce s PC (spuštění, uložení souboru, práce s prohlížečem)
- Scratch z 6. ročníku – program = sada instrukcí
- Pojem „data" z 6. ročníku (binární kódování)

**Ověření na začátku (2 min):**
*„Jmenujte 5 věcí, které jsou na počítači fyzicky vidět nebo hmatat."* (myš, klávesnice, monitor, kabel, USB…)

---

## POMŮCKY A ZDROJE

- ✓ Počítačová učebna
- ✓ Projektor pro demo
- ✓ Volitelně: vyřazené HW komponenty k ohledání
- ✓ Pracovní list `H36_hw_sw.pdf` (popis, schéma PC, pracovní tabulka)
- ✓ Příloha – schéma „Cesta dat v počítači" (CPU ↔ RAM ↔ Disk ↔ GPU ↔ I/O)

---

## PRŮBĚH HODINY

### 0–5 min: ZAHÁJENÍ

- Přivítání, cíl: *„Dnes si rozebereme počítač na součástky – pochopíme, co co dělá a proč to potřebujeme vědět."*
- Brainstorming (ústní): *„Kolik součástí má počítač? Jmenujte vše, co vás napadne."*
  - Žáci jmenují, učitel zapisuje na tabuli → pak kategorizuje na HW / SW / OS

---

### 5–20 min: PŘEDNÁŠKA + DISKUSE

#### Hardware – fyzické součásti

| Součást | Zkratka | Funkce | Analogie |
|---|---|---|---|
| Procesor | CPU | Provádí výpočty | Mozek |
| Operační paměť | RAM | Dočasné úložiště při práci | Pracovní stůl |
| Pevný disk / SSD | HDD / SSD | Trvalé uložení dat | Šuplíkový regál |
| Grafická karta | GPU | Zpracování obrazu | Malíř / výtvarník |
| Základní deska | MB | Propojuje všechny součásti | Páteř |
| Napájecí zdroj | PSU | Dodává energii | Srdce |
| Monitor / klávesnice / myš | I/O | Vstup a výstup | Smysly + hlas |

**Typy počítačů:**
```
Desktop → věž + monitor (výkon, opravitelnost)
Notebook → vše v jednom (přenosnost)
Tablet / smartphone → ARM, dotyk (baterie)
Server → bez monitoru, 24/7 běh, RAID disky
```

#### Software – programy a systémy

```
OPERAČNÍ SYSTÉM (OS):
  Windows 11, macOS, Linux (Ubuntu, Fedora), Android, iOS
  → Spravuje HW, spouští programy, uživatelské rozhraní

APLIKAČNÍ SOFTWARE:
  Libreoffice Calc, Chrome, VS Code, Scratch, Minecraft
  → Konkrétní úloha pro uživatele

FIRMWARE:
  BIOS/UEFI – spustí OS po zapnutí počítače
  → Podobně jako BIOS v tiskárně nebo televizi
```

**Otázka pro žáky:**
*„Je Windows zdarma? A Linux? Proč to tak je?"* → Diskuse o open source vs. proprietární SW

---

### 20–30 min: PRAKTICKÁ AKTIVITA – Co má náš počítač?

**Žáci zjistí parametry svého PC:**

```
Windows: Nastavení → Systém → O počítači
   → Procesor: Intel Core i5-xxxx @ x.x GHz
   → Instalovaná RAM: 8 GB
   → Typ systému: 64bitový

Správce úloh (Ctrl+Shift+Esc) → záložka Výkon:
   → Aktuální využití CPU a RAM (%)
   → Typ a rychlost disku
```

**Pracovní tabulka (žáci vyplňují):**

```
Počítač v učebně:
  CPU:       _______________________   Počet jader: ___
  RAM:       _____ GB                  Využití: _____%
  Disk:      _____ GB   Typ: SSD / HDD
  OS:        _______________________   Verze: ________
```

---

### 30–38 min: SROVNÁNÍ A POROZUMĚNÍ

**Scénáře k diskusi (žáci pracují ve dvojicích):**

```
1. Máš 2 možnosti: CPU Intel i3 + 16 GB RAM  vs.  CPU Intel i7 + 4 GB RAM
   Co si vybereš pro hraní her? Proč?

2. Kamarádka říká: „Mám plný disk, proto je počítač pomalý."
   Je to pravda? Co skutečně zpomaluje PC při práci?

3. Chceš nainstalovat program, ale OS říká: „Nedostatek oprávnění."
   Proč? Co musíš udělat? (→ administrátor)

4. Linux je zdarma, Windows stojí 3 500 Kč. Proč školy (nebo firmy) platí za Windows?
```

---

### 38–43 min: SOUHRN – SCHÉMA „CESTA DAT"

Učitel nakreslí na tabuli / promítne:

```
  Klávesnice → CPU → RAM → SSD → GPU → Monitor
  (vstup)   (výpočet) (dočas.) (trvalé) (výstup)
```

*„Napíšu 'A' → CPU přijme signál → uloží do RAM → zobrazí GPU → vidíme na monitoru."*

---

### 43–45 min: REFLEXE

- *„Co je rozdíl RAM vs. SSD?"*
- *„Proč má server hodně RAM, ale žádný monitor?"*
- Domácí úkol: Zjisti parametry počítače doma nebo telefonu. Porovnáš příště.

---

## DIFERENCIACE

| Úroveň | Aktivita |
|---|---|
| **Základní** | Přiřazení součástí ke funkcím (pracovní list – párování) |
| **Střední** | Scénáře + tabulka parametrů |
| **Rozšíření** | Srovnání ARM vs. x86, proč Apple Silicon (M1/M2) dominuje |

---

## NAVAZUJÍCÍ TÉMATA

- **Příští hodina:** Počítačové sítě – jak se PC připojí k internetu (DT)
- **8. ročník:** Formáty souborů a datová komprese (DT)
- **Přesah:** Výběr PC (doporučení pro herní, grafický, školní PC)

---

## ZDROJE A LITERATURA

- RVP ZV 2021 – výstup **I-9-4-01** (jak funguje počítač – HW i OS)
- ŠVP 4. ZŠ Plzeň – DT, 7. ročník (hardware a software, součásti PC)
- ŠVP Bolevecká ZŠ – DT, 7. ročník (hardware a software, OS, typy souborů)
- Speccy (CPU-Z): https://www.cpuid.com/softwares/cpu-z.html
