---
title: "MIT - first gui implementation - i18n project management.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/MIT resources/TODOs/MIT - first gui implementation - i18n project management.doc"
date: 2010-03-07
type: DOC
---

Additional gui layout improvements done by ^(1)^*[Change
268513]{.underline}* and ^(2)^*[Change 268535]{.underline}*

\

**\-\-\-\-\-\-\-\-- 15.4.2009 12:38:10 by Josef Hobel:**

Done.

I18NProjectMgr had to be adjusted: createNewProject() method now expects
already created I18NProject instance (not like before only project name)
that can be created by newly introduced I18NProjectFactory, additionaly
I18NProjectListeners are handled when a project changes here.

II18NProject -\> remaining setters/getters were implemented.

\

MITToolkit introduced - main gui class. Currently it supports main
project management functions:

\- create/edit dialog - when a project is edited it still is not saved,
application name of already created project can not be changed (it is a
project directory name)

\- open/delete dialog - only not currently opened project can be deleted

\- save action - a project hsqldb connection is closed to project
possible changes to the hsqldb.script, user can continue working on the
project

\

\

**\-\-\-\-\-\-\-\-- 16.1.2009 11:59:23 by Veronika Hnizdilova:**

Start with implementation of gui tool.

At first it should be available to manage i18n projects there
(create\..., open\..., save and delete\...). Some of these actions are
already provided by I18NProjectMgr, the rest of them should be done by
^(3)^*[Todo 43385: I18NProjectMgr improvement]{.underline}*. These
actions will be available through menu bar.

\
