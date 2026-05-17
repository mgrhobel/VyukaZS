# Informatika – Střední škola (SŠ obsah)

Tato složka obsahuje obsah **přesahující rámec ZŠ** (RVP ZV 2023), přesunutý sem z hlavní složky Informatika.  
Materiály navazují na ZŠ učivo a jsou vhodné pro **1.–2. ročník SŠ** (SOŠ Informatika, Gymnázium).

> 📌 Obsah vychází z: **RVP SOŠ Informatika (18-20-M01)** a **RVP Gymnázia (RVPG 2007)**.  
> Na ZŠ je zařazení volitelné pouze jako silně rozšiřující přesah pro mimořádně pokročilé žáky.

---

## Přehled souborů

### 📂 Sekvence hodin/

| Soubor | Obsah | Návaznost |
|--------|-------|-----------|
| `OOP a rekurze.md` | Objektově orientované programování (class, dědičnost), rekurzivní algoritmy | Navazuje na Python 8.r. ZŠ |
| `Databáze a SQL.md` | Relační databáze, ER diagramy, SQL (SELECT, INSERT, JOIN), Python+SQLite | Navazuje na datovou analýzu 8.r. ZŠ |
| `Pokročilý Python a sítě.md` | Web scraping (BeautifulSoup), SQL injection demo, Wireshark, sítě pokročile | Navazuje na Python a sítě 9.r. ZŠ |
| `Soubory a zpracování chyb.md` | Python: open/with, try/except, práce se soubory, deník projekt | Navazuje na Python základy 8.r. ZŠ |
| `Datová věda – CSV a matplotlib.md` | csv.DictReader/Writer, matplotlib grafy, datový průzkum projekt | Navazuje na datovou analýzu 8.r. ZŠ |
| `Vizualizace dat – matplotlib a JSON soubory.md` | matplotlib (grafy, kombinace s API), JSON soubory (open/json.dump/load) | Navazuje na Python + API 9.r. ZŠ |

### 📂 Projekty a testy/

| Soubor | Obsah |
|--------|-------|
| `SŠ témata – Projekty a testy.md` | Testové otázky a projekty zaměřené na OOP, SQL, databáze; 8.r. části (soubory, lambda, CSV); 9.r. Datový průzkum (API + matplotlib) |

---

## Proč byl obsah přesunut?

| Téma | Důvod přesunu |
|------|---------------|
| OOP (třídy, dědičnost) | Není v RVP ZV 2023; standardně 1. ročník SŠ |
| Rekurze, memoization | SŠ/VŠ algoritmika; RVP ZV nevyžaduje |
| SQL, databáze, ER diagramy | RVP SOŠ standard; RVP ZV 2023 neobsahuje |
| Python + SQLite | Kombinace dvou SŠ témat |
| Web scraping (BeautifulSoup) | Parsing HTML = SŠ/VŠ úroveň |
| SQL injection demo s kódem | Předpokládá znalost SQL |
| Wireshark, OSI model (podrobně) | Síťové obory SOŠ |
| **Python: soubory (open/with)** | Nová vrstva OS kontextu; standardně SŠ 1.r. |
| **Python: try/except** | Ošetření výjimek = SŠ 1.r. |
| **Python: csv.DictReader/Writer** | Kombinuje file I/O + struktury = SŠ |
| **matplotlib** | Externí knihovna, komplexní API = SŠ |
| **JSON soubory (open + json.dump/load)** | File I/O = SŠ; JSON z API (r.json() = dict) zůstává ZŠ |

---

## Doporučené použití

- **SŠ informatika 1. ročník:** OOP + Databáze (v tomto pořadí)
- **SŠ informatika 2. ročník:** Pokročilý Python, sítě, bezpečnost
- **ZŠ volitelný seminář / kroužek:** Možné použít selektivně pro mimořádně nadané žáky s výslovným upozorněním na obtížnost
