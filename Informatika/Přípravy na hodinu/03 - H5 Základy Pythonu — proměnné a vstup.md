# PŘÍPRAVA NA VYUČOVACÍ HODINU

| Předmět | Ročník | Téma | Hodina |
|---|---:|---|---:|
| Informatika | 8. ročník | Základy Pythonu — proměnné a vstup | H5 |

| Dotace | Cíle | RVP kód | Metody | Pomůcky |
|---:|---|---|---|---|
| 45 minut | - Žák rozumí pojmu proměnná v Pythonu a typu základních hodnot (int, float, str).
- Žák umí načíst vstup pomocí input() a převést na číslo.
- Žák umí napsat jednoduchý program, který sčítá dvě čísla z uživatelského vstupu. | Inf-8-1-01 | motivace, demonstrační demo, samostatná práce na PC v párech, prezentace | počítače s Thonny/VSC, projektor, zadání v textovém souboru |

---

## ÚVOD / Motivace (0–5 min)
Krátké představení: proměnná jako "krabička" pro hodnotu; ukázka reálné situace: kalkulačka sčítání cen.

## VÝKLAD / Demo (5–15 min)
Učitel ukáže krátký kód na projektoru a vysvětlí řádek po řádku.

Ukázka 1 (přiřazení):
```python
a = 5
b = 3
print(a + b)  # vypíše 8
```
Ukázka 2 (vstup a převod):
```python
x = input('Zadej první číslo: ')
y = input('Zadej druhé číslo: ')
# input vrací řetězec, převedeme na int
suma = int(x) + int(y)
print('Součet je', suma)
```
Ukázka 3 (řetězce):
```python
jmeno = input('Jak se jmenuješ? ')
print('Ahoj, ' + jmeno + '!')
```
Vysvětlení: rozdíl mezi int(), float(), str() a chybami při špatném převodu.

## PROCVIČENÍ (15–40 min)
Žáci pracují ve dvojicích na počítačích. Učitel obchází a pomáhá. Tři konkrétní příklady (konkrétní vstupy a očekávané výstupy):

1) Příklad 1:
- Kód: a = 5; b = 3; print(a + b)
- Očekávaný výstup: 8

2) Příklad 2 (vstup uživatele):
- Zadání: Napiš program, který načte dvě celá čísla 7 a 4 (žák zadá při běhu) a vypíše jejich součet.
- Příklad průběhu: Zadej první číslo: 7 \n Zadej druhé číslo: 4 \n Výstup: Součet je 11

3) Příklad 3 (řetězce):
- Zadání: Načti jméno "Pavel" a vypiš "Ahoj, Pavel!".
- Očekávaný výstup: Ahoj, Pavel!

Dále žáci vytvoří jednoduchý skript, který: načte dvě čísla (např. 12 a 5), vypíše jejich součet a průměr (průměr = (12+5)/2 = 8.5).

## SHRNUTÍ (40–43 min)
Krátké zopakování: co je proměnná, jak načteme vstup, proč převádíme typy. 1–2 žáci ukážou své programy stručně projekcí.

## DOMÁCÍ ÚKOL (43–45 min)
Počet úkolů: 3
- Úkol 1 (praktický): Napiš program, který načte dvě čísla (např. 9 a 6) a vypíše jejich součet a rozdíl. (2 výpočty)
- Úkol 2 (popsaný příklad): Vysvětli v 3 větách, proč musíme převádět výstup input() na int() při sčítání čísel. (krátká písemná odpověď)
- Úkol 3 (rozšíření pro zájemce): Uprav program tak, aby počítal průměr tří čísel (zadej konkrétní čísla 4, 5, 7 → průměr = 5.333...). (1 program)

---

DIFERENCIACE

- Pomalejší žáci / SVP: Poskytnout vzorový kód s vyznačenými kroky (komentáře u každého řádku), menší počet vstupů (1 příklad), nápověda jak převést typ.

- Nadaní žáci: Rozšířený úkol — ošetření chybného vstupu (try/except) a převod na float; program, který vypočítá průměr z libovolného počtu čísel zadaných oddělených mezerou.

HODNOCENÍ V HODINĚ

- Hodnocení podle fungujícího programu (spuštění), schopnost vysvětlit použití int() a input(), rychlý kontrolní checklist.
