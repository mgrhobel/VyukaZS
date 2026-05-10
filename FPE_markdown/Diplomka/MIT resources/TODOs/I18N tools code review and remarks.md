---
title: "I18N tools code review and remarks.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/MIT resources/TODOs/I18N tools code review and remarks.doc"
date: 2010-03-07
type: DOC
---

\

I am not sure what words: problematic translation means.

My suggestions:

1\] I this feature already existts - it is called Filter for longer
phrases. It has been done within todo: ^(1)^*[Todo 44879: MIT - phrases
and their translations overview]{.underline}*

2\] there is e.g. english phrase in e.g. at czech (different from en)
translation.

\

\

\

**\-\-\-\-\-\-\-\-- 14.11.2009 9:45:46 by Josef Hobel:**

\

Based on code review (kiml + hobel)

\

^(2)^*[Todo 44896: MIT - Repo/FileFilter rules definition]{.underline}*

~~-Include for reqular expression is not needed. Display only message
\"Node is excluded because of regular expression
\<regular_expression\>\".~~ done, included in

\

\

^(3)^*[Todo 44891: MIT - I18N objects from Repository
editor]{.underline}* done, included in ^(4)^Change 298427

~~- for saving with blank RepoWriteSettings should be call
RepoWriteSettings dialog for chosing this settings.~~

\- ~~after delete any object to RepoBaseCustomizer get null into
constructor to show no object in the editor.~~

\

^(5)^*[Todo 45975: MIT - Date formats tab]{.underline}*

~~- save button should be done even if user do no accept (by clicking to
another cell or pressing enter) cell change. Automatically leave the
edited cell.~~ done, included in change 302462

\

\

^(6)^*[Todo 44879: MIT - phrases and their translations
overview]{.underline}*

~~ToolTip with context info should be divided into more lines,~~ ~~make
tooltips display longer.~~ done, included in change: ^(7)^*[Change
297995]{.underline}*

~~Add filter for problematic translations~~. already exists, filter for
longer phrases then German ^(8)^*[Todo 44879: MIT - phrases and their
translations overview]{.underline}*

\

\

\

\

\

Via this TODO has been added into MITToolkit these functionalities:

Supporting language column in the Edit Phrases, Import Phrases and excel
file, supporting language dialog for choosing one or none sup. lang.

\

Dictionary tab where is possible to see these phrases that are selected
(Dict. column) in the Edit Prases tab.

\

Status of phrase which allow to switch between two states \"To
Translation\" and \"Postponed\".

\

\

\

\

\

**description:**

\

**\-\-\-\-\-\-\-\-- 5.3.2010 7:12:19 by Josef Hobel:**

\

done with questions

\

\

\

**\-\-\-\-\-\-\-\-- 28.2.2010 13:23:20 by Josef Hobel:**

\

Other improvements done

\- recognizeWorkingTrans - restructuralized

\- table manipulating is done via real columns name - instead of index
(previously used)

table indexes changed to names

interested languages improvements

\

\

\

**\-\-\-\-\-\-\-\-- 26.2.2010 16:56:37 by Josef Hobel:**

\

Remark on import phrases from excel to database:

Columns that **are imported**:

\- Working Translation

\- Translation Comment

\

Columns that **are ingored**:

\- none Locale

\- Original Translation

\- Supporting language

\- Extraction Comment

\- Context Info - in gui tool is visible by tooltip (it is not column),
but it is column in the excel file.

\

\

**supporting locale**

If user choose no supporting locale - no column will be created in the
excel file.

\

Information about \"Number of phrases to Translation\", \"Number of
phrases\" in the dabatabe

This numbers is evaluated when MITToolkit is started. When any change is
done (e.g. status of phrase is changed to Postponed) this information
will not be show immediately in the current instance of MIT. (it will be
showed when MIT will be started next time).

\

\

**\-\-\-\-\-\-\-\-- 25.2.2010 15:49:55 by Josef Hobel:**

\

\

Question: not asked

1\] Should be extraction comment changed in the excel file?

2\] Do Context Info, Filtered Phrases Only comboboxes that are used as
parameters to export into excel. Should their value stored in the
MITProperties?

3\] Translation comment Question:

This time is not possible set comment in the edit Phrases tab.

Is possible to change the phrase comment during work with Import Phrases
tab. After this is possible to change the comment in the excel file
(create new excel file that contains changes).

4\] Manipulating with saving of phrases (see text from 19.2.2010)

5\] Phrases are not sorted.

6\] Number of phrases are not updated immediately in the Project info
tab.

\

\

**\-\-\-\-\-\-\-\-- 19.2.2010 13:26:47 by Josef Hobel:**

\

To see **dictionary tab** there is no need reload button - simply
clicking at tab name the dictionary table will reload automaticly.

Even there is no changes needed. E.g. when user change status -\> then
he click to Dictionary tab -\> The phrase has changed status.

\

For other instance and launching MITToolkit in future next time, click
the **Save changes** button is needed. So save should be clicked at the
end of the work.

\

Same behavior is done for any other phrase change. e.g.:

1\] translation of phrase is changed in the Edit Phrases tab.

2\] [NO]{.underline} save changes is proceed.

2\] Import of excel file

3\] in the \"Original translation\" field of changed phrase (from 1st
step) is visible this changed value - even if phrase is not saved in
database.

\

\

**\-\-\-\-\-\-\-\-- 17.2.2010 16:23:07 by Josef Hobel:**

\

\

**Status of phrase**

postponed \...assigned boolean value = true

to translation \...assigned boolean value = false

\

default status is \"To Translations\" - if is not in the database, then
false is returned.

More concretely: if no phrase with postponed value (true) will be
present in the database , then it will be assigned the default value
(false - to translation).

\

\

\

**\-\-\-\-\-\-\-\-- 9.2.2010 13:17:17 by Jiri Kiml:**

\

Yes you can choose none as supporting language. I do NOT see reason why
we should NOT support it.

\

\

**\-\-\-\-\-\-\-\-- 25.1.2010 16:01:31 by Josef Hobel:**

\

\

Question: Can I choose none as supporting language?

\

\

\

**\-\-\-\-\-\-\-\-- 5.1.2010 15:49:32 by Josef Hobel:**

\

Some part will be separeted into own TODOs

^(1)^*[Todo 49515: MIT - Export phrases from DB to xls
file]{.underline}*

^(2)^*[Todo 49517: MIT - Import phrases improvements + new
functionality]{.underline}*

^(3)^*[Todo 49518: (Edit) Phrase tab improvements]{.underline}*

\

Following parts should be done within this TODO.

\

**Supporting Language** done

Export phrases from DB to xls file:

\- Possibility to choose **one** supporting language e.g. en.

\- Add preffix: \'(sup)\' to column header for selected supporting
language. eg. en (sup)

\

Import from xls to DB

\- Read import file:

Special column for it. Make it better visible. e.g. whole column (or
only header) should have different color then other columns.

Disable editing for sup language column.

\

\- Import Selected Phrases: During import to DB it will be ignored.

\

\

**Edit Phrase** done

\- Actual name is \'Phrases\' -\> rename it as \'Edit Phrases\'

\

\- Add information about status phrase.

There will be combobox for each row (phrase) which contains:

a\] to translations -\> phrases which should be exported into xls file.

b\] postponed -\> not be exported

\

\- Save to DB is needed. When user select one time any phrases, then
other time should be these phrases selected too.

\

\- Add dictionary column

Ii will looks like Select column (checkbox for each phrase), which
already exists. In order of Select column place dictionary column at the
end of columns hierarchy.

\

\- Add tab: Show dictionary

It will show phrases which are present in dictionary only.

It will be similar to Phrases, maybe I can use similar methods.

\

-Add \'Extraction Comment\' extra column - remarks for phrase

There will be table column for it in gui tool. For each phrase own space
to write comment.

When export will be done - then this column will be one string message
for translator.

\

**ProjectViewTab** done

There should be new row in the table, where will be noted the number of
phrases to translations (number of all phrases that has \'to
translation\' status)

\

\

\

\

**\-\-\-\-\-\-\-\-- 4.1.2010 13:59:10 by Jiri Kiml:**

\

~~Result from last personal meeting with Igor:~~

\

~~\@Hobel - TODO has to be translated to English, more complicated tasks
should be moved to separate jobs~~

\

~~(Export phrases from db to xls file)~~

~~Export -\> volba supporting language (AJ)~~

~~- ignorovat ho pri importu.~~

~~- udelat i v MITu (napr. ozncit cely jinou barvou, cely v MITu nepujde
editovat) i v excel filu (napr. u en dopsat sup- supporting language)~~

~~- udelat jenom jeden supporting lang.- to bude stacit.~~

~~- jazyku na preklad muze byt vice.~~

\

\

~~Import~~

~~-nedovolit editovat supporting sloupec.~~

~~-udelat hlavicku jinou barvou napr. zelene.~~

~~-napr. nazev sloupce: en (sup)~~

\

\

\

~~Prejmenovat Phrase tab na Edit phrase~~

\

~~Povolit country specifikace pro vsechny tooli - import/export.~~

\

~~Udelat TODO pro export frazi do filu - novy tab Export phrases~~

~~- button, ktery to spusti~~

~~- jazyky~~

\

\

~~Osetrit, importPhrases pokud nebudou existovat v databazi (zalogovat
jako error).~~

\

\

\

~~Import phrases~~

~~importovat jen jeden jazyk - napr. pote co se soubor nacte vybrat z
comboboxu jeden jazyk k importu.~~

~~viz PITToolkit - zobrazit none sloupec, original z DB, verzi od
prekladatele, translator comment, extraction comment - komentar co
napisu ja k prekladatelovu prekladu.~~

~~nacitat jen jednou.~~

~~nacist 2 mnoziny - nove phrases (ktere v databazi neexistuji) nebo
zmenene (v db jiz existuji).~~

~~horizontal scroll.~~

\

~~- filter (radiobuttony)~~

~~1\] all translations: vsechny zmenene + nove.~~

~~2\] zmenene~~

~~3\] nove~~

\

\

~~Komentare~~

~~- Translator comment - not editable~~

~~- muze byt i zmeneny - pokud translator udelal (pri druhem prekladu)
zmenu, jinak barevne~~

~~- extraction comment - editable.~~

\

~~Edit phrase~~

~~- status phrase (combobox)-\>~~

~~a\]to Translation -\> phrase, ktere se maji vyexportovat do xls.
filu.~~

~~b\] posponed -\> nemaji se vyexportovat~~

~~-\> udelat dalsi radek v ProjectView tabu: Phrases to be translated -
zde bude pocet phrasi, ktere obsahuji translated status.~~

~~extracted phrases jiz MITToolkit obsahuje (numberOfPhrases).~~

\

~~- dictionary column - phrase, ktera muze byt zarazeno do dictionary -
hlavni souhrn phrasi. Prekladatel nejprve prelozi dictionary a pak na
zaklade toho muze programator pomoci prekladateli s prekladem.~~

~~- extraction comment -\> co ta phrase skutecne znamena.~~

\

~~\|mnemonics~~

~~- hotkeys - mnemonics - prilis lokalni zalezitos -\> prekladatel s tim
nic neudela.~~

~~- staci jen jedna phrase, pokud je na vice mistech pro prekladatele
-\> pokud bude 1 phrase na vice mistech a bude mit rozdilne mnemonics,
pak to prekladatel stejnak nemuze spravne prelozit, protoze nevi zda
neudela kolizi v mnemonicsech.~~

~~-\> zatim mnemonicsy vynechame(nebudeme delat zvlastni sloupec),
dodelame je az na konci.~~

\

\

~~Phrase View Rules~~

~~- zatim neni potreba~~

~~- muzeme pozdeji pouzit regularni vyrazi ve stejnem smzslu jako pri
exclude/inlucde messagebundlu, repoRessourceBundlu.~~

\

~~\|Find phrase context~~

~~- button, ktery vytvori 2 views pro danou phrasi (stejne jako v 6.
bodu)~~

~~- ve kterych repoRessourceBundles se nachazi dana phrase~~

~~- ve kterych MessageBundlech se nachazi dana phrase~~

~~-\> pokud dam double click na danou phrasi tak mi to z repository
skoci do viewsOverView a z messagebundlu skoci do MessageBudnle
editor.~~

\

\

\

\

**workaround:**

\

\

\

\

A\] supporting language

1\] start MITTolkit

2\] select the Edit Phrases tab

3\] ensure that in the current project are contained any phrases

4\] export these phrases to excel file - via Export button.

5\] dialog for specifing exporting locales and supporting locale is
visible

6\] choose any suporting language

7\] import excel file into MITToolkit gui - via Import Phrases tab

8\] table is filled with values from excel file.

7\] There must be columns with specified locale and suffix: (sup) -\>
must not be editable and must contain right translations as related
locale in the database.

\

B\] Dictionary tab

1\] start MITTOolkit

2\] there must be the Dict. column at the end of table.

3\] select some checkboxes and remeber theirs none value.

4\] goto Dictionary tab

5\] there must be visible these phrases which has been selected.

6\] click the save button in the Edit Phrases tab

7\] exit MITToolkit

8\] start MITToolkit again -goto Dictionary tab -\> there must also be
all selected phrases from Edit PHrases dictionary column.

(if save button would be clicked then will be not possible to see
phrases in the dictionary when MITToolkit start within new instance)

\

C\] Status phrase and Number of phrases to translation

1\] start MITTolkit

2\] goto Edit Phrases tab

3\] there must be visible the Status column

4\] for each phrase should be available two possibilities - \"To
Translation\" and \"Postponed\". Default value is \"To Translation\"

5\] Change any phrase status to \"Postponed\".

7\] click the save button

8\] exit and start MITToolkit again

9\] Project info tab contains statistics: \"Number of phrases to
Translation\" which show how many phrases have \"To Translation\" status
-\> this number shouls be smaller so much from \"Number of phrases\"
number for many phrases has been selected \"Postponed status.

\

D\] Delete translation from database

1\] start MITToolkit

2\] goto Edit phrases tab

3\] set any translation to empty string, remmeber the changed phrase.

4\] exit and start MITToolkit again

5\] in the chagned phrase there should be empty string translation -\>
it means that no I18N_TRANS VALUES record is present in the databse.

\

\

\

\

\

**description:**

\

**\-\-\-\-\-\-\-\-- 21.1.2010 11:14:58 by Josef Hobel:**

\

\

**DateFormat done** done, included in ^(1)^*[Change 302462]{.underline}*

I decided to remove undo functionality - it is problematic and low
useable.

\

**Warnings** done, included in ^(2)^*[Change 302462]{.underline}*

\

**Repository** **done,** included in ^(3)^*[Change 302560]{.underline}*

repoDirectories must be skipped, instead of this the tab initialization
is really slow:

gf.mvc.dict.CollectionViewAttr.I18N

gf.mvc.dict.ColumnViewAttr.I18N

\

When user click the repository tab, then all I18N repo objects are
browsing - for each must be create own jtree node. Directories with many
repoObjects have slow progress.

Used solutins: Browsing the repoDirectories only when user click the
directory - similar functionality as in repoBrowser.

\

in progress

**QA** will be done after ^(4)^*[Todo 49515: MIT - Export phrases from
DB to xls file]{.underline}*

\

\

\

\

**\-\-\-\-\-\-\-\-- 13.1.2010 13:19:39 by Jiri Kiml:**

\

I do review for more than one job, so I dediced to collect all findings
here (intead of reopening of many jobs).

\

^(5)^*[Todo 45975: MIT - Date formats tab]{.underline}*

[![](I18N%20tools%20code%20review%20and%20remarks_html_46ee06a4.png){#Image1
align="bottom" width="987" height="193" border="0"}]{.underline} It is
unclear what is difference between Undo and Reload button. Please add
tooltips with explanation to buttons.

\

FilesEditor, RepoRBsEditor, RepoRBsModel - please clean warnings inside
(you should NOT submit anything with warnings).

\

\

^(6)^*[Todo 44891: MIT - I18N objects from Repository
editor]{.underline}*

**Problem**

repoDir contains \"ViewAttr\" must be skipped, if not reading the
repoObject is too much time consuming.

**What does the sentence above mean?**

\

\

Please do QA for:

^(7)^*[Todo 45768: Export comments to translation excel file
too]{.underline}*

^(8)^*[Bug 48952: I18NPhrases import problem - duplicit keys in the
hsqldb.skript]{.underline}*

\

\

\
