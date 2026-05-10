---
title: "RS1p_2.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/ØS1/Pøednáky/RS1p_2.pdf"
date: 2008-08-24
type: PDF (text-based)
---

2 Teorie systémů
2.1 Systém a jeho definice
Systém – soubor určitého počtu navzájem souvisejících prvků, které jsou nějak vázány na své
okolí.
Definice:
•

systém je množina prvků, mezi nimiž existují určité funkční vztahy a který má jako
celek určitý vztah ke svému okolí.

tedy:

L = {S , R}
kde: S – množina prvků
R – množina relací mezi prvky, reprezentující vztahy mezi
prvky a vztahy k okolí

Jednotlivé části systému mohou být buď prvky nebo soubory prvků – subsystémy.
Příklad: automobil
•

Z hlediska mechanika je to systém složený ze součástí (prvků).

•

Z hlediska dispečera dopravy je to prvek.

Prvek:
•

Základní element systému, který považujeme na dané rozlišovací úrovni za dále
nedělitelný.

Struktura systému:
•

Vnitřní uspořádaní systému (jeho prvků a vazeb).

Okolím systému:
•

Rozumíme souhrn všech objektů a procesů, které svými vlastnostmi ovlivňují
zkoumaný systém, nebo jsou systémem ovlivňovány.

1

Chování systému:
•

Způsob jeho reakce na vnější podněty. Je obsaženo v relaci mezi vstupem a výstupem
systému.

2.2 Klasifikace systémů
Existuje řada hledisek. Zde uvedeme třídění z pohledu teorie systémů. Později uvedeme
třídění z pohledu teorie řízení
Fyzikální systém (objekt):
•

Soubor fyzikálních zařízení.

Abstraktní systém (matematický model):
•

Množina proměnných a relací mezi nimi.

---------------------------------------------------------------------------------------------Neorientovaný systém:
•

Nechť A je abstraktní systém, v1 , v 2 , …, v n je množina proměnných.

A1 ( v1 , v 2 , …, v n )
A2 ( v1 , v 2 , …, v n )

je množina relací mezi nimi.

M

An ( v1 , v 2 , …, vn )
Orientovaný systém:
•

Nechť A je abstraktní systém, v1 , v 2 , …, v n je množina proměnných, která je
rozdělena do dvou kategorií:
a) vstupní proměnné u1 , u 2 , …, u r (nezávisle proměnná)
b) výstupní proměnné y1 , y 2 , …, ys (závisle proměnná)

A1 ( u1 , u 2 , …, u r , y1 , y 2 , …, ys ) = 0
A2 ( u1 , u 2 , …, u r , y1 , y 2 , …, ys ) = 0

je množina relací mezi nimi.

M

An ( u1 , u 2 , …, u r , y1 , y 2 , …, ys ) = 0
---------------------------------------------------------------------------------------------Ke každému fyzikálnímu systému existuje jeho abstraktní systém (model). Naopak to neplatí.
Z hlediska fyzikální realizovatelnosti lze systémy dělit:
---------------------------------------------------------------------------------------------Kauzální systémy (nonanticipativní):

2

•

Jejich chování v přítomnosti závisí na hodnotách vstupů v minulosti a přítomnosti.
Respektují vztah příčiny a následku.

Nekauzální systémy (anticipativní):
•

Jejich chování v přítomnosti závisí na hodnotách vstupů v minulosti a přítomnosti a
budoucnosti. Jsou (zatím) fyzikálně nerealizovatelné.

Je tedy potřebné nějak oddělit historii systému od jeho budoucnosti. K tomuto účelu je
zaveden stav systému.
Stav systému:
•

Je veličina x (t) vyjadřující informaci o historii systému, která je nutná k tomu,
abychom na základě znalosti stavu x(t) a vstupu na intervalu (t, τ), tj. u(t, τ) mohli
určit výstup systému y(t, τ).

---------------------------------------------------------------------------------------------Deterministické systémy:
•

Chování v budoucnosti je jednoznačně určeno jejich počátečním stavem x (t) a
hodnotami vstupů u(t, τ).

Stochastické systémy:
•

Chování v budoucnosti není jednoznačně určeno jejich počátečním stavem x (t) a
hodnotami vstupů u(t, τ).

---------------------------------------------------------------------------------------------Dynamický systém:
•

Změny stavu reálných systémů jsou vždy spojené s výměnou energie, a proto nikdy
neprobíhají skokem, ale ke změnám stavu dochází postupně s časem.

•

Charakteristickou vlastností dynamických systémů je jejich setrvačnost. Okamžitý
stav a okamžitý výstup je závislý nejen na okamžitém vstupu, ale i na předcházejících
dějích probíhajících v systému (paměť).

3

