# Copilot Instructions – VyukaZS

Repozitář obsahuje výukové materiály pro učitele matematiky a informatiky na 2. stupni ZŠ (6.–9. ročník), v souladu s **RVP ZV 2023**. Veškerý obsah je v **češtině**. Jde o čistě dokumentační repozitář – žádný kód ke kompilaci, žádné testy ani lintovací příkazy.

---

## Architektura repozitáře

```
VyukaZS/
├── 00 - Přehled a plán.md          ← roční harmonogram, hodinové dotace
├── 07 - Zdroje a metodika.md       ← učebnice, online zdroje, metodické tipy, admin checklist
├── Učebnice a materiály.md         ← přehled učebnic Prometheus + stránkové reference
├── Nápady na procvičování.md       ← 40+ aktivit, her a online nástrojů
├── Matematika/
│   ├── 01–04 - [ročník].md         ← tematické plány (přehled témat na celý rok)
│   ├── Sekvence hodin/[ročník].md  ← hodina po hodině (H1, H2, …) s příklady a DÚ
│   ├── Přípravy na hodinu/         ← plné přípravy dle šablony; 00 = master šablona
│   └── Testy/[ročník] - Testy.md  ← písemky s klíči
└── Informatika/
    ├── 05–06 - [ročníky].md        ← tematické plány
    ├── Sekvence hodin/             ← H1–H58 pro každé ročníkové pásmo
    └── Projekty a testy/           ← zadání projektů a testů
```

**FPE_markdown/** – importované materiály z fakulty (FPE ZČU), slouží jako referenční podklady; neupravovat bez důvodu.

---

## Klíčové konvence obsahu

### Pojmenování a číslování souborů
- Soubory mají dvouciferný číselný prefix: `00 - `, `01 - `, atd.
- Hodiny v sekvencích jsou číslovány `H1`, `H2`, … (ne „hodina 1").
- Testy jsou číslovány `T1`, `T2`, … v rámci souboru daného ročníku.

### Přípravy na hodinu
Každá příprava dodržuje strukturu ze šablony (`Matematika/Přípravy na hodinu/00 - Šablona přípravy.md`):

| Sekce | Obsah |
|---|---|
| Záhlaví (tabulka) | Předmět, ročník, téma, číslo hodiny v sekvenci (H__), časová dotace, cíle, výstup RVP ZV, metody, pomůcky |
| Průběh hodiny | Fáze s časovými rozsahy: ÚVOD/Motivace → VÝKLAD → PROCVIČENÍ → SHRNUTÍ → DÚ |
| Diferenciace | Pomalejší žáci / žáci se SVP **a** rychlejší / nadaní žáci |
| Reflexe | Vyplňuje se **po** hodině |

Příklady vždy psát konkrétně s čísly (ne „procvičení zlomků", ale `3/4 + 1/6 = ?`).

Přípravy na informatiku mají odlišnou strukturu (Motivace → Demo → Samostatná/párová práce → Prezentace → Reflexe → Uložení práce) – viz šablona.

### Reference na učebnice
- Primární učebnice matematiky: **Prometheus** (Odvárko, Kadleček)
- Zkratky: `UČ` = učebnice, `SÚ` = sbírka úloh, `DÚ` = domácí úkol, `TP` = tabule/projektor
- Formát citace: `SÚ str. X, č. Y–Z`
- Reference stránek jsou **orientační** – vždy ověřit s konkrétním vydáním, které škola používá.

### RVP kódy
Každá příprava odkazuje na výstup RVP ZV (např. `M-9-1-01`). Matematika: kódy M-_, Informatika: kódy dle nového RVP 2023.

### Testy a klíče
- Klíče jsou součástí stejného souboru jako testy.
- 9. ročník obsahuje simulaci JPZ (CERMAT formát, 50 bodů, bez kalkulačky).
- Klíče testů prošly rubber duck review – při úpravě ověřit správnost výsledků.

---

## Kontext výuky (důležité pro generování obsahu)

- **Matematika** – hlavní řada Prometheus; sekvence počítá s **5 h/týden** (6. roč.) resp. 4 h/týden (7.–9. roč.)
- **Informatika** – RVP 2023: zaměření na **výpočetní myšlení a programování** (Scratch → Python → HTML/CSS/JS), ne kancelářský SW
- **9. ročník** – od března priorita přípravy na JPZ (CERMAT); materiály na cermat.cz jsou zdarma
- **Žáci se SVP** – vždy zahrnout diferenciaci; kratší příklady, více času, tabulky vzorců
- **Hejného matematika** – část žáků 6. ročníku ji má z 1. stupně; konstruktivistický přístup bez algoritmů – zohledňovat v úvodu témat
- Nástroje používané v hodinách: **GeoGebra** (geometrie, grafy), **Scratch** (6.–7. roč.), **Thonny/Python** (8.–9. roč.), **VS Code** (HTML/CSS)
