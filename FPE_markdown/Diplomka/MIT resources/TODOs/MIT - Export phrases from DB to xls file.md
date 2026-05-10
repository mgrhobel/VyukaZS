---
title: "MIT - Export phrases from DB to xls file.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/MIT resources/TODOs/MIT - Export phrases from DB to xls file.doc"
date: 2010-03-07
type: DOC
---

**description:**

\

**\-\-\-\-\-\-\-\-- 5.3.2010 8:05:28 by Josef Hobel:**

\

\

Instead of DEVDIR for creating excel file is now used
I18NDefs.*I18N_DIR.*

if DEVDIR exists then i18n.tools project working directory is used,

if not i18n.tools project working directory in **MPA_ROOT** is used.

\

\

\

**\-\-\-\-\-\-\-\-- 28.2.2010 12:14:49 by Jiri Kiml:**

\

Reopened because of Igor\'s note bellow.

Use I18NDefs.*IS_DEV_ENV*to determine if dev dir exists if you need it.

Maybe you could simply use I18NDefs.*DEFAULT_ROOT_DIR* insted of you
DEVDIR.

\

\

\

**\-\-\-\-\-\-\-\-- 14.02.2010 12:44:11 by Igor Böhm:**

Look out!

\

This functionality has to work not only from Development Environment, so
you have to handle the setting of

rootDir default in more complex way.

You have written:

rootDir is set as default to DevDir\\gf2.i18n.tools

\

You should take a look into some other places in i18n package, where
devDir is used.

You will find out, that if there is no devDir, then mpaRoot is used.

Check it, maybe I have not remembered perfectly how it does work, but it
should be done

approximately in this way.

\

\

**\-\-\-\-\-\-\-\-- 9.2.2010 13:44:30 by Josef Hobel:**

\

\

done with change 303994

\

\

\

**\-\-\-\-\-\-\-\-- 6.2.2010 15:28:10 by Josef Hobel:**

\

\

Export will be possible use in two ways. First export all phrases in
current I18N project. Second export all filtered phrases in the view
(e.g. export phrases that are not translated only).

\

\

rootDir is defaulty se to DevDir\\gf2.i18n.tools

fileName consist of I18NProjectName_localesToExport_reference.xls

\

\

\

**\-\-\-\-\-\-\-\-- 26.1.2010 14:18:31 by Josef Hobel:**

\

Get languages from interested langues from MITHeader.

Do not own tab. add new action button to phrases tab, after it show
dialog for selecting sup language.

\

\

\

**\-\-\-\-\-\-\-\-- 19.1.2010 10:37:24 by Josef Hobel:**

\

Implement it as new tab in the gui tool, it will contains not many
components.

\

\- One button which start the export.

\- List of languages intended for translation which will be possible to
select .

\- Combobox for selecting supporting language. List of available
supportig lang should not contain selected language for translation.

\

\

\

\

\
