---
title: "MIT - Import phrases improvements + new functionality.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/MIT resources/TODOs/MIT - Import phrases improvements + new functionality.doc"
date: 2010-03-07
type: DOC
---

\

\

\

New functionality and some improvements o importing excel file into MIT
database has been done

-main working language must be now selected before importing phrases

-Imported phrases is possible to filter by 3 rules: New Translations,
Changed and both.

\- all table columns structure reworked - none phrase, working language,
original translation, Translator comment, Extraction comment.

\

\

\

\

\

**description:**

\

**\-\-\-\-\-\-\-\-- 29.1.2010 19:05:18 by Josef Hobel:**

\

done with ^(1)^*[Change 303411]{.underline}*

\

\

**\-\-\-\-\-\-\-\-- 29.1.2010 18:48:28 by Josef Hobel:**

\

**Questions**:

~~- Should be table sorted by none column and asc/desc order?~~

~~- Extraction comment is possible to edit in the MIT table. Is is OK?~~

~~- Context info for phrase is visible from tooltip.~~

~~- different translation comment - has red color, there is possible to
show differencem from last (from the DB) and actual (from the XLS)
comment~~ ~~**by tooltip.**~~

\

**Working language**

list of avilable working language is gathered from selected
I18NInterestedLanguages. It is fully work solutins. For gethering
available working locale list from xls file is need some change in the
[AbstractResourceBundleImport]{.underline} class. So I choosed first
way.

\

**Interested languages**

Within this TODO I decided to do some improvements in
I18NInterestedLanguages class.

\

There is implementation problem (not function problem)

\- 18NInterestedLanguages.*getInstance.getFilter*() method, after remove
/ add in the new variable of filter - changes will be show into single
instance too.

-\> Add avoid this problem by creating new instance.

\

\

\

**\-\-\-\-\-\-\-\-- 27.1.2010 16:57:29 by Josef Hobel:**

\

**Created filter**

\- after read procedure, is possible to filter table base on following
rules:

\

Different translation: imported phrase is different from related db
phrase.

New translations = empty DB phrase.

All translations = different + new + same imported phrase as related db
phrase

\

\- after import procedure, the table is not updated (only database). If
user would like to see the imprted changes in the table -\> **read
procedure must be activated again.**

\

\

**\-\-\-\-\-\-\-\-- 26.1.2010 14:47:02 by Josef Hobel:**

\

show dialog for selecting imported language (only one) **after read
import file**, gather languages from xls file header.

\

~~\'All Translations\', \'Only selected translations\' radiobuttons
should not update the table - it is used only for import into DB.~~

\

~~Different Translations - it is needed to show only different from DB
(not all !)~~

\

~~Example:~~

~~Different Translations and Only selected translations will be
selected, then import only these phrases (not all phrases).~~

\
\

\

\

**\-\-\-\-\-\-\-\-- 19.1.2010 10:51:33 by Josef Hobel:**

\

First implementation of Import phrases has been done in ^(2)^*[Todo
44879: MIT - phrases and their translations overview]{.underline}*.

There are things to be done newly or improved:

\

-   ~~There will be combobox for choosing translation language - only
    one language to import from more available langs. in xls file.~~

\

-   ~~import tab will have structure similar to PITToolkit.~~

**There will be these columns:**

None language columns,

Original Translation (from DB),

Translated Phrase (version from translator),

\

Translation Comment - Not editable. MITToolkit should recognize that
translator changed in second version the comment - make it visible by
any color.

Not visible in the Edit Phrase tab. Visible only in the Import tab.

\

Extraction Comment - Editable. (place for MITTolkit user where could
write remarks for phrases and their translations).

\

\

\

-   ~~Add horizontal scroll.~~

\

-   ~~filter of imported phrases should contain following functions:~~

1\] all translations (changed translations + new translations + same
trans. ) 2\]changed translations 3\] new translations

\

It is needed to **read xls file only one time** and do any operations
after it.

need to read again:

when user change selection of available languages

\

NOT need to read again:

after any filter change

after translation language choice

\

-   ~~When any imported~~ ~~**phrase**~~ ~~will not be present in DB
    then log this operation as ERROR.~~

It could happen when translator change the german phrase (key phrase in
MITToolkit).

\

\

\

\

**workaround:**

\

\

\

1\] run MITToolkit

2\] goto Import phrase tab

3\] point file path to excel file with imported phrases

4\] select appropriate locales in the interested language checkboxes.
Each locale presented in the excel file name must be selected!

5\] click the read button -\> dialog box for choosing working language
should be visible.

6\] select working language and click the OK

7\] after while, imported phrases should be visible.

\- result: different + new + same imported phrase as related db phrase

\- imported phrases not presented in the DB is logged as Error level.

\

A\]

8\] Import phrases to database - import all / only selected phrases.

9\] check if imported phrases is visible in the database.

\

\

B\]

8\] click the different/new phrases filter radio button.

9\] import these phrases if exist at least 1 - else skip thi test.

10\] click the read button again

11\] click the diff/new filter radio button again -\> table should be
empty.

\
