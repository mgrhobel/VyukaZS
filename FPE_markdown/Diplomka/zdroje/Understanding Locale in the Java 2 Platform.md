---
title: "Understanding Locale in the Java 2 Platform.html"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/zdroje/Understanding Locale in the Java 2 Platform.html"
date: 2010-01-13
type: HTML
---

# Understanding Locale in the Java 2 Platform

Copyright © 2002 John O\'Conner

\
\

\
\

Language and geographic environment are two important influences on our
culture. They create the system in which we interpret other people and
events in our life. They also affect, even define, proper form for
presenting ourselves and our thoughts to others. To effectively
communicate with another person, we must consider and utilize the
culture, language, and environment of that person.

[]{#pgfId-51361}Not surprisingly, a software system should utilize the
language and geographic region of its users to be effective. Language
and region form a **locale**, which represents the target for localized
software. The Java platform uses
*[[java.util.Locale]{style="font-style: normal;"}]{style=""}* objects to
represent locales. This article will describe
*[Locale]{style="font-style: normal;"}* and its important features.
Additionally, you will learn some of the important classes that are
affected by locale.

## []{#pgfId-46348}Definition

[]{#pgfId-51180} Locales identify a specific language and geographic
region. The class libraries use
*[java.util.Locale]{style="font-style: normal;"}* identifiers to
customize how they present and format data to the user. Locales affect
user interface language, case mapping, collation (sorting), date and
time formats, and number and currency formats. Locales are critical to
many culturally and linguistically sensitive data operations .

[]{#pgfId-51119} In some computing environments, locales define a large
set of related information that is pertinent to a given language and
geographic region. For example, a locale definition for a French
speaking Canadian region might include formatting definitions for time,
date, number, and currency representations. Information about collation
and character sets might also be included. A
*[java.util.Locale]{style="font-style: normal;"}* object, however, is
different from these traditional locales. A
*[Locale]{style="font-style: normal;"}* object is not a container for
locale dependent information like number or date format strings. It is a
simple identifier that other *locale
sensitive[^1^](#sdfootnote1sym){#sdfootnote1anc .sdfootnoteanc}* objects
can use to determine their own behavior.

[]{#pgfId-51501} Locales contain only a few important members: a
language code, an optional country/region code, and an optional variant
code. These three elements provide enough information to other objects
so that they can modify their behavior for a specific linguistic or
cultural purpose. For example, a number formating object created for a
German-speaking Swiss locale will format numbers differently than it
would for a German-speaking Austrian locale. See Table 1.

[]{#pgfId-50782} Since Locale objects are little more than identifiers,
locale-sensitive classes like
*[java.text.NumberFormat]{style="font-style: normal;"}* or
*[java.text.DateFormat]{style="font-style: normal;"}* do all the work to
actually provide localized number or date formats.
*[DateFormat]{style="font-style: normal;"}*, for example, uses the
*[Locale]{style="font-style: normal;"}* object provided during its
instantiation to decide how to correctly format dates.

*Table 1 Formatted output varies by locale.*

  ----------------------------------------- -----------------------------------
  []{#pgfId-50789}Locale                    []{#pgfId-50791}Formatted Numbers
  []{#pgfId-50793}German (Austria)          []{#pgfId-50795}123.456,789
  []{#pgfId-50797}German (Germany)          []{#pgfId-50799}123.456,789
  []{#pgfId-50801}German (Switzerland)      []{#pgfId-50803}123\'456.789
  []{#pgfId-50805}English (United States)   []{#pgfId-50807}123,456.789
  ----------------------------------------- -----------------------------------

[]{#pgfId-50808} When describing or talking about locales, you can use a
text abbreviation for a convenient representation. The following
notation is quite common:

###### []{#pgfId-46222}*[\<lang code\>\[\_\<country code\>\[\_\<variant code\>\]\]]{style="font-style: normal;"}*[ ]{style="font-style: normal;"} {#lang-code_country-code_variant-code .code-frag-one-line}

[]{#pgfId-46375} This notation separates each component of a locale with
an underscore character. The *[\<lang
code\>]{style="font-style: normal;"}* represents a language. The
*[\<country code\>]{style="font-style: normal;"}* represents an optional
country or region code. Finally, *[\<variant
code\>]{style="font-style: normal;"}* represents an optional variant.
The following sections describe each of these components of a
*[Locale]{style="font-style: normal;"}* .

### []{#pgfId-39783}Language Codes

[]{#pgfId-50569} Language codes are defined by *ISO 639* , an
international standard that assigns two and three letter codes to most
languages of the world. Locale uses the two letter codes to identify
their target language. Several of these language codes are listed in
Table 2.[^2^](#sdfootnote2sym){#sdfootnote2anc .sdfootnoteanc}

[]{#pgfId-50727} Language is an important component of a
*[Locale]{style="font-style: normal;"}* because it describes the
language used by a particular group of customers. Your applications will
use this information to provide a user interface that conforms to your
customer\'s language.

*Table 2 Language code examples*

  -------------------------- ----------------------
  []{#pgfId-50738}Language   []{#pgfId-50740}Code
  []{#pgfId-50742}Arabic     []{#pgfId-50744}*ar*
  []{#pgfId-50895}German     []{#pgfId-50897}*de*
  []{#pgfId-50746}English    []{#pgfId-50748}*en*
  []{#pgfId-50750}Spanish    []{#pgfId-50752}*es*
  []{#pgfId-50754}Japanese   []{#pgfId-50756}*ja*
  []{#pgfId-50758}Hebrew     []{#pgfId-50760}*iw*
  -------------------------- ----------------------

[]{#pgfId-40604} Of course, language doesn\'t paint the entire picture
of a locale. For example, even though you may use
*[de]{style="font-style: normal;"}* as the locale language,
*[de]{style="font-style: normal;"}* alone doesn\'t tell you anything
about where German is spoken. Several countries use German as an
official first or even second
language[^3^](#sdfootnote3sym){#sdfootnote3anc .sdfootnoteanc}. One of
the differences in German from one country to another is sorting order.
For this reason and others, language is not always sufficient to
precisely define a locale.

### []{#pgfId-39351}Country (Region) Codes

[]{#pgfId-50382} Country codes are defined by *ISO 3166* , another
international standard. It defines two and three letter abbreviations
for each country or major region in the world. In contrast to the
language codes, country codes are uppercased. Table 3 shows a few of the
defined codes.[^4^](#sdfootnote4sym){#sdfootnote4anc .sdfootnoteanc}
Locale uses the two letter codes instead of the three letter codes that
are also defined by other versions of this standard.

[]{#pgfId-50916}Country codes are an important l*[ocale component
because Format]{style="font-style: normal;"}* objects for dates, time,
numbers, and currency are particularly sensitive to this element.
Country codes add precision to the language component of a
*[Locale]{style="font-style: normal;"}* . For example, French as a basic
language is used in both France and Canada. However, precise usage and
idiomatic expressions will vary. These differences can be captured with
different *[Locale]{style="font-style: normal;"}* designators in which
only the country code is different. For example,
*[fr_CA]{style="font-style: normal;"}* (French-speaking Canada) is a
different *[Locale]{style="font-style: normal;"}* than
*[fr_FR]{style="font-style: normal;"}* (French-speaking France)..

*Table 3 Some country codes defined in the ISO 3166 standard.*

  ------------------------------- ----------------------
  []{#pgfId-50650}Country         []{#pgfId-50652}Code
  []{#pgfId-50654}United States   []{#pgfId-50656}US
  []{#pgfId-50658}Canada          []{#pgfId-50660}CA
  []{#pgfId-50662}France          []{#pgfId-50664}FR
  []{#pgfId-50666}Japan           []{#pgfId-50668}JP
  []{#pgfId-50670}Germany         []{#pgfId-50672}DE
  ------------------------------- ----------------------

### []{#pgfId-42128}Variant Code

[]{#pgfId-46258} Operating system (OS), browser, and other application
vendors can use the variant to provide additional functionality or
customization that isn\'t possible with just a language and country
designation. For example, a software company may need to indicate a
locale for a specific operating system, so they may create an
*[es_ES_MAC]{style="font-style: normal;"}* or
*[es_ES_WIN]{style="font-style: normal;"}* locale for the Macintosh or
Windows platforms. One historical example from the Java 2 platform
itself is the use of the *[EURO]{style="font-style: normal;"}* variant
for European locales that use the Euro currency. During the transition
period for those countries, the Java platform (version 1.3) used this
variant. For example, although a *[de_DE]{style="font-style: normal;"}*
(German-speaking Germany) locale existed, a
*[de_DE_EURO]{style="font-style: normal;"}* (German-speaking German
locale with a Euro variant) was added to the Java environment. Because
the Euro currency is now the standard currency for the affected locales
at this point, those variants have been removed since version 1.4 of the
platform. Most application designs will probably not require variant
locale definitions.

## []{#pgfId-39813}[]{#76130}Construction

[]{#pgfId-39819} The *[Locale]{style="font-style: normal;"}* class has
several constructors:

-   ##### []{#pgfId-39822}*[Locale(String language) ]{style="font-style: normal;"}* {#localestring-language .bl1-bullet-first}

-   ##### []{#pgfId-46273}*[Locale(String language, String region) ]{style="font-style: normal;"}* {#localestring-language-string-region .bl-bullet}

-   ##### []{#pgfId-41047}*[Locale(String language, String region, String variant)]{style="font-style: normal;"}* {#localestring-language-string-region-string-variant .bll-bullet-last}

[]{#pgfId-40272} The following shows how each constructor can be used:

[]{#pgfId-46276}[]{#pgfId-51413} *[// Create a generic English speaking
locale]{style="font-style: normal;"}*

[]{#pgfId-51411} *[Locale locale1 = new
Locale(\"en\");]{style="font-style: normal;"}*[
]{style="font-style: normal;"}

// Create an English speaking, Canadian locale

[]{#pgfId-46292} *[Locale locale2 = new Locale(\"en\",
\"CA\"\");]{style="font-style: normal;"}*[
]{style="font-style: normal;"}

[]{#pgfId-51417} // Create a very specific English speaking, United
States locale

[]{#pgfId-51420} // for Silicon Valley

###### []{#pgfId-46295}*[Locale locale3 = new Locale(\"en\", \"US\", \"SiliconValley\");]{style="font-style: normal;"}* {#locale-locale3-new-localeen-us-siliconvalley .code-frag-last}

[]{#pgfId-40290} Using the ISO 639 two letter code, the
*[en]{style="font-style: normal;"}* represents English. The ISO 3166
codes *[CA]{style="font-style: normal;"}* and
*[US]{style="font-style: normal;"}* represent Canada and the United
States respectively. The last code line above shows how to create a
*[Locale]{style="font-style: normal;"}* with an optional variant. The
last locale shows the creation of an
*[en_US_SiliconValley]{style="font-style: normal;"}* locale. This locale
is more specific than the first instance. Not only is the locale a U.S.
English speaking one, but it is also associated with an additional
locale variant, *[SiliconValley]{style="font-style: normal;"}* . The
variant can be anything you need since one of its purposes is to provide
developers the ability to define custom locales.

[]{#pgfId-40293} Although the compiler and run-time environment won\'t
complain if you make up your own language and country/region
identifiers, you should use only the valid codes, which are defined by
ISO standards. By constraining yourself to the ISO definitions, you\'ll
ensure compatibility with other applications and coding standards. More
importantly, locale-sensitive class libraries use only the ISO codes.
For example, the *[java.text.NumberFormat]{style="font-style: normal;"}*
class will understand how to behave for the
*[de_DE]{style="font-style: normal;"}* (German language, Germany)
locale, but it won\'t understand what to do with a fictitous
*[foo_biz]{style="font-style: normal;"}* locale. If you use non-ISO
based locale identifiers, you will be responsible for writing the
locale-sensitive code to support them.

## []{#pgfId-42356}Pre-Constructed Locales

[]{#pgfId-42357}[]{#pgfId-42361}The Locale class has many static fields
that represent instantiated Locale objects. For example,
*[Locale.FRANCE]{style="font-style: normal;"}* is a pre-made static
Locale object that represents French-speaking France. You can use
*[Locale.FRANCE]{style="font-style: normal;"}* anywhere you might use
*[new Locale(\"fr\", \"FR\") ]{style="font-style: normal;"}*. The
following table shows some of the \"pre-constructed\" Locale objects
that are available.

\

*Table 4 Some of the pre-made Locale objects.*

  -------------------------------------------- ------------------------
  []{#pgfId-42365}Member Name                  []{#pgfId-42367}Locale
  []{#pgfId-42369}Locale.CANADA                []{#pgfId-42371}en_CA
  []{#pgfId-42373}Locale.CANADA_FRENCH         []{#pgfId-42375}fr_CA
  []{#pgfId-42377}Locale.CHINA                 []{#pgfId-42379}zh_CN
  []{#pgfId-42381}Locale.CHINESE               []{#pgfId-42383}zh
  []{#pgfId-42385}Locale.SIMPLIFIED_CHINESE    []{#pgfId-42387}zh_CN
  []{#pgfId-42389}Locale.TRADITIONAL_CHINESE   []{#pgfId-42391}zh_TW
  []{#pgfId-42393}Locale.PRC                   []{#pgfId-42395}zh_CN
  []{#pgfId-42397}Locale.TAIWAN                []{#pgfId-42399}zh_TW
  []{#pgfId-42401}Locale.ENGLISH               []{#pgfId-42403}en
  []{#pgfId-42405}Locale.UK                    []{#pgfId-42407}en_GB
  []{#pgfId-42409}Locale.US                    []{#pgfId-42411}en_US
  []{#pgfId-42413}Locale.FRANCE                []{#pgfId-42415}fr_FR
  []{#pgfId-42417}Locale.FRENCH                []{#pgfId-42419}fr
  []{#pgfId-42421}Locale.GERMAN                []{#pgfId-42423}de
  []{#pgfId-42425}Locale.GERMANY               []{#pgfId-42427}de_DE
  []{#pgfId-42429}Locale.ITALIAN               []{#pgfId-42431}it
  []{#pgfId-42433}Locale.ITALY                 []{#pgfId-42435}it_IT
  []{#pgfId-42437}Locale.JAPAN                 []{#pgfId-42439}ja_JP
  []{#pgfId-42441}Locale.JAPANESE              []{#pgfId-42443}ja
  []{#pgfId-42445}Locale.KOREA                 []{#pgfId-42447}ko_KR
  []{#pgfId-42449}Locale.KOREAN                []{#pgfId-42451}ko
  -------------------------------------------- ------------------------

[]{#pgfId-50206} Pre-constructed locales exist for convenience. However,
the list of static class constants is small and incomplete. Every
important locale is not represented. Locale sensitive class support is
not determined by whether the locale exists as a Locale class constant.
For example, no South American locale constants exist, yet they have
complete support by several locale sensitive classes including
*[DateFormat]{style="font-style: normal;"}* and
*[NumberFormat]{style="font-style: normal;"}* .

[]{#pgfId-51299} Since so few of these pre-made locales exist, you
should probably just avoid these static objects altogether. Although
using these shortcut identifiers is convenient, your code will be more
consistent without them.

## []{#pgfId-50207}Identifying Supported Locales

[]{#pgfId-50208} What locales are supported in the Java platform? As you
saw in the constructors, you can create any locale that you\'d like.
However, simply creating a *[Locale]{style="font-style: normal;"}*
object doesn\'t mean that your runtime environment fully supports it.

[]{#pgfId-41249} If you simply want to know what
*[Locale]{style="font-style: normal;"}* objects you can create, the
answer is simple: you can create any
*[Locale]{style="font-style: normal;"}* you\'d like. The constructors
won\'t complain about non-ISO arguments. However, a more helpful
interpretation or restatement of the question is this: for which locales
do the class libraries provide more extensive information? Or, for which
locales can the libraries provide collation, time, date, numbers, and
currency information? Also, you might ask what scripts or writing
systems are supported by your runtime environment. The following
sections describe how to determine supported locales in the runtime
libraries. Additionally, they describe the supported scripts that can be
displayed by the text components. Finally, they enumerate the
localizations that are available for the runtime libraries and software
development kit itself.

### []{#pgfId-41239}Enabled Locales in java.util and java.text Packages

[]{#pgfId-51692} In the runtime environment, there is no requirement
that all locales be supported equally by every locale-sensitive class.
Every locale-sensitive class implements its own support for a set of
locales, and that set can be different from class to class. For example,
a number format class can support a different set of locales than a date
class. Additionally, there is no requirement that all runtime
implementations support the same set of locales. There is, however, a
minimal list that all implementations must support. This list is quite
short: English (U.S.). Fortunately, the runtime environment provided by
Sun is much more extensive. Although it is not formally required, Sun\'s
runtime implementation supports the same set of locales in each of its
locale-sensitive data format classes. This provides a consistent set of
support across classes. The following table lists just a few of the
locales supported by class libraries in the most recent version of the
JRE. Please see Sun\'s Java platform website to get the entire
list.[^5^](#sdfootnote5sym){#sdfootnote5anc .sdfootnoteanc}

*Table 5 Some of the supported Locales in java.util and java.text
Packages*

  --------------------------------------- -------------------------------- ---------------------------
  []{#pgfId-52258}Language                []{#pgfId-52260}Country          []{#pgfId-52262}Locale ID
  []{#pgfId-52126}Arabic                  []{#pgfId-52128}Saudia Arabia    []{#pgfId-52130}ar_SA
  []{#pgfId-52132}Chinese (Simplified)    []{#pgfId-52134}China            []{#pgfId-52136}zh_CN
  []{#pgfId-52138}Chinese (Traditional)   []{#pgfId-52140}Taiwan           []{#pgfId-52142}zh_TW
  []{#pgfId-52144}Dutch                   []{#pgfId-52146}Netherlands      []{#pgfId-52148}nl_NL
  []{#pgfId-52150}English                 []{#pgfId-52152}Australia        []{#pgfId-52154}en_AU
  []{#pgfId-52156}English                 []{#pgfId-52158}Canada           []{#pgfId-52160}en_CA
  []{#pgfId-52162}English                 []{#pgfId-52164}United Kingdom   []{#pgfId-52166}en_GB
  []{#pgfId-52168}English                 []{#pgfId-52170}United States    []{#pgfId-52172}en_US
  []{#pgfId-52174}French                  []{#pgfId-52176}Canada           []{#pgfId-52178}fr_CA
  []{#pgfId-52180}French                  []{#pgfId-52182}France           []{#pgfId-52184}fr_FR
  []{#pgfId-52186}German                  []{#pgfId-52188}Germany          []{#pgfId-52190}de_DE
  []{#pgfId-52192}Hebrew                  []{#pgfId-52194}Israel           []{#pgfId-52196}iw_IL
  []{#pgfId-52198}Hindi                   []{#pgfId-52200}India            []{#pgfId-52202}hi_IN
  []{#pgfId-52204}Italian                 []{#pgfId-52206}Italy            []{#pgfId-52208}it_IT
  []{#pgfId-52210}Japanese                []{#pgfId-52212}Japan            []{#pgfId-52214}ja_JP
  []{#pgfId-52216}Korean                  []{#pgfId-52218}South Korea      []{#pgfId-52220}ko_KR
  []{#pgfId-52222}Portuguese              []{#pgfId-52224}Brazil           []{#pgfId-52226}pt_BR
  []{#pgfId-52228}Spanish                 []{#pgfId-52230}Spain            []{#pgfId-52232}es_ES
  []{#pgfId-52234}Swedish                 []{#pgfId-52236}Sweden           []{#pgfId-52238}sv_SE
  []{#pgfId-52240}Thai (Western digits)   []{#pgfId-52242}Thailand         []{#pgfId-52244}th_TH
  []{#pgfId-52246}Thai (Thai digits)      []{#pgfId-52248}Thailand         []{#pgfId-52250}th_TH_TH
  --------------------------------------- -------------------------------- ---------------------------

[]{#pgfId-52275} To find out what locales are supported by your JRE, you
have to ask each locale-sensitive class. Each class that supports
multiple locales will implement
*[getAvailableLocales()]{style="font-style: normal;"}* . For example,

###### []{#pgfId-41152}*[Locale\[\] localeList = NumberFormat.getAvailableLocales();]{style="font-style: normal;"}* {#locale-localelist-numberformat.getavailablelocales .code-frag-one-line}

[]{#pgfId-51815} The
*[getAvailableLocales()]{style="font-style: normal;"}* method is
implemented in many of the classes in the
*[java.text]{style="font-style: normal;"}* and
*[java.util]{style="font-style: normal;"}* packages. For example,
*[NumberFormat]{style="font-style: normal;"}* ,
*[DateFormat]{style="font-style: normal;"}* ,
*[Calendar]{style="font-style: normal;"}* , and
*[BreakIterator]{style="font-style: normal;"}* support it.

[]{#pgfId-41153} The *[Locale]{style="font-style: normal;"}* class
itself has a static
*[getAvailableLocales()]{style="font-style: normal;"}* method. It is
tempting to use
*[Locale.getAvailableLocales()]{style="font-style: normal;"}* to
determine what locales your environment supports, but that would be an
unfortunate mistake. As mentioned previously, each locale-sensitive
class is free to support a different set of locales. The following code
demonstrates how a *[Locale]{style="font-style: normal;"}* instance can
provide localized information about itself for three different locales,
the default locale of the author\'s system, the German locale, and the
French locale:

[]{#pgfId-51735}[]{#pgfId-51736} Locale deLocale = new Locale(\"de\",
\"DE\");

Locale frLocale = new Locale(\"fr\", \"FR\");

[]{#pgfId-51737}[]{#pgfId-51772} System.out.println(\"Default language
name (default): \" + deLocale.getDisplayLanguage());

[]{#pgfId-51738}[]{#pgfId-51775} System.out.println(\"German language
name (German): \" + deLocale.getDisplayLanguage(deLocale));

[]{#pgfId-51781}[]{#pgfId-51782} System.out.println(\"German language
name (French): \" + deLocale.getDisplayLanguage(frLocale));

[]{#pgfId-51787} OUTPUT:

[]{#pgfId-51800} German language name (default): German

[]{#pgfId-51803} German language name (German): Deutsch

###### []{#pgfId-51806}German language name (French): allemand {#german-language-name-french-allemand .code-frag-last}

[]{#pgfId-51810} As you can see from the above code and output, the
*Locale* class itself is localized for several locales. For example, it
can provide information about the German locale in English, German, and
French.

### []{#pgfId-51699}Enabled Script Support

[]{#pgfId-51592} Text components don\'t usually support single locales.
Instead, text widgets support a set of scripts that often cross locale
boundaries. Although it is impossible to get a listing of supported
scripts from the various text components themselves, the list is
published on Sun\'s Java platform
website.[^6^](#sdfootnote6sym){#sdfootnote6anc .sdfootnoteanc} In
general, peered AWT components support scripts that are supported by the
underlying host. If your host system is localized to Arabic, the AWT
text components will display Arabic. On an Arabic system, you would also
be able to enter Arabic text into components like TextField or TextArea.
However, you cannot expect those same AWT components to display text
that isn\'t in the same script as the localized host. An English host
would not typically be able to display Arabic in a TextField for
example. Swing components, however, can often support multiple scripts
because of their independence from the host platform and their use of
Unicode as a multi-script character set. Therefore, Swing components can
often display a script even when peered AWT components cannot. Some of
the supported scripts are shown below.

*Table 6 Some of the supported scripts for text display*

+----------------------------------+----------------------------------+
| []{#pgfId-52315}Writing System   | []{#pgfId-52317}Language         |
+----------------------------------+----------------------------------+
| ###### []{#pgfId-52319}Arabi     | []{#pgfId-52321}Arabic           |
| c {#arabic .tsh-table-side-head} |                                  |
+----------------------------------+----------------------------------+
| ###### []{#pgfId-52323           | []{#pgfId-52325}Chinese          |
| }Chinese (Simplified) {#chinese- |                                  |
| simplified .tsh-table-side-head} |                                  |
+----------------------------------+----------------------------------+
| ###### []{#pgfId-52327}C         | []{#pgfId-52329}Chinese          |
| hinese (Traditional) {#chinese-t |                                  |
| raditional .tsh-table-side-head} |                                  |
+----------------------------------+----------------------------------+
| ####                             | []{#pgfId-52333}Hindi            |
| ## []{#pgfId-52331}Devanagari {# |                                  |
| devanagari .tsh-table-side-head} |                                  |
+----------------------------------+----------------------------------+
| ###### []{#pgfId-52335}Hebre     | []{#pgfId-52337}Hebrew           |
| w {#hebrew .tsh-table-side-head} |                                  |
+----------------------------------+----------------------------------+
| ###### []{#pgfId-52339}Japanese  | []{#pgfId-52341}Japanese         |
| {#japanese .tsh-table-side-head} |                                  |
+----------------------------------+----------------------------------+
| ###### []{#pgfId-52343}Korea     | []{#pgfId-52345}Korean           |
| n {#korean .tsh-table-side-head} |                                  |
+----------------------------------+----------------------------------+
| ###### []{#pgf                   | []{#pgfId-52349}English, French, |
| Id-52347}Latin - Western Europea | German, Italian, Spanish,        |
| n subset {#latin---western-europ | Swedish, etc.                    |
| ean-subset .tsh-table-side-head} |                                  |
+----------------------------------+----------------------------------+
| ###### []{#pgfId-52351}T         | []{#pgfId-52353}Thai             |
| hai {#thai .tsh-table-side-head} |                                  |
+----------------------------------+----------------------------------+
| ###### []{#pgfId-52469}Gre       | ###### []{#pgfId-52485}Greek     |
| ek {#greek .tsh-table-side-head} |  {#greek-1 .tsh-table-side-head} |
+----------------------------------+----------------------------------+
| ###### []{#pgfId-52359}Cyrillic  | []{#pgfId-52361}Belorussian,     |
| {#cyrillic .tsh-table-side-head} | Russian etc.                     |
+----------------------------------+----------------------------------+
| ###### []{#pgfId-52363}Lat       | []{#pgfId-52365}Latvian,         |
| in - Baltic subset {#latin---bal | Lithuanian                       |
| tic-subset .tsh-table-side-head} |                                  |
+----------------------------------+----------------------------------+
| ###### []{#pgf                   | []{#pgfId-52369}Czech,           |
| Id-52367}Latin - Central Europea | Hungarian, Polish, etc.          |
| n subset {#latin---central-europ |                                  |
| ean-subset .tsh-table-side-head} |                                  |
+----------------------------------+----------------------------------+
| ###### []{#pgfId-52371}Lat       | []{#pgfId-52373}Turkish etc.     |
| in - Turkic subset {#latin---tur |                                  |
| kic-subset .tsh-table-side-head} |                                  |
+----------------------------------+----------------------------------+

### []{#pgfId-51703}JRE and SDK Localizations

[]{#pgfId-51707} User interface elements in the runtime environment have
been localized for several locales. These elements include AWT and Swing
components and other messages generated by the JRE and included tools.
The following table shows all the current localizations provided for the
JRE:

*Table 7 User interface translations for the JRE*

+-----------------------------------------+---------------------------+
| []{#pgfId-52584}Language                | []{#pgfId-52586}Locale ID |
+-----------------------------------------+---------------------------+
| ###### []{                              | []{#pgfId-52590}zh_CN     |
| #pgfId-52588}Chinese (Simplified) {#chi |                           |
| nese-simplified-1 .tsh-table-side-head} |                           |
+-----------------------------------------+---------------------------+
| ###### []{#p                            | []{#pgfId-52594}zh_TW     |
| gfId-52592}Chinese (Traditional) {#chin |                           |
| ese-traditional-1 .tsh-table-side-head} |                           |
+-----------------------------------------+---------------------------+
| ###### []{#pgfId-52596}                 | []{#pgfId-52598}en        |
| English {#english .tsh-table-side-head} |                           |
+-----------------------------------------+---------------------------+
| ###### []{#pgfId-5260                   | []{#pgfId-52602}en        |
| 0}French {#french .tsh-table-side-head} |                           |
+-----------------------------------------+---------------------------+
| ###### []{#pgfId-5260                   | []{#pgfId-52606}de        |
| 4}German {#german .tsh-table-side-head} |                           |
+-----------------------------------------+---------------------------+
| ###### []{#pgfId-52608}                 | []{#pgfId-52610}it        |
| Italian {#italian .tsh-table-side-head} |                           |
+-----------------------------------------+---------------------------+
| ###### []{#pgfId-52612}Japa             | []{#pgfId-52614}ja        |
| nese {#japanese-1 .tsh-table-side-head} |                           |
+-----------------------------------------+---------------------------+
| ###### []{#pgfId-52616}                 | []{#pgfId-52618}ko        |
| Korean {#korean-1 .tsh-table-side-head} |                           |
+-----------------------------------------+---------------------------+
| ###### []{#pgfId-52762}                 | []{#pgfId-52764}es        |
| Spanish {#spanish .tsh-table-side-head} |                           |
+-----------------------------------------+---------------------------+
| ###### []{#pgfId-52758}                 | []{#pgfId-52760}sv        |
| Swedish {#swedish .tsh-table-side-head} |                           |
+-----------------------------------------+---------------------------+

[]{#pgfId-52774} Some tools, like the javac compiler, are provided only
by the Java 2 Software Development Kit (J2SDK). These tools provide
error, warning, and informational messages to the user. Those messages
within the SDK utilities and tools, including the compiler, are
translated into the languages shown in the table below:

*Table 8 User interface translations for SDK tools*

+-----------------------------------------+---------------------------+
| []{#pgfId-52785}Language                | []{#pgfId-52787}Locale ID |
+-----------------------------------------+---------------------------+
| ###### []{#pgfId-52789}En               | []{#pgfId-52791}en        |
| glish {#english-1 .tsh-table-side-head} |                           |
+-----------------------------------------+---------------------------+
| ###### []{#pgfId-52793}Japa             | []{#pgfId-52795}ja        |
| nese {#japanese-2 .tsh-table-side-head} |                           |
+-----------------------------------------+---------------------------+

## []{#pgfId-51085}[]{#85894}Representing Locale as a String

[]{#pgfId-43635} Although most of your use of
*[Locale]{style="font-style: normal;"}* will require a
*[Locale]{style="font-style: normal;"}* object reference, it is
sometimes convenient to use an alternative representation, especially
for internal debugging purposes. A
*[Locale]{style="font-style: normal;"}* object\'s
*[toString()]{style="font-style: normal;"}* method returns a
*[String]{style="font-style: normal;"}* that is the concatenation of the
language, region, and variant codes. The
*[toString()]{style="font-style: normal;"}* method separates each
component with \`\_\', an underscore character. You may want to use this
method during debugging since it provides a convenient and readable
representation.

[]{#pgfId-43658} Consider the Locale created with this line:

###### []{#pgfId-42158}Locale l = new Locale(\"ja\", \"JP\"); {#locale-l-new-localeja-jp .code-frag-one-line}

[]{#pgfId-42159} The *[toString()]{style="font-style: normal;"}* method
would return *[ja_JP]{style="font-style: normal;"}* for this Locale.

[]{#pgfId-43864} This string is not typically appropriate for
presentation to an end-user. Most people will think it is too cryptic.
Customers aren\'t usually familiar with the ISO 639 and 3166 standards
for language and region codes. Fortunately, more user friendly text
representations are available. Those are covered later in this article.

## []{#pgfId-42160}Using Locale

[]{#pgfId-46091} Although not always obvious,
*[Locale]{style="font-style: normal;"}* objects are used throughout the
Java class libraries. Even when you don\'t explicitly ask for a
*[Locale]{style="font-style: normal;"}* preference, the Java environment
uses default *[Locale]{style="font-style: normal;"}* settings to provide
you with localized information and behavior. When you use an explicit
*[Locale]{style="font-style: normal;"}* , you can use a different
*[Locale]{style="font-style: normal;"}* for each different part of your
application. In other words, you can use the
*[es_MX]{style="font-style: normal;"}* , Spanish (Mexico), locale for
displaying localized messages in Spanish and use the
*[en_US]{style="font-style: normal;"}* , English (United States), locale
for number and currency formatting. This type of support would be useful
for Spanish speakers who live and work in the United States. Although
the application user could view Spanish menus, prompts, and text, the
rest of the application could format numbers and currency correctly for
the United States. This is a simple example of how you can use multiple
locales in a single application. If your applications ever require this
level of *[Locale]{style="font-style: normal;"}* support, you have the
freedom to determine the behavior of every aspect of an application.

Some of the locale-sensitive classes format numbers, currencies, dates,
and time. Others provide collation as well as word breaking services.
Classes will typically provide a constructor or factory method for
creating instances. In each case, you usually have the option of
providing an explicit *[Locale]{style="font-style: normal;"}* preference
when the default isn\'t appropriate.

### []{#pgfId-46117}Using a Default Locale

[]{#pgfId-46118} The default *Locale* is used by locale-sensitive
objects whenever your application doesn\'t specify an explicit *Locale*
choice. Depending on the default *Locale* is not wise. In multi-user
applications, a single default *Locale* is usually not appropriate for
everyone using the system. Instead your application should explicitly
provide a preference to all locale-sensitive objects. The default
*Locale* is a system-wide resource, available throughout your
application to any locale-sensitive object. As the default, it may be
correct for your application\'s user, although in multilingual or
multicultural environments you should be explicit. This is especially
important when your application runs on a single host that supports many
users.

[]{#pgfId-51609} Retrieve the default *Locale* using the following
method:

###### []{#pgfId-46476}public static Locale getDefault() {#public-static-locale-getdefault .code-frag-one-line}

[]{#pgfId-41510} The default *Locale* of your application is determined
in three ways. First, unless you have explicitly changed the default,
the *getDefault()* method returns the *Locale* that was initially
determined by the Java Virtual Machine (JVM) when it first loads. That
is, the JVM determines the default *Locale* from the host environment.
The host environment\'s *Locale* is determined by the host operating
system and the user preferences established on that system.

[]{#pgfId-46473} Second, the application user can override the host\'s
default *Locale* by providing this information on the command line by
setting the *user.language* and the *user.region* system properties.

[]{#pgfId-51623} The following code will print out a different Locale
depending on the value of these properties when it is invoked:

###### []{#pgfId-43852} import java.util.Locale; {#import-java.util.locale .code-frag-first style="margin-bottom: 0.2in;"}

public class Default {

public static void main(String\[\] args) {

System.out.println(Locale.getDefault());

}

###### []{#pgfId-41457}} {#section .code-frag-last}

[]{#pgfId-41447} You can experiment with the above code example. Running
on a U.S. English system, the above code prints *en_US* . If you provide
command line options as described above, you can coax your application
into using any *Locale* you need.

[]{#pgfId-41470} For example, you can invoke the application like this:

###### []{#pgfId-41471}java -Duser.language=fr -Duser.region=CA Default {#java--duser.languagefr--duser.regionca-default .code-frag-one-line}

[]{#pgfId-41482} This invocation prints *fr_CA* as the default *Locale*
.

[]{#pgfId-41490} Third, your application can call the *setDefault()*
method. The *setDefault()* method lets your application set a
system-wide resource. After you set the default *Locale* with this
method, subsequent calls to *Locale.getDefault()* will return the newly
set *Locale* .

[]{#pgfId-42927} Take care not to call *setDefault()* in applets. The
Security Manager will not allow you to call this method since it affects
a system-wide resource within the JVM that runs on the host.

[]{#pgfId-46528} In most cases, using the default locale with other
classes means ignoring it altogether. For example, if you want to format
a number for your default locale, you simply create a NumberFormat
without any arguments:

###### []{#pgfId-46531}NumberFormat nf = NumberFormat.getInstance(); {#numberformat-nf-numberformat.getinstance .code-frag-one-line}

[]{#pgfId-46535} That\'s it; using the default locale requires almost
nothing on your part. Other locale-sensitive classes follow this same
pattern. If you want the default locale behaviour, do nothing special
when creating the object. However, the default isn\'t always
appropriate, and you\'ll need to be more explicit at those times.

### []{#pgfId-46096}Using an Explicit Locale

[]{#pgfId-46136} In some computing environments, applications utilize
only a single locale throughout their life cycle. In other environments,
applications utilize a global locale that can be changed. Those
environments allow you to programmatically change the global locale
preference, which remains in effect until you explicitly change it
again. The Java environment is unique, providing you with the ability to
use a variety of locales throughout your application in any way you
require.

[]{#pgfId-46164} Multinational companies have customers all around the
globe. This means that both their customers and employees speak
different languages and have different expectations for how the company
and its software should behave. Moreover, it is entirely possible, even
common, to have a French employee handle a sales record for an Italian
customer. In those situations, you will need absolute control over which
locale your business and user interface objects use to manipulate and
represent data. Your application may need to print sales receipts using
Italian date and currency formats, yet sort customer lists for a French
sales employee. The combinations are far to numerous to list, but the
Java environment provides you the flexibility to handle that complexity
should it ever be required.

[]{#pgfId-46180} In order to get the highest level of flexibility, you
must explicitly request support for a target locale for each
locale-sensitive class that you use. That means you must track the
locale preferences for multiple aspects of the application or assign
locale preferences to different users and customers.

[]{#pgfId-46536} If you have tracked the user\'s locale preference, you
would create instances of locale-sensitive classes by explicitly
providing a Locale in a constructor or creation method. Imagine that a
preferences object stores your customer\'s locale choice:

###### []{#pgfId-46548} Locale userLocale = preferences.getLocale(); {#locale-userlocale-preferences.getlocale .code-frag-first style="margin-bottom: 0.2in;"}

###### []{#pgfId-46557}NumberFormat nf = NumberFormat.getInstance(userLocale); {#numberformat-nf-numberformat.getinstanceuserlocale .code-frag-last}

## []{#pgfId-42928}[]{#29306}Retrieving Locale Information

[]{#pgfId-45601} Although Locale objects don\'t have a lot of
information, they do provide a few interesting methods. As you might
expect, the information is tightly related to the language, country, and
variant of the object. Some of this information is locale-independent;
some is locale-dependent. All this means is that the Locale object has
two different forms for most of its methods. One set of information is
not customer-oriented or localized. The other set is localized and is
suitable for presentation to the user.

### []{#pgfId-45618}Locale Independent Information

[]{#pgfId-42929} The *getLanguage()* method returns the ISO 639
two-letter abbreviation for the Locale\'s language. For example, if you
have created the Locale *ja_JP* , this method returns the code *ja* .
The method\'s full signature is

###### []{#pgfId-45206}public String getLanguage() {#public-string-getlanguage .code-frag-one-line}

[]{#pgfId-42865} An extension of the ISO 639 standard defines
three-letter language codes. Although these codes are not currently used
in the J2SE, the codes are available. Use the following method to
retrieve the three-letter language code:

###### []{#pgfId-45100}public String getISO3Language() {#public-string-getiso3language .code-frag-one-line}

[]{#pgfId-45136} An example shows the difference:

###### []{#pgfId-45157} Locale aLocale = Locale.JAPAN {#locale-alocale-locale.japan .code-frag-first style="margin-bottom: 0.2in;"}

[]{#pgfId-45164} System.out.println(\"Locale: \" + aLocale);

[]{#pgfId-45138} System.out.println(\"ISO 2 letter: \" +
aLocale.getLanguage());

[]{#pgfId-45139} System.out.println(\"ISO 3 letter: \" +
aLocale.getISO3Language());

[]{#pgfId-45141}  

[]{#pgfId-45175} aLocale = Locale.US;

[]{#pgfId-45142} System.out.println(\"Locale: \" + aLocale);

[]{#pgfId-45143} System.out.println(\"ISO 2 letter: \" +
aLocale.getLanguage());

[]{#pgfId-45144} System.out.println(\"ISO 3 letter: \" +
aLocale.getISO3Language());

[]{#pgfId-45176}  

[]{#pgfId-45177} OUTPUT:

[]{#pgfId-45178} Locale: ja_JP

[]{#pgfId-45179} ISO 2 letter: ja

[]{#pgfId-45180} ISO 3 letter: jpn

[]{#pgfId-45181} Locale: en_US

[]{#pgfId-45185} ISO 2 letter: en

###### []{#pgfId-45183}ISO 3 letter: eng {#iso-3-letter-eng .code-frag-last}

[]{#pgfId-45211} The *getCountry()* method returns the ISO 3166
two-letter abbreviation for the Locale\'s region or country member. Its
full signature is

###### []{#pgfId-45215}public String getCountry() {#public-string-getcountry .code-frag-one-line}

[]{#pgfId-45227} An ISO extension defines a three-letter code for
countries too:

###### []{#pgfId-45212}public String getISO3Country() {#public-string-getiso3country .code-frag-one-line}

[]{#pgfId-45225} An example demonstrates their difference:

###### []{#pgfId-42894} Locale aLocale = Locale.CANADA_FRENCH; {#locale-alocale-locale.canada_french .code-frag-first style="margin-bottom: 0.2in;"}

[]{#pgfId-45243} System.out.println(\"Locale: \" + aLocale);

[]{#pgfId-45250} System.out.println(\"ISO 2 letter: \" +
aLocale.getCountry());

[]{#pgfId-45251} System.out.println(\"ISO 3 letter: \" +
aLocale.getISO3Country());

[]{#pgfId-45265}  

[]{#pgfId-45266} OUTPUT:

[]{#pgfId-45267} Locale: fr_CA

[]{#pgfId-45268} ISO 2 letter: CA

###### []{#pgfId-45271}ISO 3 letter: CAN {#iso-3-letter-can .code-frag-last}

[]{#pgfId-41634} If your Locale object has a variant field, the
*getVariant()* method will identify and return it as a String. If the
Locale object has not defined a variant, this method returns an empty
String. This method\'s declaration is

###### []{#pgfId-42949}public String getVariant() {#public-string-getvariant .code-frag-one-line}

[]{#pgfId-45328} The following class methods can be used to retrieve
arrays of all the valid language and country codes available:

##### []{#pgfId-45329}*public static String\[\] getISOCountries()* {#public-static-string-getisocountries .bl1-bullet-first}

##### []{#pgfId-45330}*public static String\[\] getISOLanguages()* {#public-static-string-getisolanguages .bll-bullet-last}

[]{#pgfId-45638} Developers will typically get the most benefit from the
methods in this section. For example, a developer is much more likely to
appreciate and to use the code returned by getLanguage() than an actual
customer. Your customers probably expect something different as
described in the next section.

### []{#pgfId-41569}[]{#29595}Locale Dependent Information

[]{#pgfId-41642} The codes supplied by the *getLanguage(),
getCountry(),* and *getVariant()* methods are not especially user
friendly. Your customer should probably not have to interpret these
codes, so Locale provides additional methods that provide more readable,
customer-oriented informtion.

[]{#pgfId-45417} Locale objects provide methods that return human
understandable text representations. This text representation is
different from what the *toString()* method provides. Unlike the simple
concatenation of the language, country, and variant fields, these
methods provide human-readable, localized information about the Locale:

##### []{#pgfId-46496}*public final String getDisplayLanguage()* {#public-final-string-getdisplaylanguage .bl1-bullet-first}

##### []{#pgfId-46500}*public final String getDisplayCountry()* {#public-final-string-getdisplaycountry .bl-bullet}

##### []{#pgfId-46501}*public final String getDisplayVariant()* {#public-final-string-getdisplayvariant .bll-bullet-last}

#### []{#pgfId-45651}Display Language

[]{#pgfId-45852} When you need to display a locale\'s language to your
user, you should use the Locale object\'s *getDisplayLanguage()* method.
This method returns the displayable, human readable name of the
Locale\'s language. The display name is localized for the default Locale
if you don\'t provide a target Locale argument. There are two forms of
this method:

##### []{#pgfId-45508}*public final String getDisplayLanguage()* {#public-final-string-getdisplaylanguage-1 .bl1-bullet-first}

##### []{#pgfId-45516}*public final String getDisplayLanguage(Locale targetLocale)* {#public-final-string-getdisplaylanguagelocale-targetlocale .bll-bullet-last}

[]{#pgfId-45541} The following examples show how these methods can be
used:

###### []{#pgfId-45458} Locale deLocale = Locale.GERMANY; {#locale-delocale-locale.germany .code-frag-first style="margin-bottom: 0.2in;"}

[]{#pgfId-45568} // default system Locale is en_US for this method call

[]{#pgfId-45551} String defaultLanguage = deLocale.getDisplayLanguage();

[]{#pgfId-45573} // target de_DE is used as an explicit target language

[]{#pgfId-45554} String targetLanguage =
deLocale.getDisplayLanguage(deLocale);

[]{#pgfId-45459} System.out.println(defaultLanguage);

[]{#pgfId-45563} System.out.println(targetLanguage);

[]{#pgfId-45548}  

[]{#pgfId-45549} OUTPUT:

[]{#pgfId-45550} German

###### []{#pgfId-45579}Deutsch {#deutsch .code-frag-last}

[]{#pgfId-45769} The output \"German\" is the U.S. English word for the
locale\'s language. That\'s not especially impressive, but notice how
you can provide a target locale argument. In that situation,
getDisplayLanguage() tries to find and return a localized version of
it\'s language component.

[]{#pgfId-45782} This is important for at least one reason. You can show
the language of each locale your application supports in the target
language. You can provide this list in your application to allow your
customers to choose their preferred Locale.

[]{#pgfId-46513} This brings up an interesting question. How do you
present a Locale\'s display language in the language of the locale? You
would do it with the following:

###### []{#pgfId-46514}String displayLang = aLocale.getDisplayLanguage(aLocale); {#string-displaylang-alocale.getdisplaylanguagealocale .code-frag-one-line}

[]{#pgfId-46518} In other words, you simply provide the Locale object to
itself in the call to *getDisplayLanguage().* This same trick works with
other displayable Locale elements as well. For example, the display
country and variant can be handled this way too. The following code
snippet demonstrates this technique:

###### []{#pgfId-52833}[]{#pgfId-52852} Locale\[\] locales = { new Locale(\"en\", \"US\"), new Locale(\"ja\",\"JP\"), new Locale(\"es\", \"ES\"), new Locale(\"it\", \"IT\") }; {#locale-locales-new-localeen-us-new-localejajp-new-localees-es-new-localeit-it .code-frag-first style="margin-bottom: 0.2in;"}

[]{#pgfId-52835} for (int x=0; x\< locales.length; ++x) {

[]{#pgfId-52837}[]{#pgfId-52858} String displayLanguage =
locales\[x\].getDisplayLanguage(locales\[x\]);

[]{#pgfId-52838} println(locales\[x\].toString() + \": \" +
displayLanguage);

### []{#pgfId-52839}} {#section-1 .code-frag-first}

######    {#section-2 .tt-tabletitle}

![](Understanding%20Locale%20in%20the%20Java%202%20Platform_soubory/Locale_html_59e8dcb.png){#Graphic1
width="279" align="LEFT" border="0" height="183"}\
\
\

#### []{#pgfId-45395}Display Country

[]{#pgfId-45849} Retrieve a locale\'s country or region component for
user display with the following:

##### []{#pgfId-45681}*public final String getDisplayCountry()* {#public-final-string-getdisplaycountry-1 .bl1-bullet-first}

##### []{#pgfId-45699}*public final String getDisplayCountry(Locale targetLocale)* {#public-final-string-getdisplaycountrylocale-targetlocale .bll-bullet-last}

[]{#pgfId-45682} The first method form provides a localized country name
for the default locale. The second form provides the same information
localized for the target locale.

###### []{#pgfId-45728} Locale deLocale = Locale.GERMANY; {#locale-delocale-locale.germany-1 .code-frag-first style="margin-bottom: 0.2in;"}

[]{#pgfId-45729} // default en_US

[]{#pgfId-45730} String defaultCountry = deLocale.getDisplayCountry();

[]{#pgfId-45731} // target de_DE

[]{#pgfId-45732} String targetCountry =
deLocale.getDisplayCountry(deLocale);

[]{#pgfId-45733} System.out.println(defaultCountry);

[]{#pgfId-45734} System.out.println(targetCountry);

[]{#pgfId-45735}  

[]{#pgfId-45736} OUTPUT:

[]{#pgfId-45737} Germany

###### []{#pgfId-45757}Deutschland {#deutschland .code-frag-last}

#### []{#pgfId-45432}Display Variant

[]{#pgfId-45846} Variants are less used than other elements of a Locale.
However, at times you still need to access that information. The
*getDisplayVariant()* method returns the display name for the private
variant member of Locale:

##### []{#pgfId-45812}*public final String getDisplayVariant()* {#public-final-string-getdisplayvariant-1 .bl1-bullet-first}

##### []{#pgfId-45858}*public final String getDisplayVariant(Locale targetLocale)* {#public-final-string-getdisplayvariantlocale-targetlocale .bll-bullet-last}

[]{#pgfId-45993} The adoption of the Euro currency in many European
countries has given Sun the opportunity to provide support for several
locales that use variant components. The *getDisplayVariant()* tries to
find and return localized versions of a locale\'s variant element.

###### []{#pgfId-45994} Locale itLocale = new Locale(\"it\", \"IT\", \"EURO\"); {#locale-itlocale-new-localeit-it-euro .code-frag-first style="margin-bottom: 0.2in;"}

[]{#pgfId-45995} // default en_US

[]{#pgfId-45996} String defaultVariant = itLocale.getDisplayVariant();

[]{#pgfId-45997} // target it_IT_EURO

[]{#pgfId-45998} String targetVariant =
itLocale.getDisplayVariant(itLocale);

[]{#pgfId-45999} System.out.println(defaultVariant);

[]{#pgfId-46000} System.out.println(targetVariant);

[]{#pgfId-46028}  

[]{#pgfId-46029} OUTPUT:

[]{#pgfId-46030} Euro

###### []{#pgfId-46031}Euro {#euro .code-frag-last}

[]{#pgfId-46527} In this example, and in most others that you may likely
find, the variant display name is the same in both its forms. That is,
most variants are not usually localized to more than one language. This
is not because variants cannot be localized, but is perhaps because
variants have not been particularly important to localize so far.

#### []{#pgfId-46001}Display Name

[]{#pgfId-45892} The display name is simply a combination of the
localized language, country, and variants demonstrated earlier. The
method forms are the following:

##### []{#pgfId-45897}*public final String getDisplayName()* {#public-final-string-getdisplayname .bl1-bullet-first}

##### []{#pgfId-45901}*public final String getDisplayName(Locale targetLocale)* {#public-final-string-getdisplaynamelocale-targetlocale .bl-bullet}

[]{#pgfId-45896} Unlike Locale\'s *toString()* method, which
concatenates the individual components and separates them with an
underscore character, the *getDisplayName()* method uses parenthesis to
separate the elements.

###### []{#pgfId-45927} Locale deLocale = Locale.GERMANY; {#locale-delocale-locale.germany-2 .code-frag-first style="margin-bottom: 0.2in;"}

[]{#pgfId-45928} // default en_US

[]{#pgfId-45929} String defaultCountry = deLocale.getDisplayName();

[]{#pgfId-45930} // target de_DE

[]{#pgfId-45931} String targetCountry =
deLocale.getDisplayName(deLocale);

[]{#pgfId-45932} System.out.println(defaultCountry);

[]{#pgfId-45933} System.out.println(targetCountry);

[]{#pgfId-45964}  

[]{#pgfId-45965} OUTPUT:

[]{#pgfId-45956} German (Germany)

[]{#pgfId-45959} Deutsch (Deutschland)

## []{#pgfId-43221}Summary

[]{#pgfId-42739} *Locale* is an identifier for a language, region (often
a country), and an optional variant code. Locale objects provide several
methods which provide information about the Locale\'s state. Although a
*Locale* doesn\'t itself contain much functionality, locale-sensitive
objects depend on Locale for an indication on how to behave. Locale
sensitive objects use the Locale to customize their behavior so that
they meet the user\'s expections.

[]{#pgfId-42774} Locale objects do not have a lot of functionality.
However, a Locale\'s power comes from the classes that use it. In the
Java platform, each locale-sensitive object is responsible for its own
locale-dependent behavior. A Locale object doesn\'t enforce this
behavior, it simply acts as an indicator to other objects. Those objects
are then responsible for using the Locale appropriately. By design,
locale-sensitive classes are independent of each other. That is, the set
of supported Locales in one class does not need to be the same as the
set in another class.

[]{#pgfId-42761} In traditional operating systems and localization
models, one locale setting is active at a time. You programmatically set
the locale. Thereafter, all locale sensitive functions use the specified
locale selection. The specified locale is active throughout the
application as a global locale. It changes when there is another global
locale activation via a *setlocale* or similar call. The Java platform,
however, treats locales a little differently. A Java application can
actually have multiple locales active at the same time. That is, it is
possible to use a French date format and a U.S. number format in the
same application. Nothing limits you from creating truly multicultural
and multilingual Java applications.

::: {#sdfootnote1}
[]{#pgfId-51189}[1](#sdfootnote1anc){#sdfootnote1sym
.sdfootnotesym}Locale sensitive objects modify their behavior or
presentation characteristics to satisfy the requirements of a specific
locale.
:::

::: {#sdfootnote2}
[2](#sdfootnote2anc){#sdfootnote2sym .sdfootnotesym}[See
]{style="font-style: normal;"}*[http://lcweb.loc.gov/standards/iso639-2/langcodes.html
]{style="font-style: normal;"}*
:::

::: {#sdfootnote3}
[]{#pgfId-50971}[3](#sdfootnote3anc){#sdfootnote3sym
.sdfootnotesym}German is spoken in Germany, Austria, Liechtenstein,
Switzerland, Belgium, Luxembourg, and many other regions.
:::

::: {#sdfootnote4}
[]{#pgfId-50388}[4](#sdfootnote4anc){#sdfootnote4sym .sdfootnotesym}Look
at http://www.din.de/gremien/nas/nabd/iso3166ma/codlstp1/enlistp1.html
for a more complete list of country codes.
:::

::: {#sdfootnote5}
[]{#pgfId-522771}[5](#sdfootnote5anc){#sdfootnote5sym .sdfootnotesym}
See http://java.sun.com/j2se/1.4.1/docs/guide/intl/locale.doc.html.
:::

::: {#sdfootnote6}
[]{#pgfId-5227711}[6](#sdfootnote6anc){#sdfootnote6sym
.sdfootnotesym}Again, see
http://java.sun.com/j2se/1.4.1/docs/guide/intl/locale.doc.html.
:::
