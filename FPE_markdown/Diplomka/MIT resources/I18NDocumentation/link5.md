---
title: "link5.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/MIT resources/I18NDocumentation/link5.doc"
date: 2010-03-07
type: DOC
---

^(1)^[**?**]{.underline} [**User Guide:**]{.underline}
[**ResourceBundleRepoImport
(at.co.systema.gf.repo2.tools.ResourceBundleRepoImport)**]{.underline}

+---+---------------+
| \ | **see also:** |
|   |               |
|   | \             |
+---+---------------+

Is child document of: ^(2)^ User Guide Überblick: command reference

\

+-----------------------------------+-----------------------------------+
| **Beschreibung:**                 | \                                 |
+-----------------------------------+-----------------------------------+

**at.co.systema.gf.repo2.tools.ResourceBundleRepoImport**

A textfile created by an export via ResourceBundleRepoExport (^(3)^)
will be reimported after internationalisations have been applied.

\
\

Usage:

ResourceBundleRepoImport -inputFile \<filename\> \[ -repoOwner
\<ownerType\> \<ownerName\> \] \[ -repoDir \<repoDirectory\> \] \[
-locale \<locale\> \] \[ -forceOverwrite\]

\

Description:

-   inputFile: the file which should be imported

-   repoOwner: the RepoObjectOwner for which the import should be made.

-   If ommitted, the RepoObjectOwner found in the inputfile will be used
    for importing.

-   repoDir: the RepoDirectory which should be importet (Wildcards in
    DOS-Style are allowed).

-   If ommited, all directories found in the inputfile will be imported.

-   locale: the locale which should be imported.

-   If ommited, all locales will be imported (except locale \'none\')

-   forceOverwrite: if parameter available old existing localized
    RepoResourceBundle-values will be overwritten by inputFile values.

\
\

**Attention**:

When using forceOverwrite changes due to translations applied in the
meantime manually using RepoBrowser, GuiBuilder etc. will be overwritten
when data are reimported into the repository. Thus don\`t translate
anything in the meantime via RepoBrowser, GuiBuilder etc, resp. don\'t
reimport these objects from the exported textfile (e.g.: by explicit
definition of a repo directory) or don\'t use forceOverwrite in this
cases.

\

\

Sample from Serbien-Export:

-   java at.co.systema.gf.repo2.tools.ResourceBundleRepoExport
    -outputFile c:\\i18n\\allRepoRBs.txt -repoOwner cust khsm
    -useFullPath

-   The TopLevel will be exported. If a cust exist, it will be used,
    else the syex, else the syst.

-   The import should be done then to customer only, not TopLevel!

\

\

\
