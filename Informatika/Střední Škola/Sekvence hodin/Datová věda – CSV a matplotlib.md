# SŠ Informatika – Datová věda: CSV a matplotlib

> **Úroveň:** Střední škola (1.–2. ročník oboru Informatika / gymnázium)  
> **Navazuje na:** Python slovníky, moduly, práce se soubory – ZŠ/SŠ základ  
> **RVP:** Nad rámec RVP ZV 2023; odpovídá RVP SOŠ a datová gramotnost SŠ

---

## Část 1 – Python + CSV (H15–H16)

### Co je CSV?

CSV (Comma-Separated Values) = textový formát pro tabulková data:
```
jmeno,trida,body
Anna,8A,85
Bořek,8B,62
Cyril,8A,91
```

### Čtení CSV souboru

```python
import csv

with open("studenti.csv", newline="", encoding="utf-8") as f:
    ctecka = csv.DictReader(f)
    studenti = list(ctecka)

# Výpis
for s in studenti:
    print(f"{s['jmeno']}: {s['body']} bodů")

# Filtrování: studenti s body > 70
uspesni = [s for s in studenti if int(s["body"]) > 70]
print(f"Úspěšných: {len(uspesni)}")

# Průměr
body = [int(s["body"]) for s in studenti]
prumer = sum(body) / len(body)
print(f"Průměr: {prumer:.1f}")
```

### Zápis do CSV

```python
import csv

novy = {"jmeno": "Jana", "trida": "8A", "body": "82"}

with open("studenti.csv", "a", newline="", encoding="utf-8") as f:
    pisatko = csv.DictWriter(f, fieldnames=["jmeno", "trida", "body"])
    pisatko.writerow(novy)
```

### Aktualizace záznamu

```python
def uprav_body(soubor, jmeno, nove_body):
    with open(soubor, newline="", encoding="utf-8") as f:
        data = list(csv.DictReader(f))
    for radek in data:
        if radek["jmeno"] == jmeno:
            radek["body"] = str(nove_body)
    with open(soubor, "w", newline="", encoding="utf-8") as f:
        w = csv.DictWriter(f, fieldnames=["jmeno", "trida", "body"])
        w.writeheader()
        w.writerows(data)

uprav_body("studenti.csv", "Jana", 90)
```

---

## Část 2 – Python + matplotlib (H17)

### Instalace

```
pip install matplotlib
```

### Základní grafy

```python
import matplotlib.pyplot as plt

# Sloupcový graf
mesice = ["led", "úno", "bře", "dub"]
teploty = [-2, 1, 8, 15]

plt.bar(mesice, teploty, color="steelblue")
plt.title("Průměrné teploty")
plt.xlabel("Měsíc")
plt.ylabel("°C")
plt.show()

# Spojnicový graf
plt.plot(mesice, teploty, marker="o", color="red")
plt.show()

# Histogram: rozdělení dat
body_list = [85, 62, 91, 74, 55, 88, 71, 95, 43, 67]
plt.hist(body_list, bins=5, color="steelblue", edgecolor="black")
plt.xlabel("Body")
plt.ylabel("Počet žáků")
plt.title("Výsledky testu")
plt.show()
```

### Kombinovaný graf (dvě osy)

```python
import matplotlib.pyplot as plt
import csv

with open("teploty.csv", newline="", encoding="utf-8") as f:
    data = list(csv.DictReader(f))

mesice = [r["mesic"] for r in data]
teploty = [float(r["teplota"]) for r in data]
srazky = [float(r["srazky"]) for r in data]

fig, ax1 = plt.subplots()
ax1.bar(mesice, srazky, color="lightblue", label="Srážky (mm)")
ax1.set_ylabel("Srážky (mm)")

ax2 = ax1.twinx()
ax2.plot(mesice, teploty, color="red", marker="o", label="Teplota (°C)")
ax2.set_ylabel("Teplota (°C)")

plt.title("Klima – Praha 2023")
fig.legend(loc="upper right")
plt.tight_layout()
plt.show()
```

---

## Projekt: Datový průzkum (H18–H19)

Žáci provedou datový průzkum na reálných datech:

**H18 – Příprava:**
- Výběr tématu: klimatická data, výsledky ankety, Eurostat, data.gov.cz
- Příprava CSV souboru

**H19 – Analýza:**
- Načtení CSV, filtrování, průměr, maximum, minimum
- Aspoň 2 grafy s popisky (matplotlib)
- Závěrečný výpis nebo výsledkový soubor

**Hodnocení:** CSV data 2b + výpočty 3b + grafy 3b + závěr 2b = 10b

---

## Proč je toto téma pro SŠ?

- `csv.DictReader` a `csv.DictWriter` kombinují file I/O se strukturovanými daty → SŠ
- matplotlib vyžaduje instalaci balíčků, importy z externích knihoven, konfiguraci grafů → SŠ
- Na ZŠ: datová analýza se provádí v Excelu (SUMA, PRŮMĚR, grafy), kde je GUI intuitivní
- Srovnání: Excel je ZŠ ✅; Python + matplotlib je SŠ 🔴
