# Pokročilý Python a sítě – Sekvence hodin (SŠ úroveň)

**Navazuje na:** Python + API, sítě základy (9.r. ZŠ – requests, JSON, HTTP/HTTPS konceptuálně)  
**Doporučený ročník:** 2. ročník SŠ (SOŠ Informatika, Gymnázium IT)  
**Počet hodin:** 3 (H34, H51, H52 dle původní sekvence 9.r.)

---

## H34 – Web scraping s BeautifulSoup

**Cíl:** Automatizovaně stahovat a zpracovávat data z webových stránek.

> ⚠️ **Etika web scrapingu:** Vždy zkontroluj `robots.txt` (např. `https://example.com/robots.txt`).  
> Nepoužívej scraping na stránky, kde to je zakázáno. Přidej pauzu mezi požadavky (`time.sleep()`).

### Potřebné knihovny
```bash
pip install requests beautifulsoup4
```

### Základní příklad – stažení a parsování HTML
```python
import requests
from bs4 import BeautifulSoup
import time

url = "https://books.toscrape.com/"  # legální testovací web pro scraping

response = requests.get(url)
response.encoding = "utf-8"

soup = BeautifulSoup(response.text, "html.parser")

# Najít všechny názvy knih
knihy = soup.find_all("article", class_="product_pod")

for kniha in knihy:
    nazev = kniha.find("h3").find("a")["title"]
    cena  = kniha.find("p", class_="price_color").text
    print(f"{nazev}: {cena}")
```

### Procházení více stránek (pagination)
```python
import requests
from bs4 import BeautifulSoup
import time
import csv

vsechny_knihy = []

for stranka in range(1, 6):  # prvních 5 stránek
    url = f"https://books.toscrape.com/catalogue/page-{stranka}.html"
    response = requests.get(url)
    soup = BeautifulSoup(response.text, "html.parser")

    for kniha in soup.find_all("article", class_="product_pod"):
        nazev = kniha.find("h3").find("a")["title"]
        cena  = float(kniha.find("p", class_="price_color").text.replace("Â£", ""))
        rating_text = kniha.find("p", class_="star-rating")["class"][1]
        vsechny_knihy.append({"nazev": nazev, "cena": cena, "rating": rating_text})

    time.sleep(1)  # pauza – nespamuj server!
    print(f"Stažena stránka {stranka}")

# Export do CSV
with open("knihy.csv", "w", newline="", encoding="utf-8") as f:
    writer = csv.DictWriter(f, fieldnames=["nazev", "cena", "rating"])
    writer.writeheader()
    writer.writerows(vsechny_knihy)

print(f"Celkem nalezeno {len(vsechny_knihy)} knih, uloženo do knihy.csv")
```

### BeautifulSoup – přehled metod
| Metoda | Popis |
|--------|-------|
| `soup.find("tag")` | První výskyt tagu |
| `soup.find_all("tag")` | Všechny výskyty tagu |
| `soup.find("tag", class_="xyz")` | Tag s danou CSS třídou |
| `element["atribut"]` | Hodnota HTML atributu (href, src, …) |
| `element.text` | Textový obsah elementu |
| `element.get_text(strip=True)` | Text bez nadbytečných mezer |

### Kdy použít scraping vs. API
| Situace | Doporučení |
|---------|-----------|
| Web nabízí veřejné API | Vždy preferuj API – stabilnější, legálnější |
| Web nemá API, data jsou veřejně dostupná | Scraping s respektem k robots.txt |
| Data jsou za přihlášením | Právně problematické – konzultuj podmínky |

### Cvičení H34
1. Stáhni seznam nejnovějších článků z `https://news.ycombinator.com/` (Hacker News) – nadpis + URL.
2. Stáhni tabulku z Wikipedie (najdi HTML tabulku pomocí `soup.find("table")`).
3. Porovnej: totéž datum z openmeteo.com – jednou přes API (JSON), jednou ze stránky (scraping). Co je jednodušší?

---

## H51 – SQL Injection – Útok a obrana

**Cíl:** Pochopit jak SQL injection funguje a jak se mu bránit.

> ⚠️ **Etické upozornění:** SQL injection demonstrujeme POUZE na lokálním vlastním kódu. Pokus o SQL injection na cizím systému je trestným činem (zákon č. 40/2009 Sb. § 230).

### Co je SQL injection?

Útočník vloží SQL kód do vstupního pole aplikace a manipuluje s databázovým dotazem.

### Zranitelný kód (NIKDY nedělej takhle)
```python
import sqlite3

conn = sqlite3.connect("users.db")
cursor = conn.cursor()

# Vytvoření testovací tabulky
cursor.execute("CREATE TABLE IF NOT EXISTS users (id INTEGER PRIMARY KEY, username TEXT, password TEXT)")
cursor.execute("INSERT OR IGNORE INTO users VALUES (1, 'admin', 'tajneheslo123')")
conn.commit()

def prihlaseni_NEBEZPECNE(username, password):
    # CHYBA: přímé vkládání uživatelského vstupu do SQL!
    dotaz = f"SELECT * FROM users WHERE username = '{username}' AND password = '{password}'"
    print(f"Spouštím: {dotaz}")
    cursor.execute(dotaz)
    return cursor.fetchone()

# Normální přihlášení
print(prihlaseni_NEBEZPECNE("admin", "tajneheslo123"))
# Výsledek: (1, 'admin', 'tajneheslo123')

# SQL INJECTION útok!
print(prihlaseni_NEBEZPECNE("admin", "' OR '1'='1"))
# Spouštím: SELECT * FROM users WHERE username = 'admin' AND password = '' OR '1'='1'
# '1'='1' je vždy True → útočník se přihlásí BEZ hesla!

# Destruktivní injection
print(prihlaseni_NEBEZPECNE("'; DROP TABLE users; --", ""))
# Spouštím: SELECT * FROM users WHERE username = ''; DROP TABLE users; --' AND password = ''
# Smaže celou tabulku users!
```

### Bezpečný kód – parametrizované dotazy
```python
def prihlaseni_BEZPECNE(username, password):
    # SPRÁVNĚ: parametry předáme odděleně, SQLite je escapuje automaticky
    cursor.execute(
        "SELECT * FROM users WHERE username = ? AND password = ?",
        (username, password)  # hodnoty jako tuple
    )
    return cursor.fetchone()

# Útok selže – vstup je považován za data, ne za SQL kód
print(prihlaseni_BEZPECNE("admin", "' OR '1'='1"))
# None – správně odmítne útok
```

### Proč parametrizované dotazy fungují?
```
Nebezpečný: SQL + data = jeden string → databáze nerozlišuje
Bezpečný:   SQL ≠ data → databáze zpracuje odděleně
             Vstup je vždy String, nikdy SQL příkaz
```

### Další obrany
| Obrana | Popis |
|--------|-------|
| Parametrizované dotazy | **Primární obrana – vždy povinná** |
| ORM (SQLAlchemy) | Automaticky parametrizuje |
| Whitelist validace vstupu | Přijímej jen očekávané formáty |
| Princip nejmenších práv | DB uživatel jen s nutným oprávněním |
| WAF (Web Application Firewall) | Detekuje SQL injection patterny |

### Reálné dopady SQL injection
- **2008 – Heartland Payment Systems:** 130 milionů karet ukradeno SQL injection
- **2011 – Sony PlayStation Network:** 77 milionů účtů
- **OWASP Top 10:** Injection byl na #1 po 10 let; od 2021 na #3

### Cvičení H51
1. Implementuj zranitelnou přihlašovací funkci, otestuj 3 různé SQL injection techniky.
2. Oprav funkci pomocí parametrizovaných dotazů a ověř, že všechny útoky selžou.
3. Vyhledej CVE záznamy pro reálné SQL injection zranitelnosti (cve.mitre.org).

---

## H52 – Wireshark a analýza síťového provozu

**Cíl:** Zachytávat a analyzovat síťový provoz, pochopit OSI model v praxi.

> ⚠️ **Legální upozornění:** Zachytávání provozu je legální POUZE ve vlastní síti nebo se souhlasem správce sítě. Odposlouchávání cizího provozu je trestný čin (§ 182 trestního zákoníku – narušení tajemství zpráv).

### Instalace Wireshark
- Download: https://www.wireshark.org/download.html
- Windows: instalovat s Npcap driverem (pro zachytávání)
- Linux: `sudo apt install wireshark`

### Základní rozhraní Wireshark
```
[Toolbar]
[Filter bar]              ← zadáváme filtry
[Packet list]             ← seznam zachycených paketů
[Packet details]          ← detail vybraného paketu (OSI vrstvy)
[Packet bytes]            ← hexdump
```

### OSI model v praxi – Wireshark zobrazení
| Vrstva | Název | Příklad v Wireshark |
|--------|-------|---------------------|
| 7 | Aplikační | HTTP request, DNS query |
| 6 | Prezentační | TLS/SSL handshake |
| 5 | Relační | Řízení session |
| 4 | Transportní | TCP segment (SYN, ACK), UDP datagram |
| 3 | Síťová | IP paket (zdrojová/cílová IP) |
| 2 | Linková | Ethernet frame (MAC adresy) |
| 1 | Fyzická | Přenosové médium (signál) |

### Zachytávání a filtry

```
# Základní filtry v Wireshark:

http                          # jen HTTP traffic
tcp.port == 80                # port 80
ip.addr == 192.168.1.1        # konkrétní IP
dns                           # DNS dotazy a odpovědi
http.request.method == "POST" # POST requesty
tcp.flags.syn == 1            # TCP SYN pakety (navazování spojení)
```

### Cvičení – analýza HTTP vs HTTPS

**Postup:**
1. Otevři Wireshark, vyber síťový adaptér
2. Spusť zachytávání
3. V prohlížeči otevři `http://neverssl.com/` (HTTP, nešifrované)
4. Zastav zachytávání, filtruj `http`
5. Prohlédni HTTP GET request – vidíš URL, hlavičky, obsah
6. Opakuj s `https://example.com/` – zachycená data jsou šifrovaná (TLS)

**Závěr:** HTTP = čitelný text; HTTPS = šifrovaný provoz (obsah neviditelný)

### Analýza TCP handshake
```
Klient            Server
  │──── SYN ────►│   # klient navazuje spojení
  │◄─── SYN+ACK─│   # server potvrzuje
  │──── ACK ────►│   # klient potvrzuje
  │   (spojení)  │
  │──── FIN ────►│   # ukončení spojení
  │◄─── ACK ────│
  │◄─── FIN ────│
  │──── ACK ────►│
```
Filtr Wireshark: `tcp.flags.syn == 1 || tcp.flags.fin == 1`

### DNS analýza
```
# Sleduj DNS dotazy – co tvůj počítač resolvuje
Filtr: dns

# Každý DNS řádek ukáže:
# - dotaz: "Co je IP adresa google.com?"
# - odpověď: "142.250.203.142"
```

### Projekt H52 – síťová analýza
Zachyť provoz při:
1. Návštěvě 5 webových stránek
2. Odeslání e-mailu (pokud přes nešifrovaný SMTP)
3. DNS lookup `nslookup wikipedia.org`

Vytvoř report: kolik paketů, jaké protokoly (pie chart), porovnání HTTP vs HTTPS.

### Alternativa bez Wireshark – Chrome DevTools Network
Pro výukové účely lze použít DevTools (F12 → Network):
- Vidíme HTTP requesty a responses
- Hlavičky, cookies, timing
- Nepotřebuje instalaci Npcap
- Omezeno na provoz prohlížeče
