---
title: "prub_test.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/zapocet/prub_test.doc"
date: 2009-02-19
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
| ## Pr | \     | \     | \     | \     | \     | \     | \     | \     |
| ogram |       |       |       |       |       |       |       |       |
|  {#pr |       |       |       |       |       |       |       |       |
| ogram |       |       |       |       |       |       |       |       |
|  .wes |       |       |       |       |       |       |       |       |
| tern} |       |       |       |       |       |       |       |       |
+-------+-------+-------+-------+-------+-------+-------+-------+-------+
| Ahoj, | \     | \     | \     | \     | \     | \     | \     | \     |
| g     |       |       |       |       |       |       |       |       |
| etpid |       |       |       |       |       |       |       |       |
+-------+-------+-------+-------+-------+-------+-------+-------+-------+
| sa,   | \     | \     | \     | \     | \     | \     | \     | \     |
| g     |       |       |       |       |       |       |       |       |
| etpid |       |       |       |       |       |       |       |       |
+-------+-------+-------+-------+-------+-------+-------+-------+-------+
| a,    | \     | \     | \     | \     | \     | \     | \     | \     |
| g     |       |       |       |       |       |       |       |       |
| etpid |       |       |       |       |       |       |       |       |
+-------+-------+-------+-------+-------+-------+-------+-------+-------+
| sb,   | \     | \     | \     | \     | \     | \     | \     | \     |
| g     |       |       |       |       |       |       |       |       |
| etpid |       |       |       |       |       |       |       |       |
+-------+-------+-------+-------+-------+-------+-------+-------+-------+
| b,    | \     | \     | \     | \     | \     | \     | \     | \     |
| g     |       |       |       |       |       |       |       |       |
| etpid |       |       |       |       |       |       |       |       |
+-------+-------+-------+-------+-------+-------+-------+-------+-------+
| sc,   | \     | \     | \     | \     | \     | \     | \     | \     |
| g     |       |       |       |       |       |       |       |       |
| etpid |       |       |       |       |       |       |       |       |
+-------+-------+-------+-------+-------+-------+-------+-------+-------+
| c,    | \     | \     | \     | \     | \     | \     | \     | \     |
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

printf(\"sb%d \",grtpid());

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
