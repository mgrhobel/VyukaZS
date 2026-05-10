---
title: "link4.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/MIT resources/I18NDocumentation/link4.doc"
date: 2010-03-07
type: DOC
---

^(1)^[**?**]{.underline} [**User Guide:**]{.underline}
[**ResourceBundleRepoExport
(at.co.systema.gf.repo2.tools.ResourceBundleRepoExport)**]{.underline}

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

**at.co.systema.gf.repo2.tools.ResourceBundleRepoExport**

RepoObjects are exported to a tab-separated by MS Excel readable text
file. This in unicode format written textfile can again be imported via
ResourceBundleRepoImport (^(3)^) after some internationalisations have
been applied.

By means of the excel worksheet translate.xls(located in the same
directory as file translate_excel2000.xls for MS Excel 2000), the
created textfile can comfortably be imported into MS Excel for editing.

Usage:

ResourceBundleRepoExport -outputFile \<filename\> -repoOwner
\<ownerType\> \<ownerName\> \[ -repoDir \<repoDirPattern\> \] \[ -locale
\<locale\> \] \[ -useFullPath \] \[ -outputFileTrans \<filename\> \]

\

Description:

-   outputFile: the file to which data should be exported

-   repoOwner: the RepoObjectOwner for which the export should be made.

-   repoDir: the RepoDirectory which should be exported (Wildcards in
    DOS-Style are allowed).

-   If ommited, all directories found in the repository will be
    exported.

-   For details see below.

-   locale: the locale which should be exported.

-   This locale will be exported with all parent-locales (e.g.:
    specifying \'cs_CZ\' will cause an export of \'cs\' and \'none\'
    too).

-   If ommited, all available locales will be exported.

-   useFullPath: if passed the full repopath until the given owner will
    be used for searching inside the repository, if omitted only objects
    of the given owner will get exported

-   outputFileTrans: the file to which should be exported simple data
    only (no additional context information)

\

Details for parameter repoOwner:

I will explain the parameter by an example. The ResourceBundleRepoExport
is started with \"-repoOwner cust mpa38\":

-   repoObjects which are stored under syst and syex and NOT under
    customer mpa38: the syex versions are read and exported in the excel
    sheet.

-   repoObjects which are stored under customer mpa38 and/or syst/syex:
    the customer versions are read and exported in the excel sheet.

\

\

Sample from Serbien-Export:

-   java at.co.systema.gf.repo2.tools.ResourceBundleRepoExport
    -outputFile c:\\i18n\\allRepoRBs.txt -repoOwner cust khsm
    -useFullPath (-useFullPath muss man nicht angeben, wird automatisch
    so ausgeführt!)

-   The TopLevel will be exported. If a cust exist, it will be used,
    else the syex, else the syst.

-   The import should be done then to customer only, not TopLevel!

\

\
