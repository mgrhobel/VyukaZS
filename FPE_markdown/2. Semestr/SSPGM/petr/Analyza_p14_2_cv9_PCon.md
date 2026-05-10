---
title: "Analyza_p14_2_cv9_PCon.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/petr/Analyza_p14_2_cv9_PCon.doc"
date: 2009-04-27
type: DOC
---

Analýza programů p14_1.c a p14_2.c

-   programy jsme přeložili a analyzovali

-   program zapisuje, čte do textového souboru p14.txt dle analýzy (dle
    níže uvedené tabulky)

\

  ----- ------- ------- ------- -------
  1\.   Read    Read    Write   Write
  2\.   Write   Write   Read    Read
  3\.   Read    Write   Write   Read
  4\.   Write   Read    Write   Read
  5\.   Read    Write   Read    Write
  6\.   Write   Read    Read    Write
  ----- ------- ------- ------- -------

\

t![DrawObject2](Analyza_p14_2_cv9_PCon_html_95307dc0.gif){#DrawObject2
align="left" hspace="12" width="78" height="23"}
![DrawObject1](Analyza_p14_2_cv9_PCon_html_68d50c23.gif){#DrawObject1
align="left" hspace="12" width="78" height="23"} 1 t2 t3 t4

Rodič Potomek

\

\

\

![](Analyza_p14_2_cv9_PCon_html_5be2086c.png){#Image1 align="bottom"
width="604" height="608" border="0"}

\

+-----+---------------+---------------+---------------+---------------+
| \   | [\[]{la       | [\[]{la       | [\[]{la       | [\[]{la       |
|     | ng="en-US"}t1 | ng="en-US"}t2 | ng="en-US"}t3 | ng="en-US"}t4 |
|     | write\]       | write\]       | read\]        | read\]        |
+-----+---------------+---------------+---------------+---------------+
| 1\. | 2             | 3             | 0             | 1             |
+-----+---------------+---------------+---------------+---------------+
| 2\. | 0             | 0             | 1             | 1             |
+-----+---------------+---------------+---------------+---------------+
| 3\. | 1             | 2             | 0             | 4             |
+-----+---------------+---------------+---------------+---------------+
| 4\. | 0             | 2             | 1             | 4             |
+-----+---------------+---------------+---------------+---------------+
| 5\. | 1             | 3             | 0             | 2             |
+-----+---------------+---------------+---------------+---------------+
| 6\. | 0             | 4             | 1             | 2             |
+-----+---------------+---------------+---------------+---------------+

\
