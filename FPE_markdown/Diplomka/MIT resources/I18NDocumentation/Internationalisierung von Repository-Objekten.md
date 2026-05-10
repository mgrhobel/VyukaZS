---
title: "Internationalisierung von Repository-Objekten.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/MIT resources/I18NDocumentation/Internationalisierung von Repository-Objekten.doc"
date: 2010-03-07
type: DOC
---

^(1)^[**?**]{.underline} [**Spezifikation**]{.underline}
[**Internationalisierung von Repository-Objekten**]{.underline}

+-----------------------------------------------------+---------------+
| \                                                   | **see also:** |
|                                                     |               |
| ^(2)^ Typ: RepoResourceBundleHolder                 | \             |
|                                                     |               |
| ^(3)^ Typ: ResourceBundleEntryKeyHolder             |               |
|                                                     |               |
| ^(4)^ Typ: SearchableResourceBundle                 |               |
|                                                     |               |
| ^(5)^ Typ: Klasse RepoResourceBundleImpl            |               |
|                                                     |               |
| ^(6)^ Spezifikation: Hilfsklassen zur               |               |
| Implementierung der Interfaces                      |               |
| RepoResourceBundleHolder bzw.                       |               |
| ResourceBundleEntryKeyHolder                        |               |
|                                                     |               |
| ^(7)^ Spezifikation: I18NEditMode fürs Editieren    |               |
| von internationalisierten Repoobjekten              |               |
|                                                     |               |
| ^(8)^ Spezifikation: automatisches                  |               |
| Mitspeichern/Mitlöschen von RepoResourceBundle mit  |               |
| RepoResourceBundleHolder ins Repository             |               |
|                                                     |               |
| ^(9)^ Spezifikation: Wichtige Spracheinstellungen   |               |
| für customizing internationalisierter RepoObjekte   |               |
|                                                     |               |
| **Beschreibung:**                                   |               |
+-----------------------------------------------------+---------------+

\

Der **Einsatz von MessageBundle-Dateien im Filesystem** führt **bei
Repository-Objekten** (z.B. Views) zu **folgenden Problemen**:

Views können für spezifische RepoOwner (z.B. Customer und Rolle)
unterschiedlich customized werden. Falls MessageBundle-Dateien
eingesetzt werden, müssten diese rollenspezifisch abgelegt und verteilt
werden. Weiters stellt das Bearbeiten der MessageBundle-Dateien (z.B.
vom GuiBuilder aus) an sich ein Problem dar.

\

**Lösungsansatz** daher:

**Editierbare ResourceBundle** werden als logische Objekte implementiert
und **im Repository** abgespeichert. Dadurch wird der \"normale\"
Reposuchpfad (user, rolle, usw.) verwendet. Einzelne Repo-Objekte pro
Sprachversion, d.h. für ResourceBundle aus Repository zu den Locales
\"de_AT\", \"de\" und RepoEmbeddableI18N.SYSTEMA_LOCALE existieren drei
ResourceBundle-Objekte im Repository.

Da es nicht sinnvoll zu kleine ResourceBundles ins Repository zu
schreiben, wird z.B. für eine View ein einziges ResourceBundle verwendet
und dessen enthaltene L3Controls (die Werte aus einem ResourceBundle
beziehen) verwenden alle dasselbe ResourceBundle der View.

\

Die Implementierung wurde mittels folgender Klassen bzw. Interfaces
durchgeführt (siehe Übersichtsdiagramm unten):

-   Interface **SearchableResourceBundle** (^(10)^): ResourceBundle
    dessen Werte abgefragt werden können.

-   Interface **EditableResourceBundle**(^(11)^): ResourceBundle dessen
    Werte verändert werden können.

-   Interface **RepoResourceBundle** (^(12)^): EditableResourceBundle,
    das im Repository gespeichert wird.

-   Klasse **RepoResourceBundleImpl** (^(13)^): Konkrete
    RepoResourceBundle-Implementierung.

-   Interface **RepoResourceBundleHolder** (^(14)^): Objekte (wie z.B.
    eine View), die der Besitzer eines RepoResourceBundle sind.

-   Interface **ResourceBundleEntryKeyHolder** (^(15)^): Objekte (wie
    z.B. L3Controls), die Einträge aus einem EditableResourceBundle
    lesen, bzw. in ein EditableResourceBundle schreiben.

![](Internationalisierung%20von%20Repository-Objekten_html_27a154dd.gif){#Image1
align="bottom" width="643" height="563" border="0"}

\

**konkreter Einsatz bei Views und L3Controls**

Darauf aufbauend implementieren L3Controls (L3Label etc.) das Interface
ResourceBundleEntryKeyHolder und die neu implementierte View-Klasse
UIRBPanel das Interface RepoResourceBundleHolder:

![](Internationalisierung%20von%20Repository-Objekten_html_9cd1cff8.gif){#Image2
align="bottom" width="631" height="272" border="0"}

\

**Hilfsklassen**

Da die Implementierung der Interfaces RepoResourceBundleHolder bzw.
ResourceBundleEntryKeyHolder nicht unerheblichen Implementierungsaufwand
darstellen, wurden Hilfsklassen implementiert, in die Details zur Arbeit
mit den ResourceBundles aus den Anwendungsklassen auslagern. Mehr Info
dazu in ^(16)^.

\

Beim Bearbeiten der ResourceBundleEntryKeyHolder wird das
RepoResourceBundle des RepoResourceBundleHolders verändert (z.B. im
obigen Anwendungsbeispiel beim Bearbeiten der L3Controls im GuiBuilder
wird das ResourceBundle des UIRBPanel verändert). Beim Schreiben des
RepoResourceBundleHolders (z.B. des UIRBPanel) ins Repository muss das
RepoResourceBundle ebenfalls in das Repository geschrieben werden. Ein
Automatismus dazu liefert der RepoObjectMgrSupport für
RepoResourceBundleHolder (siehe ^(17)^).

\

\

**Editierung von internationalisierten Repository-Objekten**

Fürs Editieren von bestehenden internationalisierten Repoobjekten (wie
z.B. Views per GuiBuilder) reicht es nicht nur jene ResourceBundles aus
dem Repo mitgeladen, die zur Spracheinstellung beim Laden aus dem Repo
passen. Grund: Änderungen z.B. in Views (entfernen von Controls,
kopieren von Controls in andere Views, etc.) wirken sich dann nicht auf
alle Sprachversionen aus.

Daher wird fürs Editieren mit anschließendem Schreiben ins Repo in einem
speziellen Editiermodus (i18nEditMode) gearbeitet, bei dem gleichzeitig
alle ResourceBundle-Sprachversionen zur Verfügung stehen. Nähere Details
siehe: ^(18)^

\

\

\

\

\

\

\
