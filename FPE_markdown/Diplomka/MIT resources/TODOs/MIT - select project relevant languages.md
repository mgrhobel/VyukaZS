---
title: "MIT - select project relevant languages.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/MIT resources/TODOs/MIT - select project relevant languages.doc"
date: 2010-03-07
type: DOC
---

done

\

\

**\-\-\-\-\-\-\-\-- 29.6.2009 10:16:34 by Jiri Kiml:**

\

should be used in export/import tab too

\

\

**\-\-\-\-\-\-\-\-- 28.5.2009 13:47:54 by Jiri Kiml:**

\

probably part of MIT.properties

\

\

**\-\-\-\-\-\-\-\-- 14.5.2009 15:08:15 by Veronika Hnizdilova:**

Languages taken from I18NProperties.allAvailableLocales act property
should be available to select as interesting languages (display them as
checkboxes in MITToolkit header). They will not be project dependent,
but should be somehow stored for next MITToolkit application run (e.g.
in some properties file). Only languages from these locales should be
considered (so only en for both en_GB and en_US). \'none\' locale should
be omitted, it is relevant for all projects.

\

Where to use them? Currently the only suitable situation is in \'Views
Overview\' tab where a ComboBox with locales is displayed. This should
take only these project languages and consider even all possible
countries available in I18NProperties.allAvailableLocales for given
language.

\

\
