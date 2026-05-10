---
title: "MIT - I18N objects from Repository editor.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/MIT resources/TODOs/MIT - I18N objects from Repository editor.doc"
date: 2010-03-07
type: DOC
---

**\-\-\-\-\-\-\-\-- 9.12.2009 19:43:57 by Josef Hobel:**

\

**Problem**

\- repoDir contains \"ViewAttr\" must be skipped, if not reading the
repoObject is too much time consuming.

\

**Prerequisities**

It is possible to delete the \'none\' locale, but it should not be done.
User will be not possible to create this \'none\' locale again.

\

**Optional Locale info**

I18NProperteis settings and RepoResourceBundle view

when defaultRepoWriteLocale is set to **none** -\> then optionalLocale
is same as repoObject locale.

when defRepoWriteLoc is **not none** e.g. en -\> then optional locale is
en for all repoObject.

\

\

**How save works**

Changes of RepoRessourceBundle keys are allowed when repoObject already
exists in the Repository (appropriate node is visible in the tree).
Because of it is need to **create repoObject** for specified
repoWriteSettings **at first**, then is possible to modfiy it.

[Is not possible to create new repoObject and in the same time change
its values.]{.underline}

\

Each repoObject (tree list) represents one specific repowrite settings
under it is saved into repository.

E.g.:

Suposed I18NProperties settings:

language, counstry: en_US

defaultRepoWriteLocale: en

-\>In the RepoResourceBundle are visible en and en_US columns. for both

\

When some changes appeared in the en_US column for en repoObject -\>
nothing will be saved into repository, because there is possible to
change and save only en RepoRessourceBundle.

\

\

**How read works**

When exists parent for specified writeSettings, then this parent is
visible for appropriete child (same writeSettings).

When is parent deleted, then is deleted from child object.

\

\
