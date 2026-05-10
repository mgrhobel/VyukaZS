---
title: "prub_test.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/moje prace/cv4/prub_test.doc"
date: 2009-05-03
type: DOC
---

### P11.c, [dokument stáhněte z webu do vašeho domácího adresáře, v]{style="font-weight: normal"}[[yplňte tabulku a vypracovaný dokument pojmenovaný výstižně vaším ]{style="font-weight: normal"}]{lang="cs-CZ"} {#p11.c-dokument-stáhněte-z-webu-do-vašeho-domácího-adresáře-vyplňte-tabulku-a-vypracovaný-dokument-pojmenovaný-výstižně-vaším .western}

### příjmením (popř. + jméno) zkopírujte do adresáře R:\\USR\\FPE\\STU\\STUPRACE\\TOMAN\\SSPGM. !!! Uložte až definitivní dokument !!! {#příjmením-popř.-jméno-zkopírujte-do-adresáře-rusrfpestustupracetomansspgm.-uložte-až-definitivní-dokument .western lang="cs-CZ" style="font-weight: normal"}

###  {#section .western lang="cs-CZ" style="font-weight: normal"}

R

1.fork \| P1 \-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\| \|

2.fork \| P2 \-\-\-\-\-\-\-\-\-\-\-\-\-\-- \| P11
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\| [\| \| \|]{lang="en-US"}

3.fork \| P3 \| P21 \| P12 \| P111

\

+-------+-------+-------+-------+-------+-------+-------+-------+-------+
| # Pr  | **R** | *     | *     | *     | **    | **    | **    | **P   |
| ocesy |       | *P1** | *P2** | *P3** | P11** | P12** | P21** | 111** |
|  {#pr |       |       |       |       |       |       |       |       |
| ocesy |       |       |       |       |       |       |       |       |
|  .wes |       |       |       |       |       |       |       |       |
| tern} |       |       |       |       |       |       |       |       |
+-------+-------+-------+-------+-------+-------+-------+-------+-------+
| ## Pr | 14907 | 14908 | 14909 | 14910 | 1     | 14912 | 14913 | 14914 |
| ogram |       |       |       |       | 41911 |       |       |       |
|  {#pr |       |       |       |       |       |       |       |       |
| ogram |       |       |       |       |       |       |       |       |
|  .wes |       |       |       |       |       |       |       |       |
| tern} |       |       |       |       |       |       |       |       |
+-------+-------+-------+-------+-------+-------+-------+-------+-------+
| Ahoj, | 14907 | 14907 | 14907 | 14907 | 14907 | 14907 | 14907 | 14907 |
| g     |       |       |       |       |       |       |       |       |
| etpid |       |       |       |       |       |       |       |       |
+-------+-------+-------+-------+-------+-------+-------+-------+-------+
| sa,   |       | \     | \     | 14908 | 14908 | 14908 | 14908 | \     |
| g     |       |       |       |       |       |       |       |       |
| etpid |       |       |       |       |       |       |       |       |
+-------+-------+-------+-------+-------+-------+-------+-------+-------+
| a,    | \     | 14907 | 14907 | 14908 | 14908 | 14908 | 14908 | 14907 |
| g     |       |       |       |       |       |       |       |       |
| etpid |       |       |       |       |       |       |       |       |
+-------+-------+-------+-------+-------+-------+-------+-------+-------+
| sb,   | \     | \     | \     | 14909 | 14909 | \     | \     | 14912 |
| g     |       |       |       |       |       |       |       |       |
| etpid |       |       |       |       |       |       |       |       |
+-------+-------+-------+-------+-------+-------+-------+-------+-------+
| b,    | \     | 14907 | 14907 | 14909 | 14909 | 14908 | 14908 | 14912 |
| g     |       |       |       |       |       |       |       |       |
| etpid |       |       |       |       |       |       |       |       |
+-------+-------+-------+-------+-------+-------+-------+-------+-------+
| sc,   | \     | 14914 | \     | 14910 | \     | 14911 | \     | 14913 |
| g     |       |       |       |       |       |       |       |       |
| etpid |       |       |       |       |       |       |       |       |
+-------+-------+-------+-------+-------+-------+-------+-------+-------+
| c,    | \     | 14914 | 14907 | 14910 | 14909 | 14911 | 14908 | 14913 |
| g     |       |       |       |       |       |       |       |       |
| etpid |       |       |       |       |       |       |       |       |
+-------+-------+-------+-------+-------+-------+-------+-------+-------+

\

::: {#Section1 dir="ltr" gutter="47" style="column-count: 2"}
main()

{

printf(\"Ahoj %d \\n\\n\",getpid());

if (fork()==0)

{

[printf(\"sa%d \",getpid());]{lang="en-US"}

}

printf(\"a%d \",getpid());

if (fork()==0)

{

printf(\"sb%d \",getpid());

}

printf(\"b%d \",getpid());

if (fork()==0)

{

printf(\"sc%d \",getpid());

}

printf(\"c%d \",getpid());

sleep(10);

}
:::
