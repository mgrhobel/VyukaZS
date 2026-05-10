---
title: "i18n-editmode.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/MIT resources/I18NDocumentation/i18n-editmode.doc"
date: 2010-03-07
type: DOC
---

^[**(1)**]{.underline}^[**? Spezifikation**]{.underline} I18NEditMode
for Editing of internationalized Repo Objects

+-----------------------------------------------------+---------------+
| Is child document of: ^(2)^ Spezifikation:          | **see also:** |
| Internationalisierung von Repository-Objekten       |               |
|                                                     | \             |
| **Beschreibung:**                                   |               |
+-----------------------------------------------------+---------------+

\

**What does I18NEditMode do?**

For RepoResourceBundleHolder (e.g. Views) all language versions of
ResourceBundles will be loaded and can be used for editing.

\

**Why do we need I18NEditMode?**

For editing of existing internationalized repo objects (e.g. views per
GuiBuilder) will be needed all language versions. Reason: Changes would
does not affect all language versions.

\

practical examples:

-   deleting of controls from view:

-   view will be loaded in german (czech ResourceBundle exists
    additionally). Control will be deleted from view. If there would be
    no information about the czech language version, we would produce
    some dead data in czech ResourceBundle.

-   copying of controls into some other view:

-   view will be loaded in german (czech ResourceBundle exists
    additionally). Control will be copied into some other view. Without
    the czech version would the czech ResourceBundle value absent in the
    target view.

\

\

**How will be I18NEditMode activated?**

By loading of one Repo Object per RepoObjectMgr must be i18nEditMode set
to true in RepoConstraints. So all language versions of ResourceBundles
will be delivered to the client.

\

**Under which circumstances should be I18NEditMode activated?**

Principially I18NEditMode could be activated all the time (the
application would run without problem, not seeing any difference).
However, the I18NEditMode is valuable, because RepoServer has to deliver
all langauge versions all the time and on the client all language
version must be maintained too. This is the reason, why I18NMode should
be asctivated, only wenn international RepoObjects should be read,
edited and saved in repository.

I18NMode is activated in GUIBuilder, RepoBrowser and OWC all the time.
Additionally by initializing of Repo in the respective
DeploymentInitializer classes.

\

**Technical realisation of I18NEditMode**

In case of RepoResourceBundles will be the most specialized language
version substituden by FullRepoResourceBundle. This class administer all
language version of one RepoResourceBundle and contains additionally one
\"workingRB\".

FullRepoResourceBundle implements the interface RepoResourceBundle and
carry out value change operations like removeObject, resp. setObject on
the \"workingRB\". Every changes influencing the language versions (like
changeKey(),

copyEntry(), removeKey() etc.) will be carried out in the language
versions which are not contained in \"workingRB\".

\

Needed classes for implementation of I18NEditMode:

Interface **AllLocalesHolder** (^(3)^): Objects for maintainingof all
language version of one logical object has to implement this interface.

Class**EditableFullResourceBundle** (^(4)^): maintain all language
versions of EditableResourceBundle instances and implements the
interface EditableResourceBundle self.

Class**FullRepoResourceBundle**(^(5)^): Subclass of
EditableFullResourceBundle. The same purpose as
EditableFullResourceBundle, but developed only for RepoResourceBundle
instances.

\

\

\

\

\
