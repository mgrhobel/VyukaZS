---
title: "MT_BPG.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/zdroje/LISA/MT_BPG.pdf"
date: 2010-01-31
type: PDF (text-based)
---

LISA
Best Practice
Guide
Implementing Machine Translation

Localization Industry Standards Association

Localization Industry Standards Association

S

INCE 990, the Localization Industry Standards Association has been helping companies enable global business. LISA is the premier not-for-proﬁt organization in the world for individuals, businesses, associations,
and standards organizations involved in language and language technology worldwide. LISA brings together IT
manufacturers, translation and localization solutions providers, and internationalization professionals, as well
as increasing numbers of vertical market corporations with an international business focus in ﬁnance, banking,
manufacturing, health care, energy and communications.

Together, these entities help LISA establish best practice guidelines and language technology standards for enterprise globalization. LISA oﬀers other services in the form of standards initiatives, Special Interest Groups, conferences and training programs which help companies implement eﬃcient international business models to provide a
return on investment for their Globalization, Internationalization, Localization, and Translation (GILT) eﬀorts.
LISA partners and aﬃliate groups include the International Organization for Standardization (ISO Liaison Category A Members of TC 37 and TC 46), The World Bank, OASIS, IDEAlliance, AIIM, The Advisory Council (TAC),
Fort-Ross, €TTEC, the Japan Technical Communicators Association, the Society of Automotive Engineers (SAE),
the European Union, the Canadian Translation Bureau, TermNet, the American Translators Association (ATA),
IWIPS, Fédération Internationale des Traducteurs (FIT), Termium, JETRO, the Institute of Translating and Interpreting (ITI), The Unicode Consortium, OpenI18N, and other professional and trade organizations.
LISA members and co-founders include some of the largest and best-known companies in the world, including
Adobe, Avaya, Cisco Systems, CLS Communication, EMC, Hewlett Packard, IBM, Innodata Isogen, Fuji Xerox,
Microsoft, Oracle, Nokia, Logitech, SAP, Siebel Systems, Standard Chartered Bank, FileNet, LionBridge Technologies, Lucent, Sun Microsystems, WH&P, PeopleSoft, Philips Medical Systems, Rockwell Automation, The
RWS Group, Xerox Corporation and Canon Research, among others.

Why Do the Leading Corporations and Organizations Around the World Support LISA?
LISA has a proven track record of partnership with governments, non-governmental organizations (NGOs) and multinational corporations. LISA helps these bodies implement best practice and language technology standards, while
providing them with access to the best independent information about what it takes to manage their multiple language
content eﬃciently to communicate eﬀectively across cultures. LISA has held more than 45 international forums and
global strategies summits in Asia, Europe and North America, as well as workshops, executive roundtables, and other
events tailored to meet the needs of speciﬁc groups or industry segments. LISA’s members and partners know that they
can come to LISA as an unbiased information resource to learn about the cost factors, technologies and business trends
that aﬀect how they do business in an increasingly globalized and integrated world.

Why Do GILT Service Providers Support LISA?
LISA has provided an open forum for more than twelve years for GILT service providers to discuss the business
and legal issues that aﬀect them, and to learn from one another and from their customers. Like their clients, service
providers understand that they need to stay current on technical standards and business developments in the GILT
industry. They also know that they can rely on the largest archive of GILT-related information in the world, available
to LISA members, including all () issues of the Globalization Insider (LISA’s content-packed newsletter, now in its
3th year of publication), (2) presentations and summaries from every major LISA event since 997, and (3) research
and survey reports that indicate where the GILT industry is today and where it is headed in the future.

LISA Best
Practice
Guides
Implementing Machine
Translation
Mike Dillinger, PhD
Arle Lommel

Edited by
Rebecca Ray

About the Contributors
Mike Dillinger, PhD, is a California-based content management consultant who works with enterprise
clients to troubleshoot and optimize their authoring and translation processes. He also helps language
technology vendors to design, develop, and promote new functionality for content management tools.
He has been developing machine translation and related technologies at Logos, Global Words Technologies, Spoken Translation, Transclick, and other companies for almost 10 years. An experienced technical
writer, revisor, interpreter and translator, he has also done more than 20 years of research and teaching
on the reading, writing, and translation of technical documents, work that spans four continents. He can
be reached at http://www.mikedillinger.com.
Arle Lommel is LISA’s Publications Manager, responsible for the production and localization of LISA’s publications. A native of Alaska, he graduated Magna Cum Laude with a B.A. in linguistics from
Brigham Young University in Provo, Utah. He has worked with the localization industry since 1997. In
his spare time he collects and plays musical instruments from around the world. He speaks Hungarian
and German. He can be reached at arle@lisa.org.
Rebecca Ray is the Global Business Editor for the Globalization Insider. She began her international
software career in machine translation and terminology tools and has been a pioneer in designing, testing, adapting and marketing software globally for companies such as IBM, Netscape Communications,
Symantec and Sun Microsystems. She is a Summa Cum Laude graduate with an M.A. in Latin American Studies from Indiana University. She graduated Magna Cum Laude with a B.A. in Spanish, after
spending a year at the Universidad de Costa Rica on a Rotary Foundation Scholarship. She is ﬂuent in
English, French and Spanish and proﬁcient in Portuguese and Turkish. Rebecca is the co-author of the
book Doing Business in the USA: Marketing and Operations Strategies for Success. She can be reached at
rebecca@lisa.org.

LISA Best Practice Guide: Implementing Machine Translation

iii

Contents
Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

1

Understanding Machine Translation . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

3

1. What is Machine Translation? . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
2. Who Uses MT? . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
3. Will MT Replace Human Translators? . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
4. How Does MT Work? . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
Transfer-Based MT
Data-Driven MT
5. What Types of Text and What Languages Can MT Translate?. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

3
4
4
5

What Is Machine Translation Used For? . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

7

1. What Applications Can MT Enhance? . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
2. What Applications Can MT Enable? . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
MT for Information
MT for Dissemination
MT for Communication
Speech-to-Speech Applications
3. What Are the Similarities and Diﬀerences Between Human and Machine Translation? . . . . . . . .

7
8

10

Building a Business Case for Machine Translation . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

12

1. What Are the Direct Beneﬁts That MT Can Deliver? . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
2. What Are the Indirect Beneﬁts That MT Can Deliver? . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
3. What Are the Direct Costs of MT? . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
4. What Are the Indirect Costs of MT? . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
5. What Are the Costs of Human and Machine Translation at Various Translation Volumes? . . . . . .

12
13
14
15
16

Evaluating, Choosing and Customizing a Machine Translation System . . . . . . . . . . . . .

20

1. What Are the Guidelines for Evaluating MT Output? . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
2. What Are Common Sources of Error in Translation? . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
3. What Can I Expect From MT Output? . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
4. Is Evaluation Diﬀerent for Diﬀerent Applications? . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
5. On What Basis Should I Choose an MT System? . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
Author’s Use vs. Machine’s Knowledge of the Source Language
Language Support and Direction
Document Format Support
Dictionary Size
Standards for MT Data Exchange
Dictionary Tools
6. How Can I Customize MT to Meet My Needs? . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
Adapting Grammatical Rules
Customizing the Dictionary
7. How Can I Adapt My Processes to Make MT More Eﬀective? . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
Terminology Management
Sentence Structure

20
20
21
23
23

©2004 LISA and Mike Dillinger. All rights reserved.

6

27

27

iv

LISA Best Practice Guide: Implementing Machine Translation
Using MT . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

30

1. How Is MT Used in MT-Enabled Applications? . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
Integrating With Email, Chat, SMS
Integrating With Automatic Speech Recognition
Integrating With Text-to-Speech Systems
Integrating With Databases and Data Feeds
Integrating With Translation Memory Systems
2. How Is MT Used in MT-Enhanced Applications (Computer-Assisted Translation)? . . . . . . . . . . . . .
Workﬂow
Authoring
Translation Memory as a Filter
MT for Draft Translations
Post-Editing or Linguistic QA
Translation Memory as Storage for Reuse
Publication
Usability Testing
Technical Support
Next Steps

30

Additional Resources . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

38

Associations. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
Online Resources . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
On-Line Conference Proceedings
Articles from the Globalization Insider
Presentations from LISA Forums . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
Standards . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
Surveys . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
Technical Publications . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
Tools . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
Controlled Language / Style-Checking Tools
Linguistic QA Tools
Translation workﬂow systems

38
38

32

39
40
40
40
41

Appendix I. Types of MT Systems . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

42

Simple Dictionary-based MT . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
Transfer-based MT . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
Interlingual MT Systems . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
Data-driven MT . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
Hybrid Systems . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

42
42
43
44
44

Case Studies . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

47

CASE STUDY: MT Meets Instant Messaging (Transclick) . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
CASE STUDY: Machine Translation Makes Money (CLS Corporate Language Services) . . . . . . . . . . .
CASE STUDY: Machine Translation Fulﬁlls High Volume Demand (ESTeam) . . . . . . . . . . . . . . . . . . . . . .
CASE STUDY: MT for Speech-to-Speech Translation (Spoken Translation, Inc.) . . . . . . . . . . . . . . . . . . .

49
53
57
60

©2004 LISA and Mike Dillinger. All rights reserved.

LISA Best Practice Guide: Implementing Machine Translation

1

Introduction
Machine Translation (MT) is a powerful tool that that is very widely used in government, in industry
and by individual consumers. The core technology continues to evolve and improve, and innovative uses
for MT are constantly appearing. Its use is so pervasive that, in the last few years, it has surpassed human
translation: today, more words are translated per year using MT than are translated by human translators, and the demand continues to grow.
Although proposals for automated translation have existed since the Renaissance, modern MT’s roots
began in the 1950s with a joint project between Georgetown University and IBM. Although initial optimism faded in the wake of a 1966 report by a U.S. Government commission that found MT to be too
expensive, inaccurate and slow to warrant further funding, research and development continued in
Europe, Russia and Japan until picking up again in the U.S. in the late 1970s. Skyrocketing globalization
and the development of increasingly robust and powerful computers in the 1980s then paved the way for
a resurgence in MT usage. MT is now a critical component for meeting the language demands of the 21st
century, enabling applications that human translators cannot handle and enhancing their performance
in other settings.
This Guide will provide you with a basis for understanding MT, its uses, its limitations and how to implement it to meet your own needs. It is divided into the following sections, each of which contains a series
of questions and answers that will help you ﬁnd relevant content and answers to the questions that need
to be addressed when implementing MT:
•
•
•
•
•

Understanding Machine Translation
What Is Machine Translation Used For?
Building a Business Case for Machine Translation
Evaluating, Choosing and Customizing a Machine Translation System
Using Machine Translation

Together, these subjects will help you understand what MT can do for you, and how to implement MT
to meet your needs for multilingual content and communication. In addition to the sections listed above,
this Guide also contains the following additional resources:
• An appendix that describes the various types of MT systems available today
• Case studies that show how various organizations have implemented MT to meet their needs
• A list of Additional Resources that will allow you to explore the issues raised in this guide in greater
depth

©2004 LISA and Mike Dillinger. All rights reserved.

LISA Best Practice Guide: Implementing Machine Translation

Understanding Machine Translation
An understanding of what Machine Translation (MT) is—and what it is not—
will help you choose how best to apply MT and how to avoid common problems.
Ultimately, MT oﬀers the potential for (1) substantial time and cost savings during
the localization process and (2) the localization of materials that would otherwise
be impractical and/or cost-prohibitive.

1. What is Machine Translation?
Machine translation is a method for translating something from one language
to another automatically, without human intervention. Other technologies appear to do the same thing, but are really quite diﬀerent.
NOTE: When discussing translation, we often refer to the source language (the
language of the original text) and the target language (the language it will be
translated into), or source sentences and target sentences, to distinguish between
the languages.

Electronic bilingual dictionaries also oﬀer several diﬀerent translations for
words or expressions automatically so, in that sense, they also provide an automatic translation. Unfortunately, they don’t handle full sentences (except for a
few ﬁxed expressions), and they don’t help you choose which translation is the
appropriate one for a given situation. Experience shows that if they are used to
translate running text, the word-for-word translations are unintelligible.
Translation Memory products also oﬀer automatic translations for words, sentences or paragraphs, according to their similarity to a ﬁxed number of sentences that the system already has stored in memory. Humans have to ﬁll the system
with sentences and their translations in the ﬁrst place, so that when a sentence
is matched, the translation will be readable. Translation Memory products are
very useful for avoiding retranslation of the same sentence when it appears in
diﬀerent parts or diﬀerent versions of the same document or in diﬀerent documents. Unfortunately, people have a tendency to say the same things in diﬀerent ways, and Translation Memory products generally do not deal well with
varied input or with new sentences that have not been translated yet.
Machine translation systems automatically build a translation for any sentence
and are not restricted to a ﬁxed number of sentences stored in memory. MT
does not provide word-for-word translations: it processes the sentence context
to determine both word and sentence meanings. It is more ﬂexible than translation memory products and much better at dealing with new input. However,
because the knowledge of grammar and words in an MT system is more limited
than that of a human translator, the system makes more mistakes than human
translators, thus causing the output to be diﬃcult to understand at times.
©2004 LISA and Mike Dillinger. All rights reserved.

3

4

LISA Best Practice Guide: Implementing Machine Translation
Table 1 summarizes the strengths and weaknesses of the options discussed
above.
Strengths
Bilingual
•
Dictionaries

Easy to develop

Weaknesses

•
•

Translation •
Memory

•

Machine
•
Translation

•

Recycles existing
•
translations
Translations provided
from database usually require little or no
modiﬁcation
Can be used on new •
sentences
Extremely fast

Works with words, not sentences
Limited to translations of
words without regard to sentence context
Its ability to reuse translations depends on similarity to
existing content—it cannot
provide translations of new
content
More dependent on source
text quality than other solutions

Table 1. Comparison of the strengths and weaknesses of Bilingual Dictionaries,
Translation Memories, and Machine Translation as translation solutions.

2. Who Uses MT?
Individual consumers use commercial oﬀ-the-shelf machine translation packages and web-based translation services for gisting (just to get an idea of what
a foreign-language text is about) and for drafting their own texts in other languages. Each year in Japan, for example, millions of new computers are shipped
with an MT system as part of the bundled software.
• Government agencies use MT for gathering information published in
other languages.
• Translation agencies use MT to provide their translators with draft translations. They ﬁnd that this increases terminological consistency and makes
translation faster.
• Web portals use MT to oﬀer on-the-ﬂy translations of foreign-language
web sites and messages.
• Companies that deal with multilingual markets and workforces use MT
for corporate communication, user documentation, technical support and
sales support in foreign-language markets.

3. Will MT Replace Human Translators?
No. MT systems are deployed either as tools to help human translators work
more eﬃciently or as a “good-enough” solution in situations where human
translators are not or cannot be used.
©2004 LISA and Mike Dillinger. All rights reserved.

LISA Best Practice Guide: Implementing Machine Translation
For example, in many settings where monolingual users have access to MT, they
use it to choose texts to be sent for human translation. In this sense, machine
translation often increases the demand for human translation.
In addition, on-demand translation supplied by MT is now creating the expectation and demand that content be available in all users’ languages, thus creating new opportunities for both human translators and machine translation to
meet this demand. (Please refer to the following Case Studies for examples: MT
Meets Instant Messaging (Transclick) on page 49 and MT for Speech-to-Speech
Translation (STI) on page 60.)

4. How Does MT Work?
Unlike bilingual dictionaries and translation memory products, MT systems
use artiﬁcial intelligence to carry out very sophisticated analysis of the source
sentences to build as good a translation as possible for each. Described below
are two models that are currently in use.

Transfer-Based MT
One approach is to have linguists build grammar rules that the system uses to
(1) analyze source language sentences, (2) map grammatical structures to target
language grammar and (2) generate target language sentences. These grammar
rules are time-consuming and expensive to develop and debug, and as a result,
sentence patterns are usually not analyzed correctly when the rules have not yet
been developed. The rules also access detailed information about the words in
the system’s dictionary. This dictionary information is also time-consuming to
compile, so MT vendors often develop additional dictionaries on demand for
their clients. Sentence structures and terminology that are missing from the
system are key determinants of the quality of translation output.
This approach to MT is very knowledge-intensive, so a rule-based MT system
for a new language can take up to two years to develop. Almost all commercial
MT systems are of this type.

Data-Driven MT
Another approach is to compile a large number of example translations and
then employ statistical methods to compute which pieces of each source sentence go with which pieces of each target sentence. Since the pieces can range
from single words to expressions to whole sentences, the system builds the dictionary and translation correspondences automatically. Gathering the data and
verifying that it provides good coverage of diﬀerent sentence types is time-consuming, and a key determinant of the quality of the translation output.
This approach is very data-intensive, so this type of MT system may only take
a few weeks to develop for a new language, assuming that the data is available.
Presently, only a few commercial MT systems are of this type.
©2004 LISA and Mike Dillinger. All rights reserved.

5

6

LISA Best Practice Guide: Implementing Machine Translation
(For more details on how the two models work, please refer to Appendix I: How
Machine Translation Works on page 42.)

5. What Types of Text and What Languages Can MT
Translate?
By itself, MT can translate ﬁles that contain text in computer-readable format.
Examples of such ﬁles are plain text ﬁles (or text typed into an MT application’s
user interface), HTML ﬁles, Microsoft Word ﬁles, etc. In general all ﬁles (except
for plain text ﬁles) must be converted to plain text via a ﬁlter that separates text
from presentational markup (such as bold, italics, fonts, etc.) that is not part of
the text per se.
MT can translate speech or printed matter if it is ﬁrst converted to an electronic
format using other tools, such as optical character recognition or speech recognition. (For an example of such an integration, please see the Case Study, MT
for Speech-to-Speech Translation (STI) on page 60.)
MT systems are expensive and diﬃcult to develop, so only a handful of the
world’s languages have been implemented. The languages currently available are
generally ones of particular economic or strategic importance. Lesser-known
languages will likely not be available in commercial MT systems, although local
academic projects may cover them.
Just as a human translator cannot handle any arbitrary combination of languages, MT systems can only be used for a speciﬁc set of languages. They are typically
sold for speciﬁc language pairs, such as French → German or Russian ↔ English. (→ indicates that an MT system can translate from one language to another, but not the other way around, while ↔ indicates that translation can go
either direction between the two languages. The example given here means that
the MT system can translate from French into German, but not German into
French, and from Russian into English and English into Russian.)
Building MT systems is expensive and diﬃcult, so systems for only a few dozen
of the world’s languages have been implemented. The languages currently available are generally ones of particular economic or strategic importance. Lesserknown languages will likely not be available in commercial MT systems any
time soon, although local academic projects may cover them.

©2004 LISA and Mike Dillinger. All rights reserved.

LISA Best Practice Guide: Implementing Machine Translation

What Is Machine Translation Used For?
Understanding what MT can be used for, and how it relates to other translation
processes, will help you understand the problems that MT can solve and how different scenarios can impact MT use and deployment. Like any tool, MT performs
best under those conditions for which it has been designed, so understanding those
uses will aid in successful MT deployments.
MT applications can be divided into two broad categories: applications enhanced
by MT and applications enabled by MT (and which would not exist without
MT). In addition, understanding the diﬀerences between human and machine
translation will help you select the appropriate type of translation for a given situation. Please refer to the Case Studies at the end of this Guide for speciﬁc examples
of MT deployments.

1. What Applications Can MT Enhance?
MT can be used to decrease the cost and to increase the eﬃciency of human
translation. It can assist translators with routine translations, thus allowing
them to focus on documents or parts of documents that require their unique
skills and expertise. This use of machine translation, sometimes along with other tools to help human translators, is often called Computer-Aided Translation.
MT is often used for dissemination of source language information. In this
model, a source language document is translated into one or more target languages so that the source language information is available to readers of the
target languages. This model most closely resembles a traditional localization
process that uses human translators. MT in this case speeds up the localization
process by providing a draft translation for human translators to edit, rather
than create from scratch. It saves translators time in researching and checking
terminology and improves the terminological consistency of the ﬁnal text.
An example of this process is one in which a company uses MT to translate a
service bulletin from English into German, French and Italian. In this model,
translators are users of the MT system, but the information consumers do not
interact with it.
As machine translation output improves, human translators can work faster.
The most successful deployments of MT in computer-aided translation rely
on systematic terminology management (so that the MT system has all of the
terms that it needs), standardized authoring styles (to avoid grammatical structures that the MT system cannot process) and translation memory (to reuse for
revised translations). (See Using MT on page 30 for more details.)

©2004 LISA and Mike Dillinger. All rights reserved.

7

8

LISA Best Practice Guide: Implementing Machine Translation

2. What Applications Can MT Enable?
MT enables new types of translation possible that would either not be possible
for human translators, or which would be prohibitively time-consuming or expensive with human translators. These uses include the following:

MT for Information
MT is often used to gather information from foreign-language documents. In
this case, MT is used to fulﬁll an individual or corporate need for information
in situations where the content creators do not provide a translation. Two common applications include:
• Gisting. Use of MT to gather a rough idea of the information content of
foreign-language texts is often referred to as gisting. In gisting, users do not
expect a perfect translation. It is often used to locate information to decide
whether or not to have a human translator provide a publication-quality
translation. In terms of volume, MT gisting is the most common form of
translation in the world today, with on-line services providing a translation volume far in excess of that provided by human translators.
• Intelligence gathering. Intelligence gathering (either by governments or
by the private sector) is as a special kind of gisting with MT. One key difference is that intelligence gathering often adds more software between
the MT system and the human user that searches machine-translated data
for relevant information automatically. Due to the extremely high volume
of information of potential interest, and the need to automatically process
the data with little delay, intelligence gathering uses MT to help identify
what information to focus on for further analysis.

MT for Dissemination
MT is also used to deliver information that is generated in one language to
speakers of other languages. This is the case of traditional localization processes and computer-aided translation. MT enables other forms of high-volume
translation that are particularly suitable for routine, recurrent publication.
MT can rapidly provide translations of new data or data presented in new
combinations from databases or data feeds. Human translators cannot provide
translation of content produced dynamically from databases in real time—even
if delays for translation are acceptable, the cost to provide such translation using humans is prohibitive for high-volume scenarios. MT can handle such tasks
very well since data structures of dynamic data are known in advance, and MT
systems can be reliably “tuned” to the sentence structures that will be generated. (Please see the Case Study, MT Fulﬁlls High Volume Demand (ESTeam),
on page 57.)
Data-driven information often has a short “shelf life” (i.e., its value decreases
very rapidly) and is a prime candidate for MT because of the (comparatively)
high turnaround time for human translation. Stock prices, weather, and other
©2004 LISA and Mike Dillinger. All rights reserved.

LISA Best Practice Guide: Implementing Machine Translation
ﬁnancial information are good candidates for this application. A prime example
of this is the Canadian government’s MÉTÉO system, which has provided automated translations of weather bulletins from English into French since 1977.

MT for Communication
E-mail and person-to-person communication applications such as chat, IM
(instant messaging) and SMS (Short Message Service) require fast turnaround,
high-volume capacity, bi-directional translation, and always-on capability. An
MT server can reliably deliver rapid translation with minimal lag and no downtime, an especially important concern for globally deployed systems with users
in multiple time zones.
Systems designed for rapid communication often are used to convey proprietary or conﬁdential information. Security and privacy issues make the use
of a secure translation server a compelling proposition when compared with
human translators and the inherent security problems that can arise through
introduction of third parties to a conﬁdential communication.
Use of MT in interpersonal communication scenarios can deliver signiﬁcant
beneﬁts to corporate users. It is estimated that competent non-native speakers of a language take between 25 and 50% longer to read a message in their
second language than it does to read it in their native language, and writing
messages may take 100–200% longer in their second language. If a user may
reasonably be expected to spend 25% of his or her time reading or responding
to email, MT oﬀers a clear path to higher productivity. MT works well in these
situations, can be incorporated into the communications infrastructure and is
always available to users.

Speech-to-Speech Applications
When coupled with speech recognition and text-to-speech systems, MT can
provide access to on-demand interpretation services in situations like hotel or
hospital admissions, information kiosks, refugee camps, and other environments where it would be impossible or impractical to keep qualiﬁed interpreters on call. MT in such cases replaces human interpreters for routine communication, and allows them to focus on mission-critical tasks. (See the Case Study,
MT for Speech-to-Speech Translation (STI), on page 60.)
NOTE: For details on how one customer integrated MT to solve its communication
breakdowns with the Chinese market and to increase its sales worldwide, please refer
to the Case Study, MT Meets Instant Messaging (Transclick), on page 49.

©2004 LISA and Mike Dillinger. All rights reserved.

9

10

LISA Best Practice Guide: Implementing Machine Translation

3. What Are the Similarities and Diﬀerences Between
Human and Machine Translation?
Machine translation and human translation are very similar in many respects
(see Table 2). Most translators translate source texts written in a second language, i.e., not their native language, so their knowledge of that language is
often more limited than the knowledge of the authors, who are writing in their
native languages. Authors, too, often try to write “interesting” or “accurate,”
rather than “translatable,” prose. Translators also generally know much less
about the domain or topic than the authors.
The diﬀerence between writer and “translator” is even greater for machine
translation systems. This mismatch in knowledge makes both human and machine translation very sensitive to unknown vocabulary, ambiguous sentence
structure and unusual style in the input texts. It is not uncommon for this mismatch to produce misinterpretations and incorrect translations. As a result,
both human and machine translations undergo post-editing before publishing.
It is important to note that MT systems are particularly sensitive to problems
in source language text such as spelling and grammatical errors that humans
may be able to more easily compensate for, although such issues aﬀect human
translators and can decrease their productivity substantially as well. This makes
high-quality authoring especially critical for MT applications.
MT’s distinct advantages over human translators are speed, price, consistency,
availability and scalability. Human translators have an advantage for texts that
require an artistic touch, exceptional precision or complexity, or that deal with
subjects that are not covered in MT dictionaries (but are familiar to the translator).
Table 2 summarizes the similarities and diﬀerences between MT systems and
human translators.
Machine Translation System
Speed

Accuracy

Price

Human Translator

At about 4,800 pages per day, Limited to about 10 pages per
MT can easily produce hun- day, depending on text type,
dreds of thousands of words complexity and domain. Realper day. Real-time translation time translation is possible only
possible.
with interpreters.
Tuned systems working on
Depends on the skill of the
limited domains are very
translator, but generally quite
good. Unfamiliar domains,
high. Unfamiliar domains, vovocabulary or writing styles cabulary or writing styles will
decrease accuracy.
will decrease accuracy.
Incremental cost per word
Direct costs of $0.10–$0.30 per
below $0.01/word
word depending on language

©2004 LISA and Mike Dillinger. All rights reserved.

LISA Best Practice Guide: Implementing Machine Translation
Machine Translation System
Human Translator
Consistency Very good. MT systems are
Can be very good with transla-

very consistent, even in their
mistakes.
Highly suited to machine
translation.

tion memory and terminology
management tools.
Repetitive
Generally not suitable for huTexts (e.g.,
man translation due to tedium
data-driven)
and fatigue potential.
Scalability
Can be rapidly scaled to
Scaling up requires additional
accommodate surges in de- translators, training and manmand.
agers.
Availability Always on
May not always be available.
Quality
Variable, but generally not as Variable, but generally very
good as human translation. good. Editing usually focuses
Editing focuses on errors of on errors of content and congrammar and interpretation. sistency, not on correction of
grammar.
Text Types
Best suited to technical texts Requires training for speciﬁc
in focused subjects or dosubject ﬁelds. Specialized transmains, rather than general
lators can translate legal or litlanguage, legal or literary
erary texts.
texts.
Table 2. Comparison of the characteristics of Machine Translation systems
and human translators.

©2004 LISA and Mike Dillinger. All rights reserved.

11

12

LISA Best Practice Guide: Implementing Machine Translation

Building a Business Case for Machine Translation
Machine translation oﬀers substantial cost and time savings over translation done
entirely by humans. Building a business case for MT relies on an understanding
of your needs, the suitability of various solutions to meet those needs and the costs
associated with those options. It is important to consider not only the direct costs
of buying software or services, but also indirect costs such as training, implementing process changes, technology integration, ongoing maintenance costs, etc. At
the same time, the substantial indirect beneﬁts that MT can oﬀer will also play an
important role in your business decision.
Experience has shown that the lower cost of MT is often a factor leading to increased investment in localization and all forms of translation. In many cases, MT
implementation makes localization a much more cost-eﬀective strategy for organizations looking for ways to increase sales without increasing internal spending.

1. What Are the Direct Beneﬁts That MT Can Deliver?
MT’s direct cost beneﬁts are generally realized in these areas:
1. Reduced Translation Costs. With suﬃcient translation volume, MT
translation is much less expensive than human translation. The incremental cost per word translated by MT can be below $0.01/word, compared
to $0.10–$0.30/word for human translation, depending on the languages
involved so MT can oﬀer signiﬁcant savings over human-only translation,
even when the cost of human translators to review or post-edit the MT
output is added.
2. Improved Delivery Times. Delivery time for machine-generated translations is limited only by the time it takes to revise them. In many applications, revision is not critical, so delivery is immediate.
To take one example, an on-demand translation service in a 24-hour environment requires a minimum of three human translators per language
pair to cover all shifts. However, this may not cover peak demand, and the
service will be overstaﬀed for much of the time when demand is low. Unless translated information has exceptional value, it is hard to justify this
kind of service with human translators. MT provides a viable alternative
that scales up easily to cover peak demand and that requires little overhead
when demand is low.
In business applications where time-critical information is needed,
waiting for human translators may substantially decrease the value of the
to-be-translated information, or even render it worthless. Moreover, rapid
translation by humans is a premium service that is often two to three times
as expensive as general human translation. MT oﬀers a much faster, lowercost alternative.
3. Availability. MT systems have the advantage of being always on, meaning
that requests can be processed as they are received. Users do not need to
©2004 LISA and Mike Dillinger. All rights reserved.

LISA Best Practice Guide: Implementing Machine Translation
hold up projects while waiting for human translators to turn critical components around.
4. Consistency. MT systems generally use terminology more consistently
than human translators, who need additional training, tools and revision
to ensure terminological consistency.
5. Throughput. For large translation projects such as multinational contract
bidding, the administrative overhead of (1) locating translators, (2) distributing jobs, (3) collecting, collating and checking translations and (4)
reviewing for terminological consistency, makes the process more complex, slower and more risk-prone—often to a point where the project is no
longer even viable, much less cost-eﬀective. MT scales much more easily
and makes large-scale projects much simpler and more cost-eﬀective to
execute.
MT’s direct beneﬁts can be very compelling, oﬀering multilingual content at a
fraction of the cost it would take to provide it through other means, particularly as the size and complexity of translation projects increase. With MT, the
cost of delivering multilingual content decreases, so demand for content rises,
allowing organizations to increase the total content available, while leveraging
limited resources.

2. What Are the Indirect Beneﬁts That MT Can Deliver?
In addition to direct savings in translation costs and improved delivery times,
MT can deliver signiﬁcant secondary cost savings. Because MT is an enabler to
greater translation volume, it makes it possible to provide greater volumes of localized content. Greater availability of localized material can deliver the following
beneﬁts:
• Reduced Support Costs. By increasing the amount of information available
to international end-users, MT helps increase self-service customer support.
This reduces the number of service calls that arise when users cannot answer
questions on their own. A single support call will often cost an organization
US $30 or more in employee time and infrastructure, so reductions in the
number of support calls can greatly increase proﬁtability. Greater levels of
localization enabled through MT can thus have a direct impact on the profitability of international product sales.
• Improved Documentation. Implementing MT is often an occasion to review existing documentation and to re-evaluate style guides and terminology use in order to make the documentation more consistent, more readable and thus more translatable. Besides the obvious bonus of enabling
higher-quality documentation, this process usually ends up eliminating
repetitive and unnecessary portions of the documentation—with direct
reductions in the total cost of translation.

©2004 LISA and Mike Dillinger. All rights reserved.

13

14

LISA Best Practice Guide: Implementing Machine Translation
• Faster Time to Market. By shortening delivery time for localized documentation, time to market can be greatly reduced. This can be crucial in a
ﬁrst-to-market situation and is often important for gaining market share.
• Increased Product/Brand Loyalty. Most companies do not maintain support staﬀ ﬂuent in all potential customer languages, so provision of selfhelp material can help promote customer loyalty and retention. If customers are unable to use products due to language barriers, they will express
high levels of dissatisfaction and will be unlikely to buy or recommend
those products. MT services can eliminate many problems, and when
problems do arise, MT can be a facilitator for person-to-person communication with support staﬀ who do not know the customer’s language, but
who nonetheless can assist the customer. MT can thus directly aﬀect repeat sales in international markets.

3. What Are the Direct Costs of MT?
The most obvious cost associated with MT is the cost of software and/or services. MT systems can be sold as a shrink-wrapped product (typical for personaluse systems), or as software installed and maintained on one or more servers at
the client’s site. They are generally sold by language pair (either unidirectional
or bi-directional), and may be priced per user or CPU, or by number of servers.
Some MT solutions providers also have hosted solutions that are sold on variable pricing plans. Implementation costs and ROI (return on investment) are
discussed in more detail below.
NOTE: See John Hutchins’ Compendium of Translation Software,
http://www.eamt.org/compendium.html, for a list of MT solution providers and their
products.

MT providers may oﬀer a number of diﬀerent options for service, and selection
of an appropriate model depends on knowledge of your translation volume
and needs, both now and in the future. When you talk to potential technology
providers, you need to know how much translation you are likely to require
over the course of a typical contract period and which languages the process
will need to support. A model that assumes a translation volume of 1,000,000
words/year into two languages may not be the same as one for a translation
process that handles 10,000,000 words/year into sixteen languages.
Enterprise MT systems may also involve a one-time installation fee that covers
the vendor’s cost in setting up the system for a speciﬁc client and making sure
that it works in that client’s environment. In addition to the cost of purchasing
a license or installation, maintenance must be considered. Maintenance contracts typically run about 15% of the cost of a new system per year, and will
usually include all updates, as well as technical support.

©2004 LISA and Mike Dillinger. All rights reserved.

LISA Best Practice Guide: Implementing Machine Translation
After the initial investment, there will be a cost associated with customizing the
system for the client’s speciﬁc needs. Customization of the system deals with
the following items:
• Dictionary Development. MT systems come standard with a basic dictionary for the language pairs covered, but this basic dictionary will not reﬂect
company- or industry-speciﬁc terminology that is critical to quality translation. Investing in such terminology greatly increases the value of an MT
system and can help improve accuracy and usability of translated text.
Because MT systems need to know not only what term to use, but also
certain grammatical and morphological information about the term, dictionary development and maintenance may require the expertise of trained
linguists. When evaluating systems, you should ﬁnd out how much dictionary development is included in the initial customization package and
what tools are available for on-going dictionary maintenance and development. Terminology extraction and glossary import tools are particularly
important for post-sale improvements to the dictionaries.
• Additional Features. MT systems can be conﬁgured in diﬀerent ways, and
additional features beyond the standard conﬁguration will require more
investment. For example, your installation may require an additional component to interface with an Exchange mail server. Custom ﬁle ﬁlters (for
dealing with diﬀerent document types), and interfaces with additional linguistic tools and/or content management systems may also represent additional costs. For example, if a systematic link between translation memory
and MT is desired, an interface can be developed to enable the MT tools
to access the latest translation memory data and/or vice-versa.
In most cases, you will be asked to supply a collection of sample texts and translations, ﬁrst during the pre-sales phase and then for customization. It is extremely important to take this seriously. Evaluation of system performance is
impossible without ﬁrst adapting the MT system to your speciﬁc texts. The bigger the collection of sample texts, the better: a bigger collection makes it easier
to customize the MT system with representative data. If no such collection is
readily available (for example, in a translation memory ﬁle), there will be cost
and time associated with developing it. However, this investment will allow you
to avoid the mistake of deploying a system that will not meet your needs.
In addition, operational costs to consider include (1) training users, post-editors and IT employees, (2) post-editing or reviewing text (generally higher than
for reviewing human-translated text), (3) IT maintenance and (4) any on-going
dictionary development.

4. What Are the Indirect Costs of MT?
Successful deployment of MT requires a well-deﬁned documentation workﬂow.
In the past, ill-informed managers often tried to replace translators through
©2004 LISA and Mike Dillinger. All rights reserved.

15

16

LISA Best Practice Guide: Implementing Machine Translation
overlaying MT on an unstructured documentation process. The disastrous results of these poorly planned eﬀorts gave MT an ill-deserved bad reputation.
The most crucial factor for successful deployment of MT is usually high-quality source documentation. Therefore, improving the source documentation and
structuring the content management workﬂow can be seen as indirect costs of
MT when an MT deployment is the trigger for reassessing them. Unfortunately,
technical documentation is generally not as clear and simple as it should be. In
many organizations, this means that eﬀective deployment of MT will entail additional costs associated with retraining authors and deploying tools for terminology management and style checking. The upside is that these eﬀorts will produce
an excellent ROI, regardless of whether MT is involved or not
This is not only a requirement for MT. As previously explained, human translators are usually non-native speakers whose command of the source language and
of the subject matter is often much more limited than the author’s. This mismatch
between the author’s knowledge and the translator’s knowledge makes translation slower, more error-prone and more expensive, because translators have diﬃculty understanding the original documents and make more mistakes. The same
is also true for the mismatch between the author’s knowledge and the end user’s
knowledge: more diﬃcult or confusing documentation leads to escalating support costs, no matter what the language.
Fortunately, the same investment required to make source documentation
easier to read for end-users and easier to translate, also makes it easier to read
and understand for end users, i.e., (1) the consistent use of terminology, (2) a
limited range of simple sentence structures, (3) the careful use of pronouns, etc.
Terminology management plays an important role here. When authors keep
track of the terminology they use and stick to terminological norms, source
documentation is more consistent. Moreover, providing the terminology database to the translators is a big help, saving them many hours of research and
giving them a much clearer idea of the author’s intentions. Similarly, corporate
style guides and style checking tools enable authors to stick to a clear, simple
style that can be easily understood by end-users and translators alike. The issues here are more complex, however, and a good consultant’s eﬀorts will pay
for themselves many times over.
NOTE: Please refer to the Additional Resources section on page 38 for more information on terminology management and controlled authoring.

5. What Are the Costs of Human and Machine
Translation at Various Translation Volumes?
It is diﬃcult to provide a precise answer to this question because the answer depends on many factors. However, the costs of human translators tend to rise lin©2004 LISA and Mike Dillinger. All rights reserved.

LISA Best Practice Guide: Implementing Machine Translation

17

early with increases in volume. In general, doubling translation volume with human translators will result in approximately doubled translation costs. At $.10 per
word, 100,000 words will cost $10,000 and 200,000 words will cost $20,000.
NOTE: The situation is diﬀerent with revised or previously translated texts, which can
be dealt with very eﬀectively using translation memory systems. We are focusing here
on the volume of new text for translation.

In contrast to human translation, MT systems run at an approximately ﬁxed
cost, independently of volume. After a ﬁxed initial investment for customizing and installing the MT system, there are few operating costs, so in general,
the total cost of ownership per word decreases as more and more words are
translated. Table 3 shows a detailed scenario in which 1,000,000 words of documentation are translated into ﬁve languages. There are MT-speciﬁc costs associated with initial deployment of the MT system (license, customization for
ﬁve languages), for maintenance (annual fee to the MT vendor and for IT staﬀ
to maintain the server) and revision (which is usually included in the standard
price for human translation). These costs are still less than the cost of human
translation, and upkeep of the MT system in subsequent years proves to be far
less than continuing to translate without it.
Human
Translation,
5 Languages
(low rate)

Human
Translation,
5 Languages
(high rate)

MT,
5 Languages
(ﬁrst year)

1 Server License

$ 63,000

MT,
5 Languages
(subsequent
years)

Customization

$ 75,000

Annual Fee

$ 9,450

$ 9,450

Maintenance:
10% of 1
Webmaster

$ 7,000

$ 7,000

$ 250,000

$ 250,000

$ 100,000

$ 100,000

$ 250,000

$ 250,000

Translation
Price (per word)

$ 0.10

$ 0.30

Translation
Cost (1,000,000
words)

$ 500,000

$ 1,500,000

5 In-House
Localization
Managers

Revision (500
words per hour)
Delivery Time
(person-days)
Total Cost

400

400

250

250

$ 750,000

$ 1,750,000

$ 504,450

$ 366,450

Table 3. Cost breakdown for translation of 1,000,000 words of documentation into five languages. Figures for human translation are $.10 and $.30 per
©2004 LISA and Mike Dillinger. All rights reserved.

LISA Best Practice Guide: Implementing Machine Translation

18

word to cover the usual range of prices. The figures for machine translation
show the initial investment during the first year and subsequent yearly costs.
There is no additional translation cost for MT beyond deploying and maintaining the system, but there is an additional cost for revision or post-editing
(assumed here to proceed at only two pages per hour on average). All prices
are in USD.

Figures 1 and 2 illustrate the same conditions more generally. Human translation costs rise sharply as a function of the volume of translation, while machine
translation costs rise much more slowly.
����������
����������
������
����������������
�������������

����������

����������
������
��������
��������������

���
��
�
��

����������

��������
��������

�

����

�
��

��

��������

���
����������

�
����������

��
��������

��������
��

��

���

�
���
���

�

�������

�������

�������

���������

�����������������������������������
Figure 1. Costs of MT and human translation, as a function of translation volume. (Note that this example assumes one localization manager at $50,000
per year.) All prices are in USD.

To summarize, human translators will be cheaper than machine translation at
low translation volumes since MT systems have a ﬁxed cost for implementation.
As soon as human translation costs exceed the cost of installing an MT system,
however, MT can be considered a cost-saving technology, taking into account
all of the factors discussed above. In the ﬁve-language scenario used here, MT
will not generally deliver positive ROI in the ﬁrst year for translation volumes
below roughly 200,000 words per year. However, in subsequent years or as
volumes increase above this threshold, MT can deliver signiﬁcant cost savings.
The precise value of this break-even point will vary according to the diﬀerent
parameters in Table 3. For example, if the source documents and/or the dictionary customization are better than average, then revision will go faster and
the breakeven point will be reached with smaller document sets. Finally, the
payback period is the time it takes to install and customize the MT system plus
the time needed to produce and revise 200,000 new words for translation, i.e.,
©2004 LISA and Mike Dillinger. All rights reserved.

LISA Best Practice Guide: Implementing Machine Translation
less than a year in this scenario. When average costs are considered over multiple years (Table 4), MT’s price advantages become even clearer.
���

��������������������

���

�����������������
�������������
���������������������

���
����������
������
����������������
�������������

���

��

�

�������

����������
������
��������
��������������

�������

�������

���������

�����������������������������������
Figure 2. Price per word of MT and human translation, as a function of
translation volume, corresponding to Figure 1 (assuming one localization
manager). All prices are in USD.

Year 1

Year 2

Year 3

Year 4

Avg. cost/
year

Human
(low rate)

$750,000

$1,500,000

$2,250,000

$3,000,000

$750,000

Human
(high rate)

$1,750,000

$3,500,001

$5,250,001

$7,000,001

$1,750,000

$604,450

$1,070,900

$1,537,350

$2,003,800 ☞ $500,950

MT

Table 4. Cumulative cost of translating 1,000,000 words per year into five
languages, over four years, with each year calculated as in Table 1. The first
scenario (low rate) assumes a translation rate of $.10 per word. The second
(high rate) assumes a translation rate of $.30 per word. The last column
shows the average cost per year for the four-year period.

©2004 LISA and Mike Dillinger. All rights reserved.

19

20

LISA Best Practice Guide: Implementing Machine Translation

Evaluating, Choosing and Customizing a Machine
Translation System
Selecting a Machine Translation system can be compared to selecting a complex
industrial tool, such as a robot assembler. Such devices will not be truly eﬀective
outside of their proper setting and workﬂow. For example, a robotic arm will not
function properly without a hydraulic system, and evaluating it without that critical component in place will provide no indication as to how it will function with it.
MT systems are very similar in this regard, and should be thought of as industrial
tools that must be customized to meet particular needs and deployed as such.

1. What Are the Guidelines for Evaluating MT Output?
Unfortunately, there are no standardized measures of translation quality or rating systems for human translators or MT systems. Moreover, evaluation is very
subjective and variable: end users, translators, and MT developers will make very
diﬀerent assessments of translations of the same document. Speakers of diﬀerent languages, too, have diﬀering levels of tolerance for errors in translation: in
general, the less they need translation (because they know the source language),
the less tolerant they are of errors in translation (see Business Users Speak Out
on the Value of Pure Machine Translation at http://www.roi-learning.com/dvm/
pubs/articles/tatc-24/). So, if we ask three people about the quality of translation output, we are likely to receive four or more opinions!
Asking which MT system is better than another simply does not lead to useful results. A better approach is to identify which systems meet your needs in
terms of languages, document formats, etc. (see On what basis should I choose
an MT system? on page 23). Then evaluate how much work will be required
to adapt the candidate MT systems and your own documents and workﬂow
processes to implement the best solution. That means commercial users cannot
evaluate an MT system “out of the box” or on a web site—they have to run a
trial installation with some customization.

2. What Are Common Sources of Error in Translation?
Both human translators and MT systems inevitably make errors. One practical
way to think about translation quality is in terms of the source of errors and
how they can be avoided. Experience shows that it is much more cost-eﬀective
to prevent errors, rather than to ﬁx them after the fact.
As discussed previously, source documents are written by humans with wildly
diﬀerent knowledge of diﬀerent topics and of the languages they use. For example, in the case of product documentation, the authors are usually highly
trained experts with extensive knowledge of the products in question and the
language in which they are writing. They are hired because of that knowledge.
Translators, on the other hand, usually know much less about the products and
©2004 LISA and Mike Dillinger. All rights reserved.

LISA Best Practice Guide: Implementing Machine Translation
the author’s native language (which is frequently the translator’s second or third
language). Similarly, the product knowledge of MT systems is limited to the
product-speciﬁc vocabulary in their dictionaries, while their knowledge of the
author’s native language is limited to what the system developers had time and
funding to implement. The end users of the product documentation also have
less knowledge of the product (by deﬁnition) and less knowledge of the author’s
language, since they are the ones who require the translation in the ﬁrst place.
These mismatches, or disparities in knowledge and expectations, are the root
causes of many translation problems, although the translation phase receives
most of the blame. Of course, there are additional errors introduced by forgetful authors, confused translators and incomplete MT systems, but the key is
clearly to synchronize the authoring and translation phases.
Errors in translation output, then, are symptomatic of problems that exist
throughout the entire content management process. MT systems are simply
more sensitive to these issues so these problems become more obvious when
MT is deployed.

3. What Can I Expect From MT Output?
You should expect MT output to be a surprising mix of perfect translations,
good translations with a strange choice of word here and there, funny mistakes
and garbled sentences. The proportion can change quite a bit from one text
to another, depending on how well the text matches the MT system’s current
capabilities. Some translators can compensate for unclear writing and unusual
topics, but MT systems can actually make unclear writing look worse. Clear,
simple input, on the other hand, most often leads to clear, simple translations.
Tables 5 and 6 provide two examples to show the eﬀects of writing style on
translation output. (Translations by Word Magic Software’s ESI system.)
In the ﬁrst (Spanish) sentence (labeled Original) in Table 5, there was a typing
error: está was typed without the accent. The sentence is also very long and
complex. The translation (Original Translation) is diﬃcult to understand. In
the revised original, the accent was added, and the original was split into two
sentences. The second translation is very good. We can still see that su/his was
too unclear for the MT system (and probably for many humans, too) to render
correctly (it can mean his/her/its). In addition, the wrong sense for direcciones
(it can mean addresses or directions) was chosen. Generally, however, the translation is very readable.

©2004 LISA and Mike Dillinger. All rights reserved.

21

LISA Best Practice Guide: Implementing Machine Translation
Source

Translation

Original

Una computadora esta formada por
dos componentes estructurales con el
mismo nivel de importancia: el equipo físico (hardware) y los programas
con los que funciona (software), lo
cual signiﬁca que su grande avance
debe considerarse en esas dos direcciones

A computer this formed by two structural components with the same level
of importance: The hardware (hardware) and the programs that it works
with (software), that which signiﬁes
with that his grand advance must be
considered in those two addresses.

Revised original

22

Una computadora está formada por
dos componentes estructurales con el
mismo nivel de importancia: el equipo físico (hardware) y los programas
con los que funciona (software). Por
lo tanto, su grande avance debe considerarse en esas dos direcciones

A computer is composed of two structural components with the same level
of importance: The hardware (hardware) and the programs that it works
with (software). Therefore, his grand
advance must be considered in those
two addresses.

Table 5. Examples of Spanish � English MT output, before and after revision
of the source sentences.

Revised original

Original

In the second sample, below, MT is translated as Montana. This is correct, but
inappropriate for the speciﬁc topic of computers. Again the original sentence
is long. When the abbreviation is spelled out and the sentence split in two, the
translation is much better.
Source

Translation

Similarly, MT systems have knowledge of the same products that is
limited to any vocabulary in their
dictionaries and knowledge of the
author’s native language that is limited to what the system developers had
time and funding to implement

De modo semejante, los sistemas de
Montana tienen conocimiento de los
mismos productos que es limitado a
cualquier vocabulario en sus diccionarios y el conocimiento de lengua
materna del autor que es limitada a
lo que los desarrolladores de sistema
tuvieron el tiempo y ﬁnanciar para
implementar.

Similarly, machine translation systems have knowledge of the same
products which is limited to the vocabulary in their dictionaries. They
have knowledge of the author’s native
language as well, but it is limited to
what the system developers had time
and money to implement.

De modo semejante, los sistemas de
traducción por máquina tienen conocimiento de los mismos productos
que es limitado al vocabulario en sus
diccionarios. Tienen conocimiento de
lengua materna del autor bien, pero es
limitado a lo que los desarrolladores
de sistema tuvieron tiempo y dinero
para implementar.

Table 6. Examples of English → Spanish MT output, before and after revision
of the source sentences.

©2004 LISA and Mike Dillinger. All rights reserved.

LISA Best Practice Guide: Implementing Machine Translation
These examples are provided to show that clear, simple writing leads to good (if
somewhat imperfect) translations.

4. Is Evaluation Diﬀerent for Diﬀerent Applications?
Yes. Evaluation of a candidate MT system varies according to whether it is possible to control or revise the source documents that are being translated.
For translation of chat, email, web pages and other applications in which there
is no control over the source documents, all improvements in quality depend
on improvements to the MT system. Most enterprise-grade MT systems have
similar linguistic performance for these applications, so evaluation will be
based on the availability of language pairs, price and ease of integration.
For translation of technical documentation, product information, etc.—applications in which the production of source documents can be altered—the
improvements in quality depend on both improvements to the MT system and
enhancements to the authoring process. In this case, the emphasis in evaluation
will be on (1) the eﬀectiveness of the dictionary customization tools (terminology extraction, glossary import, etc.), (2) the level of detail in the style guide
produced by the MT vendor, (3) the size of existing domain-speciﬁc dictionaries and (4) the amount of customization available from the vendor at a particular price.

5. On What Basis Should I Choose an MT System?
If you are a single user who will spend no time adapting the system, you can
evaluate an MT system by selecting a text at random and running it through
the system. You will not get a good idea of what the system can and cannot
do, but it really doesn’t matter for your limited needs. You just have to decide
whether the rough translation is good enough for occasional use. The casual
user sacriﬁces quality for convenience.
For most enterprise applications, however, MT systems are component technologies that have to be integrated with company-speciﬁc workﬂow processes
to be evaluated eﬀectively. The translation quality of a system on the web or
right out-of-the-box is completely irrelevant for a corporate user. MT systems
cannot be eﬀectively evaluated “out-of-the-box” because they are tools used to
build solutions, not solutions in and of themselves. MT systems are part of a
process, and evaluating them outside the context of the entire process will not
provide an accurate assessment of their capabilities or usefulness.
When examining an MT system, evaluate the following characteristics:

©2004 LISA and Mike Dillinger. All rights reserved.

23

24

LISA Best Practice Guide: Implementing Machine Translation
Author’s Use vs. Machine’s Knowledge of the Source Language
A basic notion in many discussions of MT evaluation is coverage: how much of
the vocabulary and grammar of a language does the system cover? In other words,
does it cover 60% of English grammar? 40% of Japanese vocabulary? etc. In practice, this is not a useful way of stating the problem, for the simple reason that
there is no master list of what vocabulary and grammar make up English or
Japanese or any other language. There simply is no absolute standard against
which to measure. There may be millions of terms and hundreds of thousands
of sentence patterns, but no one knows what this master list should be.
The key practical notion here is not coverage but overlap: how similar (in grammar and vocabulary) are the texts that will be translated and the capabilities of
the MT system? How much do they overlap?
An MT system may cover 250,000 terms and 100,000 sentence patterns, but
this is of little immediate use if the vocabulary and grammar structures in the
texts to be translated diﬀer from those implemented in the MT system. Authors
know much more of their language than an MT system, but MT systems also
cover a very wide range of phenomena. At issue is to make them coincide—in
other words, to increase the overlap.
There are two ways to increase this kind of overlap and to make MT work more
eﬀectively: (1) improve the MT system, and (2) adapt the authors’ writing style
to produce more translatable output. Adapting an MT system to a user’s needs
is called tuning or customization, and it plays a key role in making MT work effectively. (See How can I customize MT to meet my needs? on page 27.)

Language Support and Direction
Most commercial systems cover common European languages as a minimum,
and may also cover Japanese. Ensure that all directions that you need are available. For example, a system may support Arabic → English, but not English →
Arabic. If you require both directions, then this particular system will not support your needs.
In addition, MT systems may not support translation between all languages
represented in the system. For example, a system may support English ↔ German and English ↔ Arabic but not Arabic ↔ German. Chain translation (e.g.,
translating between German and Arabic via an intermediate English translation) may be considered if you have needs for language pairs that are not directly supported by a system. Chain translation, however, is usually only a stopgap measure since its quality is not as good as a direct translation between two
languages (e.g., Arabic ↔ German).
During evaluation, you should consider not only present language needs, but
also future needs. Since building new language pairs for most MT systems is
©2004 LISA and Mike Dillinger. All rights reserved.

LISA Best Practice Guide: Implementing Machine Translation
expensive and time-consuming, make sure that the system will support any
languages that you may require in the near-term future.
NOTE: See John Hutchins’ Compendium of Translation Software,
http://www.eamt.org/compendium.html, for a list of MT solution providers and their
products.

Document Format Support
MT systems must be able to extract text from ﬁles in order to translate it. For
any format except plain text, extraction of text requires ﬁlters that separate text
from other ﬁle components and deliver it to the MT engine for translation and
then reinsert it in a translated copy of the source ﬁle. Filters for proprietary
formats can be very expensive to develop and must be constantly updated as
ﬁle formats change with new releases and updates to source applications. Make
sure that candidate MT systems support your document format requirements.
There are two levels of ﬁle format support:
• Direct Support. MT tools may directly support a ﬁle format (possibly
through a plug-in ﬁlter) and be able to work with it natively. In this case,
native ﬁles can be submitted directly to the MT engine for translation.
• Indirect Support. Just because an MT tool does not have a ﬁlter for a
particular ﬁle format does not necessarily mean that it cannot support
that format. Very often ﬁles can export text in a number of common ﬁle
formats (such as RTF, plain text, or HTML) that MT tools do support. If
conversion to and from one of these intermediate formats can be automated, MT systems will be able to deal with content in formats that are not
directly supported.
If MT is integrated with other translation tools, it is often possible to leverage ﬁle format support in other translation tools to allow MT to access
otherwise unavailable ﬁle formats. For example, if an MT tool does not
support Quark XPress ﬁles, but a supported translation memory tool does,
it may be possible to use the translation memory tool to provide a bridge
into and out of the Quark XPress ﬁles.
Indirect support requires appropriate process development (and possibly programming of simple tools) and is thus not cost-free, but can provide
an eﬀective route to support ﬁle formats that cannot be directly accessed.

Dictionary Size
MT systems are critically dependent on the completeness of their dictionaries.
Unlike a human translator, an MT system cannot simply consult a large paper
dictionary to supply a translation for an unknown term. Signiﬁcant numbers
of unknown words can render MT output unreadable since the MT system
must contain a considerable amount of information about words and their
grammatical function to provide a correct translation. Human translators can
©2004 LISA and Mike Dillinger. All rights reserved.

25

26

LISA Best Practice Guide: Implementing Machine Translation
often deduce the function of an unknown word or term from context, but MT
systems have a much harder time with unknown terms, and are thus much
more sensitive to dictionary problems. Building MT dictionaries is sometimes
a simple matter of adding pairs of words to a dictionary; in other cases, additional information about verb type, gender, or other grammatical information
must be added as well.
MT vendors will often supply multiple dictionaries with their tools: a general
language dictionary and one or more subject matter dictionaries. The size of
the general language dictionary must be suﬃcient to cover common words in
the source and target languages, but the subject matter dictionary will be the
most critical component for quality translation within a speciﬁc subject ﬁeld.
Subject ﬁeld dictionaries are generally available for common subject ﬁelds, but
it is important to evaluate how comprehensive these dictionaries are for speciﬁc
purposes and to look at the scope of their language coverage. While lack of subject ﬁeld dictionaries may not prevent the use of MT, it will add to the cost of
deployment and the time required before the system is ready for use.

Standards for MT Data Exchange
MT systems often need to communicate with other systems in integrated workﬂow processes, and exchange standards facilitate this integration. For example,
in environments with mixed human and machine translation, it is important
that both types of translation show terminological consistency. A company
may also support multiple MT engines to achieve needed language coverage, thus making dictionary integration vital. In such situations MT systems
need to support a standard such as OLIF (Open Lexicon Interchange Format –
http://www.olif.net), for the exchange of MT lexicon information. Human-oriented terminology systems should support a standard such as TBX (TermBase
eXchange – http://www.lisa.org/tbx/), which can be used to integrate OLIF data
with human-oriented terminology data. If the MT implementation includes integration with a translation memory system, then TMX (Translation Memory
eXchange – http://www.lisa.org/tmx/) should be supported to provide a bridge
for moving translated segments between the two tools.

Dictionary Tools
As your documentation needs evolve, your translation needs also change. New
features and new products mean you will be using new terminology. As you
use a machine translation system, you will identify better translations and additional terms for use. Maintaining and improving MT dictionaries is generally more convenient and more cost-eﬀective when done in-house. Therefore,
choose an MT provider that can supply tools that make it easy to review, edit,
and add entries to your dictionaries. It is also very important to have a tool for
importing whole glossaries rather than entering terms one at a time. The optimal situation is to have interoperability between the terminology management
tools and the MT dictionary using the standards listed above.
©2004 LISA and Mike Dillinger. All rights reserved.

LISA Best Practice Guide: Implementing Machine Translation

6. How Can I Customize MT to Meet My Needs?
MT systems can be customized directly in two primary ways:
• editing and/or adding grammatical rules (done by the system vendor)
• customizing the dictionary (done by both the vendor and the client)

Adapting Grammatical Rules
Most MT systems use rules to parse sentences for translation. If an MT system’s
grammatical rules do not contain a structure that appears in documentation,
or if it misinterprets a structure, the system will most likely provide an incorrect translation. If such constructions occur frequently and are essential to the
texts being translated, then the rules can be altered to correctly interpret the
grammatical structures, either though the addition of new rules, or through
alteration of existing rules. This work must be done by expert linguists on the
vendor’s team.

Customizing the Dictionary
Most MT vendors will provide dictionary customization services for the initial
installation phase. For most users of MT systems it is much more practical to
take charge of on-going customization of the system’s dictionary, in order to
make improvements and additions as required by new documents.
Like human translators, MT systems are dependent on correct terminology for
proper translation. Unlike human translators, however, MT systems cannot
consult reference sources to identify unfamiliar terms, so it is important that
MT dictionaries contain terms needed for the texts the systems will translate
before translation begins.
As explained above, most MT systems ship with a basic dictionary that covers
essential general language. They may also ship with subject ﬁeld dictionaries
that address the terminology of speciﬁc ﬁelds and that improve translation for
texts in these ﬁelds. Beyond any generic subject ﬁeld dictionaries, individual
companies also need to add their company-speciﬁc terminology (such as product/brand names and product-speciﬁc terms). The addition of correct companyand domain-speciﬁc terminology to MT dictionaries is perhaps the single most
critical task in implementing an MT system for a particular company.

7. How Can I Adapt My Processes to Make MT More
Eﬀective?
The content management process can be adapted to make the use of MT more
eﬀective, by focusing on the input to the MT system, i.e., the source documents.
The goal is to minimize the mismatch between the vocabulary and sentence
structures that the MT system can deal with and those that the authors actually
use. See the examples in Tables 5 and 6 above.
©2004 LISA and Mike Dillinger. All rights reserved.

27

28

LISA Best Practice Guide: Implementing Machine Translation
Terminology Management
Part of this adaptation process has already been addressed during customization of the MT system: the vocabulary that the authors use is included in the
MT system. If an eﬀective terminology management system is in place, it is
quite simple to customize the MT system with it. To the extent that authors use
only this standard terminology, MT will provide good results. However, authors do not always stick to terminological standards and the standard terminology may be out-of-date or incomplete. These issues emphasize the need for
eﬀective terminology gathering, documentation and storage as well as tools for
monitoring how the terminology is used in practice (“controlled language” or
“style checking” tools).
Synonyms also require attention. For example, if a document uses phrases such
as “when the engine is switched on” and “when the engine is powered on” to
mean the same thing, translators will not know if they should translate them the
same way or diﬀerently in the target language. In most cases, human translators
spend extra time to translate them diﬀerently, so as not to destroy any possible
meaning diﬀerence. Depending on dictionary entries, MT also translates them
diﬀerently. Although the inconsistency appears to be a translation problem in
both cases, it in fact indicates a problem in the source materials.
Terminology management processes, then, help minimize the mismatch in vocabulary between authors and the MT system. As an additional beneﬁt, this
increase in terminological consistency increases readability for the end users
and makes the documents easier for human translators, as well.
NOTE: Please refer to the Additional Resources section on page 38 for more links to
information on terminology management.

Sentence Structure
Professional authors know a lot about their language and use what they know
to make documents more interesting. One way they do this is by using a wide
variety of sentence structures. One structure that aﬀects both human translators and MT in English is the use of long strings of modiﬁers, such as “left-hand
manual brake cable retract/release lever.” It is very diﬃcult for human translators (reading in a second language) to understand and then to ﬁgure out how
to render such complex structures in the target language. These sorts of phrases
also lack the linguistic cues MT systems require to translate them accurately.
Another simple rule of thumb is to limit sentence length to twenty words. Both
humans and MT systems can analyze longer sentences, but as sentences grow
longer, the number of misunderstandings and errors increases signiﬁcantly.
These are just two examples to show how writing clear and simple sourcelanguage materials to improve MT quality will also help human translators and
end users. The most important rule when writing for translation is the same
©2004 LISA and Mike Dillinger. All rights reserved.

LISA Best Practice Guide: Implementing Machine Translation
one used to maximize readability—“KISS” (keep it short and simple). Keeping
sentences short helps make sure that they use simple sentence structures that
can be accurately parsed by MT systems and humans, too.
Writing to speciﬁc standards is sometimes called controlled (language) authoring. Style checkers are also available to provide authors and managers with
detailed feedback on how well speciﬁc sentences and documents conform to
a company’s style guide or writing standards. (Please refer to Additional Resources on page 38 for more information on controlled authoring.)

©2004 LISA and Mike Dillinger. All rights reserved.

29

30

LISA Best Practice Guide: Implementing Machine Translation

Using MT
Machine translation has been used in a variety of contexts, from translating helicopter manuals in Vietnam to translating the weather in Canada and translating
letters to Grandma on the web. Where once MT systems only ran on mainframe
computers, they now work comfortably on most laptops, and several companies
are working to put MT systems on PDAs (personal digital assistants).
We started oﬀ this Guide by grouping uses of MT into situations where it is not
possible or practical for humans to translate (“MT-enabled applications”) and
situations where it is used to increase translators’ productivity (“MT-enhanced
applications” or “Computer-assisted Translation”).
This chapter provides an overview of how MT systems are deployed, while the
Case Studies provide speciﬁc examples of how it can be customized or adapted
for speciﬁc uses. The overall theme is that MT is a component technology that
can be mixed and matched with other technologies to provide solutions in a
wide range of settings.

1. How Is MT Used in MT-Enabled Applications?
It is simply not possible to have humans translate email, chat, telephone messages or news feeds: the volume is so large that a veritable army of translators
would be needed 24/7. Trying to provide human translation for refugee workers, soldiers, government oﬃces, healthcare and transportation facilities is likewise undermined by the limited availability of human and ﬁnancial resources.
Providing weather reports and directions in multiple languages is an application that is simply too tedious for humans. MT also appears in a wide range of
applications, integrated with other technologies.

Integrating With Email, Chat, SMS
Electronic messaging systems for email, chat, and SMS (Short Message Service)
route digital documents from server to server. In many installations, they are
also routed through an MT server that accepts the messages, translates them
according to the recipient’s preferences and sends them on to their destinations
with the translations. The additional delay of a few seconds is more than made
up for by the ease of reading the messages in your own language.
The technology is well understood, so integrating MT with electronic messaging
is already available. The Case Study, MT Meets Instant Messaging on page 49 describes how Transclick implemented multilingual wireless messaging using MT.
This kind of system can be eﬀective in oﬀering multilingual support or customer
relations with monolingual staﬀ.

©2004 LISA and Mike Dillinger. All rights reserved.

LISA Best Practice Guide: Implementing Machine Translation
Integrating With Automatic Speech Recognition
Speech recognition and dictation software has improved over the last few years
to the point where it is possible to obtain very good results by speaking a little
more slowly and clearly than usual. These systems “translate” speech into a textual form that can be used as input for machine translation.
The challenge is that when speech recognition systems misrecognize something,
machine translation systems cannot correct it before translation, as humans do
so easily and automatically. The errors from speech recognition disrupt the
translation process, so the translated output is not always understandable. The
situation is the same with optical character recognition (OCR) input.
Although the performance of both speech recognition and machine translation
systems improves with each passing year, other technologies are still needed to
make the integration more practical. The Case Study, MT for Speech-to-Speech
Translation (STI) on page 60 explores one strategy: giving the user the ability to
monitor and correct both speech recognition and translation when accuracy of
the message is important.

Integrating With Text-to-Speech Systems
Text-to-Speech (TTS) software “reads” a text aloud, and it is a simple matter to
route the output of an MT system to TTS. Many home machine translation systems already come with TTS as an option. Even when the output does not ﬂow
as smoothly as human speech, the pronunciation is clear and understandable.
Applications of MT and TTS in information kiosks for transportation centers
or hospital waiting rooms can eﬀectively reduce the burden on human support
personnel to answer repetitive questions.

Integrating With Databases and Data Feeds
Simple sentence templates and sophisticated natural language generation systems can take values from a database or data feed and present them as whole
sentences. An MT system can take these automatically generated sentences and
provide the same information in a range of languages within seconds.
Financial and weather information that already exist as data feeds can be offered to additional, foreign-language markets quickly and inexpensively. Similarly, a system for monitoring foreign-language websites can present machinegenerated translations to help analysts decide which items may be important
enough for human translation.

Integrating With Translation Memory Systems
Although translation memory systems were developed for use by human translators, they can also be integrated with machine translation to provide handsoﬀ “interleaved” translations on the ﬂy. In this case, some of the translated sentences are taken from translation memory (when the match is close enough)
©2004 LISA and Mike Dillinger. All rights reserved.

31

32

LISA Best Practice Guide: Implementing Machine Translation
while the others are generated with MT. This mix yields better readability than
machine translation alone, with the same advantages over manual translation
of reduced cost and increased speed. To ﬁnd out how ESTeam integrated MT
and translation memory to cover 110 language directions for one of their global
clients, please see the Case Study, Machine Translation Fulﬁlls High Volume Demand (ESTeam), on page 57.

2. How Is MT Used in MT-Enhanced Applications
(Computer-Assisted Translation)?
The volume and associated cost and time of translation in many enterprise settings are often high enough to justify deployment of MT along with other technologies. At about 200,000 words of new text per year for ﬁve languages (see
Table 3 on page 17 in Building a Business Case for Machine Translation), MT
becomes cost-eﬀective. With larger volumes, MT becomes essential to making
human translation more eﬀective. MT delivers the best results when integrated
into a workﬂow process with other tools. The steps below describe a workﬂow
that is common to many successful deployments of MT and associated technologies.

Workﬂow
Workﬂow refers to a plan for multi-step processes that (1) speciﬁes who does
what with which tools at each step of the way, and (2) deﬁnes the required input and output for each step. As processes become more complex, an explicit
workﬂow becomes increasingly important.
Multilingual content management is one complex process that beneﬁts greatly
from a planned workﬂow that covers authoring, revision, translation, formatting, testing etc.—all carried out by multiple groups in diﬀerent locations. A
range of software tools has emerged to improve planning, communication and
process consistency, called Enterprise Information Portals (see eWeek’s special
report at http://www.eweek.com/category2/0,1738,1372236,00.asp), Content
Management, Document Management, or Translation Workﬂow Systems.
These tools are extremely eﬀective for managers who have to monitor several projects over the course of multiple processing steps in diﬀerent locations.
These systems can even be programmed to automate handoﬀ and to schedule
routine tasks with rules like, “After a document is checked in by Jeﬀ, submit
it for machine translation with these settings, and send the result to Jasmina
or to Consuelo if Jasmina is too busy.” Transactions are time-stamped, and
the system can send out alerts when a given step is taking too long or request
progress reports at given intervals. An ad hoc project group can be deﬁned for
components of a product being documented so that translators and testers can
communicate with authors and programmers to avoid errors and misunder©2004 LISA and Mike Dillinger. All rights reserved.

LISA Best Practice Guide: Implementing Machine Translation
standings. Catching and ﬁxing errors during production is much less expensive
than ﬁnding errors during testing or after publication.
One of the most important beneﬁts of these workﬂow systems is that they foster
planning and communication, so that once things are set up, documentation
quality increases and costs, completion times and headaches decrease. Several vendors already oﬀer workﬂow systems speciﬁcally designed for managing translation projects (please refer to Additional Resources for a partial list of
workﬂow products).

Authoring
The point of having documentation is to add value to the users’ experience by making their use of products easier and more eﬀective. Readability plays a key role in
this, both for the readers of the source documentation and for the translators who
have to understand it well to make it easy to read in the target languages.
“Soft” authoring technologies such as style guides, training and glossaries often lead to documentation that is more readable. “Hard” technologies such as
distributed terminology management tools and style checking software give
authors instant feedback about how well their writing conforms to the norms
and standards being implemented (please refer to Additional Resources on page
38 for more information on these technologies).
“Single sourcing” refers to the use of XML (rather than proprietary formats such
as rtf, pdf, etc.) to structure and package authored content to make it easier to reuse the same content in diﬀerent documents published through diﬀerent channels. Annotations, revisions and translations can be added as additional ﬁelds
to make the content a “living” document. Additional tools can easily apply different style sheets to format the same content for diﬀerent kinds of publications.
(See the Resource Cooperative at http://www.innodata-isogen.com/resources
for more information.)
The importance of well-structured, readable source documentation cannot be
understated. Wordy, hard-to-read documentation costs more to write, to revise,
to translate and to publish. It also generates more costs for support as users
phone and email to ask for clariﬁcation.

Translation Memory as a Filter
Translation memory systems are very eﬀective tools for updating translations of
revised material. They automatically identify sentences that have already been
translated and veriﬁed so that this work does not have to be repeated. In this
sense, they ﬁlter out the sentences that have already been translated and draw
the translator’s attention only to the sentences that have to be revised or translated from scratch.

©2004 LISA and Mike Dillinger. All rights reserved.

33

34

LISA Best Practice Guide: Implementing Machine Translation
This often means that 80% to 90% of the original text does not have to be retranslated, with a very large savings in time and expense. Standardized authoring plays
a role here, as well. As terminology becomes more consistent and sentences are
shorter and easier to read, the ﬁltering eﬀect of translation memory shows clear
improvements and further reductions in translation costs are possible.
The leading vendors of translation memory systems and tools are
TRADOS (http://www.trados.com), SDL (http://www.sdl.com), Star
(http://www.star-group.net), MultiCorpora (http://www.multicorpora.ca) and
Atril (http://www.atril.com).

MT for Draft Translations
After a translation memory system has ﬁltered out the sentences that have already
been ﬁnished, any revised or new material is identiﬁed for translation. This is
where MT makes its contribution to the computer-aided translation process. MT
provides human translators with draft translations to work from, rather than requiring them to start from scratch. Some of the machine-generated translations
are perfect, others need revision and a small proportion is not very useful.
This is the key point with using machine translation: even if the MT system
provides correct or partially correct translations only 50% of the time, that is
50% less work, less time and less expense with human translation. Many critics
of MT think that because it cannot substitute for the human translator, it is of
no use at all. That is like saying that because bicycles and automobiles cannot
substitute for humans, they are useless. Like any other power tool, MT is engineered to certain speciﬁcations so it has signiﬁcant, built-in limitations, but
within those limitations, it is very eﬀective.
The most signiﬁcant limitation of MT is dealing with source documentation
that is “out of bounds”—documentation that uses sentence patterns and terminology that the MT system does not know how to process. Similarly, if you
drive your car in deep sand, snow, mud or water it will not perform nearly as
well as if you drive it on the highway.
As discussed in Evaluating, Choosing and Customizing a Machine Translation System, there are two ways two deal with these limitations: (1) standardizing terminology and writing style on the one hand, and (2) dictionary and
grammatical “tuning” of the MT system on the other. As the mismatch between
the authors’ style and the system’s knowledge is reduced, the proportion of highquality or perfect translations increases dramatically.

Post-Editing or Linguistic QA
Post-editing is important both for human and for machine-generated translations. This phase of processing compensates for the limitations of the translation process, no matter how it is carried out.
©2004 LISA and Mike Dillinger. All rights reserved.

LISA Best Practice Guide: Implementing Machine Translation
In the case of human translation, translators sometimes misunderstand the
source document, select a non-standard translation for a given term or unwittingly use synonyms when the same term is needed. The authors’ knowledge
of the topic and the source language is often very diﬀerent than the translator’s
knowledge, and this mismatch leads to errors that have to be ﬁxed in QA. If the
translator is not very skilled or very experienced, post-editing his or her work
can be extremely time-consuming.
In the case of machine translation, the situation is essentially the same: because
the authors’ knowledge of the source language (vocabulary and sentence structure) is much greater than the knowledge in the MT system, the mismatch leads
to errors that have to be ﬁxed in QA. If the MT system has not been customized
or tuned to the authors’ writing style and terminology, post-editing the output
can also be extremely time-consuming.
The need for post-editing often comes up in criticisms of MT. However, if excessive post-editing is necessary for a given deployment of MT, it is a sure sign
that the installation was poorly planned and/or executed. Similarly, if excessive
post-editing is necessary for a human translator, it is a sure sign that the hiring
manager was ineﬀective and the wrong translator was selected.
NOTE: Please refer to http://www.geocities.com/mtpostediting/ for more information on post-editing of MT output and to Additional Resources on page 38 for
linguistic QA tools/guides.

Translation Memory as Storage for Reuse
After translation of new or revised material has been ﬁnalized, a key step is to
make sure that the newly translated material is stored in the translation memory system. This creates a virtual cycle in that, each time a translation is created
or polished, the ﬁltering function of translation memory improves, and the
improved translations are reused throughout the document. Translations and
revisions do not have to be redone, and on-going improvements to the translation memory database increase overall quality of the translated documents.
A similar eﬀect of storage-for-reuse is created by storing translations together
with the source sentence in an XML-based single-sourcing system. The same
translation can be used anywhere the source content is deployed for reuse.
One limitation of many implementations of this XML approach, however, is that
the translations are linked only to one content unit (e.g., a procedure) and are
reused only when that whole content unit is reused. Translation memory systems and more sophisticated XML implementations (see http://www.xml-intl.
com) reuse translations more eﬃciently because the units of reuse are smaller:
any time a given sentence is reused (in what ever content unit or document),
the translation for that sentence can be located and reused.
©2004 LISA and Mike Dillinger. All rights reserved.

35

36

LISA Best Practice Guide: Implementing Machine Translation
Publication
The main driving factor behind the single-sourcing approach to content management is to avoid incompatibilities between diﬀerent proprietary tools
throughout the content management process, and the formatting bottleneck
at publication. If documents are authored in multiple formats and then published in other multiple formats, then all of the cross-format conversion, revision and correction becomes a time-consuming, costly nightmare. Add to this
localization and encoding diﬀerences for diﬀerent languages and multilingual
publication starts to seem impossible.
Single-sourcing eﬀectively does away with these problems by standardizing the
authoring format throughout the entire process. Generating multiple delivery
formats from a single source simpliﬁes publication greatly. (Please refer to the
Resource Cooperative at http://www.innodata-isogen.com/resources for more
information.)

Usability Testing
Post-editing and Linguistic Quality Assurance (QA) check for accuracy, readability and completeness of the translations. In some cases, an additional step
of usability testing is done, to double-check that the translated version is an
eﬀective guide to using the product. The advantage of this process is that end
users have much-improved documentation and an enhanced experience with
the product.
The disadvantage is that any errors found at this late stage are as much as 20 times
more expensive and time-consuming to ﬁx than errors caught during the authoring stage (please refer to http://www.iai.uni-sb.de/docs/lrec98.pdf). All too frequently, the errors reﬂect information missing and/or changed from the source
documentation. This means that additional eﬀort and expense will be spent on
those parts of the text, as each of the content management steps cited above is
repeated.
This, once again, emphasizes the importance of high-quality source documentation and an automated localization process that will make quick updates not
only possible, but also inexpensive.

Technical Support
Once the documentation is published and reaches the end user, any diﬃculties
or inaccuracies in the documentation turn into user frustration and dissatisfaction and/or requests for technical support. With estimated costs of USD 30 per
telephone support incident and USD 10 per email support incident, moving
to self-service support with abundant, high-quality source documentation and
accurate translation will provide excellent return on investment.

©2004 LISA and Mike Dillinger. All rights reserved.

LISA Best Practice Guide: Implementing Machine Translation
Next Steps
MT plays a key role in eﬀective multilingual content management. This guide
provides only an overview of what you need to know to improve your content
management processes.
Now it is time to move on:
•
•
•
•
•

determine your expectations for machine translation
explore the information in Additional Resources,
review the Case Studies,
research what diﬀerent companies can oﬀer for your speciﬁc situation,
download a copy of the LISA Global Content Management Guide
(http://www.lisa.org/interact/gcms.html),
• consider hiring a consultant to guide you through the improvements required for your content management process.

©2004 LISA and Mike Dillinger. All rights reserved.

37

38

LISA Best Practice Guide: Implementing Machine Translation

Additional Resources
Associations
International Association of Machine Translation
European Association of Machine Translation:
http://www.eamt.org
Association of Machine Translation in the Americas:
http://www.amtaweb.org
Asian-Paciﬁc Association for Machine Translation:
http://www.aamt.info
LISA (Localization Industry Standards Organization):
http://www.lisa.org/
ATA (American Translators’ Association):
http://www.atanet.org/
STC (Society for Technical Communication):
http://www.stc.org/
IABC (International Association for Business Communication)
http://www.iabc.com/

Online Resources
Compendium of Translation Software, compiled by John Hutchins
http://www.eamt.org/compendium.html
Machine Translation: An introductory guide, online book by Doug Arnold, et al.:
http://www.essex.ac.uk/linguistics/clmt/MTBook/
Publications about the history and state of the art of machine translation:
http://ourworld.compuserve.com/homepages/WJHutchins/
Archive of publications about machine translation:
http://www.mt-archive.info/
Publications about post-editing machine translation output:
http://www.geocities.com/mtpostediting/
Bowne Global Position Papers:
http://www.bowneglobal.com/english/exp_pp.htm
(see Internationalization, Terminology, Controlled English, and To Build or To Buy?)
CLS White Papers:
http://www.lisa.org/2003/HylandNEU.pdf
(Testing Prompt: The Development of a Rapid Post-Editing Service)
ESTeam White Papers:
http://www.esteam.gr/whitepapers/ESTeam_WhitePaper_2003.doc
Lionbridge Knowledge Center White Papers:
http://www.lionbridge.com/kc/default.asp
(Under Content Globalization: When to automate translation processes –
http://www.lionbridge.com/kc/gp_intro.asp?kb=sap&wp=when_auto
Under Customer Support: When to use MT –
http://www.lionbridge.com/kc/ec.asp?kb=mlcs)
MultiCorpora White Papers:
http://www.multicorpora.com/whitepapers_e.html
©2004 LISA and Mike Dillinger. All rights reserved.

LISA Best Practice Guide: Implementing Machine Translation
SDL White Papers:
http://www.sdl.com/localization-information/white-papers-articles.htm
Systran White Papers:
http://www.systransoft.com/company/technology/whitepapers.html
Systran Case Studies:
http://www.systransoft.com/company/technology/casestudies.html
EUROPA listing of speeches and articles relating to translation technology:
http://europa.eu.int/comm/translation/reading/articles/
tools_and_workﬂow_en.htm
The KANT Project:
http://www.lti.cs.cmu.edu/Research/Kant/

On-Line Conference Proceedings
MT Summit IX, New Orleans, USA, September 2003:
http://www.amtaweb.org/summit/MTSummit/papers.html
Controlled language translation, Dublin, May 2003:
http://www.ctts.dcu.ie/presentations.html
MT Summit VIII, Santiago de Compostela, Spain, September 2001:
http://www.eamt.org/summitVIII/papers.html

Articles from the Globalization Insider
NOTE: The following articles are available to LISA members.
The Business Case for MT: The Breakthrough Is for Real
(Jaap van der Meer, Cross Language N.V.)
http://www.lisa.org/archive_domain/newsletters/2003/2.6/vandermeer.html
The Beneﬁts of Maturity: SYSTRAN Prioritizes Source Content Engineering and
Knowing your Customers (Interview with Pierre-Yves Foucou)
http://www.lisa.org/archive_domain/newsletters/2002/3.1/foucou.html
Making Money with Machine Translation: Every Cash Cow Starts Out as a Calf!
(Monika Röthlisberger, CLS Communication)
http://www.lisa.org/archive_domain/newsletters/2004/3.2/roethlisberger.html

Presentations from LISA Forums
NOTE: The following presentations are available via the LISA’s members domain to
LISA General Assembly members. A listing with links is available at http://www.lisa.
org/products/bestPractice/MTlisting.html
Putting Machine Translation to Work: Language Translation at Cisco
Peter Jaeger, Cisco Systems (San Francisco, 2004)
A Term Extraction and Glossary Embedding System
Naoyuki Tokuda & Pingkui Hou, Sunﬂare Co. Ltd (San Francisco, 2004)
Terminology for Machine Translation
Kara Warburton, IBM (Washington D.C., 2003)
©2004 LISA and Mike Dillinger. All rights reserved.

39

40

LISA Best Practice Guide: Implementing Machine Translation
Single-Source Publishing
Bärbel Strothmann-Schmitt, Software AG (Heidelberg, 2002)
Controlling Controlled Language
Melanie Wells, SAP AG, & Dr. Andrew Bredenkamp, acrolinx GmbH
(Heidelberg, 2004)
MT Developers and Users Discuss Industry Applications, Investments, Outlook
and ROI (Heidelberg, 2002) includes the following presentations:
• Pricing a Machine Translation Service, Monika Röthlisberger, CLS Corporate
Language Services AG
• Translation Technology in Multilingual Help Desk Applications, Dr. Adriane
Rinsche, The Language Technology Centre Ltd.
• LOGOS MT Portal Applications, Dr. Frank Beckmann, GlobalWare
Language Resource Management for Enterprise Communications: The ROI
Kara Warburton, IBM (Washington D.C., 2002)

Standards
OLIF (Open Lexicon Interchange Format)
http://www.olif.net
SALT (Standards-based Access service to multilingual Lexicons and Terminologies)
http://www.ttt.org/salt/
TBX (TermBase eXchange)
http://www.lisa.org/tbx/
TMX (Translation Memory eXchange)
http://www.lisa.org/tmx/

Surveys
Terminology Management Comparative Study
http://www.lisa.org/archive_domain/newsletters/2003/3.2/termReport.html
LISA/OSCAR Translation Memory Survey
http://www.lisa.org/products/survey/2003/tmsurvey.html
LISA/OSCAR Global Content Creation Report
http://www.lisa.org/products/survey/2003/gccsurvey.html
Summary Report on the Results of the LISA Terminology Survey
http://www.lisa.org/2001/termsurveyresults.html

Technical Publications
LISA Best Practice Guide: QA - The Client Perspective
http://www.lisa.org/archive_domain/newsletters/2004/2.1/BPG.html
Globalization Insider:
http://www.localization.org
LISA Global Content Management Guide:
http://www.lisa.org/interact/gcms.html
Machine Translation:
http://www.ccl.umist.ac.uk/staﬀ/harold/MTjnl/
Multilingual Computing
http://www.multilingual.com/
©2004 LISA and Mike Dillinger. All rights reserved.

LISA Best Practice Guide: Implementing Machine Translation
Computational Linguistics
http://mitpress.mit.edu/catalog/item/default.asp?ttype=4&tid=10
Journal of Natural Language Engineering
http://uk.cambridge.org/journals/nle

Tools
Controlled Language / Style-Checking Tools
Resource Cooperative:
http://www.innodata-isogen.com/resources
Multidoc/CLAT:
http://www.iai.uni-sb.de/docs/clatfactsheet.pdf
Acrocheck:
http://www.acrolinx.de/acrocheckOverview_en.html
Boeing Simpliﬁed English Checker:
http://www.boeing.com/phantom/sechecker/
Maxit:
http://www.smartny.com/maxit.htm

Linguistic QA Tools
LISA QA Model:
http://www.lisa.org/products/qamodel.html

Translation workﬂow systems
SDL Workﬂow:
http://www.sdl.com/products-home/enterprise-systems/sdlworkﬂow.htm
Trados TeamWorks:
http://www.trados.com/products.asp?page=1450
Star Translation Workﬂow Server:
http://www.star-group.net/eng/software/sprachtech/tws.html
Language Technology Centre Communicator:
http://www.langtech.co.uk/eng/communicator/index.asp

©2004 LISA and Mike Dillinger. All rights reserved.

41

42

LISA Best Practice Guide: Implementing Machine Translation

Appendix I. Types of MT Systems
There are various types of machine translation systems, and they work in different ways. All MT systems, however, rely on a computer program that takes
source text and converts it to a target text in some manner. This is a simple introduction to the most common approaches to MT. For more information, see
Machine Translation: An Introductory Guide, an online book by Doug Arnold,
et al.: http://www.essex.ac.uk/linguistics/clmt/MTBook/.
The European Association for Machine Translation publishes a Compendium of Translation Software, compiled by John Hutchins, which is available at
http://www.eamt.org/compendium.html. The Compendium contains system
characteristics and contact information for a wide array of translation software
vendors.
Current approaches to MT include the following:

Simple Dictionary-based MT
The simplest form of MT is based on lexical transfer, or word-for-word (dictionary style) translation. In this model, words are simply translated as they occur. For example, if the Hungarian sentence Azt a nagy piros kocsit láttam were
input and translated into English, the MT system would output something like
That the large red car saw I, a literal word-for-word rendering of the Hungarian
sentence.
This sort of simple translation has its uses, since an English speaker would certainly be able to ﬁgure out that the original sentence has something to do with
seeing a large red car. However, in the case of more complex sentences, simple
lexical transfer can be diﬃcult to understand and unclear, unless the reader
already has some understanding of the source language and is using the MT
system to understand words he or she may not know.
A key problem is that without any linguistic analysis, it is diﬃcult for this kind
of system to distinguish between diﬀerent meanings of a word in order to select
an appropriate meaning based on the other words in the sentence.
Some small-scale MT systems might be of this type, but few commercial products ﬁt easily into this category today.

Transfer-based MT
The great majority of today’s commercial MT systems, both for consumers and
for enterprises, consists of transfer-based systems, also called “rule-based” systems. Transfer-based MT has been in development since the 1950s.
©2004 LISA and Mike Dillinger. All rights reserved.

LISA Best Practice Guide: Implementing Machine Translation
These systems start with dictionary lookup and parsing (grammatical analysis)
of the original, source language sentence. A system that parses text will break
sentences into component parts, assigning a grammatical role (such as subject,
predicate or object) to each word in the sentence. Parsing produces better results than simple lexical transfer because it makes better use of sentence context
and can provide translations that follow the grammar of the target language.
After the sentence has been parsed, a series of transfer rules are used to reorder
words and otherwise alter the structure of the incoming sentence to produce
a translation that is grammatically correct for the target language. Finally, a
generation stage produces inﬂections, contractions, etc. for the target language
words. Transfer-based systems are designed for speciﬁc language pairs, so new
sets of rules must be created for each language pair and each direction of translation.
A system using parsing and transfer rules for the Hungarian example cited
above would produce something equivalent to I saw that large red car.

Interlingual MT Systems
Transfer-based systems are built and optimized for speciﬁc pairs of languages.
As transfer systems became more complex, adding a new language became
more and more diﬃcult. For example, in a system designed for seven languages,
a separate transfer system would have to be built for each of the 42 possible language combinations of those languages (six for each language in the system)
To solve this problem, many developers have worked with an interlingual approach in which the meaning of the original sentence is expressed in a common notation (an “interlingua”) that can be used to generate sentences in any
other language. Interlinguas are similar to the recent XML-based standards for
representing information, which can be processed with diﬀerent programming
languages on diﬀerent kinds of hardware. For example, someone can build an
XML document or database with Java, while another person can extract data
from the same XML document using Perl or C. XML, then, is a kind of interlingua for data.
In this approach, techniques from transfer-based MT are used to “translate”
sentences into the interlingua and back. The technical challenge is to make the
interlingual version of the sentence reliable and detailed enough for accurate
translation, and this has proved diﬃcult to do for a wide range of sentences.
For this kind of system, each language needs only two components for translation to and from any number of other languages: an analyzer that builds an
interlingual notation for an incoming sentence and a generator that produces
sentences for any interlingual notations. A Japanese system, for example, can
©2004 LISA and Mike Dillinger. All rights reserved.

43

44

LISA Best Practice Guide: Implementing Machine Translation
produce interlingual notation for a document, which can then be sent to a Russian or Italian system for generation in that language.
There are no commercially available interlingual MT systems, but they continue to attract the interest of a growing number of researchers.

Data-driven MT
Attention has recently turned to the possibility of producing MT systems that
do not make direct use of explicit parsing or transfer rules, but which rely on
examples of previously translated text drawn from massive databases. This approach oﬀers the potential of much faster development of an MT system and
can take advantage of the large translation memory databases that many organizations have built up.
Statistical machine translation (SMT) and Example-based machine translation (EBMT) are two diﬀerent approaches to data-driven MT. They both
use complex statistical methods to produce new translations based on sample
translations that are available. These systems analyze a large number of original
sentence/translated sentence pairs to discover which words or expressions in
one language are most highly correlated with words or expressions in the other.
Oversimplifying, the system basically builds the bilingual dictionary and the
transfer rules automatically. When a new sentence appears for translation, the
system uses the correlations found in the samples to propose the translated version that is most likely to be correct. Generally, the more sample translations
that are available, the better the results.
Commercial systems using this approach have only recently become available.
They can start delivering translations quickly without the need for lengthy development and testing of transfer rules and lexicons. They also provide the potential for reuse of translation memory data in new ways, further increasing the
value of that technology.

Hybrid Systems
Current research work is focusing on combining the strengths and weaknesses
of diﬀerent approaches to machine translation to produce better results. Examples include systems that use rule-based analysis and generation connected
by data-driven transfer rules, or statistical systems that blur the distinctions
between example-based and standard statistical approaches.
The greatest challenge in developing any of these systems is that people tend
to write in a wide variety of ways, even when discussing the same topic. The
vast range of terms and sentence structures that people use makes it more difﬁcult to prepare systems to analyze them. This is one reason why standardized
©2004 LISA and Mike Dillinger. All rights reserved.

LISA Best Practice Guide: Implementing Machine Translation
approaches to authoring, with clear style guides and common terminology,
continue to play an important role in the eﬀective deployment of MT.
A close look at research into machine translation shows that very high quality
systems are within reach, but developing them for freely variable texts requires
more funding than is available today.

©2004 LISA and Mike Dillinger. All rights reserved.

45

LISA Best Practice Guide: Implementing Machine Translation

Case Studies

©2004 LISA and Mike Dillinger. All rights reserved.

47

LISA Best Practice Guide: Implementing Machine Translation

49

CASE STUDY: MT Meets Instant Messaging (Transclick)

The following case study discusses the integration of MT and Instant Messaging (IM) technology to facilitate interpersonal business communications and increased international sales.
João Gonçalves, Head of International Marketing for Aços Unidos in Belo Horizonte, Brazil, had a
problem. Gonçalves speaks thousands of words of ﬂuent Brazilian Portuguese, about 800 words of
English and about 10 words of Chinese. His ﬁrm had experienced a leap in sales to China in recent
years. However, as sales grew exponentially, misunderstandings seemed to grow even faster. Mistakes
were often made in purchase orders. Miscommunications occasionally resulted in delayed shipments,
and even orders lost to competitors. Finally, Gonçalves wanted to sell a higher value-added titanium
alloy to the Chinese, but he found it diﬃcult to convey the merits of his proprietary product to the
Chinese purchasing manager in broken English.
Aços Unidos employed several human translators to translate legal documents and contracts into
Chinese from English and from Portuguese into English. However, these eﬀorts were time-consuming and very expensive. The Chinese translator charged at least USD 50 per page and took two days to
turn around ﬁve pages by fax or email. It was simply not practical for day-to-day communications or
real-time collaboration, which was now economically feasible thanks to the Internet.
Then, through a contact at the World Trade Center of São Paulo, Gonçalves heard about a new software product called TrIM. He tried out a free demo on a trial basis with his principal Chinese customer, Zhong Guo Jian Zhu (ZGJZ). The results were instant and gratifying.
TrIM allowed for essentially instantaneous multilingual communication (up to 5,000 words a minute)
between the two companies from one computer to another over the internet, or between corporate
enterprise collaboration portals. Whereas before, low- and mid-level employees communicated with
great diﬃculty in broken English (the common language), now each person could type in his/her
native tongue (Portuguese to Chinese and the reverse). While the translations were not perfect, they
were quite understandable. Any questions were usually resolved by a simple request for rephrasing.
As they practiced, the communication improved. They learned to avoid slang, idiomatic expressions,
spelling errors and dependent clauses that can lead to mistranslations.
This is important because the way sentences and phrases are constructed in a language in one context
may convey an entirely diﬀerent meaning from the meaning of the words taken individually in another context. For example, cool can mean a low temperature or very interesting. Bit can mean 8 bits to a
byte of data in computer science, a horse’s bit in a bridle in an equestrian setting, a drilling bit in petroleum engineering, or a little bit of food in terms of quantity. Selecting the right dictionary or subject
domain will eliminate false connotations and improve translation quality as a result. Machine translation works best when one uses it for a specialized subject domain where there is a consistent need for
the same terminology and phrases. That is true for most vertical market business enterprises.
©2004 LISA and Mike Dillinger. All rights reserved.

50

LISA Best Practice Guide: Implementing Machine Translation

What Is TrIM?
TrIM stands for Translated Instant Messenger from Transclick, which connects machine (computerized) translation engines to instant messaging servers available from a web-based, Java client downloadable to any computer. Machine translation uses pattern recognition algorithms (artiﬁcial intelligence software) in which grammar and syntax are already built into the software for each language
pair, quickly translating text from one language into another, using online dictionaries (similar to a
grammar checker and a spell checker). Since this is a very complex task, machine translation often
produces results that are not perfect. However, they are often intelligible enough to be useful and
even acceptable for collaboration over the internet. Publishable quality translation of text may be too
expensive and slow by comparison for everyday use and not practical for real-time collaboration, thus
opening the way for machine translation to ﬁll the need.
TrIM has been proven in trials with NATO, where it is currently in use at 200 locations in Iraq for
Arabic. Transclick has integrated a number of best-of-breed language pairs so that Transclick now offers sixteen languages. Accuracy levels vary, but typically average from 80% to 90% for noun accuracy.
With the aid of drop-down specialized dictionaries, accuracy levels can approach 95% or higher. This
can often exceed the accuracy of a human translator, especially if the latter is not experienced with a
speciﬁc domain.
Transclick has also developed web-based enterprise collaboration tools in Java that access its networked translation servers in Boston (USA) to create a scalable and modular real-time text and messaging translation web service. It is the only company to oﬀer wireless, real-time translation with
instant messaging, email and customizable dictionaries.

How Aços Unidos Adapted TrIM
After a suitable period using the free demo, both Aços Unidos and ZGJZ were hooked. The charge was
only USD 35 per seat (user) per month, based on a minimum of ten seats. Aços Unidos could easily
put the other seats to use with other clients in the Far East and the United States, as well as with its
overseas coal suppliers. It could utilize any of the ﬁfteen languages at any time of the night or day. Best
of all, its cost per word was inﬁnitesimal based on its heavy usage.
Aços Unidos decided to print all of its pre-purchase orders in both Portuguese and English with
TrIM, with only the ﬁnal draft to be reviewed in English. In addition, all sales materials were translated into the customer’s language from English and then reviewed by a native speaker. Much time
and expense were thus eliminated.
However, the greatest use for TrIM by far was in day-to-day communications between the marketing, shipping and logistics people at Aços Unidos and their counterparts in China and other overseas
markets. Misunderstandings that had plagued relationships before were quickly ironed out. People
learned to use clear words like solved instead of idiomatic expressions such as ironed out, and caused
problems in relationships for plagued relationships, which resulted in much better quality.

©2004 LISA and Mike Dillinger. All rights reserved.

LISA Best Practice Guide: Implementing Machine Translation

51

Integrating Quality
The President of Aços Unidos was very impressed with the results. However, he was concerned that
there might be a mistranslation on a big order that might result in a damaged commercial relationship. Gonçalves explained to him that the quality of the TrIM translation was continuously improving, and that this was being done in several ways. First, as previously mentioned, the individuals using
the service were learning how to avoid misunderstandings by not using slang, dependent clauses, etc.
Second, each user occasionally incorporated special words in a TrIM dictionary at USD 3 per word.
Finally, ZGJZ decided to pay for the use of a specialized Chinese/English industrial materials digital
dictionary that was supplied by Transclick.
Transclick, itself, was contributing to this continual improvement in quality by employing a best-ofbreed assortment of the machine translation engines available for each language pair, instead of sourcing all machine translation engines from just one vendor. It was also licensing the latest generation of
example-based statistical machine translation engines and training them on large corpora of linguistic
data in the subject domain required by each client, as well as customizing dictionaries for the older
generation machine translation engines.

Integrating TrIM With Other Linguistic Tools
The Head of Corporate Communications at Aços Unidos met with Gonçalves and several support
staﬀ to determine the best way to integrate TrIM with other linguistic tools such as human translation. They identiﬁed a number of issues such as speed, accuracy, cost and availability. They decided to
use TrIM on everything except ﬁnal versions of contracts, published articles, sales documents and ﬁnal quotes (which were always done in English anyway). They also decided to conduct in-house seminars on how to use TrIM. These seminars dealt with such issues as avoiding ambiguity and idiomatic
expressions in language, correcting spelling errors before translating, the use of simple declarative
sentences, as well as when it might be advisable to request the inclusion of new technical words and
phrases in the specialized dictionaries. NOTE: Translation memory tools (for re-using human quality
translation), including real-time terminology servers, can also be integrated for larger terminology
databases.

Adjusting the Work Flow to Incorporate TrIM
When Gonçalves proposed using TrIM to the Head of Operations, he ﬁrst encountered some resistance. The latter wondered if his organization would have to issue special purchase orders in addition
to its regular purchase orders. Gonçalves solved the problem by suggesting that Operations continue
to use its regular purchase orders and simply add the printout of the SMS TrIM conversation, which
was translated into Brazilian Portuguese and saved in archival digital memory. The Purchase Order,
which was always issued in English, would then be veriﬁed and checked against this Portuguese SMS
text by the oﬃcial translator from the Sales Department. The Acquisitions Department also instituted
similar procedures for using TrIM when dealing with overseas suppliers.

©2004 LISA and Mike Dillinger. All rights reserved.

52

LISA Best Practice Guide: Implementing Machine Translation

Diﬃculties Faced and How They Were Overcome
The integration of TrIM at Aços Unidos proceeded fairly smoothly, so only a few diﬃculties were encountered. One issue, alluded to above, was the question of who would pay for the link (or seat) when
a customer, such as ZGJZ, adopted the service. That was fairly easy to deal with. Since Aços Unidos
was the supplier, it would continue to pay for its link with ZGJZ. Should there be any discontinuity in
service (so far, there has not been), then ZGJZ would pick up the slack.
Another issue that arose was the change in responsibilities for the in-house translators at Aços Unidos. It soon became clear that there would continue to be enough work for the translators. Final drafts
of oﬃcial documents and contracts still required review by human translators, although TrIM proved
to be of great assistance for the preliminary drafts. The translators also reviewed the SMS TrIM texts
that were annexed to the English language Purchase Orders.
Indeed, Aços Unidos found that, for the most part, TrIM was allowing it to perform translation that
simply had not been done before. Thus, its translation costs did not decline nor did they signiﬁcantly
increase. Rather, the beneﬁts turned out to be increased sales and more value-added sales. Costs were
also signiﬁcantly reduced since mistakes on both purchase and sales orders were greatly reduced or
even eliminated entirely. This resulted in a return on investment (ROI) in excess of 1,000% over one
year on real-time translation costs of about $350 per month for 10 licenses.
And with Transclick planning to launch a wireless version of TrIM in the near future over Vivo, the
largest wireless carrier in Brazil, wireless real-time translation of email and text messaging over a
mobile Smart Phone will be enabled. This will open up many more possibilities for users like Aços
Unidos.
Please visit the Transclick web site at http://www.transclick.com for more information.

©2004 LISA and Mike Dillinger. All rights reserved.

LISA Best Practice Guide: Implementing Machine Translation

53

CASE STUDY: Machine Translation Makes Money (CLS Corporate
Language Services)

The following case study describes how CLS Corporate Language Services developed MT into a service
that is now available to approximately 70,000 customers worldwide through UBS AG, one of the largest
ﬁnancial institutions in the world.
CLS Corporate Language Services AG oﬀers its machine translation solution as part of UBS AG’s intranet services. The system can be accessed from the company’s intranet through an easy-to-use, webbased interface. Both text fragments and entire documents in a variety of formats can be processed.
The system translates from and to several languages:
German ↔
↔
↔
↔

English
Spanish
French
Russian

English ↔
↔
↔
→

Spanish
French
Russian
Italian

The MT component (licensed from COMPRENDIUM) has been augmented with extensive subject
dictionaries related to banking/ﬁnance and telecommunications. The dictionaries are maintained and
continuously improved by a dedicated team that provides both linguistic and IT support. The CLS
oﬀering is supplemented by pre- and post-editing services, as well as human translation. The service
is currently available to approximately 70,000 users worldwide.
Customer surveys, which are carried out on a regular basis, have shown that our customers are using
MT for the following purposes:
• comprehension of texts (documents, e-mails, internal communication) written in a language
unknown to the user
• translation of texts that will be post-edited by the user
• single word translations / dictionary lookups
Before the introduction of MT, the need for multilingual documentation was being addressed through
human translation services since no high-speed and/or low-cost solution was available. Customers
are now experiencing signiﬁcant savings through decreases in (1) the time spent on creating text and
(2) the expenditures required for human translation services.
As the system was implemented as a browser-based HTML application, installations on the customer’s
desktops are not required. Similarly, maintenance is exclusively server-based. No changes are required
for the client’s workﬂow. Access to the system is provided by means of a URL that is accessible via the
UBS Tools menu.
©2004 LISA and Mike Dillinger. All rights reserved.

54

LISA Best Practice Guide: Implementing Machine Translation

The system is also indirectly integrated with further tools provided by CLS:
• a terminology database (term bank) for German, English, French and Spanish (partial) which
contains up to 50,000 banking/ﬁnance terms per language, together with their translations, deﬁnitions and associations. This term bank is also accessible through the UBS intranet.
• a translation memory containing all human translations previously created by CLS for UBS.
Both the contents of the term bank and the translation memory are incorporated into the machine
translation system. By using in-house terminology and translation resources in conjunction with
machine translation, CLS ensures that corporate wording and terminology standards are met at all
levels.
Quality is critical insofar as the added value over free internet-based MT solutions must be obvious
at all times. In contrast to free MT solutions, the system must provide (1) a large vocabulary in the
customer’s ﬁeld of specialization (e.g.,. banking/ﬁnance, along with IT), and a continuous coverage
and updating of corporate names and company-speciﬁc terminology.
Overall quality is ensured through the following measures:
• logging and coding of the unknown words that occur most frequently; by doing so the vocabulary is continuously adapted to emerging needs
• translation analyses and coding/ﬁxing of the most pressing problem cases; this task leads to an
improvement of both structural and vocabulary-based translation problems
• benchmark tests carried out on a regular basis; based on a set of relevant customer tests, improvements (and potentially, degradation) of the translation quality can be measured over time.
The main problem throughout the introduction of MT was to demonstrate the usefulness and added
value of MT to management. With usefulness being in most cases equivalent to cost savings, the question to be answered was how much money could be saved using machine translation. Or perhaps
phrased another way:
• How much could be saved in human translation costs, i.e.,
• which texts previously submitted for human translation could now be translated automatically?
• how much faster could employees now produce multilingual texts in-house by using machine
translated text?
• how many dictionary lookups could now be made more eﬃcient by having an online system,
instead of paper dictionaries that need to be replaced from time to time?
• How much could be saved in communication costs now that misunderstandings could be prevented because all internal communication could be translated?
Both types of cost savings were diﬃcult, if not impossible, to estimate before the introduction of MT.
These problems were largely overcome by carrying out a sequence of pilot projects in which an increasing number of users became familiar with MT. By providing a very extensive support model
©2004 LISA and Mike Dillinger. All rights reserved.

LISA Best Practice Guide: Implementing Machine Translation

55

and by establishing a close interaction between the MT team and MT users, the system was gradually
improved to meet user needs.
The support model includes:
• an initial survey addressing the users’ expectations concerning MT
• introductory materials provided before the start of each pilot project (e.g., instructions on how
to use the system)
• frequent customer mailings providing tips and tricks to optimize translation quality
• a survey at the end of each pilot project in order to assess system utilization, user satisfaction
and pending issues
The pilot phases were a great success since users were very satisﬁed with the system, and the translation volume exceeded all expectations. The extensive security requirements, especially within the
banking/ﬁnance sector, were met. Furthermore, some of the cost issues were addressed on the basis
of the experience gained during the pilot phases.
On the basis of the results, CLS management committed to a full integration of the system into the
company’s intranet and the oﬀering of the service worldwide.

Additional Technical Information
File Formats Supported
Text (.txt), Word (.rtf, .doc), Web (HTML), XML; other formats supported upon request.

Available Deployment Options
ASP (service hosted by CLS) with browser-based access (no client-side installations necessary). Offered as an Internet-/Intranet service, and secure connections are available. Can be installed on the
client’s server upon request.

Integration
The tool integrates with translation memories (e.g., TRADOS) and has import-/export interfaces for
term banks (e.g., Multiterm).

Customization
The end user can conﬁgure the system according to
•
•
•
•

translation direction
the subject dictionary used
translation alternatives displayed
language in which the user interface is displayed

In addition to these options, the system administrator may also conﬁgure additional user choices
such as:
©2004 LISA and Mike Dillinger. All rights reserved.

LISA Best Practice Guide: Implementing Machine Translation

56

• preference of certain grammatical choices
• selection of speciﬁc translation memories
Furthermore, the system provides open and well-documented APIs for integrating additional functionality, e.g.
• workﬂow integration
• billing

Standards Supported
•
•
•
•

system access through a SOAP interface
client server architecture using the http/https protocol
HTML, XML translation formats
.rtf as an industrial standard for document formats

Please visit the CLS web site at http://www.cls.ch for more information.

©2004 LISA and Mike Dillinger. All rights reserved.

LISA Best Practice Guide: Implementing Machine Translation

57

CASE STUDY: Machine Translation Fulﬁlls High Volume Demand
(ESTeam)

This case study describes how ESTeam succeeded in taking on the challenge of blending machine translation and translation memory to develop an example-based MT system to handle more than 70 million
words in 11 languages for one of its global customers.

The High Volume Challenge
ESTeam’s client is a legal and intellectual property (IP) information provider doing business on a
global scale. The client recognized early on that providing a translation of its information resources,
laws and IP material (such as trademark descriptions) would provide an advantage over the competition. Its databases contain in excess of 70 million words per language and are updated on a daily
basis with new materials in Danish, Dutch, English, Finnish, French, German, Italian, Norwegian
(including both modern Bokmål and an older form known as Riksmål), Portuguese, Spanish and
Swedish. The main focus is on English as the target language, but the client must be able to provide
translations of laws and IP materials written in any one of these eleven languages into any of the other
languages—for a grand total of 110 possible language combinations!
The client’s content is stored in a large database that is used to provide information to its customers
worldwide in the form of online access or distributed reports. Translations must be sent to users without
human intervention, and they must be provided in a very short period after they are requested—a delay
of greater than two minutes between request and delivery of a translation, regardless of size, is considered unacceptable. The delay in production of a report is, thus, an economic loss to the company.

An Automated Solution That Blurs the Distinction Between Translation
Memory and MT
Thus, a fully automated solution was required. Because of the unique requirements for speed and also
because of the huge volume of materials that must be translated (theoretically 7,700,000,000 words),
human translation would be unable to meet the mission requirements, and would also be prohibitively expensive. Due to the legal importance of the material being translated, quality and accuracy
were prime concerns, and there was a very low tolerance for error. However, because the texts were
limited in domain, they represented an ideal candidate for machine translation.
ESTeam and its client faced the challenge that no existing MT systems could handle all of the 110 language pairs, nor was the quality of general-purpose MT good enough to meet the need. Development
of rule-based MT systems for each language pair would have taken too long and been prohibitively
expensive. Therefore, the decision was made to implement a new system starting with a few languages, where the average cost per language into all directions was €200,000.
©2004 LISA and Mike Dillinger. All rights reserved.

58

LISA Best Practice Guide: Implementing Machine Translation

ESTeam Created Several New Inventions for This System
ESTeam went to work on building an example-based MT system, using corpus-based statistical principles—essentially blurring much of the distinction between translation memory and MT. This required the developers to align translations from non-parallel resources in all the languages, which was
not feasible at that time. Therefore, ESTeam developed a new method using MT to access the target
language equivalents. The repetition at a sentence level was not high enough to hit eﬀectively; in fact,
every text was a single sentence that could be several pages long. Therefore, ESTeam decided to go
below the sentence level and build a phrasal translation memory working with an MT lexicon to ﬁll
the gaps. Several new inventions were created during the development, including the following:
• a linguistic fuzzy match where no post-editing is required
• an automatic machine translation correction method to enhance the quality when processing is
done using the MT lexicon alone
• full multilingualism, whereby one language pair is added to the system to provide translation
into all of the others.
The very limited required turnaround time on even lengthy documents required that texts be translated prior to their actual request, ideally upon new additions to the database. Thererfore, ESTeam’s
created a document database where each phrase was indexed to access the translation at extremely
high speeds. This approach allowed for existing translations to be used in the databases where they
already existed, and for new translations to be added as needed. This approach had the advantage that
new languages could be added with a minimum of development.
The translation results were tested intensively prior to going into full production. The ﬁrst test was to
compare the translation quality of the software compared to a human translation of the same text. A
number of documents were selected and sent for translation to a translator with domain terminology expertise. The results were measured according to time, cost and translation quality. The ﬁrst two
were easily won by the software, but the surprise was that translation quality of the human translation
was reduced by the fact that the translator omitted the translation of one line in the source text. Since
this was a legal document, this was a more serious error than any made by the system.

A Resounding Success With Customers
ESTeam’s client then selected a number of their steady customers for a pre-production study. The
customers were asked what level of accuracy they were willing to accept, with most replying 90-100%.
They used the output for six months and were then surveyed about the results. They were asked (1) if
they wanted the service stopped, and if not, (2) if they were willing to pay for it and (3) how much. All
customers conﬁrmed that they were willing to pay to keep the service.
The solution went into production with a number of languages in 1998 and has been running continually with no downtime since then. Several languages have been and continue to be added. ESTeam
has taken this technology one step further in its new product, the ESTeam Translator, nominated for
the IST Prize 2004. When publication quality is required, the system provides high quality translation
coverage by applying translation memory at both the sentence and phrasal levels before outsourcing
©2004 LISA and Mike Dillinger. All rights reserved.

LISA Best Practice Guide: Implementing Machine Translation

59

the text for human translation. When browsing quality is required, existing translation memory resources are applied at the sentence and phrasal levels before applying MT.
Please visit ESTeam’s web site at http://www.esteam.gr for more information.

©2004 LISA and Mike Dillinger. All rights reserved.

LISA Best Practice Guide: Implementing Machine Translation

60

CASE STUDY: MT for Speech-to-Speech Translation (Spoken
Translation, Inc.)

By employing interactive techniques while integrating state-of-the-art dictation and machine translation
programs, STI has produced the ﬁrst commercial-grade, speech-to-speech translation system that can
achieve broad coverage without sacriﬁcing accuracy.

Product Description
Spoken Translation, Inc. (STI) develops and licenses technology for cross-lingual communication. The
company aims to enable wide-ranging conversations across language barriers whenever and wherever
they are needed, through software solutions combining automatic translation, speech recognition and
related technologies. The translated conversations are multimodal: input can be typed, while speech
recognition, handwriting or touch screens can also be used; and synthesized spoken output is always
available. Conversations can be face-to-face, for example when speakers pass a tablet or laptop PC
back and forth; but sessions can also be online, since all system components can be server-based.
Using STI systems, doctors and nurses can communicate directly with patients speaking other languages; businesses can expand their potential customer base by communicating with contacts who
do not speak their language and by providing better service to overseas customers; international
non-proﬁt and governmental organizations can reach out to more of their constituents in their own
languages; police and military staﬀ can coordinate their activities with allies from other countries;
language students can correspond with their counterparts abroad; and people everywhere can reach
across borders to friends and family.
The company’s proprietary technologies allow users to interactively monitor and correct speech recognition and machine translation, yielding unprecedented quality and user conﬁdence. As a result, STI’s
systems can translate ﬂexible, open-ended conversations including spoken input, rather than being limited to pre-packaged translations of ﬁxed phrases, or rough translations within narrow domains.
The company’s business consists of two channels:
• an OEM business, in which it licenses its technologies for interactive monitoring and correction
of dictation and translation (discussions are now underway with two major Japanese technology
and communication ﬁrms);
• and a products business. The ﬁrst product will address the health-care sector, and the company
will soon beta test a tablet-PC-based system designed to help Spanish-speaking patients to communicate with English-speaking caregivers at several major hospitals in the U.S.

©2004 LISA and Mike Dillinger. All rights reserved.

LISA Best Practice Guide: Implementing Machine Translation

61

Addressing the Need for Reliability, Accessibility and Aﬀordability
Machine translation is the core component of STI communication systems, since its aim is precisely
to aid cross-lingual communication—most typically in real-time conversations, but sometimes for
short-term dialogues as well, for example via e-mail.
Past methods for enabling cross-language dialogues have, of course, included human interpreters for
live meetings and phone calls. However, interpreters are sometimes unqualiﬁed, and when qualiﬁed,
are prohibitively expensive for spontaneous or informal communications. Human interpreters cannot
always be available 24/7 or upon short notice. They add another listener to conversations that may be
conﬁdential. They may interpret inconsistently, and generally provide no written transcript. It is diﬃcult
for them to give clients an independent means of verifying their accuracy. Perhaps most important, human interpreters cannot contribute to the increasingly preferred methods of business communication,
i.e., email, instant messaging and live chat. An additional practical limitation is that they ordinarily need
to be physically present where their services are needed. (Recently, however, a range of experiments with
audio and videoconferencing has begun. These approaches to long-distance human interpreting are
promising, and no doubt will prove to oﬀer the best solution for some situations—but not for others. By
themselves, they cannot be expected to address all of the issues just enumerated.)
Other approaches to enabling cross-language conversations involve the use of existing machine translation tools for translating chat or emails. However, the quality of translation is often unreliable. Human translators or translation service companies have also been employed for short-term written
communications; but this mode, too, is expensive and delays communication.
Of course, no technology can meet every possible need. STI’s solutions are not intended for life-anddeath communications, and there are many other situations in which an interpreter with a human
touch and human brain will remain invaluable. Nevertheless, the company’s systems can help to address the needs for reliability, privacy, record keeping, consistency, veriﬁability, convenient accessibility and aﬀordability in translating or interpreting everyday conversations.

Extensive Component Integration
STI’s conversational translation systems are in fact extended exercises in component integration. Machine translation components from several vendors have been ﬁtted with front ends for input (via
typing, speech, handwriting or touch screen) and with back ends for text display and speech synthesis. As mentioned, proprietary tools for interactive monitoring and correction add value to the mix.
This integration is nontrivial, since components are written in various programming languages and
dialects. Further, many components were originally intended to run as standalone applications, and
thus require adaptation for server-based use. Currently, STI resolves these issues by embedding all
translation and speech recognition components within Microsoft’s .NET environment. In other
words, it creates software layers in managed code within which to encapsulate the components (often
originally produced in unmanaged code, e.g. C++).

©2004 LISA and Mike Dillinger. All rights reserved.

62

LISA Best Practice Guide: Implementing Machine Translation

Quality: Balancing the Twin Goals of Accuracy and Broad Coverage
STI applications of automatic translation are intended for serious uses, e.g. in health-care, business,
the military, etc. Thus, it is essential that users have conﬁdence in the translation quality. At the same
time, if conversations are to proceed relatively freely, they must not be tightly restricted within narrow
domains.
Particularly when speech input is enabled, the twin goals of accuracy and broad coverage have almost
always been in opposition. Until now, speech translation systems have gained tolerable accuracy only
by sharply restricting both (1) the range of topics which can be discussed and (2) the sets of vocabulary
and structures which can be used to discuss them. The essential problem is that both speech recognition and translation technologies are still quite error-prone. While the error rates may be tolerable
when each technology is used separately, the errors combine and even compound when they are used
together. The resulting translation output is generally below the threshold of usability—unless restriction to a very narrow domain supplies suﬃcient constraints to signiﬁcantly lower the error rates of
both components.
As mentioned, STI’s approach has been to concentrate on interactive monitoring and correction of
both technologies. First, users can monitor and correct the speaker-dependent speech recognition
system to ensure that the text that will be passed to the machine translation component is completely
correct. Voice commands (e.g. Scratch That or Correct <incorrect text>) can be used to repair speech
recognition errors. While these commands are similar in appearance to those of IBM’s ViaVoice or
ScanSoft’s Dragon NaturallySpeaking dictation systems, they are unique in that they remain usable
even when speech recognition operates on a server. Thus, they provide for the ﬁrst time the capability
to interactively conﬁrm or correct wide-ranging text that may be dictated from anywhere.
Next, during the MT stage, users can monitor, and if necessary correct, one especially important
aspect of the translation—lexical disambiguation. The problem of determining the correct sense of
input words has plagued the machine translation ﬁeld since its inception. In many cases, the correct
sense of a given term is in fact available in the system with an appropriate translation, but for one
reason or another it does not appear in the output. Word-sense disambiguation algorithms being developed by research groups have made signiﬁcant progress, but still often fail, and the most successful
have yet to be integrated into commercial MT systems. Thus, no really reliable solution for automatic
word-sense disambiguation is on the horizon for the short- to medium-term.
STI’s approach to lexical disambiguation is twofold. First, it supplies a specially controlled back translation, or translation of the translation. Using this paraphrase of the initial input, even a monolingual
user can make an initial judgment concerning the quality of the preliminary machine translation output. To make this technique eﬀective, STI uses proprietary facilities to ensure that the lexical senses
used during back translation are appropriate.
In addition, in case uncertainty remains about the correctness of a given word sense, STI provides a
proprietary set of Meaning Cues™—synonyms, deﬁnitions, etc.—which have been drawn from various resources, collated in a unique database (called SELECT™), and aligned with the respective lexica
of the relevant machine translation systems. With these cues as guides, the user can select the preferred meaning from among those available. Automatic updates of translation and back translation
©2004 LISA and Mike Dillinger. All rights reserved.

LISA Best Practice Guide: Implementing Machine Translation

63

then follow. The result is an utterance that has been monitored and perhaps repaired by the user at
two levels—those of speech recognition and translation.
Importantly, the system progressively adapts to speciﬁc users, both for speech recognition and translation preferences. For speech recognition, learning involves continual updating of a personal audio
model. For translation, an individual user can indicate, when selecting a word meaning, that it should
be reused whenever the same word is seen throughout the current session, or until further notice.
Thus, over time, the need for correction should diminish.
By employing these interactive techniques while integrating state-of-the-art dictation and machine
translation programs (Philips Speech Processing for speech recognition, Word Magic [Spanish MT]
and Lingenio [German MT], and ScanSoft for text-to-speech), STI has been able to build the ﬁrst
commercial-grade, speech-to-speech translation system which can achieve broad coverage without
sacriﬁcing accuracy.

A Usage Example
When run on a Motion Computing Tablet PC, the system has four input modes: speech, typing, handwriting and touchscreen. To illustrate the use of interactive correction for speech recognition, assume
that the user has clicked on the microphone icon onscreen to begin entering text by speaking.
The results of automatic speech recognition are good, but often imperfect. Thus, if the input sentence
were “What seems to be the matter today?” the preliminary speech recognition result might be “What
sees to be the matter today.” “Seems” has been incorrectly transcribed as “sees.” In this case, the user can
perform voice-activated correction by saying “Correct sees.” A list of alternative speech recognition candidates then appears, including “seems,” “seem,” “sings,” etc. The user can select the correct alternative
in this case by saying, “Choose one,” thus yielding a corrected sentence. (If the intended alternative is
not among the candidates, the user can supply it manually by typing on a standard keyboard, by using a
touchscreen keyboard or by writing with a stylus for high-accuracy handwriting recognition.)
The spoken (or clicked) “Translate” command produces a translation of the corrected input. Also
provided are a back translation (the translated sentence re-translated back into the original, as explained above) and an array of Meaning Cues giving information about the word meanings that were
used to perform the translation. The user can use these cues (synonyms, deﬁnitions, examples, etc.)
to verify that the system has interpreted the input as intended. The back-translation may indicate
that the system has misunderstood—for instance, “What appears to be the substance today?” would
indicate that “matter” had been understood as meaning “substance.” Presumably, this is not what the
user intended. By clicking on the word in the Word Meanings list, he or she can bring up a new window containing alternative word meanings, each indicated by suitable cues. In the present example,
another meaning for “matter” might be indicated via synonyms as “problem, trouble, diﬃculty” with
the example “What is the matter with you?” etc.
When a new word meaning has been chosen from this list, e.g. the “problem” meaning in this case,
the system updates the display in all windows to reﬂect that change. In this example, in addition to
©2004 LISA and Mike Dillinger. All rights reserved.

64

LISA Best Practice Guide: Implementing Machine Translation

an updated translation, the new back translation might now be “What appears to be the problem today?”—close enough, perhaps, to the intended meaning.
When the user is satisﬁed that the intended meaning has been correctly understood and translated by
the system, the system’s Send button can be used to transmit the translation to the foreign-language
speaker via instant messaging, chat or on-screen display for face-to-face interaction. At the same
time, synthesized speech can be generated, and if necessary transmitted, thus completing the speechto-speech cycle.

Challenges Overcome
STI’s greatest challenge in developing interactive monitoring and correction capabilities for translation has related to the Meaning Cues (synonyms, deﬁnitions, examples, etc.) that help users to recognize, and if necessary, correct lexical ambiguity errors. STI has had to build a database of meaning
cues accurately indexed by word meaning, although cues may come to it through a variety of disparate resources. Since the time required for this construction would be prohibitive if it were carried
out by hand, considerable automation has been required. STI has, in fact, been able to correlate cues
automatically with more than eighty percent accuracy using proprietary techniques and has built efﬁcient developer tools for handling the remaining cases.
Second, STI has had to align the resulting proprietary database with the lexicons of several machine
translation software vendors. This task, too, has been carried out semi-automatically with high accuracy.
Finally, STI has been required to work with MT vendors case-by-case to retroﬁt their respective translation engines so that (1) word senses can be captured and displayed to users following preliminary
translations, and (2) selected word senses can be passed to the engine to be used as constraints during
subsequent translation processes.

What the Future May Hold
Since STI’s principal concern to date has been with the translation of real-time or short-term conversations, rather than with document translation, it has not yet developed elaborate workﬂow tools, e.g.
for version control or for tracking document changes. However, some potential clients in the healthcare ﬁeld have already indicated a desire to extend STI’s translation tools for generating relatively
short-lived documents, e.g., materials giving directions around hospitals, providing basic instructions
or making announcements.
On the other hand, there has been from the outset an obvious need to transcribe conversations – ﬁrst,
in order to keep users oriented within their ongoing dialogues, and secondarily for record-keeping
(likely to prove important for liability and conﬁdentiality concerns in health-care situations). Accordingly, STI is now developing tools for displaying and recording such running records. The current
user interfaces resemble those used for instant messaging or chat. Saving protocols for transcripts will
allow users to enter preferred saving locations as part of personal registration proﬁles; standard Save
As… facilities will also be provided.
©2004 LISA and Mike Dillinger. All rights reserved.

LISA Best Practice Guide: Implementing Machine Translation

65

Some users will be too busy or impatient to interactively monitor and debug each utterance. Doctors
are notorious in this respect. In compensation, they frequently reuse the same utterances repeatedly.
Thus, it has become clear that translation memory or “Favorites” facilities are needed. Using them,
a busy user can opt to save an utterance that has just been veriﬁed, or can prepare useful translations oﬀ-line in advance. Later, during important but overstressed interchanges, he or she can employ
menus and lookup facilities to quickly ﬁnd and replay the stored utterances.
In the meantime, users will be well served. By employing interactive techniques while integrating
state-of-the-art dictation and machine translation programs, STI has produced the ﬁrst commercialgrade, speech-to-speech translation system that can achieve broad coverage without sacriﬁcing accuracy.
Please visit the STI web site at http://www.spokentranslation.com for more information.

©2004 LISA and Mike Dillinger. All rights reserved.

The Localization Industry Standards Association
Domaine en Prael • CH-1323 Romainmotier • Switzerland
Tel: + 41 (24) 453 2310 • Fax: +41 (24) 453 2312 • lisa@lisa.org

