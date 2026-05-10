---
title: "MIT - checkbox for DateFormatExport_Import in Export_Import .doc"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/MIT resources/TODOs/MIT - checkbox for DateFormatExport_Import in Export_Import .doc"
date: 2010-03-07
type: DOC
---

\

**fixed**

\

\

**\-\-\-\-\-\-\-\-- 27.10.2009 7:45:33 by Jiri Kiml:**

\

DateFormatExport fails becase of YOUR changes in it: see Change 292576

**initDefaultLocale() was/has to be called BEFORE**

**final** DateFormatExport F_exp = **new** DateFormatExport(P_repoOwner,
P_locale);

\

Similar can be said about DateFormatImport

***initDefaultLocale*****() was/has to be called BEFORE**

**final** DateFormatImport F_imp = **new** DateFormatImport(P_repoOwner,
P_locale);

\

\

**\-\-\-\-\-\-\-\-- 20.10.2009 16:39:07 by Josef Hobel:**

\

My task is done, but I am not sure if application logic of DateFormat
work well.

\

\

DateFormat Export/Import is possible to run separetely without
Repository export/import

Default values is set to false.

\

\

\

**\-\-\-\-\-\-\-\-- 29.9.2009 12:14:13 by Jiri Kiml:**

\

If you have list of locases and DateFormatExport/Import takes only one
locale, you have to run it multiple times for every locale in the list.

\

\

**\-\-\-\-\-\-\-\-- 21.9.2009 18:24:38 by Josef Hobel:**

\

\

Now is possible to run Export (Export MessageBundle + RepoRBs to DB
**or** export DateFormats) for same set locales.

ExportDB runs good with list of locales, but DateFormatExport/Import run
with only one locale.

\

How should I solve it?

\

\

\

**\-\-\-\-\-\-\-\-- 1.9.2009 9:09:40 by Jiri Kiml:**

\

What is current state ?

\

\

**\-\-\-\-\-\-\-\-- 25.8.2009 15:24:27 by Josef Hobel:**

\

\

Is possible to call DateFOrmatImport/Export with list of locales? This
time is possible to call only with one locale.

\

\

**\-\-\-\-\-\-\-\-- 29.6.2009 13:29:26 by Jiri Kiml:**

\

see classes: DateFormatImport

and DateFormatExport

\

There could be problem that files are in p4 and written during export
and no p4 handling (open for edit) is done now.

(hint: p4helper class).

\

\

**\-\-\-\-\-\-\-\-- 25.6.2009 13:51:22 by Veronika Hnizdilova:**

import tab - add checkbox for DateFormatImport (true by default) - only
for Repository import

export tab - add checkbox for DateFormatExport (true by default) - only
for Repository export

\

\
