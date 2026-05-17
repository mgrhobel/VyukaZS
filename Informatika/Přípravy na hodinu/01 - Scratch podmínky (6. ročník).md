# Příprava na hodinu – Scratch podmínky (6. ročník)

```
═══════════════════════════════════════════════════════
PŘÍPRAVA NA VYUČOVACÍ HODINU – INFORMATIKA
═══════════════════════════════════════════════════════

Datum:          _______________
Třída:          6.
Hodina č.:      H9  (celkové pořadí v tematickém plánu)
Časová dotace:  45 minut

NÁSTROJ:   ✓ Scratch (scratch.mit.edu) – v prohlížeči, bez instalace

TEMATICKÝ CELEK: Blok 2 – Algoritmy a programování v Scratch
TÉMA HODINY:     Podmínky v Scratch – pokud / jinak (větvení)
```

---

## CÍLE HODINY

**Kognitivní:**
- Žák **vysvětlí** rozdíl mezi větvením „pokud" a „pokud/jinak"
- Žák **použije** blok podmínky k větvení chování spritu na základě vstupu nebo stavu

**Procesní:**
- Žák samostatně naprogramuje reakci postavy na klávesnici a na dotyk překážky
- Žák otestuje chování podmínky záměrnou změnou hodnot

---

## VÝCHOZÍ ZNALOSTI

- Scratch prostředí: sprite, scéna, bloky
- Smyčka `opakuj vždy`
- Pohyb spritu (jdi, otoč se, nastavení polohy)

**Ověření na začátku (2 min):** Otázka: *„Jak se jmenuje blok, který opakuje příkazy donekonečna?"*

---

## POMŮCKY A ZDROJE

- ✓ Počítačová učebna (PC pro každého nebo dvojice)
- ✓ Projektor pro demo
- ✓ scratch.mit.edu – žáci mají záložku / školní účet připraveny
- ✓ Hotový startovní projekt na sdílené složce: `H09_start.sb3` (sprite + scéna, bez podmínek)

---

## PRŮBĚH HODINY

### 0–5 min: ZAHÁJENÍ

- Přivítání, sdělení cíle: *„Dnes naučíme postavu rozhodovat se – reagovat jinak podle situace."*
- Otázka pro žáky: *„Kdy v životě rozhodujete jinak podle situace? Příklad?"* (Déšť → deštník, jinak slunce → brýle)

---

### 5–10 min: MOTIVACE / ZADÁNÍ

Ukáž hotovou hru: postava se pohybuje po scéně, při dotyku červené barvy zastaví.

*„Jak to funguje? Postava se neustále pohybuje, ale POKUD se dotkne červené – zastavíme ji. To je podmínka. Dnes se to naučíme."*

---

### 10–20 min: DEMO (učitel ukazuje, žáci sledují)

**Krok 1 – Blok `pokud` (základní větvení)**

```
opakuj vždy:
  pokud <klávesa mezerník stisknuta?>:
    řekni "Mezerník!" po dobu 1 sekund
```

- Ukaž v editoru: kategorie Řízení → blok `pokud <> pak`
- Spusť → stiskni mezerník → postava reaguje
- *„Co se děje, když mezerník nestisknu? Nic. Blok `pokud` se zkontroluje, ale podmínka není splněna."*

**Krok 2 – Blok `pokud / jinak`**

```
opakuj vždy:
  pokud <klávesa mezerník stisknuta?>:
    řekni "Stisknuto!" po dobu 0.5 sekund
  jinak:
    řekni "Čekám..." po dobu 0.5 sekund
```

- *„Teď má postava dva možné výstupy. To je větvení – dvě cesty."*

**Krok 3 – Podmínka s pohybem a dotykem barvy**

```
opakuj vždy:
  jdi 3 kroků
  pokud <dotýkáš se barvy [červená]?>:
    zastavit [vše]
```

- Nakresli na scénu červenou zeď
- Spusť → postava dorazí ke zdi a zastaví
- Záměrná chyba: změň barvu na modrou → *„Proč teď nezastaví?"*

---

### 20–38 min: SAMOSTATNÁ / PÁROVÁ PRÁCE

**Zadání (na tabuli nebo vytisknout):**

Otevři startovní projekt `H09_start.sb3` a naprogramuj:

1. **Základní pohyb** – postava se pohybuje šipkami (vlevo/vpravo/nahoru/dolů)
   ```
   opakuj vždy:
     pokud <klávesa šipka vpravo stisknuta?>: jdi 5 kroků vpravo
     pokud <klávesa šipka vlevo stisknuta?>: jdi 5 kroků vlevo
   ```

2. **Překážka** – přidej na scénu červenou zeď/překážku
   - Při dotyku červené: postava se vrátí na startovní pozici (nebo zastaví)

3. **Rozšíření (pro rychlejší):**
   - Přidej proměnnou `životy = 3`
   - Při dotyku překážky sniž životy o 1
   - Pokud životy = 0: zastavit vše

**Nápovědy (připravit na lístek nebo na obrazovce):**
- Blok podmínky: Řízení → `pokud <> pak`
- Barva: Snímání → `dotýkáš se barvy <>`? (klikni na vzorek barvy a pipetou vyber)
- Startovní pozice: `jdi na x: 0 y: -100`

---

### 38–43 min: PREZENTACE / SDÍLENÍ

- 1–2 dobrovolníci ukáží svůj projekt na projektoru
- Třída: *„Co je jiné? Jak jste to řešili?"*
- Porovnej různá řešení – podtrhni, že víc způsobů může být správně

---

### 43–45 min: REFLEXE + EXIT TICKET

**Exit ticket** (lístek nebo ústně):
> *„Vysvětli jednou větou: jaký je rozdíl mezi `pokud` a `pokud/jinak`?"*

**Uložení práce:**
- scratch.mit.edu: Soubor → Uložit nyní + Sdílet (volitelně)
- Nebo: Soubor → Uložit do počítače → složka `Informatika/H09`

---

## DIFERENCIACE

**Pomalejší žáci:**
- Připravit soubor s kostrou (pohyb je hotový, doplnit jen podmínku s barvou)
- Pomoci s pipetou pro výběr barvy (časté místo zaseknutí)

**Nadaní žáci:**
- Přidat 2. překážku (jiná barva = jiná reakce)
- Postava komentuje, co dělá: `řekni "Utíkám!" po 1 s`
- Přidat časovač: proměnná `čas`, každou sekundu +1

---

## HODNOCENÍ V HODINĚ

- ✓ Pozorování a obcházení (kontrola, zda podmínka funguje)
- ✓ Exit ticket (ústně nebo lístek)
- ✓ Sdílení na projektoru

---

## REFLEXE PO HODINĚ

Co se povedlo:    _____________________________________
Co příště jinak:  _____________________________________
Tempo / nestihli: _____________________________________
Technické problémy: __________________________________
