---
title: "steffen_gross_thesis.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/zdroje/I18N thesis/steffen_gross_thesis.pdf"
date: 2010-01-28
type: PDF (text-based)
---

Internationalization and Localization of Software
by
Steffen Gross

A Review Paper Submitted to the
Eastern Michigan University
Department of Computer Science

In Partial Fulfillment of the Requirements for the
Master of Science
in Computer Science

Approved at Ypsilanti, Michigan on June 19th, 2006

________________________________________
Professor William W. McMillan

________________________________________
Professor Ben Keller

________________________________________
Professor Edward Garrett

Abstract
This thesis is a review paper that covers and summarizes the way software is prepared for international markets nowadays.
Internationalization and localization of software are the key topics this thesis deals with.
Therefore it first analyzes and portrays major differences in culture and language and gives advice
about how to deal with these differences when developing internationally usable software.
Then it describes some internationalization recommendation for helping to prepare software for
easy localization. In this context a standard encoding scheme for international characters and text is
explained.
Furthermore, an example is provided of how internationalization and localization of software is
done by means of a popular existing operating system platform.
Finally, some commercial software localization tools and Open Source XML standards are shown
making the processes of internationalization and localization easy and efficient.

Contents
List of Figures

iii

List of Listings

iv

Foreword

1

1

Introduction

2

1.1

The Needs of Software for the Global Market . . . . . . . . . . . . . . . . . . . .

2

1.2

Terms and Definitions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

2

1.2.1

Globalization . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

3

1.2.2

Internationalization . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

3

1.2.3

Localization . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

3

Structure of the Thesis . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

4

Internationalization and Localization - Problem Description and Formal Definition

6

2.1

Problem Description . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

7

2.1.1

Components of Internationalization . . . . . . . . . . . . . . . . . . . . .

8

2.1.2

Components of Localization . . . . . . . . . . . . . . . . . . . . . . . . .

10

Formal Definition . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

13

2.2.1

Definition of the Internationalization Process . . . . . . . . . . . . . . . .

15

2.2.2

Definition of the Localization Process . . . . . . . . . . . . . . . . . . . .

18

Collaborations during the process of internationalization and localization . . . . . .

20

1.3
2

2.2

2.3
3

Internationalization of Software - Difficulties & Recommendations

23

3.1

24

Prerequisites for localizing software . . . . . . . . . . . . . . . . . . . . . . . . .
i

3.2

3.3

4

24

3.1.2

Solution for separating resources . . . . . . . . . . . . . . . . . . . . . . .

25

All about Strings . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

27

3.2.1

String handling and ordering in source files . . . . . . . . . . . . . . . . .

27

3.2.2

Sorting Algorithms . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

31

Unicode . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

31

3.3.1

What is Unicode? . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

31

3.3.2

Why should Unicode be used? . . . . . . . . . . . . . . . . . . . . . . . .

32

3.3.3

Unicode Encodings . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

33

3.3.4

Pitfalls of Unicode . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

34

3.3.5

Unicode and its use in programming languages . . . . . . . . . . . . . . .

35
41

4.1

Preliminaries under Microsoft Windows . . . . . . . . . . . . . . . . . . . . . . .

41

4.2

Microsoft and Unicode . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

42

4.2.1

Variable Types . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

43

4.2.2

System Functions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

44

4.2.3

Using Standard C Libraries under Microsoft Windows . . . . . . . . . . .

44

Mirroring for Right-to-Left Languages . . . . . . . . . . . . . . . . . . . . . . . .

45

4.3.1

Mirroring in Resources . . . . . . . . . . . . . . . . . . . . . . . . . . . .

47

4.3.2

Mirroring in Code . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

48

4.3.3

Handling Direction-Sensitive Graphics . . . . . . . . . . . . . . . . . . .

50

Software Localization Tools and Standards

52

5.1

Localization Tools . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

53

5.1.1

Alchemy Catalyst 6.0 . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

53

5.1.2

PASSOLO 5.0 . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

56

Open Source Standards for Localization . . . . . . . . . . . . . . . . . . . . . . .

58

5.2.1

TMX - Translation Memory eXchange . . . . . . . . . . . . . . . . . . .

58

5.2.2

XLIFF - XML Localization Interchange File Format . . . . . . . . . . . .

59

5.2

6

Keeping source code clear from localizable resources . . . . . . . . . . . .

Localization by Example - Microsoft Windows

4.3

5

3.1.1

Outlook

61

Bibliography

63

ii

List of Figures
1.1

Relation between G11n, I18n and L10n . . . . . . . . . . . . . . . . . . . . . . .

4

2.1

English main page of wikipedia.org . . . . . . . . . . . . . . . . . . . . . . . . .

11

2.2

Arabic main page of wikipedia.org . . . . . . . . . . . . . . . . . . . . . . . . . .

12

2.3

Process and component diagram of I18n and L10n . . . . . . . . . . . . . . . . . .

14

2.4

Diagram of the Software Internationalization Process . . . . . . . . . . . . . . . .

17

2.5

The ”unknown” Localization Process . . . . . . . . . . . . . . . . . . . . . . . . .

18

2.6

Diagram of the Software Localization Process . . . . . . . . . . . . . . . . . . . .

20

2.7

Collaboration between groups of people during internationalization and localization
process . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

22

3.1

Comparison of the English and Spanish ”OK”-buttons[15] . . . . . . . . . . . . .

31

4.1

Arabic Windows XP desktop[16] . . . . . . . . . . . . . . . . . . . . . . . . . . .

46

4.2

Coordinate transformation[16] . . . . . . . . . . . . . . . . . . . . . . . . . . . .

47

4.3

Notepad.exe file that has been mirrored by adding two LRMs[16] . . . . . . . . . .

48

4.4

Setting the mirroring style of the dialog resources within the resource editor of Visual Studio 6[16] . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

49

4.5

Example of a direction-sensitive arrow that changes meaning when mirrored[16] .

50

5.1

Screenshot of Alchemy Catalyst 6.0 . . . . . . . . . . . . . . . . . . . . . . . . .

55

5.2

Screenshot of PASSOLO 5.0 . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

57

iii

Listings
3.1

Example of strings that get composed during application’s runtime . . . . . . . . .

27

3.2

Written out sentences for better translation . . . . . . . . . . . . . . . . . . . . . .

28

3.3

English sentence broken up into three pieces . . . . . . . . . . . . . . . . . . . . .

28

3.4

German translation of the sentence . . . . . . . . . . . . . . . . . . . . . . . . . .

28

3.5

Sentence translated back into English . . . . . . . . . . . . . . . . . . . . . . . .

29

3.6

Java code example - opening a file which is in the default Locale encoding . . . . .

36

3.7

Java - Specifiying encoding of file . . . . . . . . . . . . . . . . . . . . . . . . . .

37

3.8

Java - Converting from one encoding to another . . . . . . . . . . . . . . . . . . .

37

3.9

Java - using non-ASCII characters in source code . . . . . . . . . . . . . . . . . .

38

3.10 C code example - modifying locale settings . . . . . . . . . . . . . . . . . . . . .

39

4.1

ASCII version of type char . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

43

4.2

Unicode version of type char . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

43

4.3

Using macro ”L” in Unicode version of type char . . . . . . . . . . . . . . . . . .

43

4.4

ASCII version of ’printf’ function . . . . . . . . . . . . . . . . . . . . . . . . . .

45

4.5

Unicode version of ’printf’ function . . . . . . . . . . . . . . . . . . . . . . . . .

45

iv

Foreword
Software companies want to sell their products in markets all over the world. But a lot of those
companies think that software is already ”world-ready” if it is just developed for the English spoken
market. But they do not consider that there are millions of people in the world who don’t speak
English or have trouble in understanding the meanings of metaphors and icons of the user interface
adapted from the North-American or Western-European culture. They are excluded from using such
software and usually change to a software product which is available in their language.
So what can these companies learn about how to internationalize software and how to offer their
products in many different languages and for different cultures?
This thesis seeks to give an answer to those questions and to explain popular methods of localizing
software.

1

Chapter 1

Introduction
1.1

The Needs of Software for the Global Market

In times where the markets all over the world are growing together, especially software companies
tend to be ”global players” and want to sell their software products everywhere. And, indeed, there
is an international market for plenty of software applications. Therefore the requirements on the
software to be multilingual is increasing heavily, and developers should consider this.
Unfortunately these requirements often are being followed only late in the development process.
Although it is getting more and more important for software developers to deal with this topic,
methods, technologies and tools are only rarely known. Naturally the requirements on multilingual
software is manifold and there is no universal concept for internationalization. But for the most
standard situations methods and technologies have been established, and it makes sense having a
closer look at them before making own concepts.

1.2

Terms and Definitions

The following terms are usually used when talking about modifying software for different languages
and cultures. They are closely connected to each other. Sometimes they are even used interchangeably.
2

1.2.1 Globalization

1.2.1

3

Globalization

Globalization, also known as G11n, ”addresses all of the enterprise issues associated with making
a company truly global. For the globalization of products and services this involves integrating all
of the internal and external business functions with marketing, sales, and customer support in the
world market”[27].
This term takes place outside software development and will be not discussed in this thesis.

1.2.2

Internationalization

The development of multilingual software is divided into two phases: At first software has to be
developed or modified to be translated easily into several different languages. The goal of this
internationalization is to get a software which does not contain any language- or culture-dependent
information. Also it should work in every region of the world in a way the users want.
Internationalization1 of software is a requirement which affects design as well as implementation.
And the bad thing about it is that it can possibly stand in conflict with other requirements. Disregarding the ability of software to be run multilingual in a later state can cause a software slanted towards
other goals of optimization. Hence internationalization of software requires special diligence on all
tasks related to software design and implementation.

1.2.3

Localization

In the second step the internationalized software has to be adjusted to the respective target market.
This process is called localization2 , and it is not only about the translation of text the user interface
contains, but also about further adjustments. These adjustments can be, for example:
• Extension of the dialog fields if the translation makes messages longer.
• Cultural circumstances that require adjustments of bitmaps, icons or cursors.
1 Internationalization: Also known as i18n, where the number replaces the letters which have been substituted.
2 localization: Also known as i10n

1.3 Structure of the Thesis

4

If software has been internationalized continuously and cleanly, no programmers should be necessary for localization.
Figure 1.1 shows the relation between Globalization, Internationalization and Localization. Globalization is a company’s issue, affecting indirectly software development processes taking place inside
the company. Successful Localization of the company’s software then depends directly on the effort
being made in advance during internationalization of the same software.

Figure 1.1: Relation between G11n, I18n and L10n

1.3

Structure of the Thesis

Chapter 2 gives a problem description and a formal definition of the internationalization and localization processes. This includes a presentation of major cultural and linguistic differences. Furthermore it describes what kinds of changes have to be made to obtain a localized software application,

1.3 Structure of the Thesis

5

and finally collaboration between people involved in the internationalization and localization processes is explained.
Chapter 3 deals with major difficulties and recommendations for internationalizing software. First
a few ”prerequisites” for localizing software are shown. It is recommended to pay attention to them
for easing the following localization process. Then major issues about string handling are shown
before the main focus changes to Unicode3 . There is an overview about how to work with Unicode
in different programming languages.
Chapter 4 points out the steps to make when localizing applications for the Microsoft Windows
operating system. Here, as in the previous chapter, there are at first some preliminaries discussed.
Then the focus again changes to Unicode due to the fact that Unicode is playing a major role when
localizing windows applications. The third part of this chapter outlines the mirroring process for
right-to-left languages.
Chapter 5 presents an overview of software localization tools and standards to simplify and to make
the localization process of software more efficient. These are on the one hand mainly commercial
third-party localization tools and on the other hand Open Source XML standards that are available
for free.
Chapter 6 is the conclusion of the thesis. It discusses a possible outlook about how future development may go on and in which direction it possibly may steer.

3 Unicode is an international standard that defines a digital code for every character, glyph and ideogram of all known

languages worldwide.

Chapter 2

Internationalization and Localization Problem Description and Formal
Definition
As an introduction to the topic of internationalizing and localizing software, this chapter describes
what kinds of changes have to be made to obtain a localized software application. These changes
affect mostly certain differences between countries, their cultures and their locales. For a definition
of locales see section 2.1.2.3. It is not only the language that has to be translated. There are many
other issues which have to be considered and converted during localization.
Furthermore, there will be a formal description of the problem of internationalizing and localizing
software. This should help future developers and localizers identify certain problems and considerations in the process of localizing their software.
Finally, the collaboration between people involved in the internationalization and localization processes is explained and it is shown how they can benefit from each other.

6

2.1 Problem Description

2.1

7

Problem Description

”Translating” a software application needs a variety of different steps. It starts with handling foreign data, continues in translating the user interface and ends up with supporting country-specific
formats which are collected in locales (section 2.1.2.3). But it is not said that all steps are necessary
for localizing each application. Furthermore, it depends on the purpose of the application and the
chance of placing the software product successfully on different foreign markets.
We can distinguish between the following internationalization and localization levels[14]:
1. U.S.-English product only
This is the non-localized version of the software and therefore a complete ”English-language
product only”. All locales are set to U.S.-English. In some cases it may be difficult using this
software in other, non-U.S. English-Speaking countries.
2. English product handling European data
This is also not localized software so far. But it supports most single-byte character sets used
in European countries and it is able to handle the main cultural conventions like date, time
and monetary formats.
3. English product handling Far-Eastern data
This step is similar to the step before, but more effort is required to support Far-Eastern data
like Japanese or Chinese. It requires changing the logic of the U.S. software and maybe it is
necessary to change the architecture of the whole software application.
4. English product handling bidirectional data
Supporting bidirectional data requires special logic and architecture. The software must be
capable of displaying and handling data which is read from left to right and also from right
to left. At this stage the software product is capable of supporting almost every kind of data
from all over the world. But the user interface is still in English.
5. Partial or full translation of the English user interface and documentation
This is usually the most complex and most expensive step in software localization. But it
makes sure that the software can be used by non-English speaking people. If the budget is
limited and doesn’t allow a complete translation, companies can choose which component
they want to translate and which not:

2.1.1 Components of Internationalization

8

• User Interface
• Online Help
• Tutorials
• Sample programs
• Printed Documentation
6. Full localization plus local market features
Fully localized software with local market features is perfectly tailored for a local market. It
supports the specific language and locale as well as market-specific features like supporting
an import filter for specific formats of other products which are popular on this market.

2.1.1

Components of Internationalization

Now that different stages of internationalization and localization have been discussed, it is very
interesting to see which components are affected by internationalization. These components are
important for localization as well, but they should already be fit for localization before any modifications due to localization are made on the software application. Therefore the internationalization
step is made before the localization. So the following list gives an overview of what areas internationalization can affect and what problems can occur:[14]
• User Interfaces and printed documentation
This includes error messages, help text, menus, prompts and graphics. Also the documentation to any software application should be translated with care and be free of any countryspecific idioms or metaphors.
• Character classification
English usually classifies only 52 characters as ”alphabetic”. These are [A - Z] and [a - z].
But many other languages have more characters in their alphabet like the French é and è, or
the German Umlaute ä, ö and ü.
• Character transliteration
Converting characters form upper case to lower (or vice versa) case can make problems if the
character is not listed in the English ASCII code page.

2.1.1 Components of Internationalization

9

• Numerical/monetary formats
Displays of amounts of money vary from country to country. In the U.S. the dot ’.’ is used to
separate the currency’s whole and fractional units. In Germany the Comma ’,’ is used instead.
Also different currency signs are used. These issues are collected in a countries locale (section
2.1.2.3).
• Date/time formats
Same as above the exact display of date and time is collected in a country’s locale which is
discussed briefly in section 2.1.2.3.
• Collating or sorting
In most applications sorting means sorting in ASCII code page order. But this is not correct
for foreign languages. Section 3.2.2 tells more about sorting.
• Regular expressions
”Regular expressions are patterns used for searching text in data”[14]. Therefore many applications use pattern matching. But the matching often doesn’t work properly for foreign
languages due to its bias towards English and the ASCII code page. This problem is associated with character classification and collating and sorting.
• Encoding schemes
During internationalization multiple encoding schemes or code pages have to be integrated.
An encoding scheme ”illustrates the one-to-one mapping between a character and the computer’s bit representation”. The most common code page is ASCII, but ASCII ”doesn’t support much more than the English language”[14].
• Character versus byte processing
Internationalized software needs to support multibyte code pages, because ASCII with its onebyte encoding does not support all worldwide characters used by languages. Especially the
Far-Eastern languages are multibyte code. So a software application has to support correctly
character and byte-processing.
• Text directionality
Text can flow in different directions. Western languages are written and read from left to
right, while Hebrew and Arabic form right to left. So the internationalized software has to
support both kinds of text flows.

2.1.2 Components of Localization

10

• Input method editors
Many languages, especially Asian ones, have more characters in their language than keys on
the keyboard. So a mechanism or solution has to be found and implemented to enable the
typing of all character sets by using a limited number of keys.
The key issue is that none of these components should be hard-coded in the source code. ”All this
information should be kept external to the source code” but be accessible by the software. The clue
is to use it at runtime to communicate with users in their own language and use all local conventions.
The only component which can be integrated in the source code might be the encoding schemes. If
Unicode is used, no other encoding schemes should be necessary. Sections 3.3 and 4.2 give more
details about the use of Unicode. More general information about components to be separated from
source code can be read in section 3.1.1.

2.1.2

Components of Localization

Now that all components relevant for internationalization have been presented, the following section
gives an overview of what to consider when localizing software. There are some topics related to
Language, Layout, graphics and locales.

2.1.2.1

Language and Layout

Language and screen layout of a user interface are connected together very closely. Languages are
read in different ways. English and other Western European languages are read from left to right.
Others, for example Arabic, are read from right to left. This also affects the eye-movement over
screens. People who are used to read and write from right to left would also have their first glance
on a picture at the top right corner and then move their eyes to the bottom left corner. Whereas other
people from occidental cultures (where languages are written and read from left to right) would
at first look at the top left corner and then move their eyes to the bottom right corner. Therefore
the layout of a user interface has to be mirrored for Arabic localization. As an example figure 2.1
shows a screenshot of the English main page of wikipedia.org.1 Figure 2.2 shows a screenshot of
1 Wikipedia.org - ”the free encyclopedia that anyone can edit” (http://www.wikipedia.org)

2.1.2 Components of Localization

11

the Arabic main page of wikipedia.org. As the Arabic language is written and read from right to
left, the whole interface layout has been mirrored.

Figure 2.1: English main page of wikipedia.org
There are some more aspects involved in localizing a user interface. In general, user interfaces have
to fulfill the following requirements[6]:
• Communication has to be done in the country’s native language.
• Country-specific writing symbols (e.g. punctuation) have to be supported.
• Native display of date, currency, weight scales, numbers and addresses have to be supported.
Those attributes are defined in locales (section 2.1.2.3).
• Consider how the work environment of the specific country looks and supports people’s nat-

2.1.2 Components of Localization

12

ural work habits.
• Keep the communication polite and friendly.

Figure 2.2: Arabic main page of wikipedia.org

2.1.2.2

Visual Language

Computers communicate with their users not only with written text. There are also many signs and
icons which have their own special meanings. Users must understand these meanings to operate with
them properly. But many signs differ from country to country, even if in these countries the same
language is spoken. For example, if a user interface adapts some American traffic signs for its user
interface, a lot of users, e.g. those coming from Great Britain, might have difficulties understanding
their meaning, even though their native language is English, too, because Great Britain uses different

2.2 Formal Definition

13

traffic signs than the U.S. Developers of a globally used user interface should be aware of that fact.
A better solution is to use signs that are internationally known.
Also using puns in user interfaces should be avoided. In some countries they might be understood
right but it is for sure, that their meanings are not understood all over the world.

2.1.2.3

Locales

Locales are defined to collect and support national differences in formats of e.g. numbers, currency, calendars, date, time, units of measures, postal addresses and telephone numbers. They can
significantly differ between two countries even though they have the same official language.
Here are some examples of differences in locales:
• Differences in displaying numbers, e.g., between the U.S. and Germany. In the U.S. the point
separates the decimals, and the comma the thousands (1,234.56). In Germany it is vice versa
(1.234,56).
• The display of date and time can be different, with some countries using the 12-hour system (with ”am” and ”pm”) and others using the 24-hour system, where e.g. ”23:00” means
”11:00pm”.
• The arrangement of date displays differs, e.g. the order in the U.S. is month/day/year and in
Germany day.month.year (even the character for separating the numbers can be different).
• Units of measurement have to be changed, as well. The U.S. uses the English system of
measurement, while most other countries in the world use the metric system.

2.2

Formal Definition

This section covers the formal definition of internationalization and localization of software. First
all steps of the internationalization process are defined. Then all steps of the localization process
are defined. Furthermore the collaboration between developers, users and translators is shown and
explained.

2.2 Formal Definition

14

To get an initial overview of the process of internationalization and localization the diagram in
Figure 2.3 shows how components and processes may belong together.

Figure 2.3: Process and component diagram of I18n and L10n

2.2.1 Definition of the Internationalization Process

2.2.1

15

Definition of the Internationalization Process

The internationalization process starts right in the beginning when computer scientists are collecting
software requirements for the application to be developed. So this process is almost the same as in
other software requirements engineering processes.
As the very first step, a company developing localizable software should make clear statements
about how much they want their software to be localized in a later state. The more they want
to localize the more they have to internationalize. Localization nuances are already described in
section 2.1. Of course it is recommended to internationalize as much of the software as possible
or as the financial budget and time-frame allows. Experience in software development has shown
more than once that software development projects have been expanded in different ways during
their maintenance as opposed to formerly plans. Most often sudden changes in requirements or
adjustments in functionality for other markets cause those redirections in software development.
The same can happen to rudimentarily internationalized software: At first it was planned to sell
the product only in a limited number of markets, when suddenly and unpredictably a huge demand
occurs for this software from other markets. Then it would be much more difficult to adapt such a
software for those markets. This thesis assumes that internationalization and localization is done at
the highest level as described in the last item of section 2.1.
The special thing about developing internationalized software is to make sure that all components
described in section 2.1.1 are separated from the source code. All data processing functionality
should be integrated as modules. This ensures that certain modules can be exchanged with others having slightly different functionality as necessary. The functionality for sorting and collating
would be an example, because sort sequences differ in some countries. In the Spanish language, for
example, the ’ch’ is sorted as a separate letter after ’c’ but before ’d’ while other languages which
use the Roman alphabet would sort a ’ch’ between ’cg’ and ’ci’.
Also Locales can be integrated as modules. Depending on the programming language to be used,
Locales don’t need to be developed. Java, for example, has a huge set of supported Locales where all
necessary changes are already implemented. At this stage considerations should be made also about
what kind of encoding scheme is to be used. Unicode gives the most freedom to developers but
needs more memory resources due to 2-byte and 3-byte character sets. If software is planned to be
localized only for European or South American markets, the ISO 8859-standards with 1-byte char
sets would be sufficient. But here as in the discussion about Locales, the use of the programming

2.2.1 Definition of the Internationalization Process

16

language plays a role, too. Java, for example, has full support of Unicode. More information about
the use of Unicode in the Java programming language can be read in section 3.3.5.1.
Text Strings which are used to communicate with the users should be separated completely from
the source code. More about this can be read in chapter 3 which also provides some methods of
resolution for some issues. Figure 2.4 shows a UML2 -diagram explaining all branches of the process
of software internationalization.

2 UML: Unified Modelling Language - an object modelling and specification language used in software engineering

Figure 2.4: Diagram of the Software Internationalization Process

2.2.1 Definition of the Internationalization Process
17

2.2.2 Definition of the Localization Process

2.2.2

18

Definition of the Localization Process

Now that the software to be localized is completely internationalized, the next thing is to specify the
localization process.

Figure 2.5: The ”unknown” Localization Process
So what is behind this cloud in figure 2.5 that makes sure that formerly non-localized software is
suddenly translated into dozens of different languages and therefore usable in almost all areas of the
world without forcing users to understand English?
To successfully localize software there are three major steps:
1. Translating all relevant text strings of the user interface with which the application is communicating with the user. Optionally the printed documentation can also be translated.
2. Adjusting graphics, colors, menus and if necessary text directionality of the user interface

2.2.2 Definition of the Localization Process

19

for different cultures to allow it to display text correctly and look familiar to users of those
cultures. They should not get the impression of working with foreign software.
3. Defining a locale that makes sure that all country-specific formats are displayed correctly.
Translating text strings of software (including the user interface as well as the printed documentation) is a process usually done by human translators, so there’s the possibility of outsourcing it to
translation companies. But often developers take the role of the translators and translate their own
software. Neither the one nor the other way is completely free of error. Developers, for example,
know exactly what parts to translate and which parts not to. They know which variables can carry
which text strings. So they know how the whole phrase has to be translated correctly. More information about this topic can be read in section 3.2. The disadvantage of letting developers do the
translation is that translating is not their main profession. That means wording and phrasing may
not be as accurate as if it were done by professional translators. Another point to mention is that developers translating software are unavailable for other projects during the time translation takes. If
translation is done by professional translators, they have to know exactly where the string resources
are stored to be translated and which parts not to translate. So collaboration between developers and
translators takes place. Another option is to let software be translated by another piece of software.
But this localization software also needs human interaction. Most of these applications employ a
translation vocabulary that formally has to be defined or the application has to be fed with words
from formal translations. Section 5.1 gives some short reviews of localization software.
Adjusting graphics, colors and menus for other cultures and languages should be done by a person
who is familiar with the cultural and linguistic conditions of the specific country. Whether this
person is a translator or developer doesn’t matter. It is even better to let this process be done by a
usability engineer who knows best about software ergonomics and cultural differences. Graphics
and maybe some colors of the user interface have to be changed as described in 2.1.2.2. But a lot
of companies, for example Microsoft Windows, use colors in their user interfaces consistent with
their corporations visual identity. Changing text directionality (mirroring) for right-to-left languages
should be done pretty easily. This feature should be implemented as a simple switch to be changed.
More information about mirroring user interfaces can be found in section 4.3.
Defining a locale is only required if the programming language the software was developed with
or the operating system the software is running on do not provide a ”global” locale setting by
themselves. If during internationalization the process of defining a locale has been simplified, this

2.3 Collaborations during the process of internationalization and localization

20

process can be done by a human translator and does not need to be done by a developer. The
simplification could be done, for example, through defining a locale template where the translator
has only to fill in the right country-specific formats as described in section 2.1.2.3.
Recapitulating, figure 2.6 shows a diagram that gives a complete overview of the localization process with all steps included.

Figure 2.6: Diagram of the Software Localization Process

2.3

Collaborations during the process of internationalization and localization

Internationalization and localization are processes where still a lot of tasks are done by humans.
Therefore collaboration between those groups of people involved with internationalization and localization is recommended.

2.3 Collaborations during the process of internationalization and localization

21

There are three main groups of people:
1. Developers
2. Translators
3. Users
Developers create the software including all back-end and data processing functionality, the user
interface and, if necessary, a locale template (or even the whole locale). As described in 2.2.2, they
give advice to the translators about the resources to be translated.
Translators translate the string resources of the application (mostly of the user interface) with which
the software is communicating with the user. Translators may also define a country-specific locale
by using the locale template developed by the developers. They need feedback from the developers
about the resources to be translated as described in 2.2.2.
Users are using the software, whether localized or not. But for using the non-localized version the
users have to understand the English language and typical American metaphors to understand the
meanings of some graphics and buttons on the user interface (see section 2.1.2.2 for a brief discussion). Users can give very useful hints to developers to help them developing a user-friendly
software by giving advice for usability of the user interface to be used. Users coming from specific
countries can give very helpful information about locale-specific features to developers or translators, depending on who is creating the specific locale. But usually translators should know about
locale-specific features of the country into whose language they are translating.
Users and translators can help developers in validating and verifying their software product. While
users can give useful comments about usability of the software, translators can give comments about
the localized version and its string resources. Also users can give comments if data processing of
the localized version shows some errors (e.g. sorting algorithm is not correct).
Figure 2.7 shows at a glance how collaboration between those different human groups can take
place.

2.3 Collaborations during the process of internationalization and localization

22

Figure 2.7: Collaboration between groups of people during internationalization and localization
process

Chapter 3

Internationalization of Software Difficulties & Recommendations
There is an international market for plenty of software applications. Therefore the requirements on
the software to be multilingual is increasing heavily, and developers should consider this.
Unfortunately these requirements often are being followed only late in the development process.
Although it is getting more and more important for software developers to deal with this topic,
methods, technologies and tools are only rarely known. Naturally the requirements on multilingual
software is manifold and there is no universal concept for internationalization. But for the most
standard situations methods and technologies have been established, and it makes sense having a
closer look at them before making own concepts.
This chapter gives advice and an overview about requirements source code should fulfill during
internationalization so that it can be localized without huge effort.
Also it shows up difficulties which have to be faced and considered during internationalization. Only
well internationalized software is able to be localized for different languages and cultures easily and
effectively. Useful references are [15], [30] and [31].

23

3.1 Prerequisites for localizing software

3.1

24

Prerequisites for localizing software

The development of multilingual software is divided into two phases:
1. Software has to be developed or modified to be translated easily in several different languages.
The goal of this internationalization is, to get a software which does not contain any languageor culture-dependent information. Also it should work in every region of the world in a way
the users want it. Internationalization of software is a requirement, which affects design as
well as implementation. And the bad thing is that it can possibly stand in conflict with other
requirements. Disregarding the ability of a software to be run multilingual in a later state, can
cause a software to be biased too one-sidedly towards other goals of optimization. Anyway
internationalization of software is connected with additional work during its development.
2. In this step the internationalized software has to be adjusted to the respective target market.
This process is called localization, and it is not only about the translation of text the user
interface contains, but also about further adjustments. These adjustments can be for example
• Extension of the dialog fields if the translation makes messages longer.
• Cultural circumstances that requires adjustments of bitmaps, icons or cursors.
If a software has been internationalized continuously and cleanly, no programmers should be necessary for localization.

3.1.1

Keeping source code clear from localizable resources

Software can only be localized in an effective way if its source code, or in better words, the design
of the source code is prepared to handle all the differences explained in chapter 2. As long as
the design of the source code of a software is not systematically built up, translators or 3rd-party
localization software (for automatic localization) won’t have a chance to localize the own software.
The expression ”systematically built up” is defined especially in two ways which are given in the
following list:
• The executable application and its user interface must be separated from each other. Components requiring localization are usually[15]

3.1.2 Solution for separating resources

25

– Menus
– Messages
– Dialog boxes
– Prompts
– Images
– Sounds
– Toolbars
– Status bars
– Constants
• Text files, which for example contain error messages and comments given out to the user
during use of the software, have to be stored in external files. These files are being loaded
dynamically by the application.
As mentioned in 3.1 translators usually are no programmers. So imagine what could happen, if
translators have to pick out all the words and sentences that must be translated from the source code.
The chance that important code details will be deleted accidentally is very high. Also consider that
source code is always in a process of permanent modification. Translators would lose their overview
in the code very fast. This can cause translations of wrong code elements. For example names of
variables could be translated instead of messages, because the translators have little relation to the
functional code. On the other side these errors have to be corrected by the developers; overall a very
time and money consuming process.
Beware of hard-coded elements. They usually do not appear until the software is localized. So they
are very hard to find.

3.1.2

Solution for separating resources

A good and very simple solution for separating resources which have to be localized is to put them
in so called resource files. In the Microsoft Windows world, for example, Windows resource files or

3.1.2 Solution for separating resources

26

.NET assemblies files1 can be used. This solution has the advantages that these files are easy to edit
and avoid the need for recompiling source code after localization. Especially in the Windows World,
developers very often use these ”resource repositories” to store resources which are referenced in
different places in their code. But not all of them should or can be localized. The following list
gives an overview of what kinds of resources these resource repositories contain2 [15]:
• User interface resources. These resources can be localized without affecting or even losing
functionality.
• Resources used for the adaptation of a product. These resources can be fonts, locale
information, folder names, account names, etc. If such strings are not localized correctly,
they impact functionality. It is better to query these resources from the supporting platform
and not store them inside the application.
• Debug resources. Debug resources are useless for normal users. They are only helpful for
developers and support technicians. Due to their profession, they usually understand English.
Hence debug information may be localized or may be not. In neither way does it affect
functionality.
• Functional resources. These can be registry keys, procedure calls, message strings for communication between components, etc. They are all part of the basic functionality of a software.
So these resources can not be localized without affecting functionality.
Developers should make sure that these resources are not mixed up in common resource files. Translators and localizers do not have access to registry keys and they even should not have access to
them. So all localizable resources should be collected and stored outside of resource files that collect non-localizable information.

1 .NET assemblies files can be a executable .exe files or ”dynamic link library” .dll files.
2 This list only itemizes typical resources how they appear in Microsoft Windows, but it can be similar for applications

running on other operating systems.

3.2 All about Strings

3.2

27

All about Strings

The handling of strings and characters is the most important and most complex issue in internationalization. There are lots of issues that have to be considered. They are
• String handling and ordering in source files
• String Buffer Sizes
• Element Resizing of text fields in user interfaces
• Sorting algorithms

3.2.1

String handling and ordering in source files

Besides the fact that strings for display on user interfaces should be stored separately from the
source code, it is also important to know what kinds of faults should be avoided that probably can
make the localization process more difficult.

3.2.1.1

Generating strings during application runtime

The developer has to be careful with reusable sentences that are composed at the application’s
runtime. Listing 3.1, taken from [15] shows an example of constructing such sentences.
Listing 3.1: Example of strings that get composed during application’s runtime
"Are you sure you want to delete the file?" ;
"Are you sure you want to delete the directory?" ;
"Are you sure you want to delete the subdirectory?" ;
char s z S t r i n g [ ] = "Are you sure you want to delete the " ;
char s z F i n a l S t r i n g [ cbMaxSz ] = s z S t r i n g + s z D e l O b j e c t +"?" ;

The variable szDelObject can contain either a file, directory, or subdirectory. This technique is
very useful for the developers, but the translators will have problems finding out the right context.
Other than in English, there are many languages which have gender. Such constructed sentences

3.2.1 String handling and ordering in source files

28

can not be translated universally, because file, directory and subdirectory can have different genders.
In German for example ”the file” is ”die Datei”, ”the directory” is ”das Verzeichnis. A better way
would be to write out the sentences completely, as listing 3.2 demonstrates[15].
Listing 3.2: Written out sentences for better translation
D e l F i l e = "Are you sure you want to delete the file?" ;
D e l D i r = "Are you sure you want to delete the directory?" ;
Del SubD = "Are you sure you want to delete the subdirectory?" ;

Another point to mention is that sentences should be kept together in a single string. It doesn’t
make much sense to break up a string into several pieces. It is not said that those pieces appear
consecutively in the translators’ string tables. So they can be mixed up and the meaning of the
sentence could be lost. The translation of each part separately does not guarantee that the string has
its original meaning. The reason for this is that sentences often are built up differently in different
languages due to grammatical differences. Breaking up a sentence means that in some pieces there
is no object, and in another may not be a subject or a verb, for example. Translating such pieces
correctly can be very difficult.
Listing 3.3 from [15] shows an example of a sentence that has been broken up into three pieces.
Listing 3.3: English sentence broken up into three pieces
"When this box is checked, Windows NT does not"
"automatically display the user name of the last person"
"to log on in the Authentication dialog box."

The string pieces then are translated into German (see listing 3.4).
Listing 3.4: German translation of the sentence
"Wenn dieses Kontrollkästchen aktiviert ist, zeigt"
"Windows NT nicht automatisch den Namen des"
"Benutzers an, der sich zuletzt in dem Dialogfeld"
"" A u t h e n t i f i z i e r u n g " angemeldet hat."

If now this German sentence is being translated back to English, some grammatical faults will occur.
Listing 3.5 shows the result of the reverse translation.

3.2.1 String handling and ordering in source files

29

Listing 3.5: Sentence translated back into English
"When this controlbox checked is, -plays"
"Windows NT not automatically the name of"
"the user -dis, who him/herself last in the dialog box"
"" A u t h e n t i c a t i o n " logged has."

If translations are made by automatic translation tools, it is strongly recommended to keep sentences
in single strings. This also saves money, because translators, whether human or software-driven, are
more precise and productive.

3.2.1.2

Use of unique names for variables

If variables in strings are necessary, they should be unique in their name. Otherwise, if they are
used in different ways, translators would not understand the meaning of the whole sentence. Wrong
translations and grammatical faults would be the result. To give an example, sometimes it is useful
to use a placeholder in a sentence which is repeated for usage in different contexts:
Del_File = "Are you sure you want to delete the %s";
This placeholder refers to a function that replaces the placeholder with the corresponding word.
This word could be ”file”, ”directory” or ”subdirectory”.
A good documentation about the used variables and their values is also useful for the translators.
With that help they can easily translate them into the correct language using correct syntax and
grammar.
Now that the word order can vary from language to language, it would not be appropriate using the
same placeholder for different functions:
Memory_Error = "Not enough memory to %s the file %s.";
The first \%s is a function like open, close or save. The second \%s refers to the name of the file. If
this sentence is now translated into other languages, the placeholders may be mixed up. A possible
output would be (translated back into English):
"Not enough memory to filename1 the file open."
A better way for this example would be:
Memory_Error = "Not enough memory to %f the file %n.";

3.2.1 String handling and ordering in source files
3.2.1.3

30

String Buffer Sizes and Element Resizing

String sizes vary from language to language. A consequence is that a string that has been translated
in another language is suddenly much longer and needs more characters than the original one.
Especially when translating from English to another European language, string sizes increase in
most cases. As an example the English sentence[15]
"Press Ctrl+Alt+Del to restart."
has to be translated into German. The result would be
"Drücken Sie Strg+Alt+Entf, um den Computer neu zu
starten."
System crashes or severe failures due to a string buffer overflow can be caused if the string buffer
size is not large enough to hold all characters of the translated string.
To avoid these kinds of faults developers should communicate with translators to make sure how
much room such translations need. The other way would be to tell the translators the maximum
available string buffer size for a translation. Then the translators will have to find an appropriate
translation that is short enough. Alternative solutions would be to use the maximum buffer size if
practicable, or using dynamic buffer sizes.
The problem with the increasing string sizes also affects the user interface, because strings have to
be displayed e.g. in windows, message boxes or on buttons. Therefore it is required to resize these
user interface elements to give the string its necessary space. A button, which is labeled "Cancel"
can be too small to carry the German Translation "Abbrechen".
Microsoft recommends in[15] ”to leave about 30 percent additional room for text expansion”. Exceptions should be made if ”a string or a button contains less than 10 characters”.
A good example to represent the exception is the typical ”OK” button. Once translated into Spanish
the two characters expand to seven characters. The original small ”OK”-button would never be able
to hold all these characters. Figure 3.1 depicts these two buttons and their differences in size.

3.2.2 Sorting Algorithms

31

Figure 3.1: Comparison of the English and Spanish ”OK”-buttons[15]

3.2.2

Sorting Algorithms

In the English language sorting functions usually don’t cause any problems. Corresponding mechanisms are created in assumption that an alphabet is used and all words in a sentence are separated
by a space character. But Eastern Asian languages use symbols and characters. Accordingly implementing sorting functionalities causes more difficulties. Also there exist different sorting criteria
from country to country. Some European languages differ in handling special characters. For example in the Spanish language the ”ch” is handled as a single entity and is sorted after the ”c” but
before the ”d”. This causes the country names Canada, China and Czech Republic being sorted in
the order Canada, Czech Republic and China[30]. Besides the sorting algorithms, search algorithms
are also affected by these difficulties.

3.3

Unicode

A lot of Asian languages don’t use an alphabetic system. They illustrate words with pictorial characters (e.g. glyphs and ideograms). Problems can occur, because some applications still only support
languages with single-byte characters. But Asian languages need at least double-byte characters
or even more. For that reason software products, which are translated into Japanese, Chinese or
Korean, should support the double-byte system or should be written in Unicode.

3.3.1

What is Unicode?

Unicode is an international standard that defines a digital code for every character, glyph and
ideogram of all known languages worldwide. Unicode (version 1.0 was released in 1991) is platform independent and is already integrated into all modern programming languages such as Java
and C#. Those programming languages which are still in heavy use but which have existed longer

3.3.2 Why should Unicode be used?

32

than the Unicode standard (e.g. C or C++) support Unicode through libraries that are available for
free.
”The Unicode Standard is the universal character encoding scheme for written characters and
text.”[3] With Unicode multilingual text is encoded in a standardized way, so that text data can
be exchanged internationally. This is the basis for global software. The World Wide Web already
uses Unicode in many languages and Unicode is required in all new Internet protocols. It is the
default encoding of HTML and XML. The main goal of Unicode is to enable the creation of one
software system that functions all over the world.

3.3.2

Why should Unicode be used?

Combining all existing letters and characters of all languages in the world, there are far more characters than an 8-bit character set, like ISO 8859-13 , can hold. Also new characters are being invented
continuously, like for example the European currency symbol C. So there are some problems which
have to be faced[7]:
• Characters from different character sets cannot be stored in the same document. It’s quite
possible to do this in word processing applications (e.g. LaTeX), but it’s not possible in plain
text.
• If there is no automatic recognition of the character set of documents, users have to intervene
manually when they want to display their documents with an application (e.g. web browser).
That means, if unreadable symbols or letters are displayed on the screen, users have to install a
language package for a certain language using a certain character set to support and correctly
display this special character set of that language. If, for example, web sites use Unicode (e.g.
http://www.wikipedia.org), there should be no problems in displaying different languages
even without installing any language packages.
• If new symbols are invented, there is often no more room for them left in an existing character
set. Then new character sets are being issued, where old symbols, which are not used any
3 ISO 8859 or ISO/IEC 8859 is a standards with actually 15 different parts (from ISO 8859-1 to ISO 8859-15) used

in information technology for character encoding using 8 bit. These standards are for encoding most of the special
characters of certain languages. ISO 8859-1 is the standard for Western Europe which tries to cover all special characters
of all Western European languages.

3.3.3 Unicode Encodings

33

longer, are being replaced by new symbols. This happened for example with ISO 8859-1,
which does not include the Euro symbol C. Therefore ISO 8859-15 has been issued, where
old currency symbols were replaced by the Euro symbol. Besides that, both character sets are
quite identical. But if users adopt this standard, they have different documents in different
character sets. And this doesn’t make things simpler.
These problems can be solved by adopting a world-wide usable system for encoding character sets.
And this system is Unicode.

3.3.3

Unicode Encodings

Before implementing Unicode in one’s own applications, there is only one technical problem that
has to be considered:
”How to transport Unicode characters using the 8-bit bytes? 8-bit units are the smallest addressing
units of most computers and also the unit used by TCP/IP network connections.”[7] Because of the
fact that computer development started in Europe and the U.S., where 96 characters were sufficient
for a long time, it is an ”accident of history” that 1 byte is used to represent 1 character.
There are basically four ways to encode Unicode characters in bytes (list taken from[7]:
• UTF-8:4 128 characters are encoded using 1 byte (the ASCII characters). 1920 characters
are encoded using 2 bytes (Roman, Greek, Cyrillic, Coptic, Armenian, Hebrew, Arabic characters). 63488 characters are encoded using 3 bytes (Chinese and Japanese among others).
The other 2147418112 characters (not assigned yet) can be encoded using 4, 5 or 6 bytes.
• UCS-2:5 Every character is represented as two bytes. This encoding can only represent the
first 65536 Unicode characters.
• UTF-16: This is an extension of UCS-2 which can represent 1112064 Unicode characters.
The first 65536 Unicode characters are represented as two bytes, the other ones as four bytes.
• UCS-4: Every character is represented as four bytes.
4 UTF: Acronym for ”Unicode Transformation Format”
5 UCS: Acronym for ”Universal Character Set”

3.3.4 Pitfalls of Unicode

34

Consequently these encodings require more space for certain languages and characters respectively,
compared to 8-bit encodings currently in use the most often. That means some European languages
(Greek and Cyrillic) and Far Eastern languages need more than 8-bit for character encoding. This
affects the requirement of disk storage and network download speed (assuming no form of compression is used).
With UTF-8 there is no change for US ASCII. ISO 8859-1 needs a few percent more. Chinese/Japanese/Korean need 50% more, because the actually used encodings for Far Eastern languages
already use more than one byte per character. So the increase of space usage is not that high when
using UTF-8. Greek and Cyrillic in contrast need 100% more space, because with UTF-8 they
have a 2-byte encoding, while with the ISO 8859-5 (Cyrillic) and ISO 8859-7 (Greek) character set
encodings they need only one byte per character.
With UCS-2 and UTF-16 there is no change for Chinese/Japanese/Korean, but US ASCII and ISO
8859-1 need 100% more space, also Greek and Cyrillic (but in comparison to UTF-8 there is no
change in space usage).
Using UCS-4 Chinese, Japanese and Korean use 100% more space. US ASCII, ISO 8859-1, Greek
and Cyrillic need even 300%.
Since there are some encodings which penalize U.S. and European character sets, it is unlikely that
they will have a chance of acceptance for wide-scale use. But there is UTF-8 that doesn’t penalize
them. Also many text processing programs don’t need to be changed for UTF-8 support. Most
Unicode implementations are for UTF-8.

3.3.4

Pitfalls of Unicode

Unicode is a complex standard. This is also a reason why a whole consortium is needed to maintain
the Unicode Standard. The home Page of the Unicode Consortium can be reached under [3]. It has
taken some time until it was supported by most of the programming languages and technologies.
But there are still some problems. Developers should be aware of one major problem: The issue of
input encoding and storage encoding can be hazardous. For example problems can occur when the
front-end of an application uses ISO 8859-1 for displaying but the back-end might use UTF-8. This
has one good and one bad thing. The good thing is, this back-end can still be used. The bad thing is,
the front-end has to be modified if it should work together with other Unicode-compliant software.

3.3.5 Unicode and its use in programming languages

35

Another difficulty is the fact that Unicode (UTF-8) has ”gaps”. That means there are illegal multibyte sequences which cannot be converted into a valid Unicode character. During decoding developers have to make dispositions for these cases which may slow down an application considerably.
Collating, or sorting as described in section 3.2.2 is also problematic. Unicode defines a character
set, but how characters should be sorted inside that set is not defined. There are two criteria the sort
order depends on: One is the character set itself, but also on the locale in which the character set is
being applied.
In general decoding and encoding is more complex. Even trivial tasks like e.g. determining the
length of a character string (which is in byte-oriented applications usually a simple counting of
bytes) suddenly can be a challenge.

3.3.5

Unicode and its use in programming languages

So after considering the good and bad things about Unicode, the question is: Which programming
languages support Unicode?
In fact the ”more recent programming languages that were developed after around 1993 have already
special data types for Unicode/ISO 10646-1 characters”[11]. These languages are for example
Ada95, Java, TCL, Perl, Python and C#.
So this subsection at first describes the use of Unicode in a new language like Java in subsection
3.3.5.1, and then in 3.3.5.2 how it works in C and C++. These programming languages have existed
quite a long time now, but are still very powerful.

3.3.5.1

Use of Unicode in Java-Programs

Using Unicode in Java is one of the easiest ways, because Unicode (UTF-8) support is built into the
programming language. ”Java uses Unicode as internal code for char and String”[10]. Java uses
the Locale of the running platform and converts encoding automatically for input/output. Therefore
users don’t notice anything of Unicode during use of their applications written in Java.
Developers also live in comfort with Unicode and don’t have to care about internal encoding. Character processing (e.g. character counting in a string) works well. There is also no need to be worried

3.3.5 Unicode and its use in programming languages

36

about display and input.
More technically, every char variable denotes a character of the Unicode type. Hence the
java.lang.String class ”denotes a string built up from Unicode characters”[7].
Through its windowing system AWT6 , Java is able to display any Unicode character. There are only
a few steps necessary:
1. Proper setup of Java system property ”user.language”.
2. Setup of /usr/lib/java/lib/font.properties.language font set definitions
have to be appropriate.
3. Being sure that the fonts specified in that file are installed.[7]
If a developer wants to handle specified encodings as for example MIME encoding/decoding,
”I/O can be done by specifying external encoding”[10]. This is done by checking the classes
InputStreamReader and OutputStreamReader.

It is also possible to convert ”be-

tween the internal encoding and specified encodings by String.getBytes(encoding) and
String(byte [] bytes,encoding)”[10].
For example, to open a file which is encoded in the default Locale, code as shown in listing 3.6 can
be used.
Listing 3.6: Java code example - opening a file which is in the default Locale encoding
BufferedReader read =
new B u f f e r e d R e a d e r ( new F i l e R e a d e r ( "file.txt" ) ) ;
String t e x t = read . readLine ( ) ;

If it is not said that the opened file is always in the same Locale as the running platform, the encoding
of the file has to be specified, as shown in listing 3.7.

6 Java AWT: Acronym for ”Abstract Windowing Toolkit”

3.3.5 Unicode and its use in programming languages

37

Listing 3.7: Java - Specifiying encoding of file
BufferedReader read =
new B u f f e r e d R e a d e r (
new I n p u t S t r e a m R e a d e r ( new F i l e I n p u t S t r e a m ( "file.txt" ) ,
"ISO-8859-1" ) ) ;
String t e x t = read . readLine ( ) ;

Sometimes it is necessary that programs need to encode or decode data directly. Both of these
functionalities are provided by the class java.lang.String. Example 3.8, taken from [21],
shows a method to convert data from one encoding to another.
Listing 3.8: Java - Converting from one encoding to another
public s t a t i c byte [ ] convert ( byte [ ] data , S t r i n g srcEncoding ,
String targetEncoding ) {
/ / F i r s t , decode t h e data using t h e source encoding .
/ / The S t r i n g c o n s t r u c t o r d o e s t h i s ( J a v a d o c ) .
S t r i n g s t r = new S t r i n g ( d a t a , s r c E n c o d i n g ) ;
/ / Next , e n c o d e t h e d a t a u s i n g t h e t a r g e t e n c o d i n g .
/ / The S t r i n g . g e t B y t e s ( ) method d o e s t h i s .
byte [ ] r e s u l t = s t r . getBytes ( targetEncoding ) ;
return r e s u l t ;
}

The javac compiler is also capable of reading Java source files using the encoding of the programmer’s choice. That means it is possible to type non-ASCII characters directly into the source code.
It doesn’t matter if these characters are only in a string or even in a variable name. The following
code example 3.9 from [21] uses German characters.

3.3.5 Unicode and its use in programming languages

38

Listing 3.9: Java - using non-ASCII characters in source code
public class Hallo {
p u b l i c s t a t i c v o i d main ( S t r i n g [ ] a r g s ) {
S t r i n g Gruß = "Hallo, verrückte Welt!" ;
System . o u t . p r i n t l n ( Gruß ) ;
}
}

Nevertheless it is important to tell the compiler which encoding it should use. Normally it
uses the default encoding of the running platform. But if this platform does not have the German encoding as the default, javac may generate a lot of syntax errors. With the option
-encoding the encoding can be specified. To compile the above code the command would look
like javac -encoding Latin-1 Hallo.java.
However it can happen that some characters are still not displayed correctly, because Java produces
its output in Latin-1. And if the computer where such code is compiled does not understand Latin-1,
such errors can occur. A solution is to use a Unicode-capable GUI. Swing is very suitable for client
applications and works well with Unicode strings. Also Sun’s JDK7 is shipped with some special
Unicode fonts. These fonts ensure that international text has a consistent look[25]. Java servlets
and JSPs8 can rely on the client’s browser and its capabilities displaying Unicode correctly.

3.3.5.2

Use of Unicode in C/C++ Programs

Using Unicode in C or C++ is not as trivial as in Java. C has existed longer than the Unicode
standard, though C-libraries have been changed to support Unicode.
There are several ways to modify software for UTF-8 support. One is keeping data in its UTF-8 form
everywhere. This practice has the advantage that only a few software modifications on applications
are necessary. To give an example, a lot of typical Unix/Linux programs (e.g. cat and echo) don’t
have to be modified at all. Those commands just handle byte streams and do not process them. They
only recognize ASCII characters and control codes (e.g. ’\n’) which do not change under UTF-8.
So it doesn’t matter to them if the output is UTF-8 or ISO 8859-1. The terminal emulator is doing
7 JDK: Java Development Kit
8 JSP: Java Server Pages

3.3.5 Unicode and its use in programming languages

39

the job of UTF-8 encoding and decoding for these applications. Some more ways of modifying
software are explained in [11].
The support for Unicode and UTF-8 in the programming language C is mainly done by the GNU9
glibc 2.2 library. This library has the type wchar_t. This type is intended to be used only for
32-bit ISO 1064610 values. It is not dependent on the currently used locale. With the definition of
the macro __STDC_ISO_10646__, as required by ISO C99, applications know what to do. Glibc
2.2 and higher versions do have a full implementation of the ISO C multi-byte conversion functions
(e.g. mbsrtowcs(), wcsrtombs()). These functions are needed to convert between wchar_t
and any multi-byte encoding which is locale-dependent (e.g. UTF-8, ISO 8859-1, etc).
The following code sample3.10 taken from [11] shows what to do to get different outputs of character set encodings:
Listing 3.10: C code example - modifying locale settings
# i n c l u d e < s t d i o . h>
# i n c l u d e < l o c a l e . h>
i n t main ( )
{
i f ( ! s e t l o c a l e ( LC CTYPE , "" ) ) {
f p r i n t f ( s t d e r r , "Can’t set the specified locale!" ,
"Check LANG, LC_CTYPE, LC_ALL.\n" ) ;
return 1;
}
p r i n t f ( "%ls\n" , L"Schöne Grüße" ) ;
return 0;
}

If this program has been called with the locale setting LANG=de_DE, then the output will be in ISO
8859-1. If it is called with LANG=de_DE.UTF-8, then the output will be in UTF-8. The \%ls
format specifier in printf calls the function wcsrtombs mentioned in the paragraph before. This
function converts the wide character argument string into the locale-dependent multi-byte encoding.
9 GNU: ”Gnu is Not Unix” - The GNU project, invented by Richard Stallman, has its goal in developing a completely

free operating system which is Unix-compatible.
10 The international standard ISO 10646 defines the Universal Character Set (UCS).

3.3.5 Unicode and its use in programming languages

40

Fortunately, many of C’s string functions are independent of any locales. They just look at zeroterminated byte sequences.
String functions are, for example:
strcpy, strncpy, strcat, strncat, strcmp, strncmp, strdup, strchr, strrchr,
strcspn, strspn, strpbrk, strstr and strtok
Nevertheless the locale-dependent C functions, like strcoll and strxfrm are also useful and
work quite well if they are used in UTF-8 locales.
Some of the locale-independent functions (like strcpy) can be used for single-byte (ISO 8859-1)
as well as for multi-byte (UTF-8) encoded character sets. This is because these string functions
don’t need information about how many bytes long a character is. But others (e.g. strchr)
”depend on one character being encoded in a single char value”[11]. This fact makes them less
useful for UTF-8.
More information about using Unicode, especially in the Microsoft MSDN11 can be read in section
4.2.

11 MSDN: Microsoft Developer Network

Chapter 4

Localization by Example - Microsoft
Windows
This chapter gives a more detailed view of how software localization is done. As an example the
Microsoft Windows platform has been chosen to demonstrate localization of applications.

4.1

Preliminaries under Microsoft Windows

For localization under Microsoft Windows it should be known at an early stage of the development
process which target languages the software application should support, because localization effort is not the same for all languages. In increasing order of effort required, the languages are as
follows[24]:
• Western European fonts,
• Fonts with other alphabets, such as Cyrillic or Greek,
• Fonts with another writing direction, such as Arab or Hebrew,
• Asian fonts with their thousands of unique symbols.

41

4.2 Microsoft and Unicode

42

If a software application is intended to support only Western European fonts, then the data type
char will be sufficient for storing text information. All letters of Western European languages
fit in one character set. For example English, German, French and Spanish people are able to
exchange text without any misunderstandings. But differences in sorting characters and letters have
to be considered. They can be different between Locales as they have special sorting algorithms to
properly treat special characters used in the language the Locale is for. That means the same data
can be differently sorted in different Locales. Section 3.2.2 provides a short discussion about sorting
algorithms.
If another language is added to the existing ones that uses its own alphabet (e.g. the Greek language)
things get more complicated. Both fonts use different character sets. The allocation to byte values
or code points to letters of the alphabet is done by so called code pages.
As long as the software application does not have to exchange data between these two user groups
(e.g. the English and the Greek users) it can still use a single-byte character set. But if there is data
exchange between users that use different character sets, it is recommended to change the character
set to Unicode. But this change is very complicated, if the software already exists. And even during
development of new software the developers have to be careful to always use the right operating
system functions.
A negative aspect of using Unicode under Windows is that Unicode is only supported by the newer
Windows versions. At least Windows NT is needed. Windows 9x does not support all necessary
operating system commands. Therefore Windows software which uses Unicode cannot be used with
every Windows platform.
If fonts of a language are used that are written and/or read from right to left, dialog fields and buttons
have to be mirrored vertically.
If the software application has to support Asian fonts, it is best to change to Unicode. All modern
windows versions (like NT, 2000, XP and Server 2003) are supporting Unicode.

4.2

Microsoft and Unicode

As mentioned in 4.1, Windows has supported Unicode since Version NT 4.0. Even though many
character-processing tasks on the user interface are done with ASCII and ANSI, the internal pro-

4.2.1 Variable Types

43

cessing is already done completely with Unicode. Developing one’s own software with Unicode
support under Visual C++ is quite easy. To tell the compiler to support Unicode, only one special
line is used in the first header file: #define _UNICODE.

4.2.1

Variable Types

As described in 3.3.5.2 wchar_t is the 2-byte equivalent to char. There are a few other variable
types, but those usually are barely used. The header file ”tchar.h” consists of a type _TCHAR
which automatically is a define for wchar_t or char, depending on whether _UNICODE has
been defined or not.
To display a character string, usually a syntax like in listing 4.1 is being used.
Listing 4.1: ASCII version of type char
char m y s t r i n g [ ] = "Hello" ;

The Unicode equivalent would look like the one in listing 4.2.
Listing 4.2: Unicode version of type char
w c h a r t m y s t r i n g [ ] = "Hello" ;

But unfortunately constant character strings are still ordinarily 1-byte arrays for the compiler. To
”explain” to the compiler that this example is a Unicode character string, the macro ”L” has to be
used. This is shown in listing 4.3.
Listing 4.3: Using macro ”L” in Unicode version of type char
w c h a r t m y s t r i n g [ ] = L"Hello" ;

This works the same with single characters:
mychar[1] = L’S’;
Microsoft has simplified the programming effort if developers want to switch between ASCII and
Unicode. All character strings or single characters, which are marked with "_T", are either ASCII
or Unicode depending on the declaration of _UNICODE. If _UNICODE is not defined, "_T" is
ignored. If it is defined, "_T" is converted to "_L". That means programmers can easily switch

4.2.2 System Functions

44

between ASCII and Unicode if they use the type _TCHAR instead of char or wchar_t and placing
a "_T" in front of each constant string character or constant single character. Then the only thing
to do is defining _UNICODE for Unicode or not defining for ASCII. A "_T" marked string would
look like
_TCHAR *str = _T("A string");

4.2.2

System Functions

Almost every function of the Microsoft Windows-API1 exists in two versions. One is a Unicodeversion and one is an ASCII-version.
As an example the function MessageBox() is being explained[13]:
This function actually doesn’t exist. It is only a definition which is, depending on the definition of
_UNICODE, a mapping on the function
MessageBoxA() or on MessageBoxW().
The MessageBoxA() function is the ASCII or ANSI version (identified by the ’A’ in the function
name), and the MessageBoxW() is the Unicode version, where the ’W’ stands for ”wide char”.
Developers don’t need to care about these mappings. They use the official name MessageBox() as
normal.

4.2.3

Using Standard C Libraries under Microsoft Windows

Under Visual C++ Microsoft has simplified the use of unicode quite a lot. Applications can easily
be developed to support both, ASCII and Unicode. Legitimate questions would now be: What
happened with the functions of the standard C library? Is the handling of those functions as easy
as those of the Windows-API? Is there a mapping, too? Finally the standard C functions weren’t
defined by Microsoft and they have existed longer now than the Unicode standard.
In fact, every function of the standard C library exists in two versions, a unicode-capable version and
a ”normal” version processing ASCII, as well. But this time there is no define-switch that would
make it possible to use one name for both functions as explained in 4.2.2. For example ASCII
version of the printf function is shown in listing 4.4 and listing 4.5 shows the Unicode-version:
1 API: Application Programming Interface

4.3 Mirroring for Right-to-Left Languages

45

Listing 4.4: ASCII version of ’printf’ function
i n t p r i n t f ( c o n s t char * f o r m a t [ , a r g u m e n t ] . . .

);

Listing 4.5: Unicode version of ’printf’ function
i n t w p r i n t f ( const wchar t * format [ , argument ] . . .

);

This circumstance makes it a bit complicated for developers programming in Unicode when they
want to use functions out of the standard C library. They have to have a look at the documentation
of the unicode-version, although they probably know the ASCII-version very well. But Microsoft
lists both versions in their MSDN documentation[17] which makes it a bit more comfortable and
time-saving.
A short remark on Microsoft’s MFCs2 : They operate exclusively with CString wherever character
strings may occur. They also use defines as explained in 4.2.1.

4.3

Mirroring for Right-to-Left Languages

Right-to-Left (RTL) languages are those which are read from right to left direction. These are
mainly Arabic and Hebrew. But besides the text alignment and reading direction, there is also the
user interface elements layout which should follow the direction of going from right to left. To solve
this issue, mirroring technology was introduced. This should give an optimal right-to-left look &
feel to the user interface.
Since Windows 2000, all Windows versions, independent of their language version, are mirroring
aware. Also a mirrored application can be developed and executed on all these Windows Platforms.
Figure 4.1 displays an Arabic Windows XP desktop. It’s easy to see that all user interface elements,
including ”Start” button and tree-view controls are mirrored.

The technique behind mirroring is just a coordinate transformation[16]:
• ”Origin (0,0) is in the upper RIGHT corner of a window”
2 Microsoft Foundation Classes

4.3 Mirroring for Right-to-Left Languages

46

Figure 4.1: Arabic Windows XP desktop[16]
• ”X scale factor = -1 (i.e. x values increase from right to left)”
Figure 4.2 shows how a typical coordinate transformation from Left-to-Right (LTR) to Right-to-Left
(RTL) is done.
It is recommended by [16] to ”replace the concepts of left and right with the concepts of near and
far”. This should avoid confusion around coordinates.
Modifications have been made to system components like the GDI3 and user modules to be able
to enable and disable mirroring with almost no additional code changes. So the effort of rewriting
applications to support mirroring has been minimized. But how about owner-drawn control buttons
and bitmaps? They have to be mirrored, too. So there are two different approaches to allow turning
on and off mirroring on owner-drawn graphics[16].
3 Microsoft Windows Graphics Device Interface - Enables applications to use graphics and formatted text on both the
video display and the printer.

4.3.1 Mirroring in Resources

47

Figure 4.2: Coordinate transformation[16]
1. Compiled application approach: This is the approach to be used when full access to the
applications source code is given.
2. Non-compiled application approach: This is the approach to be used when no access to any
of the code is given. This is usually done with some resource localization tool (see chapter
5).
These two approaches will not be discussed in this research paper as they require deeper knowledge
in Windows Programming and would be too theoretical and complex. For more information see the
Microsoft ”Global Development and Computing Portal”[15].
In general mirroring in Win32 applications can be enabled on two ways:
• Mirroring in Resources
• Mirroring in Code

4.3.1

Mirroring in Resources

Mirroring in Resources means the ability of mirroring one’s own applications by simply editing
one’s own resources. This is useful in the case where old components have to be mirrored for which
the source is not available, or the applications are first being tested to see if the mirroring looks fine.
Applications can be mirrored by ”adding two left-to-right marks (LRMs)-represented by Unicode

4.3.2 Mirroring in Code

48

code point U+200E-in front of the FileDescription value of the version stamping”[16]. Figure
4.3 shows a mirrored notepad.exe from Windows that has been mirrored with this technique.

Figure 4.3: Notepad.exe file that has been mirrored by adding two LRMs[16]
If a window is mirrored, all windows and controls within this window are mirrored, too. This can
cause some problems, if only a certain part inside of a window should have been mirrored. Such
problems are usually only resolvable by doing code fixes. To gain more flexibility, the second way
- mirroring in code - is used instead.

4.3.2

Mirroring in Code

Mirroring in code gives the developers more freedom and flexibility in deciding which parts of their
applications should be mirrored. Beside this it’s the only way to gain full control over mirroring per
process, per window, for dialog resources, or per device context. Following is a short description
about what those mirroring approaches mean.

4.3.2.1

Mirroring per Process

Mirroring on a per process basis means that only newly created windows will be mirrored after this
layout has been activated. All others (the parent windows), which existed before activation, will not
be affected by mirroring.

4.3.2 Mirroring in Code
4.3.2.2

49

Mirroring per Window

Mirroring per window is an alternative approach to Mirroring per process. Its use is recommended
when developers want to activate mirroring at a lower level than the process-level. The benefit in
this approach is that not all of the newly created windows are automatically mirrored, but developers
can decide for each window if it should be mirrored or not.
An example when this method is recommended is if there are windows that ”host or import external
controls, such as Microsoft ActiveX, Java applets or Component Object Model (COM) objects”[16].
The problem is that these controls are limited in manipulation of their behavior and it’s difficult to
give them mirroring requirements.

4.3.2.3

Mirroring for Dialog Resources

Dialog boxes are handled a bit differently than windows by Microsoft Visual Studio. So there is an
extra activation needed for mirroring dialog boxes.
If developers want to switch between mirrored and nonmirrored dialog resources during runtime,
they need a set mirrored dialog resources as well as a nonmirrored. Mirroring style of dialog resources are set in the resource editor of Microsoft Visual Studio by the Dialog Properties property
sheet shown in figure 4.4.

Figure 4.4: Setting the mirroring style of the dialog resources within the resource editor of Visual
Studio 6[16]

4.3.3 Handling Direction-Sensitive Graphics
4.3.2.4

50

Mirroring per Device Context

All mirroring technologies described in 4.3.2.1, 4.3.2.2 and 4.3.2.3 affect all objects (like for example bitmaps and icons) in a standard window. But there has to be a way to exclude graphics objects
from mirroring, if for example they include text or images (such as brands and logos of companies)
which should not be mirrored. Mirroring per device context allows to define which objects within
such a window should be mirrored and which not.

4.3.3

Handling Direction-Sensitive Graphics

During mirroring user interface objects, developers should be careful with direction-sensitive graphics. Direction-sensitive means, that these graphics get a different meaning once they are mirrored.
For example the arrow of a browser’s ”back” button usually points to the left in a left-to-right layout. This represents the concept of ”going back” to the previous page. On the other hand an arrow
pointing to the right means ”going forward” to the next page. so what happens if the entire browser
window has been mirrored. Figure 4.5 shows that the meaning of the buttons and arrows respectively
are interchanged.

Figure 4.5: Example of a direction-sensitive arrow that changes meaning when mirrored[16]
But as described in 4.3.2.4 there are also graphics containing text (e.g. names of companies/institutions) or logos which should not be mirrored.

4.3.3 Handling Direction-Sensitive Graphics

51

Depending on the particular situation, there are four methods for solving such cases:[16]
1. During rendering direction-sensitive graphics the right-to-left layout of the device context
can be shut off temporarily. Once mirroring is completed, it can be turned on again. The
drawback of this method is that sometimes developers have no ”access to the device context
where the graphics will be rendered”[16]. For example if an icon or bitmap handle is being
passed to a third-party DLL4 which displays the image.
2. This method picks up the idea already used in Mirroring for Dialog Resources in section
4.3.2.3 - using two different sets of graphics in the resources. One set is used for the left-toright oriented drawing destination, and the other set for the right-to-left. Mostly the left-toright graphics are the original versions. So the second set is just a copy of the first set, where
modifications are only made to those graphics which need to be mirrored for proper rightto-left display. So the developers can choose between the original non-mirrored graphics for
left-to-right use and their second set made only for right-to-left use (including graphics which
are not mirrored due to their meaning or design). If such a mirrored set contains a lot of
direction-sensitive graphics which have not been mirrored, this method might not be the best
one, because there are a lot of duplicates in comparison to the left-to-right set. This increases
the demands on the developers’ resources.
3. The third method uses a separate set of graphics elements based on the target localized languages. So a localization team can mirror these graphics elements using a resource editor
(e.g. image editing software).
4. If developers don’t have direct access to the graphics rendering device context, a final method
is ”to create a mirrored copy of the resource”[16]. Finally this mirrored copy is being passed
instead of the non-mirrored originals.
Overall this chapter gave an overview of the special techniques needed to localize software under
Microsoft Windows. These techniques can vary depending on the platform for which software is
developed. But all prior considerations and advice shown in chapter 2 and 3 are quite similar for all
platforms.

4 Dynamic Link Library

Chapter 5

Software Localization Tools and
Standards
There are several methods for localizing software product files. One is to edit and modify the
original resource files before starting compilation. Another method takes the contrary way: Here
the final compiled binaries of the software are localized and then saved either into the same binaries
or into a localization database.[18]
There are localization tools on the market which are capable of handling at least one of these methods. But regardless of the chosen localization method, the right choice of localization tools (or in
other words resource editor tools) hinges on how quickly and easily the localization of a software
can be made. A good localization tool has the feature of creating a localized version of the corresponding original file. Also such a tool can localize different types of files, like for example a
resource file or a compiled file.
So the question is now, what criteria should a good localization tool meet besides the ability of
translating ”the string resources within the localization tool”?
Here are some tasks such a tool should fulfill[18]:
• Change names, sizes, and styles of the user interface fonts.
• Resize, move, and hide controls as necessary.
52

5.1 Localization Tools

53

• Change the encoding of the text.
• Replace graphics and icons with localized ones.
• Modify keyboard shortcuts.
But there are also other features a good localization tool should provide. It should manage version
numbers of files and log the changes which were made during localization of those files. Furthermore, it should track exactly which resources have already been localized and in addition identify
the responsible person who did the localization. This information helps the localization manager
monitor and plan further activities of the localization team.
The localization tool should support many file formats which can potentially be localizable. Here
it is recommended not only supporting proprietary file formats (e.g. Microsoft .dll or .inf files), but
also standardized ones like those from XML and other freely usable standards.
To simplify localization of often repeated tasks, especially in translating strings, some tools maintain localization glossaries. These glossaries store already translated strings. So the localizers can
look up the translation of certain strings within the glossaries and can reuse them if someone else
has already translated the same string before. This helps maintain a consistent translation throughout all localized applications. Thinking about the next step, these glossaries with all their stored
translated strings can be used to automatically translate software. This practice will significantly
reduce localization costs. And finally, to bring this thought to an end, there should be the possibility
to add instructions on how to localize resources - another way to ease localization and reduce costs.
Now this chapter gives an overview of software localization tools and some XML standards. The
localization tools are commercial third-party products, while the XML standards are Open Source
and therefore freely available.

5.1

Localization Tools

5.1.1

Alchemy Catalyst 6.0

Alchemy CATALYST was formerly developed by the Corel Corporation, but has been bought by
the Alchemy Software Development Ltd.[1]. Catalyst is by Alchemy’s account ”the market leader

5.1.1 Alchemy Catalyst 6.0

54

in total visual localization technology”.
Alchemy CATALYST is ”a total visual localization solution for digital content files and all Microsoft
desktop, Internet and mobile applications”. The benefit is to reduce the effort to be made when
translating and updating large numbers of different file formats. CATALYST includes ”a suite of
visual editors” in WYSIWYG1 manner to make sure that translators have control over their work
permanently. There is an automatic validation of translations for each editor included ensuring that
the translated text strings are free of errors and already tested. Also included are glossary support
and spell checking features.
Furthermore, CATALYST provides a suite of Quality Assurance tools useful for validation of software and help files. The tools aid in finding errors in layout, clipped text, duplicate hotkeys, missing
parameters or controls and spell-checking. Developers get a number of tools and utilities for locating and fixing problems. Also user interfaces, help and XML based files can be updated to new
revisions. CATALYST ships with a Software Development Kit (SDK) with which Developers can
create custom editors and validators. The ”Text Parser Expert”, another feature of CATALYST,
allows the parsing of any text file and includes it in the Translation Environment.
CATALYST supports following formats[1]:
• All Microsoft Desktop Development Platforms: 9x, NT, 2000, XP, Win32, Winx64, RC,
RESX, .NET Binaries(1.x and 2.0), Visual Basic.NET
• Mobile Computing Platforms: Windows CE, Symbian, EPOC
• Java Platforms: J2EE, J2SE, J2ME
• Content Files: MS Excel, HTML (and all derivatives PHP, ASP, JSP), XHTML, XML (including derivative ASP.NET, ASP, JSP and XSL)
• Data sources: All Microsoft DB technologies, Oracle 8/9/10 and IBM DB2
But there is another interesting product from Alchemy. It is connected to CATALYST, but can also
run separately. Its called ”Alchemy Layout Manager”. This layout manager automatically creates
layouts for translated user interfaces. The benefit is that developers don’t have to manually resize
elements in application windows due to text expansion. Alchemy Layout Manager scans localized
1 WYSIWYG - What You See Is What You Get

5.1.1 Alchemy Catalyst 6.0

55

files and uses an ”advanced mathematical analysis” to determine the ”spatial relationships between
user interface elements”. These relationships are then the base for a completely new layout for
the translated application files. Alchemy Layout Manager is able to automatically adjust the user
interface. Everything like buttons and text boxes are automatically resized without destroying the
layout of the interface. Manual interaction is only required where elements could not be changed
automatically. They are flagged for manual checking.
Currently Alchemy Layout Manager is available on all Windows development platforms (16-, 32-,
64-bit, VB.NET and MS .NET 1.x and 2.0).

Figure 5.1: Screenshot of Alchemy Catalyst 6.0

5.1.2 PASSOLO 5.0

5.1.2

56

PASSOLO 5.0

PASSOLO (PASs SOftware LOcalizer) is a product of the German ”PASS Engineering GmbH[22]”.
It is actually available in version 5, but version 6 has been presented to the public recently.
Software localization with PASSOLO can be performed without access to the source code and can
be started during development phase, even the final version of the software is not finished yet.
PASSOLO is able to handle various file formats including Windows 32- and 16-bit binaries, as well
as binary files developed by Microsoft Visual BASIC and Windows resource files (.rc files). Also
it supports any text based formats and includes a powerful XML parser. Several Add-Ins are available to provide additional support for software development environment, such as Microsoft .NET,
Borland Delphi and C++ Builder. An add-on for all Java platforms is also available supporting,
for example, compiled (.class) files and compressed Jar-archives. PASSOLO also includes a Visual XLIFF component. This component is a macro-based parser processing XLIFF (see section
5.2.2 for a brief description of XLIFF) files according to the XLIFF specification 1.1. Furthermore
it supports the XLIFF profiles for Windows Resources. This specification describes how standard
Windows resources are mapped in XLIFF. Accordingly built up XLIFF files can be edited with
PASSOLO.
Extracted text strings can be translated into a variety of languages, including Asian languages (with
Unicode) and right-to-left script languages such as Hebrew and Arabic. For the problem of oversized
character strings as discussed in section 3.2.1.3 there is a WYSIWYG editor for dialogs, menus,
graphics (bitmaps and icons) and cursors that visualizes the user interface during translation. So it
is immediately visible if any translation strings would not fit in their designated window or message
box.
PASSOLO features an integrated ”Translation Memory Technology” which allows the reuse of text
from existing translations even from programs not localized by PASSOLO. They can be used for
an automatic pre-translation of a new project. The ”Fuzzy Matching Technology” is able to search
for similar text as well as exact translation matchings. PASSOLO is able to exchange data directly
with all major Translation Memory systems and supports all common data exchange formats such
as TMX (see section 5.2.1).
Spelling errors can be checked and typical mistakes made during localization are detected or avoided
automatically. These can be missing translations, incorrect allocation of shortcuts and access keys

5.1.2 PASSOLO 5.0

57

and truncated or overlapping text.
New features of version 6 include, among other things:
• multi-user support for projects and glossaries
• Cascading parsers for localizing of embedded resources
• Secure editing environment for strings by protecting embedded tags for different parsers
(HTML, .NET, Java)
• Fuzzy matches for automatic translation
• XML reporting with XSLT formating

Figure 5.2: Screenshot of PASSOLO 5.0

5.2 Open Source Standards for Localization

5.2

Open Source Standards for Localization

5.2.1

TMX - Translation Memory eXchange

58

”TMX2 is the vendor-neutral open XML standard for the exchange of Translation Memory (TM)
data created by Computer Aided Translation (CAT) and localization tools. The purpose of TMX
is to allow easier exchange of translation memory data between tools and/or translation vendors
with little or no loss of critical data during the process. In existence since 1998, TMX is a certifiable standard format. TMX is developed and maintained by OSCAR3 , a LISA4 Special Interest
Group.”[27]
”TMX provides a standard XML format for the representation of Translation Memory (TM) data.
According to research conducted by OSCAR, Translation Memory assets increasingly represent
a strategic corporate asset, worth, in some cases, millions of dollars, and supporting hundreds of
millions of dollars of international business. TMX provides a way to protect these assets against
market and technology changes since TMX keeps users from being locked into a particular CAT
tool.”

5.2.1.1

Overview of TMX

This section gives only a rough overview of the structure of TMX. It is not the intention of this thesis
to explain TMX in detail. Interested Readers can find more information about the specifications of
TMX under [29]. The definition of the TMX DTD5 can be found under [28].
TMX is defined in two parts:
1. ”A specification of the format of the container (the higher-level elements that provide information about the file as a whole and about entries). In TMX, an entry consisting of aligned
segments of text in two or more languages is called a Translation Unit.”
2 TMX: Translation Memory eXchange
3 OSCAR: Open Standards for Container/Content Allowing Re-use
4 LISA: Localization Industry Standards Association
5 DTD: Document Type definition

5.2.2 XLIFF - XML Localization Interchange File Format

59

2. ”A specification of a low-level meta-markup format for the content of a segment of
translation-memory text.
Also TMX offers two levels of implementation:
• Level 1 is a plain text support for the container only without Content Markup. ”This level
is enough when the data do not have inline codes, for example software messages. It is not
sufficient for documentation-type formats.”[29]
• ”Level 2 Contains also Content Markup and allows therefore a better reuse of data. But
Translation Memory Systems use different algorithms for segmenting the data to be translated. That makes an efficient reuse even with Level 2 impossible. Therefore a new standard
is being developed supporting the possibility of exchanging the segmentation rules.

5.2.2

XLIFF - XML Localization Interchange File Format

XLIFF is an XML-based format that allows translators to concentrate on the text to be translated.
To work with XLIFF localizers have to write converters for their source file formats. With those
they can manipulate XLIFF files. The benefit is that they don’t have to worry about the original file
format. New tools dealing with XLIFF can always be written. This makes localization engineering
much easier.
To support a full localization process, XLIFF supports following elements:
• Tags and attributes for review comments.
• The translation status of individual strings.
• Metrics (e.g. word counts) of the source sentences.
The main goals of the XLIFF format are[4]:
• Separating localizable text from formatting.
• Enabling multiple tools to work on source strings and adding information to the data about
the string.
• Storing information which is helpful in supporting a localization process.

5.2.2 XLIFF - XML Localization Interchange File Format

60

Finally this chapter showed that localizing software is a serious issue for which an increasing number of powerful tools are available. The process of localizing software gets less time-consuming.
And in the variety of localization tools the customers can choose the one that fits best to their localization requirements. The progress in creating XML standards shows also that there is a big interest
of the localization community in creating common interfaces for localization that are being used
more and more by manufacturers of localization software.

Chapter 6

Outlook
Internationalizing and localizing software are processes that have not changed much in the last
decade. This is recognizable especially when looking through the bibliography. A lot of references
are from the 1990’s, and a lot of the newer sources have references to those older ones.
A reason for this is that software internationalization is still a process that takes place ”deep” in
the source code. Especially smaller companies who produce software for a smaller market will
still have the whole job of internationalizing their software on their own. It is difficult to provide
automation for something that has to be built by hand. There exist some very useful libraries for
programming internationalized software under Microsoft Windows and under UNIX/Linux. But
still there is no automatic way to develop internationalized software.
The ongoing development in localization tools looks much better in comparison to internationalizing
software. For the localization process there are some really good and powerful commercial software
products on the market. However, their strength is only in translating software and user interfaces
respectively or adjusting locales. Changing cultural issues is still not easy to handle automatically.
There is no automatic technique that designs appropriate icons and buttons for each culture. This is
an issue where human translators or localizers have to have a closer look at each graphic in the user
interface and have the right feeling about culturally sensitive pictures and gestures. But fortunately
those tools provide an exchange mechanism. With that mechanism a pool of icons and buttons for
each language or culture can be maintained and exchanged according to requirements.

61

CHAPTER 6. OUTLOOK

62

For future internationalization projects, software development platforms (like Microsoft Visual Studio, Borland J-Builder or Sun Microsystem’s Eclipse platform) should provide an automatic and
standardized internationalization feature. That means that the development platforms distinguish
automatically between functionality in source code and localizable resources and arrange them in
different files. Those files should always be the same, independent of the developer platform. The
developers do not need to take care of this data separating process. Once there is a standard, everybody will know where he or she finds the appropriate data. Those standardized files then help in
localizing software, because all resources to be localized are always to be found at the same place.
The next step would be to provide a global ”localization framework”. This framework could be a
basis for software applications which will provide interfaces for several languages and replaceable
items (like graphics, buttons, etc.). These interfaces would help to facilitate the localization process.
This would be the place where all those powerful localization tools which are actually available
would merge in the whole internationalization and localization framework.
The final step would be to provide a resource for automatic translations. For example, a database
can collect expressions and words (or even whole sentences) in several languages, which are very
common and often used in user interfaces. Such databases exist already, but each company has
to maintain its own. A global database available for everyone would help a lot in providing an
automatic translation process.
This is the vision of a complete framework starting at the beginning of software internationalization,
when the first line of code is being written. Then it is going on with localization of the written
software and finally it provides a common resource platform for future localization projects.
Actually, the localization industry is on a good path to facilitate the localization process. There are
many useful tools on the market and XML standards available for localizing software. But what is
still missing is software that helps during the internationalization process. Too many processes still
have to be done by hand.

Bibliography
[1] A LCHEMY S OFTWARE D EVELOPMENT LTD .

Alchemy Catalyst 6.0 - Total visual

Localization. http://www.alchemysoftware.ie/products/catalyst.html,
05/07/2006.
[2] B ECKMANN , T. International Software - i18n/L10n for Business Applications. http://
tom.alten.de/en/projects.xml, 12/02/2003.
[3] C ONSORTIUM , T. U. Unicode home page. http://www.unicode.org, 03/09/2006.
[4] C ORRIGAN , J., AND F OSTER , T. XLIFF: An Aid To Localization. http://developers.
sun.com/dev/gadc/technicalpublications/articles/xliff.html,
04/20/2006.
[5] DEL G ADO , E. M., AND N IELSEN , J. International User Interfaces. Wiley Computer Publishing, 1996.
[6] F ERNANDES , T. Global Interface Design - A Guide to Designing International User Interfaces. Academic Press Inc, 1995.
[7] H AIBLE , B. The Unicode HOWTO. ftp://ftp.ilog.fr/pub/Users/haible/
utf8/Unicode-HOWTO.html, 01/23/2001.
[8] H OGAN , J. M., H O -S TUART, C., AND P HAM , B. Key Challenges in Software Internationalisation. In CRPIT ’04: Proceedings of the second workshop on Australasian information
security, Data Mining and Web Intelligence, and Software Internationalisation (Darlinghurst,
Australia, 2004), Australian Computer Society, Inc., pp. 187–194.
[9] K APLAN , M. S. Internationalization with Visual Basic. Sams Publishing, 2000.
63

BIBLIOGRAPHY

64

[10] K UBOTA , T. Introduction to i18n. http://www.us.debian.org/doc/manuals/
intro-i18n/, 02/14/2003.
[11] K UHN , M. UTF-8 and Unicode FAQ for Unix/Linux. http://www.cl.cam.ac.uk/
%7Emgk25/unicode.html, 12/29/2005.
[12] L ERNER , R. M. At the forge: Unicode. Linux Journal Issue 107 (March 2003), 8.
[13] L IMA C ITY.

Unicode-Anwendungen schreiben.

http://www.lima-city.de/

tutorials.php?m=show&id=1887, 01/21/2006.
[14] L UONG , T. V., L OK , J. S., TAYLOR , D. J., AND D RISCOLL , K. Internationalization Developing Software for Global Markets. Wiley Computer Publishing, 1995.
[15] M ICROSOFT C ORPORATION.
by-Step.

Global Development Portal - Globalization Step-

http://www.microsoft.com/globaldev/getWR/steps/wrguide.

mspx, 03/04/2006.
[16] M ICROSOFT C ORPORATION. Globalization Step-by-Step - Mirroring Awareness. http:
//www.microsoft.com/globaldev/getwr/steps/WRG_mirror.mspx,
04/18/2006.
[17] M ICROSOFT C ORPORATION. MSDN Home Page. http://msdn.microsoft.com,
04/18/2006.
[18] M ICROSOFT C ORPORATION.

Globalization Step-by-Step - Localization Tools.

http://www.microsoft.com/globaldev/getwr/steps/localization/
loc_tools.mspx, 04/20/2006.
[19] N ETWORK W ORKING G ROUP. UTF-8, a transformation format of ISO 10646. http://
www.ietf.org/rfc/rfc3629.txt, 03/11/2006.
[20] OASIS. XLIFF 1.1 Specification. http://www.oasis-open.org/committees/
xliff/documents/xliff-specification.htm, 10/31/2003.
[21] O RENDORFF , J. Unicode for Programmers (draft). http://www.jorendorff.com/
articles/unicode/index.html, 03/01/2002.
[22] PASS E NGINEERING G MB H. PASSOLO - Makes Your Software ready for the Global Market.
http://www.passolo.com/, 05/07/2006.

BIBLIOGRAPHY

65

[23] P ÉREZ -Q UI ÑONES , M. A., PADILLA -FALTO , O. I., AND M C D EVITT, K. Automatic Language Translation for User Interfaces. In TAPIA ’05: Proceedings of the 2005 conference on
Diversity in computing (New York, NY, USA, 2005), ACM Press, pp. 60–63.
[24] S ACHSE , F. Flagge zeigen - Lokalisieren von Windows-Software. c’t - Magazin für Computertechnik Issue 02 (January 2001), 204–213.
[25] S UN M ICROSYSTEMS. Java technology. http://java.sun.com/, 04/17/2006.
[26] S UN T ECHNICAL P UBLICATION. READ ME FIRST! A Style Guide for the Computer Industry.
Prentice Hall PTR, 1996.
[27] T HE L OCALISATION I NDUSTRY S TANDARDS A SSOCIATION. The Localisation Industry
Standards Association. http://www.lisa.org/, 02/08/2006.
[28] T HE L OCALISATION I NDUSTRY S TANDARDS A SSOCIATION. TMX 1.4b Document Type
Definition. http://www.lisa.org/standards/tmx/tmx14.dtd, 03/08/2006.
[29] T HE L OCALISATION I NDUSTRY S TANDARDS A SSOCIATION.

TMX 1.4b Specification.

http://www.lisa.org/standards/tmx/tmx.html, 04/26/2005.
[30] T URNBULL , S. Alphabet Soup: The Internationalization of Linux, Part 1. Linux Journal Issue
59es (March 1999), 2.
[31] T URNBULL , S. Alphabet Soup: The Internationalization of Linux, Part 2. Linux Journal Issue
60es (April 1999), 30.
[32] T YKHOMYROV, O. Y. Introduction to Internationalization Programming. Linux Journal Issue
103 (November 2002), 3.
[33] W IKIPEDIA . ORG. Wikipedia.org - the free encyclopedia. http://www.wikipedia.org,
02/13/2006.
[34] Z YDRON , A. Coping with Babel: How to Localize XML - Part 1. The Globalization Insider
volume XIII, 4.2 (December, 10th 2004).

