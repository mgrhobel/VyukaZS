---
title: "Import phrases from translation file.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/MIT resources/I18NDocumentation/relatedUseCases/Import phrases from translation file.doc"
date: 2010-03-07
type: DOC
---

[**Detailed Use Case:**]{.underline} [**Import phrases from translation
file**]{.underline} (Start with a verb)

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

An excel file with translated phrases is available.

**Triggers:** ()

\

**Success Guarantee:** (what must be true on successful completion, and
worth telling the reader ?)

Allready translated phrases in the excel file are imported back into
repository and message bundle files in two steps.

**Use Case Steps / Main Success Szenario:** ( A typical, unconditional
happy path szenario of success)

1\. Run the command line tool with all needed parameters -\> all phrases
are successfully imported back into database.

2\. Run the command line tool with all needed parameters -\> all phrases
are successfully imported back in resource bundles.

**Extensions:** (Alternate Szenarios of successes and failures)

The gui tool should be provided too.

**Related Non functional requirements:**

\

**Expected frequency of executions:**

Every time the excel file with translated phrases is updated.

**Business Rules:**

\

\

[**References:**]{.underline}

**Test Case(s):**

\

**User Guide:**

\

**Specificactions, Analyses:**

Following features have to be supported:

\

-   Context information should be applied in order to keep the context
    dependent translation (if any).

-   Consider situation that for locale which is imported doesn\'t exist
    repo and message bundles - so they have to be created.

-   A parameter for overwriting existing translation should be provided
    (by default do not overwrite anything)

\

**Import of phrases from translation file into the repository**

-   New implementation of ResourceBundleRepoImport
    (ResourceBundleRepoImport2) should be implemented.

-   Concept: All I18N objects will be examined (exactly like by
    ResourceBundleRepoExport). For every object its \"none\" phrase will
    be searched in the \"translation file\". If found, existing
    translations for every locale from \"translation file\" should be
    imported into the repository.

-   If needed, new I18N object for corresponding locale should be
    created and saved.

\

**Import of phrases from translation file into MessageBundle Files**

-   To be implemented:
    at.co.systema.gf.i18n.util.MessageBundlePhraseImporter

-   It investigates all \*Bundle.properties files (that means for
    \"none\" locale). For every key the corresponding phrase will be
    searched in the translation file. For all translated locales the
    corresponding translations will be saved in the corresponding
    \*Bundle_locale.properties.

-   Carry out some check of formatting: That means the number of symbols
    \<CR\>, \<TAB\>, {0}**,** {1}**, \...** must be the same in the
    orginal phrase as in the translated phrase.

\

**1st step - Import from file into database**

-   At first all translated phrases in output file should be imported in
    the local i18n database where can be adjusted (this is not part of
    this use case).

\

**2nd step - Import phrases form database into repository and
MessageBundle files**

-   The last step of translation process is import of translated phrases
    back into repo and file resource bundles.

-   
