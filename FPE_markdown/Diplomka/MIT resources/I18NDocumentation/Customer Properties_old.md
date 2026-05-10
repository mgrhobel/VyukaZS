---
title: "Customer Properties_old.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/MIT resources/I18NDocumentation/Customer Properties_old.doc"
date: 2010-03-07
type: DOC
---

^(1)^[**?**]{.underline} [**Administrator Guide -
Overview:**]{.underline} [**Customer Properties_old**]{.underline}

**Description:**

Alle Einstellungen und Steuerungen, die über Einträge im File
\"customer.properties\" bzw. \"client.properties\" gesetzt werden
können.

\

Diese Dateien werden am Verzeichnis \"**customer**\", welches per
CLASSPATH gesucht wird (z.B. \'d:\\head\\java\\customer\' - CLASSPATH
enthält \'d:\\head\\java\'), gelesen.

\

Enthält die Datei \'**switch.properties**\' im
\"**customer**\"-Verzeichnis einen gültigen Property-Eintrag
\'**customer=\...**\' (z.B. customer=testKISE), so wird in diesem
Unterverzeichnis (z.B. testKISE) nach den oben genannten Dateien
gesucht.

\

**Suchreihenfolge:**

-   CLASSPATH/customer/\<customer\>/customer.properties

-   CLASSPATH/customer/customer.properties (nur wenn die vorherige Datei
    nicht gefunden wurde)

-   CLASSPATH/customer/\<customer\>/client.properties

\
\

Es werden alle Einstellungen von diesen Dateien eingelesen, wobei die
weiter unten genannten Dateien die Einstellungen der vorherigen Dateien
übersteuern, d.h. \'client.properties\' übersteuert alle vorherigen
Dateien.

Hinsichtlich dem Parameter \'\<customer\>\' sind die vorherigen Absätze
zu beachten.

\
\

**Allgemeine Anmerkungen:**

-   Hier sollten AUCH Umgebungsvariablen beschrieben werden, die mit
    Environment.autoset gesetzt werden.

-   Es wird bei allen Einträgen die Groß- und Kleinschreibung beachtet.

-   Falls sich ein Eintrag (Property-Wert) über mehrere Zeilen
    erstrecken soll, so muss das Zeilenende mit einem Backslash markiert
    werden. Bsp:

repo2.CacheInitializer.directories = \\

gf.dict.LogObject, \\

gf.dict.LogPhysMap.ToLogMapper,\\

gf.dict.LogPhysMap.ToPhysMapper,\\

gf.dict.LogPhysMap.SurrogatElem,\\

gf.dict.LogPhysMap.HauptPhysTable,\\

gf.omgr.ObjectMgr,\\

\

Siehe auch: Verwendung von Variablen in Properties: ^(2)^

\

See also: Files in the customer-directory: ^(3)^

**Details:**

D.h. der COMMPROXY_TIMEOUT - Wert wird nur dann verwendet wenn dieser
den Wert den der Programmierer vorgegeben hat übersteigt,

Beispiel:

Lt. Applikation 60 Sekunden

COMMPROXY_TIMEOUT=15000

Wert lt. Applkation wird verwendet

\

Beispiel: COMMPROXY_TIMEOUT=15000

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**WAIT_FOR_APPLICATION_TO_END (at least since rel_3.4, file property,
ACT_BASE)**

#Initialize.terminate muss die Applikation innerhalb der eingegebenen
Zeit (ms) beenden sonst kommt es

#zu Runtime.getRuntime().halt

#Default Wert ist 15000 ms

#WAIT_FOR_APPLICATION_TO_END=0 - keine Beendung durch halt()

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\

\-\-\-\--**TRANSACTION
SERVICE**\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**FORBIDDEN_MULTITHREADING_HANDLING_VIA_SEMAPHOR** **(since rel_3.8.3,
file property)**

boolean property with default value = false

Defines if multithreaded access in TransactionManager is permitted. This
was introduced because of several multithreading problems with
AccessBridge.

This property should only be enabled if assistive technologies are used
(e.g. COBRA)

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**TRANSACTION_DURATION_WARN_THRESHOLD** **(**ab 3.4.3 Change ^(4)^,
rel_3.6, **NICHT** 3.5.X**, file property, ACT_BASE)**

Nur TopLevelTransaktionen, welche die Dauer, der von dem Property
angegebenen Schwellwert übersteigen,

werden protokolliert.

Zum Beispiel:

TRANSACTION_DURATION_WARN_THRESHOLD=10000

Nur Top-Transaktionen mit Zeiten großer als 10 Sekunden werden
protokolliert.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**SQLSTATEMENT_DURATION_WARN_THRESHOLD** **(**ab 3.4.3 Change ^(5)^,
rel_3.6, **NICHT** 3.5.X**, file property, ACT_BASE)**

Nur Statement welche Dauer der Schwellwert übersteigen werden
protokolliert.

Zum Beispiel:

SQLSTATEMENT_DURATION_WARN_THRESHOLD=1000

Nur Statements mit Ausführungsdauer größer als 1 Sekunde werden
protokolliert

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**COMMPROXY_DURATION_WARN_THRESHOLD** **(**ab 3.4.3 Change ^(6)^,
rel_3.6, **NICHT** 3.5.X**, file property, ACT_BASE)**

Nur RMI-Method AUfrufen ausgehend von CommunicationProxy welche Dauer
der

Schwellwert übersteigt werden protokolliert.

Zum Beispiel:

COMMPROXY_DURATION_WARN_THRESHOLD=1000

Nur RMI-Aufrufe mit Dauer gößer als 1 Sekunde werden protokolliert.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**MAX_TRANSACTION_DURATION (since \<= rel_3.4, file property,
ACT_BASE)**

Timeout fuer offene DB-Transaktionen in Sekunden

Alle Transaktionen die länger als das gesetzte TIMEOUT dauern, beenden
die Applikation.

Beispiel:MAX_TRANSACTION_DURATION=30

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

~~(Release 2.2.12 Build größer 63 only):~~
~~**TransactionManager.ignoreOpenTransaction**~~

~~Wenn dieser Wert NICHT gesetzt ist (DEFAULT), dann wird in bestimmten
Fehlersituationen beim Auftreten einer offenen Datenbanktransaktion ein
Rollback derselben gemacht und das Programm mit einer Exception
unterbrochen.~~

~~Diese Property kann in Notfällen auf einen beliebigen Wert != \"\"
gesetzt werden, wenn dies in einer best. Situation nicht gewünscht ist
(Todo:~~ ~~^(7)^)~~

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\

\-\--**-DEFAULT-SETTINGS**\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**WinWordVersion** **(since rel_2.x, file property, DOC/Kamleithner)**

Default 97

Legt fest, welche Wordversion vom User verwendet wird. Möglich sind die
Werte \"97\" und \"2000\". Verwendet wird diese Property beim Speichern
von contextsensitive Hilfe im GuiBuilder.

zB.: WinWordVersion=2000

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**SCT_VERSION** **(at least since rel_3.4, file property, MPA_KIS)**

verwendete Native-Bibliotheken für KIS-Version (Default56)

ab MPA Version 2.0

Beispiel:

SCT_VERSION=57

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**SctRuntime.isSctInstalled** **(since rel_3.10, file property, Erich)**

Default: false

This property tell\'s if native methods from SCT are allowed to call.

It is additional to the property SCT_VERSION.

It should ensure, that native DLL are not used for Vendors like SAP,
NOVACOM and KISMPA.

Necessary for the x64 project.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**ORION.StartFile.cmdLine** **(at least since rel_3.4, file property,
ACT_BASE/MPA_KIS)**

Commandline-Befehl zum Starten des SCT-Orion-Programmes

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**client.properties**

**Verifikation Krankenhaus**

Prüft beim Laden der ptreadxx.dll die khs_kh_bez mit dem Eintrag im
customer.properties

Environment.autoset.defaultKH=431

Environment.autoset.KH_BEZ_VERIFY=Test KHSR srphtest

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\

\-\--**- LANGUAGE
SETTINGS**\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**org.vendor (ab rel_3.8, see also:** ^**(8)**^**, file property,
ACT_BASE)**

Definitiert welcher Vendor im Einsatz ist.

Durch Änderung des Werts kann nicht zwischen Vendoren gewechselt werden!
Wird für einige Applikationen (z.B. CreateStandardDSEnv) benötigt.

Folgende Werte sind gültig: SYSTEMA, SAP, NOVACOM, KISMPA,G3

Beispiel:

org.vendor=SYSTEMA

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**org.vendor.sapLand (ab rel_3.8, file property, ACT_BASE)**

Falls als org.vendor SAP als Wert hinterlegt ist, wird zusätzlich noch
eine Landangabe benötigt.

Gültige Werte sind z.B.: AT, DE

**Falls** der **Vendor nicht SAP** ist, so muss **org.vendor.sapLand
auskommentiert** werden!

Beispiel:

org.vendor.sapLand=AT

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**kue.vendor** **(since rel_3.8.3, file property)**

default=SYSTEMA

If kue.vendor=SAP, MPA kitchen with SAP kitchen as \"data delivery
system\" will be used, otherwise usual SYSTEMA kitchen will be the data
delivery system.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**gf.i18n.markStrings** **(rel_3.5, file property, ACT_BASE)**

(default: false), seit rel_3.5 ^(9)^

Wenn auf true, dann werden Strings, die aus ResourceBundle-FILES gelesen
werden mit einem \"+\" vorne markiert, und Strings, die FALSCHERWEISE
NICHT in einem Resourcebundle gefunden werden, mit \"@2 markiert.

Dies gilt z.Zt NICHT für Strings, die aus RepoResourceBundles kommen

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

~~**runInI18NDemoMode**~~ ~~(ab rel_3.4) bestimmt ob Repo-Objekte in
einer anderen als Sprache RepoEmbeddableI18N.SYSTEMA_L~~

~~OCALE (Locale \"none\") gespeichert werden dürfen.~~ ~~**true**~~
~~falls es erlaubt ist in anderen Sprachen Repo-Objekte zu speichern,~~
~~**false (default)**~~ ~~falls nur für
RepoEmbeddableI18N.SYSTEMA_LOCALE gespeichert werden darf.~~
~~**true**~~ ~~ist~~ ~~**nur für Test- bzw. Demoinstallationen
zugelassen**.~~

~~Beispiel:~~

~~RunInI18NDemoMode=false~~ **\--\> Property obsolet ab 3.5 (alex1)**

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\

\-\--**-** ORB
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**orb.SocketCreateTimeout=1000** **(since 3.8, file property,
GF/Jachs)**

Timeout in milliseconds for RMI socket creation (connect). Default
value: 0 (= infinity).

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**orb.SocketCreationThreshold (since 3.9) with Change 187472**

#Purpose is to set a Threshold value for logging. If connection creation
takes longer than the defined Threshold value a message is printed.

#If Threshold is not defined or greater than the creation timeout value
defined by orb.SocketCreateTimeout than the threshold is ignored (only a
warning will be printed).

#Scale unit is milliseconds.

#Value must be \>0, for disabling comment out

orb.SocketCreationThreshold=5000

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**orb.SocketFactory.serverPortRangeFrom,
orb.SocketFactory.serverPortRangeTo** (ab 3.4.3, Change ^(10)^, rel_3.6,
**NICHT** 3.5,X**, file property, ACT_BASE**)

Gibt einen Bereich von Portnummern an, in dem MPA seine Port-Adressen
für Serversockets verwendet. der \*To Wert sollte größer oder gleich dem
\*From Wert sein. Wenn \*From nicht gesetzt ist oder null, dann wird der
normale Mechanismus zur Portnummer-Ermittlung verwendet.d.h. es wird
irgendein freier Port verwendet.

Diese Property kann auf Systemen mit Firewalls verwendet werden. (Vgl
Todo: ^(11)^)

**orb.SocketFactory.serverPortRangeFrom**

**orb.SocketFactory.serverPortRangeTo**

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**orb.ServicePingInterval (at least since rel_3.4, file property,
ACT_BASE)**

**// former: wfl.ServerPingInterval**

Thread am Workflow Client, der periodisch Verfügbarkeit des Servers
prüft (in millis)

none/no/No oder remarked =\> kein Thread

5 Minuten Intervall

Beispiel:

orb.ServicePingInterval= 300000

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**(orb.ServiceListener.SocketReadTimeout) (at least since rel_3.4, file
property, ACT_BASE)**

**orb.SocketReadTimeout(lucky:30.09.2004) -\> alle RMI Sockets (at least
since rel_3.4, file property, ACT_BASE)**

**// former: wfl.WFLListener.SocketReadTimeout**

SocketReadTimeout-Werte geben die Zeit an, die eine Verbindung MAXIMAL
gehalten wird.

Angabe in milli-Sekunden. In der Praxis dauert es immer 2 x die
angegebene Zeit, bis

die Verbindung tatsächlich unterbrochen wird.

Bsp: 10000 =\> nach 20 Sekunden wird Verbindung unterbrochen

Spezielle Werte für sog. SerivceListener (z.B. Workflow, Hl7, usw.)

Seit rel_3.8 wird dieser Wert von PatRead auch dafür verwendet um
festzustellen ob ein native-call abgebrochen werden soll oder nicht.
Überschreitet die Ausführungszeit eines native-calls diesen Wert wird
PatRead beendet und neu gestartet.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**orb.ServiceListener.SocketBlockOnClose (at least since rel_3.4, file
property, ACT_BASE)**

**orb.SocketBlockOnClose(lucky:30.09.2004)-\> alle RMI Sockets (at least
since rel_3.4, file property, ACT_BASE)**

**// former: wfl.WFLListener.SocketBlockOnClose**

Angabe in Sekunden.

Gibt an, ob die close Methode am Socket X Sekunden lang blockieren soll,
bis alle ausstehenden Daten gesendet und vom Empfänger entgegengenommen
sind.

Wenn auf 0 gesetzt, wird die Verbindung unmittelbar geschlossen.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**orb.ServiceListener.SocketTcpDelay (at least since rel_3.4, file
property, ACT_BASE)**

**orb.SocketTcpDelay(lucky:30.09.2004)-\> alle RMI Sockets (at least
since rel_3.4, file property, ACT_BASE)**

**// former: wfl.WFLListener.SocketTcpDelay**

gibt an, ob Daten gepuffert werden, bis ein Bestätigung für alle bereits
gesendeten Daten vorliegt

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**(SystemProperty, MPA_DOC/Schachinger, seit ca. rel_3.0 obsolet)**

**org.omg.CORBA.ORBClass** bisher immer com.ooc.CORBA.ORB

**org.omg.CORBA.ORBSingletonClass** com.ooc.CORBA.ORBSingleton

**ooc.config** c:/winnt/ob.cfg

Properties zur Initialisierung einer Orb-Instance

Werden bisher nur in SERInitializeHelper verwendet

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**orb.NetworkInterfacePattern,** **(at least since 3.4, file property,
ACT_BASE)**

**orb.NetworkAddressPattern**

(Change: ^(12)^) Nur dann auf Werte != null, wenn ein Rechner mehrere
IP-Adressen besitzt und die Anwendung deswegen beim Start eine Warnung
ausgibt.

Details dazu siehe in der Change.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**gf.orb.ServiceVersion** **(rel_3.2, file property, ACT_BASE)**

(Ab Version 3.2)

Default: 0, Typ=Integer

) Nur dann auf Werte != null, wenn ein Rechner mehrere IP-Adressen
besitzt und die Anwendung deswegen beim Start eine Warnung ausgibt.

Details dazu siehe in der Change.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**gf.orb.ServiceVersion** **(rel_3.2, file property, ACT_BASE)**

(Ab Version 3.2)

Default: 0, Typ=Integer

Wird von RMIRegistry gehalten. Clients fragen diese Nummer periodisch
(gf.orb.ServiceVersionCheckInterval) ab. Wenn sich diese Nummer ändert,
beendet die Anwendung (erfüllt Requirement: ^(13)^, Dokumentation:
^(14)^)

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**orb.VersionCheck** **(at least since rel_3.4, file property,
ACT_BASE)**

Versionskontrolle Server - Client: default Eingeschalten! true oder
false

Beispiel:

orb.VersionCheck = false

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**gf.orb.ServiceVersionCheckInterval** **(rel_3.2, file property,
ACT_BASE)**

(Ab Version 3.2)

Default: 60, Typ Integer (Wert in Sekunden)

Gibt an, in welchen Abständen Anwendungen die gf.orb.ServiceVersion
Nummer der RMIRegistry überprüfen.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\-\--**-** WORKFLOW
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\

**wfl.JMSListener_Reconnect** **(since rel_3.8.3, file property)**

(default=true)

With this property the reconnect of a client triggered by JBoss WFL can
be disabled. If the workflow events can not be sended due to
InvalidDestinationException normally JBossWFL tries to inform the Client
application that he should trigger a reconnect. This information is done
via RMI.

If the property wfl.JMSListener_Reconnect is set to false no client
information is performed and the client must recognize on his own that
he has to reconnect.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**wfl.ProzessProgramm.asynchronous** **(since 3.8, file property,
WFL/Haugeneder)**

\# This property determines if you are allowed to start and extend

\# a processprogram asynchronous or not, if the property is true

\# it will be checked if you are allowed to start it asynchronous
otherwise

\# it will never be done asynchronous

wfl.ProzessProgramm.asnychronous=true

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**Automatische Symbolvergabe**

\

**wfl.expr.Symbol.Aufenthalt.useTermin** **(WFL, APP/Bimminger) - ab
rel_3.6.b, für RepoInit relevant -\> Keine PropertiesKlasse**

Legt fest, ob bei der Expression zur automatischen Symbolvergabe der
Termin verwendet werden kann. [Nach dem Ändern dieses Properties ist ein
RepoInit erforderlich]{.underline}, da erst danach die entsprechenden
Expressions im RepoBrowser editiert werden können. Nähere Informationen
siehe ^(15)^

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**cb.MetaProzessVersionsToDisplay** **(ab 3.6.b, fileProperty, MPA_WFL,
Trummer)**

Gibt an, wieviele der LETZTEN Versionen eines MetaProzess zu sehen sind.
Sind bei diesen Versionen die aktive bzw. test-aktive Version noch NICHT
inkludiert, werden diese zusätzlich angezeigt! Wird bei dieses Property
nicht verwendet, werden alle Prozess-Versionen angezeigt.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\# Parameter ob automatisch die aktuelle Version eines MetaProzesses zum
Starten von Terminen,.. hergenommen wird

\# start current version of MetaProzess automatically (Default)

**wfl.app.startCurrentVersionOfMetaProzess=0** **(ab 3.6, file property,
MPA_WFL)**

\# ask User to start current version of MetaProzess

**#wfl.app.startCurrentVersionOfMetaProzess=1**

\# always start planed (old) version of MetaProzess

**#wfl.app.startCurrentVersionOfMetaProzess=2**

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**WAIT_FOR_SUBSYSTEM_TO_END** **(since rel_3.6, file property,
ACT_BASE)**

\# Wie lange wird gewartet fuer die Beendigung des Subsystems

\# Default:10000 ms

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**ASYEXECUTION_THREADPOOL_SIZE (at least since rel_3.4, file property,
ACT_BASE)**

\# Asynchrone Verarbeitung - Anzahl der WorkerThread(ThreadPool
Verarbeitung)

Beispiel:

#Die Asynchrone Verarbeitung wird durch 20 Worker Threads durchgeführt.

ASYEXECUTION_THREADPOOL_SIZE=20

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**ASYEXECUTION_THREADPOOL_TIMEOUT (since rel_3.8, file property,
ACT_BASE)**

Timeout of the ThreadPool used for asynchron execution (in Seconds).

If the timeout gets reached while waiting for an idle thread the
ThreadPool will start up to \<*ASYEXECUTION_THREADPOOL_SIZE*\>
additional threads.

ASYEXECUTION_THREADPOOL_TIMEOUT=300

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**#BlockOnAE@at.co.systema.wfl.svr.NotifySupport\$BackgroundNotification=true**
**(ab 3.4.3, file property, MPA_WFL)**

Aktivierung/Deaktivierung der **asynchronen Verteilung** der Nachrichten
der WorkflowEngine:

Wenn auskommentiert, dann ist die ASYNCHRONE Verteilung AKTIVIERT.

In jedem anderen Fall ist die SYNCHRONE Verteilung AKTIVIERT!

Auch via
BlockOnAE@at.co.systema.wfl.svr.NotifySupport\$BackgroundNotification=false
!!!!!!!!!!!!!

Default: auskommentiert und damit AKTIVIERT

Basiert auf dem allgemeinen Mechanismus: **\"Steuerung fuer
Blocking/Nonblocking Method-Calls durch Property\".** Siehe ^(16)^

Beispiele:

#BlockOnAE@at.co.systema.wfl.svr.NotifySupport\$BackgroundNotification=true

=\> asynchrone Verteilung

BlockOnAE@at.co.systema.wfl.svr.NotifySupport\$BackgroundNotification=true

=\> synchrone Verteilung

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**(at least since rel_3.4, file properties, ACT_BASE)**

#Steuerung fuer Blocking/Nonblocking Method-Calls durch Property.

\# Property fuer Blocking sollte so definiert werden:

\# \[PREFIX\] + Classname

Beispiel:

**BlockOnAE@**at.co.systema.gf.util.tests.TestAsyExecThreadPool=true

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**ASYEXECUTION_BLOCKCALLS**=true **(at least since rel_3.4, file
property, ACT_BASE)**

Schaltet die asynchrone Verarbeitung aus. Gilt nur für die Klassen
welche asynchrone Verarbeitung mittels

gf.util.AsynchronExecution implementiern.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**wfl.templatePaths** **(ab 3.6.B file property, MPA_WFL, Trummer)**

Dieses Propertie definiert eine Liste, in der die Pfade festgelegt
werden, wo Jython-Skript Vorlagen zu finden sind. Diese können dann im
Jython-Skript Editor im \"template\" Panel ausgewählt werden.

z.B.: wfl.script.vorlage

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**wfl.scriptPaths** **(ab 3.6.B file property, MPA_WFL, Trummer)**

Dieses Propertie definiert eine Liste, in der die Pfade festgelegt
werden, wo gespeicherte Jython-Skripts zu finden sind. Diese können im
Jython-Skript Editor mittels \"öffnen-Dialog\" augewählt werden.

z.B.: wfl.script

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

~~**wfl.suspendProcesses (ab rel_3.8)**~~ ~~**obsolet ab .38**~~

~~gibt an nach wievielen Stunden ein Prozess geparkt werden soll (siehe
Todo 16396~~ ~~^(17)^~~ ~~)~~

~~Beispiel:~~

~~wfl.SuspendProcesses= 24 =\> Prozess wird nach 24 Stunden geparkt~~

~~wenn dieses Property nicht gesetzt ist bzw. auf 0 gesetzt ist, werden
Prozesse nicht geparkt~~

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

~~**wfl.startSuspend (ab rel_3.8)**~~ ~~**(liegt ab rel_3.8 im
Repository CommonWFLProperties, WFL/Trummer)**~~ ~~**Property ist ab 3.8
obsolet**~~

~~gibt an, wann das Parken der Prozesse durchgeführt werden soll (siehe
Todo 16396^(18)^~~ ~~)~~

~~Beispiel:~~

~~wfl.startSuspend=22 =\> Prozesse werden um 22 Uhr geparkt~~

~~Anmerkung: das parken der Prozesse sollte immer in der Nacht erfolgen,
da durch das Parken der Prozesse die WorkflowEngine stark belastet
wird~~

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**wfl.enableServerCFT (**ab 3.4.3 Change ^(19)^ , rel_3.6, **NICHT**
3.5.X**), file property, MPA_WFL,** **ab 3.8 obsolet**

Steuert die Ausfürung der CFTs mit Bearbeitungsmodus WorkflowEngine. Mit
false wird die Service-Ausfuehrung ausgeschaltet

Defaultwert ist true.

wfl.enableServerCFT=false

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**wfl.MetaProzessListForCFTServer (**ab 3.4.3 Change ^(20)^, rel_3.6,
**NICHT** 3.5.X**)** **file property, MPA_WFL,** **ab 3.8 obsolet**

Steuert die Ausfürung der CFTs mit Bearbeitungsmodus WorkflowEngine. Nur
für die MetaProzessen von

dieser Liste werden die CFTs auf einen CFT-Server ausgeführt.

Beispiel:

wfl.MetaProzessListForCFTServer=\\

QS_ROE,\\

QS_UNT,\\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

~~**wfl.EnableSmallAufenthalt (ab rel_3.6)**~~ ~~**(entfernt mit
rel_3.8)**~~

~~Steuert die Verwendung von kleinem Aufenthalt (Small Aufenthalt).
Dadurch wird WorkflowEngine~~

~~nicht mit unnötigen Daten belastet. Defaultwert ist TRUE.~~

~~Verwendung:wfl.EnableSmallAufenthalt=false~~

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

~~**wfl.NotifyClientsForMetaProcessChange**~~ ~~**(wurde mit rel_3.8
entfernt)**~~

~~Property für die Steuerung der Verteilung von MetaProzessaenderungen
zu den Clients.~~

~~Bei Default werden die Clients über Metaprozessaenderungen nicht
informiert.~~

~~Die Metaprozessaenderungen werden trotzdem dei dem naechsten
Prozessstart beruecksichtigt.~~

~~Metaprozessaenderungen zu den Clients verteilen:~~

~~wfl.NotifyClientsForMetaProcessChange=true~~

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

~~**gf.actx.visio.VisioSavePath**~~

~~Gibt den Ordner an, in dem die Visio-Prozess-Zeichnungen gespeichert
werden sollen.~~

~~Beispiel:
gf.actx.visio.VisioSavePath=c:\\\\mpa\\\\head\\\\lib\\\\vsd\\\\~~

Wird nicht mehr gebraucht, weil Visio-Zeichnung mittels FileSystemAblage
gespeichert wird. Der Pfad kann also nur mehr im
doc.DeploymentInitializer geändert werden!

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

~~**WorkflowDispatcher**~~ ~~**ab 3.8 obsolet**~~

~~**wfl.dispatch.WorkflowEngineCount**~~

~~Gibt die Anzahl der zu startenden WorkflowEngine Instanzen an. Muss
gesetzt sein, kein DefaultWert!~~

~~Bsp.: wfl.dispatch.WorkflowEngineCount=2~~

~~**wfl.dispatch.WorklfowEngineStartCmd**~~

~~Cmd String zum Starten der einzelnen WorkflowEngine Instanzen an. Muss
gesetzt sein, kein DefaultWert!~~

~~Bsp.: wfl.dispatch.WorklfowEngineStartCmd=jstart
at.co.systema.wfl.svr.WorkflowEngine -norestore -user username
username~~

~~**wfl.dispatch.TestIntervalForWorkflowEngineInstances**~~

~~Intervall in dem der WorkflowEngineDispatcher seine laufenden
WorkflowEngine Instanzen überprüft.~~

~~Wert in Sekunden. Default: 30 (sec)~~

~~Bsp.: wfl.dispatch.TestIntervalForWorkflowEngineInstances=30~~

Für Details siehe auch ^(21)^

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

~~**wfl.checkTodos**~~ ~~**(entfernt mit rel_3.8)**~~

~~Wie oft sollen Todos die den Status \"in Bearbeitung\" haben überprüft
werden, ob sie noch~~

~~einen gültigen Client(der das Todo bearbeitet) haben. Wenn sie keinen
mehr haben, werden sie~~

~~auf zu erledigen zurückgesetzt. Angabe im Minuten.~~

~~Beispiel:~~

~~wfl.checkTodos=10 d.h. es werden alle 10 Min. alle Todos die in
Bearbeitung sind überprüft.~~

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

~~**wfl.startAppointmentsAsynchron**~~ ~~**(entfernt mit rel_3.8)**~~

~~legt fest, ob Termine asynchron gestartet werden sollen~~

~~**wfl.startAppointmentsAsynchron=true (=default)**~~

~~asynchrones Starten von Terminen~~

~~**wfl.startAppointmentsAsynchron=false**~~

~~synchrones Starten von Terminen~~

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

~~**wfl.useUnsynchronizedNotification**~~ ~~**(mit rel_3.8 entfernt)**~~

~~Damit lässt sich die Verteilung auf der WorkflowEngine wie folgt
beeinflussen:~~

~~**wfl.useUnsynchronizedNotification=false (Default):**~~

~~Bei der Verteilung werden die sog. Evaluierungsobjekte nicht geklont
und mittels DBMonitor synchronisiert (ev. langsam)~~

~~**wfl.useUnsynchronizedNotification=true**~~

~~Hierbei werden die sog. Evaluierungsobjekte vor der Verteilung geklont
und es sollte dann nicht mehr notig sein, dies mittels DBMonitor zu
synchr.~~

~~(ev. etwas schneller bei vielen gleichzeitigen Clientzugriffen)~~

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\-\--**-** DOKUMENT/ORDER
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**doc.mpaDotName** **(since rel_3.8.X, file property)**

This property can be used to use another mpa.dot within lib-folder than
the origin.

Path mustn\'t be inserted only the name of the updated mpa.dot (e.g:
mpaExtra.dot). This updated \*.dot-File must be also within lib-folder.

[Aim of this property:]{.underline}

\- if there are problems with the origin mpa.dot =\> an updated mpa.dot
can be used without needing all user the close MPA

\- some user can work with a specific mpa.dot =\> this is very helpfull
for error-finding

[defautlValue]{.underline}: not set =\> origin mpa.dot will be used

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**DOCIMPORT_MAXRETRY** **(since rel_3.8.3, file property)**

default value = 5

if the word application is busy during the first atempt to import then
the system

automaticaly retries to import a specifified number of times

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**DOCIMPORT_RETRY_WAIT** **(since rel_3.8.3, file property)**

default value = 5000

between each atempt to retry the system will wait for a specified
ammount of msec.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**DOCIMPORT_RETRY_CONDITION** **(since rel_3.8.3, file property)**

default value = 8001010a,busy,80010001

to determin if the failure / exception was generated by a \"busy\"
situation her can be

specified different contents in the exception message. the system will
search for one

of them, and if found, it will start the retry loop.

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**SCANNER_FORCE_FEEDER** **(since rel_3.8.3, file property)**

Boolean value used to tell the system to ignore the autodetect
functionality for the feeder of an connected scanner. (Bug in HP twain
driver).

DefaultValue = False

If set to True the multipage scanning capability is always active.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**Word.suppressPrintErrorAtNativePart** **(since rel_3.8.X)**

If set to true Native-errors during printing of documents will be
suppressed. There will be only a logging-information (logger.error) that
an error has occured.

This property has been implemented because of Call 84656.

[default-value]{.underline}: ***Word.suppressPrintErrorAtNativePart =
false*** (will be used if property has not been set)

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**DEL_ORDPOS_PROFILE** **(since 3.6.b, file property, ORD/alex)**

Default:false

Defines if an selected OrderProfile containing empty text fields should
replace pre-edited or by default filled order positions. This behaviour
is valid only for non boolean order positiontypes (like: string,
freetext, date and so on). See Applix Call 82412.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**USE_LABORBEF_SERVICE (since rel_3.6.b, file property, DOC / Dorfmair,
change 127830)**

Has to be used if Laboratory and KIS- Documents are contained in
different DB\'s. In this case two services are necessary with sepparte
SCT_DB logicals.

Default value is false. In such a case all SCT document reading is done
by the ATxtI class.

If value is set to \"true\" then the laboratory SCT documents will be
read by the LaborATxtI class.

Usage with the Dispatcher is: the class which has to be entered in the
dispatcher config is

the at.co.systema.labor.LaborATxtI.

Usage: USE_LABORBEF_SERVICE=true

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**ImportedDataExtractor.pvcrosscheck** **(since rel_3.8, file property,
DOC / Gunda)**

Allows to specify if during an document import a crosscheck between
patient data and the visit data has to be performed.

Default value is true (the crosscheck for name, givenname and birthdate
will be done)

Usage: ImportedDataExtractor.pvcrosscheck=false

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**gf.print.MpaPrinterManager.domainname (since rel_3.5, file property,
ACT_BASE, Siegfried Kaltenbrunner)**

**(since rel_3.8 im Repo unter GFPrinterProperties.domainName,
MPA_DOC/wolfgang8)**

(default: empty)

Allows to specify an optional domain name to be added to the
printer-server-name during printer-checking.

e.g. in noeKIT sometimes a printer is known to MPA as
\"\\\\nkprinta\\printerXY\" while the correct printer known to Windows
is \"\\\\nkprinta.nk.lokal\\printerXY\". To enable the program to fix
this, set this property to \"nk.lokal\". (see Call 58351, Change 116868
^(22)^)

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

~~**AudioDokType**~~

~~Default Audio Dokumenttyp für Workflow-Diktate~~

~~Beispiel:~~

~~AudioDokType=24~~

thomas9/lucky: obsolet mit rel_2.0

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\

\-\--**-** DRUCKVORLAGEN
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**useOOPrint** **(since rel_3.8.3, file property)**

if set to True this property enables for all print actions, on that
client, that OpenOffice is used instead.

This property is designed to be used on servers only where also an
OpenOffice is installed localy.

default = False

This implementation is still in experimental state and should be used
accordingly!

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**LogPrinterCodePage_LogDrucker** **(file property, since rel_3.6,
MPA_DOC/Dorfmair)**

Um für den Etikettendrucker die verwendete CodePage zu definieren wird
diese Propertie verwendet, Der Eintrag besteht aus zwei Teilen:
LogPrinterCodePage\_ ist für alle gleich und LogDrucker wird durch den
LogPrinter Namen des jeweiligen Druckers ersetzt werden.

Falls der LogPrinter Name \"LaborDrucker\" währe wurde der Eintrag im
Customer.propertie wie unten ausschauen.

LogPrinterCodePage_LaborDrucker=Cp863

Die zur Verfügung stehenden CodePages sind im Dokument ^(23)^
beschrieben.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**LogPrinterCharMap_LogDrucker** **(file property, since rel_3.6,
MPA_DOC/Dorfmair)**

Um für den Etikettendrucker die verwendete Character-Umschlüsselung zu
definieren wird diese Propertie verwendet, Der Eintrag besteht aus zwei
Teilen: LogPrinterCharMap\_ ist für alle gleich und LogDrucker wird
durch den LogPrinter Namen des jeweiligen Druckers ersetzt werden.

Falls der LogPrinter Name \"LaborDrucker\" währe wurde der Eintrag im
Customer.propertie wie unten ausschauen.

LogPrinterCharMap_LaborDrucker=ä:123,Ä:91,ö:124,Ö:92,ü;125,Ü:93,ß:126

\

Die zu beachtenden Details sind im Dokument ^(24)^ beschrieben.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

~~**USE_PRINTING_LIGHT**~~

~~gibt an ob die im Repository unter views.edit.print gespeicherten
Druckvorlagen zu verwenden sind.~~

~~Falls nicht, dann wird via Word gedruckt.~~

~~USE_PRINTING_LIGHT=true~~

~~**OBSOLETE: ab Rel_3.2**~~

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\-\--**-** LOGGING
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**gf.logging.ChainsawParsingPattern (since 3.8, file property,
bwajtr@ACT_ICZ2)**

\# This variable is mandatory if gf.logging.UseChainsawForLogViewing
property is set to true.

\# This variable specifies the default configuration pattern Chainsaw
log viewer

\# will use to parse log files of services. It is ABSOLUTELY NECESSARY

\# to update this property whenever the layout configuration pattern of

\# of loggers changes, otherwise Chainsaw will be unable to parse the
files

\# correctly and will issue errors and display the data incorrectly.

\# see details in help of Chainsaw or
http://logging.apache.org/log4j/docs/chainsaw.html

gf.logging.ChainsawParsingPattern = TIMESTAMP LEVEL THREAD\] LOGGER :
MESSAGE

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**gf.performance.performanceRecordingEnabled (ab rel_3.6, file property,
ACT_BASE, Sascha Hofer)**

Hauptschalter für das Performancerecording. Gültige Werte: true/false

siehe auch ^(25)^

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**gf.util.SystemLoggerDir** **(at least since rel_3.4, file property,
ACT_BASE)**

Bestimmt das Verzeichnis, in welchem die LOG-Dateien abgelegt werden.

Wird dieses Property nicht gesetzt, so werden die LOG-Dateien im
Unterverzeichnis \'log\' vom \'customer\'-Verzeichnis ^(26)^

angelegt, evtl. wird das \'log\'-Verzeichnis neu angelegt. Sollte das
Anlegen des Verzeichnisses misslingen, so wird das
\'customer\'-Verzeichnis verwendet.

gf.util.SystemLoggerDir=d:\\\\temp

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**gf.util.SystemLoggerName** **(at least since rel_3.4, file property,
ACT_BASE)**

Dieser Dateiname wird für die LOG-Datei verwendet - siehe auch
\'gf.util.SystemLoggerEnum\'.

Wird dieses Property nicht angegeben, so wird der Dateiname
\'*SystemLogger.log*\' verwendet.

(Note by Zbynek Novotny/ICZ2 \-- the %appName% parameter is needed for
the display of log files of stopped/dead services to work correctly in
ACT Monitor)

gf.util.SystemLoggerName = %appName%\_Output.log

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**gf.util.SystemLoggerEnum** **(at least since rel_3.4, file property,
ACT_BASE)**

Es wird der LOG-Dateiname (\'gf.util.SystemLoggerName\') so angepasst,
dass das Datum und die Uhrzeit im

Dateinamen enthalten sind, dadurch entsteht je Applikationsaufruf ein
neuer (eindeutiger) LOG-Dateiname,

z.B. Output_20010918_085930.log.

Dieses Property ist ein \'boolean\'-Property, somit wird es mittels
\'true\' aktiviert.

gf.util.SystemLoggerEnum=true

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**gf.util.SystemLoggerObsoleteAfter** **(at least since rel_3.4, file
property, ACT_BASE)**

Logfiles werden nach 30 Tagen gelöscht, und zwar zu dem Zeitpunkt

nach dem man den Usernamen und das richtige Passwort eingegeben hat.

Wer die 30 Tage auf einen anderen Zeitraum ändern möchte kann

das im Properties-File unter *gf.util.SystemLoggerObsoleteAfter*

machen, wenn man dort nichts angibt, werden keine Dateien gelöscht.

gf.util.SystemLoggerObsoleteAfter=5

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**gf.util.SystemLogger.reprintLines** **(since rel_3.2.1, file property,
ACT_BASE)**

Seit rel_3.2.1 (Change: ^(27)^)

Typ integer

Defaultwert: 20

Wenn der SystemLogger.Reopener ein Logfile schliesst und ein neues
öffnet, werden die angegeben Anzahl von

Zeilen aus dem OriginalFile in das neue File kopiert.

Damit steht auch in den Folgefiles der \"Programmstart\" und alle seine
Ausgaben

gf.util.SystemLogger.reprintLines=20

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**gf.logging.memoryLoggerTI (since rel_3.8, file property, ACT_BASE,
Sascha, Alex)**

By this property the time interval in milliseconds for regular logging
of memory (done by MemoryLogger)

is set.

By this property, one part the old structured MEMORY_LOGGER property is
replaced.

Default value:

gf.logging.memoryLoggerTI = 600000

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**gf.logging.memoryCriticalRatio (since rel_3.8, file property,
ACT_BASE, Sascha, Alex)**

By setting this property it is posssible to specify ratio, by which
MemoryWatcher MBean changes status from OK to WARN (consumed memory /
max. heapsize).

(Monitoring issue - the status of MemoryWatcher than influences the
status of entire service, which can be displayed somewhere)

By this property, one part the old structured MEMORY_LOGGER property is
replaced.

Default value:

gf.logging.memoryCriticalRatio = 0.9

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**gf.logging.mbean.logHistoryLength (kiml@ACT_ICZ2) - since rel_3.8 in
the customer.properties file**

This property specifies the max. number of log entries kept in
LogFileWatcher history. Once the limit is reached, the oldest entries
are discarded whenever new log entry is recorded (simply - it specifies
the FIFO length).

The higher this number is, the longer is the history of logged events,
which are subject of examination by LogFileWatcher MBean.

The cost for long history are of course the performance payload and
memory consumption.

Default value:

gf.logging.mbean.logHistoryLength = 100

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**gf.logging.mbean.tailLogFileLines (kiml@ACT_ICZ2) - since rel_3.8 in
the customer.properties file**

This property specifies default lenght of logfile tail to see of
LogFileWatcher history.

Is using as safe maximum value too.(ptimal value is about 10000).

Going above this value might cause instability on the server\'s side(if
the server\'s log is too big).

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**gf.util.ObjectStatisticsMgr.logInterval (since rel_3.6.b, file
property, ACT_BASE/Sascha)**

\# The log interval for object statistics in seconds

\# possible values:

\# n \<= 0: only print object statistics when the application exits

\# n \> 0: print object statistics every n seconds

\# default value: -1

\# see also Notes Software Development Doc# 3645 ^(28)^

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**gf.logging.lowMemoryWaterMark (since rel_3.6.b file property,
ACT_BASE)** **g6 - obsolete ?**

If a MPA service or application notice that the currently used memory is
near the maximum memory size it can send an email to someone.
(customizeable via log4j).

MPA uses this property to determine if it should sendout mail or not. So
the lowMemoryWaterMark is a number with a range from 0 to 100 while 0
indicate

that 0% of the available memory is used and 1 indicate that 100% of the
available memory is used. For example if the property is set to 90 MPA
will start sending emails

if 90% of the maximal available memory is used by the application.

DefaultValue

gf.logging.lowMemoryWaterMark=90

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

~~**MEMORY_LOGGER**~~ ~~~~ **replaced with 3.8 by:** ^**(29)**^ and
^(30)^

~~Definition MEMORY_LOGGER=\<Zeitintervall(s)\[#Speicher(MB)
Schwellwert\]. Protokolliert der JVM-Heap-Speicher je Zeitintervall und
ab Schwellwert.~~

~~zum Beispiel:~~

~~\# je 5 min ab 30MB protokollieren~~

~~MEMORY_LOGGER=300#30~~

~~#Protokollierung ausschalten~~

~~MEMORY_LOGGER=0~~

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\-\--**-** PERFORMANCE LOGGING
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**client.properties**

\# Zeitintervall für die Generierung der ThreadDumps \[ms\].

**THREADDUMP_LOG_INTERVAL**=500

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**client.properties**

\# IP des Clients. Nur für den Client werden ThreadDumps generiert

\# Client der Unfallabulanz, Erstuntersuchung: psraeeu03

\#**THREADDUMP_LOG_FOR_CLIENT**=10.138.9.136

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\

\

\-\--**-** ENVIRONMENT/SCT-LOGICALS
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**Environment.autoset.PPK_MEDENTL_CURSOR_NEU=T** **(ab 3.6.b,
fileProperty,**mit **Environment.autoset, MPA_KIS, Tomschi)**

**must be a file based property**

[Typ:]{.underline} Stringliste

*kein Defaultwert*

Cursor zum Lesen von nicht medizinisch entlassenen Patienten wird
beeinflusst (**Applix-Call 50096**).

Der unterschied liegt darin, dass unterschiedliche Index verwendet
werden.

***nicht gesetz**t* - alter Cursor wird verwendet:

Index x5_pat_auf wird verwendet:

khs_kh_kz

pat_last_lst

pat_last_zimmer

pat_last_bett

pat_auf_nr

***gesetzt*** - neuer Cursor wird verwendet:

Index x4_pat_auf wird verwnedet:

khs_kh_kz

pat_entl_zp

pat_last_lst

pat_ambk

pat_name

pat_az

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**AZ_FILL_JHDT19** **(at least since rel_3.4, file property, MPA_KIS)**

gibt an wie die AZ in der DB gespeichert sind (Default \"\" = ohne 19)

wenn gesetzt, dann wird 19 mitgespeichert

Beispiel:

AZ_FILL_JHDT19=False

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\

**SCT Umgebungsvariablen**

die mit **Environment.autoset** gesetzt werden können bzw. müssen.

\

Diese Variablen werden von den SCT DLL\'s verwendet.

Genauere Beschreibung kann unter
\\\\fix\\sct\\OPENSct\\V40\\SAS\\DOC\\SCT_RUN.DOC nachgelesen werden

\

Beispiel: Environment.autoset.SCT_DB=kis_db

\

**Environment.autoset. (at least since rel_3.4, file properties, various
development teams)**

Ist ein Prefix für Properties die zusätzlich als Environmentvariable
erzeugt werden. Die Property \'Environment.autoset.XX=yy\' erzeugt
zusätzlich eine EnvironmentVariable mit Namen XX. Der Wert der Variable
entspricht dem Wert der Property (Bsp: yy). Es können Environments nur
gesetzt, nicht aber entfernt werden. Das Environment gillt nur innerhalb
der VM.

Beipiel:

Environment.autoset.SCT_DB=kis_db

\

^(31)^Environmentvariablen

\

**SCT_ALL_USER** **(at least since rel_3.4, file property,
ACT_BASE/MPA_KIS)**

Ist dieses Logical auf irgendeinen Wert gesetzt, so kann man mit jedem
SCT-Usernamen und beliebigem Passwort in einer SCT-Applikation
einsteigen.

(Trifft im MPA nicht zu:) ~~Ebenso kann man dann im Benutzer-Feld nach
einem Benutzer suchen, ansonsten ist Suchen in diesem Feld
deaktiviert.~~

\

**SCT_MSTR_TXN_MODE(at least since rel_3.4, file property,** mit
**Environment.autoset, ACT_BASE/MPA_KIS)**

Legt fest, ob READ MASTER als READ oder READ/WRITE Transaktion
ausgeführt wird. Falls auf \'READ\' gesetzt, dann READ-TXN, sonst RW-TXN
(alle anderen Werte bzw. nicht gesetzt).

Beispiel:

Environment.autoset.SCT_MSTR_TXN_MODE=READ

\

**SCT_STMTBUF_SIZE(since rel_3.6, file property,** mit
**Environment.autoset, ACT_BASE/MPA_KIS)**

Bestimmt die Größe des SQL-Statement-Puffers (d.h die Anzahl der
SQL-Statements (z.B. 1 Statement = SELECT oder INSERT \...), die
gepuffert werden) bei halb-dynamischen Datenbankzugriffen (dynamischer
DBUC).

Default-Puffergrösse: 50 Statements

Beispiel:

Environment.autoset.SCT_STMTBUF_SIZE=100

\

**SCT_DB_NAMES(file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

Mit diesem Logical kann bestimmt werden, daß unterliegende Applikationen
auf eine andere Datenbank als SCT_DB zugreifen können.

Diese Einstellung mit mehreren Datenbanken ist nur bei halb-dynamischen
DB-Zugriffen möglich.

Syntax

names -\> appl_name { \',\' appl_name } \'=\' db_name { \',\' names }

Beispiel:

ABU und FIB sollen auf DB1 zugreifen, KOR auf DB2 und SAS auf DB0,

alle sonstigen Applikationen verwenden SCT_DB.

Environment.autoset.SCT_DB_NAMES=ABU,FIB=DB1,KOR=DB2,SAS=DB0

\

**SCT_DB(at least since rel_3.4, file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

Auf diese Datenbank wird im laufenden Programm zugegriffen

Diese UmgebungsVar muss gesetzt werden wenn der ODBC Test durchgeführt
werden soll! (siehe ODBC Test)

\

**SCT_READ_TXN_MODE(file property,**mit **Environment.autoset,
ACT_BASE/MPA_KIS)**

Falls gesetzt, werden alle READ-TXN als READ/WRITE-TXN ausgeführt.

\

**DB_INFO_IGNORE_CASE(file property,**mit **Environment.autoset,
ACT_BASE/MPA_KIS)**

Ist dieses Logical definiert, so wird die Groß-/Kleinschreibung bei der
Einschränkung von Info-Stringfeldern ignoriert.

Diese Funktionalität wird nicht bei allen DBMS-Systemen unterstützt!

\

**SCT_ROTCO_ENA(file property,**mit **Environment.autoset,
ACT_BASE/MPA_KIS)**

Ist dieses Logical gesetzt, so wird der SCT-Mechanismus für carry-over
von Read-Only-Transaktionen eingeschaltet.

Mehrere aufeinanderfolgende Read-Only-Transaktionen werden innerhalb
eines zu bestimmenden Zeitraums (siehe SCT_ROTCO_TIM) automatisch zu
einer einzigen Transaktion zusammengefaßt.

\

**SCT_ROTCO_TIM(file property,**mit **Environment.autoset,
ACT_BASE/MPA_KIS)**

Achtung: ein zu großes Intervall hat Auswirkungen auf die Größe der
Datenbank-Snapshot-Files!

Bestimmt den Commit-Verzögerungszeitraum für carry-over von Read-Only
Transaktionen (siehe SCT_ROTCO_ENA).

Der numerische Wert in diesem Logical wird als Sekunden interpretiert.

Default-Wert (bei eingeschaltetem carry-over) ist 3 Sekunden.

Beispiel:

Environment.autoset.SCT_ROTCO_TIM=4

\

**DB_USE_MIN_VMSDAT(file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

AB RDB V6.1 (bzw. \> 6.0-11) NOTWENDIG!

für RDB

Gibt an, in welchem Format ein leeres SCT-DATUM verspeichert wird. Ist
dieses Logical gesetzt, so wird als leeres Datum das minimale VMS-Datum
verwendet (vorher eine Hundertstel Sekunde, \"0000 00:00:00.01\").

Ab RDB6.1 muß dieses Logical gesetzt sein (zuvor müssen alle leeren
Datumswerte von ein Hundertstel-Sek. auf minimales VMS-Datum umgestellt
werden (\'17-NOV-1858 00:00:00.00\')!

\

**DB_USE_LONG_ORA_DAT(file property,**mit **Environment.autoset,
ACT_BASE/MPA_KIS)**

für Oracle

Gibt an, in welchem Format ein SCT-DATUM unter Oracle verspeichert wird.
Ist dieses Logical gesetzt, so wird das Datum mit leerer Uhrzeit
verspeichert,

z.B. Datum 20.10.1997 -\> \'1997-10-20 00:00:00.00\', ansonsten wird
\'1997-10-20\' verspeichert.

Alte Daten-Felder müssen vorher umgespielt werden, so ein Datum brauchen
die Powerbuilder-Applikationen.

Ab SCT V3.4 wird dieses Format automatisch verwendet (mit Uhrzeit), wird
das bisherige Format benötigt, so muß das Logical DB_USE_SHORT_ORA_DAT
gesetzt werden.

\

**SCT_MAX_PIC_STR(file property,**mit **Environment.autoset,
ACT_BASE/MPA_KIS)**

für Windows, für ODBC-SQLServer

Normalserweise ist der höchste String-Wert ein \'Ü\'. Bei SQLServer und
lexikalischem Sort ist \'Ü\' aber ungeeignet (\'Ü\' kommt direkt nach
\'U\'). Deshalb verwendet die SQLServer-Schnittstelle als Default \'Z\'.

Der SQLServer-Default-Wert kann mit diesem Logical übersteuert werden.

Beispiel:

Environment.autoset.sct_max_pic_str=Z

\

**SCT_DBUSR(file property,**mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

für VMS, für Oracle

Übersteuert den Default-Oracle-User (SCTUSR).

Beispiel:

Environment.autoset.SCT_DBUSR=KIS54

\

**SCT_DBPWD(file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

für VMS, für Oracle

Übersteuert des Default-Oracle-Userpasswort (SCTUSR).

Beispiel:

Environment.autoset.SCT_DBPWD=KIS54

\

**SCT_ODBC_USER(file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

für Windows, für ODBC

In diesem Logical wird der OS-Benutzername eingetragen, mit welchem eine
Verbindung zu einer Datenbank per ODBC errichtet wird (ORACLE - dieser
Benutzer wird auch als Datenbank-Benutzer verwendet).

Beispiel:

Environment.autoset.sct_odbc_user=username

Diese UmgebungsVar muss gesetzt werden wenn der ODBC Test durchgeführt
werden soll! (siehe ODBC Test)

\

**SCT_ODBC_PWD(file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

für Windows, für ODBC

In diesem Logical wird das Passwort des ODBC-Benutzers eingetragen. Ist
eine ODBC-Passwort-Datei für die aktuelle SCT_DB (SCTDB_NAME.PWD)
vorhanden, so wird von dort das Passwort verwendet, außer das Logical
DB_IGNORE_PWDFILE ist gesetzt.

Beispiel:

Environment.autoset.sct_odbc_pwd=passwort

Diese UmgebungsVar muss gesetzt werden wenn der ODBC Test durchgeführt
werden soll! (siehe ODBC Test)

\

**SCT_ODBC_USER_sct_db_name(file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

ab SCT V3.6, für ODBC

Gleiche Verwendung wie Logical \'SCT_ODBC_USER\', nur gilt es für
Datenbanken aufgrund dem Logical \'SCT_DB_NAMES\'.

Beispiel:

Environment.autoset.sct_odbc_user_dbname=username

\

**SCT_ODBC_PWD_sct_db_name(file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

ab SCT V3.6, für ODBC

Gleiche Verwendung wie Logical \'SCT_ODBC_PWD\', nur gilt es für
Datenbanken aufgrund dem Logical \'SCT_DB_NAMES\'.

Beispiel:

Environment.autoset.sct_odbc_pwd_dbname=passwort

\

**DB_IGNORE_PWDFILE(since rel_3.4, file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

ab SCT V3.4, für ODBC

Ist dieses Logical gesetzt, so wird die ODBC-Passwort-Datei
(SCTDB_NAME.PWD) ignoriert und es werden die Daten von den Logicals
SCT_ODBC_USER, SCT_ODBC_PWD verwendet.

Beispiel:

Environment.autoset.db_ignore_pwdfile=true

\

**DB_PWDFILE_CASE(since rel_3.4, file property,**mit
**Environment.autoset, ACT_BASE/MPA_KIS)**

Ist dieses Logical gesetzt, so können alte Passwort-Dateien nicht mehr
ausgelesen werden bzw. Applikationen mit älterem SCT können die neue
Datei nicht mehr korrekt auslesen.

ab SCT V3.4, für ODBC

Bisher wurde die Groß- bzw. Kleinschreibung des OS-Benutzernamens bzw.
dessen Passwortes für die ODBC-Verbindung nicht unterschieden, daher
konnten auch keine Benutzernamen bzw. Passwörter mit Kleinbuchstaben
verwendet werden.

Ist dieses Logical gesetzt, so wird die Groß- bzw. Kleinschreibung beim
Erstellen der ODBC-Passwort-Datei (SCTDB_NAME.PWD) beachtet.

\

**SCT_OOE_DB_SECURITY(since rel_3.5, file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

ab SCT V3.5, für OSF, für Informix

Ist dieses Logical gesetzt, so wird eine spezielle Logik beim Aufbau
einer Verbindung zur Datenbank angewandt.

\

**DB_UCO_BY_ROWID(file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

ab SCT V3.6, für VMS - Oracle, für Windows - ODBC-Oracle

Wird dieses Logical auf \'FALSE\' gesetzt, so wird das Statement
\'UPDATE_WHERE_CURRENT_OF\' nicht mehr per \'ROWID\' durchgeführt.

Beispiel:

Environment.autoset.db_uco_by_rowid=FALSE

\

**DB_TXNCHECK_DISABLED(file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

ab SCT V3.6

Ist dieses Logical gesetzt, so wird nicht mehr geprüft, ob eine
Transaktion bereits implizit geöffnet wurde.

\

**LS_UML_druckername(file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

Je LS-Drucker kann man ein Logical definieren, in welchem die
Umschlüsselung von SCT-Zeichen auf Drucker-Zeichencode bei der Ausgabe
auf diesen Drucker definiert wird. Hinsichtlich Syntax siehe
\'sas_help:ls.doc\'.

Beispiel:

Für Drucker MT908:

Environment.autoset.LS_UML_MT908=ä:246;

\

Unter Windows-NT müssen die Sonderzeichen für LS_UML\_\... UNBEDINGT mit
einem DOS-Editor (edit in DOSBox) bearbeitet werden! (Problem
Windows/Dos-Character-Sets)

\

Unter Windows-95(98) müssen die Sonderzeichen für LS_UML\_\... UNBEDINGT
mit einem Windows-Editor (wordpad) bearbeitet werden!

\

**LS_PR_ls_queue_name(file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

für Windows

Je LS-Queue kann ein Logical definiert werden, welches dann den
Queue-Namen im Windows-Format enthält. Beim Ausdruck einer Liste wird
dann der \'Windows-Queue-Name\' verwendet, hinsichtlich genauerer
Details - siehe \'sas_help:ls.doc\'.

Beispiel:

Für LS-Queue TEST\$PRINT:

Environment.autoset.LS_PR_TEST\$PRINT=\\\\prt_pc\\test\$p

\

**Logicals für Working-Set-Trimming** **(file property,**mit
**Environment.autoset, ACT_BASE/MPA_KIS)**

Durch Definition folgender Logicals kann ein automatisches, asynchrones
Working-Set-Trimming von SCT-Prozessen aktiviert werden.

Die SCT-Implementierung ist im Backend-Bereich erfolgt. Bei ACMS wirkt
sich das automatische WS-Trimming somit nur auf ACMS-Server-Prozesse
aus!

Alle Logicals können zur Laufzeit verändert werden. Die Logicals werden
in SCT_WSTRIM_INVT-Intervallen neu geprüft.

\

Automatisches Workingset-Trimming ist auf folgenden Betriebssystemen
unterstützt:

Digital VMS (VAX und AXP)

\

\

**Es wird zwischen zwei Arten von Trimming unterschieden:**

**normales Workingset-Trimming**

(siehe Logicals SCT_WSTRIM_TMO bzw. SCT_WSTRIM_SIZE).

Die Werte für normales WS-Trimming sollten so gewählt werden, daß es zu
keiner wesentlichen Performancebeeinträchtigung beim normalen
Arbeitsablauf kommt.

Die SCT_WSTRIM_SIZE sollte hierbei so gewählt werden, das Userprozesse
nach einem Trimming keine allzuhohe Page-Fault-Rate aufweisen.

\

Normales Workingset-Trimming wird duch Definition folgender Logicals
aktiviert:

SCT_WSTRIM_INTV

SCT_WSTRIM_TMO

SCT_WSTRIM_SIZE

\

**aggressives Workingset-Trimming**

(siehe Logicals SCT_AWSTRIM_TMO bzw. SCT_AWSTRIM_SIZE).

Die Werte für aggressives WS-Trimming sollten so gewählt werden, daß
Benutzer, die über einen längeren Zeitraum inaktiv sind, möglichst viel
Memory freigeben.

Hierbei ist eine höhere Page-Fault-Rate bei neuerlicher Aktivität
durchaus zu akzeptieren.

\

Aggressives Workingset-Trimming wird durch Definition folgender Logicals
aktiviert:

SCT_WSTRIM_INTV

SCT_AWTRIM_TMO

SCT_AWSTRIM_SIZE

\

Es wird empfohlen, die SCT_WSTRIM-Logicals prinzipiell systemweit zu
definieren.

Userspezifische Übersteuerungen können dann prozessweit vorgenommen
werden.

\

siehe auch: Anwendungsbeispiel VMS

\

\

**Regeln**

Automatisches WS-Trimming wird nicht durchgeführt, wenn:

\- Logical SCT_WSTRIM_INTV nicht definiert ist

In diesem Fall wird beim Image-Start auch kein AST aufgesetzt, durch
welchen WS-Trimming nachträglich zur Laufzeit eingeschaltet werden kann.

\- Logical SCT_WSTRIM_INTV auf 0 definiert ist

WS-Trimming ist deaktiviert - kann aber jederzeit zur Laufzeit
eingeschaltet werden.

Siehe auch Logical-Beschreibung

\- Die Transaction-Idle-Timeouts nicht erreicht wurden

Siehe Logicals SCT_WSTRIM_TMO bzw. SCT_AWSTRIM_TMO

\- Die WSTRIM-Prüfung feststellt, daß gerade eine Transaktion aktiv ist.

\

**SCT_WSTRIM_INVT(file property,**mit **Environment.autoset,
ACT_BASE/MPA_KIS)**

ab SCT V3.5

Integer - bestimmt die Sekunden zwischen den WS-Prüfungen.

\

Ist dieses Logical auf 0 gesetzt, so wird automatisch ein 15-Minuten
Prüfintervall auf die WSTRIM-Logicals gesetzt, wobei WS-Trimming
allerdings deaktiviert ist.

\

Eine nachträgliche Redefinition dieses Logicals auf einen anderen Wert
aktiviert bei allen bereits aktiven Sessions das Workingset-Trimming
(wobei das 15-Minuten-Prüfintervall nicht geändert wird).

Für neue Sessions wird Working-Set-Trimming mit dem angegebenen
Intervall aktiviert.

Dieses Logical wird normalerweise systemweit gesetzt.

Soll für bestimmte User kein WS-Trimming durchgeführt werden, so kann
das Logical userspezifisch auf 0 definiert werden.

\

**SCT_WSTRIM_TMO(file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

ab SCT V3.5

Integer - bestimmt die Sekunden, die seit der letzten Transaktion
vergangen sein müssen, um automatisches WS-Adjustment durchzuführen.

\

**SCT_WSTRIM_SIZE(file property,**mit **Environment.autoset,
ACT_BASE/MPA_KIS)**

ab SCT V3.5

Integer zwischen 1 und 100 - beschreibt die Ziel-WS-Size in MB.

Es wird asynchron in SCT_WSTRIM_INTV-Intervallen geprüft, ob seit
SCT_WSTRIM_TMO-Sekunden keine Transaktion mehr aktiv war. Ist dies der
Fall und ist SCT_WSTRIM_SIZE definiert, so wird das Working-Set des
Prozesses automatisch auf SCT_WSTRIM_SIZE verkleinert.

\

**SCT_AWSTRIM_TMO(file property,**mit **Environment.autoset,
ACT_BASE/MPA_KIS)**

ab SCT V3.5

Aggressives Working-Set-Trimming

Integer - bestimmt die Sekunden, die seit der letzten Transaktion
vergangen sein müssen, um aggressive-WS-Adjustment durchzuführen.

\

**SCT_AWSTRIM_SIZE(file property,**mit **Environment.autoset,
ACT_BASE/MPA_KIS)**

ab SCT V3.5

Integer zwischen 1 und 100 - beschreibt die Ziel-WS-Size in MB bei
aggressive-WS-Adjustment.

In SCT_WSTRIM_INTV-Intervallen wird geprüft, ob seit
SCT_AWSTRIM_TMO-Sekunden keine Transaktion mehr aktiv war. Ist dies der
Fall und ist SCT_AWSTRIM_SIZE definiert, so wird das Working-Set des
Prozesses automatisch auf SCT_AWSTRIM_SIZE verkleinert.

\

**SOSIEHF_IGN_LOG_F(file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

Ist dieses Logical gesetzt, so werden die speziellen Log-Funktionen
(z.B. zum Ausgeben des letzten DB-Statements), welche beim SYSERR,
WARNING, OSERR, VMSERR installiert sind, NICHT aufgerufen.

Bricht ein Programm ohne ein SOSIEHF.LOG ab, so könnte eine der
speziellen Log-Funktionen Schuld sein.

Beispiel:

Environment.autoset.SOSIEHF_IGN_LOG_F =TRUE

\

**SOSIEHF_NOHANDLER(file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

Ist dieses Logical gesetzt, so kommt keine Meldung \'ACHTUNG FEHLER\'.

Dieses Logical dient dem besseren Handling mit dem Debugger. (siehe
\'sas_doc:sosiehf.doc\')

\

**SOSIEHF_USE_EXCPT(file property,**mit **Environment.autoset,
ACT_BASE/MPA_KIS)**

ab SCT V3.6, für Windows

Ist dieses Logical gesetzt, so wird eine Applikation bei einem
\'SYSERR\', \'OSERR\' bzw. \'ERR\' nicht mehr beendet, sondern es wird
eine spezielle Exception ausgelöst, welche mit einem speziellen
Exception-Handler in der Applikation abgefangen werden muss.

Der SCT Exception-Handler \'SOSIEHF_START/STOP\' darf nicht verwendet
werden.

\

**SOSIEHF_NOSTACKCHECK(file property,**mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

Ist dieses Logical gesetzt, so wird der Stapelspeicher des
Error-Handling-Systems nicht geprüft, d.h. fehlende SCT_RETURN/\_VOID
werden nicht mit einem SYSERR \'belohnt\'.

\

**SOSIEHF_INFO_CNT(file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

Mit diesem Logical kann man die Anzahl der Zeilen im Info-Buffer des
Error-Handling-Systems einstellen, ist das Logical nicht gesetzt, so
werden die letzten 100 Info-Einträge gepuffert.

Beispiel:

Environment.autoset.SOSIEHF_INFO_CNT 200

\

**SOSIEHF_MODE(file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

Dieses Logical dient zur Überwachung von SCT-Aktivitäten und sollte nur
in Ausnahmefällen verwendet werden.

Folgende Buchstaben werden unterstützt:

**S**

Es werden die verschiedensten Informationen einer SCT-Applikation in
einen \'shared memory\'-Bereich geschrieben, ebenso wird der Call-Stack
der aufgerufenen Funktionen eingetragen (Informationen werden per SCTMON
ausgewertet).

**SN**

wie \'S\', Call-Stack wird nicht eingetragen

**N**

Es wird kein genereller Call-Stack mitgeführt, d.h. kein Call-Stack im
\'SOSIEHF.LOG\'.

**D**

Es wird ein File \'SOSIEHF.DMP\' mit allen Funktions-Aufrufen (beim
SCT_ENTER) erstellt.

\

**SOSIEHF_IPC_STACK_CNT(file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

ab SCT V3.6

Mit diesem Logical kann die Größe des \'Call-Stacks\' für die
IPC-Überwachung (SCTMON, SOSIEHF_MODE = \'S\') eingestellt werden,
defaultmäßig werden 20 \'function calls\' gespeichert.

Beispiel:

Environment.autoset.SOSIEHF_IPC_STACK_CNT=40

\

**SOSIEHF_DIR(file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

ab SCT V3.4 auch auf VMS, OSF (bisher nur Windows)

Ist dieses Logical gesetzt, so werden die Error-Handler-Log-Files
(SOSIEHF.LOG) auf diesem Verzeichnis abgelegt.

Beispiel:

Environment.autoset.SOSIEHF_DIR=c:\\temp

\

**SOSIEHF_VERSION(file property,**mit **Environment.autoset,
ACT_BASE/MPA_KIS)**

für Windows

Ist dieses Logical gesetzt, so wird beim Datei-Namen der Error-Handler
Log-Files (SOSIEHF.LOG) eine Versions-Nummer angehängt
(\'SOSIEHF.LOG000\' bis \'SOSIEHF.LOG999\').

Ist das Logical \'SOSIEHF_DIR\' gesetzt, so wird \'SOSIEHF_VERSION\'
ignoriert, da dann ein anderer Datei-Name erstellt wird
(SO_pcname_000.LOG\' bis \'SO_pcname_999.LOG\', z.B. SO_PC1_000.LOG).

\

**SOSIEHF_EXTEND_NAME(file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

ab SCT V3.4

Wird normalerweise nur zusammen mit \'SOSIEHF_DIR\' verwendet, damit die
Error-Handler-Log-Files leichter dem Verursacher zuzuordnen sind.

Ist dieses Logical gesetzt, so wird der Datei-Name des Error-Handler
Log-Files erweitert.

Name:

SOSIEHF_sctusername.LOG bzw. SOSIEHF_osusername.LOG

(wenn keine SCT-User aktiv)

Name unter GUI:

SOSIEHF_clientpcname_sctusername.LOG bzw.

SOSIEHF_clientpcname_osusername.LOG

\

**SCT_MEM_DEBUG(file property,**mit **Environment.autoset,
ACT_BASE/MPA_KIS)**

Dient der Überwachung von sosimem, sosimem(c)free Bereich bzw.
wiederholtes \'\_free\'.

Wird in Verbindung mit \'sosimem_alloc_cnt\' verwendet, siehe auch
\'sosimem.h\'.

Schreibt syserr, falls allokierter Speicherbereich über seine Grenzen
hinaus beschrieben wird, z.B. Array mit 5 Elementen allokiert und 6.
Element beschrieben etc.

Folgende Buchstaben werden unterstützt:

**X**

gesamter Check wird nach jedem ALLOC durchgeführt

**A**

gesamter Check wird nach jedem ALLOC bzw. vor jedem FREE durchgeführt

**F**

wie \'A\', nur wird der gesamte Check auch noch zusätzlich bei jedem
SCT_RETURN durchgeführt, sodaß die überschreibende Routine sofort
gefunden wird (langsam, aber wirksam \...)

**C**

ist dieser Buchstabe gesetzt, so wird eine WARNING ausgegeben, wenn die
Anzahl an FREE\'s größer als die an ALLOC\'s ist (irgendeine Adresse
wird mehrmals freigegeben, \...).

Diese Option kann nicht mit anderen Optionen kombiniert werden.

**R**

überprüft die korrekte Verwendung von SOSIMEM_SET_CHK (bzw.
SOSIMEM_SET_CHK2) via Status-Check bei SCT_ENTER bzw. SCT_RETURN.

Falls nicht korrekt verwendet (vor SCT_RETURN wurde vom Programm der
ursprüngliche SET_CHK-Status nicht wiederhergestellt \...), wird der
Status automatisch korrigiert und eine Fehlermeldung am BS angezeigt.
(ab SCT V3.5)

**L**

Permanent-Memory-Klasseninformation sammeln. Jede mit SOSIMEM_SET_CHK2
als permanent allokierte Memory wird der beim Markieren angegebenen
Klasse (Parameter 2 von sosimem_set_chk2) zugeordnet.

Diese Informationen werden nur über SCT_PROTO (Menüpunkt Memory)
angezeigt bzw. in die Datei SOSIMEM.DMP geschrieben. (ab SCT V3.5)

**S**

gesamte Stack-Information speichern. Bei offenen Allocs bzw. bei
Permanent-Alloc-Dump (siehe Option L) wird nicht nur die aktuelle und
aufrufende Funktion angezeigt, sondern zusätzlich der gesamte
Call-Stack. (ab SCT V3.5)

**M**

Free-Memory-Check.

Bei einem sosimem_free wird die Memory in der internen
Speicherverwaltung nur als frei markiert, aber nicht wirklich
freigegeben. Mit dieser Option werden mehrfache Free\'s auf die gleiche
Adresse geprüft, bzw. ein nachträgliches Überschreiben von bereits
freigegebener Memory.

Achtung: Der Memorybedarf (dyn. alloc\'s) verdoppelt sich bei Verwendung
dieser Option!

\

Es können alle Buchstaben miteinander verknüpft werden (Ausnahme: Option
\'C\').

\

Meldungen:

FREE ohne ALLOC

Eine allokierte Adresse wird nochmals freigegeben, obwohl sie bereits
freigegeben ist.

CFREE AUF ALLOC

Eine allokierte Adresse (sosimem_alloc) wird mit der falschen
Freigabe-Routine (sosimem_cfree) freigegeben.

FREE AUF CALLOC

Eine allokierte Adresse (sosimem_calloc) wird mit der falschen
Freigabe-Routine (sosimem_free) freigegeben.

ALLOC OVERWRITE, CALLOC OVERWRITE

Ein allokierter (sosimem_alloc, sosimem_calloc) Bereich wurde
überschrieben.

FREE eines PERMANENTEN ALLOC\'s

Eine permanent allokierte Adresse wurde freigegeben, die Freigabe sollte
jedoch permanent erfolgen.

\

Eine Allokierungs-Funktion bzw. Freigabe-Funktion arbeitet dann im
Permanent-Modus, wenn sie wie folgt aufgerufen wird:

sosimem_set_chk (False)

funktion

sosimem_set_chk (True);

FREE_PERMANENT eines ALLOC\'s

Eine allokierte Adresse wurde permanent freigegeben, die Freigabe sollte
jedoch nicht permanent erfolgen.

\

**SCT_MEM_CLSFLT(file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

ab SCT V3.5

Logical für die Auswertung von Permanent-Memory-Klassen (siehe
SCT_MEM_DEBUG - Option L).

Dieses Logical definiert einen Filter für die Klassen-Auswertung:

Syntax:

\"\[!\]\<zeichenkette\>\[,\...\]\"

Der angegebene Filter kann Wildcards beinhalten.

Das Zeichen \'!\' gilt als NOT-Filter (Ausgrenzung).

Die Klasse NULL beschreibt nicht zuordenbare permanente Memory
(normalerweise Memory, die noch mit SOSIMEM_SET_CHK und nicht mit
SOSIMEM_SET_CHK2 markiert wurde).

\

Beispiele:

Auswertung aller Klassen, die nicht zu SCD bzw. SSRI gehören:

Environment.autoset.sct_mem_clsflt=!%SCD%,!%SSRI%

Auswertung der Klasse NULL:

Environment.autoset.sct_mem_clsfld=NULL

\

**SSRI_LOG(file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

Falls gesetzt, wird für alle dynamisch generierten DB - Zugriffe (DBUC
ohne DBUC_STATIC_GEN) ein Eintrag in einem Logfile (SSRIHD.LOG)
geschrieben - mit Statementname, Schema.

Außerdem werden alle START / COMMIT /ROLLBACK Transactions und
Attachments protokolliert (unabhängig von der Art der Generierung).

Spezielle Werte:

**F**

(full), es werden auch die Parameter-Werte von SQL-Statements
ausgegeben.

\

**SCT_EXPLAIN(file property,**mit **Environment.autoset,
ACT_BASE/MPA_KIS)**

Informix

Ist diese Umgebungsvariable gesetzt, werden Optimizer-Messages in den
File sqexplain.out auf dem Default-Directory geschrieben.

Oracle

Ist diese Umgebungsvariable bei Verwendung von ORACLE-DBMS gesetzt, so
wird ein SQL-Tracefile erzeugt, der mit dem TKPROF-Utility von Oracle
ausgewertet werden kann.

\

**SOSIPROC_USER_LOWER(file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

für OSF

Ist dieses Logical gesetzt, so wird der OS-Username nicht in
Grossbuchstaben umgewandelt.

\

**SCT_LOCK_DIR(file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

für Windows, OSF

Auf diesem Verzeichnis werden unter NT Files abgelegt, welche zum
\'Locken\' einer Resource verwendet werden.

Dieses Logical muß angegeben werden, damit \'sosilock\...\' unter NT
funktioniert (Verzeichnis sollte auf einer Netzfreigabe liegen).

Unter OSF wird auf diesem Verzeichnis eine Lock-Datei abgelegt.

Environment.autoset.sct_lock_dir=\\\\computer\\lockdir

\

**SCT_CLIENT_DEF_DIR(file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

ab SCT V3.4

Bestimmte kundenspezifische Definitions-Dateien (INI-Dateien, \...)
werden auf diesem Verzeichnis gesucht.

Momentane Verwendung:

\'scd_dyn.ini\' wird dort gesucht, ist das Logical nicht definiert, so
wird wie bisher auf \'PATH_CLSD\' gesucht.

Beispiel:

Environment.autoset.SCT_CLIENT_DEF_DIR KND_DISK:\[DEF\]

\

**PATH_BIG_BUF(file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

Dieses Logical zeigt auf ein Verzeichnis, auf welchem eine
\'BIG_BUF\'-Datei angelegt wird.

\

**PATH_BIG_BUF1(file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

Ist dieses Logical gesetzt und wird die \'BIG_BUF\'-Datei sortiert, so
wird die sortierte \'BIG_BUF\'-Datei auf diesem Verzeichnis abgelegt.

Soll die \'BIG_BUF\'-Datei erhalten bleiben (KEEP), so darf dieses
Logical nicht auf das gleiche Verzeichnis wie das Logical PATH_BIG_BUF
zeigen.

\

**SCT_BIG_BUF_NO_DEL(file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

Ist dieses Logical gesetzt, so wird die \'BIG_BUF\'-Datei niemals
gelöscht.

\

**KOMM_PAR_UPDT(file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

Steuert, nach wievielen Sätzen die Write-Transaktion (Update der
Schnittstellenparameter

im Record HL7_SCHNITTST) gestartet werden soll. Ist das Logical nicht
gesetzt, so erfolgt

defaultmäßig ein Update der Schnittstellenparameter nach 50 Sätzen

\

Verwendung: zB: Polling Service

**HL7_LOGFILE_PATH** **(file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

Legt den Pfad fest, auf welchem das Logfile bei der HL7-Schnittstelle -
Sanitas

abgelegt wird. Ist das Logical nicht gesetzt, wird das File auf dem
aktuellen

Verzeichnis abgelegt.

\

Verwendung: zB: Polling Service

\

**PAT_STORNO_RELATION(file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

Aktiviert beim Stornieren von Verlegungen, Leistungen, Frequenzen u.

Entlassungen die Sicherung der stornierten Daten in die Stornorelation.

\

**AZ_AUTO_FORMAT(at least since rel_3.4, file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

Steuert, ob die AZ bei der Eingabe automatisch auf die Eingabelänge
formatiert wird.

Mögliche Werte: SYSTEMA, JJ, JJJJ, NEIN

Default-Wert: SYSTEMA

JJ: Ist die Länge der eingegebenen AZ \<= (AZ-EING-LEN-2), so wird die
AZ auf die Eingabelänge expandiert und die 2-stellige aktuelle
Jahreszahl vorangestellt. z.B: 99

JJJJ: Ist die Länge der eingegebenen AZ \<= (AZ-EING-LEN-4), so wird die
AZ auf die Eingabelänge expandiert und die 4-stellige aktuelle
Jahreszahl vorangestellt z.B: 1999

SYSTEMA: Ist die Länge der eingegebenen AZ \<= (AZ-EING-LEN-2), so wird
die AZ auf die Eingabelänge expan-diert und die 2-stellige aktuelle
Jahreszahl vorangestllt z.B: 99

Bei der Eingabe einer AZ \<= 47483647 wird zusätzlich das aktuelle
Jahrhundert (2-stellig) vorangestellt.

NEIN: Keine Formatierung der Eingabe

Ist das Logical AZ_AUTO_FORMAT nicht gesetzt, dann wird der Default-Wert
SYSTEMA herangezogen.

Dieses Logical muß auch auf den Laborrechnern gesetzt werden!

\

Beispiel:

Environment.autoset.AZ_AUTO_FORMAT=SYSTEMA

\

**AZ_FILL_JHDT19(since rel_3.4, file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

Steuert die Länge der Aufnahmezahlen vor dem Jahr 2000

Mögliche Werte: TRUE, FALSE

Default-Wert: FALSE

Ist dieser Parameter auf TRUE, dann werden auch Aufnahmezahlen vor dem
Jahr 2000 auf

10 Stellen konvertiert.

Bei FALSE werden alle Aufnahmezahlen vor dem Jahr 2000 auf 8 Stellen
formatiert.

Ist das Logical AZ_FILL_JHDT19 nicht auf TRUE gesetzt oder gar nicht
gesetzt,

so wird der Default-Wert FALSE

Herangezogen.

Dieses Logical muß auch auf den Laborrechnern gesetzt werden!

\

Environment.autoset.AZ_FILL_JHDT19=TRUE

\

**SOSILP_NO_COPIES(file property,**mit **Environment.autoset,
ACT_BASE/MPA_KIS)**

Steuert auf welchen Druckerqueues die Anzahl der Kopien nicht ueber die
(SCT-)Druckfunktion gesteuert wird. In

diesem Fall, wird vom SCT immer genau **1** Ausdruck getriggert.

Die angegebene Druckerqueue darf Wildcards (?, \*) enthalten.

\

**PATH_CLSD** **(at least since rel_3.4, file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

gibt an wo das KHS_PARAM.INI liegt (DEFAULT \"\")

Beispiel:

PATH_CLSD=c:\\\\systema\\\\mpa\\\\lib

\

\

**\-\-\-\-\-- Ende SCT Umgebungsvariablen**

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**client.properties**

**SCT_LIS_ATTR_KONV_TBL** **(file property,** mit
**Environment.autoset,ACT_BASE/MPA_KIS)**

**Wird ab SCT V3.6 (mit Patch vom 17. September 2004) unterstützt!**

(Datentyp: String)

Dieses Property enthält jene Listen-Attribute , welche bei der Ausgabe
einer Liste in eine Datei, umgeschlüsselt und nicht entfernt (ist das
Default-Verhalten) werden sollen.

Die genaue Syntax für den Inhalt dieses Property\'s ist in der
**SCT-Datei \'sas_help:ls.doc\'** nachzulesen.

Siehe auch Dokument \'Anzeige von KIS/SCT-Dokumenten\' (^(32)^).

Für das \"1-Problem\" beim Kunden GESPAG ist das unten dargestellte 1.
Beispiel zu verwenden (sollte der Kunde auch mit den Zeichen 1/3 bzw.
3/4 Probleme haben, so muss eben das 2. Beispiel verwendet werden).

Im LKH WJ wurde festgestellt, dass statt den standardmäßigen \'##\' das
Zeichen \'\"\' (Hochkomma) verwendet wird, also nicht \'**##1/2**\'
sondern \'**\"1/2**\'.

[Beispiel:]{.underline}

Nr. 1: Environment.autoset.SCT_LIS_ATTR_KONV_TBL=##1/2:189;

Es wird das Attribut \'##1/2\' auf das Zeichen \'1\' bei der
Datei-Ausgabe umgeschlüsselt.

Nr. 2:
Environment.autoset.SCT_LIS_ATTR_KONV_TBL=##1/2:189;##1/4:188;##3/4:190;

Es werden die Attribute \'##1/2\', \'##1/4\', \'##3/4\' auf das Zeichen
\'1\' , \'1\', \'3\' bei der Datei-Ausgabe umgeschlüsselt.

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**Environment.autoset.bef_mail_dir (at least since rel_3.4, MPA_KIS,
nicht in Properties-Klasse übernehmen!)**

Im SCT-Kis werden zu mailende Befunde in ein bestimmtes Verzeichnis (lt.
der Umgebungsvariable \'bef_mail_dir\') abgestellt. Diese muss fuer die
MPA-Validierung richtig gesetzt werden - nur fuers PatientenService
notwendig!

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\-\--**-** SERVICE-LAUNCHER
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\

**JLAUNCH_CONFIG (at least since rel_3.4, file property, ACT_BASE)**

Name der Konfigurationsdatei des Service-Launcher

Beispiel:

JLAUNCH_CONFIG=c:\\\\mpa\\\\rel2.2\\\\java\\\\customer\\\\jlaunch.cfg

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**JLAUNCH_START_TRY (at least since rel_3.4, file property, ACT_BASE)**

Anzahl der Überprüfungen ob das Service registriert ist.

Beispiel:JLAUNCH_START_TRY=35

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**JLAUNCH_SHUTDOWN_TRY (at least since rel_3.4, file property,
ACT_BASE)**

Anzahl der Überprüfungen ob das Service nicht mehr registriert ist.

Beispiel:JLAUNCH_SHUTDOWN_TRY=10

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**gf.util.JLaunchStarter.jlaunchStartCommand (kiml@ACT_ICZ2) - since
rel_3.8 in the client.properties file**

Property which specifies the command-line String at starting of JLaunch
(since 3.8, from Todo ^(33)^22801)

**gf.util.JLaunchStarter.jlaunchStartCommand** =
%MPA_ROOT%/JLaunchOnlyNoEnv.bat

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\-\--**-** SERVICE-DISPATCHER
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\

**DISPATCH_CONFIG (at least since rel_3.4, file property, ACT_BASE,
Sascha Hofer)**

Name der Konfigurationsdatei des Service-Dispatcher

Beispiel:

DISPATCH_CONFIG=c:/mpa/rel3.0/java/customer/dispatch.cfg

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\-\--**-** CACHING
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\# Definition if User also updates Association on AssocService when
using UpdateAssocDialog

**UserUpdatesAssocCache**=false

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**associations (at least since rel_3.4, file property, ACT_BASE)**

Caching der Associations in den AssociationMgr-Instanzen

(falls unerwünscht, folgende Zeile auskommentieren)

Beispiel:

associations=cache

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

Association Local-Cache deaktivieren

**DO_NOT_USE_LOCAL_ASSOC_CACHE**=true **(at least since rel_3.4, file
property, ACT_BASE)**

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

~~**gf.omgr.OmgrRecordCacheMgr.oneCachePerLogObject**~~ Wurde mit Change
92594 für HEAD/rel_3.8 ersatzlos gestrichen.

~~Gibt an, ob ein Cache pro Logisches Objekt (z.B. Ressourcen) verwendet
werden soll, oder ob es parallele Caches geben kann.~~

~~(Default=false)~~

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\

\-\--**-** GENERAL FOUNDATIONS
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**Reconnect_Graphic_Icon** **(since rel_3.9, file property)**

With this Property you can change the icon which is displayed in
WaitForReconnectionDialog (this dialog is shown when connection to RMI
is lost for example).

It\'s not the icon in the title bar. It\'s the icon in the root panel
(next to the Messagetext)

When the property is not set, the default icon is used.

Default = /icons/default/logo/mpa_reconnect.gif

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**gf.util.TimerFactory.timerType** **(since rel_3.8.3, MPA_LINZ, Alex
Schmied, file property)**

With property gf.util.TimerFactory.timerType you can choose the
timer-implementation to use. by default (=RobustHighResolutionTimer) a
robust timer is used, which tries to use a timer measuring in
nanoseconds, but uses currentTimeMillis as fallback value when there
seems to be a problem with the nano time value (it\'s value is
negative).

So it\'s a combination of the 2 other possible implementations to choose
HighResolutionTimer \--\> uses nanoseconds to measure duration or
LowResolutionTimer \--\> uses currentTimeMillis from system to measure
duration.

It was necessary to offer the implementation variants, because
HighResolutionTimer may deliver wrong values. This may be true on some
multi processor, multi core or hyperthreading systems. Further we got
such (still unclear) bug situation like in Bug #38009. You would then
see logging like \"at.co.systema.gf.util.PostconditionException: return
value must be zero or positive\" in your logfile.

So there are 3 possible values for this property:
\"RobustHighResolutionTimer\" (=default), \"HighResolutionTimer\",
\"LowResolutionTimer\"

#gf.util.TimerFactory.timerType=RobustHighResolutionTimer

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**WindowIcon (since rel_3.6.b, file property, ACT_BASE, Siegfried
Kaltenbrunner)**

(bis rel_3.6 default=MPA / seit rel_3.8 default=MPA_2005)

Der Name jenes Icons, dass im Fenstertitel verwendet werden soll. Der
Name muss im repo registriert sein. Vorzugsweise sollte ein 16x16 Icon
verwendet werden. Sinnvolle Werte sind: MPA (wie bisher) MPA_2005
(MpaNeu) ANALYTICS_2005 (LaborNeu)

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**Password.NotifyXDaysBeforeExpiration (since rel_3.6, file property,
ACT_BASE)**

Gibt die Anzahl der Tage VOR dem Ablauf des Passwortes an. Ab diesem
Zeitpunkt wird das Programm bei jedem Einstieg darauf aufmerksam machen,
dass das Passwort in X Tagen ablaufen wird. Der User kann sein Passwort
sofort ändern (muss es aber nicht) Siehe auch customer.property:
Password.changeable

default=0 (Es wird nicht auf den Ablauf hingewiesen)

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**Password.changeable (since rel_3.6, file property, ACT_BASE)**

Legt fest, ob Passwort vom Benutzer geändert werden kann. Wenn false,
dann wird der User nie aufgefordert sein Passwort zu ändern. Es gibt
auch sonst keine Möglichkeit für den Benutzer sein Passwort zu ändern.
true bedeutet, dass das System bestimmen kann, dass der User sein
Passwort zu ändern hat (beim Einstieg). Weiters hat der User
Möglichkeiten sein Passwort zu ändern.

default=true

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**gf.actx.timerDelay** **(since rel_3.8, file property,
DOC/Kamleithner)**

Gibt an in welchem Zeitabstand (in ms) die Bearbeitung von Messages in
der Windows-Message-Queue neu angeworfen wird (Default = 100)

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**gf.actx.oleUnInitializeOnClose** **(since rel_3.6.b, file property,
DOC/Kamleithner)**

Gibt an, ob UnInitialize der COM-Library nur bei mpa-Ende (=true) oder
bei jedem close auf ActiveXContainer/ActiveXObject (=false) durchgeführt
wird.

(Default = true)

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**MemoryTools.minFreeMemoryInPercent (at least since rel_3.4, file
property, ACT_BASE)**

#Schwellwert fuer die GC-Ausloesung. Ist den freien Speicher unter
Schwellwert wird GC-Ausgeloest.

#Beispiel:Wenn JVM free heap unter 30%, dann GC\...

MemoryTools.minFreeMemoryInPercent=30

#Um GC abzuschalten das Property so setzen:

MemoryTools.minFreeMemoryInPercent=0

#Default ist 40%

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**MemoryTools.GCDelay (at least since rel_3.4, file property,
ACT_BASE)**

#Verzoegerung vor dem GC in ms

#Beispiel mit 1100 ms

MemoryTools.GCDelay=1100

#Default ist 1000 ms

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**informix.setExplainOn** **(at least since rel_3.4, file property,
ACT_BASE)**

(Datentyp: boolean)

Wenn auf \"true\", dann wird beim JDBC Verbindungsaufbau das Informix
Statement SET EXPLAIN ON

ausgeführt.

Die Auswirkung dieses Befehles ist, dass im HOME Verzeichnis des
Datenbank-Users auf dem Datenbank Server eine Datei sqexplain.out
angelegt wird, in dem alle vom Client ausgef. Statements samt
Optimizer/Index-Informationen protokolliert werden.

Kann sein, dass dies aus Berechtigungs-Gründnen nicht mit allen Usern
funktioniert - nicht weiterverfolgt, warum.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**informix.isolationLevel** **(since rel_3.2.1_b127, file property,
ACT_BASE)**

(Datentyp: String

Mögliche Werte:

COMMITTED

DIRTY

REPEATABLE

Default: nicht gesetzt.

Setzt auf jeder von MPA Java aufgebauten JDBC Connection zu einer
Informix-Datenbank den Isolationlevel auf den angegebenen Wert. Wenn der
Wert nicht gesetzt ist, dann wird nichts gemacht.

Ab 3.4.3 und in 3.2.1_b127: ^(34)^

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**(MPA_DOC/Kamleitner, ist noch nicht im Einsatz, since rel_3.4)**

**gf.jaas.Login**

(siehe auch Dokument 3248 ^(35)^)

Gibt Art des User-Login\'s an

Mögliche Werte:

PKCS - User-Login mit Chipkarte

PKCSPin - User-Login mit Chipkarte und PIN

UsernamePwd - User-Login mit Username/Passwort unter Verwendung von JAAS

\[else\] - Default; Login mit Username/Passwort wie bisher

\

Dieses Property wird ab ^(36)^*[Change 273853]{.underline}* in den
AuthenticationProperties (gf.actproperties im Repo) verwaltet und ist in
der File somit obsolet.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**gf.jaas.PKCSLoginModule.password.\<username\>**

(siehe auch Dokument 3248 ^(37)^)

Ermöglicht für den Chipcard-Login unter SAP die Angabe des Passwords des
SAP-Users

gf.jaas.PKCSLoginModule.password.\<username\>=\<password\> (\<username\>
durch Usernamen und \<password\> durch Password des SAP-Benutzers
ersetzen)

z.B.:

gf.jaas.PKCSLoginModule.password.MPA=systema

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**gf.assoc.MetaAssociation.autosortnumber (at least since rel_3.4, file
property, ACT_BASE)**

\# Einstellung um welchen Wert, beim Anlegen einer neuen Association,
die Sortiernummer automatisch erhöht wird

\# wird dieser Wert nicht gesetzt so ist der Standardwert 10

gf.assoc.MetaAssociation.autosortnumber=1

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**AssocSvr\_\[HOSTNAME\]=\[Servicename\] (at least since rel_3.4, file
properties, ACT_BASE)**

Association Service mit bestimmtem Name verwenden. **HOSTNAME** - Name
des Clients.

**Servicename** entspricht dem Reg.BIND-Name.

Beispiel:

AssocSvr_mpa67=XXX

starten von AssociationServer mit dem Name XXX

java at.co.systema.gf.assoc.AssociationServer -name XXX

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**rdi.optimizeSQLStatements (since rel_3.6.b, file property, ACT_BASE,
Sascha Hofer)**

(default: true)

Determines whether the optimizer should try to optimize SQL-statments or
not. See also documentation for optimizer hints: ^(38)^

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**(MPA_DOC/Gunda,** **wird ab rel_3.8 nicht mehr verwendet)**

**USE_BASE64_ENCODING**

Auswahl des beim speichern von Blobs in die Datenbank verwendete
Codierung-System.

Base64 oder Hexa-String. Diese Codierung wird für das speichern ins
Repository sowie

für das speichern von Word-Dokumenten verwendet.

Default-Wert = true

Beispiel für Hexa-Codierung:

USE_BASE64_ENCODING = false

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**client.properties**

**gf.rt.checkClientNameForServerAlias** **(since rel_3.8.3, file
property. GF / Alex)**

Default: false (don\'t check)

This property defines if the clientname (from environment) should be
checked if it\'s a clientname part of a cluster.

Every cluster node has it\'s own clientname, but in mpa as clientname we
want to work with the alias name, which is the same for all cluster
nodes. (and the same of our customer.property \"SERVER\")

This property must be activated in the client.properties of a clustered
server machine (It\'s no problem to activate it on every server machine
by default).

On client PCs this check is typically not necessary but may take long if
(as in TKL) the InetAddress can\'t be looked up.

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**client.properties**

**gf.util.ThreadDeadlockDetector.checkPeriod = 60000** **(since 3.8.3,
file property, kiml@ACT_QUERITY)**

\# default value to observe deadlocks is 60000 -\> means 60 s

\# property is NOT mandatory, if does NOT exists its default is used

\# check for deadlock is quite expensive operation, so do NOT set it to
very small values (let say smaller than 10 s)

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**client.properties**

**SCT_ALL_USER** **(at least since rel_3.4, file property, MPA_KIS)**

gibt an ob der Passwortcheck im Falle eines Systema-KIS / SCT Backends
deaktiviert ist (DEFAULT aktiv)

*since release 3.8.3 this property only works for batch-applications and
is ignored by all GUI-Applications (DWC, OWC, RepoBrowser, \...)*

Beispiel:

SCT_ALL_USER=False

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

not in referenz-customer.properties!

**gf.version.RequiredJREVersion (since: rel_3.4, file property,
ACT_BASE)**

Die Versionsnummer der Java Runtime Environment, die für die Ausführung
von MPA Anwendungen nötig ist. Wird bei jedem Start einer MPA Anwendung
geprüft. (Siehe auch: ^(39)^)

\

**Alex1: Don\'t think that this is correct:** ~~Michael2- Achtung: Wenn
eine neuere Java Version auf dem Rechner installiert ist als in MPA
verwendet wird, so hat man mit JStart Probleme! CreateProzess nimmt
leider dann die java.exe aus Root\\Windows\\System32\\ . Workaround:
java.exe dort unbenennen!~~

Sigi: Steht übrigens im systema.properties und wird ~~üblicherweise~~
vom Programmierer vorgegeben

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**\-\-\-\--DEPLOYMENT-INITIALIZER**
**\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--**

\

**RepoInit.initializeDeployments (starting with 3.x, file property,
ACT_BASE, Sascha Hofer) - siehe Todo** ^**(40)**^

\

List of Deployment- und Runtime- Initializers, that are invoked by
at.co.systema.RepoInit automatically.

(siehe dazu auch ^(41)^)

\

**Example:**

RepoInit.initializeDeployments=\\

at.co.systema.gf.customizer,\\

at.co.systema.gf.bere,\\

at.co.systema.gf.print,\\

at.co.systema.doc,\\

at.co.systema.doc.dicom,\\

at.co.systema.labor,\\

at.co.systema.ward,\\

at.co.systema.kue,\\

at.co.systema.ser,\\

at.co.systema.app,\\

at.co.systema.wfl,\\

at.co.systema.ord,\\

at.co.systema.cb

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**\-\-\-\--** **MAILING**
**\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--**

**(at least since rel_3.4, file properties, ACT_BASE)**

**mail.host = smtp.systema.co.at**

**mail.user = josef**

**mail.from = josef.schachinger@systema.co.at**

**mail.debug = true**

\

Diese Properties werden von Java Mail (Package javax.mail) verwendet.
Erforderlich für die Dokument-Verteilung per e-mail. Die genaue
Beschreibung dieser und weiterer Properties ist in der \"Java Mail API
Design Specification\" im \"Appendix A: Environment Properties\"
enthalten (http://joker/html/java/javamail-1.1.3/docs/JavaMail-1.1.pdf).

Systema-intern muß offensichtlich nur \"mail.host\" definiert werden.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**\-\-\-\--** **HL7**
**\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--**

\

\

**ANFOHL7_MSG_EMPF_FIELD** (ab rel_3.4.1 patch 61786) **(file property
since rel_3.4, MPA_DOC/Gunda)**

Diese Property dient um dem AnfoHL7CFT zu sagen aus welchem Feld der
ausführenden Leistungsstelle die bei einer Order hinterlegt ist und als
\"Adresse\" für den HL7Server dient. Defaultmässig wird \"matchcode\"
genommen. Im spezial Fall Novacom wird aber nor das Feld \"kz\"
gemapped.

Bsp.:

ANFOHL7_MSG_EMPF_FIELD=kz

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**HL7_PATH** **(file property since rel_3.1: HL7/Donner)**

Verzeichnis der Konfigurationdateien für den HL7Server

z.B:

HL7_PATH=c:\\\\mpa\\\\hl7\\\\

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**app.IGNORE_AVAILABILITIES_FOR_EXTERNAL** **(rel_3.8.3 only, file
property since rel_3.8, APP/Bimminger)**

Must be set to TRUE for and [only for]{.underline} HL7 server
application to guarantee pure MCC appointment controlling.

See Call 88296. **Property is NOT required for rel_3.10 and later**.
Note that file properties can be **set as java parameter**, what\'s
recommended for HL7Engine command line: java
-Dapp.IGNORE_AVAILABILITIES_FOR_EXTERNAL=true \<\...other java
parameters like -Xmx256M -Xincgc \...\> at.co.systema.gf.hl7.HL7Engine
\<mpa parameters like -xlog \... -user \...\>

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**\-\-\-\--** **DIAGNOSE- / LEISTUNGSERFASSUNG**
**\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--**

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**DL.diagdef.Vendor** **(since rel_3.11, file property)**

default value = SYSTEMA

setup data store environment for diagnosis definitions and catalogs.
Possible values are SAP and SYSTEMA

SAP: diagnosis definitions and catalogs will be read from SAP system

SYSTEMA: diagnosis definition and catalogs will be read from SYSTEMA db.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**DL.leistdef.Vendor** **(since rel_3.11, file property)**

default value = SYSTEMA

setup data store environment for procedure definitions and catalogs.
Possible values are SAP and SYSTEMA

SAP: procedure definitions and catalogs will be read from SAP system

SYSTEMA: procedure definition and catalogs will be read from SYSTEMA db.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**dl.KatalogCheckDate** **(since rel_3.8.3, file property)**

default not activated

Format: dd.mm.yyyy (d = day, m = month, y = year)

Date for Katalog validation. Has to be set to create hitlists for
Katalogs which are not valid at the moment.

E.g. someone wants to create a hitlist for the next year he has to set
this property to any date of the year the needed Katalog is valid.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**Environment.autoset.SCORING_STAMMDAT_PATH** **(at least since rel_3.4,
file property,** mit **Environment.autoset, MPA_KIS)**

Legt das Verzeichnis fest, in dem sich die LKF-Stammdaten befinden.
Dieser Eintrag ist nur erforderlich, wenn das KIS auf einer anderen
Plattform als Windows NT läuft. Andernfalls wird der Eintrag
SCORING-STAMMDAT-PATH aus der KHS_PARAM.INI herangezogen.

Beispiel:
Environment.autoset.SCORING_STAMMDAT_PATH=\\\\\\\\foxi\\\\scoring

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**Environment.autoset.NOHD_IGN_LKFPLAUS** **(at least since rel_3.4,
file property,** mit **Environment.autoset, MPA_KIS)**

Wenn eine fehlende Hauptdiagnose der einzige Fehler in den
Systema-Plausibilitätsprüfungen ist, liefern diese als Ergebnis Ok. Über
die Environment-Variable NOHD_IGN_LKFPLAUS kann nun festgelegt werden,
ob in diesem Fall die LKF-Plausibilitätsprüfungen ausfgerufen werden
sollen. Bei nicht gesetzter Environment-Variable werden sie aufgerufen;
sonst nicht

Beispiel: Environment.autoset.NOHD_IGN_LKFPLAUS=True

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\# Properties for diagnosese and procedures - TermTable **(since
rel_3.5, file property, DL/Hintersteiner, Tomschi)**

\# The term is feature for performant searching of diagnosese and
procedures.

\# this feature must be custoized for each catalog

\# Details see on SW 3924 ^(42)^

\# \-\-\-\--DiagnoseDefinition\-\-\-\--

\# Aufbau von Surrogaten der DiagnoseDefiniton

DiagnoseDefinition.Surrogat.Trennzeichen=/

DiagnoseDefinition.Surrogat.Katalog=1

DiagnoseDefinition.Surrogat.Code=2

\

DiagnoseDefinition.D_DEF_KATALOG=idDiagnoseKatalog

DiagnoseDefinition.D_DEF_CODE=id

DiagnoseDefinition.D_DEF_TERM=bezeichnungCase

DiagnoseDefinition.D_SYN_KATALOG=null

DiagnoseDefinition.D_SYN_CODE=id

DiagnoseDefinition.D_SYN_TERM=khs_syn_bez

\

\# DiagnoseKatalog

DiagnoseDefinition.D_KATALOG_ID=id

DiagnoseDefinition.Katalog.Surrogat.Trennzeichen=/

DiagnoseDefinition.Katalog.Surrogat.id=1

\

\# \-\-\-\--LeistungsDefinition\-\-\-\-\--

\# Aufbau von Surrogaten der LeistungsDefinition

LeistungsDefinition.Surrogat.Trennzeichen=/

LeistungsDefinition.Surrogat.Katalog=1

LeistungsDefinition.Surrogat.Code=2

\

\# \-\-\-\--HAUSLeistungsDefinition\-\-\-\-\--

\# Felder der LeistungsDefinition für: katalog, code und bezeichnung

\_HausLeistungsDefinition.HL_DEF_KATALOG=idLeistungsKatalog

\_HausLeistungsDefinition.HL_DEF_CODE=id

\_HausLeistungsDefinition.HL_DEF_TERM=bezeichnungCase

\# Felder der \...\_syn_bez für: katalog, code und bezeichung

\_HausLeistungsDefinition.HL_SYN_KATALOG=null

\_HausLeistungsDefinition.HL_SYN_CODE=id

\_HausLeistungsDefinition.HL_SYN_TERM=khs_syn_bez

\_HausLeistungsDefinition.HL_KATALOG_ID=id

\

\# \-\-\-\--MELLeistungsDefinition\-\-\-\-\--

\_MelLeistungsDefinition.ML_DEF_KATALOG=idLeistungsKatalog

\_MelLeistungsDefinition.ML_DEF_CODE=id

\_MelLeistungsDefinition.ML_DEF_TERM=bezeichnungCase

\# Felder der \...\_syn_bez für: katalog, code und bezeichung

\_MelLeistungsDefinition.ML_SYN_KATALOG=null

\_MelLeistungsDefinition.ML_SYN_CODE=id

\_MelLeistungsDefinition.ML_SYN_TERM=khs_syn_bez

\_MelLeistungsDefinition.ML_KATALOG_ID=id

\

\# LeistungsKatalog

LeistungsDefinition.HL_KATALOG_ID=id

LeistungsDefinition.Katalog.Surrogat.Trennzeichen=/

LeistungsDefinition.Katalog.Surrogat.id=1

LeistungsDefinition.Katalog.Surrogat.melhaus=2

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**DTermYearsGenerate** **ab Version 3.5 obsolet, MPA_KIS**

Das CustomerProperty **DTermYearsGenerate** legt fest, für welche Jahre
die jeweils gültigen Diagnosekataloge in die Tabelle DL_DTERM generiert
werden sollen. (Als Basis für die Ermittlung der Kataloge wird das Datum
des Übergabeparameter des Generierprogrammes verwendet)

0 \--\> befüllt DL_DTERM aus dem Katalog für das Datum laut
Übergabeparameter (bzw. aktuelle Jahr)

1 \--\> befüllt DL_DTERM aus dem Katalog für das Datum laut
Übergabeparameter (bzw. aktuelle Jahr) und das Vorjahr

(Vorsicht: Dabei kann es sich um einen Katalog handeln;

Falls dieser 2 od. mehrere Jahre gültig ist.)

usw.

\

Es ist günstig nicht zu viele Kataloge zu laden, da zu viele Datensätze
in der Tabelle DL_DTERM die Performance erst recht wieder beeinträchtigt
!

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**useTermTable** **ab Version 3.5 obsolet, MPA_KIS**

Steuert ob der AlphaBrowser für Diagnosen in der Begrifftabelle DL_DTERM
sucht

Beispiel: useTermTable=true

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**kodippath (MPA_KIS,** **nicht mehr in Verwendung)**

Pfad des Programmes Kodip für den Prototypen der Diagnose -
Leistungserfassung.

z.B.: kodippath d:\\\\kodip\\\\kodip.exe

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**RolleVerantwortlicherLeistungserbringer** **(obsolete, KIS/ only SAP/
Böhm,Tomschi)**

~~is an old property only for sap und it isn\'t used, only for
docmentation, now it is realized with tables from sap~~

~~RolleVerantwortlicherLeistungserbringer = ER~~

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**RolleWeitereLeistungserbringer** **(obsolete, KIS/ only SAP/
Böhm,Tomschi)**

~~is an old property only for sap und it isn\'t used, only for
docmentation, now it is realized with tables from sap~~

~~Im MPA wird (momentan) automatisch die Rolle für den
Hauptverantwortlichen und für weitere Leistungserbringer eingetragen.
Diese Rollen müssen im SAP als EXTROLETYP (Tabelle TN18R) angelegt
sein.~~

~~RolleWeitereLeistungserbringer=ZU~~

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**Entgeltsart** **(obsolete, KIS/ only SAP/ Böhm, Tomschi)**

~~is an old property only for sap und it isn\'t used, only for
docmentation, now it is realized with an association
\"LeistungsKatalogEntgeltartKatalogwerk \"~~

~~\# Die eingestellte Entgeltsart (defaultWert A3) bestimmt, wann eine
Leistung als Haus oder MEL Leistung erkannt wird.~~

~~\# Wenn in der aus SAP kommenden Leistung das Feld \"charge_type\" den
gleichen Wert wie das Entgeltsart hat,~~

~~\# wird die Leistung als MEL Leistung gewertet. Sonst ist sie eine
Hausleistung.~~

~~Entgeltsart=A3~~

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\

\-\--**-** AUFENTHALT / PATIENT
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**SearchEditor.DoCriteriaCheck** **(at least since rel_3.4, file
property, ACT_BASE, Siegfried Kaltenbrunner - g6: sollte nicht als
Globales Property, sondern als Teil der SearchEntrerDefinition
definierbar sein -\> Todo eintragen !)**

Wenn diese Eigenschaft gesetzt ist, werden in SearchBrowsern beim
Starten der Suche die Einschränkungskriterien keiner Prüfung unterzogen.

(-\>Bei der Aufenthalts/Patientensuche kann beliebig Eingeschränkt
werden)

Default ist true

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\-\--**-** DICOM / BILDVERARBEITUNG
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**jvisionAvailable** **(since rel_3.8.3, file property)**

boolean property with default value = True

Defines if the ShowJVisionForPatientCFT will try to start JVision or
not. If the property is set to false it will be asumed that no JVision
is installed on that client. Use Case: the same process can be executed
on a PC with JVision and on one w/o JVision, we don\'t want in such a
case that a error message is showed.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**DICOM_VENDOR** **(ab rel_3.8, MPA_DOC/Dorfmair)**

Definitiert welcher Dicom-Vendor im Einsatz ist. Durch Änderung des
Werts kann nicht zwischen Dicom-Vendoren gewechselt werden!

Wird für einige Applikationen (z.B. autom. erzeugen installierter
Plugins während RepoInit) benötigt.

Mögliche Werte: SIEMENS, TIANI, RADIN, PHILIPS

Falls **kein Dicom** verwendet wird, so muss der **Wert auskommentiert**
werden!

Beispiel:

DICOM_VENDOR=TIANI

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**doc.dicom.DicomStudyMgr.PatientID.\<pid\>** **(at least since rel_3.4,
file property, MPA_DOC/Dorfmair)**

ermöglicht die Umschlüsselung von MPA/KIS-Patient-IDs für DICOM-Query

z.B.

doc.dicom.DicomStudyMgr.PatientID.100016868=01234567899

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\-\--**-** MAILING & SMS VIA WORKFLOW
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**gf.mail.MobileNetProviderNames (at least since rel_3.4, file property,
ACT_BASE)**

Anzeigenamen der einzelnen Mobilfunkbetreiber (durch komma getrennt)

\

**gf.mail.MobileNetAreaCodes (at least since rel_3.4, file property,
ACT_BASE)**

Vorwahl der einzelnen Mobilfunkbetreiber (durch komma getrennt, müssen
in der Anzahl mit den ProviderNames übereinstimmen)

\

**gf.mail.MobileNetAddressPrefixes (at least since rel_3.4, file
property, ACT_BASE)**

Prefix für die Mailadresse eines Handies (durch komma getrennt, müssen
in der Anzahl mit den ProviderNames übereinstimmen)

\

**gf.mail.MobileNetProviderDomains (at least since rel_3.4, file
property, ACT_BASE)**

Domain an die eine Mail geschickt wird, wenn sie als SMS zu einem Handy
weitergeleited werden soll (durch komma getrennt, müssen in der Anzahl
mit den ProviderNames übereinstimmen)

\

**gf.mail.MobileNetAlphaNumerics (at least since rel_3.4, file property,
ACT_BASE)**

Gibt an ob in die betreffende Netze alphanumerische SMS gesendet werden
können (durch komma getrennt, müssen in der Anzahl mit den ProviderNames
übereinstimmen)

\

**gf.mail.MaximumAlphaNumericChars (at least since rel_3.4, file
property, ACT_BASE)**

Maximale Länge einer SMS; DefaultValue: 160

\

**gf.mail.MaximumNumericChars (at least since rel_3.4, file property,
ACT_BASE)**

Maximale Länge einer Nachricht an einen Pager; DefaultValue: 20

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\-\--**-** EXPRESSIONS
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**gf.expr.ValidationExprTest (at least since rel_3.4, file property,
ACT_BASE)**

Bei ValidationExpressions das Caching aus- u. zusätzliche
Protokollierung einschalten.

Beispiel:

gf.expr.ValidationExprTest=true

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\-\--**-**TELEFON
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**Environment.autoset.PAT_VERL_KLAPPE_UPDT=true**

wird vom SCT-KIS benötigt, damit bei einem update der Verlegung auch die
Telefonnummer

im Patientenstamm upgedated wird.

Kann und soll immer auf true gesetzt werden

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**Telefon.tvsInUse** **(obsolete, Tel, Tomschi)**

wurde nie im Programm verwendet!

\# Boolean, defaultwert = false

\# Gibt an ob die TVS-Tabellen befüllt werden.

#Telefon.tvsInUse

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**Telefon.menueItem** **(at least since rel_3.4, file property,
at.co.systema.tel, MPA_KIS, )**

Gibt an ob und welche Menuepunkte des Telefons im Kontextmenü des
Aufenthaltes vorhanden sind

mögliche Werte: standard anmelden abmelden

**-\> wird ab rel_3.8 nicht mehr unterstützt**

Dies kann über das Menue-Customizing und Berechtigungen für Aktionen
besser gelöst werden.

Es gibt keine unterschiedlichen Action für anmelden, abmelden oder
standard.

Da sich die Maske die die alle Funktionen beinhaltet bewährt hat.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\

\-\--**-** APPLICATION SERVER
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**gf.ejb.pingIntervalSecs** **(since 3.8, file property, GF/Jachs)**

Defines the interval in seconds for pinging EJBs. This is required for
the EJB reconnection (GenericReader, Workflow, etc.). A value of -1
disables the ping feature. A value of 0 and greater enables it where 0
leads to continuous pings.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**gf.ejb.ApplicationServer.Provider** **(since rel_3.6, file property,
ACT_BASE)**

Gibt den Hersteller des Application Server an.

Derzeit stehen zur Auswahl (In Klammer stehen mögliche Schreibweisen):

JBoss: (JBoss, Jboss, jboss)

Bea Weblogic: (Bea, bea)

Sun Referenz Implementierung: (Sun, sun)

Beispiele:

gf.ejb.ApplicationServer.Provider=JBoss

gf.ejb.ApplicationServer.Provider=Bea

gf.ejb.ApplicationServer.Provider=Sun

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**gf.ejb.ApplicationServer.Port (since rel_3.6, file property, ACT_BASE,
Martin Jachs)**

\# NamingService Port Nr. des Application Servers

\# Portnummer-Konventionen siehe Lotus Notes Doku Nr. 3793

\# Wird nur mehr fuer nicht JBoss AS benoetigt.

gf.ejb.ApplicationServer.Port=10001

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**gf.ejb.useApplicationServerForDataAccess (since rel_3.6.b, file
property, ACT_BASE, Sascha Hofer)**

(default: true)

Determines whether the application server should be used for
reading/writing Object from/to the database.

possible values:

true: the application server will be used for reading and writing

false: the application server won\'t be used for reading and writing
(but access to other services inside the application server are still
accessible (e.g. PatRead))

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**gf.ejb.useApplicationServer** **(rel_3.5.1, file property, ACT_BASE)**

Globale Einstellmöglichkeit, ob Application Server verwendet werden
soll.

true: Application Server wird verwendet (default, auch falls Property
auskommentiert wird)

false: Application Server wird nicht verwendet

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**gf.ejb.ApplicationServer.Host** **(since rel_3.6, file property,
ACT_BASE)**

Rechnername (Host) auf dem der Application Server läuft.

Beispiele:

gf.ejb.ApplicationServer.Host=mpa9890

gf.ejb.ApplicationServer.Host=mpa9890.systema.co.at

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**jboss.server.configname (since rel_3.8, file property, ACT_BASE,
Martin Jachs)**

\# Name der zu verwendenden JBoss Konfiguration. Wird benoetigt, um z.B.
Naming

\# Ports zu ermitteln.

jboss.server.configname=mpa-default

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**jboss.server.instanceno (rel_3.8, file property, ACT_BASE, Martin
Jachs)**

\# Nummer der zu verwendenden JBoss Konfiguration. Wird benoetigt, um
z.B.

\# Naming Ports zu ermitteln.

jboss.server.instanceno=0

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**jboss.server.jms.persistence** **(since 3.8, file property, GF/Jachs,
SWDEV** ^**(43)**^*[Documentation 4525: Configuration on
JBoss]{.underline}***)**

(default value = hypersonic)

\# Name des zu verwendenden JMS Persistenz Providers.

\# Wird nur verwendet wenn jboss.server.jms.provider == jboss

\# Moegliche Werte: file, hypersonic, informix, mysql, null, oracle

jboss.server.jms.persistence=hypersonic

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**jboss.JMXConsole.port** (**rel_3.6, file property, ACT_BASE, Martin
Jachs**)

**obsolete since rel_3.8**

Port auf dem TomCat im Rahmen des JBoss auf der JMX-Console horcht (z.B.
36102)

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**jboss.WebService.port** (**rel_3.6, file property, ACT_BASE, Martin
Jachs)**

**obsolete since rel_3.8**

Port auf dem TomCat im Rahmen des JBoss als WebService horcht (z.B.
36104)

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**gf.ejb.ApplicationServer.RMIPort** (**rel_3.6, file property,
ACT_BASE, Martin Jachs)**

**obsolete since rel_3.8**

RMI-Port Nr. des NamingService vom Application Server (z.B. 36103)

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**jboss.mq.uil.port (rel_3.6, file property, ACT_BASE)**

**obsolete since rel_3.8**

Port the JBoss JMS provider should listen to for connection requests.
This property (as many other JBoss properties) only exists to avoid port
collisions when running several services from the same release on one
machine and to be able to simplify firewall configuration. This property
is used in the file \<JBoss config dir\>/deploy/jms/uil2-service.xml.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**gf.ejb.ApplicationServer.JRMPPort** **(rel_3.6, file property,
ACT_BASE, Martin Jachs)**

**obsolete since rel_3.8**

JRMPInvoker-Port Nr. vom ApplicationServer (z.B. 36105)

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\-\--**-**TIMESTRIP
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**TimeStrip** (ab rel_3.6) **(alle FILE, MPA_DOC/not used)**

**tstrip.usecustomDefinedTimeSpan**

Bestimmt ob ein benutzerdefinierter Zeitraum im TimeStrip verwendet
wird:

-   true TimeStrip zeigt die customDefinedTimeSpan an.

-   Diese wird durch *tstrip.customDefinedTimeSpanStart* und
    *tstrip.customDefinedTimeSpanEnd* festgelegt.

-   false (default) TimeStrip verwendet den letzten Aufenthalt.

Bemerkung: Wenn der TimeStrip gestartet wird, stellt der *Navigator*
einen Zeitstreifen von Geburt des Patienten bis Jetzt dar. Innerhalb
dieser Zeit ist eine Zeitspanne ausgewählt: der letzte Aufenthalt oder
eine benutzerdefinierte Zeitspanne. Diese Zeitspanne stellt der
*ItemViewer* dar: mit allen in diese Zeitspanne fallenden Objekten.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**tstrip.customDefinedTimeSpanStart**

Beginn der benutzerdefinierten Zeitspanne. Ob die Benutzerdefinierte
Zeitspanne verwendet wird hängt von *tstrip.usecustomDefinedTimeSpan*
ab.

-   Datum; muss kleiner als *tstrip.customDefinedTimeSpanEnd* sein

-   z.B.: 1.1.2000 (default)

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**tstrip.customDefinedTimeSpanEnd**

Ende der benutzerdefinierten Zeitspanne. Ob die Benutzerdefinierte
Zeitspanne verwendet wird hängt von

*tstrip.usecustomDefinedTimeSpan* ab.

-   Datum; muss größer als *tstrip.customDefinedTimeSpanEnd* sein

-   z.B.: 2.2.2003 (default)

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**tstrip.maximumDaysShownAfterNow**

Bestimmt die Anzahl der maximal sichtbaren Tage nach \"Jetzt\". Der
TimeStrip zeigt Objekte im folgenden Zeitraum an:

(Geburtstag des ausgewählten Patienten) bis (Jetzt +
*tstrip.maximumDaysShownAfterNow* Tage).

Das bedeutet: Es kann nur innerhalb dieses Zeitraumes navigiert werden.

Zahl größer gleich Null

z.B.: 7 (default)

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**tstrip.navigatorClass**

Bestimmt, welche Klasse der TimeStrip als *Navigator* verwendet.

-   gültiger Klassenname vollständig qualifiziert

-   z.B.: at.co.systema.tstrip.proposal.navigators.RubberBandNavigator
    (default)

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**tstrip.itemViewerClass**

Bestimmt, welche Klasse der TimeStrip als *ItemViewer*verwendet.

-   gültiger Klassenname vollständig qualifiziert

-   z.B.: at.co.systema.tstrip.proposal.navigators.LabeledItemViewer
    (default)

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**tstrip.scrollBarNavigatorClass**

Bestimmt, welche Klasse der TimeStrip als *ScrollBarNavigator*verwendet.

-   gültiger Klassenname vollständig qualifiziert

-   z.B.: at.co.systema.tstrip.proposal.navigators.ScrollBarNavigator
    (default)

-   

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**tstrip.previeverClass**

Bestimmt, welche Klasse der TimeStrip als *Previewer*verwendet.

-   gültiger Klassenname vollständig qualifiziert

-   z.B.: at.co.systema.tstrip.proposal.navigators.SimplePreviewer
    (default)

-   

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**tstrip.sideBarClass**

Bestimmt, welche Klasse der TimeStrip als *SideBar*verwendet.

-   gültiger Klassenname vollständig qualifiziert

-   z.B.: at.co.systema.tstrip.proposal.navigators.FormLayoutSideBar
    (default

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\

\-\--**\-\-\-\-\-\-\-\--** MONITORING (SNMP)
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**gf.mbean.mbeanCallTimeout** **(since 3.10, file property,
wajtr@ACT_ICZ2)**

When operating on mbeans (getting or setting attributes, or calling
operations) there is a possibility

that the call to mbean will never end. This can be harmful, so this
property is here to limit

time of such call - in milliseconds. If duration of the call exceeds
this time limit an error is generated,

but application can continue to work unblocked. Default is 20000.

example: gf.mbean.mbeanCallTimeout = 20000

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**gf.mbean.statusOrDescriptionTimeout** **(since 3.10, file property,
wajtr@ACT_ICZ2)**

This property does the same thing as \"gf.mbean.mbeanCallTimeout\" but
this one limits duration of

calls of getStatus and getDescription mbean operations. In milliseconds,
default is 5000.

example: gf.mbean.statusOrDescriptionTimeout = 5000

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**gf.monitor.ReadOnlyMode (tmuller@ACT_ICZ2) -** **since rel_3.9 in the
customer.properties file**

This property sets read only or standard mode for buttons on ACTMonitor
which adjust ACTServer services.

Read only mode means that the buttons which could adjust ACTServer\'s
services are disabled.

Default value is false and it means that all the buttons are enabled.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**gf.monitor.connectionsCriticalRatio** **(wajtr@QUERITY) -** **since
rel_3.10 in the customer.properties file**

This is a property of ACTMonitor. Sets the ratio which decides when
ManagedConnectionPool mbean goes into WARN state.

A relationship between max count of connections and connections in pool
is measured

It has to be a value between 0 and 1.

example: gf.monitor.connectionsCriticalRatio = 0.9

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**gf.monitor.ClientServerOutputAreaEntriesCount** **(tmuller@ACT_ICZ2) -
since rel_3.8.3 in the customer.properties file**

This property sets count of entries which could be writen into
client/server output area. Default value is 12 and minimal is 9.

Lesser values are NOT accetable, because usually 1 \"information block\"
in output area consist of 3 entries:

1\. client output

2\. server output

3\. client output (if Automatical refresh is enabled)

And therefore is minimal value set to 9.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**client.properties**

**gf.logging.UseChainsawForLogViewing** **(since 3.8.3, file property,
znovotny@ACT_ICZ2)**

\# This variable determines whether the default log file viewer

\# should be Chainsaw or the LogViewer used previously

\# Default value is \'false\', which means that Chainsaw will NOT be
used

gf.logging.UseChainsawForLogViewing = false

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**client.properties**

**\# gf.logging.ChainsawParsingPattern (since 3.8, file property,
znovotny@ACT_ICZ2)**

\# This variable specifies the default configuration pattern Chainsaw
log viewer

\# will use to parse log files of services. It is ABSOLUTELY NECESSARY

\# to update this property whenever the layout configuration pattern of

\# of loggers changes, otherwise Chainsaw will be unable to parse the
files

\# correctly and will issue errors and display the data incorrectly.

\# see details in help of Chainsaw or
http://logging.apache.org/log4j/docs/chainsaw.html

gf.logging.ChainsawParsingPattern = TIMESTAMP LEVEL THREAD\] LOGGER :
MESSAGE

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**client.properties**

**gf.logging.ChainsawParsingPattern.SERVICE_NAME (since 3.8, file
property, bwajtr@ACT_ICZ2)**

#This variable is NON-mandatory. Because services can have different log
file formats

#it is necessary to have posibility to override default configuration
pattern for Chainsaw log viewer (property
gf.logging.ChainsawParsingPattern).

#example:

\# gf.logging.ChainsawParsingPattern = TIMESTAMP LEVEL THREAD\] LOGGER :
MESSAGE

\# gf.logging.ChainsawParsingPattern.RMIRegistry = TIMESTAMP LEVEL
LOGGER : MESSAGE

\# in this example a special parsing pattern will be used for
RMIRegistry service and default pattern for all others.

\# The SERVICE_NAME string is can be obtained from ACTMonitor - it is
the name of the service in ACTMonitor services tree without

\# a client name. For example:

\# in ACTMonitor tree: RepoServer_BRETA -\> property:
gf.logging.ChainsawParsingPattern.RepoServer

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**client.properties**

**gf.logging.ChainsawTimeStampFormat (since 3.8, file property,
bwajtr@ACT_ICZ2)**

\# This variable is mandatory if gf.logging.UseChainsawForLogViewing
property is set to true.

\# This variable specifies the default timestamp format for Chainsaw log
viewer

\# will use to parse log files of services. It is ABSOLUTELY NECESSARY

\# to update this property whenever the layout configuration pattern of

\# of loggers changes, otherwise Chainsaw will be unable to parse the
files

\# correctly and will issue errors and display the data incorrectly.

\# see details in help of Chainsaw or
http://logging.apache.org/log4j/docs/chainsaw.html

gf.logging.ChainsawTimeStampFormat=HH:mm:ss,SSS

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**client.properties**

**gf.logging.ChainsawTimeStampFormat.SERVICE_NAME (since 3.8, file
property, bwajtr@ACT_ICZ2)**

#This variable is NON-mandatory. Because services can have different log
file formats and thus different format of log timestamp

#it is necessary to have posibility to override default timestamp
pattern for Chainsaw log viewer (property
gf.logging.ChainsawTimeStampFormat).

#example:

\# gf.logging.ChainsawTimeStampFormat= HH:mm:ss,SSS

\# gf.logging.ChainsawTimeStampFormat.RMIRegistry = DD:MM:YYYY
HH:mm:ss,SSS

\# in this example a special timestamp parsing pattern will be used for
RMIRegistry service and default pattern for all others.

\# The SERVICE_NAME string is can be obtained from ACTMonitor - it is
the name of the service in ACTMonitor services tree without

\# a client name. For example:

\# in ACTMonitor tree: RepoServer_BRETA -\> property:
gf.logging.ChainsawTimeStampFormat.RepoServer

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**client.properties**

**gf.snmp.descriptionFormat (wajtr@ACT_ICZ2) - since rel_3.8.3, file
property**

All returned service descriptions are formatted by this format-string.
It consists from simple text

and property definitions, which follows this pattern: \${PROPERTY_NAME}

Where PROPERTY_NAME must be one of customer.properties properties or one
of service related properties:

\${snmp.state.name} - service status name (\"WARN\", \"OK\" etc.)

\${snmp.state.id} - service status id (1,2,3\...)

\${snmp.state.description} - description of the service

If you want to use \"\${\" as normal text use \"\\\${\".

Example: \${customer} at \${SERVER}: \${snmp.state.name} -
\${snmp.state.description}

Note: If this gf.snmp.descriptionFormat property is missing, simple
default format is used.

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**gf.snmp.SNMPAdaptor.port=161 (kiml@ACT_ICZ2) - since rel_3.8.3, file
property,**

**from 3.11.2 obsolete**

SNMP adaptor is registered in JLaunch and use this port for comunication
with SNMP tool (CA Unicenter, Tivoli, Open View, Nagios, \...)

Default value is 161. (from 3.11.2 SNMP support is provided by SNMP
Agent running at port 8001, that can be registered as subagent

to Windows SNMP agent running at port 161 - see also ^(44)^)

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**client.properties**

**gf.util.JLaunch.EnableSNMPSupport (Znovotny@ACT_ICZ2) - since rel_3.8
in the customer.properties file**

This property enables/disables the SNMP support in JLaunch.

The default value is \'true\', which means that SNMP service MBeans will
be registered with JLaunch, \'false\' disables this registration.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**client.properties**

**gf.monitor.MonitoringAutomaticRefresh (kiml@ACT_ICZ2) - since rel_3.8
in the customer.properties file**

This property enables/disables automatic refresh of ACTMonitor (e.g.
after \"*Force OK status*\" button click) for more user friendly
environment.

gf.monitor.MonitoringAutomaticRefresh=true set up this function.

gf.monitor.MonitoringAutomaticRefresh=false disable this function.

User can set this variable in ACTMonitor Option menu.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**client.properties**

**gf.monitor.MonitoringUpdatePeriodically (kiml@ACT_ICZ2) - since
rel_3.8 in the customer.properties file**

This property sets the length (in seconds) of the interval between two
automatic updates in ACTMonitor.

Minimal value is 30 s. You can turn off (disable) automatic updates by
setting this value to 0.

gf.monitor.MonitoringUpdatePeriodically = 300

User can enable/disable this variable in ACTMonitor\'s Option menu.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

~~**gf.util.jlaunch.failIfThereIsMoreThanOneJLaunchRegistered
(verha@ACT_ICZ2) - since rel_3.10 in the customer.properties file**~~
**-** **removed**

~~This property disallows to register more than one JLaunch on the
server.~~

~~Default value is true.~~

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

~~**cz.i.EnableNServerSupport (verha@ACT_ICZ2) - since rel_3.10, file
property**~~ **-** **renamed**

**gf.monitor.EnableNServerSupport (verha@QUERITY) - since rel_3.11 file
property**

This property allows to monitor more than one server (asociated to
JLaunch process) in ACTMonitor.

It means that allows to register more than one JLaunch and to display
JLaunch node

as a server node in ACTMonitor. It has to be enabled on both client and
server.

This property replaces old
gf.util.jlaunch.failIfThereIsMoreThanOneJLaunchRegistered property.

Default is false.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

~~**cz.i.monitor.JLaunchNodeClass (verha@ACT_ICZ2) - since rel_3.10,
file property**~~ **-** **removed**

~~**cz.i.monitor.ServerNodeClass**~~

~~**cz.i.monitor.JLaunchSummaryClass**~~

~~These properties store class names from cz.i.monitor plugin that will
be used in gf.monitor when NServerSupport is enabled.~~

~~They are called by reflection mechanism.~~

~~Default values:~~

~~cz.i.monitor.JLaunchNodeClass =
cz.i.monitor.view.JLaunchServerMetaTreeNode~~

~~cz.i.monitor.ServerNodeClass =
cz.i.monitor.view.ACTServerMetaTreeNode~~

~~cz.i.monitor.JLaunchSummaryClass =
cz.i.monitor.view.JLaunchServicesSummary~~

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\-\--**-** REPORTING
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**gf.report.ireport.fgnFieldsThreshold** **(since 3.9, file property,
verha@ACT_ICZ2)**

(Default value = 250)

Threshold value of count of log.object\'s foreign fields. If this value
is exceeded generating of all foreign fields may be critical.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\-\--**-** MemoryWarningSystem
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**MemoryWarningSystem.enabled** **(since 3.9, file property, georg1)**

(Default value = true)

This property is used by the memory warning system due to the fact that
MPA is running on low heap memory.

It starts the memory warning system when it is setted to true.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**MemoryWarningSystem.MemoryTresholdRangeInitInPercentage**
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**sap.FieldsForVerlegung \--\> ab Rel. 3.5**
***pat.FieldsForVerlegung*** **(gilt dann auch für systema KIS)**
**(at.co.systema.pat, MPA_KIS, ab rel_3.8 in Repo unter
PatProperties.fieldsForTransfer )**

\# Liste jener Felder, deren Änderung das Abstellen einer neuen
Verlegung verursacht. Die Änderung aller anderen Felder bewirkt nur ein
Update der

\# letzten Verlegung. Fehlt dieser Eintrag, löst die Änderung jedes
Feldes eine neue Verlegung aus. Die Einträge in der Liste müssen durch
Beistrich

\# getrennt werden.

\#

\# Folgende Felder werden berücksichtigt:

\# idKrankenhaus

\# idFach (nur systema KIS)

\# idFachlicheOE (Abteilung)

\# idPflegerischeOE (Station in SAP IS_H; Leistungsstelle im systema
KIS)

\# idZimmer

\# idBett

\# idKlasse

\# idPflegeart

\# idAufenthaltsart

\# idBewegungsArt

\#

\# [Beispiel]{.underline}:

\#
sap.FieldsForVerlegung=idKrankenhaus,idFachlicheOE,idPflegerischeOE,idKlasse,idPflegeart,idAufenthaltsart,idBewegungsArt

\#
pat.FieldsForVerlegung=idKrankenhaus,idFach,idPflegerischeOE,idZimmer,idBett,idKlasse

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**pat.MovementActionWhenNoBed** **(at.co.systema.pat, MPA_KIS, ab
rel_3.8 in Repo unter PatProperties.movementActionWhenNoBed)**

Legt fest, was bei einer Verlegung passieren soll, wenn der Patient zum
Zeitpunkt der Verlegung in keinem Bett liegt

0 =UPDATE_MOVEMENT\... wie bisher (Aktualisierung der letzten Verlegung)

1 =ASK_FOR_NEW_MOVEMENT\... Abfrage, ob eine neue Verlegung erzeugt
werden soll

2 =CREATE_NEW_MOVEMENT\... Abstellen einer neuen Verlegung (ohne
Rückfrage)

3 =ASK_FOR_NEW_MOVEMENT_IF_ADMISSION\... Abfrage, ob neue Verlegung,
wenn aktuelle Verlegung die Aufnahmeverlegung ist

4 =CREATE_NEW_MOVEMENT_IF_ADMISSION\... Abstellen einer neuen Verlegung,
wenn die aktuelle Verlegung die Aufnahmeverlegung ist (sonst
Aktualisierung der Verlegung)

5 =CREATE_NEW_MOVEMENT_IF_BM_NOT_ACTIVE\... Abstellen einer neuen
Verlegung, wenn Bettenmanagement nicht aktiv ist (sonst Aktualisierung
der Verlegung)

(Konstanten siehe BMVerlegungsHelper)

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**pollingEventForPatientUpdateEvent** **(since rel_3.11,
PatProperties)**

DefaultValue = empty list

This property could reduce update-events in the pollingservice.

Each event (A01, A03, A08, \....) causes an update-event for the cases.

If also a update event for patient is required, the event has to be
added to this list.

If the list is empty always a event for patients is triggered (as it was
before this property comes)

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**RECOM.Grips.Program=D:\\\\recom\\\\grips32\\\\grips.exe** **(ab
rel_3.8 in Repo unter PatProperties.RECOMGripsProgram)**

**RECOM.Grips.User=mpa-grips** **-\> obsolet, jetzt angemeldeter User**

**RECOM.Grips.Station=INT** **-\> obsolet, jetzt plegerische Station
laut Patientendaten**

Parameter für den Aufruf der RECOM-Grips-Pflegedokumentation

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**resendBedEventsOnTransferEvents(since rel_3.8.3, repo property
PatProperties)**

(default=false)

Definiert, ob das PollingService bei VerlegungsEvents (A02) die Update
Events für alle beteiligten Betten erneut versendet.

true \.... Das PollingService versendet die UpdateEvents erneut -
sinnvoll wenn es zu häufigen Verbindungsproblemen der Clients zum JMS
Service kommt

false \... Das PollingService versendet keine UpdateEvents für die
Betten

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\

**gf.actproperties.PatReadProperties**

\

\

**PatReadEJB.serviceStarter.applicationArguments (since rel_3.6.b, file
property, ACT_BASE, Sascha Hofer, Alex Schmied)**

**since rel_3.8 located in Repository:
PatReadProperties.applicationArguments**

(default: no application arguments)

Additional arguments for the PatReadService. For a description of those
see ^(45)^. **Attention: the parameter \"-bindName\" is not allowed!!**

Example:

PatReadEJB.serviceStarter.applicationArgument=-user mpa_qs mpa_qs -log
action

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**clientRetryCount**

**PatReadEJBClient.maxRetryCount (since rel_3.6.b, file property,
ACT_BASE, Sascha Hofer, Alex Schmied)**

**since rel_3.8 located in Repository:
PatReadProperties.clientRetryCount**

maximum number of retries when calling the PatReadService from a client
if a method failed to be invoked

(default: 5)

min = 1 retry

max = 2.147.483.647 retries

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**javaVMArguments**

**PatReadEJB.serviceStarter.javaArguments (since rel_3.6.b, file
property, ACT_BASE, Sascha Hofer, Alex Schmied)**

**since rel_3.8 located in Repository:
PatReadProperties.javaVMArguments**

(default: no java arguments)

Additional arguments for starting the java virtual machine. For a
description of those see sun documentation of java.exe.

Example:

PatReadEJB.serviceStarter.javaArguments=-Xms10m -Xmx256m

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**PatReadEJB.serviceStarter.maxShutdownTime (since rel_3.6.b, file
property, ACT_BASE, Sascha Hofer, Alex Schmied)**

**since rel_3.8 located in Repository:
PatReadProperties.maxShutdownTime**

(default: 20 seconds)

min = 1 second

max = 7.200 seconds = 2 hours

Maximum shutdown time for the PatReadService (in seconds) which has been
started from JBoss. If this time exceeds the service will be killed.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**PatReadEJB.serviceStarter.maxStartTime (since rel_3.6.b, file
property, ACT_BASE, Sascha Hofer, Alex Schmied)**

**since rel_3.8 located in repository: PatReadProperties.maxStartTime**

(default: 30 seconds)

min = 1 second

max = 7.200 seconds = 2 hours

Maximum start time for the PatRead-service (in seconds) which will be
started from JBoss. If this time exceeds the service will be killed.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**serverRetryCount**

**PatReadEJB.retryCount (since rel_3.6.b, file property, ACT_BASE,
Sascha Hofer, Alex Schmied)**

**since rel_3.8 located in Repository:
PatReadProperties.serverRetryCount**

Applicationserverseitige, maximale Anzahl der Wiederholungsversuche für
fehlerhafte Serviceaufrufe. Beschreibt die maximale Anzahl von
Wiederholungen die vom Applicationserver (z.B. JBoss) aus gemacht werden
wenn beim Serviceaufruf Fehler auftreten (z.B. Netzwerkprobleme).

Zulässige Werte:

null Der Defaultwert wird verwendet (derzeit 5 Wiederholungen)

1 - 2.147.483.647 Wiederholungen der eingestellte Wert wird verwendet

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**PatReadEJB.serviceStarter.serviceTestInterval (since rel_3.6.b, file
property, ACT_BASE, Sascha Hofer, Alex Schmied)**

**since rel_3.8 located in Repository:
PatReadProperties.serviceTestInterval**

(default: 5 seconds)

min = 1 second

max = 86.400 seconds = 1 day

Interval (in seconds) in which the started PatReadService will be tested
periodically. If a service cannot be reached this service will be killed
and restarted.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\

**gf.actproperties.ProcessBuilderProperties**

\

**wfl.allowSavingStartStopProcess (**ab 3.5 Change ^(46)^**)** **(liegt
ab rel_3.8 im Repository unter ProcessBuilderProperties, WFL/Trummer)**

Ermöglicht das Abspeichern von Prozessen die nur aus einem Start + Stop
Task bestehen (ClientProzesse).

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**visioDocumentVersion**

Legt fest unter welcher Visio Version eine Prozesszeichnung gespeichert
wird.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**gf.actx.visio.VisioPropertyDisplayConnectionNames ab 3.6.b** **(liegt
ab rel_3.8 im Repository ProcessBuilderProperties als
visioPropertyDisplayConnectionNames WFL/Trummer)**

Gibt an ob die Namen der Verbindungen zwischen Tasks angezeigt werden
oder nicht (default == true)

Beispiel: gf.actx.visio.VisioPropertyDisplayConnectionNames=true

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**gf.actx.visio.VisioPropertyDlgState ab 3.6.b** **(liegt ab rel_3.8 im
Repository ProcessBuilderProperties als visioPropertyDlgState
WFL/Trummer)**

Gibt an, welche Eigenschaften der Dialog zum Editieren der Visio Shapes,
bzw. die Eigenschaften der zugeordneten Prozesselemente, haben kann
(default == 1)

Derzeit:

gf.actx.visio.VisioPropertyDlgState=0 // normaler Dialog

gf.actx.visio.VisioPropertyDlgState=1 // Dialog wird im \"top most\"
Status angezeigt und ist daher immer sichtbar

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**gf.actx.visio.VisioTemplate ab 3.6.b** **(liegt ab rel_3.8 im
Repository ProcessBuilderProperties als visioTemplatesPath
WFL/Trummer)**

Gibt den Ordner und Namen der Visio-Dokumentvorlage an, die zum Zeichnen
eines Prozesses benötigt wird.

Beispiel:
gf.actx.visio.VisioTemplate=c:\\\\mpa\\\\head\\\\lib\\\\ProzessZeichnung.vst

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\

\

**gf.actproperties.ProgressNotesProperties**

\

\

**editorDividerLocation(since rel_3.8.6, repo property
ProgressNotesProperties)**

(default=140)

Location of divider between tablebrowser and editor.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**heightOfCalendarDialog(since rel_3.8.6, repo property
ProgressNotesProperties)**

(default=250)

Height of calendardialog that will be shown creating new
progressnotes-objects.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**isDividerFixed(since rel_3.8.6, repo property
ProgressNotesProperties)**

(default=true)

Defines if divider between tablebrowser and editor is fixed

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**numberOfMaximumSelectableDays(since rel_3.8.6, repo property
ProgressNotesProperties)**

(default=31)

Number of maximum selectable days (within optiondialog(calendar))when
new dailyprogressnotes will be created.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**stateEditorDefaultFont(since rel_3.8.6, repo property
ProgressNotesProperties)**

(default=\"Courier New\", Font.*PLAIN*, 12)

Default font for state-editor.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**stateEditorHeaderColorForNewBlocks(since rel_3.8.6, repo property
ProgressNotesProperties)**

(default=Green)

Backgroundcolor for the headertext of readonly blocks of state-editor.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**stateEditorHeaderColorForReadOnlyBlocks(since rel_3.8.6, repo property
ProgressNotesProperties)**

(default=Red)

Backgroundcolor for the headertext of readonly blocks of state-editor.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**therapyTextEditorDefaultFont**

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**widthOfCalendarDialog(since rel_3.8.6, repo property
ProgressNotesProperties)**

(default=250)

Width of calendardialog that will be shown creating new
dailyprogressnotes-objects

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\

\

**gf.actproperties.ProtocolProperties**

\

\

**ProtoHistoryInMenu** **(at least since rel_3.4, file property,
ACT_BASE)**

**since rel_3.8 located in Repository:
ProtocolProperties.protHistoryInMenu**

Betrifft Protokollierung: Steuert, ob der Menüpunkt \'Änderungen
anzeigen\' im PopupMenü der Editore angezeigt wird.

Beispiel:

ProtoHistoryInMenu=true

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\

**gf.actproperties.QuickCheckInProperties**

\

\

\

**QuickCheckInProperties.eCardPollingInterval** **(since rel_3.6, repo
property since rel_3.8, APP/Bimminger)**

Intervall in Millisekunden zwischen den Leseversuchen auf den
eCard-Reader. Default value is 1000 (msec

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**wfl.app.qcheckin.cardMode** **(liegt ab rel_3.8 im Repo unter
QuickCheckInProperties.cardMode, APP/Bimminger)**

Wird bei Quick-Check-In verwendet

Gibt an ob Patientenidentifikation mittels e-card oder
Quick-Check-InTicket erfolgt.

bei Parameter \"ticket\" wird Patientenid vom Quick-Check-In Ticket
gelesen

bei Parameter \"ecard\" wird die Sozialversicherungsnummer +
Geburtsdatum von der e-card gelesen

\

Beispiel: cardMode=ticket

cardMode=ecard

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**wfl.app.qcheckin.mpaExtend** **(liegt ab rel_3.8 in Repo unter
QuickCheckInProperties.mpaExtend, APP/Bimminger)**

legt fest ob Quick-Check-In als zusätzliche Funktionalität im
Patientenbrowser und bei Prozessplanung angeboten wird. Defaultmäßig ist
false eingestellt \--\> Quick-Check-In wird nicht als zusätzliche
Registerkarte im Patientenbrowser und bei Prozessplanung angezeigt.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**wfl.app.qcheckin.timeout** **(liegt ab rel_3.8 im Repo unter
QuickCheckInProperties.timeout APP/Bimminger)**

wird verwendet bei Quick-Check-In

Gibt an wie lange die Ergebnis-View (in Millisec) des Quick-Check-In dem
Patienten angezeigt wird. Dies dient zur Info an den Patienten ob die
Anmeldung mittels Quick-Check-In erfolgreich war oder nicht.

Dieser Timeout wird in SimpleQuickCheckController verwendet.

[Beispiel]{.underline}: timeout = 50000

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\

\

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\

\

\

\

\

\

\

\

\

\

\

\

\

\

\

\

\

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**gf.actproperties.RDIProperties**

**gf.actproperties.RTFProperties**

**gf.actproperties.RepoProperties**

**gf.actproperties.ReportProperties**

**gf.actproperties.ReservationProperties**

**gf.actproperties.SecurityProperties**

**gf.actproperties.SerProperties**

**gf.actproperties.SessionProperties**

\

**doOrgUnitSelect** **(since rel_3.12, change 289288, Doris Siegl)**

(default = false)

If set to true the selection of an OrgUnit is supported in MPA. This
works similar to selecting a role. The orgUnit selection dialog is
displayed each time a role is changed, or if it is called explicitly by
toolbar button orgUnitChange.

\

**gf.actproperties.SessionTimeOutProperties**

**gf.actproperties.SurgeryProperties**

\

**acuteSurgerySessionDefaultingDef** **(since rel_3.10, repo property
SurgeryProperties)**

(default = EMPTY)

Referes to a defaultingDefinition which is applied whenever a new acute
surgery is created in any surgeryrelated workarea (e.g. OP-planing).
This defaultingdefinition can be used to prefill fields of a new created
emergency-surgery.

\

**anaReleaseLockIconMC** **(since rel_3.10, repo property
SurgeryProperties)**

(default=ANAESTHESIA_OVERLAY_LOCK)

Name of icon which should be used in OP-calendar to indicate if a
surgery is locked by an anaesthesian.

\

**anaReleaseMissingIconMC** **(since rel_3.10, repo property
SurgeryProperties)**

(default=ANAESTHESIA_OVERLAY)

Name of icon which should be used in OP-calendar to indicate if a
surgery is not yet released by an anaesthesian.

\

**boolFieldrenderBitSurgeryCommitedFalseIconMC** **(since rel_3.10, repo
property SurgeryProperties)**

(default=SMALL_LIGHT_RED)

Name of icon which should be used in OP-calendar to indicate if a
surgery is not commited.

\

**boolFieldrenderBitSurgeryCommitedTrueIconMC** **(since rel_3.10, repo
property SurgeryProperties)**

(default=SMALL_LIGHT_GREEN)

Name of icon which should be used in OP-calendar to indicate if a
surgery is commited.

\

**criticalOrangeRange** **(since rel_3.10, repo property
SurgeryProperties)**

(default=90)

Used in capacitybrowser in OP-planing workarea. If the number of free
minutes in browsercell drops below this value, the cellcolor turns
orange.

\

**criticalRedRange** **(since rel_3.10, repo property
SurgeryProperties)**

(default=60)

Used in capacitybrowser in OP-planing workarea. If the number of free
minutes in browsercell drops below this value, the cellcolor turns red.

\

**defaultOPTimes** **(since rel_3.10, repo property SurgeryProperties)**

(default = 100 Vorrüsten-Beginn;200 Vorrüsten-Ende;300
Anästhesie-Beginn; 400 Anästhesie-Einleitung fertig; 500 OP-Beginn; 600
Schnitt; 700 Naht; 800 OP-Ende; 900 Anästhesie-End)

Used whenever a new SurgeryOPCatalog is created (OWC,
OP-CatalogWorkArea). The detail with OP-times is filled based on this
property. The propertyvalue must have a specific format: A semicolon
separates rows. each row contains 2 values: A ordernumber (must be a
valid number) and separated by a single blank: The name of the OP-time.
Technically:

ordernumber + \" \" + name of optime + \[\";\" + ordername + \" \" +
name of optime \....\]

see defaultvalue for example.

\

**maxVisibleCapacity** **(since rel_3.10, repo property
SurgeryProperties)**

(default = 480)

Used in capacitybrowser in OP-planing workarea. The bar which indicated
the available optime is truncated after XXX minutes. There is no optical
deference between free OPtime=480 and free opTime=900

\

**serviceEnabled** **(since rel_3.10, repo property SurgeryProperties)**

(default=true)

Turns on/off automatic refreshing of surgery-recordchanges. The
op-calendar uses this functionality to keep the shown appointments
up2date. Switch to \"false\" and the op-calendar must be refreshed
manually.

\

**useDefaultDurationInCalendar** **(since rel_3.10, repo property
SurgeryProperties)**

(default=\"from OP procedure\")

When planning new OPs from within the OP-calendar the planned length of
the new OP can be determined in two ways. First, by the selected area in
the calendar, second by the default duration of the OP procedure(s) to
be planned. Which length should be used, can be definied using this
property - the default length of the OP procedure defined in surgery
catalog, or the selected duration on the calendar.

\

\

**gf.actproperties.SymbolProperties**

**gf.actproperties.SystemaDLProperties**

\

**dl.diacos.leistungsCodeUpper** **(at.co.systema.dl, MPA_KIS, ab
rel_3.8 in Repo dl.Diacos.DiacosSettings.procedureCodeToUppercase)**

Gibt an ob Leistungscodes aus dem Diacos Uppercase übernommen werden
sollen

dl.diacos.leistungsCodeUpper=true

\

**DL.EDKatalogFromPhysColumn** **(at.co.systema.dl.sct, MPA_KIS, ab
rel_3.8 SystemaDLProperties.EDKatalogFromPhysColumn)**

\... definiert beim Vendor Systema das physColumn das in das LogColumn
idKatalog der **Einweisungsdiagnose** gemapped wird.

Ist das Property nicht angegeben, so erfolgt das Standard Mapping.

Beispiel: DL.EDKatalogFromPhysColumn=PAT_AUFN_ICDK

**DL.EDcodiertFromPhysColumn** **(at.co.systema.dl.sct, MPA_KIS, ab
rel_3.8 SystemaDLProperties.EDcodiertFromPhysColumn)**

\... definiert beim Vendor Systema das physColumn das in das LogColumn
diagnoseCode und idDiagnosedefinition der **Einweisungsdiagnose**
gemapped wird.

Ist das Property nicht angegeben, so erfolgt das Standard Mapping.

Beispiel: DL.EDcodiertFromPhysColumn=PAT_AUFN_ICDC

**DL.EDcodiertBezFromPhysColumn** **(at.co.systema.dl.sct, MPA_KIS, ab
rel_3.8 SystemaDLProperties.EDcodiertBezFromPhysColumn)**

\... definiert beim Vendor Systema das physColumn das in das LogColumn
bezeichnung der **Einweisungsdiagnose** gemapped wird.

Ist das Property nicht angegeben, so erfolgt das Standard Mapping.

Beispiel: DL.EDcodiertBezFromPhysColumn=PAT_AUFN_DIAG

**DL.EDlangFromPhysColumn** **(at.co.systema.dl.sct, MPA_KIS, ab rel_3.8
SystemaDLProperties.EDlangFromPhysColumn)**

\... definiert beim Vendor Systema das physColumn das in das LogColumn
freieDiagnose der **Einweisungsdiagnose** gemapped wird.

Ist das Property nicht angegeben, so erfolgt das Standard Mapping.

Beispiel: DL.EDlangFromPhysColumn=PAT_AUF_DIAG1

\

**DL.ADKatalogFromPhysColumn** **(at.co.systema.dl.sct, MPA_KIS, ab
rel_3.8 SystemaDLProperties.ADKatalogFromPhysColumn)**

\... definiert beim Vendor Systema das physColumn das in das LogColumn
idKatalog der **Aufnahmediagnose** gemapped wird.

Ist das Property nicht angegeben, so erfolgt das Standard Mapping.

Beispiel: DL.ADKatalogFromPhysColumn=PAT_AUF_ICDK

**DL.ADcodiertFromPhysColumn** **(at.co.systema.dl.sct, MPA_KIS, ab
rel_3.8 SystemaDLProperties.ADcodiertFromPhysColumn)**

\... definiert beim Vendor Systema das physColumn das in das LogColumn
diagnoseCode und idDiagnosedefinition der **Aufnahmediagnose** gemapped
wird.

Ist das Property nicht angegeben, so erfolgt das Standard Mapping.

Beispiel: DL.ADcodiertFromPhysColumn=PAT_AUF_ICDC

**DL.ADcodiertBezFromPhysColumn** **(at.co.systema.dl.sct, MPA_KIS, ab
rel_3.8 SystemaDLProperties.ADcodiertBezFromPhysColumn)**

\... definiert beim Vendor Systema das physColumn das in das LogColumn
bezeichnung der **Aufnahmediagnose** gemapped wird.

Ist das Property nicht angegeben, so erfolgt das Standard Mapping.

Beispiel: DL.ADcodiertBezFromPhysColumn=PAT_AUF_DIAG

**DL.ADlangFromPhysColumn** **(at.co.systema.dl.sct, MPA_KIS, ab rel_3.8
SystemaDLProperties.ADlangFromPhysColumn)**

\... definiert beim Vendor Systema das physColumn das in das LogColumn
freieDiagnose der **Aufnahmediagnose** gemapped wird.

Ist das Property nicht angegeben, so erfolgt das Standard Mapping.

Beispiel: DL.ADlangFromPhysColumn=PAT_AUFN_DIAG1

\

**DL.EDKatalogToPhysColumn** **(at.co.systema.dl.sct, MPA_KIS, ab
rel_3.8 SystemaDLProperties.EDKatalogToPhysColumn)**

\... definiert beim Vendor Systema das physColumn in das das LogColumn
idKatalog der **Einweisungsdiagnose** gemapped wird .

Ist das Property nicht angegeben, so erfolgt das Standard Mapping.

Beispiel: DL.EDKatalogToPhysColumn=PAT_AUFN_ICDK

**DL.EDcodiertToPhysColumn** **(at.co.systema.dl.sct, MPA_KIS, ab
rel_3.8 SystemaDLProperties.EDcodiertToPhysColumn)**

\... definiert beim Vendor Systema das physColumn in das das LogColumn
diagnoseCode und idDiagnosedefinition der **Einweisungsdiagnose**
gemapped wird.

Ist das Property nicht angegeben, so erfolgt das Standard Mapping.

Beispiel: DL.EDcodiertToPhysColumn=PAT_AUFN_ICDC

**DL.EDcodiertBezToPhysColumn** **(at.co.systema.dl.sct, MPA_KIS, ab
rel_3.8 SystemaDLProperties.EDcodiertBezToPhysColumn)**

\... definiert beim Vendor Systema das physColumn in das das LogColumn
bezeichnung der **Einweisungsdiagnose** gemapped wird .

Ist das Property nicht angegeben, so erfolgt das Standard Mapping.

Beispiel: DL.EDcodiertBezToPhysColumn=PAT_AUFN_DIAG

**DL.EDlangToPhysColumn** **(at.co.systema.dl.sct, MPA_KIS, ab rel_3.8
SystemaDLProperties.EDlangToPhysColumn)**

\... definiert beim Vendor Systema das physColumn in das das LogColumn
freieDiagnose der **Einweisungsdiagnose** gemapped wird.

Ist das Property nicht angegeben, so erfolgt das Standard Mapping.

Beispiel: DL.EDlangToPhysColumn=PAT_AUF_DIAG1

**DL.ADKatalogToPhysColumn** **(at.co.systema.dl.sct, MPA_KIS, ab
rel_3.8 SystemaDLProperties.ADKatalogToPhysColumn)**

\... definiert beim Vendor Systema das physColumn in das das LogColumn
idKatalog der **Aufnahmediagnose** gemapped wird.

Ist das Property nicht angegeben, so erfolgt das Standard Mapping.

Beispiel: DL.ADKatalogToPhysColumn=PAT_AUF_ICDK

**DL.ADcodiertToPhysColumn** **(at.co.systema.dl.sct, MPA_KIS, ab
rel_3.8 SystemaDLProperties.ADcodiertToPhysColumn)**

\... definiert beim Vendor Systema das physColumn in das das LogColumn
diagnoseCode und idDiagnosedefinition der **Aufnahmediagnose** gemapped
wird.

Ist das Property nicht angegeben, so erfolgt das Standard Mapping.

Beispiel: DL.ADcodiertToPhysColumn=PAT_AUF_ICDC

**DL.ADcodiertBezToPhysColumn** **(at.co.systema.dl.sct, MPA_KIS, ab
rel_3.8 SystemaDLProperties.ADcodiertBezToPhysColumn)**

\... definiert beim Vendor Systema das physColumn in das das LogColumn
bezeichnung der **Aufnahmediagnose** gemapped wird.

Ist das Property nicht angegeben, so erfolgt das Standard Mapping.

Beispiel: DL.ADcodiertBezToPhysColumn=PAT_AUF_DIAG

**DL.ADlangToPhysColumn** **(at.co.systema.dl.sct, MPA_KIS, ab rel_3.8
SystemaDLProperties.ADlangToPhysColumn)**

\... definiert beim Vendor Systema das physColumn in das das LogColumn
freieDiagnose der **Aufnahmediagnose** gemapped wird.

Ist das Property nicht angegeben, so erfolgt das Standard Mapping.

Beispiel: DL.ADlangToPhysColumn=PAT_AUFN_DIAG1

**DL.EDLines** **(at.co.systema.dl.sct, MPA_KIS, ab rel_3.8
SystemaDLProperties.EDLines)**

definiert, ob die Einweisungsdiagnose in einer od. zwei Zeilen
dargestellt wird

z.b: DL.EDLines = 2

\

\

\

**gf.actproperties.SystemaKisProperties**

**gf.actproperties.TLMProperties**

**gf.actproperties.TelProperties**

**gf.actproperties.TelnetAuthProperties**

**gf.actproperties.TimingProperties**

**gf.actproperties.TransactionServiceProperties**

**gf.actproperties.UpdateProperties**

**gf.actproperties.WFLAppointmentProperties**

\

**gf.actproperties.Properties**

\

\

\

\

\

\

\

**app.svc.maxFailuresBeforeDisconnect** **(file property in rel_3.6.b,
repo property since rel_3.8: APPProperties.maxFailuresBeforeDisconnect,
APP/Bimminger)**

(default=1)

(recommended value = 5)

number of failures before disconnect. Value should be low enough to have
as less \"failed\" communication as possible because we here have to
wait for timeouts. On the other hand, it should be large enough to step
over temporarily network loss. Behavior as before patch 2266?? can be
reached with value 1.

\

**app.svc.maxNumberThreadsForService** **(file property in rel_3.6.b,
repo property since rel_3.8: APPProperties.maxNumberThreadsForService
APP/Bimminger)**

(default=1 on rel_3.6.b)

(recommended value = 100)

Number of threads used as maximum for concurrent client communication in
thread pool. The number of threads limits the number of ports used. If
value is 1, no ThreadPool will be used and the clients will be notified
about appointment changes directly in RunnableThread. The ThreadPool
allows other notifications to proceed while failureful connections wait
for timeout. Recommended value 100 Threads is an intuition. Behavior as
before patch 2266?? can be reached with value 1.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**handleStayTransitionInAutostart** **(since 3.8.3, repo property in
WFLAppointmentProperties, APP/christoph1)**

(Default value = false)

Legt fest, ob beim automatischen Terminstart der Übergang von

einem Aufenthalt von stationär-\>ambulant oder von

\* ambulant-\>stationär erkannt werden soll. Wenn diese Funktion

\* aktiviert ist, wird beim ersten Öffnen aus der Todo-Liste a) bei

\* einem start mit einem bestehenden stationären Aufenthalt - wenn

\* entlassen - nach einem nicht entlassenen ambulanten Aufenthalt

\* gefragt oder b) bei einem ambulanten Aufenthalt - wenn es einen

\* nicht entlassenen stationären Aufenthalt gibt - dieser

\* stationäre Aufenthalt verwendet. Siehe Notes Job 30731.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**handleStayTransitionInManualStart** **(since 3.8.3, repo property in
WFLAppointmentProperties, APP/christoph1)**

/\*\*

\* Defaultwert: false

\* Legt fest, ob beim manuellen Terminstart der Übergang von einem

\* Aufenthalt von stationär-\>ambulant oder von ambulant-\>stationär

\* erkannt werden soll. Wenn diese Funktion aktiviert ist, wird

\* beim ersten Öffnen aus der Todo-Liste a) bei einem start mit

\* einem bestehenden stationären Aufenthalt - wenn entlassen - nach

\* einem nicht entlassenen ambulanten Aufenthalt gefragt oder b)

\* bei einem ambulanten Aufenthalt - wenn es einen nicht

\* entlassenen stationären Aufenthalt gibt - dieser stationäre

\* Aufenthalt verwendet. Bei Nicht-GUI-Anwendungen sowie bei

\* QuickCheckIn wird kein Aufenthaltswechsel durchgeführt. Siehe

\* Notes Job 30731.

\*/

\

**WFLAppointmentProperties.fillNoteTextByContextWithoutOptionDialog**
**(since rel_3.8, repo property, APP/Bimminger, integrated to
rel_3.6.b - file property
wfl.app.FillNoteTextByContextWithoutOptionDialog)** fill the note of the
appointment automatically from context positions, e.g. Anforderung, when
planning without option dialog? \[when planning with option dialog, the
note will always be filled automatically\]

default: FALSE - set on TRUE to enable the feature described in Todo
26365 ^(47)^, SWDEV 5238 ^(48)^

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**WFLAppointmentProperties.cancelAppointmentAfterDischargeTime** **(repo
property since rel_3.8, APP/Bimminger)**

Um welche Uhrzeit soll täglich das Löschen der Termine für entlassene
Patienten gestartet werden. Falls das automatische Löschen nicht
verwendet werden soll ist diese Property NULL zu setzen. Will be done by
WFLAppointmentService.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**WFLAppointmentProperties.metaProzessMatchcodeForExternalPlanned**
**(since rel_3.8, repo property, APP/Bimminger)**

which MetaProzess should be used for appointments planned on external
system (e.g. Meierhofer MCC), when they are planned in MPA via HL7?

See Job 21213 ^(49)^

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**gf.repo2.RepoPath.enableUserOwner (since 3.1.5, file property,
ACT_BASE, Sascha Hofer)**

**since rel_3.8 located in Repository: RepoProperties.userOwnerEnabled**

Determines whether the owner from type \"USER\" is allowed when reading
or writing a repo object.

Basically this owner can be used. Should this however not be wanted,
then it can be prevented by setting this property to \'f**alse**\'.

If this property is not existent resp. is it set to \'true\', then the
owner \"USER\" may be used (standard).

\

IMPORTANT:

Gets the \"USER\" deactivated and have already data been stored in the
repository under \"USER\", then these data will no longer be found.

In case the \"USER\" is not active, then objects that have so far been
stored in the repository on owner level \"USER\", are going to be stored
to the [\'TopOwner\']{.underline}(^(50)^)

\

To these special types of objects, that are usually stored automatically
along with the owner \"USER\" (no dialog involved), are belonging

UIHintDialog (Advices): RepoDir - gf.Assistant.SingleHints

HittreeDefinitionMgr (Adjustment Tree - personal folder): RepoDir -
gf.browser.hittree

UIDialog (Storage Size/Location of dialogs f.e. Role-Dialog): RepoDir -
gf.ui.controls.UIDialog

\

\

**repo2.CacheInitializer.directories (since \<= rel_3.4, file property,
ACT_BASE, Sascha Hofer)**

**since rel_3.8 located in Repository:
RepoProperties.cacheInitializerDirectories**

Liste von Repository-Verzeichnissen, die vom Programm
gf.repo2.tools.CacheInitializer gelesen werden (und damit im Cache des
RepoServers \"preloaded\" werden. Die Einträge werden durch Komma
getrennt.

Bsp:

repo2.CacheInitializer.directories = \\

gf.dict.LogObject, \\

gf.dict.LogPhysMap.ToLogMapper,\\

gf.dict.LogPhysMap.ToPhysMapper,\\

gf.dict.LogPhysMap.SurrogatElem,\\

gf.dict.LogPhysMap.HauptPhysTable,\\

gf.omgr.ObjectMgr,\\

\

\

**useOrgIdAsCode** **(since rel_3.11, SAPProperties)**

When this property is set to true, the orgUnitID will be mapped into the
code (\"kz\") column of orgUnits. Otherwise (default) the column
\"okurz\" will be used.

\

After changing this property, you need a repoInit -phase2!

**This property should only be changed for new SAP customers (GESPAG in
our case)!**

\

**sessionTimeoutCountdown** **(since rel_3.11,
SessionTimeoutProperties)**

Before the Session times out a dialog is displayed. The dialog is
visible for the time set in this property.

When the time is over the dialog is closed automatically and the session
times out.

When the property is set the 0, no dialog is displayed and the session
times out instantly.

Default = 5 (minutes)

\

**terminationTimeoutEnabled(since rel_3.11, SessionTimeoutProperties)**

If set to True, TerminationTimeout is enabled.

This means, when the Session has timed out, MPA is restarted after the
time defined in the property \'terminationTimeoutTime\'.

SessionTimeout has to be enabled too (Property \'enabled\' in
SessionTimeoutProperties).

Default = false

\

**terminationTimeoutTime(since rel_3.11, SessionTimeoutProperties)**

Defines the time for TerminationTimeout. See
\'terminationTimeoutEnabled\'.

Default = 120 (minutes)

\

**allowedToStopAbsence** **(since rel_3.8.3, repo property
SapProperties)**

Defaultwert = true

Steuert, ob im MPA Urlaubsbewegungen, die nicht sowieso am aktuellen Tag
enden, beendet werden dürfen

\

\

**domainname(since rel_3.8.6, repo property GFPrintProperties)**

(default=)

specifies the domain name to add

\

**SessionTimeOutProperties(since rel_3.10, ACT property**
**SessionTimeOutProperties)**

Used for setting and enabling SessionTimeOut in MPA.

Properties

enabled (default = disabled)

sessionTimeOutTime (default = 10 min)

\

\

**rowHeight(since rel_3.9, repo property ReservationProperties)**

(default=50)

Höhe der Planungszeile in Pixeln in der Reservierungsübersicht

\

**rowHeaderWidth(since rel_3.9, repo property ReservationProperties)**

(default=150)

Breite der Zeilenüberschrift in Pixeln in der Reservierungsübersicht

\

**transparency(since rel_3.9, repo property ReservationProperties)**

(default=0.4f)

Opazität (Undurchsichtigkeit) des Panels in der Reservierungsübersicht

Die Werte dürfen sich zwischen \<0; 1\> bewegen. Der Wert 0 bedeutet
\"undurchsichtig\",

der Wert 1 \"transparent = durchsichtig\".

\

**defaultDividerLocation(since rel_3.9, repo property
ReservationProperties)**

(default=200)

Position des \"Teilers\" in Pixeln in der UISplitPane der
Reservierungsübersicht

\

**firstVisibleDay(since rel_3.9, repo property ReservationProperties)**

(default=0)

Der erste sichtbare Wochentag (Montag bis Sonntag) in der
Reservierungsübersicht

\

**lastVisibleDay(since rel_3.9, repo property ReservationProperties)**

(default=4)

Der letzte sichtbare Wochentag (Montag bis Sonntag) in der
Reservierungsübersicht

\

\

**showGraphicalView(since rel_3.8.6, repo property SymbolProperties)**

(default=true)

defines the type of dialog, which will be shown to assign symbols

\

**logObjectsSetting(since rel_3.8.6, repo property SymbolProperties)**

(default=null)

A list of logical objects to define the kind of dialog, that should be
shown for those objects

map-key \..... name of the logical object

map-value \... true = show dialog with toggle-buttons

false = show dialog with table-browser

\

\

**TLMHermeskimEnabled(since rel_3.6.b, repo property TLMProperties)**

(default=false)

If the property is activated patient transportation can be organized via
TLM Heremeskim (which needs an external DLL).

\

**TLMHermeskimPath(since rel_3.6.b, repo property TLMProperties)**

If TLMHermeskimEnabled is set to true this property represents the path
to the DLL from Hermeskim.

\

**TLMHermeskimLoggingEnabled(since rel_3.6.b, repo property
TLMProperties)**

(default=false)

If the property is activated Hermeskim logs its logfiles into the folder
which you defined in the property TLMHermeskimPath.

\

**TLMHermeskimMoveProcess(since rel_3.6.b, repo property
TLMProperties)**

(default=\"\")

Defines the matchcode of the process which has to be started when an
appointment with an order is moved. The process starts the TLM Hermeskim
GUI.

\

**transportTypeExpressionName(since rel_3.8.3, repo property
TLMProperties)**

(default=TLMTransportType)

Defines the name of the expression which is responsible to get the
transport type from the \"Anforderung\" to send this information to TLM
(for new orders).

\

\

**filterOutSSNForPatientSearch** **(since 3.8.3, repo property in
SAPProperties)**

(Default value = false)

Damit diese Property funktioniert, muss auch die Property
**defineFieldsForPatientSearch** auf true gestellt werden.

Wenn eingeschaltet, wird bei der Patientensuche folgendermassen
vorgegangen:

1.) Zuerst wird die Suche so gestaltet, wie beim Einschalten der
Property **defineFieldsForPatientSearch**, d.h:

Wenn die Felder \"Vorname\", \"Geschlecht\", \"SVNR\" und
\"Geburtsdatum\" eingegeben, werden alle zusätzlichen Einschränkungen
nicht mehr wahrgenommen (guenstig speziell bei der e-card Suche).

Es wird nur nach Geburtsdatum und SVNR (ohne Patientenindex) gesucht.

Wenn nichts gefunden, dann wird nach Geb.Datum, Geschlecht und
Vorname(ohne Patientenindex) gesucht.

Dazu kommen Resultate aus dem Patientenindex mit der Einschränkung nach
Geb.Datum, Geschlecht, Vorname UND SVNR.

Jetztz kommt die neue Property zum Zug:

Wenn eingeschaltet, werden jetzt alle Patienten, die eine SVNR haben,
nich in die Result Collection aufgenommen.

Es bleiben nur die SVNR-losen drinnen.

\

\

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**sap.MovementTypesFromFirstMovement** **(at.co.systema.sap, MPA_KIS, ab
rel_3.8 im Repo SapProperties.movementTypesFromFirstMovement)**

Bestimmt, welche Bewegungsarten sollten bei einer automatischen Anlage
der Bewegungen aus der Leistungsgenerierung (DLOrd)

aus der ersten ambulanten Bewegung übernommen werden.

Mehrere eingetragene Bewegungsarten müssen durch einen Beistrich
getrennt werden.

Beispiel: **sap.MovementTypesFromFirstMovement=FE,DI**

Wenn keine solche Property eingetragen, wird die Bewegungsart für die
generierte ambulante Bewegung so wie bis jetzt von einer Assoc oder
Expression bestimmt.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**defineFieldsForPatientSearch** **(since 3.8.3, repo property,
KIS/Böhm, integrated to rel_3.6.b - file property
SAP.DefineFieldsForPatientSearch)**

(Default value = false)

Wenn eingeschaltet, wird bei der Patientensuche folgendermassen
vorgegangen:

Wenn die Felder \"Vorname\", \"Geschlecht\", \"SVNR\" und
\"Geburtsdatum\" eingegeben, werden alle zusätzlichen Einschränkungen
nicht mehr wahrgenommen (guenstig speziell bei der e-card Suche).

Es wird nur nach Geburtsdatum und SVNR (ohne Patientenindex) gesucht.

Wenn nichts gefunden, dann wird nach Geb.Datum, Geschlecht und
Vorname(ohne Patientenindex) gesucht.

Dazu kommen Resultate aus dem Patientenindex mit der Einschränkung nach
Geb.Datum, Geschlecht, Vorname UND SVNR.

Wenn die Felder \"Vorname\", \"Geschlecht\", \"SVNR\" und
\"Geburtsdatum\" eingegeben, werden alle zusätzlichen Einschränkungen
nicht mehr wahrgenommen (guenstig speziell bei der e-card Suche).

Damit wird der Patient richtig gefunden, auch wenn z.B. sein Nachname
(durch Heirat oder Sonstiges) gegenüber der Ersterfassung geändert
wurde.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**SapProperties.phoneticPatientSearch** **(since 3.9, repo property,
KIS/Oberndorfinger)**

(Default value = false)

Wenn eingeschaltet wird unter SAP der Nachname phonetisch gesucht

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**wfl.displayCacheRestoredFromDB** **(since 3.8, repo property,
WFL/Trummer)**

If set to true the wfl-display-cache (contains all DisplayProzesse and
DisplayTodos) will be written to the database when terminating the
wfl-JBoss. Later on when restarting the JBoss all running process must
no be restored because the DisplayTodos and DisplayProzesse will be
restore from the database (which is much more faster than the normal
restoration).

Default wfl.displayCacheRestoredFromDB and wfl.restoreProcesses is set
to true. This means that all DisplayTodos and DisplayProzesse will be
restored from the database and if this fails the normal restoration will
start.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**gf.timing.maxDifference (since \<= rel_3.4, file property, ACT_BASE)**

**since rel_3.8 located in Repository: TimingProperties.maxDifference**

Das TimingService ist ein \"MiniService\" im InvokeServer.

Tritt die Fehlermeldung \"TimingService läuft nicht\" auf, so muß der
InvokeServer gestartet werden.

Die Aufgabe des TimingService ist, den Zeitunterschied zwischen dem
Server und dem Client festzustellen.

Die angabe der Toleranz erfolgt im customer.properties File mit
**gf.timing.maxDifference.**

Der Wert der hier eingetragen wird ist in Minuten (z.B.
gf.timing.maxDifference = 2 Toleranz beträgt 2 Minuten)

der Defaultwert beträgt 5 Minuten

Ist maxDifference = -1 dann wird die überprüfung nicht durchgeführt

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**client (Service)-Properties (beeinflusst Verhalten der Klasse
TransactionServiceImpl)**

**gf.txmgr.cleanupInterval (since \<= rel_3.4, file property,
ACT_BASE)**

**since rel_3.8 located in Repository:
TransactionServiceProperties.cleanupInterval**

Intervall in dem TransactionService nicht aufgehobene Locks sucht und
diese Sperren aufhebt (Angabe in Millisekunden)

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**customer-Properties (beeinflusst Verhalten der Klasse
TransactionLockClient)**

**gf.txmgr.gf.txmgr.maxServiceLookupTime (since \<= rel_3.4, file
property, ACT_BASE)**

**since rel_3.8 located in Repository:
TransactionServiceProperties.maxServiceLookupTime**

maximale Zeit in Millisekunden, die vom TransactionLockClient für einen
notwendigen Restart des TransactionService aufgewendet wird. Falls
Reconnection durch CommunicationProxy durchgeführt wird, hängt die Dauer
des Restarts vom CommunicationProxy ab und ist unter Umständen höher als
maxServiceLookupTime.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

^(51)^**defaultLAB** = 1**(at.co.systema.labor, file property,
MPA_DOC/Dorfmair, since rel_3.8 in Repo in
LaborProperties.defaultLaborID)**

Mit dieser Labor-ID (LAB_LABOR_KZ) wird im SCT-LIS-System zugegriffen.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**gf.timing.maxDifference (since \<= rel_3.4, file property, ACT_BASE)**

**since rel_3.8 located in Repository: TimingProperties.maxDifference**

Das TimingService ist ein \"MiniService\" im InvokeServer.

Tritt die Fehlermeldung \"TimingService läuft nicht\" auf, so muß der
InvokeServer gestartet werden.

\

Die Aufgabe des TimingService ist, den Zeitunterschied zwischen dem
Server und dem Client festzustellen.

Die angabe der Toleranz erfolgt im customer.properties File mit
**gf.timing.maxDifference.**

Der Wert der hier eingetragen wird ist in Minuten (z.B.
gf.timing.maxDifference = 2 Toleranz beträgt 2 Minuten)

der Defaultwert beträgt 5 Minuten

\

Ist maxDifference = -1 dann wird die überprüfung nicht durchgeführt

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\

\

**TELNET_TIMEOUT (ab rel_3.6.b Change 110577) file property, ACT_BASE**

**Wechselt mit Einführung der ActiveDirectory Paßwortüberprüfungsmethode
(rel_3.8.3) ins Repository (TelnetAuthProperties.telnetTimeout)**

(default=5000 ms)

Timeout für die Passwort-Überprüfung mittels Telnet. Bei Active
Directory und sonstige kann durch die dynamische Adressvergabe

kann mehr Zeit in Anspruch genommen werden.

Timeout for password checks using telnet. In some cases (f.e. Active
Directory) it may take longer because of the dynamic IPs.

Timedimension is in \[ms\].

example:

TELNET_TIMEOUT=8000

Changes the timeout to 8000 ms or 8 sec.

\

\-\-\--**NovacomProperties**\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**ignoreAppointmentsOlderThan**

**(gültig ab rel_3.8.3 im Repo unter
NovacomProperties.ignoreAppointmentsOlderThan, MPA_KIS)**

definiert die Anzahl der Tage, die ein Betttermin in der Vergangenheit
liegt, dass er trotzdem noch berücksichtigt wird

(Default: ignoreAppointmentsOlderThan = 7)

\

\-\-\-\--**ODBC TEST -
kis.sct.SctNative**\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**(** **MPA_KIS, ab rel_3.8** **im Repo unter
SystemaKisProperties.testODBC)**

\# Einstellung für das Testen der ODBC Verbindung; wird beim Start des
InvokeServers zum Beispiel durchgeführt;

\# Aktivieren des Tests:

kis.sct.testODBC=true

\# Sollte DB Driver von SUN sein (nur ändern wenn sich der Pfad im SUN
JDK ändert! Der von Systema erweiterte JDBC

\# Treiber kann nicht verwendet werden Fehler im \'Native Bereich\'
auftritt und nicht nachvollziehbar ist!

kis.sct.SctNative.odbcDriver=sun.jdbc.odbc.JdbcOdbcDriver **(MPA_KIS,**
**obsolate, Wert wurde fix programmiert)**

\# statt CLIENT wird im Programm der entsprechende SCT_DB Wert
eingesetzt

kis.sct.SctNative.url=jdbc:odbc:CLIENT **(MPA_KIS,** **obsolate, Wert
wurde fix programmiert)**

\

ACHTUNG: folgende Werte müssen auch gesetzt sein!!!!!

Environment.autoset.SCT_DB=MPA_LZMPA88

Environment.autoset.SCT_ODBC_USER=mpa

Environment.autoset.SCT_ODBC_PWD=kis

\

\

**SAP.ReadBewegungenMitAufenthalt** ab rel_3.6, aber nicht rel_3.6.1
**(at.co.systema.sap, MPA_KIS, ab rel_3.8 in Repo unter
SapProperties.readBewegungenMitAufenthalt)**

Setzt voraus, dass **SAP.UseOptimizedBAPIForAufenthalt** **= true.**

Steuert, ob die migelesenen Bewegungen gleich nach dem Lesen eines
Aufenthaltes in die LO\'s Bewegungen kopiert werden.

Damit sind die Bewegungen genau so frisch (alt) wie die Falldaten.

Die angenehme Konsequenz: die Aufrufe zu /SYSTEMA/MPA_GET_NBEW_TAB
(Lesen der Fall Bewegungen) wurden auf 0 reduziert.

Damit sinkt die Netzbelastung deutlich. Die \"lokale\" Performance einer
Aufnahme wurde damit auch verbessert.

\

\

**SAP.UseOptimizedBAPIForAufenthalt** ab rel_3.6, aber nicht rel_3.6.1
**(at.co.systema.sap, MPA_KIS, ab rel_3.8 in Repo unter
SapProperties.useOptimizedBAPIForNFAL)**

Steuert, welche IS-H Methode zum Lesen der Fälle verwendet wird.

Die ursprüngliche BAPI zum Lesen der Aufenthalte konnte keine
Bewegungsdaten mitliefern, so dass man pro Fall noch eine BAPI
/SYSTEMA/MPA_GET_NBEW_TAB aufrufen musste, um einige Falldaten (die in
SAP Datenmodell auf den Bewegungen liegen) zu ermitteln.

Bei einer größeren Anzahl der eingelesenen Fälle performte diese Methode
in der Summe sehr schlecht.

Deswegen existiert jetzt eine neue RFC Methode
/SYSTEMA/MPA_GET_CASE_LIST2, die auf einmal alle gewünschten Fälle
liefert und zwar so, dass auch Felder wie Aufnahmedatum (die von der
ersten Bewegung ermittelt werden müssen) schon von der BAPI richtig
gesetzt werden.

Die exakte Businesslogik zum einlesen solcher Felder wurde aus MPA in
die BAPI Methode verschoben.

true\.....(oder nicht gesetzt = Default) es wird die neue optimierte
BAPI verwendet.

false\...es wird die \'alte\' BAPI verwendet.

\

\

**COS.KlinischesDokumentEditor.replaceFullOnStatic=false (since rel_3.6,
file property, ACT_BASE)**

**since rel_3.8 located in Repository:
RTFProperties.replaceFullOnStatic**

Defaultwert: false

Werden im RTF-Text Platzhalter aufgelöst und sind diese danach
unveränderlich wird über diese Property bestimmt ob der Platzhalter nach
wie vor bestehen bleiben soll (Wert=false) oder durch reinen Text
ersetzt wird. Wurde ein Platzhalter durch Text ersetzt ist der Text
danach nichtmehr readonly.

Bisher (Rel3.7) erfüllen alle normalen Platzhalter die oben angeführten
Bedingungen.

\

**SAP.MaxNrOfRepeatingCalls** (ab rel_3.6) **(at.co.systema.sap,
MPA_KIS, ab rel_3.8 in Repo unter SapProperties.maxNrOfRepeatingCalls)**

Neuer Parameter für die maximal erlaubte Anzahl der sukzessiven Calls
desselben RFC Funktionsbausteines.

Es sollen damit (als letzte Instanz) mögliche unendliche Schleifen
verhindert werden und das Leben eines SAP Servers \'gerettet\' werden.

Beispiel:

**SAP.MaxNrOfRepeatingCalls** = 5000

Defaultwert: 10000

Wenn der Wert \"0\" eingestellt ist, gibt es keine Begrenzung für die
Anzahl der Calls.

\

\

**sap.trace** (ab rel_3.8) **(at.co.systema.sap, MPA_KIS ab rel_3.8 in
Repo unter SapProperties.trace)**

Wenn sap.trace=true, wird bei der Verbindung zu einem SAP System das
Tracing eingeschaltet. Damit wird inm der JCO sehr ausführlich die
komplette Kommunikation über die rfclib32.dll Aufrufe protokolliert. Es
entsteht am Client am aktuellen Verzeichnis ein File mit den
Protokolldaten. Gut für Fälle, wo auch der defaultWorkbench
Startparameter \"-log sapdebug\" nicht den Erfolg bringt.

Defaultwert ist false.

\

**sapDebugTraceListLO** **(at.co.systema.sap, MPA_KIS ab rel_3.8 in Repo
unter SapProperties.sapDebugTraceListLO)**

für das logische Objekt (z.B. Patient) oder eine gewisse RFC Funktion
auf diesem LO (z.B. Patient.lock, Patient.read) wird das sapdebug
Logging eingeschaltet.

\

**sapDebugTraceListRfc** **(at.co.systema.sap, MPA_KIS ab rel_3.8 in
Repo unter SapProperties.sapDebugTraceListRfc)**

für alle RFC Funktionen aus der Liste wird das sapdebug Logging
eingeschaltet.

\

\

**SER.Archiving_Server_Name** **(at.co.systema.ser.SERProperties,
MPA_DOC/Dorfmair, ab rel_3.8 in Repo unter ab rel_3.8 in Repo unter**

**SerProperties.archivingServerName)**

Name/Adresse des Rechners und eventuell Portnummer, wo die Archivierung
(über SER-OnlineScanning) durchgeführt wird. Ist dieses Property nicht
gesetzt wird der Wert von SER.Server_Name übernommen.

\

**sap.debug.RfcFunktionsname** (ab rel_3.5) **(at.co.systema.sap,
MPA_KIS, ab rel_3.8 in Repo unter SapProperties.debugRfcFunctionNames**
**-\> auch kleine Änderung der Logik)**

Wenn die gewünschte RFC Funktion aufgerufen wurde, wird automatisch der
ABAP Debugger auf dem Client Rechner gestartet,

vorausgesetzt auf dem Client Rechner ist SAPGUI Client installiert.

Der Text \"RfcFunktionsname\" muss durch den Namen der gewünschten
BAPI/RFC Funktion ersetzt werden.

Beispiel:

**sap.debug.BAPI_PATIENT_SEARCH=true**

**sap.debug./SYSTEMA/MPA_GET_OE_LIST1=true**

Defaultwert ist false, daher wenn keine Einträge aktiv, wird auch kein
ABAP Debugger aktiviert.

\

**SAP.MaxNrOfSuccessfulQueries** (ab rel_3.5) **(at.co.systema.sap,
MPA_KIS, ab rel_3.8 in Repo unter
SapProperties.maxNrOfSuccessfulQueries)**

Neuer Parameter für die Simulation des SAP R/3 Verbindungsverlustes.

**SAP.MaxNrOfSuccessfulQueries** = 0 (Default), KEIN Verbindungsverlust
simuliert

**SAP.MaxNrOfSuccessfulQueries** \> 0 , Verbindungsverlust simuliert
nach der angegebenen Anzahl der Queries.

Die Connection wir so lange gültig gehalten, wie oft innerhalb von
getObjectForKey oder getObjectsForCondition auf irgendwelche RFC
Funktion zugegriffen wird. Dann wird die Methode Connection.open() eine
Exception werfen. Das MPA Verhalten auf diesen Umstand kann jetzt
getestet werden.

\

**SAP.MaxNrOfUnsuccessfulQueries** (ab rel_3.5) **(at.co.systema.sap,
MPA_KIS, ab rel_3.8 in Repo unter
SapProperties.maxNrOfUnsuccessfulQueries)**

Neuer Parameter für die Simulation des SAP R/3 Verbindungsverlustes.

**SAP.MaxNrOfUnsuccessfulQueries** = 0 (Default), KEIN
Verbindungsverlust simuliert

**SAP.MaxNrOfUnsuccessfulQueries** \> 0 , es wird dem MPA so lange
vorgegaukelt, dass es keine Connection zu dem SAP R/3 System gibt, bis
die Anzahl der nicht erfolgreichen Queries den eingestellten Wert
erreicht hat. Nachdem wird sich das System **wieder verbinden können**.

Dieser Wert ist nur dann relevant, wenn es zu einer Unterbrechung der
Connection mittels SAP.MaxNrOfSuccessfulQueries \> 0 gekommen ist.

\

\

REPORTING

**ReportPrerequisitesEditor.DoCheckBeforeEnd=true** **(since 3.11,**
[**act property since change**]{.underline} ^**(52)**^*[Change
270491]{.underline}***,** **paruch@ACT_QUERITY)**

(Default value = true)

Determines if check/validation in ReportPrerequisitoesEditor will be
called/done before end of user´s work (before getting of
updated(changed) report prerequisities in edit dialog).

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**wfl.allowStartOfProcessForPlannedPatient (seit rel_3.5)** **(liegt ab
rel_3.8 im Repository unter WFLAppointmentProperties als
allowStartOfProcessForPlannedPatient, WFL/Trummer)**

\# steuert ob Prozesse mit geplanten Patienten gestartet werden können

\# oder nicht

\# default = true

siehe auch Todo 3413 ^(53)^

\

\

\

\

**PatientSearchEditor.MaxReadCount** **(at.co.systema.kis, MPA_KIS, ab
rel_3.8 in Repo unter
SystemaKisProperties.patientSearchEditorMaxReadCount)**

~~Legt die Anzahl der Aufenthalte fest, die bei der Patientensuche
maximal gelesen wird. Wurde eingebaut, weil in dieser Info kein
Weiterlesen möglich ist. Default=500~~

Änderung ab rel_3.5: (erich)

Auch bei der Patientensuche funktioniert das weiterlesen korrekt.

Im KIS werden Aufenthalte gelesen, und diese auf die Patienten
komprimiert.

Der Defaultwert ist der Defaultwert der SearchEditoren und der ist
derzeit 200.

Beim Kunden sollte aus Performancegruenden das Property noch niedriger
gewaehlt werden (z.B. 50)

Beim Weitersuchen wird der Wert jeweils mit 50 (=Defaultwert des Search
Editor) erhöht.

\

\

\

\-\-\-\--**AGFA-Archiv**\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**(alle agfa.AgfaProperties, MPA_DOC/Dorfmair, liegen ab rel_3.8 im Repo
unter** **AgfaProperties)**

\

**AGFA.SERVER_IP** **(agfa.AgfaProperties, MPA_DOC/Dorfmair, liegt ab
rel_3.8 im Repo unter** **AgfaProperties.serverIP)**

\

IP Adresse des Rechners auf dem AGFA eCodis läuft

Derzeit ist wirklich die IP Adresse nötig - der Name (z.B.: MPADOC führt
zu Fehlern)

AGFA.SERVER_IP=212.124.145.118

\

\

**AGFA.LOGIN_USER** **(agfa.AgfaProperties, MPA_DOC/Dorfmair, liegt ab
rel_3.8 im Repo unter** **AgfaProperties.loginUser)**

\

gültiger User am AGFA eCodis Server

AGFA.LOGIN_USER=systema\\\\mpa989

\

**AGFA.LOGIN_PWD** **(agfa.AgfaProperties, MPA_DOC/Dorfmair, liegt ab
rel_3.8 im Repo unter** **AgfaProperties.loginPWD)**

\

Passwort zu oben angegebenem User

AGFA.LOGIN_PWD=mpa

\

**AGFA.SERVER_PORT** **(agfa.AgfaProperties, MPA_DOC/Dorfmair, liegt ab
rel_3.8 im Repo unter** **AgfaProperties.serverPort)**

\

Port an dem eCodis verfügbar ist

AGFA.SERVER_PORT=3000

\

\

AGFA benötigt die Dateien die archiviert werden in einem speziellen
Verzeichnis am eCodis Rechner

zum FileUpload wird ein FTP Server eingerichtet

\

**(agfa.AgfaProperties, MPA_DOC/Dorfmair, liegt ab rel_3.8 im Repo
unter** **AgfaProperties.ftpServer)**

**AGFA.FTP_SERVER**=mpadoc

\

**(agfa.AgfaProperties, MPA_DOC/Dorfmair, liegt ab rel_3.8 im Repo
unter** **AgfaProperties.ftpUser)**

**AGFA.FTP_USER**=systema\\\\mpa989

\

**(agfa.AgfaProperties, MPA_DOC/Dorfmair, liegt ab rel_3.8 im Repo
unter** **AgfaProperties.ftpPWD)**

**AGFA.FTP_PWD**=mpa989

\

**(agfa.AgfaProperties, MPA_DOC/Dorfmair, liegt ab rel_3.8 im Repo
unter** **AgfaProperties.ftpPort)**

**AGFA.FTP_PORT**=21

\

**AGFA.VIEW_URL** (ab rel_3.4) **(agfa.AgfaProperties, MPA_DOC/Dorfmair,
liegt ab rel_3.8 im repo unter**

**AgfaProperties.viewUrl)**

Aufruf des AGFA Viewers aus MPA benötigt eine spezielle URL

URL enthält :

Rechnername : MPADOC

SearchProfil Nr :4 auf MPADOC - Muß aus den Profileinstellungen
ermittelt werden

einziges Feld in diesem Searchprofil:docid

im Viewer wird dann noch die DokId angehängt

&From1=\...&To1=

AGFA.VIEW_URL=/ecodisauto/start.asp?ProfileID=4&Link1=&Field1=docid&Operator1=EXACT

\

\

\-\-\-\--**EuroSystemsProperties**\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**(alle eurosystems.EuroSystemProperties, MPA_DOC/Dorfmair, liegen ab
rel_3.8 im Repo unter** **EuroSystemsProperties**

**diese Properties waren vor rel_3.8 nicht im customer.properties,
sondern in einem eigenen Propertiesfile)**

\

**EuroSystemsFileProcessor.DeleteFilesMode**

**(eurosystems.EuroSystemProperties, MPA_DOC/Dorfmair, liegt ab rel_3.8
im Repo unter EuroSystemProperties.deleteFileMode)**

Gibt an, welche Dateien nach erfolgreichem Archivieren gelöscht werden
sollen.

[Mögliche Werte:]{.underline}

none \... keine Dateien

all \... alle Dateien

datafiles \... nur die Dateien mit den Images werden gelöscht

(Default: deleteFilesMode = none)

\

**EuroSystemsFileProcessor.fileExtension**

**(eurosystems.EuroSystemProperties, MPA_DOC/Dorfmair, liegt ab rel_3.8
im Repo unter EuroSystemProperties.fileExtension)**

Gibt die Extension für die Dateien mit dem eigentlichen Dokument an.

Ist dieses Property nicht vorhanden, wird \"rtf\" angenommen.

(Default: fileExtension = rtf)

\

**WordContainerMaxUseCount**

**(eurosystems.EuroSystemProperties, MPA_DOC/Dorfmair, liegt ab rel_3.8
im Repo unter EuroSystemProperties.wordContainerMaxUseCount)**

Gibt an, nach wievielen importierten Dokumenten die Word-Ressourcen
freigegeben werden.

Ist diese Property nicht vorhanden, werden die Ressourcen erst mit
Programmende freigegeben.

(Default: wordContainerMaxUseCount = 0)

\

**eurosystems.EuroSystemsDokumentImport_RMIName**

**(eurosystems.EuroSystemProperties, MPA_DOC/Dorfmair, liegt ab rel_3.8
im Repo unter EuroSystemProperties.dokumentImport_RMIName)**

Definiert den zu verwendenden RMI-Name für den EuroSystemsDokumentImport

\

\-\-\-\--**Aufenthalt /
Patient**\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**AufenthaltSearch.MedEntl.TageEntlassen** **(at least since rel_3.4,
fileProperty, MPA_KIS, nicht im Repo, da native auch gelesen)**

Im SearchBrowser für Aufenthalte, die noch medizinisch zu entlassen sind
wird zusätzlich auch nach dem Entlassungsdatum eingeschraenkt (Default
=30). Der hier festgelegte Wert gibt an, daß nur Aufenthalte
berücksichtigt

werden deren Entlassungsdatum maximal diese Anzahl von Tagen zurück
liegt.

\

**Aufenthalt.enableWriteCheck** **(at.co.systema.kis, MPA_KIS, ab
rel_3.8 in Repo unter SystemaKisProperties.admissionEnableWriteCheck)**

Falls aktiviert, wird beim Speichern des Aufenthaltes geprueft, ob Daten
(versehentlich ?) fehlerhafterweise ueberschrieben wurden (nur SYSTEMA
KIS) - ist das der Fall, wird nicht gespeichert

Bsp: Aufenthalt.enableWriteCheck=true

Kann auch auf den Wert warning gesetzt werden - Meldungen, falls etwas
ueberschrieben wird, wird ausgegeben, es kann aber gespeichert werden

Bsp: Aufenthalt.enableWriteCheck=warning

\

**Aufenthalt.writeCheckIgnoreFields** **(at.co.systema.kis, MPA_KIS, ab
rel_3.8 in Repo unter
SystemaKisProperties.admissionWriteCheckIgnoreFields)**

Alle Felder fuer die der Write Check NICHT durchgefuehrt werden soll

Bsp:

Aufenthalt.writeCheckIgnoreFields=UPDT_CNT,MOD_TIME,MOD_USER,PAT_LMOD_DATUM

\

**Aufenthalt.writeCheckIgnoreFieldsDL** **(at.co.systema.kis, MPA_KIS,
ab rel_3.8 in Repo unter
SystemaKisProperties.admissionWriteCheckIgnoreFieldsDP)**

Alle Felder fuer die der Write Check NICHT durchgefuehrt werden soll
(z.B.: UPDT_CNT,PAT_AUF_NR) - in DiagnoseLeistungsErfassung

Bsp:

Aufenthalt.writeCheckIgnoreFieldsDL=UPDT_CNT,MOD_TIME,MOD_USER,PAT_DIAG_A_MCODE,\\

PAT_ENTL_DIAG_ARZT,PAT_ENTL_ICDC,PAT_ENTL_DIAG,PAT_LMOD_DATUM,PAT_ENTL_DIAG1,\\

PAT_ENTL_ICDC_GRP,PAT_DIAG_DATUM,PAT_AUFN_DIAG1,PAT_AUF_ICDC,\\

PAT_ENTL_ICDC_GBIS,PAT_AUFN_ICDC,PAT_AUF_DIAG,PAT_DIAG_LST_KURZBEZ,\\

PAT_DIAG_FACH,PAT_ENTL_ICDC_GVON,PAT_AUFN_DIAG,PAT_ENTL_ICDK,PAT_AUF_DIAG1,\\

PAT_DIAG_LST,PAT_MCODE_DIAG_LST,PAT_ENTL_DIAG2,PAT_MEDENTL_ARZT,\\

PAT_MEDENTL_ZP,KHS_KONT_ALLG_JN,PAT_AUFN_ICDK,KHS_DIAG_KZ

\

**Aufenthalt.writeCheckIgnoreFieldsAufnahme** **(at.co.systema.kis,
MPA_KIS, ab rel_3.8 in Repo unter
SystemaKisProperties.admissionWriteCheckIgnoreFieldsAdmission)**

Alle Felder fuer die der Write Check NICHT Durchgefuehrt werden soll
(z.B.: UPDT_CNT,PAT_AUF_NR) - in der Aufnahme

\

**Aufenthalt.writeCheckIgnoreFieldsEntlassung** **(at.co.systema.kis,
MPA_KIS, ab rel_3.8 in Repo unter
SystemaKisProperties.admissionWriteCheckIgnoreFieldsDischarge)**

Alle Felder fuer die der Write Check NICHT Durchgefuehrt werden soll
(z.B.: UPDT_CNT,PAT_AUF_NR) - bei der Entlassung

Bsp:

Aufenthalt.writeCheckIgnoreFieldsEntlassung=UPDT_CNT,MOD_TIME,MOD_USER,PAT_ENTL_DATUM,\\

PAT_AUFN_STATUS,PAT_ENTL_ZP,KHS_KONT_ALLG_JN,PAT_ENTL_ZEIT,PAT_ENTL_JN,\\

KHS_ENTLA_BEZ,KHS_ENTLA_KURZBEZ,KHS_ENTLA_KZ,PAT_ENTL_ORT,PAT_TODESZEIT,\\

PAT_TODESDAT,KHS_KONT_ALLG_JN

\

\-\-\-\--**Aufenthalt Ende**

\

\

\-\-\--**DICOM -
RADIN**\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**(Alle RadinProperties/RadinSettings, MPA_STEYR/Dorfmair, liegen seit
rel_3.8 im Repo unter doc.dicom.DicomSettings.RADIN\_\....)**

see also []{.underline} ^[**(54)**]{.underline}^*[Documentation 6113:
Description of properties within DicomSettings (since
rel_3.8)]{.underline}*

**DicomSettings.RADIN_host**

**(MPA_STEYR/Dorfmair, liegen im Repo unter
doc.dicom.DicomSettings.RADIN_host)**

Gibt den Server an, unter welchem das Radin Programm läuft

Beispiel: \[www.demo.radon.de\].

Ein null-Value ist nicht erlaubt.

\

**DicomSettings.RADIN_progPath**

**(MPA_STEYR/Dorfmair, liegen im Repo unter
doc.dicom.DicomSettings.RADIN_progPath)**

Gibt den Radin Programmpfad Aufruf an.

Der default-Wert ist \[oemquery.exe\].

Ein null-Value ist nicht erlaubt.

\

**DicomSettings.RADIN_addAttributes**

**(MPA_STEYR/Dorfmair, liegen im Repo unter
doc.dicom.DicomSettings.RADIN_root)**

Ermöglicht Einstellung der Sprache (Englisch, Deutsch,..) .

[Mögliche Werte:]{.underline}

\- radin/de - Deutsch

\- radin/en - Englisch

\- radin/it - Italienisch

\- radin/fr - Französisch

Ein null-Value ist nicht erlaubt.

\

**DocDicomViewRadinProperties.addAttributes**

**(MPA_STEYR/Dorfmair, liegen im Repo unter
doc.dicom.DicomSettings.RADIN_addAttributes)**

Zusätzliche Programmattribute.

Bei einem Null value werden keine zusätzlichen Attribute übergeben.

=\> genauere Beschreibung (siehe Repo (gf.actProperties))

\

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\

\-\-\-\--**DICOM-TIANI (alte unzuverlässige Variante)**
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**(at least since rel_3.4, MPA_DOC - werden nicht ins Repo übernommen,
da alte Funktionalität)**

für den Aufruf von Tiani JVision mittels Parameter-Datei in einem
Kommunikationsverzeichnis

(at.co.systema.doc.dicom.view.tiani.TianiInhaltViewerSupport)

\

**DICOM_TIANI_DIR** **(MPA_DOC/Dorfmair)**

Kommunikation Verzeichnis. Das Verzeichnis wird auf dem
PACS-Archiv-Rechner zur

Verfügung gestellt.

Beispiel:

DICOM_TIANI_DIR=\\\\\\\\edv87\\\\tiani

\

**DICOM_TIANI_DISPLAY_NODE** **(MPA_DOC/Dorfmair)**

Gibt den Host-Name der PACS-Station an bei der die Bildpräsentation
erfolgen soll.

Beispiel:

DICOM_TIANI_DISPLAY_NODE=edv87

\

**DICOM_TIANI_PACS_HOST** **(MPA_DOC/Dorfmair)**

Node von der geladen werden soll. Wenn nicht bekannt dann PACS-Archive
Host-Name.

Beispiel:

DIACOM_TIANI_PACS_HOST=pacs01

\

**DICOM_TIANI_FILENAME_PRX** **(MPA_DOC/Dorfmair)**

File-Name Prefix. Führender Buchstabe \'L\' plus Host-Name der
PACS-Station.

Beispiel:

DICOM_TIANI_FILENAME_PRX=LPACS01\_

\

**DICOM_TIANI_DLM** **(MPA_DOC/Dorfmair)**

Zeichen-Delimiter für die Felder der Tiani-Schnittstelledatei.

Wenn nicht gesetzt wird \# verwendet.

\

**DICOM_TIANI_KEY** **(MPA_DOC/Dorfmair)**

TIANI Key - siehe TIANI Schnittstellenbeschreibung. Wenn nicht

gesetzt wird LOAD verwendet.

\

**DICOM_TIANI_STUDIES** **(MPA_DOC/Dorfmair)**

Anzahl der Studien, die geladen werden sollen. Wenn nicht gesetzt

wird 1 verwendet.

\

**DICOM_TIANI_LOAD_SWITCH** **(MPA_DOC/Dorfmair)**

\"Load-Switch\" gibt an, ob die bereits angezeigten Studien gelöscht
oder ob ein

dazu laden erwünscht wird.(1=\"Neuladen\", 2=\"dazu Laden\"). Wenn nicht

gesetzt wird 1 verwendet.

\

**DICOM_TIANI_FILENAME_SFX** **(MPA_DOC/Dorfmair)**

File-Type.Wenn nicht gesetzt wird new verwendet.

\

\-\-\-\--**DICOM-TIANI (neue zuverlässige Variante)**
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**(Alle TianiProperties/TianiSettings, MPA_STEYR/Dorfmair, liegen ab
rel_3.8 im Repo unter doc.dicom.DicomSettings.TIANI\_\....)**

für den Aufruf von Tiani JVision mittels Study Content Notification

(at.co.systema.doc.dicom.view.tiani.JVisionSCNInhaltViewerSupport)

see also ^(55)^*[Documentation 6113: Description of properties within
DicomSettings (since rel_3.8)]{.underline}*

\

**(MPA_DOC/Dorfmair, MPA_STEYR/Dorfmair, liegen ab rel_3.8 im Repo unter
doc.dicom.DicomSettings.TIANI\_jVisionHost)**

**doc.dicom.DicomSettings.TIANI\_jVisionHost**

Gibt den Rechnernamenan, wo Tiani JVision läuft und die Studien
angezeigt werden sollen.

(Default=localhost)

z.B: doc.dicom.DicomSettings.TIANI_jVisionPort=localhost

\

**(MPA_STEYR/Dorfmair, liegen ab rel_3.8 im Repo unter
doc.dicom.DicomSettings.TIANI\_jVisionPort)**

**doc.dicom.DicomSettings.TIANI\_jVisionPort**

Gibt den Port für den Rechner an, wo Tiani JVision läuft und die Studien
angezeigt werden sollen.

Der Port muß mit dem Eintrag \"CMT_RESULT_SRV_PORT\" im Abschnitt
\"\[CHKDBNODE\]\" in der Konfigurationsdatei \"JVISION.INI\"
übereinstimmen!

(Default=5105)

z.B: doc.dicom.DicomSettings.TIANI_jVisionPort=5105

\

**(MPA_DOC/Dorfmair, MPA_STEYR/Dorfmair, liegen ab rel_3.8 im Repo unter
doc.dicom.DicomSettings.TIANI\_.calledAET)**

**doc.dicom.view.tiani.JVisionSCNInhaltViewerSupport.calledAET**

Application Entity Title (AET) des aufgerufenen Rechners; wird dzt. von
Tiani nicht geprüft

z.B.:
doc.dicom.view.tiani.JVisionSCNInhaltViewerSupport.calledAET=calledAET

\

**(MPA_DOC/Dorfmair, MPA_STEYR/Dorfmair, liegen ab rel_3.8 im Repo unter
doc.dicom.DicomSettings.TIANI\_.callingAET)**

**doc.dicom.view.tiani.JVisionSCNInhaltViewerSupport.callingAET**

Application Entity Title (AET) des aufrufenden Rechners; wird dzt. von
Tiani nicht geprüft

z.B.:
doc.dicom.view.tiani.JVisionSCNInhaltViewerSupport.callingAET=callingAET

\

**DocDicomViewTianiProperties.threadTimeout (verwendbar ab rel_3.8 =\>
RepoProperty, MPA_DOC)**

\

Timeout for thread calling Tiani DICOM-Viewers.\<br\>

Im Thread der den Tiani DICOM-Viewer aufruft gibt es eine
Timeout-Behandlung\<br\>

mit entsprechender Fehlermeldung. Über dieses Property kann die Dauer
des Timout\<br\>

festgelegt werden.\<br\>

\

Defaultwert=10

\

\-\-\-\--**DICOM-SIEMENS**\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**(Alle SiemensProperties/SiemensSettings, MPA_STEYR/Dorfmair, liegen ab
rel_3.8 im Repo unter doc.dicom.DicomSettings.SIEMENS\_\....)**

see also ^(56)^*[Documentation 6113: Description of properties within
DicomSettings (since rel_3.8)]{.underline}*

\

**SIEMENS_HOSTNAME**

**(MPA_DOC/Dorfmair, MPA_STEYR/Dorfmair, liegen ab rel_3.8 im Repo unter
doc.dicom.DicomSettings.SIEMENS_host)**

Parameter benötigt beim Funktionsaufruf. Falls nicht gesetzt wird
PC-Hostname

verwendet.

Beispiel:

SIEMENS_HOSTNAME=PACS0001

\

**SIEMENS_GET_ASYNCHRON**

**(MPA_DOC/Dorfmair, MPA_STEYR/Dorfmair, liegen ab rel_3.8 im Repo unter
doc.dicom.DicomSettings.SIEMENS_getAsynchron)**

Holt die Untersuchung asynchron wenn True aus dem Archiv, falls die
Untersuchung

lokal nicht vorhanden ist.

Beispiel:

SIEMENS_GET_ASYNCHRON=True

\

**SIEMENS_ABTEILUNG**

**(optional, (MPA_DOC/Dorfmair, MPA_STEYR/Dorfmair, liegen ab rel_3.8 im
Repo unter doc.dicom.DicomSettings.SIEMENS_department)**

Abteilung des MPA Benutzers. Mit TODO#1861 wird dieses Property
automatisch mit

dem angemeldeten MPA-User gefüllt.

Beispiel:

SIEMENS_ABTEILUNG=username

\

\

**SAP.CreateBatchInput.VV** **(at.co.systema.sap, MPA_KIS, ab rel_3.8 in
Repo unter SapProperties.insuranceCreateBatchInput)**

Versicherungsverhältnisse werden im SAP über BatchInput gespeichert.
Wenn es dabei zu Problemen kommt, kann mit diesem Property ein
BatchInput erzeugt werden, der dann im SAP manuell importiert werden
kann. Beim manuellen Import kann man dann erkennen was das eigentliche
Problem ist.

Ist das Property gesetzt, werden die Versicherungsverhältnisse aus dem
MPA nicht gespeichert. Es wird nur der BatchInput erzeugt !

Beispiel: SAP.CreateBatchInput.VV=true

Default (keine Angabe): false

\

**SAP.CreateBatchInputIfError.VV** **(at.co.systema.sap, MPA_KIS/ab
rel_3.8 in Repo unter SapProperties.insuranceCreateBatchInputIfError)**

Wenn beim Speichern von Versicherungsverhältnisseen eine Exception
auftritt, wird automatisch eine BatchInputMap erzeugt.

Wenn dieses Property eingestellt ist, wird das Property
SAP.CreateBatchInputIfError.VV ignoriert.

Beispiel: SAP.CreateBatchInputIfError.VV=true

Default (keine Angabe): true

 

**sap.DL.ActivePrint** **(at.co.systema.sap, MPA_KIS, ab rel_3.8 in Repo
unter SapProperties.activePrint)**

Steuert, ob der OrgMittelDruck ueber ActivePrint erfolgt

Beispiel: sap.DL.ActivePrint=true

Default (keine Angabe): false

\

\

**sap.DL.GrouperResult.History** **(at.co.systema.sap, MPA_KIS, ab
rel_3.8 in Repo unter SapProperties.grouperResultHistory)**

Steuert, ob im SAP die Historienfuehrung fuers Grouperresult (DRG)
eingeschaltet ist oder nicht

true (default) = ist eingeschaltet, ins SAP wird jedes Grouperresult
geinserted (keine Deletes mehr, Update wird zu Insert)

false = ist ausgeschaltet, im SAP gibts nur max 1 Grouperresult, kann
geloescht u. geupdated werden

z.B: sap.DL.GrouperResult.History=true

\

**SAP.DL.UseModifyMultForWrite** ab rel_3.5 **(at.co.systema.sap,
MPA_KIS, ab rel_3.8 in Repo unter
SapProperties.useModifyMultiForWriteDP)**

Steuert, welche IS-H Methode zum Speichen von Diagnosen verwendet wird.

true \... Es gibt ein BAPI (/SYSTEMA/CASEDIAGNOSIS_MODMULT), das sich um
das Insert, Modifizieren, Löschen von Diagnosen kümmert

false \... (oder nicht gesetzt). Es gibt jeweils ein BAPI zum Insert,
Modifizieren, Löschen. Dies kann aber Probleme beim Ändern von Diagnosen
verursachen (z.B. eine andere Diagnose als Hauptdiagnose)

SAP.DL.UseModifyMultForWrite=true

\

**SAP.UseOptimizedBAPIForLeistungen** ab rel_3.3 **(at.co.systema.sap,
MPA_KIS, ab rel_3.8 in Repo unter
SapProperties.useOptimizedBapiForNLEI)**

Steuert, welche IS-H Methode zum Lesen der Leistungen verwendet wird.

Die ursprüngliche BAPI zum Lesen der Leistungen BAPI_CASESERVICE_GETLIST
konnte keine leistenden Ärzte zu den Leistungen liefern, so dass man je
einzeln noch die Methode BAPI_CASESERVICE_GETDETAIL aufrufen musste, um
auf diese Informationen pro Leistung zu kommen.

Bei einer größeren Anzahl der eingelesenen Leistungen performte diese
Methode sehr schlecht.

Deswegen existiert jetzt eine neue RFC Methode
/SYSTEMA/MPA_CASESERVICE_LIST, die auf einmal alle gewünschen Leistungen
und die leistenden

Ärzte liefert.

true\.....(oder nicht gesetzt = Default) es wird die neue optimierte
BAPI verwendet.

false\...es wird die \'alte\' BAPI verwendet.

\

**statusForMedicalDischarge** **(at.co.systema.dl, MPA_KIS, ab rel_3.8
in Repo unter SAPProperties.statusForMedicalDischarge)**

Gibt an welcher Anwenderstatus aus dem SAP im MPA eine medizinische
Entlassung darstellt (soll heißen das bei der medizinischen Entlassung
im MPA dieser dieser Status gesetzt (und gespeichert) wird). Beispiel:
Wert = \"E0001\"

\

\

**dl.Leistungen.createAmbBewegungen** **(at.co.systema.sap, MPA_KIS, ab
rel_3.8 in Repo unter SapProperties.NLEI_CreateAmbMovement)**

Steuert ob im SAP für Hausleistungen und MELs Bewegungen eine Bewegung
zugeordnet sein muß.

Ist das Property **true** und es ist der Hausleistungen bzw. MEL keine
Bewegung zugeordnet, dann wird beim Speichern versucht automatisch eine
ambulante Bewegung zuzuordnen. Ist das nicht möglich wird automatisch
eine Bewegung erzeugt.

dl.Leistungen.createAmbBewegungen=false -\> in Österreich werden in
diesem Fall keine Bewegungen für HAUS und für MELLeistungen generiert,
in Deutschland werden nur bei HAUSLeistungen keine Bewegungen generiert

default ist true

\

\

**dl.Prozeduren.createAmbBewegungen** **(at.co.systema.sap, MPA_KIS, ab
rel_3.8 in Repo unter SapProperties.NICP_CreateAmbMovement)**

Steuert ob im SAP für OPS in Deutschland eine Bewegung zugeordnet sein
muß.

Ist das Property **true** und es ist der OPS keine Bewegung zugeordnet,
dann wird beim Speichern versucht automatisch eine ambulante Bewegung
zuzuordnen. Ist das nicht möglich wird automatisch eine Bewegung
erzeugt. In Österreich ohne Bedeutung,

dl.Prozeduren.createAmbBewegungen=false -\> in Deutschland werden bei
OPSLeistungen keine Bewegungen generiert

default ist true

\

\

**DL.maxNrOfLockCalls** **(at.co.systema.sap, MPA_KIS, ) \--\> neuer
Name: SAP.maxNrOfLockCalls ab rel_3.8 in Repo unter
SapProperties.maxNrOfLockCalls)**

(Defaultwert ist 10) \--\> Beim Speichern der Diagnosen/Leistungen muss
nach jedem COMMIT ein UNLOCK und sofort nachher ein LOCK abgesetzt
werden.

Diese Property bestimmt die maximale erlaubte Anzahl der Versuche den
Fall zu sperren.

Wenn dieser Wert überschritten wird, kommt eine Fehlermeldung, dass der
Fall durch den User \<USER\> gesperrt wurde und dass das Speichern der
Daten möglicherweise nicht vollständig durchgeführt wurde. Ein leerer
Aufenthalt wird in die DLWorkArea gesetzt.

\

**DL.lockRepeatDelay** **(at.co.systema.sap, MPA_KIS, ) \--\> neuer
Name: SAP.lockRepeatDelay ab rel_3.8 in Repo unter
SapProperties.lockRepeatDelay)**

(Default ist 50 ms) \--\> Es bestimmt die Zeitverzögerung zwischen den
einzelnen Versuchen den Fall zu sperren.

Wenn die Zeitverzögerung grösser eingestellt wurde, ist die
Wahrscheinlichkeit gross, dass schon der ZWEITE Lock Aufruf erfolgreich
ist,

die Performance leidet aber darunter.

Wenn die Zeitverzögerung kleiner eingestellt wurde, ist die Performance
besser, aber die Wahrscheinlichkeit grösser, dass mehrere Lock Aufrufe

gebraucht werden, bis der Fall wirklich gesperrt wird. Damit ist
eigentlich die Performance unter dem Strich schlechter.

Der Defaultwert 50 ms wurde auf SIMBA getestet und liefert relativ
zuverlässig immer nur einen zusätzlichen Lock nötig, um einen Fall
erfolgreich

zu sperren.

Diese Property sollte in dem Echtbetrieb manchmal angepasst werden (wenn
die Applikation mit dem -log dltime gestartet wurde, werden die

Lock Versuche beim Speichern protokolliert, so dass man einen optimalen
Wert finden kann).

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**TELNETUSER ab 1.2 file property, ACT_BASE**

**Wechselt mit Einführung der ActiveDirectory Paßwortüberprüfungsmethode
(rel_3.8.3) ins Repository (TelnetAuthProperties.telnetHost)**

dieses Property wird für die User-Anmeldung über Telnet service
erforderlich. Der OS-User wird so geprüft (nicht SCT-Passwort)

ACHTUNG - ein SCT-User mit dem gleichen Name muss existieren.

\

Beispiel:

TELNETUSER=carlo

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**TELNET_LOGIN_TOKEN**

**Wechselt mit Einführung der ActiveDirectory Paßwortüberprüfungsmethode
(rel_3.8.3) ins Repository (TelnetAuthProperties.telnetLoginToken)**

\

Property fuer die Steuerung des TelNet-Login Token.

\

Nach dem Login über Telnet kommt folgendes:

\

**Last** **login: Wed Feb 26 10:34:31 from lmlap1.systema.c**

**Digital UNIX V4.0F (Rev. 1229); Mi 22 Aug 15:03:49 2001**

\

Alle Strings zwischen Login und OS-Prompt koennen als

moegliche Tokens verwendet werden.

\

zum Beispiel:

TELNET_LOGIN_TOKEN=**login:**

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**KAVInhaltViewerSupport.BrowserPath** (ab rel_3.5)
**(kav.KavProperties, MPA_DOC/Dorfmair, liegt ab rel_3.8 im Repo unter**

**KavProperties.kavContentViewerSupportBrowserPath) (gültig bis inkl.
rel_3.11)**

Anzeigen von Dokumenten aus einem KAV-IGV Archiv erfordert einen
speziellen Viewer.

Der angegebene Viewer wird mit der StudyID als Parameter gestartet

KAVInhaltViewerSupport.BrowserPath=C:\\\\KAV-IGV\\\\ImageArchive\\\\Browser2.exe

\

\

**systemaKISMandant** **(at.co.systema.sap, MPA_KIS, ab rel_3.8 in Repo
unter SAPProperties.systemaKISMandant)**

Mandant für Zugriffe auf SystemaKIS Daten (Befunde,\...) unter SAP

\

\

**COS.KlinischesDokumentEditor.useDefaultAction4Links=true** **(ab
rel_3.8 im repo: RTFProperties, MPA_DOC/Kamleithner)**

Defaultwert: true

Im Normalfall wird beim Aufruf eines Links ein Standard-Editor für das
verknüpfte Objekt aufgeblendet. Es ist möglich bei einem Link explizit
eine Action anzugeben. Wurde eine Action angegeben wird, STATT dem
Aufblenden des Editors, die angegebene Action auf dem Editor
durchgeführt. Dies kann dazu verwendet werden um zB bei Worddokumenten
oder Orders nicht den Header sondern direkt das Formular anzuzeigen.

Diese Property defniert ob, falls keine explizite Action angegeben ist,
eine ev. definierte Defaultaction des Editors verwendet werden soll.

\

**RTFProperties.KlinischesDokumentEditor_defaultFontFamily**

**(ab rel_3.8, RepoProperty:
gf.rtf.RTFProperties.ClinicalDocumentEditor_defaultFontFamily,
MPA_DOC/Dorfmair)**

Sets the default Font used by the RTFEditor.

(Defaultwert = Arial)

\

**RTFProperties.KlinischesDokumentEditor_defaultFontSize**

**(ab rel_3.8, RepoProperty:
gf.rtf.RTFProperties.ClinicalDocumentEditor_defaultFontSize,
MPA_DOC/Dorfmair)**

Sets the default Font Size used by the RTFEditor.

(Defaultwert = 12)

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**sap.BewegungsArtStation** **(at.co.systema.sap, MPA_KIS, ab rel_3.8 im
Repo SapProperties.movementTypWard)**

Fuer Verlegungen auf eine andere Station wird diese BewegungsArt
verwendet, z.B: 3/WS

\

**sap.BewegungsArtBett** **(at.co.systema.sap, MPA_KIS, ab rel_3.8 im
Repo SapProperties.movementTypBed)**

Fuer Verlegungen innerhalb einer Station wird diese BewegungsArt
verwendet, z.B: 3/WB

\

**sap.BewegungsArtUrlaubsbeginn** **(at.co.systema.sap, MPA_KIS, ab
rel_3.8 im Repo SapProperties.movementTypAbsenceStart)**

Bewegungsart fuer Urlaubsbeginn, z.B: 6/PE

\

**sap.BewegungsArtUrlaubsende** **(at.co.systema.sap, MPA_KIS, ab
rel_3.8 im Repo SapProperties.movementTypAbsenceEnd)**

Bewegungsart fuer Urlaubsende, z.B: 7/AE

\

**sap.DestSystemMPA(at.co.systema.sap, MPA_KIS, ab rel_3.8 im Repo
SapProperties.destinationSystemPollingEvents)**

Fuer welches DestSystem werden SAP Events uebers Polling gelesen

Beispiel: sap.DestSystemMPA=MPA_TEST

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**wfl.viewOldPlanungen** **(liegt ab rel_3.8 im Repository unter
WFLAppointmentProperties als viewOldAppointmentPlannings, WFL/Trummer)**

Wielviele Tage sollen versäumte Termine in der Prozessplanung angezeigt
werden.

Falls alle angezeigt werden sollen, Zeile auskommentieren

Beispiel:

wfl.viewOldPlanungen=8 d.h in der ProzessPlanung es werden alle Termine
die nicht älter als 8 Tage sind, angezeigt

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**ProtoEnabled** **(at least since rel_3.4, file property, ACT_BASE)**

**since rel_3.8 located in Repository: ProtocolProperties.protoEnabled**

Hauptschalter für die Protokollierung von DB-Zugriffen durch den
ObjectManager

Beispiel:

ProtoEnabled=true

Default: false

\

\-\-\-\--**Security**\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**Security.enabled (file property, ACT_BASE, Siegfried Kaltenbrunner)**

**since rel_3.8 located in Repository: SecurityProperties.enabled**

Main switch for access control system

Example:

Security.enabled=true

\

**Security.caching (file property, ACT_BASE, Siegfried Kaltenbrunner)**

**obsolete since rel_3.8**

Caching für SecurityCeckPoints

Security.caching=true

\

**Security.SystemUser (file property, ACT_BASE, Siegfried
Kaltenbrunner)**

**since rel_3.8 located in Repository: SecurityProperties.systemUser**

Bestimmt jenen User, der im Berechtigungssystem für \'ALLE USER\' steht
(quasi der WilcardUser)

Beispiel:

Security.SystemUser=SYSTEM

\

**Security.SystemRolle (file property, ACT_BASE, Siegfried
Kaltenbrunner)**

**since rel_3.8 located in Repository: SecurityProperties.systemRolle**

Bestimmt jene Rolle, die im Berechtigungssystem für \'ALLE ROLLEN\'
steht (die Wildcard-Rolle)

Beispiel:

Security.SystemRolle=8

\

**Security.UseSystem.Mpa (file property, ACT_BASE, Siegfried
Kaltenbrunner)**

**since rel_3.8 located in Repository:
SecurityProperties.usingSystemMPA**

Default true

Kann nur true oder false sein. Bestimmt, ob beim Prüfen von
Berechtigungen jene die im MPA erfasst wurden berücksichtigt werden
sollen.

\

**Security.UseSystem.Kis (file property, ACT_BASE, Siegfried
Kaltenbrunner)**

**since rel_3.8 located in Repository:
KisSecurityProperties.usingSystemKIS**

Default false

Kann nur true oder false sein. Bestimmt, ob beim Prüfen von
Berechtigungen jene die im KIS erfasst wurden berücksichtigt werden
sollen.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\-\-\-- **Autom. Starten von
Terminen-**\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**app.AutoStartMetaProzess:** **(liegt ab rel_3.8 im Repo unter
WFLAppointmentProperties als autoStartMetaProzess, WFL/Trummer) -**

Bestimmt, ob das TerminService (WFLAppointmentService) automatisch
Termine starten soll. Fungiert als Genereller Ein- bzw. Ausschalter.

Mögliche Werte: true, false

\

Für Details siehe Customizing Guide - Überblick: Automatisches Starten
von Terminen ^(57)^

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

\

\

\-\-\-\--**SER-Archiv**\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**(alle ser.SerProperties, MPA_DOC/Dorfmair, liegen ab rel_3.8 im
Repo)**

\

**SER.Server_Name** **(ser.SerProperties, MPA_DOC/Dorfmair, liegt ab
rel_3.8 im Repo unter** **SerProperties.archivingServerName)**

Name/Adresse des Rechners und eventuell Portnummer, wo die
SER-Middleware SERframewareDM bzw. Blueline läuft.

(muß vom SER-Archiv-Administrator erfragt werden).

Der Wert wird in MPA nicht verwendet, sondern nur an den SER-Viewer
weitergereicht.

\

z.B. (nur Name des Rechners)

SER.Server_name=MPA989

z.B. (Name und Portnummer)

SER.Server_name=MPA989:4711

\

**SER.ItaSystem_Name** **(ser.SerProperties, MPA_DOC/Dorfmair, liegt ab
rel_3.8 im Repo unter** **SerProperties.itaSystemName)**

**SER.DataBase_Name** **(ser.SerProperties, MPA_DOC/Dorfmair, liegt ab
rel_3.8 im Repo unter** **SerProperties.dataBaseName)**

Name des Systems und der Datenbank (manchmal auch als Teilbestand
bezeichnet), in die archiviert wird (muß vom SER-Archiv-Administrator
erfragt werden)

\

z.B.

SER.ItaSystem_Name=SYSTEM1

SER.DataBase_Name=TEST

\

**(ser.SerProperties, MPA_DOC/Dorfmair, liegt ab rel_3.8 im Repo unter**
**SerProperties.itaSystemUser)**

**SER.ItaSystem_User** SUPERVISOR

\

**(ser.SerProperties, MPA_DOC/Dorfmair, liegt ab rel_3.8 im Repo unter**
**SerProperties.itaSystemPwd)**

**SER.ItaSystem_Pwd** SUPERVISOR

\

**(ser.SerProperties, MPA_DOC/Dorfmair, liegt ab rel_3.8 im Repo unter**
**SerProperties.roleName)**

**SER.RoleName** bisher immer SystemAdministrator

\

**(ser.SerProperties, MPA_DOC/Dorfmair, liegt ab rel_3.8 im Repo unter**
**SerProperties.unitName)**

**SER.UnitName** SystemAdministration

Name und Password des SER-Archiv-Users, sowie Rollen- und Unit-Name, mit
dem archiviert werden soll (muß vom SER-Archiv-Administrator erfragt
werden)

\

z.B.

SER.ItaSystem_User=SUPERVISOR

SER.ItaSystem_Pwd=SUPERVISOR

SER.RoleName=SystemAdministrator

SER.UnitName=SystemAdministration

\

**ser.DOXISOnlineScanning.enabled (ab rel_3.4.3)** **(ser.SerProperties,
MPA_DOC/Dorfmair, liegt ab rel_3.8 im Repo unter**

**SerProperties.enableDOXISOnlineScanning)**

gibt an, ob die Aufenthalt-Action \"callDOXISOnlineScanning\" für den
Aufruf des SER-Online-Scanning verfügbar sein soll. Dieses Property wird
typischerweise im client.properties eines Rechners mit installiertem
Scanner und installiertem SER-Online-Scanning-Programm gesetzt.

(Default=false)

\

z.B.

ser.DOXISOnlineScanning.enabled=false

\

**SER.MaskID (ab rel_3.6)** **(ser.SerProperties, MPA_DOC/Dorfmair,
liegt ab rel_3.8 im Repo unter**

**SerProperties.maskID)**

ID der Ablagemaske für Bluelinearchivierung (muß vom
SER-Archiv-Administrator erfragt werden)

z.B.

SER.MaskID=1003

\

**SER.MaskVersion (ab rel_3.6)** **(ser.SerProperties, MPA_DOC/Dorfmair,
liegt ab rel_3.8 im Repo unter**

**SerProperties.maskVersion)**

Version der Ablagemaske für Bluelinearchivierung (muß vom
SER-Archiv-Administrator erfragt werden)

z.B.

SER.MaskVersion=0000

\

**DELETE_IMPORTED_FILES**

**(ser.SerProperties, MPA_DOC/Dorfmair, liegt ab rel_3.8 im Repo unter
SerProperties.deleteFilesMode)**

Gibt an, welche Dateien nach erfolgreichem Archivieren gelöscht werden
sollen.

[Mögliche Werte:]{.underline}

none \... keine Dateien

all \... alle Dateien

datafiles \... nur die Dateien mit den Images werden gelöscht

Bei einem ungültigen Werte erfolgt ein logger.info(\"..\")

(Default: deleteFilesMode = none)

\

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**Session.defaultUsername** **(file property, ACT_BASE)**

**since rel_3.8 located in Repository:
SessionProperties.defaultUserName**

Der Username, der im Loginfenster vorgeschlagen wird (Default:
\"Username\")

Beispiel: Session.defaultUsername=Systema

\

\-\-\-\--**Telefon**
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

**TelProperties.fillCardNumber** **(at.co.systema.tel, MPA_KIS,** **ab
rel_3.8)**

Dieses Property steuert den Telefondialog bei der Telefonanmeldung.

Sobald dieses gesetzt ist, kann die Wertkartennummer nicht mehr editiert
werden. Sie wird immer mit einem Fragezeichen befüllt.

Von der Telefonanlage wird dieses Fragezeichen über die Schnittstelle
mit der virtuellen Nummer befüllt.

Dies ist sinnvoll, wenn Nachinkasso ohne Wertkartentelefonen im Haus
verwendet wird.

(für gespag ApplixCall 73644, P2 TVS-Ablöse durch PASCOM/BDE)

\

\

**Telefon.inVerlegung** **(at.co.systema.tel, MPA_KIS,** **ab rel_3.8 in
TelProperties.phoneDialogOnTransfer)**

Gibt an welcher Dialog bei Verlegung verwendet wird

nicht gestetzt-\>Telefon nicht berücksichtigt

standard-\>Telefondialog mit dem Viewnamen AufenthaltTelefon.standard
wird verwendet

verlegen-\>ohne Dialog, automatisch nach Stammdaten.

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**rdi.StatementManager.cacheSize** **(at least since rel_3.4, file
property, ACT_BASE)**

**since rel_3.8 located in Repository:
RDIProperties.preparedStatementsCacheSize**

Anzahl der Prepared DB-Statements, die der StatementManager cached
(default=48)

z.B.:

rdi.StatementManager.cacheSize=64

\

\

\
