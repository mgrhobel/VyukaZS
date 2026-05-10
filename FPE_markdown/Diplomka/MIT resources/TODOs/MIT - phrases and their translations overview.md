---
title: "MIT - phrases and their translations overview.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/MIT resources/TODOs/MIT - phrases and their translations overview.doc"
date: 2010-03-07
type: DOC
---

\

\

\

**description:**

\

**\-\-\-\-\-\-\-\-- 2.12.2009 6:44:45 by Josef Hobel:**

\

Additional changes

AbstractResourceBundleImport.importFromFIleToDB() has been divided into
2 methods, in order to be use in MITToolkit.

\

**Problem**

Importing phrases are added into hsqldb.skript, but is it should
overwrite original phrases and their translation values. In other words,
after import there are 2 same keys.

Separate bug created for it: ^(1)^*[Bug 48952: I18NPhrases import
problem - duplicit keys in the hsqldb.skript]{.underline}*

\

**\-\-\-\-\-\-\-\-- 30.11.2009 23:23:51 by Josef Hobel:**

\

\

Created ImportTab.

The behavior of ImportTab mostly correspond to PITToolkit ImportTab.

1\] At first must be **specified the xls file** (that had been previosly
exported from DB).

2\] In **second step** must user specified the Iocales (from Interested
languages panel) - there must be selected these locales that had been
exported. In other way an exception throws.

3\] After then is possible to show the file in MITToolkit. For this
function there is **Read button**.

\- There is possible to run Read procedure in two ways :

a\] different translations - Only these translations that are changed or
different, or in db are not present will be show. The value because of
the all row (values for all locales) has been added into jtable is
highlighted with yellow color and italic font. The user can see very
fast different values.

For each cell there is **Tooltip** that shows related valued from hsql
database.

b\] All translations - there is no limitation.

\

4\] Botton control panel that provide **import** **selected rows** into
database.

RadioButtons reload the table base on which rows are selected or
deselected. - So they provides only view behavior.

\

\

\

\

\

**\-\-\-\-\-\-\-\-- 18.11.2009 6:25:57 by Josef Hobel:**

Added Phrases filter that contains these filter rules:

All Translations (no filter),

Not translated Phrases,

Longer Phrases in \<selected available language\> then in German.

\

There was few problems with reload button and its synchronization with
filter. It was needed to add each one only specific functionality:

Reload should only updates table base on available languages,

filter should only updates table on filter rules.

\

\

**\-\-\-\-\-\-\-\-- 11.11.2009 15:56:22 by Josef Hobel:**

\

Added Reload button, that recreate table base on available languages.
E.g. when cs language is deselected from available languages, then is
clicked on reload -\> the whole **cs** column id removed from the table.
It is also possible to get cs col;umn into table back (by selecting cs
and click the reaload).

\

Added mechanism that colors cells when the translation is more (or much
more) then phrase. (Like at the first screenshot at the bottom of this
document).

\

\

\

**\-\-\-\-\-\-\-\-- 6.11.2009 9:16:34 by Josef Hobel:**

\

Now is possible to show table that contains all phrases and theirs
translations.

There was problem with phrases that contains any HTML tags, defaulty
swing show formatted text into HTML. In internationalization is needed
to show text with html tags. So **I disabled the default cell renderer
from parsing the html.**

\

\

\

\

![](MIT%20-%20phrases%20and%20their%20translations%20overview_html_14bdebd.gif){#Image1
align="bottom" width="1449" height="836" border="0"}

\

\

\

![](MIT%20-%20phrases%20and%20their%20translations%20overview_html_f7ef4218.gif){#Image2
align="bottom" width="1449" height="836" border="0"}

\

\

\

**\-\-\-\-\-\-\-\-- 28.4.2009 10:43:56 by Veronika Hnizdilova:**

Add a new tab to MITToolkit, something like \"Phrases\". There will be
displayed a table with all existing phrases and all available
translations. Some columns of the table are editable, particularly
translations.

For each phrase provide a context menu action that would display all
file and repo contexts. When a repo context is selected and if it is a
view, there is a possibility to display the view in view i18n editor
(will be done by ^(2)^*[Todo 44876: MIT - view I18N
editor]{.underline}*).

\

\
