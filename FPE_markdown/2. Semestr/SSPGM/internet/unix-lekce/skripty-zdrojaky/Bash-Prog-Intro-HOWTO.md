---
title: "Bash-Prog-Intro-HOWTO.html"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/internet/unix-lekce/skripty-zdrojaky/Bash-Prog-Intro-HOWTO.html"
date: 2009-05-01
type: HTML
---

[Next](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-1.html) Previous
Contents

------------------------------------------------------------------------

# BASH Programming - Introduction HOW-TO

## by Mike G `mikkey at dynamo.com.ar`

Thu Jul 27 09:36:18 ART 2000

------------------------------------------------------------------------

*This article intends to help you to start programming
basic-intermediate shell scripts. It does not intend to be an advanced
document (see the title). I am NOT an expert nor guru shell programmer.
I decided to write this because I\'ll learn a lot and it might be useful
to other people. Any feedback will be apreciated, specially in the patch
form :)*

------------------------------------------------------------------------

## [1.]{#toc1} [Introduction](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-1.html)

-   [1.1 Getting the latest
    version](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-1.html#ss1.1)
-   [1.2
    Requisites](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-1.html#ss1.2)
-   [1.3 Uses of this
    document](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-1.html#ss1.3)

## [2.]{#toc2} [Very simple Scripts](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-2.html)

-   [2.1 Traditional hello world
    script](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-2.html#ss2.1)
-   [2.2 A very simple backup
    script](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-2.html#ss2.2)

## [3.]{#toc3} [All about redirection](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-3.html)

-   [3.1 Theory and quick
    reference](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-3.html#ss3.1)
-   [3.2 Sample: stdout 2
    file](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-3.html#ss3.2)
-   [3.3 Sample: stderr 2
    file](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-3.html#ss3.3)
-   [3.4 Sample: stdout 2
    stderr](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-3.html#ss3.4)
-   [3.5 Sample: stderr 2
    stdout](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-3.html#ss3.5)
-   [3.6 Sample: stderr and stdout 2
    file](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-3.html#ss3.6)

## [4.]{#toc4} [Pipes](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-4.html)

-   [4.1 What they are and why you\'ll want to use
    them](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-4.html#ss4.1)
-   [4.2 Sample: simple pipe with
    sed](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-4.html#ss4.2)
-   [4.3 Sample: an alternative to ls -l
    \*.txt](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-4.html#ss4.3)

## [5.]{#toc5} [Variables](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-5.html)

-   [5.1 Sample: Hello World! using
    variables](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-5.html#ss5.1)
-   [5.2 Sample: A very simple backup script (little bit
    better)](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-5.html#ss5.2)
-   [5.3 Local
    variables](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-5.html#ss5.3)

## [6.]{#toc6} [Conditionals](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-6.html)

-   [6.1 Dry
    Theory](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-6.html#ss6.1)
-   [6.2 Sample: Basic conditional example if ..
    then](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-6.html#ss6.2)
-   [6.3 Sample: Basic conditional example if .. then \...
    else](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-6.html#ss6.3)
-   [6.4 Sample: Conditionals with
    variables](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-6.html#ss6.4)

## [7.]{#toc7} [Loops for, while and until](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-7.html)

-   [7.1 For
    sample](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-7.html#ss7.1)
-   [7.2 C-like
    for](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-7.html#ss7.2)
-   [7.3 While
    sample](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-7.html#ss7.3)
-   [7.4 Until
    sample](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-7.html#ss7.4)

## [8.]{#toc8} [Functions](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-8.html)

-   [8.1 Functions
    sample](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-8.html#ss8.1)
-   [8.2 Functions with parameters
    sample](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-8.html#ss8.2)

## [9.]{#toc9} [User interfaces](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-9.html)

-   [9.1 Using select to make simple
    menus](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-9.html#ss9.1)
-   [9.2 Using the command
    line](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-9.html#ss9.2)

## [10.]{#toc10} [Misc](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-10.html)

-   [10.1 Reading user input with
    read](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-10.html#ss10.1)
-   [10.2 Arithmetic
    evaluation](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-10.html#ss10.2)
-   [10.3 Finding
    bash](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-10.html#ss10.3)
-   [10.4 Getting the return value of a
    program](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-10.html#ss10.4)
-   [10.5 Capturing a commands
    output](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-10.html#ss10.5)
-   [10.6 Multiple source
    files](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-10.html#ss10.6)

## [11.]{#toc11} [Tables](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-11.html)

-   [11.1 String comparison
    operators](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-11.html#ss11.1)
-   [11.2 String comparison
    examples](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-11.html#ss11.2)
-   [11.3 Arithmetic
    operators](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-11.html#ss11.3)
-   [11.4 Arithmetic relational
    operators](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-11.html#ss11.4)
-   [11.5 Useful
    commands](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-11.html#ss11.5)

## [12.]{#toc12} [More Scripts](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-12.html)

-   [12.1 Applying a command to all files in a
    directory.](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-12.html#ss12.1)
-   [12.2 Sample: A very simple backup script (little bit
    better)](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-12.html#ss12.2)
-   [12.3 File
    re-namer](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-12.html#ss12.3)
-   [12.4 File renamer
    (simple)](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-12.html#ss12.4)

## [13.]{#toc13} [When something goes wrong (debugging)](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-13.html)

-   [13.1 Ways Calling
    BASH](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-13.html#ss13.1)

## [14.]{#toc14} [About the document](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-14.html)

-   [14.1 (no)
    warranty](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-14.html#ss14.1)
-   [14.2
    Translations](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-14.html#ss14.2)
-   [14.3 Thanks
    to](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-14.html#ss14.3)
-   [14.4
    History](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-14.html#ss14.4)
-   [14.5 More
    resources](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-14.html#ss14.5)

------------------------------------------------------------------------

[Next](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-1.html) Previous
Contents
