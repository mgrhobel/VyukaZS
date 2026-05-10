---
title: "Serbian locale.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/MIT resources/TODOs/Serbian locale.doc"
date: 2010-03-11
type: DOC
---

Summary

\

We have two possible solutions:

1\. use implementation from http://klaus.e175.net/java-locale-sh

It created totally new locale (full implementation). It is created by
person with good knowledge of Serbia.

\

2\. create new \"country/region\" version of existing sr locale. Josef
did sr_QQ in his example bellow.

In such case we provide only part of implementation and rest is
inherited from already existing sr locale.

\

First solution/implementation is more complex (author created totally
new locale). See his complains here: http://klaus.e175.net/java-yu

Second solution is more simple and maintainable, but it has the risk
that in the future we will other problems in sun\'s implementation of sr
locale.

\

If we could easily as Serbian colleagues what is better solution for
them -\> please ask.

In my opinion it is slightly better to use first solution:

\- somebody from Serbia has done it already ;-)

\- we do not have to maintain it (created new plugin, \....)

\

Final decision:

Plugin gf2.i18n.locales (second solution) implmented.

\

Manual copy of files is needed:

copy gf2.i18n.locales-\<version\>-SNAPSHOT.jar from release image to
MPA_ROOT\\tools\\jdk1.6.0_05\\jre\\lib\\ext\\**gf2.i18n.locales.jar**

\

JDK update documentation updated: ^(1)^*[Documentation 4943: Necessary
adjustments when upgrading a release to a new JDK]{.underline}*

\

*[\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--]{.underline}*

*[(1) -]{.underline}*
[*[Notes:///8025680A005AD0C0/427F562B545BDE1741256850002D7AA1/24E6AB90F8D6970CC125709F004747EC]{.underline}*](notes:///8025680A005AD0C0/427F562B545BDE1741256850002D7AA1/24E6AB90F8D6970CC125709F004747EC)

\

\

\

\

**\-\-\-\-\-\-\-\-- 2.6.2009 12:32:54 by Jiri Kiml:**

\

Well I made some experiment and it looks like we are NOT able to build
it in our environment because we use default encoding (cp1252) and

utf8 is necessary. I realy do NOT want to change such settings for whole
mpa ;-(

I discuss it with Igor and we decided to use second option because of
it.

\

\

**\-\-\-\-\-\-\-\-- 2.6.2009 9:56:29 by Jiri Kiml:**

\

Discussed with Igor and decided to try to use version from Serbian guy,
but we do NOT want to create new \"sh\" locale but we would like to use

it as sr_sl instead.

\

\

**\-\-\-\-\-\-\-\-- 29.5.2009 8:43:55 by Jiri Kiml:**

\

I converted Josef\'s test to be more \"unit\" like:

\

![](Serbian%20locale_html_494da6e7.png){#Image1 align="bottom"
width="166" height="47" border="0"}

\

**\-\-\-\-\-\-\-\-- 26.5.2009 8:25:50 by Josef Hobel:**

There are two jar files for implementation DateFormatSymbolsProvider
class for Serbian Locale:

\

1\]

![](Serbian%20locale_html_8bb876ef.gif){#Image2 align="bottom"
width="91" height="47" border="0"}

This implementation is taken by http://klaus.e175.net/java-locale-sh.

It works for sh, sh_HR, sh_RS locales. For each there is completly new
implementation of all local-specific methods.

\

2\]

![](Serbian%20locale_html_209c9426.png){#Image3 align="bottom"
width="52" height="47" border="0"}

It is my implementation.

It works for sr_QQ (only for test purpose) locale. There are implemented
two methods -\> getWeekdays() and getMonths().

I created test, I check whether I get serbian months and weekdays by
calling getWeekdays() and getMonths() method. Default results are ???
characters.

Then I check if I get formatting different from default by calling
methods which I did not implement. For example: With method
getDateInstance() I formatting same date but for two different locales.
First for serbian, next time for default formatting.

I should get different formatted results:

Default fromatting 01.02.2009

Serbian formatting 01.02.2009.

\

Test instructions on HEAD_CI using Eclipse:

1\] run eclipse

2\] Put jars into
~~D:\\builds\\head_ci\\tools\\jdk1.6.0_05\\jre\\lib\\ext\\~~
MPA_ROOT\\tools\\jdk1.6.0_05\\jre\\lib\\ext\\

3\] run test SerbianSymbolsProviderTest.java

![](Serbian%20locale_html_fd87ee3d.png){#Image4 align="bottom"
width="166" height="47" border="0"}

Note:There is not need to restart eclipse after putting/remove jars into
lib/ext.

\

**\-\-\-\-\-\-\-\-- 25.5.2009 16:52:10 by Josef Hobel:**

Basic Implementation ( weekdays and months of DateFormatSymbolsProvider
done. Next objetctive - how to join SR mehtods which could not be
implemented by provider and SR method (weekdays. monts) which copuld be
implemented by provider.

\

**\-\-\-\-\-\-\-\-- 23.5.2009 23:51:57 by Josef Hobel:**

Created automatic test.

Implementation of DateFormatSymbolsProvider class in progress. I tried
to create the class on the basic of texts below, but there is not
concrete infrmation (example) how to create the new locale.

I tried to do it on the basic of klaus site. There is almost done this
problem, but I was not able to register new locale. After I get the jar
to lib/ext no change shows.

\

\

**\-\-\-\-\-\-\-\-- 23.5.2009 22:55:58 by Jiri Kiml:**

\

**Very interesting:**

http://klaus.e175.net/java-locale-sh

\

\

**\-\-\-\-\-\-\-\-- 07.05.2009 15:31:31 by Igor Böhm:**

Hello Jiri,

 

here the needed week- and month names in serbian.

There are differences in months between Serbian and Croatian.

The weekdays should be the same.

That means we can not make our "rersource hook" so that for both cases

we take the replacing of "sr" locale with "hr" (Croatian).

 

**Von:** Sasa Smiljanic \[mailto:sasa.smiljanic@medicom.co.yu\]

**Gesendet:** Donnerstag, 07. Mai 2009 15:01

**An:** Hintersteiner Roland

**Cc:** Igor Mitric

**Betreff:** Re: months in serbia

\

Hello Roland,

 

here is translation of months

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

January                                 **Januar**

February                                **Februar**

March                                    **Mart**

April                                      **April**

May                                      **Maj**

June                                      **Juni**

July                                       **Juli**

August                                  **Avgust**

September                            **Septembar**

October                                 **Oktobar**

November                              **Novembar**

December                             **Decembar**

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

 

 

translation of weekdays

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

Monday                            **Ponedeljak**

Thursday                          **Utorak**

Wednesday                      **Sreda**

Thursday                          **Četvrtak** (Č is Serbian
character)     Cetvrtak

Friday                               **Petak**

Saturday                           **Subota**

Sunday                             **Nedelja**

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

 

 

 

Until now I did not see in Skype conversation part about sendings DVDs
and

about translation of date and time.

 

You can send DVD to Igor and I will make a copy for myself.

Translation of date and time is  **Datum i Vreme.**

 

Looking forward to your reply

\

**\-\-\-\-\-\-\-\-- 7.5.2009 9:33:24 by Jiri Kiml:**

\

Do NOT forget to write automatic test for it.

\

\

**\-\-\-\-\-\-\-\-- 12.01.2009 22:40:02 by Igor Böhm:**

\

See the problem with serbian weekday/month names

^(1)^*[Todo 43133: Weekdays and Month Names in MPA, correct
Internationalization]{.underline}*

\

Java Runtime implementation of DateFormatSymbol for serbian is
\"politically correct\" and

the names are correct too, but written in cyrillic (like russian).

Based on informations of our serbian partners, in the IT is Latin
EastEurope charset widely used and not cyrillic.

The names of weekdays/month correspond to the names of Locale(\"hr\")
(croatian).

\

So implement DateFormatSymbolsProvider class for locale \"sr\" which
works exactly like \"serbian\" Java runtime

implementation, with exception of names for weekdays and months, which
should deliver the same strings as

for locale \"hr\" (croatian).

\

For studying of Locale Provider classes, see:

http://www.j2ee.me/docs/books/tutorial/i18n/locale/services.html

and

http://www.docjar.org/docs/api/java/util/spi/LocaleServiceProvider.html

\

\

\

\

\

\

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\(1\) -
[Notes:///002567BC006B84CD/790384F5DFF8BC06C1256E5C00568763/4E984F16C8CE72F1C12575200029A0D9](notes:///002567BC006B84CD/790384F5DFF8BC06C1256E5C00568763/4E984F16C8CE72F1C12575200029A0D9)
