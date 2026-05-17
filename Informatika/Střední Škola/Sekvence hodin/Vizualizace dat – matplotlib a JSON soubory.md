# Vizualizace dat – matplotlib a JSON soubory (SŠ obsah)

> ⚠️ **Tento soubor obsahuje SŠ obsah** přesunutý ze sekvence 9. ročník ZŠ.  
> Doporučená úroveň: **SŠ 1. ročník** (technické obory, informatika).  
> Na ZŠ nahrazeno: textovými tabulkami v Pythonu + grafy v Excelu/Google Sheets.

---

## Původ obsahu

Přesunut z `Informatika/Sekvence hodin/9. ročník.md`:
- **H33** – Vizualizace dat (matplotlib) → tato hodina
- **H34** – JSON soubory (open/with + json.dump/load) → tato hodina

---

## H33 – Vizualizace dat (matplotlib)

### Proč SŠ?
`matplotlib` je externí knihovna s komplexním API, která vyžaduje:
- pochopení figure vs. axes objektů
- konfiguraci os, popisků, barev, markerů
- instalaci `pip install matplotlib`

Na ZŠ nahrazeno Excelem/Google Sheets (stejná funkcionalita, nulová kódovací bariéra).

### Instalace
```bash
pip install matplotlib
```

### Základní grafy
```python
import matplotlib.pyplot as plt

mesice = ["Led", "Úno", "Bře", "Dub", "Kvě", "Čer"]
teploty = [-2, 1, 6, 12, 17, 21]

# Spojnicový graf
plt.plot(mesice, teploty, marker="o", color="red", linewidth=2)
plt.title("Průměrné teploty")
plt.xlabel("Měsíc")
plt.ylabel("Teplota (°C)")
plt.grid(True)
plt.tight_layout()
plt.show()

# Sloupcový graf
plt.bar(mesice, teploty, color="skyblue", edgecolor="navy")
plt.title("Průměrné teploty – sloupcový graf")
plt.show()
```

### Kombinace s API (requests + matplotlib)
```python
import requests
import matplotlib.pyplot as plt

url = "https://api.open-meteo.com/v1/forecast?latitude=50.07&longitude=14.42&daily=temperature_2m_max,temperature_2m_min&timezone=Europe/Prague&forecast_days=7"
r = requests.get(url)
data = r.json()

dny = data["daily"]["time"]
max_t = data["daily"]["temperature_2m_max"]
min_t = data["daily"]["temperature_2m_min"]

plt.figure(figsize=(10, 5))
plt.plot(dny, max_t, marker="o", color="red", label="Max. teplota")
plt.plot(dny, min_t, marker="s", color="blue", label="Min. teplota")
plt.fill_between(dny, min_t, max_t, alpha=0.2, color="orange")
plt.title("Týdenní předpověď počasí – Praha")
plt.xlabel("Den")
plt.ylabel("Teplota (°C)")
plt.legend()
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()
```

### Více typů grafů
```python
import matplotlib.pyplot as plt
import random

# Koláčový graf
aktivity = ["Škola", "Sport", "Hraní", "Spánek", "Jiné"]
hodiny = [6, 2, 3, 8, 5]
plt.pie(hodiny, labels=aktivity, autopct="%1.1f%%", startangle=90)
plt.title("Denní rozvrh")
plt.show()

# Scatter plot
x = [random.randint(0, 100) for _ in range(50)]
y = [xi * 0.8 + random.randint(-10, 10) for xi in x]
plt.scatter(x, y, alpha=0.7, color="green")
plt.title("Scatter plot – korelace")
plt.xlabel("Osa X")
plt.ylabel("Osa Y")
plt.show()
```

### Projekt – Datový průzkum s vizualizací
```
Žáci stáhnou reálná data (počasí, kurzy, sporty) pomocí API
→ Zpracují v Pythonu (statistiky, filtrování)
→ Vizualizují pomocí matplotlib (min. 2 různé typy grafů)
→ Interpretují (co data říkají? co tě překvapilo?)
→ Výstup: Python skript + 3 grafy uložené jako PNG

Hodnocení:
  5b – funkčnost a správnost dat
  4b – matplotlib: min. 2 grafy, popisky, legenda
  3b – statistiky (průměr, min, max, seřazení)
  3b – interpretace a komentář
  5b – prezentace (5 min)
  Max: 20 b
```

---

## H34 (SŠ část) – JSON soubory: open/with + json.dump/load

### Proč SŠ?
Práce se soubory (`open`, `with`, `json.dump`, `json.load`) kombinuje:
- file I/O (nová vrstva OS kontextu)
- JSON serializaci/deserializaci
- kontextové managery (`with` statement)

Na ZŠ nahrazeno: data zůstávají v paměti jako Python slovníky (bez ukládání).

### Instalace
`json` je součástí standardní knihovny – žádná instalace není potřeba.

### Ukládání dat do JSON souboru
```python
import json

zaci = [
    {"jmeno": "Anna", "body": 85, "trida": "9A"},
    {"jmeno": "Bořek", "body": 62, "trida": "9B"},
    {"jmeno": "Cecílie", "body": 91, "trida": "9A"},
]

# Uložit do souboru
with open("zaci.json", "w", encoding="utf-8") as f:
    json.dump(zaci, f, ensure_ascii=False, indent=2)

print("Soubor uložen.")
```

### Načítání ze JSON souboru
```python
import json

# Načíst ze souboru
with open("zaci.json", encoding="utf-8") as f:
    data = json.load(f)

uspesni = [z for z in data if z["body"] > 70]
print(f"Úspěšných: {len(uspesni)}")
for z in uspesni:
    print(f"  {z['jmeno']}: {z['body']} b")
```

### Aktualizace záznamu
```python
import json

with open("zaci.json", encoding="utf-8") as f:
    data = json.load(f)

# Najít a aktualizovat
for z in data:
    if z["jmeno"] == "Bořek":
        z["body"] = 75

with open("zaci.json", "w", encoding="utf-8") as f:
    json.dump(data, f, ensure_ascii=False, indent=2)

print("Aktualizováno.")
```

### Kombinace: API → JSON soubor → matplotlib
```python
import requests, json
import matplotlib.pyplot as plt

# 1. Stáhnout data z API
r = requests.get("https://api.open-meteo.com/v1/forecast?latitude=50.07&longitude=14.42&daily=temperature_2m_max&timezone=Europe/Prague&forecast_days=7")
data = r.json()

# 2. Uložit do JSON
with open("pocasi.json", "w") as f:
    json.dump(data["daily"], f, indent=2)

# 3. Načíst a vizualizovat
with open("pocasi.json") as f:
    ulozena = json.load(f)

plt.bar(ulozena["time"], ulozena["temperature_2m_max"], color="orange")
plt.title("Předpověď počasí – uložená data")
plt.xlabel("Den")
plt.ylabel("Max. teplota (°C)")
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()
```

---

## Vazba na ostatní SŠ obsah

| Téma | Soubor |
|------|--------|
| Soubory a zpracování chyb (open/with/try/except) | `Soubory a zpracování chyb.md` |
| Datová věda – CSV a matplotlib (8.r.) | `Datová věda – CSV a matplotlib.md` |
| OOP a rekurze | `OOP a rekurze.md` |
| Databáze a SQL | `Databáze a SQL.md` |
