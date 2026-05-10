---
title: "Navigate through all views to check the translation.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/MIT resources/I18NDocumentation/relatedUseCases/Navigate through all views to check the translation.doc"
date: 2010-03-07
type: DOC
---

[**Detailed Use Case:**]{.underline} [**Navigate through all views to
check the translation**]{.underline} (Start with a verb)

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
change of translation has to be projected into all proper repo bundles.

**Use Case Steps / Main Success Szenario:** ( A typical, unconditional
happy path szenario of success)

1\. Run the I18N tool and go through all available views (it is possible
to choose a locale).

2\. Translate a phrase if it is necessary. It is possible to translate
the phrase for the displayed context only.

3\. Go to the next view.

**Extensions:** (Alternate Szenarios of successes and failures)

Additionaly ,if DWB is launched with the -design parameter there should
be available an action \"view translate\" that leads to the same window
(but without the possibility to navigate to the next view).

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

-   (use GUI Builder functionality)

-   Every view should be drawn with one of availabe/chosen locales.

-   Separate list of all phrases of this view (like in RepoBrowser)
    should be shown.

-   Translating of phrases (new phrase/edit phrase) should be possible.
    This change should be saved in Repo, but paralelly in the \"central
    dictionary\" too.

-   Normally, the translations of some phrases are not context
    sensitive. But, exceptionally, after correction (or creation) of
    some translation phrase in the view, this translation should not be
    used \"globally\". My imagination: Small checkbox (default = yes) by
    every phrase, if the translation should be used globally.
