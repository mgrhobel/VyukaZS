---
title: "MIT - Date formats tab.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/MIT resources/TODOs/MIT - Date formats tab.doc"
date: 2010-03-07
type: DOC
---

\

Results from review are here: ^(1)^*[Todo 49446: I18n tools - MIT -
current state review]{.underline}*

\

\

\

**\-\-\-\-\-\-\-\-- 29.10.2009 16:51:26 by Josef Hobel:**

**Table hierarchy**

\- there is only one (default) model for table that presents values from
DateFormatList.xml.

\

**Changes in the table**

\- with any change in date format list and after click the save button
this changes are show in xml.

\- save pattern into xml is skipped when in MITToolkit DateFormats table
is present empty cell.

\- undo button get back any changes on beginning state when MITToolkit
was started for both MITToolkit DateForamt table and DateFormatList.xml.

\- reaload

\

**Problems**

~~- When edit or add new pattern using GUI then in xml could not be
saved in right (default) sort:~~ ~~de_AT,~~ ~~de_DE,~~ ~~cs_CZ,~~
~~en_GB,~~ ~~en_US.~~

\- To save hass been done successfully any change must be confirmed by
enter or click to another cell in the table. Without it save do not know
about new value in table.

\- Undo works good only for first click, for second and others it does
not get back the changes.

\- ~~when MITToolkit is started and xml is changed there is not possible
to show these changes (only start MITToolkit again).~~

\

**Loading patterns from xml**

Loading DateFormats from xml is done by appropriate locale.

When Export is crun (DateFormatList.xml is created) each pattern does
not need to contain all langugages (there could be e.g. only de_AT
patterns). Because of this is not possible to load data into table by
related row and column.

Insted of mentioned problem the DateFormats are loaded into MITToolkit
table correctly.

\

**Save pattern into xml**

There is check that inhibit to save more then one pattern for one
locale. When pattern for locale already exists then old values is
re-writed.

\

**Adding and deleting new rows**

\- for adding new rows must be defined key (de_AT pattern) -\> is is
done by text field. (When this textfield is empty is not possible to add
new row).

\- remove row button delete any selected row.

\

**Unicity check**

\- in the column de_AT there is not possible to add two key with same
value -\> there is statusbar message (Key is already defined) and into
cell is got back original value (apporopriate value from xml is
returned).

\

\

**\-\-\-\-\-\-\-\-- 7.8.2009 16:58:30 by Josef Hobel:**

Almost done,

\

~~I am not able to implement save action - save table changes into XML.
There is no method like setPattern in the DateFormat.~~

\

\

\

**\-\-\-\-\-\-\-\-- 3.8.2009 12:42:14 by Josef Hobel:**

Table with buttons:

add, delete, save, load

\

\

**\-\-\-\-\-\-\-\-- 27.7.2009 14:16:17 by Jiri Kiml:**

\

head_ci\\i18n\\DateFormatList.xml -\> in java it is read via jaxb to
List\<DateFormat\>

\

DateFormatMgr.getDateFormatList() - you will probably have to change
method visibility here to public

DateFormatMgr.writeDateFormatList() - for write()

\

In other words you should create editor/gui for List\<DateFormat\>.

\

\

I think we could use editable jtable + methods like save/reload.

\

\

\

\

\

**\-\-\-\-\-\-\-\-- 25.6.2009 14:48:00 by Veronika Hnizdilova:**

Create a new tab where **DateFormatList.xml** file will be somehow
displayed and will be able to edit/translate there (most likely some
editable table).

\
