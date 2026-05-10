---
title: "MITT, Repo_FileFilter rules definition.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/MIT resources/TODOs/MITT, Repo_FileFilter rules definition.doc"
date: 2010-03-07
type: DOC
---

**\-\-\-\-\-\-\-\-- 17.8.2009 15:10:25 by Josef Hobel:**

done

with head_CI change 284204

\

intergration to rel_3.12, rel_3.12.1 done.

\

\

**\-\-\-\-\-\-\-\-- 13.8.2009 13:56:43 by Jiri Kiml:**

\

Reopened:

1\. Make sure that i18n/DefaultFileter.xml is NOT open for edit in p4.
Choose one node in the tree and press exclude -\> exception happend
because

DefaultFilter.xml is NOT writable. It is good behaviour, no problem till
now. But if I click node again I see \"Include\" instead of \"Exclude\".

![](MITT,%20Repo_FileFilter%20rules%20definition_html_b2fffe2.png){#Image1
align="bottom" width="1280" height="750" border="0"}

\

2\. MessageBundleTabController - remove **public** **static** String
getSelectedFilePath().

It is now used in MessageBundleEditorPanel. MessageBundleEditorPanel
could NOT know about controller.

Controler should provide such info to MessageBundleEditorPanel instead.

Controler should add listener to tree (to obtain file path) and pass it
to MessageBundleEditorPanel.

\

\

**\-\-\-\-\-\-\-\-- 11.8.2009 13:22:08 by Josef Hobel:**

done with change 283530

\

**\-\-\-\-\-\-\-\-- 11.8.2009 11:42:34 by Josef Hobel:**

\

On the basis of folowing TODO: ^(1)^*[Todo 44896: MIT - Repo/FileFilter
rules definition]{.underline}*

\

**Added functionality: Expands/Collapse fileTree to a selected tree
node**.
