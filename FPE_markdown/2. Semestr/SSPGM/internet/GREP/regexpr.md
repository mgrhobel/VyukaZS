---
title: "regexpr.html"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/internet/GREP/regexpr.html"
date: 2009-04-27
type: HTML
---

[![\[Robelle\]](regexpr_soubory/robelle.gif)](http://www.robelle.com/)
[![\[SmugBook\]](regexpr_soubory/smug.gif)](http://www.robelle.com/smugbook/welcome.html)
[![\[Index\]](regexpr_soubory/index.gif)](http://www.robelle.com/smugbook/index.html)
[![\[Prev\]](regexpr_soubory/up.gif)](http://www.robelle.com/smugbook/manpages.html)
[![\[Next\]](regexpr_soubory/down.gif)](http://www.robelle.com/smugbook/whence.html)

### Searching Files on UNIX

On [MPE](http://www.robelle.com/smugbook/mpe.html) you can display files
using the :Print command, Fcopy,
[Magnet](http://www.robelle.com/smugbook/nuggets.html#magnet), or
[Qedit](http://www.robelle.com/smugbook/qedit.html) (with pattern match
searches). On [HP-UX](http://www.robelle.com/smugbook/hp-ux.html) you
can display files using **cat** and even better using **more** (and
string search using the slash \"/\" command), and
[Qedit](http://www.robelle.com/smugbook/qedit.html) (including searches
of \$Include files, and so on), but if you really want to search for
patterns of text like a UNIX guru, [grep](#grep) is the tool for you.

[Text version.](http://www.robelle.com/smugbook/regexpr1.txt)

  ----------------------------------- -------------------------------------------
  cat report.c                        {prints file on stdout, no pauses}
  cat -v -e -t dump                   {show non-printing characters too}
  cat \>newfile                       {reads from stdin, writes to \'newfile\'}
  cat rpt1.c inp.c test.s \>newfile   {combine 3 files into 1}
  more report.c                       {space for next page, q to quit}
  ps -a \| more                       {page through the full output of ps}
  grep smug \*.txt                    {search \*.txt files for \'smug\'}
  ----------------------------------- -------------------------------------------

MPE users will take a while to remember that **more**, like most UNIX
tools, responds to a Return by printing the next line, not the next
screen. Use the Spacebar to print the next page. Type \"q\" to quit. To
scan ahead to find a string pattern, type \"/\" and enter a [regular
expression](#expression) to match. For further help, type \"h\".
[]{#grep}

#### Searching Files Using UNIX grep

The **grep** program is a standard
[UNIX](http://www.robelle.com/smugbook/unix.html) utility that searches
through a set of files for an arbitrary text pattern, specified through
a [regular expression.](#expression) Also check the [man pages as
well](http://www.robelle.com/smugbook/manpages.html) for **egrep** and
**fgrep**. The [MPE](http://www.robelle.com/smugbook/mpe.html)
equivalents are **MPEX** and
[Magnet](http://www.robelle.com/smugbook/nuggets.html#magnet), both
third-party products. By default, grep is case-sensitive (use -i to
ignore case). By default, grep ignores the context of a string (use -w
to match *words* only). By default, grep shows the lines that match (use
-v to show those that **don\'t** match).

[Text version.](http://www.robelle.com/smugbook/regexpr2.txt)

  ------------------------------ -----------------------------------------------------------------------------------------------
  \% grep BOB tmpfile            {search \'tmpfile\' for \'BOB\' anywhere in a line}
  \% grep -i -w blkptr \*        {search files in [CWD](http://www.robelle.com/smugbook/cwd.html) for word *blkptr*, any case}
  \% grep run\[- \]time \*.txt   {find \'run time\' or \'run-time\' in all txt files}
  \% who \| grep root            {pipe **who** to **grep**, look for *root*}
  ------------------------------ -----------------------------------------------------------------------------------------------

[]{#expression}

#### Understanding Regular Expressions

**Regular Expressions** are a feature of
[UNIX](http://www.robelle.com/smugbook/unix.html). They describe a
pattern to match, a sequence of characters, not words, within a line of
text. Here is a quick summary of the special characters used in the
[grep](#grep) tool and their meaning:

[Text version.](http://www.robelle.com/smugbook/regexpr3.txt)

  ------------------ --- -------------------------------------------------------------------------------------------------------------
  \^ (Caret)         =   match expression at the start of a line, as in \^A.
  \$ (Question)      =   match expression at the end of a line, as in A\$.
  \\ (Back Slash)    =   turn off the special meaning of the next character, as in \\\^.
  \[ \] (Brackets)   =   match any **one** of the enclosed characters, as in \[aeiou\]. Use Hyphen \"-\" for a range, as in `[0-9]`.
  \[\^ \]            =   match any one character **except** those enclosed in \[ \], as in \[\^0-9\].
  . (Period)         =   match a single character of any value, except end of line.
  \* (Asterisk)      =   match zero or more of the preceding character or expression.
  \\{x,y\\}          =   match **x** to **y** occurrences of the preceding.
  \\{x\\}            =   match exactly **x** occurrences of the preceding.
  \\{x,\\}           =   match **x** or more occurrences of the preceding.
  ------------------ --- -------------------------------------------------------------------------------------------------------------

As an [MPE](http://www.robelle.com/smugbook/mpe.html) user, you may find
regular expressions difficult to use at first. Please persevere, because
they are used in many UNIX tools, from **more** to **perl**.
Unfortunately, some tools use simple regular expressions and others use
extended regular expressions and some extended features have been merged
into simple tools, so that it looks as if every tool has its own syntax.
Not only that, regular expressions use the same characters as shell
[wildcarding](http://www.robelle.com/smugbook/wildcard.html), but they
are **not** used in exactly the same way. What do you expect of an
operating system built by graduate students?

Since you usually type regular expressions within shell commands, it is
good practice to enclose the regular expression in single quotes (\') to
stop the shell from expanding it before passing the argument to your
search tool. Here are some examples using **grep**:

[Text version.](http://www.robelle.com/smugbook/regexpr4.txt)

  ------------------------------ ------------------------------------------------------
  grep smug files                {search *files* for lines with \'smug\'}
  grep \'\^smug\' files          {\'smug\' at the start of a line}
  grep \'smug\$\' files          {\'smug\' at the end of a line}
  grep \'\^smug\$\' files        {lines containing only \'smug\'}
  grep \'\\\^s\' files           {lines starting with \'\^s\', \"\\\" escapes the \^}
  grep \'\[Ss\]mug\' files       {search for \'Smug\' or \'smug\'}
  grep \'B\[oO\]\[bB\]\' files   {search for BOB, Bob, BOb or BoB }
  grep \'\^\$\' files            {search for blank lines}
  grep \'\[0-9\]\[0-9\]\' file   {search for pairs of numeric digits}
  ------------------------------ ------------------------------------------------------

**Back Slash** \"\\\" is used to *escape* the next symbol, for example,
turn off the special meaning that it has. To look for a Caret \"\^\" at
the start of a line, the expression is `^\^`. **Period** \".\" matches
any single character. So `b.b` will match \"bob\", \"bib\", \"b-b\",
etc. **Asterisk** \"\*\" does not mean the same thing in regular
expressions as in wildcarding; it is a modifier that applies to the
preceding single character, or expression such as `[0-9]`. An asterisk
matches **zero** or more of what precedes it. Thus `[A-Z]*` matches any
number of upper-case letters, including none, while `[A-Z][A-Z]*`
matches **one** or more upper-case letters.

The **vi** editor uses `\< \>` to match characters at the beginning
and/or end of a **word boundary**. A word boundary is either the edge of
the line or any character except a letter, digit or underscore \"\_\".
To look for `if`, but skip `stiff`, the expression is `\<if\>`. For the
same logic in **grep**, invoke it with the **-w** option. And remember
that regular expressions are **case-sensitive**. If you don\'t care
about the case, the expression to match \"if\" would be `[Ii][Ff]`,
where the characters in **square brackets** define a character set from
which the pattern must match one character. Alternatively, you could
also invoke **grep** with the **-i** option to ignore case.

Here are a few more examples of **grep** to show you what can be done:

[Text version.](http://www.robelle.com/smugbook/regexpr5.txt)

  ---------------------------------------- --------------------------------------------
  grep \'\^From: \' /usr/mail/\$USER       {list your mail}
  grep \'\[a-zA-Z\]\'                      {any line with at least one letter}
  grep \'\[\^a-zA-Z0-9\]                   {anything not a letter or number}
  grep \'\[0-9\]\\{3\\}-\[0-9\]\\{4\\}\'   {999-9999, like phone numbers}
  grep \'\^.\$\'                           {lines with exactly one character}
  grep \'\"smug\"\'                        {\'smug\' within double quotes}
  grep \'\"\*smug\"\*\'                    {\'smug\', with or without quotes}
  grep \'\^\\.\'                           {any line that starts with a Period \".\"}
  grep \'\^\\.\[a-z\]\[a-z\]\'             {line start with \".\" and 2 lc letters}
  ---------------------------------------- --------------------------------------------

------------------------------------------------------------------------

[![\[Robelle\]](regexpr_soubory/robelle.gif){align="bottom"}](http://www.robelle.com/)
[![\[SmugBook\]](regexpr_soubory/smug.gif)](http://www.robelle.com/smugbook/welcome.html)
[![\[Index\]](regexpr_soubory/index.gif)](http://www.robelle.com/smugbook/index.html)
[![\[Unix\]](regexpr_soubory/chapter.gif)](http://www.robelle.com/smugbook/unix.html)
[![\[Prev\]](regexpr_soubory/up.gif)](http://www.robelle.com/smugbook/manpages.html)
[![\[Next\]](regexpr_soubory/down.gif)](http://www.robelle.com/smugbook/whence.html)
