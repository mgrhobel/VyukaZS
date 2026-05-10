---
title: "Investigate translations according to context information .doc"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/MIT resources/I18NDocumentation/relatedUseCases/Investigate translations according to context information .doc"
date: 2010-03-07
type: DOC
---

[**Detailed Use Case:**]{.underline} [**Investigate translations
according to context information**]{.underline} (Start with a verb)

**Pending Issues** (Topics to be discussed)

\

+-----------------------+-----------------------+-----------------------+
| **Level:**            | **Design Scope:**     | **referenced in:**    |
|                       |                       | ^**(1)**^             |
|                       |                       | Internationalisation  |
|                       |                       | and Localisation      |
|                       |                       | Tools                 |
+-----------------------+-----------------------+-----------------------+

\

**Primary Actor:** (calls on the system to deliver its services)

\

**Stakeholders and interests :** (Who cares about this use case, and
what do they want.)

\

**Preconditions:** (what must be true on start, and worth telling the
reader ?)

Translated phrases are already imported in repo and message bundles.

**Triggers:** ()

\

**Success Guarantee:** (what must be true on successful completion, and
worth telling the reader ?)

The \"central dictionary\" is created/updated. For the same phrase there
can be more than one translations (depending on context) and these
information are stored in the \"central dictionary\". Of course any
change of translation has to be projected into all proper repo and
message bundles.

**Use Case Steps / Main Success Szenario:** ( A typical, unconditional
happy path szenario of success)

1\. Run the I18N tool and go through all phrases and their translations.

2\. Show all occurrences of a selected phrase (it means all message and
repo bundles where the phrase appears).

3\. If the global translation of the phrase is not suitable for some
context, correct it. It is also possible to correct the translation
globally.

**Extensions:** (Alternate Szenarios of successes and failures)

Additionaly (if it is possible) concrete views where the selected phrase
occurs (it means concrete context) can be displayed.

**Related Non functional requirements:**

\

**Expected frequency of executions:**

\

**Business Rules:**

\

\

[**References:**]{.underline}

**Test Case(s):**

\

**User Guide:**

\

**Specificactions, Analyses:**

\

-   The \"central dictionary\" should be used during export (into the
    excel file for translation) in the feature.

-   Investigation has to be made, if the context informations should be
    built by starting of I18N Tool (some tool name has to be found) and
    then no performance problems should appear, or by searching of
    context information for some phrase Repo and MessageBundles should
    be searched (maybe with some caching mechanism).

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--
