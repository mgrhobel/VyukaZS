---
title: "kartprojekce.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/1. Semestr/G3/Pracovní materiály na pøednáku a cvièení/Navíc/kartprojekce.pdf"
date: 2008-09-28
type: PDF (text-based)
---

Deskriptivní geometrie 1

Základy kartografických projekcí 1

Základy kartografických projekcí

Významné křivky na ploše

Úvodní pojmy

Ortodroma
– nejkratší spojnice dvou bodů na ploše (na kulové ploše je to kratší z
oblouků hlavní kružnice, která spojuje tyto dva body)

Země má tvar geoidu, což je těleso, které není definované
matematicky, ale fyzikálně. Jeho povrch je nepravidelná plocha. Proto
se geoid často nahrazuje rotačním elipsoidem nebo koulí.
– elipsoid s hlavní poloosou a a s vedlejší poloosou b, tento elipsoid je
zploštělý – zploštění i = (a-b)/a
– koule o poloměru R (poloměr náhradních koulí pro různé účely nemusí
být stejný, většinou platí 6370 km < R < 6380 km)
– reliéf tvoří cca 2 ‰
Na kulové ploše zavádíme zeměpisné souřadnice u a v – viz
obrázek. Souřadnici u nazýváme zeměpisná šířka a souřadnici v říkáme
zeměpisná délka.
severní pól

Greenwichský
poledník
u
v
rovník

jižní pól
Křivky na kulové ploše s konstantní zeměpisnou šířkou jsou
rovnoběžky a křivky s konstantní zeměpisnou délkou jsou poledníky.
Rovnoběžky spolu s poledníky vytvářejí zeměpisnou sítˇ.

Loxodroma
– křivka, která protíná všechny poledníky pod stejným úhlem – tato
křivka byla důležitá například v námořní plavbě
Příklad:
– rovnoběžka je obecně loxodroma, pouze rovník je současně loxodroma
i ortodroma

Kartografická zobrazení a projekce
Jedním z mnoha úkolů kartografie je tvorba map, neboli rovinných
kartografických obrazů zakřiveného zemského povrchu.
Uvažujme Zemi jako kouli. Je potřeba určit vztah mezi původním
bodem na kulové ploše a jeho obrazem v rovině mapy – kartografické
zobrazení. Matematickým vyjádřením kartografického zobrazení jsou
zobrazovací rovnice – vztah mezi souřadnicemi bodů v originále a v
obraze. Zobrazovací rovnice se odvozují z požadavků na zobrazení –
například chceme získat kuželové zobrazení v obecné poloze s jednou
nezkreslenou rovnoběžkou, které navíc nezkresluje úhly. Zobrazovací
rovnice potom získáme řešením diferenciálních rovnic.
Kartografická projekce je speciálním případem kartografického
zobrazení, kdy body na kulové ploše promítáme na jinou plochu (rovina,
válcová nebo kuželová plocha), můžeme nakreslit promítací paprsky a
zobrazovací rovnice odvodíme pomocí nich. V této kapitole se ale
budeme zabývat hlavně geometrickou konstrukcí obrazu zeměpisné sítě
v různých kartografických projekcích.

Deskriptivní geometrie 1

Základy kartografických projekcí 2

Kartografická zkreslení

(C) – rozdělení projekcí podle vzájemné polohy Země a plochy, na
kterou se promítá:
– pólová (normální) poloha – pokud splývá zemská osa s osou plochy
– rovníková (transverzální) poloha – pokud je zemská osa kolmá na
osu plochy
– obecná (horizontální) poloha – ostatní případy

O

T

PJ
T

τ

τ
O S

PS
O S
τ

PJ
τ

PS S
O

T

PJ
T

PJ

T

PS

PS

O

O

S
τ

PJ

pólová

PJ

T

O S

PJ
T

τ

τ

PS

T

s

O

PJ

PS

τ

PS
s

T

rovníková

S

PJ

obecná

Ortografická azimutální projekce v pólové poloze
τ

T
A

s.š

.

A

ρ

u

ε

R

T

j. š .

(B) – rozdělení projekcí podle toho, jak se promítá:
– pravoúhlá (ortografická) projekce
– středová projekce:
– gnómonická – promítá se ze středu koule
– stereografická – promítá se ze povrchu koule
Poznámka: stereografická projekce je konformní zobrazení

PS

s

O

Rozdělení kartografických projekcí
(A) – rozdělení projekcí podle toho, na co se promítá:
– azimutální projekce – promítá se na rovinu
– kuželové projekce – promítá se na kuželovou plochu
– válcové projekce – promítá se na válcovou plochu

τ

PS

stereografická gnómonická

Při zobrazování zakřiveného zemského povrchu do roviny mapy
dochází k určitému zkreslování jednotlivých veličin – délek, úhlů a
ploch. Neexistuje zobrazení, které by zachovávalo všechny tyto veličiny.
Podle toho, která veličina zůstane v rovině mapy nezkreslená, lze
zobrazení dělit na:
– ekvidistantní (délkojevná) – zobrazení, která nezkreslují délku
určitých křivek – například poledníků; nelze odvodit zobrazení, které
by zachovávalo délku všech křivek na kulové ploše
– ekvivalentní (plochojevná) – zobrazení zachovávající velikost ploch
– konformní (úhlojevná) – zobrazení, která zachovávají velikost úhlů
Ale existují i zobrazení, která nepatří do žádné z těchto tří skupin,
protože zkreslují délky, plochy i úhly.

ortografická

Azimutální projekce

s
ρ = R cosu
ε=v

τ

Deskriptivní geometrie 1

Základy kartografických projekcí 3

Ortografická azimutální projekce v rovníkové poloze
τ

60°

Gnómonická azimutální projekce v pólové poloze
PS

τ

30°
s .š .

T

30°

180°

45°
60°

120°
S

T
j.š.
ρ = R tg(90°-u)
ε=v

τ
60°z
.d

.
v.d

s

60°

.

30°

τ

0°

z.d
.

.
v.d

– v gnómonické azimutální projekci v pólové poloze se ortodroma
zobrazuje jako přímka, proto je tato projekce vhodná například pro
zakreslení průběhu ortodromy do jiné mapy

Stereografická azimutální projekce v pólové poloze
Ortografická azimutální projekce v obecné poloze
τ

PS

30°

60°

0°

τ
s

τ

T

0°

60°

120°

30°

T

0°

180°

S
ρ = 2R tg
ε=v

60°
90°-u
2
τ

z.d
.

0°

.
v.d

Deskriptivní geometrie 1

Základy kartografických projekcí 4

Gnómonická azimutální projekce v rovníkové poloze

Stereografická azimutální projekce v rovníkové poloze

– v této projekci jsou obrazem rovnoběžek hyperboly

– je možné ukázat, že v této projekci se rovnoběžky i poledníky zobrazují
jako kružnice (s výjimkou rovníku a poledníku procházejícího středem
projekce)
– jedná se o konformní zobrazení, a proto platí, že obrazy rovnoběžek
svírají s obrazy poledníků pravý úhel
S

0° 30°

60°

30°

S

0°

τ
τ

τ

τ

S

52,5°s.š.

rovník

S
Gr
ee

sk
ich
nw

.
°v.d

20

.
ýp

τ

τ

Deskriptivní geometrie 1

Základy kartografických projekcí 5

Válcové projekce

Kuželové projekce

Gnómonická válcová projekce v pólové poloze

Gnómonická kuželová projekce v pólové poloze

Y'

S

Y
S

X
X'

y 0°

60°

120°

180°

60°

S

30°
0°

R
S

60°

x

30°
0°
30°
0°

x = R arcv
y = R tgu

180°
60°

120°

