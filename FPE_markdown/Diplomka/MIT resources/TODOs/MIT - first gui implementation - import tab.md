---
title: "MIT - first gui implementation - import tab.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/MIT resources/TODOs/MIT - first gui implementation - import tab.doc"
date: 2010-03-07
type: DOC
---

**\-\-\-\-\-\-\-\-- 23.6.2009 17:49:33 by Josef Hobel:**

Import panel adds two parameters extra. All others are same both for
import and export - in this case was created parent for these same
components.

\

There was problem with rootDir path. Its starting point was different
from DEVDIR path. RootDir use c:/depot/head_ci and DEVDIR use
c:/depot/HEAD_CI.

Now all characters in both paths are set to lowerCase.

\

Created also mechanism which check if rootDir, repoDirPattern are not
empty and locales are not selected.

\

When import is started and some values from DB are different from
depot - new messageBox with question - \"Do you want to overwrite
translation\" is visible.

\

\

**\-\-\-\-\-\-\-\-- 16.4.2009 14:20:18 by Veronika Hnizdilova:**

at.co.systema.gf.i18n.AbstractResourceBundleImport.askForOverwriteOriginalTranslation()
has to be changed - it asks an user a question, currently in console
output only.

\

**\-\-\-\-\-\-\-\-- 16.1.2009 12:17:18 by Veronika Hnizdilova:**

Create the next tab in the gui tool - setting of all import parameters
and a button that launch the import process will be available there.
Display what is being imported and where.

\

\
