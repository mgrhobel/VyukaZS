---
title: "MITT, MessageBundle files editor.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/MIT resources/TODOs/MITT, MessageBundle files editor.doc"
date: 2010-03-07
type: DOC
---

**\-\-\-\-\-\-\-\-- 28.7.2009 8:17:27 by Josef Hobel:**

done head_ci: ^(1)^*[Change 282263]{.underline}*

integrated into rel_3.12 with chagne 282264

\

**\-\-\-\-\-\-\-\-- 19.7.2009 17:20:04 by Josef Hobel:**

\

almost done,

\

prepared to submit, but not have been done yet - because some problems
with perforce.

TODO Jiri Kiml - check my changelist, if good please submit it.

\

\

Added button, that save current changes into MessageBundle.proeprties.
Now methos exitRoutine() is only hadnled by this button. Maybe future
feature: when user do some changes and click the exit this method should
be called too.

\

AbsolutePathToHierarchyTest :

DefaultMutableTreeNodeTest:

\- created but need some improvements there will be submited next time

\

\

Commentary to new classes .will be done in close future.

Exception loggers will be done in close future too.

\

\

TestInstructions:

\

1\) run MITToolkit

2\) goto MessageBundles tab

3\) select any MessageBundle.properties from tree

4\) this MB is loaded into right panel with all languges version if
exists

5\) Select a language for which you want to write translations from the
list of languages in upper left. In this example \"Italian\" has been
selected.

6\) Select a translation key from the list in the lower left.

7\) Type the translation into the \"Translated Text\" section.

8\) Type comment

9\) ensure that MessageBundle is writable

9\) click the SaveChanges button

10\) check in .properties file that you changes has been done.

\

\

**\-\-\-\-\-\-\-\-- 28.4.2009 16:24:57 by Veronika Hnizdilova:**

Add a new tab to MITToolkit, something like \"MessageBundles\".

There will be displayed a tree with all MessageBundle files (for none
locale only) on left side and some kind of MessageBundle editor on right
side. The editor can be somehow exctracted from already existing
at.co.systema.gf.i18n.ostermiller.MessageBundleEditor and it should be
able to edit RB-entries for all existing MessageBundle files.

\
