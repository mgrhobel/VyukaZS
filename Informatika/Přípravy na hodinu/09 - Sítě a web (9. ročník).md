# Příprava na hodinu – Sítě a web: jak funguje internet (9. ročník)

```
═══════════════════════════════════════════════════════
PŘÍPRAVA NA VYUČOVACÍ HODINU – INFORMATIKA
═══════════════════════════════════════════════════════

Datum:          _______________
Třída:          9.
Hodina č.:      H40–H41  (celkové pořadí v tematickém plánu; blok DT – sítě)
Časová dotace:  45 minut × 2 (nebo 1 × 45 min pro základní přehled)

NÁSTROJ:   ✓ Prohlížeč, příkazový řádek (cmd / PowerShell / Terminál)
           ✓ Nástroje: ping, tracert, nslookup, DevTools (F12)
           ✓ Volitelně: Wireshark (demo od učitele, pro žáky jen prohlídka)

TEMATICKÝ CELEK: Blok DT – Digitální technologie
TÉMA HODINY:     Počítačové sítě a web – IP, DNS, HTTP, klient-server, cloud
```

---

## CÍLE HODINY

**Kognitivní:**
- Žák **vysvětlí**, co je IP adresa a jak ji přiděluje DHCP
- Žák **popíše** princip DNS (překlad domény na IP adresu)
- Žák **rozliší** HTTP a HTTPS a zdůvodní, proč záleží na zeleném zámku
- Žák **vysvětlí** model klient–server na konkrétním příkladu
- Žák **uvede** příklady cloudových aplikací a jejich výhody/nevýhody

**Procesní:**
- Žák zjistí IP adresu svého počítače a interpretuje výsledek
- Žák pomocí `tracert` / `traceroute` sleduje cestu dat k serveru
- Žák prozkoumá HTTP hlavičky v DevTools prohlížeče

---

## VÝCHOZÍ ZNALOSTI

- Hardware: síťová karta, router, kabel/WiFi (7. ročník)
- Binární soustava a kódování dat (6. ročník)
- Základní práce s prohlížečem a internetem

**Ověření na začátku (2 min):**
*„Co se stane, když napíšeš google.com do prohlížeče a stiskneš Enter? Kde je ten web uložen?"*

---

## POMŮCKY A ZDROJE

- ✓ Počítačová učebna s internetem
- ✓ Projektor pro demo
- ✓ Příkazový řádek (cmd.exe nebo PowerShell)
- ✓ DevTools v prohlížeči (F12 → záložka Network)
- ✓ Pracovní list `H40_site_web.pdf`
- ✓ Volitelně: https://howdns.works/ (animované vysvětlení DNS)

---

## PRŮBĚH HODINY

### 0–5 min: ZAHÁJENÍ

- Cíl: *„Dnes si odpovíme na otázku: Co se OPRAVDU stane, když klikneš na odkaz?"*
- Motivace: *„Kolik kroků proběhne, než se načte YouTube video? Odhadněte."*
  → Realita: desítky kroků za méně než 1 sekundu.

---

### 5–20 min: TEORIE – VRSTVY SÍTĚ

#### IP adresa a MAC adresa

```
IP adresa (IPv4):  192.168.1.105   ← přidělena dynamicky (DHCP), může se měnit
IP adresa (IPv6):  2001:0db8:85a3::8a2e:0370:7334  ← budoucnost
MAC adresa:        00:1A:2B:3C:4D:5E  ← pevná (výrobce → karta)

Veřejná IP = adresa routeru (vidí ji internet)
Privátní IP = adresa v domácí síti (192.168.x.x)
```

**Analogie:** IP adresa = poštovní adresa, MAC adresa = rodné číslo zařízení

#### Model klient–server

```
KLIENT (prohlížeč):      → Odešle požadavek (Request)  →
                                                              SERVER (web server)
KLIENT (prohlížeč):      ← Přijme odpověď (Response)  ←

Protokol HTTP/HTTPS: jazyk, kterým klient a server mluví
Status kódy:
  200 OK           → stránka nalezena
  301 Přesměrování → stránka se přesunula
  404 Not Found    → stránka neexistuje
  500 Server Error → server má problém
```

#### DNS – Překlad domény na IP

```
Ty zadáš:  google.com
DNS říká:  google.com = 142.250.185.46
Prohlížeč se připojí k: 142.250.185.46

Hierarchie DNS:
  Root server → .com server → google.com server → 142.250.185.46
```

**Animace DNS:** https://howdns.works/ (doporučeno promítnout, ~3 min)

#### HTTPS a šifrování

```
HTTP  = data cestují jako čitelný text (nebezpečné!)
HTTPS = data jsou šifrovaná (TLS/SSL) – zelený zámek v prohlížeči

Certifikát = potvrzení, že server je opravdu ten, za koho se vydává
           vydávají ho certifikační autority (Let's Encrypt, Comodo...)
```

---

### 20–33 min: PRAKTICKÁ AKTIVITA – Příkazový řádek

**Žáci otevřou cmd.exe nebo PowerShell**

```bash
# Zjistit vlastní IP adresu
ipconfig                    # Windows
# nebo
ip a                        # Linux / macOS

# Odeslat "ping" – ověřit, zda je server dostupný
ping google.com             # Kolik ms trvá odpověď?
ping 8.8.8.8               # Google DNS server

# Sledovat cestu dat (hop po hopu)
tracert google.com          # Windows
traceroute google.com       # Linux / macOS

# Přeložit doménu na IP
nslookup zsbolevec.cz
nslookup google.com
```

**Žáci zaznamenají výsledky:**

```
Pracovní list:
1. Moje IP adresa v lokální síti: _____________
2. Odezva na google.com: _____ ms
3. Kolik hopů projde tracert k google.com? _____
4. Jaká je IP adresa google.com? _____________
5. Co se stalo, když jsi pingoval neexistující doménu? (ping xyznexistuje123.cz)
```

---

### 33–40 min: DEVTOOLS – Zákulisí webu

**Demo v prohlížeči:**

1. Otevři prohlížeč → F12 → záložka **Network**
2. Znovu načti stránku (F5)
3. Žáci vidí: seznam všech požadavků (HTML, CSS, JS, obrázky, API)

**Co zkoumat:**

```
Klikni na první řádek (HTML dokument):
  Headers → Request URL, Request Method (GET), Status Code (200)
  Response → HTML kód stránky

Filtr "Img" → uvidí jen obrázky
Filtr "XHR" → API požadavky (data v JSON)
```

**Diskuse:** *„Kolik požadavků odešle prohlížeč pro načtení YouTube? (může být 100+)"*

---

### 40–43 min: CLOUD A BUDOUCNOST

```
Cloud = vzdálené servery, k nimž přistupuješ přes internet

Příklady:
  Google Drive / OneDrive  → úložiště (SaaS)
  AWS / Azure / Google Cloud → infrastruktura (IaaS)
  GitHub Codespaces         → vývojové prostředí (PaaS)

Výhody: dostupnost odkudkoli, záloha, škálování
Nevýhody: závislost na internetu, soukromí, cena
```

**Diskuse:** *„Je bezpečné ukládat školní práce na Google Drive? Kdo k nim má přístup?"*

---

### 43–45 min: REFLEXE A SHRNUTÍ

- *„Jak se liší veřejná a privátní IP adresa?"*
- *„Co dělá DNS a proč ho potřebujeme?"*
- *„Proč je HTTPS bezpečnější než HTTP?"*
- Domácí úkol: Nainstaluj rozšíření prohlížeče „HTTPS Everywhere" nebo zkontroluj, zda tvoje oblíbené stránky mají HTTPS.

---

## DIFERENCIACE

| Úroveň | Aktivita |
|---|---|
| **Základní** | ping, nslookup, pracovní list s vyplněnými otázkami |
| **Střední** | tracert + DevTools analýza |
| **Rozšíření** | Nastavení vlastního DNS (1.1.1.1 Cloudflare), rozdíl TCP vs UDP |

---

## NAVAZUJÍCÍ TÉMATA

- **Příští hodina:** Kybernetická bezpečnost – hrozby, malware, firewall (DT)
- **9. ročník:** Závěrečný projekt – žáci mohou tvořit webové stránky (AP, DIM)
- **Přesah:** Python `requests` – žáci sami volají API (HTTP GET z programu)

---

## ZDROJE A LITERATURA

- RVP ZV 2021 – výstup **I-9-4-03** (sítě, připojení, charakteristiky)
- ŠVP 4. ZŠ Plzeň – DT, 9. ročník (klient-server, IP, web, cloud)
- ŠVP Bolevecká ZŠ – DT, 7. ročník (sítě, web, cloud, zabezpečení)
- How DNS Works: https://howdns.works/
- MDN Web Docs – HTTP: https://developer.mozilla.org/cs/docs/Web/HTTP
- CS Unplugged – Internet: https://classic.csunplugged.org/activities/
