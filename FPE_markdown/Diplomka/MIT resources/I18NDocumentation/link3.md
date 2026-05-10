---
title: "link3.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/MIT resources/I18NDocumentation/link3.doc"
date: 2010-03-07
type: DOC
---

^(1)^[**?**]{.underline} [**Customizing Guide - Use Case:**]{.underline}
[**I18N-able RepoObjects: relevant settings in property
files**]{.underline}

**Verweis auf Requirement - Use Case:**

\

**Verweis auf Spezifikation:**

Siehe ^(2)^

**Beschreibung:**

**basic mechanism**

-   There is the most general language setting setting for repository
    objects: \<none\>. For every specific language a specific locale is
    possible. Since mpa is german/austrian from its origin the \<none\>
    setting contains german language settings and according to this a
    specific locale for german is not necessary.

-   Specific localisation has in the first a language level like de, en
    and second a country level like en_UK and en_US for United Kingdom
    and United States.

-   The application is started up with a special locale ^(3)^ and tries
    to get the specific synonyms to the technical keywords in use. If it
    does not find an entry, the next - more general level is searched.
    Last level - and most general one - is \<none\>.

\

**property settings and effects**

-   **defaultRepoWriteLocale:**

Where to save after editing a RepoObject? Property \"default
RepoWriteLocale\" defines the standard language setting for writing to
repository.

For every locale it should be the language setting only, without country
extension. (e.g. \"cs\" for czech customers in the area of cs_CZ)

For german speaking customers this is \"none\".

\

**effects in RepoBrowser:**

Defaulting for the setting in \"save as\" dialog; defines the editable
languages in resourcebundle editor table (not inside path \"by object
name\" / \"nach Objektname\")

\

**effects GuiBuilder:**

Default language in opening a view, if not explicitely changed in the
open-view dialog box.

\

-   **availableLocales:**

\...defines a list of all available locales that may be in use. They
appear in any dialog for save settings an can be chosen by the
customizer.

Possible values are the specific locales with country extension;
language settings without the extension are generated automatically.
(e.g. \"de_AT\", \"de_DE\", \"cs_CZ\").

It\'s also in use in the logon-dialog when change of locale is enabled.
(details ^(4)^).

\

-   **locale** und **country:**

To read objects from repository the default locale (from
java.util.Locale.getDefault()) is used, according to to the locale of
default RepoConstraints. Which language is set in default locale is
described in ^(5)^ (and normally the same as in the properties
\"locale\" and \"country\".

\

\

**important annotation**: **for Czech Republic** all localization should
be done on **cs** and **for Slovakia** it should be done on **sk**.
It\'s not supposed here to store something under cs_CZ, sk_SK as because
Jiri Novotny told us we don\'t need any more separation here from point
of the country.

**Details:**

\

**Verweis auf automatische Tests & QS-Templates:**

\

\

\
\

\

\

\

\
