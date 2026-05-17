# Příprava na hodinu – Správa souborů, formáty a cloud (7. ročník)

```
═══════════════════════════════════════════════════════
PŘÍPRAVA NA VYUČOVACÍ HODINU – INFORMATIKA
═══════════════════════════════════════════════════════

Datum:          _______________
Třída:          7.
Hodina č.:      H29  (celkové pořadí v tematickém plánu)
Časová dotace:  45 minut

NÁSTROJ:   ✓ Průzkumník souborů (Windows Explorer / Správce souborů)
           ✓ Webový prohlížeč (Google Drive nebo OneDrive – ukázka)
           ✓ Projektor pro demo

TEMATICKÝ CELEK: Blok 1 – Opakování a digitální technologie
TÉMA HODINY:     Správa dat – souborové formáty, komprese, cloud a záloha
```

---

## CÍLE HODINY

**Kognitivní:**
- Žák **rozliší** hlavní souborové formáty a vysvětlí, pro jaké použití se hodí
- Žák **vysvětlí** princip komprese a proč záleží na velikosti souboru
- Žák **porovná** ukládání dat lokálně vs. v cloudu a uvede výhody a nevýhody

**Procesní:**
- Žák organizuje soubory do logické adresářové struktury
- Žák vybere vhodný formát pro konkrétní situaci a zdůvodní výběr (I-9-4-02)

**Vazba na RVP ZV 2023:** I-9-4-02 (ukládání a správa dat ve vhodném formátu s ohledem na jejich další zpracování či přenos)

---

## VÝCHOZÍ ZNALOSTI

- Základní práce se soubory (H3 v 6. ročníku): kopírování, přesouvání, přejmenování
- Přípony souborů: .docx, .jpg, .mp3, .exe, .py
- Cloudové úložiště: žáci pravděpodobně znají Google Drive nebo OneDrive z praxe

**Ověření na začátku (2 min):** *„Co je souborová přípona? Příklad: .jpg – co to je za soubor?"*

---

## POMŮCKY A ZDROJE

- ✓ Počítačová učebna (PC pro každého)
- ✓ Projektor pro demo
- ✓ Sdílená složka: `H29_soubory_test.zip` (soubory různých formátů k analýze)
- ✓ Tabulkový procesor (Excel/Calc) pro porovnání velikostí souborů
- ✓ Kalkulačka (nebo Python shell) pro výpočet přenosové doby

---

## PRŮBĚH HODINY

### 0–5 min: ZAHÁJENÍ

- Přivítání, sdělení cíle: *„Dnes se naučíme, jak správně ukládat data – správný formát, správné místo, záloha. Je to nudné? Počkejte, ukážu vám případ, kde špatná správa dat stála firmu miliony."*
- Případ: `Příklad: Pixar ztratil snímek Toy Story 2 (1998), protože někdo spustil rm -rf a záloha nefungovala. Zachránil ho záložní počítač z domova.`

---

### 5–10 min: MOTIVACE / ZADÁNÍ

Dilema: Jitka má fotky z výletu (500 fotek, každá 5 MB). Chce je:
1. Sdílet s rodinou (email)
2. Archivovat navždy (kvalita!)
3. Nahrát na Instagram (rychle online)

*„Pro každý případ použije jiný formát a jiné úložiště. Jaký a proč?"*
→ Žáci hádají → rozebereme v demo.

---

### 10–20 min: DEMO (učitel ukazuje, žáci sledují)

**Krok 1 – Souborové formáty: přehled**

| Kategorie | Formát | Vlastnost | Použití |
|-----------|--------|-----------|---------|
| **Obrázky** | .jpg | Ztrátová komprese, malý soubor | Fotografie, web |
| | .png | Bezztrátová, průhlednost | Loga, grafy, ikonky |
| | .svg | Vektový (nerozmaže se) | Loga, ikony, tisk |
| | .raw | Bez komprese – maximální kvalita | Profesionální fotografie |
| **Dokumenty** | .docx | Upravitelný text | Word dokument |
| | .pdf | Pevný layout, nešlo by snadno měnit | Faktura, smlouva, tisk |
| | .md | Čistý text s formátováním | Programátoři, GitHub |
| **Data** | .xlsx | Tabulka s vzorci | Excel |
| | .csv | Čistá tabulka (jen data, bez formátu) | Import/export dat, databáze |
| | .json | Strukturovaná data | Web API, aplikace |
| **Archiv** | .zip | Komprese + balení více souborů | Posílání emailem |
| | .7z | Lepší komprese než zip | Archivace |
| **Video/Audio** | .mp4 / .mp3 | Komprimované médiá | Přehrávání |

**Krok 2 – Komprese: jak funguje?**

*„Komprese = zmenšení souboru bez (nebo s malou) ztrátou informace."*

Příklad:
- Obrázek 5 MB → zip → 4,8 MB (obrázek nelze moc zkomprimovat – je již komprimovaný)
- Textový soubor 1 MB → zip → 0,1 MB (text má hodně opakujících se vzorů)
- Video 1 GB → mp4 (H.264) → 200 MB (masivní komprese)

Ukázka v Windows:
- Klikni pravým tlačítkem na složku → Odeslat do → Komprimovaná složka
- Porovnej velikost před a po

**Krok 3 – Cloud vs. lokální ukládání**

| | Lokální (HDD/SSD/USB) | Cloud (Google Drive, OneDrive) |
|--|----------------------|-------------------------------|
| Výhody | Rychlý přístup, bez internetu, soukromí | Přístup odkudkoliv, záloha, sdílení |
| Nevýhody | Ztráta při poruše, krádež, oheň | Závislost na internetu, soukromí (?), cena |
| Kdy použít | Velké soubory, citlivá data | Sdílení, spolupráce, záloha |

**Záloha 3-2-1:**
- 3 kopie dat
- 2 různá média (HDD + cloud)
- 1 kopie mimo budovu

---

### 20–38 min: SAMOSTATNÁ PRÁCE

**Zadání:**

Otevřete složku `H29_soubory_test.zip` (rozbalit do Desktop/H29).

**Úkol 1 – Inventář souborů (10 min):**

Vytvořte tabulku v Excelu:

| Soubor | Formát | Velikost (KB) | Účel souboru | Vhodné pro... |
|--------|--------|---------------|-------------|---------------|
| foto_vylet.jpg | .jpg | ... | Fotografie | Web, sdílení |
| logo_skola.png | .png | ... | Logo | Tisk, prezentace |
| seznam_zaku.csv | .csv | ... | Data | Import do databáze |
| ... | | | | |

**Úkol 2 – Výpočet přenosové doby (5 min):**

Rychlost internetu ve škole: 50 Mb/s (megabit za sekundu)

Vzorec: `čas (s) = velikost souboru (MB) × 8 / rychlost (Mb/s)`

Spočítejte:
- Soubor 10 MB → jak dlouho se přenese?
- Soubor 1 GB → jak dlouho?

**Úkol 3 – Rozhodovací scénáře (5 min):**

Pro každý scénář zvol správný formát a úložiště + zdůvodni:

a) Chceš sdílet školní projekt (text + obrázky) se spolužákem přes email.
b) Ukládáš záznamy ze závodů (časy, jména, umístění) pro pozdější analýzu.
c) Chceš archivovat 1000 fotek ze školy navždy s maximální kvalitou.
d) Posíláš fakturu klientovi, nesmí ji měnit.

**Nápovědy:**
- Formáty pro email: .pdf, .zip (max 25 MB)
- Formát pro data: .csv (otevřitelný v každém nástroji)
- Vhodné pro archivaci fotek: .png nebo .raw (žádná kompresní ztráta)

---

### 38–43 min: PREZENTACE / SDÍLENÍ

- 1 žák ukáže svou tabulku a zdůvodní volby formátů
- *„Souhlasíte? Kde byste zvolili jinak?"*
- Diskuse: *„Co se stane, když posíláte .docx někomu, kdo nemá Word?"* → PDF jako řešení

---

### 43–45 min: REFLEXE + EXIT TICKET

**Exit ticket** (ústně nebo lístek):
> *„Jaký formát bys zvolil/a pro ukládání třídního seznamu žáků se známkami, pokud ho budete importovat do nového školního systému? A proč?"*

**Uložení práce:**
- `H29_soubory_JMENO.xlsx` → sdílená složka

---

## DIFERENCIACE

**Pomalejší žáci:**
- Pracují jen s Úkolem 1 (inventář) a Úkolem 3a, 3b (bez výpočtu)
- Dostanou zjednodušenou tabulku s formáty a jejich popisem jako tahák

**Nadaní žáci:**
- Zjistí, jaké je maximální rozlišení fotografie, aby ji šlo kvalitně vytisknout na A4 (DPI výpočet)
- Napíší Python skript, který projde složku a vypíše velikosti souborů: `os.path.getsize()`
- Porovnají kompresi .zip vs. .7z vs. žádná komprese na stejné sadě souborů

---

## HODNOCENÍ V HODINĚ

- ✓ Tabulka inventáře souborů (správná analýza)
- ✓ Rozhodovací scénáře (zdůvodnění volby formátu)
- ✓ Exit ticket

---

## REFLEXE PO HODINĚ

Co se povedlo:    _____________________________________
Co příště jinak:  _____________________________________
Tempo / nestihli: _____________________________________
Technické problémy: __________________________________

---

## PŘÍLOHA – Přehledový tahák: Souborové formáty

### Obrázky

| Chci... | Použij |
|---------|--------|
| Fotku na web (malá, rychlá) | .jpg |
| Logo nebo ikonu s průhledností | .png |
| Ikonu pro tisk v jakékoli velikosti | .svg |
| Archivovat fotku beze ztráty | .png nebo .raw |

### Dokumenty

| Chci... | Použij |
|---------|--------|
| Sdílitelný dokument k dalšímu editování | .docx |
| Dokument, který nikdo nezmění (smlouva, faktura) | .pdf |
| Data pro import do jiného programu | .csv |
| Programátorský text / GitHub | .md |

### Komprese a záloha

| Potřebuji... | Řešení |
|-------------|---------|
| Poslat více souborů emailem | Zabalit do .zip |
| Maximální kompresi | .7z |
| Záloha dat: pravidlo 3-2-1 | 3 kopie, 2 média, 1 mimo budovu |
