---
title: "link1.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/MIT resources/I18NDocumentation/link1.doc"
date: 2010-03-07
type: DOC
---

^(1)^[**?**]{.underline} [**Documentation - Use Case:**]{.underline}
[**Language choice dependent on the user**]{.underline}

\

^(2)^ Documentation: Folgen einer Sprachänderung

^(3)^ Documentation Use Case: Explizite Sprachwahl des Benutzers beim
Anmelden

^(4)^ Documentation Use Case: Wahl der Standardsprache

^(5)^ Documentation Use Case: Wahl der Sprache, die dem Benutzer
hinterlegt ist

**Verweis auf Requirement - Use Case:**

\

**Verweis auf Spezifikation:**

\

**Beschreibung:**

The following **strategy to choose the language** will be taken:

1.  Take the language setting which will be explicitely set by the user
    during login. ^(6)^

2.  Take the language setting which will be related to the user. ^(7)^

3.  Take the language setting which will be defined in the
    customer.property file. ^(8)^

\

The strategy will be used in the following use cases:

-   The user will be choosen during application start.

-   The user will be changed during application run within mpa

-   The workspace will be locked and the lock will be lifted.

\

Consequences of a language change: ^(9)^

**Details:**

\

**Logging of chosen language at program start**

\

You have possibility to see why the currently used language (locale) was
taken. You have to turn on gf.session.Session logger to DEBUG level - to
do it start program with parameter -log gf.session.Session.

\

What can be printed by this logger for following strategies to choose
the language (default language was cs and was changed to en):

**1. Language setting was explicitely set by the user during login**

\

DEBUG \[AWT-EventQueue-0\] gf.session.Session () : Using explicitely
given locale settings

DEBUG \[AWT-EventQueue-0\] gf.session.Session () : Locale seetings
modified from: cs_CZ to: en_GB

\

**2. Language setting is related to the user**

\

DEBUG \[AWT-EventQueue-0\] gf.session.Session () : Using locale settings
of the new user.

DEBUG \[AWT-EventQueue-0\] gf.session.Session () : Locale seetings
modified from: cs_CZ to: en_GB

\

**3. Language setting is defined in Repository
(gf.actproperties.I18NProperties)**

\

DEBUG \[AWT-EventQueue-0\] gf.session.Session () : Using locale settings
of the new user.

DEBUG \[AWT-EventQueue-0\] gf.session.Session () : User USERNAME has no
associated locale

DEBUG \[AWT-EventQueue-0\] gf.session.Session () : \--\> Using default
locale settings from properties.

DEBUG \[AWT-EventQueue-0\] gf.session.Session () : Locale settings stay
at: en_GB

\

Related to the language and country codes see the following URL\'s:

-   language: http://www.loc.gov/standards/iso639-2/php/code_list.php

-   country:
    http://www.iso.ch/iso/en/prods-services/iso3166ma/02iso-3166-code-lists/list-en1.html

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
