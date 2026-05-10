---
title: "Bereiche, die durch Internationalisierung.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/MIT resources/I18NDocumentation/Bereiche, die durch Internationalisierung.doc"
date: 2010-03-07
type: DOC
---

[**Analysis:**]{.underline} [**Bereiche, die durch Internationalisierung
geändert werden müssen**]{.underline}

+-----------------------------------+-----------------------------------+
| \                                 | \                                 |
|                                   |                                   |
|                                   | **see also:**                     |
|                                   |                                   |
|                                   | \                                 |
+-----------------------------------+-----------------------------------+

Is child document of: ^(1)^ Analyse: Internationalisierung von MPA

**Reference to requirement:**

**Description:**

In diesem Analysedokument sind jene Bereiche angeführt, die durch die
Internationalisierung geändert werden müssen. Zu den jeweiligen Teilen
werden in Folge Todos erstellt.

**Views (Controls)**

Aus dem GuiBuilder können folgende Controls in Views platziert werden,
und sind damit Ausgangspunkt für eine eventuelle Umwandlung in ein
L3Control zur Internationalisierung. Welche Controls davon betroffen
sind und Status von dessen Umwandlung siehe ToDo 2348 ^(2)^.Die
wichtigsten Controls sind umgestellt, Rest siehe dieser Link !

Titled Borders ^(3)^. - offen

\

~~CompoundTypeControl in RepoEmbeddable und RepoResourceBundleHolder
umwandeln. -\> ToDo~~ ~~^(4)^~~ g6: Nicht direkt i81n-Relevant

**Actions -\> Todo:**^**(5)**^ Vieles erledigt, siehe

-   Menüleiste ^(6)^ - erledigt

-   Popupmenü ^(7)^ (- \> Fixe Strings im Hautpmenu als
    Sub-Menu\"träger\" wird z.Zt in ein ResourceBundle-FILE gehalten. -
    \>vorläufig so lassen) - erledigt

-   Toolbar ^(8)^ - erledigt

-   NavigationBar^(9)^ - erledigt

-   Button^(10)^ - erledigt

\

Ausgangspunkt ist Action als Objekt. Dieses muss eindeutig
identifizierbar sein. Dazu kann es eine **ActionViewAttr** geben, die
Formatierungen für die Action enthält (z.B. angezeigter Text, Icon,
\...). **ActionViewAttr** kann als RepoResourceBundleHolder
implementiert werden und hat somit sein eigenes ResourceBundle.

Grafische Elemente sollten wie bei ColumnViewAttr auch von
ActionViewAttr erzeugt werden können, z.B. per Methode
createPopupMenuItem( ) der ActionViewAttr.

\

-   DefaultToolbar zu RepoResourceBundleHolder machen: ^(11)^ - offen

**ColumnViewAttr (I18N abgeschlossen)**

Definiert die Eigenschaften mit welchen Strings die logischen Columns
anzuzeigen sind. Controls werden mit internationalisierten Texte durch
diese Klasse erzeugt.

\

**CollectionViewAttr -\>Todo:** ^**(12)**^ - erledigt

Scheint nur eine Eigenschaft (description) zu sein, die
internationalisiert werden muss.

Muss deshalb CollectionViewAttr auf L3PropertyHolder umgebaut werden,
oder reicht Implementierung als RepoResourceBundleHolder und
ResourceBundleKeyHolder?

**EnumTypes -\> Todo:** ^**(13)**^  - erledigt

Nach erster Untersuchung gibt's zwei Werte, die internationisiert werden
müssen, auf die jeder EnumType mit folgenden Methoden abgefragt werden
kann:

public String getLangValueFor(Value P_value);

public String getLangDescFor(Value P_value);

Die Implementierungen müssen dabei auf ein RepoResourceBundle gehen.

**Hardcoded-Strings in ResourceBundles -\> Todo:** ^**(14)**^  -
erledigt**, Folgetodo für Gruppen:** ^**(15)**^  - erledigt

-   Text, der irgendwann in Dialogen etc. in der Benutzerschnittstelle
    angezeigt wird, bzw. auf Konsole ausgegeben wird (ausgenommen
    Logging-Meldungen)

-   Fehlermeldungen

-   Aufwand \~ 1-2 Arbeitswochen

\

**Trees bzw. TreeNodes -\> Todo 4142** ^**(16)**^  - erledigt

-   für gf.tree.IndirectTreeNode ist in gf.tree.UDITreeRenderer ein
    MpaResourceBundle-Mechanismus implementiert.

-   gf.tree.SimpleTreeNode zeigt dzt. einfach nur den Namen seines
    MetaTreeNode an

-   in Anforderungs-Browser und Dokument-Browser SimpleMetaRecords
    \"StringField\" verwendet, um einen UDI-selektierbaren Knoten zu
    erhalten. Ideen für I18N:

\- in Projektion \"StringField\" spezielle Projektions-Column, die mit
dem Wert im Record einen MpaResourceBundle-Lookup durchführt

\- Erweiterung von \"StringField\" um Felder für I18NKey und
internationalisierten Text, Implementierung einer entsprechenden get()
-Methode auf der typ. Klasse

\

**Sonstiges**

-   Automatisches Mitspeichern von ResourceBundles -\> Implementierung
    abgeschlossen

-   ~~ForeignKeyViews als RepoEmbeddable und RepoResourceBundleHolder
    inkl. Transformation -\> Todo:~~ ~~^(17)^~~

-   ~~Ev. Änderung an Connections nötig (da Connection von Haupt-View in
    Embedded-View bzw. umgekehrt möglich ist) -\> im Rahmen von Todo:~~
    ~~^(18)^~~

-   ~~Im GuiBuilder wird foreignKeyView nur mehr eingebettet und kann
    nicht mehr bearbeitet werden -\> Todo:~~ ~~^(19)^~~nicht 18n
    relevant.

-   Reihenfolge der Verzeichnisse in RepoImport garantieren -\> Todo:
    ^(20)^ - erledigt

-   Editoren für L3Property (Todo: ^(21)^- erledigt), RepoResourceBundle
    (Todo: ^(22)^- erledigt)

-   Sprach-/Userwechsel während Programmausführung, reagieren auf
    LocaleChangeEvent -\> Todo: ^(23)^ - offen, nicht so wichtig

-   Ev. ist es nötig Icons zu internationalisieren (z.B. die Icons auf
    Labels bzw. Buttons). Prinzipiell sollten die ResourceBundles aus
    dem Repo mit beliebigen Objekten somit auch mit Icons funktionieren.

-   Aufteilung der bisher bestehenden ResourceBundles auf
    Applikationsbereiche \--\> Todo: ^(24)^ - offen, nicht so wichtig

-   g6: 4.7.03: Feiertage: ^(25)^ - erledigt

-   pepi: 7.8.03: String-Vergleiche, Sortierung: Todo 4189 ^(26)^ offen

-   gf.dict.types.Type.description ^(27)^ offen: nicht so wichtig

-   Functions: Description sollte aus MessageBundle kommen: ^(28)^ -
    erledigt

-   DefaultSettings: Default-Buttons etc. werden noch hardcoded erzeugt.
    ^(29)^ - erledigt

-   Editieren/Konvertieren von MessageBundles ^(30)^ offen

-   Im GuiBuilder nicht nur technische Namen sondern auch (optional)
    übersetzte Werte anzeigen ^(31)^ offen

-   UIOptionPane I18N-fähig machen ^(32)^ - erledigt

-   RepoExport für spezielle Locale ^(33)^ - erledigt

-   lokalisierte Anzeige von LO LC (z.B. in ExpressionEditor): ^(34)^ -
    erledigt

-   Kontrolle aller einzelnen Bereiche ^(35)^ offen

\

\
\

\

\
