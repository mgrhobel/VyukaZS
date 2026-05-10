---
title: "arguments.txt"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/internet/unix-lekce/skripty-zdrojaky/arguments.txt"
date: 2009-05-01
type: TXT
---

#!/bin/bash

echo nazev skriptu je $0
echo prvni argument je $1
echo druhy argument je $2
echo sedmnacty argument je $17 --- huh, opravdu? Asi chyba!
echo ve skutecnosti je sedmnactym argumentem ${17}
echo pocet argumentu je $#
