---
title: "link6_How logging may help with translation.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/MIT resources/I18NDocumentation/link6_How logging may help with translation.doc"
date: 2010-03-07
type: DOC
---

^(1)^[**?**]{.underline} [**Customizing Guide - Use Case:**]{.underline}
[**How logging may help with translation**]{.underline}

Is child document of: ^(2)^ Customizing Guide Use Case: Guide to
Localisation-Settings (Example Czech Republic)

\

+---+---------------+
| \ | **see also:** |
|   |               |
|   | \             |
+---+---------------+

**requirement/use case (reference)**

\

**Specification (reference)**

\

**Description:**

Translation detalis may be facilitated by logging. If you turn on
\"gf.i18n.translation\" logger, all i18n localized values will be logged
by him.

\

There are two possibilites how to do it:

1\. Start mpa with parameter **-log gf.i18n.translation**. This will set
the logger on DEBUG level. For each *ResourceBundle-file* will be logged
its key, package and value. For each *RepoResourceBundle* will be logged
its key, RepoDirectory, RepoID and value. If you start mpa with
parameter **-xlog gf.i18n.translation TRACE**, even stactrace will be
logged for *ResourceBundle-file*.

\

2\. Start mpa and open the logging dialog (see figure below) where you
can select **i18nTranslation** predefined logger and activate him. Or
use \'All available Loggers\' field and choose Level DEBUG (or TRACE).

\

![](link6_How%20logging%20may%20help%20with%20translation_html_8921980d.png){#Image1
align="bottom" width="620" height="300" border="0"}

\

Then look inside the logfile (see figure below) and search for
\"gf.i18n.translation\" logger messages and for desired string which you
want to translate.

\

![](link6_How%20logging%20may%20help%20with%20translation_html_195d62cc.gif){#Image2
align="bottom" width="1161" height="234" border="0"}

\

Example:

The translator opens the document browser and wants to know where the
specific value \"xy\" can be translated. Turn on \"gf.i18n.translation\"
logger first. Then open the document browser. Next display the logfile
and search in it for the value \"xy\" \--\> maybe a little more help can
be given for search string, because if the value is \"Aufenthalt\" this
value may not only be printed by the new logging. So by including the
logger name in the search string the hit quote may raise.

\

\

**Fallback values**

\

Sometimes when a *ResourceBundle-file* or *RepoResourceBundle* doesn\'t
return a value often some \'fallback\' value is taken. i18nTranslation
logger provides also information which value was taken instead (and if
it is possible also from where was taken). This logging is done also in
DEBUG level and follows the *ResourceBundle/RepoResourceBundle* for
which the fallback value was used.

\

Look at the following example. There wasn\'t found a value for
*RepoResourceBundle* with key \"Vorlage.textProperty\", but finally
fallback value \"Vorlage\" was taken.

\

![](link6_How%20logging%20may%20help%20with%20translation_html_b138712b.png){#Image3
align="bottom" width="1160" height="234" border="0"}

\

\

\

\

\

\
