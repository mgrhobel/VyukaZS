# Skill: test-matematika

## Účel
Generuje testy z matematiky pro ZŠ (6.–9. ročník) se správným klíčem. Pro 9. ročník podporuje CERMAT formát.

## Kdy použít
Kdykoliv je potřeba vytvořit písemný test, prověrku nebo pětiminutovku z matematiky.

## Instrukce pro AI

### Povinné vstupy (zjisti od uživatele, pokud chybí)
- Ročník (6, 7, 8 nebo 9)
- Téma / tematický celek (např. „Zlomky", „Rovnice", „Pythagorova věta")
- Typ testu: **pětiminutovka** / **prověrka** (20–30 min) / **CERMAT** (9. roč., 50 min)
- Počet bodů celkem (nepovinné; výchozí viz typ)

### Typy testů

#### Pětiminutovka (5–10 min)
- 3–5 příkladů, každý 1–2 body.
- Zaměřena na procvičení jednoho konkrétního postupu.
- Bez kalkulačky (výchozí).

#### Prověrka (20–30 min)
- 4–8 úloh, různá obtížnost (lehčí → těžší).
- Body na každou úlohu vyznačit.
- Celkem doporučeno 20–30 bodů.

#### CERMAT formát (pouze 9. ročník, 50 min)
- **Bez kalkulačky.**
- Celkem **50 bodů**.
- Typy úloh dle reálného JPZ:
  - Uzavřené (výběr ze 4 možností, 1 b)
  - Otevřené krátké (přímý výsledek, 1–2 b)
  - Otevřené komplexní (postup + výsledek, 3–4 b)
- Pokrýt různé tematické celky (číslo, algebra, geometrie, statistika).
- Uvést instrukci: _„Napište postup řešení. Bez kalkulačky."_

### Struktura souboru testu

Klíč (správné odpovědi + bodování) se VŽDY nachází v **témž souboru** jako test, oddělený horizontální čárou a záhlavím.

```markdown
# Test – [Téma] – [X. ročník]

**Jméno:** ___________________  **Třída:** _____  **Datum:** _________

**Celkem bodů: __ / __**  *(hranice: výborný __, chvalitebný __, dobrý __, dostatečný __, nedostatečný __)*

---

## Část A – [název] (__ b)

**1.** [Příklad s konkrétními čísly]  (__b)

...

---
---

# KLÍČ – [Téma] – [X. ročník]

| Úloha | Správná odpověď / postup | Body |
|---|---|---|
| 1 | [výsledek] | __ |
...

**Bodovací hranice:**
| Body | Známka |
|---|---|
| 45–50 | 1 – výborný |
| 35–44 | 2 – chvalitebný |
| 24–34 | 3 – dobrý |
| 14–23 | 4 – dostatečný |
| 0–13  | 5 – nedostatečný |
```

### SVP varianta
Pokud uživatel požádá nebo ročník je 6.–7., vygeneruj také **zjednodušenou SVP variantu**:
- Méně příkladů (70 % rozsahu).
- Jednodušší čísla (celá čísla místo zlomků, menší hodnoty).
- Více prostoru na list pro výpočty.
- Klíč pro SVP variantu odděleně.

### Pravidla
- Veškerý text v češtině.
- Příklady VŽDY konkrétní čísla — žádné abstraktní proměnné v zadání pro žáky.
- Každá úloha má jasně přiřazený počet bodů.
- Klíč obsahuje nejen výsledek, ale i stručný postup u komplexních úloh.
- 9. ročník od března: zaměřit na témata JPZ (CERMAT) — priorita.
