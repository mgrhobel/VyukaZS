# SŠ Matematika – Kombinatorika: Permutace a kombinace

> **Úroveň:** Střední škola (1.–2. ročník gymnázia / SOŠ)  
> **Navazuje na:** Základní pravděpodobnost P(A)=|A|/|Ω| – ZŠ 9. ročník  
> **RVP:** Není součástí RVP ZV 2023; zařazeno v RVP G

---

## Pravidla kombinatoriky

### Pravidlo součtu
Je-li jev A nebo jev B (vzájemně se vylučující), pak počet možností = |A| + |B|.

*Příklad: Výběr sladkosti ze 4 čokoládových nebo 3 bonbónů = 7 možností*

### Pravidlo součinu
Je-li jev A a pak jev B (na sobě nezávislé), pak počet možností = |A| × |B|.

*Příklad: Oblečení – 3 trička × 4 kalhoty = 12 kombinací oblečení*

---

## Permutace

**Permutace** = uspořádání **všech** n prvků (pořadí záleží!)

```
P(n) = n! = n × (n−1) × (n−2) × … × 2 × 1
```

### Faktoriály
```
0! = 1    (definice)
1! = 1
2! = 2
3! = 6
4! = 24
5! = 120
6! = 720
```

### Příklady

**P1:** Kolika způsoby lze seřadit 4 žáky do řady?
```
P(4) = 4! = 24 způsobů
```

**P2:** Kolika slovy lze sestavit ze slova KOLO?
```
Slovo KOLO: K, O, L, O – dvě stejná písmena O
Počet = 4!/2! = 24/2 = 12
```

**P3:** Kolik různých čísel lze sestavit z číslic 1, 2, 3 (bez opakování)?
```
P(3) = 3! = 6 čísel: 123, 132, 213, 231, 312, 321
```

---

## Kombinace (bez opakování)

**Kombinace** = výběr k prvků z n (pořadí **nezáleží**)

```
C(n,k) = n! / (k! × (n−k)!)
```

### Příklady

**K1:** Kolik 3-členných skupin lze sestavit z 8 žáků?
```
C(8,3) = 8! / (3! × 5!) = (8×7×6) / (3×2×1) = 336/6 = 56
```

**K2:** Kolik způsoby lze vybrat 2 knihy z 5?
```
C(5,2) = 5! / (2! × 3!) = (5×4) / (2×1) = 10
```

**K3:** Loterie: z 49 čísel vybereme 6. Kolik kombinací?
```
C(49,6) = 49! / (6! × 43!) ≈ 13 983 816
```

---

## Pravděpodobnost se složenými jevy

### P(obě červené) – výběr bez vracení

Máme 4 červené a 6 modrých koulí (celkem 10). Vytáhneme 2. P(obě červené)?

```
Příznivé: C(4,2) = 6  (vybereme 2 z červených)
Všechny:  C(10,2) = 45
P(obě červené) = 6/45 = 2/15 ≈ 0,133
```

### P(A ∩ B) – nezávislé jevy

Hodíme dvěma kostkami. P(obě sudé)?
```
P(1. sudá) = 3/6 = 1/2
P(2. sudá) = 3/6 = 1/2
P(obě sudé) = 1/2 × 1/2 = 1/4  (jsou nezávislé)
```

---

## Cvičení

1. Kolika způsoby lze seřadit 5 knih na polici?
2. Z 10 studentů vybíráme 3 do komise. Kolik způsobů?
3. V sáčku je 6 červených a 4 zelené kuličky. Vytáhneme 2 bez vracení. P(obě zelené)?
4. Kolik různých čtyřmístných čísel lze sestavit z číslic 1,2,3,4 (bez opakování)?
5. Třída má 15 dívek a 10 chlapců. Výbor 2 dívky a 1 chlapec – kolika způsoby?

### Řešení
1. 5! = 120
2. C(10,3) = 120
3. C(4,2)/C(10,2) = 6/45 = 2/15
4. P(4) = 24
5. C(15,2) × C(10,1) = 105 × 10 = 1050

---

## Proč je toto téma pro SŠ?

- RVP ZV 2023: pouze základní P(A)=|A|/|Ω| a pravidlo součtu/součinu (bez faktoriálů)
- Výpočet n! a C(n,k) vyžaduje abstraktní myšlení a algebraické schopnosti SŠ úrovně
- V JPZ (přijímací zkoušky) se kombinatorické vzorce neobjevují
- Zařazeno v RVP G (gymnázia, 2. ročník) – povinná část maturitní přípravy
