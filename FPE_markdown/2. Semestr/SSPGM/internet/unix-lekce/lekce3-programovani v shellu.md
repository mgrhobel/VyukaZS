---
title: "lekce3-programovani v shellu.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/internet/unix-lekce/lekce3-programovani v shellu.doc"
date: 2009-05-01
type: DOC
---

# [Programov]{lang="en-US"}ání v shellu {#programování-v-shellu .western lang="cs-CZ"}

\

provedení konkrétním shellem

\

#!/bin/sh

\

proměnné -- vždy string

\

x=50

y=60

\

z=[\`]{lang="pl-PL"}expr \$x+\$y\`

\

Parametry programu

\

\$1\... \$9

\

shift -- posunutí parametru

\

vypsání parametrů

\

count=0

while test \$1

do

count=\`expr \$count + 1\`

echo \"\$count parametr je \$1\"

shift

done

\

Základní příkazy

\

if then fi

if then else fi

if then elif then else fi

pro porovnání test

\

řetězce

test [\$a = \$b != ]{lang="en-US"}

[test -z(nulov]{lang="en-US"}ý) --n(nenulový) [\$a]{lang="en-US"}

\

integer

n1 -eq n2 -ne, -gt, -ge, -lt, -le

\

file

-r file true if file exists and is readable.

-w file true if file exists and is writable.

-x file true if file exists and is executable.

-f file true if file exists and is a regular file.

-d file true if file exists and is a directory.

-c file true if file exists and is a character special file

-b file true if file exists and is a block special file.

-p file true if file exists and is a named pipe (fifo).

-u file true if file exists and its set-user-ID bit is

-g file true if file exists and its set-group-ID bit is set.

-k file true if file exists and its sticky bit is set.

-s file true if file exists and has a size greater than zero.

while do done

until do done

for in do done

\

\

[tr -- nahrazen]{lang="en-US"}í znaku

wc -- word count

ls --R -- recursively

\

\

grep

\

\

**znak** odpovídající znak

**.** libovolný znak

**\[znaky\]** jeden z uvedených znaků

**\[\^znaky\]** libovolný znak kromě uvedených

**\\x** vyřadí/zapne speciální význam znaku x

libovolný počet opakování předchůdce

**+** nebo **\\+** alespoň jeden výskyt předchůdce

**?** nebo **\\?** nanejvýš jeden výskyt předchůdce

**{min,max}** nebo **\\{min,max\\}** alespoň *min* a nanejvýš *max*
výskytů předchůdce

**\^** začátek řádku

**\$** konec řádku

**\\\<** nebo **\\b** začátek slova

**\\\>** nebo **\\b** konec slova

\

\

\

\

Výrazu **A\*** tedy vyhoví libovolný počet písmen \"A\",

zatímco **\[0-9\]\*** ztělesňuje libovolně dlouhou posloupnost číslic

(opakovaným regulárním výrazem je zde **\[0-9\]**, tedy libovolná
číslice).

**\[0-9\]\[0-9\]\***

Regulárnímu výrazu **i\\{1,3\\}** vyhoví řetězce \"i\", \"ii\" nebo
\"iii\".

Regulární výraz pro rodné číslo by vypadal takto:
**\[0-9\]\\{6\\}/\[0-9\]\\{3,4\\}** Šest číslic, lomítko a ještě tři
nebo čtyři číslice.

\

#!/bin/sh

#Zjisti pocet zanoreni aktualniho adresare

pocet=0

n=1

gstring=\'.\*/.\*\'

adds=\'/.\*\'

ls -Rx \| grep \"\${gstring}\" \> poc

while test -s poc

do

rm poc

pocet=\`expr \$pocet + 1\`

gstring=\$gstring\$adds

ls -Rx \| grep \"\${gstring}\" \> poc

done

\

#!/bin/sh

old=0

for i in \`ls -Rx\`

do

z=\`echo \$i \| tr \'/\' \'\\n\' \| wc -l\`

if test \`expr \$z\` -gt \`expr \$old\`

then

old=\$z

fi

done

\
