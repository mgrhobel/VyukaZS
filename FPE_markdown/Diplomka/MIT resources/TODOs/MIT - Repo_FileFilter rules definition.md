---
title: "MIT - Repo_FileFilter rules definition.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/MIT resources/TODOs/MIT - Repo_FileFilter rules definition.doc"
date: 2010-03-07
type: DOC
---

\

\

\

\

\

\

\

**description:**

\

**\-\-\-\-\-\-\-\-- 3.12.2009 17:09:01 by Josef Hobel:**

FileFIlter,improvement - disallow include filePath specified by regular
expression

base on ^(1)^*[Todo 48704: I18N tools code review and
remarks]{.underline}*

\

**RepoFilter done**

It has similar functionality as Filter. It is possible to export only
specified items -\> no regular expressions.

When exclude/include is called under repoDir, then all related
**repoObject** are **colored to gray** in the tree, into **FileFilter**
were added related **repoIDs.**

\

\

Notice

disallowance include repoPath by regular expression is not assumed.
There are no filePath items specified by regular expression in the
DefaultFilter.

RepoFIlter for RBKey is not done.

\

\

\

\

**\-\-\-\-\-\-\-\-- 28.10.2009 19:51:38 by Josef Hobel:**

This time is possilble to exclude/include more MessageBundles (under
selected dir) at one time.

\

**Added functionality**

Regular expression is possible to add manually only into
DefaultFilter.xml.

\- Exclude works for Separate messageBundles only.

\- Include regExp is possible by MITToolkit.

-There is no way to include only part of files that has been excluded by
regexp.

\

\

Exclude/Include context menu items and statusbar messages

\- there are both Exclude and Include items and they are enabled for all
times.

\- If all MessageBundles are excluded under selected dir. There is
possible to click the exclude, but statusbar message \"No MessageBundled
are availabe for Exclude\" is visible.

\- If all MessageBundles are included (are not present in
DefaultFilter.xml). There is possible to click the include, but
statusbar message \"No MessageBundled are availabe for Include\" is
visible.

\

Excluding/Including **more MessageBundles** at one time (under selected
dir)

\- Click the Excluded/Include for any DIR -\> it will exclude/include
**all MessageBundles** under this dir.

\- If minimally one MessageBundle is not Excluded/Included the operation
Exclude/Include is run for this left MessageBundle(s) only.

\

Color tree highlighting

\- Excluded MessageBundles has gray color.

\- There is not possible to color directories.

\

\

**Problem:**

Show excluded files checkbox works only with MessageBundles (no
directories)

When FileFilter.xml contains any excluded files and Show excluded files
checkbox is **UN**selected (do not show excluded files). -\> Only this
messagebundle is not visible. (**directories stay visible**).

It is not good for user -\> there needn\' t to be any visible
MessageBundle when user exploring any branch of the tree. See picture:

![](MIT%20-%20Repo_FileFilter%20rules%20definition_html_83734f87.png){#Image1
align="bottom" width="416" height="316" border="0"}

\

I am able to add such functionality that will invisible **all nodes**
under folder that has been excluded. **BUT** MITToolkit is not possible
to remeber this excluded nodes (only MessageBundles under excluded
folder). So when MITToolkit is run again there is also mentioned problem
from above.

\

\

**\-\-\-\-\-\-\-\-- 5.10.2009 8:45:31 by Josef Hobel:**

\

There is also missing support for including / excluding objects by
regualr expressions.

This time include exclude works for separate MessageBundles.

\

\

**\-\-\-\-\-\-\-\-- 1.9.2009 9:12:36 by Jiri Kiml:**

\

So if code review is done, why it is still open ?

\

\

**\-\-\-\-\-\-\-\-- 11.8.2009 13:20:53 by Josef Hobel:**

code review done with change 283530

\

**\-\-\-\-\-\-\-\-- 7.8.2009 10:13:46 by Petr Haka:**

\

Code review

\

Look at the possibility of expanding the file tree until the resource
bundle is found. May be helpful even when you exclude a bundle from the
tree.

\

Line 104 - **if** (**new** File(*getSelectedFilePath*()).isFile())
should at the beginning of the block

\

**private** **void** \_excludeIncludeMessageBundle(**final** String
Ps_path) :

\- the two conditions should be the same - fileTree.setNodeVisible
inside the condition **if** (!FileFilterHelper.*excludePath*(Ps_path) &&
Fi_selectedOption == 0)

\- remove code repetition

\

create constants for Including/excluding path

\

\

**\-\-\-\-\-\-\-\-- 5.8.2009 14:04:19 by Josef Hobel:**

\

almost done - application not works with regular expressions yet.

\

\

\

**\-\-\-\-\-\-\-\-- 27.7.2009 13:56:41 by Jiri Kiml:**

\

First step:

For files:

FileFilterHelper.excludePath -\> directories which should be excluded

FileFilterHelper.excludeRBKey -\> excluded keys

\

Use different e.g. to distinguis such entries.

\

There should be posibility to modify these filters too, for now prepare
only gui design for it (empty impl with e.g. message box \"directory xxx
should be ignored\"

as implementation. Implementation methods will be prepared in
^(2)^*[Todo 46573: I18N - Jaxb - introduction]{.underline}*

\

\

\

\

**\-\-\-\-\-\-\-\-- 29.6.2009 10:32:13 by Jiri Kiml:**

\

This job is about possibility to edit DefaultFileter.xml easily then via
notepad.

Gui design is unclear.

\

\

**\-\-\-\-\-\-\-\-- 28.4.2009 16:40:26 by Veronika Hnizdilova:**

In navigation trees in the two tabs created by ^(3)^*[Todo 44894: MIT -
MessageBundle files editor]{.underline}* and ^(4)^*[Todo 44891: MIT -
I18N objects from Repository editor]{.underline}* should be possibility
to uncheck concrete path and in this way define RepoFilter or FileFilter
rule (already existing rules should be applied and such RBs should be
unchecked). Only checked RBs are considered during export-import
process.

\

Another idea how to define rules there: not by checkboxes because some
rules are somehow general (e.g. regular expression definition) so they
can cover more RBs (or RB-keys). So distinguish excluded RB somehow else
(font type, color, ?) and concrete RB (or whole path or key) can be
excluded by a new rule definition (by context menu action and some
dialog).

\

\

\

**workaround:**

\

\

\

\

**RepoFilter**

Exclude:

1\] run MITTolkit

2\] goto Repository tab

3\] click by left mouse button to any repoDir and select Exclude from
popupmenu

4\] confirmDialog should appears. Accept it.

5\] Check the exported repoID under selected dir are in
DefaultFilter.xml.

\

Include:

1\] click into same reopoDir as in exclude.

2\] Now choose include item from popoupmenu.

3\] confirm dialog

4\] all repoID under repoDir must not be in the DefaultFIlter.xml now.

\
