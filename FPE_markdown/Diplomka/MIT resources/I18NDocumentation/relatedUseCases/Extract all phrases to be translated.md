---
title: "Extract all phrases to be translated.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/MIT resources/I18NDocumentation/relatedUseCases/Extract all phrases to be translated.doc"
date: 2010-03-07
type: DOC
---

[**Detailed Use Case:**]{.underline} [**Extract all phrases to be
translated**]{.underline} (Start with a verb)

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

\

**Triggers:** ()

\

**Success Guarantee:** (what must be true on successful completion, and
worth telling the reader ?)

The output is an excel file with all available non duplicate phrases
that are stored in all message and repo bundles which will be offered
for translation. The extraction should follow some rules to the intent
that some untranslatable phrases (e.g. digits) will be skiped.

**Use Case Steps / Main Success Szenario:** ( A typical, unconditional
happy path szenario of success)

1\. Define the rules which phrases must be skipped. The rules should be
defined in an xml file.

2\. Run the command line tool with all needed parameters -\> all phrases
are successfully exported in database.

3\. Run the command line tool with all needed parameters -\> excel file
is created.

**Extensions:** (Alternate Szenarios of successes and failures)

The gui tool should be provided too. The user should be able to do there
both - define the extraction rules and start the extraction process.

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

Following features have to be supported:

\

-   The output file contains at least three columns:

-   the default german (\"none\") phrases

-   one or more columns of selected locales

-   \"context info\" column

-   Every \"none\" phrase is included only ONCE (clearly, no context
    information will be extracted)

-   If no output file exists, new one will be created. If the file
    already exists, only new \"none\" phrases will be extracted (no
    existing translations will be losed). Additionaly a parameter
    -overwriteExistingTranslations should be implemented to be able to
    overwrite the already translated phrases.

-   If there is only one context information for some phrase (mostly the
    case by MessageBundle phrases), this could be exported into the
    \"translation file\" in some special column \"context info\". For
    other phrases like \"Aufenthalt\", \"Patient\", \"Anforderung\",
    etc. no context information can be exported into the \"translation
    file\", because there are many repo objects containing these
    phrases.

-   there is provided some additional parameter to be able to exclude
    some chosen plugins from extraction

\

**Extract phrases from repo**

-   Improve at.co.systema.gf.repo2.tools.ResourceBundleRepoExport

-   These phrases are vendor dependent - that means that per release the
    extraction from repo should be done for every vendor to get all
    possible phrases supported by MPA on syex and syst level (or
    somebody has to decide what is the reference repository for basic
    MPA translation).

\

\

**Extract phrases from message bundles**

-   Implement at.co.systema.gf.i18n.util.MessageBundlePhraseExtractor

-   Investigates all \*Bundle\*.properties files starting with
    \'dirRoot\'

-   Write out all non duplicate reasonable phrases into some
    \'outputFile\'

-   This could/should be the same file used for export of all Repo
    phrases

-   Positive side effect: check of correct message bundle keys was built
    in. That means, if there is some key in Czech locale, but no key for
    \"none\", this error will be logged. So we could find out, that in
    at.co.systema.MessageBundle_cs.properties many keys are in Czech.
    The reason was bad import of czech phrases (\\n character iowas
    really

-   These phrases are release dependant

\

**Apply some translation rules for all extracted phrases to build the
definitive phrases to be translated**

Many extracted phrases should/may not be translated.

Examples:

2a, 2b, 2c, 24x30, 2x1/2, 35x43, A (? context information needed), AB (?
context information needed), age \> 35 (dangerous, context needed),
Alter \> 35 (the same), B, BOOLEAN, C, D, DEBUG-LEVEL, \...

\

Some rules (based on RegularExpressions) should be introduced. Every
rule has following properties:

modus: \"-\" \--\> if the translation status on phrase was
\"translate\", after succesful applying of rule, change the translation
status to \" not translate\"

\"+\" \--\> if the translation status on phrase was \"not translate\",
after succesful applying of rule, change the translation status to
\"translate\"

\"?\" \--\> do not change the phrase status, but show all phrases
fulfilling the rule.

\

batch: \"1\" \--\> this rule can be applied in automatic modus

\"0\" \--\> this rule will not be applied in automatic modus (user
interaction is needed).

\

-   These rules are valid for all phrases (e.g. \"A\"). This can be
    overriden by context sensivite translation.

-   E.g. there is some repo object with I18N phrase \"A\", which is
    abbreviation for \"ambulant\". Some \"internal I18N expert\"
    decides, that the phrase \"A\" should be translated to \"X\" for
    this repo object.

-   This context information should be saved in some way.

\

**1st step - Extract phrases into database**

-   Local database should be stored in p4 to be able share it easily

-   The extraction process done by RepoResourceBundeExport and
    FileResourceBundleExport can be reused.

-   Consider DB model from ^(2)^*[Design 6359: Proposal for DB Model of
    I18N Tools and some ideas for GUI]{.underline}*

\

**2nd step - Export from database into file**

-   Content of the local database should be exported into the output
    file for translation.

-   The output format should be the same like RepoResourceBundeExport
    and FileResourceBundleExpor do.

\

\
