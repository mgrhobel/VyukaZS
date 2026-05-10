---
title: "primer3_en.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/zdroje/LISA/primer3_en.pdf"
date: 2010-01-31
type: PDF (text-based)
---

n • Boston • Brussels • Budapest • Cairo
Dublin • Estoril • Geneva • Heidelberg •
• Monterey • Mountain View • Newport
The
alt Lake
City Globalization
• San Francisco • San Jose •
The Hague • Tokyo • Valbonne • Vienna
Industry
Primer
• Yokohama
• Amsterdam
• Arlington •
dapest • Cairo • Chicago • Copenhagen
• Heidelberg • London • Luxembourg •
ViewAn
• Newport
Beach
• Paris your
• Prague
introduction
to preparing
cisco business
• San Jose
• products
Shanghaifor• Singapore
•
and
success
bonne • Vienna • Warsaw • Washington
in international markets
• Arlington • Beijing • Berlin • Boston •
penhagen • Dromoland • Dublin • Estoril
mbourg • Madrid • Mainz • Monterey •
• Prague • Runnymede • Salt Lake City
ingapore • St. Petersburg • The Hague •
Washington DC • Windsor • Yokohama •
n • Boston • Brussels • Budapest • Cairo
Dublin • Estoril • Geneva • Heidelberg

The Globalization Industry Primer was written by Arle Lommel (LISA) and
edited by Rebecca Ray (LISA). LISA thanks the following individuals for
their contributions to the Primer: Deborah Fry, Alex Lam, Peter Stumpf,
Alison Rowles and William J. Sullivan, as well as LISA members, past and
present, who have contributed to the success and growth of LISA and the
globalization industry.

The Globalization
Industry Primer
An introduction to preparing your
business and products for success in
international markets

© 2007 • The Localization Industry Standards Association • All rights reserved

Dear Reader,
The Globalization Industry Primer is based on the two editions of our successful Localization Industry Primer. The change in name is more than cosmetic, however. The renaming of the Primer reflects the growing realization
that globalization cannot be separated from business as normal: globalized
enterprises are global in every aspect of their operations, and localization is
just one part (albeit an important one) of the picture.
Critics of globalization often view it as a homogenizing force, but the only
way for an enterprise to be global is to be simultaneously local in the markets in which it does business. By respecting local languages and cultures at
every level—in their products, services, documentation, customer support,
marketing, maintenance procedures, business practices, etc.—global enterprises paradoxically expand the options available at the local level. As this
enterprise view of globalization has spread, localization has moved further
up the production chain. Between 2001 and 2006 LISA’s members reported
productivity (and ROI) gains of approximately 250% on globalization efforts, an improvement made possible only by the shift from a focus on localization to a focus on globalization.
Since LISA’s founding in 1990 globalization and localization have gone from
being seen as part of the software industry to playing a fundamental role in
almost every vertical industry. Its growth has taken it from humble beginnings to an estimated $30 billion per year and growing industry.
This Primer is designed to introduce you to the concepts of globalization,
internationalization, and localization, along with their roles in international
business today. It presents the history and current role of the industry and
will help you understand the business opportunities that globalization of© 2007 LISA • All rights reserved

iv

• LISA Globalization Industry Primer •

fers to enterprises today. It describes the major parties and technologies involved in globalization and helps you understand the roles they play. It also
provides reference information needed to better understand the technical
aspects of globalization.
The Globalization Industry Primer distills the wisdom and knowledge of industry leaders, most of whom are members of LISA, the Localization Industry Standards Association (http://www.lisa.org). This non-profit organization provides a forum in which organizations can exchange information
on globalization best practices, strategies, standards, and business issues.
We hope that you will find the Primer useful and invite you to join LISA
to learn more about what it takes to prepare your products and services to
ensure international success.
Sincerely yours,

Michael Anobile
Managing Director
LISA—The Localization Industry Standards Association

© 2007 LISA • All rights reserved

• LISA Globalization Industry Primer •

Contents
Introduction

1

A Global Context
History of the Globalization Industry
How Big Is the Globalization Industry?

3
6
8

Localization
Linguistic Issues
Physical Issues
Business and Cultural Issues
Technical Issues

11
12
12
14
14

Internationalization

17

Planning for Globalization
Product Requirements Analysis (Global/Local)
Assessing Market Potential
Internationalized Product Design
Internationalized Product Development
Internationalized Product Testing and Quality Assurance
Product Localization
Localized Product Testing and QA
Local Product Marketing, Support and Feedback
Starting It All Over Again

19
20
21
21
24
24
25
25
26
26

Global Business Priorities
Strategic and Maintenance Markets
Languages

27
27
28

Market Players
Clients
Service Providers and Consultants
Tools Providers
Global Scope

31
31
33
34
35

© 2007 LISA • All rights reserved

vi

• LISA Globalization Industry Primer •

Technologies and Tools
Terminology Management Systems
Translation Memory (TM)
Machine Translation (MT)
Localization Workbenches
Global Content Management Systems (GCMS)

37
37
38
38
39
39

Evaluating and Ensuring Success

41

Best Practices and Standards
Standards for Quality Management
Standards for Linguistic Data Interchange
Business Practices

43
43
44
45

Future Challenges
Technology and Organizational Processes
Strategic Importance
Managing Global Content, Not Projects
International Support
Increased Focus on Value Creation

47
47
47
48
48
48

Glossary

49

About LISA
What is LISA?
What Are Its Goals?
What Are LISA’s Values and Principles?
What Services Does LISA Offer?
How Do I Join LISA?

53
53
53
53
54
55

Additional Resources
The LISA Web Site – www.lisa.org
Globalization Insider – www.localization.org
LISA QA Model
Surveys
Other Standards Bodies
Books

57
57
57
57
58
58
59

© 2007 LISA • All rights reserved

• LISA Globalization Industry Primer •



Introduction

Driven largely by the unprecedented mobility of information enabled by
the Internet, fewer and fewer companies can think of business in strictly
national terms. Instead, they are finding that they must focus on international business to be competitive even in their home markets. The path to
effectively engaging international markets is not always clear however. It is
not enough to translate a few manuals and a product’s user interface. Organizations must account for a number of business issues if they are to succeed in international markets: local languages, currencies, business practices,
technical requirements, and cultural preferences all must be dealt with, as
well as marketing and sales and technical support for local markets.
Globalization, as used in this Primer, refers to all of the business decisions and
activities required to make an organization truly international in scope and outlook. Globalization is the transformation of business and processes to support customers around the world, in whatever language, country, or culture
they require. As long as international business is seen as an add-on process,
organizations will never achieve their global potential.
This Primer will help you understand the process of globalization and the
key technical processes of internationalization and localization that make
globalization possible. It will describe the business and technical issues involved in globalizing an enterprise and introduce the key companies that
play a role in this daunting task.

© 2007 LISA • All rights reserved



• LISA Globalization Industry Primer •

© 2007 LISA • All rights reserved

• LISA Globalization Industry Primer •



A Global Context

Since the late 1980s, the world has witnessed tremendous economic, political, technological, and social changes. These changes are often lumped
together under the term globalization. The shift towards international business integration is felt at every level around the world. Whereas a century
ago most goods were produced for local or regional consumption, today it is
common for a shopper in the United States to buy fruit grown in Chile or
a consumer in Brussels to buy clothes made in China. Services once based
on face-to-face interaction are now, thanks to the Internet, often carried out
in different countries or on different continents from where the consumer
happens to be. Even physical products are composed of parts from all over
the world. A single model of consumer electronics may have components
made in 20 different countries and be sold in 150.
Globalization is not without its opponents, many of whom feel that the
international expansion of businesses is leveling local cultures and erasing
local differences. As UN Secretary General Kofi Annan put it in his 1999
report to the U.N. General Assembly, however, globalization is “an irreversible process, not an option.” What we do have is the option to globalize
responsibly, in a way that provides value to people around the world and
that respects their local cultures, languages, business conventions and ways
of life.
The Localization Industry Standards Association (LISA – www.lisa.org)
and its members are committed to a positive approach to globalization. This
means that its members focus on responding to local needs, languages and
cultures to deliver a variety of high quality good and services, thus offering
consumers around the world more choices and better quality. The process
© 2007 LISA • All rights reserved



• LISA Globalization Industry Primer •

of localization, as described in this Primer, is what allows globalization to
respect the local practices and customs by adapting to and serving particular
markets and people.
Key factors driving the development of globalization include the following:
•

•

•

•

The liberalization and deregulation of key industries, such as
telecommunications and power generation, coupled with a redefinition of the role of the state. This process has fueled private investment and global competition, at the same time that it has provided
a political and economic framework for technological innovation.
The emergence of capitalism and free trade as the dominant economic model. Physical and political barriers to communications
and trade have fallen throughout the world. Countries (and companies) previously unable to compete globally can now do so with
relatively little up-front investment, while countries previously offlimits to foreign competitors now have to open up or risk having
their enterprises falling behind.
At the same time, regional economic and political communities have emerged in the Americas, Europe and Asia. Increasing
numbers of countries are realizing the advantages of free trade and
flexible markets. Key initiatives include those of the World Trade
Organization (WTO), which aims to establish ground rules for
free trade in products and services, and the protection of intellectual property rights.
The creation of a seamless worldwide technical and logistics infrastructure. PCs, the Internet, and fiber-optic, wireless and satellite networks all have reduced the cost of communications and
made it easy to connect around the world. The result has been an
unprecedented level of business and personal interconnectivity, as
distance and geography have become largely irrelevant. At the same

© 2007 LISA • All rights reserved

• LISA Globalization Industry Primer •



time, there has been a quantum leap in the speed at which business
is conducted, and therefore in required reaction times.
The Internet revolution offers companies the following:
• A low-cost, worldwide advertising and marketing platform.
By setting up a web site, even small companies can advertise
themselves, their products and their services to an audience
that potentially extends around the world. In addition, they
can use their web sites to directly gather information on customer needs in real time.
• A low-cost, worldwide sales platform. The rise of e-commerce
solutions enables companies to sell goods direct from their
web sites. Payment is typically made by credit card or by debiting an existing offline account, and alternative payment means
suitable for specific markets have emerged.
• A low-cost, worldwide distribution platform. Any product
that can be made available as electronic data (e.g., software,
books and other text-based information, music, films and so
on) can also be directly distributed via the web. Companies
and their customers now expect materials to be available immediately at any time of the day anywhere in the world. This
level of expectation is made possible only through the Internet.
In the case of physical products such as hardware, cars, etc.,
worldwide logistics providers now offer efficient international
distribution. Shenzhen (China) is now closer in many ways to
Los Angeles (U.S.) than Detroit (U.S.).
• A low-cost, worldwide support platform. Companies serving a newly acquired international customer base can minimize support issues by providing registered customers with
information and contacts via their web sites. Moving support
to web sites can drastically reduce support costs. At the same
time, it introduces management challenges since companies
© 2007 LISA • All rights reserved



• LISA Globalization Industry Primer •
must now maintain current versions of support materials for
multiple languages.

These radical changes in economics have leveled the playing field, allowing
even small companies to compete outside their traditional markets. This
also means, however, that their competitors can also take advantage of the
same opportunities. Companies can no longer assume that years of investment in a market or previous customer loyalty will protect them from more
agile competitors that better meet customer needs. Enterprises that are slow
to bring new products to market, or that fail to reinvent existing ones, may
well find their place already taken. Global exposure means global competition, while “speed of innovation” leads to “speed of imitation.” Competitors
can easily research and often copy new features or products within days.
At the same time, the liabilities of economic globalization are becoming increasingly apparent as individuals and organizations highlight the environmental, cultural and personal impacts of globalization. Localization is what
allows the benefits of globalization to accrue not only to large companies
and powerful nations. Localization lets speakers of less common languages
enjoy access to the same products and resources that those in major markets use. It allows the flow of products and information to be two-way, as
dominant countries receive goods and services from smaller countries that
have traditionally had no access to their markets. When companies localize
their products and services, they help to redress economic inequalities and
to create a better world in which no one is left out.
History of the Globalization Industry
Globalization is not an easy task. As a result, a distinct industry has grown
to facilitate product and service globalization. This industry (often called
the localization industry because of the importance of localization in any globalization effort) arose in the 1980s from roots in the computer software industry. Unlike most physical products, software was easily portable around
© 2007 LISA • All rights reserved

• LISA Globalization Industry Primer •



the world and relied heavily on textual content, meaning that it had to be
adapted for local languages. While other industries did make use of translation services and sell into other markets, there was no industry specifically
devoted to business globalization issues prior to the rise of the software
industry.
For a number of years, localization served as a way for software developers
to increase sales by entering worldwide markets. A body of companies that
specialized in the translation of software and the accompanying technical
tasks (resizing dialog boxes, adapting user interfaces, etc.) appeared during
this time. This process came to be known as localization, to distinguish it
from translation, which focused on communicating the meanings and messages of words.
In 1990, when LISA was founded, localization was still primarily a function of the software industry, although some expansion was occurring into
consumer electronics, medical equipment, and a few other technical fields
in which software components were becoming increasingly important. As
late as 2001, however, the bulk of the clientele of most localization service
providers (LSPs) came from the computer software and hardware industries. As more and more products gained significant information technology
components, localization became increasingly common. Leading companies in other industries began to see the benefits of localization in terms of
increased sales, lower support costs and the ability to access new markets
more quickly.
Today, localization is no longer a function of any one vertical industry, or
even of a few. LISA’s members include manufacturers of automobiles, heavy
equipment and consumer goods, retailers, media and entertainment companies, legal firms, pharmaceutical companies, financial institutions, governmental and non-profit bodies, food services companies, and companies
in many other vertical segments. While software localization is still a key
© 2007 LISA • All rights reserved



• LISA Globalization Industry Primer •

source of revenue for most LSPs, software is now often simply one part
of much larger projects that may include localization of hardware, documentation and web content, along with many other components. Thus, the
number of localization projects and their complexity has risen exponentially
since LISA’s founding.
How Big Is the Globalization Industry?
The definitive size of the globalization industry is uncertain. The expansion of globalization beyond the vertical sectors of hardware and software,
coupled with the tendency for globalization-related tasks to be treated as
project costs rather than as a line item in corporate budgets, makes it very
difficult to assess the size of these efforts. Estimates vary by several orders
of magnitude. In 2001, LISA published a very conservative estimate that
worldwide spending on localization was approximately $5 billion USD per
annum, and perhaps as high as $15 billion. To date, there has been no single
definitive survey addressing worldwide spending on localization-related
spending, so the size of the worldwide market for localization is uncertain.
However, an examination of the revenues of just those 2006 Global Fortune
500 companies that LISA knows to be actively localizing their products or
services yields annual total revenues of approximately $5.9 trillion (with
profits of $365 billion). If only 10% of their total revenues are derived from
international sales dependent upon localization (i.e., sales that would not
have been made were products or services not localized), this means that
$590 billion of their revenues would not have been achieved without localization. Their net 2006 profits would have been reduced to -$225 billion. For
these companies, localization is not an option, it is an imperative.
(Note that the portion of revenues from international markets estimated
above is likely to be quite low. In 1998 David Brooks of Microsoft reported
that:

© 2007 LISA • All rights reserved

• LISA Globalization Industry Primer •



In [Fiscal Year] 1998 more than 60% of Microsoft’s revenues came
from markets outside of the United States. The majority of these
revenues come from non-English speaking markets, and a key
component of Microsoft’s international strategy has been to lead
the industry in the delivery of localized products to these markets.
In [Fiscal Year] 1998, Microsoft revenue from localized product
exceeded $5 billion. Only five years ago, these figures were a fraction of what they are today, and as revenues have grown, so has
Microsoft’s investment in localization.
With some LISA members’ international revenues hovering around 70%,
it is clear that localization is a key component of their business strategies.
Without localization, they could not maintain positions of world leadership.)
Based on interviews with LISA members and other companies, globalization experts, and companies just beginning to engage in international business, LISA believes that industry size is only half of the picture, and that any
complete view of the globalization industry needs to examine the revenues
unlocked through globalization. In 2001, LISA members reported that, on
average, they achieved $10 of additional revenue for every $1 spent on localization. Since that time, LISA members have almost universally reported
15–25% annual productivity increases on their localization spending. This
means that today companies are receiving approximately $25 of additional
revenue for every $1 spent on localization, placing the annual spending of
the International Fortune 500 on globalization-related services at a minimum of approximately $24 billion. When other companies (as well as governmental bodies, NGOs, and non-profits) are added in, the market is even
larger, and it continues to grow every time a new product, service or technology is created, or a language reaches “official status.”

© 2007 LISA • All rights reserved

10

• LISA Globalization Industry Primer •

While we cannot provide a definitive annual figure for the total localization market, we can estimate total localization expenditures by industry in
2006 to have been approximately $30 billion. Whatever the actual market
size may be, it is clear that globalization represents a major opportunity for
companies providing the services to support it and for companies looking
for a cost-effective means to increase their sales.

© 2007 LISA • All rights reserved

• LISA Globalization Industry Primer •11

Localization

Localization is often treated as nothing more than “high-tech translation,” but
this view does not capture its importance, its complexity, or what actually
takes place during localization. It also hides the fact that localization must
be integrated with other business processes if it is to be effective. Localization is an integral part of globalization, and without it, other globalization
efforts are ineffective.
So what exactly is localization if it isn’t simply translation? Localization is
the process of modifying products or services to account for differences
in distinct markets.
While this definition sounds simple, it actually impacts many business and
technical issues and requires a good deal of expertise to implement successfully. Localization involves the adaptation of any aspect of a product or service that is needed for a product to be sold or used in another market. This
process significantly impacts both technical and business functions within
organizations. This includes how sales are made; how products and services are designed, built and supported; how financial reporting systems are
implemented; and so on.
While there is overlap between translation and localization, localization
generally addresses significant, non-textual components of products or services in addition to strict translation. Localization commonly addresses the
following issues:

© 2007 LISA • All rights reserved

12

• LISA Globalization Industry Primer •

Linguistic Issues
Almost any product or service that will be sold to individuals who do not
speak the language in which it was created will require linguistic adaptation.
For example, a piece of computer software will require translation of the
textual components of the user interface, online help, user documentation,
installers, etc. Beyond the product itself, business needs will require translation of marketing and product collateral materials, web pages, and support
materials, and perhaps training documents, internal service bulletins, and
other similar components. For media or informatics products, linguistic
aspects of localization may also include dubbing and adaptation of speechbased audio components.
While translation of text generally constitutes the bulk of a localization
project, it is seldom the only component and may directly impact other aspects of product design. For instance, a product’s user interface may require
modification to support characteristics of particular languages or space requirements may need to be adapted for languages that require significantly
more or less space than the original language.
Physical Issues
Beyond translation, localization often involves physical modification to
products or services in order to be acceptable in the local market. These
changes can represent substantial time and cost. Examples of physical localization include the following:
•

•

Automobiles sold in Australia, the United Kingdom, India, Japan
and much of southern Africa (as well as a number of other countries) need to have their steering wheels on the right side of the
vehicle. Cars sold in the rest of the world require that their steering
wheels be on the left side.
Electrical equipment sold in the United States and Canada requires
120-volt power, while most of Japan requires only 100 volts. Most
© 2007 LISA • All rights reserved

• LISA Globalization Industry Primer •13

•

•

of the rest of the world uses 220- or 230-volt power. In addition,
there are thirteen different sorts of electrical plugs used around the
world, meaning that even if a piece of equipment is configured for
the proper voltage, it may still not work with a particular power
system. While it is common now for computers to automatically
adjust for power supply variations, other electrical equipment may
not work or even catch fire if the wrong voltage is used.
Radios and wireless equipment sold around the world must be
modified to conform to local standards and governmental regulations. A product acceptable in one country may not be legal in another one.
Computer keyboard layouts vary from country to country (and
even within a country if more than one language is used). For some
languages, there are multiple ways to input the language (e.g., Chinese and Japanese, or even English). All relevant input methods
must be supported if local users are to have access to the equipment.

Some products may also require adaptation to the average body size of people in a given country or need to be adapted to fit local customs. The first hybrid automobiles sold by Toyota in the United States required larger trunks
(“boots” in the United Kingdom) than their Japanese counterparts because
many American families transported large baby carriages in their vehicles.
While physical modification is not required for most software and user
documentation, physical differences may impact software and documentation that refers to or is embedded in hardware. For example, graphical representations of products or items such as electrical outlets may need to be
adapted to reflect the particular hardware used in specific markets.

© 2007 LISA • All rights reserved

14

• LISA Globalization Industry Primer •

Business and Cultural Issues
Local business and cultural issues can affect all aspects of product design
and localization. Local currencies and accounting conventions must be supported. Local address and telephone number formats need to be supported,
and even the format of names must be appropriate to the target market.
These sorts of issues are often missed by product designers, simply because
they are not aware of them. However, they often make the difference between a product that works and is successful in a market, versus one that is
frustrating for or even rejected by customers.
Other areas of adaptation include colors and graphics that must be adapted
to meet local cultural norms. In addition, product designers must be aware
of political and business issues and local cultural expectations. For example, e-commerce solutions must account for local payment preferences and
methods, i.e., they cannot assume that credit cards will be available everywhere or universally accepted. These issues vary by country and region, so
the importance of local market knowledge cannot be overstated.
Technical Issues
Supporting local languages may require special attention and planning at
the engineering stage. For example, support for East Asian languages that
require thousands of characters requires special design and attention. Other
languages, such as Arabic and Hebrew, are written from right to left, requiring the adaptation of user interfaces and the use of special text-handling
routines in software. Other issues include the order in which text is supported (e.g., in Norwegian, the letter å follows z, while an English speaker
would expect it to appear after a), date formats, the separators used in numbers, etc. Provision must also be made to allow input of text in the local
language. If these technical issues are not considered from the early stages
of project development, they will add substantially to the expense and time
required to localize a product.

© 2007 LISA • All rights reserved

• LISA Globalization Industry Primer •15
Localizing a product is not a trivial task. In practice, not all products are
localized to the same extent. Some products require extensive localization,
while others require less. Research by LISA indicates that, in general, the
more important textual information is to the function of a product and the
more the user must interact with the product, the more localization it will
require. Anti-virus software is a good example: since properly understanding what anti-virus software will do to a computer system is vital when a
virus is encountered, accurate and easy-to-understand localization is vital.
In contrast, a back-end system that requires little interaction with users will
generally require less localization.
In the real world of business today, factors influencing the extent of localization include the nature and scope of the product concerned, the size of the
target market and audience, the length of the product life cycle and anticipated update frequencies, competitor behavior, market acceptance, and national or international legislation. Only after performing a thorough analysis
of these issues, along with the related risks, should a decision not to localize,
or to localize only in part, be made.
Choosing what to localize and into what languages (and how extensively for
those languages) depends on an organization’s specific business priorities
and needs. Localization is thus another business process, not a task done for
its own sake. That said, localization should not be viewed as just a cost, but
as the opportunity cost to unlock new markets.

© 2007 LISA • All rights reserved

16

• LISA Globalization Industry Primer •

© 2007 LISA • All rights reserved

• LISA Globalization Industry Primer •17

Internationalization

Localization does not just happen; it must be planned for. Even in the simplest cases, there will be issues that will work against successful localization.
Here is just a short list of examples for software localization:
(1) graphics may contain embedded text that must be translated
(2) screenshots may appear in a particular language
(3) phone numbers may be usable only in one country
Because of such issues, a process known as internationalization is used to remove cultural assumptions from products during development so that they
can be effectively localized.
Internationalization is the process of enabling a product at a technical
level for localization. In other words, an internationalized product does
not require remedial engineering or redesign at the time of localization. Instead, it has been designed and built to be easily adapted for a specific market after the engineering phase.
Internationalization primarily consists of abstracting the functionality of a
product away from any particular culture, language or market so that support for specific markets and languages can be integrated easily. If a product has not been internationalized in advance, additional expenditure will
almost certainly be incurred during localization. In some cases, such added
expense will make it uneconomical to even localize. As a general rule, it is
best to assume that it takes twice as long and costs twice as much to localize
a product if it is not properly internationalized to start with. In the case of
computer code, the difference can be much greater.
© 2007 LISA • All rights reserved

18

• LISA Globalization Industry Primer •

The degree of internationalization required depends, in part, upon the languages into which the product will be localized. If a product starts out in
English and will be localized into French, Italian, German and Spanish (the
so-called “FIGS” languages that were traditionally the most popular choices
for localization), the level of internationalization engineering will likely be
less than would be required if the product must support Japanese, Chinese,
Thai, Arabic or Hindi, all of which require special planning and design considerations.
Thus, internationalization, like localization, should be considered from a
business perspective: In what languages and regions will the product be
sold? In what languages will it be sold next year or in five years?
Internationalization requires the active support of everyone involved in
product design and development and of corporate management. The temptation is always to put off internationalization and to pass the resulting costs
onto the localization team (which usually operates under a different cost
center) to save time and money up front. The results are usually less than
satisfactory since release dates are pushed back. In addition, functions available in the original language often fail to work in the localized versions.
Proper internationalization requires education and negotiation, as well as
formal procedures that are consistently applied. One common problem with
software is that developers attempt to add features as late as possible in the development cycle and then switch their efforts to complete the product. After
project completion, they frequently take vacations or are reassigned to other
projects, leaving localization staff without needed access to key members of
the development team during their efforts. Such common working practices
can contribute greatly to delays in the release of localized software.

© 2007 LISA • All rights reserved

• LISA Globalization Industry Primer •19

Planning for Globalization

Successful globalization requires proper planning for both the internationalization and localization phases, as well as for ongoing support and maintenance needs. To make proper plans, these two phases need to be understood
as part of the larger global product development cycle (Figure 1). When
globalization is treated as a cycle, it becomes clear that globalization ties
into every level of the business and must be treated as a core function if it
is to succeed. (While the following description of the cycle is most easily
applied to the software industry, the general principles hold for documentation, hardware, and services with some modification.)

Localization
Local product
marketing support

Local product
testing & QA

Product
requirements
analysis
(global/local)

Internationalization
Internationalized
product
design

THE GLOBAL PRODUCT
DEVELOPMENT CYCLE

Product
localization

Internationalized
product
development

Internationalized
product
testing & QA

Figure 1. The Global Product Development Cycle for Software
© 2007 LISA • All rights reserved

20

• LISA Globalization Industry Primer •

Product Requirements Analysis (Global/Local)
Any product design process starts with a basic requirements analysis. What
is the core functionality and content that users—wherever they are—need?
What are they prepared to pay money for? What feedback has been received
on previous versions, and how do competitors’ products compare? What
return on investment must be generated within what time frame?
In a global environment, the important point is to make sure that this analysis is conducted not just for the domestic market, but for all potential markets. This fact-finding and planning process should draw on the expertise of
in-country staff, distributors, and users, at the same time that it takes into
account overall ROI (return on investment) and strategic considerations. It
must include an evaluation of the potential difficulties in each market and
what steps are required to overcome them.
The result of this process is a global product specification that incorporates
input from all local markets identified as desirable, rather than a specification developed with a particular market in mind that is subsequently modified more or less appropriately for other markets. In other words, the process requires companies to start “thinking global” from the outset to ensure
efficient product internationalization and localization to minimize update
and maintenance costs. In particular, the specifications will contain information on the following issues:
•
•
•
•

What content and functionality will the global product supply, and
what local content requirements exist?
What functions need to be adapted to conform to local business
processes or regulatory practices?
What technical support and features must be provided? How will
they be delivered?
What languages must be supported and what will be required to
support them?
© 2007 LISA • All rights reserved

• LISA Globalization Industry Primer •21
The specification will divide requirements between those needed for all markets, and those needed for specific markets. In addition, the requirements
should be prioritized based on assessed need and their market value, so
that they can be considered from a business perspective, rather than what is
technically required to produce them.
Assessing Market Potential
Organizations just starting the globalization process often are unclear about
the size of their potential markets and the costs and benefits of globalization. While localizing a product or service can deliver significant market
advantages, it can also incur substantial costs. Therefore, organizations need
to analyze their target markets carefully and consult local representatives or
partners on the potential return on investment for localization. Only when
the market potential is clearly understood should they decide what and how
much to localize for a particular market.
Internationalized Product Design
After the product requirements analysis has been completed, the next step
is an internationalized product design. This design implements the requirements of the global product requirements analysis. While development will
take place in one language, this development must be carried out with other
languages in mind. Critical issues to keep in mind include the following (the
list may vary for non-software products):
•

Graphics. Are the graphics used in the product appropriate for the
target market? Do they show events or actions particular to one
country? If so, can they be replaced by more neutral graphics? (If
graphics do need to be specific to a given culture, plans need to be
made to replace them with other appropriate graphics in localized
versions.)

© 2007 LISA • All rights reserved

22

• LISA Globalization Industry Primer •
•

•

•

•

•

•

Colors. Colors may have different values in various cultures. A color scheme that looks very good in one country may appear strange
or “foreign” in another.
Icons. Icons often rely on culturally or linguistically specific images
to be intuitive for end users. Care must be taken in designing icons
so that graphic designers’ unconscious cultural assumptions do not
lead to icons that are confusing or misleading in other cultures. In
some cases (particularly with images of animals or of body parts
such as eyes, hands and feet), icons that are innocuous in one culture may be offensive in another.
Abbreviations. Abbreviations are often used to save space in user
interfaces and documentation. What happens when they do not
make sense in another language or culture, or even sound like offensive words?
Product Markings. Product markings, such as regulatory compliance markings, prices on packaging, etc., are usually specific to
a given country and may be meaningless outside of that country.
Designs must allow room for the inclusion of any needed product
markings.
Shortcut Keys. Since the choice of software shortcut or “hot” keys
often relies on mnemonics (such as control-O for “open” or controlN for “new document” in English), they must be adapted for other
languages if users are to easily remember them.
Forms and Other User Input. Users must be able to use local data
in all forms, so all data processing must accept and work with local
input. If a product requires the input of a street or postal address or
a phone number, will it accept these in the local format? Will users
be able to use their local currency? Does the product assume that
personal names come before family names, something that is true
in most of Europe and the Americas, but not true in most of Asia
and even some parts of Europe? There are many issues to consider,
not all of which are immediately obvious.
© 2007 LISA • All rights reserved

• LISA Globalization Industry Primer •23
•

Text Shrinkage/Expansion. An important consideration in any
product or document design is how to deal with text that takes
significantly more or less space than the original that it replaces.
The amount of change depends on the languages involved. For example, it is not uncommon for short texts, such as titles or software
commands, to be two to three times as long in German as they are
in English, while texts in Chinese will be significantly shorter than
in English. If insufficient room is left in the design phase for translated text to be displayed, expensive reengineering or redesign may
be required during the localization phase. Proper planning requires
knowledge of the characteristics of the specific target languages involved.

When these issues are not planned for, the entire globalization process will
take longer, be more expensive, and will usually result in products that are
not as successful as they should be worldwide. Only when knowledgeable
staff members who have the authority to provide input and to make changes
are involved early on can such problems be avoided. It is also best to have
engineers and content creators involved who are thoroughly familiar with
globalization processes and best practices. While it may be expensive to hire
such staff, they will more than pay for themselves in improved customer
satisfaction, faster time to market and reduced overall costs.
There are two principles to be considered when creating an internationalized product: flexibility and translatability. Keeping these principles in mind
throughout the design phase will take care of most potential problems.
A flexible product is easily adaptable by design. In software, a flexible product
is engineered to support multiple writing systems, e.g., languages such as
Arabic and Hebrew that are primarily read from right to left. In hardware
design, flexibility means the automatic adjustment for different voltages of
power input. It means engineering an automobile so that the steering system
© 2007 LISA • All rights reserved

24

• LISA Globalization Industry Primer •

can be placed on either side of the car without needing to re-engineer the
entire transmission and steering system. Wherever possible, such a product will utilize international and operating system standards that have been
designed to work with various languages and cultures. While such design
may increase design costs and the cost of the base product, it will save costs
overall when international markets are factored in.
A translatable product has all of its translatable content written with translation in mind (see the LISA publication Quality Assurance: The Client
Perspective, available from the LISA web site, for more information on this
subject). In addition, all of the content is accessible to translators and can
be easily changed. For example, user interface strings should never be hardcoded into software (where translating them requires altering the program
itself ). Instead, they should instead be loaded from an external resource file
so that the translator can easily access them. Markings should not be etched
into hardware components. They should be printed separately so that they
can be easily altered. In all cases, leaving room for text shrinkage/expansion
is a critical aspect in translatable product design.
Internationalized Product Development
The next stage in the process is to develop the basic internationalized product
according to the global design specifications. If these have been carefully thought
out, the coding and the manufacturing processes will be relatively straightforward. Nowadays, these processes are often outsourced to third parties.
Internationalized Product Testing and Quality Assurance
After initial development, a product needs to be tested against the global
product specifications that were developed early on. It is critical that errors
be caught at this stage and fixed, or each localized version may require a
separate fix for the same problem, increasing development costs dramatically. For software, current best practice includes testing the internationalized
product early-on using pseudo-translation. This is the process of replacing all
© 2007 LISA • All rights reserved

• LISA Globalization Industry Primer •25
text with “garbage” text that approximates the characteristics of real target
languages (such as using accent marks or other writing systems) to find any
problems that may result during localization.
The testing and quality assurance (QA) process requires developers to adhere to strict deadlines to allow sufficient time for testing prior to release
deadlines. If development milestones are missed, or the product is altered
after localizers have begun their work, costs will rise significantly and quality will suffer.
Product Localization
Following QA and testing of the internationalized product, the actual product localization process can then begin. This leverages and implements the
criteria for particular target markets established during the requirements
analysis phase. In practice, enterprises may be localizing products regularly
into 60 or more languages (and sometimes in excess of 170). In some cases,
these are divided into three or four different tiers, according to market importance. The aim is to keep the time gap between the appearance of the
product in its lead market and localized versions as small as possible, especially for the key, first-tier markets. As a result, many companies aim for
“simship”—simultaneous shipment of multiple language versions. The allocation of localized versions to specific tiers may also influence the depth to
which products are localized (translation of user interface and documentation alone, content localization, adaptation of underlying functionality, etc.).
It is at this point that efficient internationalization will pay off, since localizers will not only have a list of required features for their target versions, but
also a globally enabled, stable product with which to work.
Localized Product Testing and QA
The localized versions of the product must also be subjected to rigorous testing. This testing includes technical and linguistic quality assurance, which
may be performed in-house and/or by LSPs. If at all possible, such tests
© 2007 LISA • All rights reserved

26

• LISA Globalization Industry Primer •

should include in-country validation or acceptance testing by local subsidiaries, distributors or customers. In many cases, the results obtained from
one language version are made available to localizers of other versions and
developers via a central “bug database” or similar mechanism, in order to cut
overall troubleshooting times.
Local Product Marketing, Support and Feedback
After the localized product has been tested and released, it enters the incountry marketing and support phase. Organizations need to develop clear
channels for customers to report errors (both functional and localizationrelated), along with processes to ensure that customer-reported errors make
it back to the central development team.
LISA research has shown, however, that obtaining local language feedback
can be quite difficult because of the lack of contact between product developers, localizers and the local offices that support products in their markets.
As a result, product developers are often unaware of serious problems in
localized versions. Too many times, these problems are not fixed, and they
lead to decreased customer satisfaction and lower sales. The only way to
prevent such problems is to implement consistent reporting processes that
result in real changes. For more details, read Taking Software to the World
(available through the LISA web site).
Starting It All Over Again
By the time a product has been on the market for a brief time, the developer
is usually already considering the next version, and the cycle starts all over
again with a new set of global and local product specifications. These new
specifications should incorporate specific requirements to address any issues that were encountered in the last cycle so that changes are implemented
and problems are avoided. Very often, developers will become familiar with
issues that they did not initially anticipate. Their updated solutions can be
rolled into the next release.
© 2007 LISA • All rights reserved

• LISA Globalization Industry Primer •27

Global Business Priorities

What markets and languages are most important in today’s global business
environment? What products are most dependent on localization?
Strategic and Maintenance Markets
International markets can be divided into two groups. Maintenance markets
are those markets where an established customer base already exists. Strategic markets are markets where an organization hopes to gain a presence,
either for strategic purposes or to facilitate new growth. Globalization approaches for these two sorts of markets are rather different. (A market can
exist as both types if an organization is marketing multiple product lines.)
In the case of maintenance markets, legacy documents usually exist in the
local language(s), along with a significant customer base. As a result, existing localization tends to be quite extensive. The localization efforts tend to
focus on incremental updates to product lines and on support of existing
revenue sources. Costs of localization for maintenance markets are usually
low if linguistic localization technologies have been implemented well.
Strategic markets, in contrast, usually do not have a large base of existing
customers or localized products. Localization tends to focus on essential
items such as web sites, user interfaces, documentation and sales materials.
Initial localization costs may be quite high since all pieces are being processed for the very first time. Localization of support and other secondary
materials tend to be put off until it is clear that market returns will justify
the time and effort needed for full localization. Localization costs in strategic markets may initially cost more than direct returns, but the goal in a

© 2007 LISA • All rights reserved

28

• LISA Globalization Industry Primer •

strategic market is to use localization to grow market share and build market revenue streams in the long run.
While the division between strategic and maintenance markets will vary
based on an organization’s history and by how mature its localization efforts are, there are some clear trends as to what markets are considered strategic on a global basis. China is currently (as of 2007) the strategic market
attracting the most attention on a global scale. The country’s opening up
to foreign investment and its booming economy have combined to make
China highly attractive. India is also increasing in importance as a strategic
market due to its burgeoning economy and developing middle class. India’s
linguistic fragmentation (over 400 languages are spoken there) and a lack of
good computer support for most of those languages make localization for
the Indian market difficult, but English is widely spoken by the educated
classes. Brazil and Russia are two other major strategic markets. The United
States/Canada and the European Union also serve as major strategic markets for organizations coming from other regions of the world.
Languages
Because of localization’s historical emergence from the computer software
and hardware industries, which were largely based in the U.S., English is
the overwhelming source language in localization. It is the source language
in approximately three quarters of the language pairs used in localization.
Top target languages chosen by organizations include French (56%), Spanish (53%), German (50%), English (35%), Japanese (29%), Simplified Chinese (27%), and Italian (21%), with all other languages figuring as targets for
less than 7% of organizations (source: Global Business Practices, LISA, 2006,
p. 13)
The major shift in language priorities since 2000 is the emergence of the
People’s Republic of China as a major market and the corresponding rise of
© 2007 LISA • All rights reserved

• LISA Globalization Industry Primer •29
Simplified Chinese as a major target language. This prominence is a result
of major corporations vying to establish themselves in the Chinese market
now to take advantage of future growth. Comparatively little localization is
taking place from Chinese into other languages, though this will increase as
Chinese companies continue to build global brands.

© 2007 LISA • All rights reserved

30

• LISA Globalization Industry Primer •

© 2007 LISA • All rights reserved

• LISA Globalization Industry Primer •31

Market Players

The current globalization market depends on the following players to deliver
results:
•

•
•
•
•

Clients: content/product creators, with or without in-house localization (management) facilities, whose primary focus is on creating
products or services
Localization service providers (“vendors”) providing local-language
engineering, linguistic, and auxiliary services
Consultants of various expertise providing services to both the
above-mentioned groups
Academics and training organizations providing training or research in globalization-related topics and skills
Tools developers who provide globalization productivity tools (see
the section Globalization Technologies and Tools for more information)

Individual organizations may fill multiple roles, and it is common for clients,
service providers, and academic organizations to develop their own tools,
while vendors, academics, and tools developers often provide consulting services.
Clients
Until the mid 1990s, the client side of the globalization industry was dominated by a relatively small number of IT companies. Initially these clients
tended to localize products either through local distributors or with inhouse localization teams. As the demand for rapid, high-volume globalization (with corresponding peaks and valleys in demand for services) increased,
© 2007 LISA • All rights reserved

32

• LISA Globalization Industry Primer •
Service

Percentage
Outsourcing

Document translation
Software localization
Graphics translation/localization
Web site localization
Proofreading/editing
Multimedia localization
Internationalization
Technical Writing
Telephone interpretation
Testing
Localization of embedded systems/informatics systems
Conference interpretation
Escort interpretation

85%
52%
51%
49%
48%
37%
37%
36%
34%
28%
26%
20%
8%

Table 1. Outsourcing of globalization-related tasks by clients
(source: Global Business Practices, LISA, 2006, p. 10).
the in-house model increasingly fell out of favor. Clients now usually partner with globalization service providers to meet their needs. Client-side
headcounts for globalization-related services have fallen as a result and it is
common for very large client organizations involved in globalization to have
only a few full-time localization staff. These staff are usually dedicated to
engineering, internal education, vendor selection, and product management,
rather than to the actual task of localization.
Translation is the most frequently outsourced globalization skill, with 85%
of clients outsourcing it. Overall outsourcing levels continue to increase,
having risen since 2000. Table 1 presents outsourcing rates for various tasks
in 2006.

© 2007 LISA • All rights reserved

• LISA Globalization Industry Primer •33
Subject Matter
User documentation
Software/IT
Marketing
Legal
Sales support
Regulatory compliance
Engineering
Medical/Life sciences
Customer support
Organization administration
Literature
Banking/finance

Percentage
Purchasing
58%
48%
35%
23%
22%
19%
17%
15%
13%
13%
9%
6%

Table 2. Percentage of clients outsourcing translation/localization by subject matter (source: Global Business Practices, LISA, 2006, pp. 10–11).
User documentation is the type of content most frequently outsourced by
clients, followed by software, marketing material, and legal documentation.
Table 2 presents the percentage of clients that outsource various types of
material for localization/translation.
Service Providers and Consultants
Modern globalization service providers have grown from companies providing translation services to providing globalization-specific services. Many of
these companies originally specialized in a single language (and are thus
called “single-language vendors” or SLVs) and offered very high quality services that language. However, as client needs for comprehensive solutions
have grown, “multiple-language vendors” (MLVs) have become the major
force in the industry. These vendors offer project management and a broader
range of services and languages. MLVs typically subcontract to SLVs and
free-lance localizers to deliver portions of their services. Since the mid 1990s
© 2007 LISA • All rights reserved

34

• LISA Globalization Industry Primer •
Subject Matter
User documentation
Software/IT
Marketing
Medical/Life sciences
Legal
Engineering
Sales support
Customer support
Organization administration
Regulatory compliance
Banking/finance
Literature

Percentage
Providing
75%
75%
60%
59%
51%
48%
37%
35%
32%
29%
27%
21%

Table 3. Percentage of vendors providing translation/localization services for various subject matters and application areas
(source: Global Business Practices, LISA, 2006, pp. 10–11).
the vendor segment has seen intense competition and consolidation in the
MLV sector. These larger MLVs are able to provide comprehensive services
to large multinational organizations. SLVs and smaller MLVs often enjoy
considerable success by focusing on particular industries or technical skills.
Because of such specialization, the distinction between vendors and consultants has become somewhat blurred.
Table 3 presents the percentage of vendors providing services in various specific subject matters.
Tools Providers
Globalization depends heavily on technology and the developers of globalization technology tools are an important part of the industry. Some clients
and service providers are also involved in tools development: approximately
© 2007 LISA • All rights reserved

• LISA Globalization Industry Primer •35
10% of organizations develop their own TM tools and many more develop
custom tools to address specific problems and issues that they face. The
overwhelming majority (over 90%) of organizations involved in globalization, however, rely on commercial tools to some extent (source: LISA 2004
Translation Memory Survey, LISA, 2004, p. 11).
Global Scope
The globalization industry is globally based. LISA members have come from
over forty-five countries, and LISA holds forums each year in the United
States, Europe, and Asia. The majority of LISA’s client members earn at
least 20% of their income outside of their home countries, with many earning far more internationally. The bulk of localization work is conducted
in the countries where the final product will be sold and the number of
languages they localize into is only increasing. Fifteen years ago ten target
languages was considered a large number, but organizations now routinely
localize into thirty or more languages, and some localize into well over 100.
Without localization, the international expansion this increase represents
would have been impossible. These is also an increasing trend toward “reverse localization,” in which products developed in small markets are localized for sales in the U.S. and other traditional sources of localization.

© 2007 LISA • All rights reserved

36

• LISA Globalization Industry Primer •

© 2007 LISA • All rights reserved

• LISA Globalization Industry Primer •37

Technologies and Tools

There are two main categories of globalization tools: language technology
tools and tools used to manage the globalization process. Both sorts of tools
are essential in modern globalization workflows if quality, speed and volume
demands are to be met. These tools can result in significant cost savings for
organizations that use them, with one large multinational corporation reporting annual cost savings of $750 million U.S. from the use of translation
memory technology alone.
Language technologies do not replace skilled human translators. Instead,
they allow translators to deliver better results in shorter times and to add
value to the globalization supply chain. Predictions that computers would
replace humans as translators have been made since the 1950s, but this appears no closer to being true today than it was fifty years ago. What has
happened is that technologies have automated some of the most tedious
and error-prone tasks of translation and resulted in translation volumes
that would otherwise be impossible to deliver.
Key language technologies include the following:
Terminology Management Systems
Quality translation relies on the correct use of specialized terms. It improves reader understanding and reduces the time and costs associated with
translation. Special terminology management systems store terms and their
translations, so that terms can be translated consistently. Full-featured systems go beyond simple term lookup, however, to contain information about
terms, such as part of speech, alternate terms and synonyms, product line

© 2007 LISA • All rights reserved

38

• LISA Globalization Industry Primer •

information, and usage notes. They are generally integrated with translation
memory systems and word processors to improve translator productivity.
Translation Memory (TM)
Texts are often revised slightly for new product versions. When these revised
versions are retranslated, it does not make sense to have someone retranslate those portions of the text that are unchanged. As a result, technology
called translation memory (TM) is used to store texts and their translations,
broken down into small pieces (usually sentences) called segments. When
a new version of the text is translated, the TM tool processes the text and
automatically replaces those parts that are unchanged with the previously
created translations. This allows the human translator to focus on the new
content. In the case of text that is only partially changed (so-called “fuzzy”
matches), the translator is given the nearest matches and their translations
for reference and editing. This process is called leveraging. Translation memory is most efficient for revisions of existing texts, but is sometimes used
within projects where there is significant duplication between components
(e.g., online help and user manuals) to create internal leveraging. The quality of results from translation memory depends on the quality of previous
translations. The efficiency depends on how well the database is maintained
and how proficient translators are in using the tool.
Machine Translation (MT)
Unlike translation memory, machine translation (MT) actually translates
text that is not in a database. Most MT systems grammatically analyze
(parse) the source text and then generate a translation based on this analysis.
Newer technologies are based on statistical analysis or on a hybrid approach
that leverages both linguistic and statistical analysis.
The results of MT are generally not as good as translations produced by humans, but are useful for understanding roughly what a text says (a process
known as “gisting”). MT is often used to determine whether a human trans© 2007 LISA • All rights reserved

• LISA Globalization Industry Primer •39
lator should prepare a high-quality translation. Through Internet translation portals that make use of machine translation, it is perhaps the most
commonly used translation tool in the world, but such results are seldom incorporated into localized documents for publication. In some cases, human
translators edit machine translation results to produce final translations in
what is called “post-editing.”
Machine translation can be used to provide very high-quality translations
under certain controlled circumstances. It is also critical for providing translations of materials (such as results from database queries) that are timesensitive and which cannot wait for the time required for human translation.
(To learn more about machine translation, please see the LISA Best Practice Guide, Implementing Machine Translation, available through the LISA
web site.)
Localization Workbenches
Localization workbenches are tools that combine translation technologies
together into a single application. Translation memory and terminology
management, for instance, are often combined. Specific workbenches may
be optimized for specific tasks, such as software localization, document
translation or software testing. Those intended for software localization
often include the ability to extract text from resource files, provide pseudotranslations (see the section Internationalized Product Testing and Quality
Assurance for more information), and edit program resources such as dialog
boxes and icons.
Global Content Management Systems (GCMS)
Traditional localization processes typically relied on a workflow in which
entire projects (often consisting of hundreds or thousands of files) were
completed and then localized into multiple languages. However, this model
is not suitable for web sites that are constantly changing, often with little
or no central control over the process. Manually tracking site changes is
© 2007 LISA • All rights reserved

40

• LISA Globalization Industry Primer •

an almost impossible task, so global content management systems (also
known as global translation management systems or globalization management
systems) starting appearing in the late 1990s. These systems were specifically
engineered to facilitate localization of web site content, but have since been
extended to work with other content. Their functionality is increasingly being integrated with general content management systems (CMS).
GCMS typically consist of an engine that monitors content for change and
a component that, using business rules specific to each organization, passes
content to translators or other linguistic tools for further processing. It also
manages the workflow and synchronization of translated content with the
source language versions.
Although GCMS are complex tools, they are currently the only way to successfully localize the large and dynamic bodies of web content that customers increasingly rely upon for everything from sales to tech support. (For
more information on GCMS, please read the LISA Best Practice Guide,
Managing Global Content, available through the LISA web site.)

© 2007 LISA • All rights reserved

• LISA Globalization Industry Primer •41

Evaluating and Ensuring Success

Attention to certain details will help organizations evaluate the success of
their globalization efforts. Here are some recommended guidelines:
•

•

•

•

Make the globalization process transparent. In most cases, direct
localization costs are only a portion of the costs of globalization.
Internal costs for project management must be considered. Globalization projects may need to aggregate costs from a number of
departments (e.g., product design, development, project management, document authoring, web site development, and marketing)
for each market if accurate statistics and business decisions are to
be made.
Establish actual revenue streams. In many industries, it is now
common to distribute products which the user can set up to use in
various languages, a practice which may make it difficult to identify
which languages are actually being used. To have an accurate idea
of globalization ROI, it is important to develop processes to evaluate which versions are actually being used.
Manage globalization cost-effectively. Companies will find that
they are equipped to handle certain globalization tasks in-house,
while other tasks are best outsourced. They need to periodically
assess their in-house capabilities and costs versus what they outsource to make sure their globalization-related needs are being met
cost-effectively. They also need to evaluate the impact of their business models on time-to-market and product quality, and how those
impact their overall ROI.
Don’t make purchasing decisions based on price alone. Other
factors are often more important. These include quality, experience
© 2007 LISA • All rights reserved

42

• LISA Globalization Industry Primer •
in a particular market segment and understanding of an organization’s requirements. As with most other purchasing decisions, the
cheapest bid will often not be the best offer. Organizations that
make outsourcing decisions on a price basis alone are likely to
achieve substandard results.

© 2007 LISA • All rights reserved

• LISA Globalization Industry Primer •43

Best Practices and Standards

The number of globalization services, technologies and processes has grown
considerably in recent years. As these various solutions have developed, and
as users have wanted to be able to take advantage of the best solutions, the
need for standardization has also grown. There is also emerging consensus
regarding industry best practices, much of which has been encapsulated in
LISA Best Practice Guides (available from the LISA web site).
Standards for Quality Management
Historically, staff members who reviewed materials looking for errors typically provided their assessment of overall project quality. This process is
highly subjective and disagreements regarding quality are common. In addition, many times the problems reviewers identify are actually problems in
the source text that were faithfully localized.
Because of the difficulties in assessing quality, most globalizers implement a
formal quality management process. Among the most popular quality standards are the ISO 9000 series, Total Quality Management (a generic standard that can be customized for any industry), EN-15038 (a European Union
standard), DIN 2345 (a German standard), and CMM (for software development). The LISA QA Model (version 3.1 as of January 2007) is the most frequently used quality assessment tool for localization. This tool was developed
by LISA in conjunction with its members to address globalization quality
issues not normally addressed by translation standards. In practice, many of
LISA’s members implement multiple standards to provide customized quality
management solutions that can be easily adapted to current needs.

© 2007 LISA • All rights reserved

44

• LISA Globalization Industry Primer •

Standards for Linguistic Data Interchange
According to LISA research, the value of translation memory data exceeds
the cost of globalization tools by a large factor. Standardization is very important if substantial organizational assets are not to be limited in application by a comparatively low-value tool. As a result, LISA has actively developed standards through its OSCAR (Open Standards for Container/Content Allowing Re-use – http://www.lisa.org/sigs/oscar/) Special Interest
Group. Standards developed by OSCAR include the following:
•
•
•

•

•

Translation Memory eXchange (TMX) for the interchange of
Translation Memory data between tools.
Term Base eXchange (TBX) for the interchange of terminological data
Segmentation Rules eXchange (SRX) for defining how TM tools
segment source texts to produce their databases, an important consideration in making TM data portable between tools.
Global information management Metrics eXchange (GMX) for
representing the volume (word or character count), quality expectations, and complexity of localization jobs. As of January 2007
only the volume portion of the standard has been released.
xml:tm for embedding text memory (including translation memory) within XML documents.

In a 2003 interview, Mr. Glenn H. Nordin, Assistant Director (Language),
U.S. Department of Defense, stated that, “language technology tools purchased by the U.S. government are expected to implement TMX and TBX
among other open standards like Unicode.” Other large organizations
around the world also mandate use of LISA standards. In November 2006,
the International Organization for Standardization (ISO) and LISA jointly
announced that TBX would be submitted to ISO for ratification as a joint
LISA/ISO standard, a move that will further facilitate its adoption by national governments and large international organizations.
© 2007 LISA • All rights reserved

• LISA Globalization Industry Primer •45
Business Practices
As an emerging and fast-moving industry, globalization needs to rapidly
develop and disseminate best practices for successfully creating, building,
marketing and supporting products and services worldwide. As the premier
global business industry association, LISA has played a central role here.
Its initiatives include a code of practice for LISA members and a Common
Bidding Platform designed to help standardize client-partner expectations.
By defining a project’s deliverables in terms of its languages, engineering,
technology and documentation requirements, customers and their service
partners are in a good position to establish reasonable time, cost and quality
parameters for any type of localization project.

© 2007 LISA • All rights reserved

46

• LISA Globalization Industry Primer •

© 2007 LISA • All rights reserved

• LISA Globalization Industry Primer •47

Future Challenges

The globalization industry is still relatively young and changes are rapid.
The following challenges are especially important to organizations involved
in globalization:
Technology and Organizational Processes
Globalization processes are often divided between a number of different
departments, so it is difficult for organizations to control their globalization
efforts and gain an idea of their true scope. Because of this lack of visibility,
organizations often face significant difficulties in making sure that globalization best practices are implemented uniformly throughout the organization. They also have problems in making sure that problems discovered in
one phase of the process are reported to those responsible for solving them.
Despite recent improvements in standardization, not all globalization tools
fully support standards, and there is often considerable difficulty in integrating tools into an efficient automated workflow. Much work remains in
the integration of globalization tools with other enterprise content management and development tools.
Strategic Importance
Despite the important of international revenues for many large organizations, upper-level management often does not see the connection between
globalization efforts in the organization and these revenues. Rather than
treating globalization as the key to unlocking international markets, they
treat it as a primarily linguistic process and a cost to be minimized. While
cost reduction is always a goal, the result is that organizations cut corners to
save a little cost but then face resulting expenses that are much higher than
© 2007 LISA • All rights reserved

48

• LISA Globalization Industry Primer •

what they saved initially. Until globalization is seen as the strategic is­sue that
it really is, rather than as a simple expense—and integrated into the organization’s business processes—cost, quality, and efficiency will all suffer.
Managing Global Content, Not Projects
The globalization industry initially focused on localization of products or
services, but organizations increasingly demand global content management, in which content-creation and -management tools can interact with
content in any language. Integration of localization technologies with content management is an area of active and ongoing development.
International Support
Organizations are often very good at releasing their products in multiple
markets, but post-sales support remains a major issue for many organizations. The development of globalization workflow tools that address web
content in particular has aided many organizations to move support to the
Internet, but LISA research shows that they still have a long way to go if
they are to provide full-spectrum support to international users (source:
Taking Software to the World, LISA, 2005; see the results from LISA’s Ten
Best International Web Sites Awards program as well).
Increased Focus on Value Creation
Localization has traditionally been seen as a pure service industry that adds
little value to international business. As the proportion of revenues from
international markets increases, however, localization service providers have
the opportunity to recreate themselves as full-service globalization solutions
providers that can partner with their clients to deliver internationalization
services, local market analysis and advising, global product design consulting, testing, and other value-added services.

© 2007 LISA • All rights reserved

• LISA Globalization Industry Primer •49

Glossary

Enabling

Sometimes used as a synonym for internationalization.
Gisting

Use of machine translation to provide a rough translation of text in
order to determine its content.
Globalization

The process of making all the necessary technical, financial, managerial,
personnel, marketing and other enterprise decisions necessary to facilitate international business.
Global Content Management System (GCMS)

A translation tool designed to automate translation of web site and
other content that changes frequently.
Internationalization

The process of ensuring at a technical/design level that a product can
be easily localized.
Localization

The process of modifying products or services to account for differences
in distinct markets.

© 2007 LISA • All rights reserved

50

• LISA Globalization Industry Primer •

Machine Translation (MT)

A translation tool that automatically translates text not previously seen
based either on linguistic parsing or on similar text stored in a database
(example-based machine translation)
Multiple Language Vendor (MLV)

A relatively large localization service provider that offers a wide range of
languages and other services.
OSCAR

Open Standards for Container/Content Allowing Re-use, LISA’s special interest group for the development of globalization-related standards
Simship

An abbreviation for “simultaneous shipment,” the release of multiple
product versions at the same time.
Single Language Vendor (SLV)

A relatively small localization service provider offering services in only
one or a few languages.
TBX

Term Base eXchange, the LISA standard for representing terminological data for purposes of exchange or interchange.
Terminology

A database of specialist words for a subject area or areas used to facilitate high-quality human- or computer-aided translation.

© 2007 LISA • All rights reserved

• LISA Globalization Industry Primer •51
TMX

Translation Memory eXchange, the LISA standard for representing
translation memory data for purposes of exchange or interchange.
Translation Memory (TM)

A translation tool that stores text segments (usually sentences) and
their translations in a database and automatically retrieves translations
for text that is already in the database (usually from a previous version
of the text). The tool may also find similar segments and their translations to assist the translator.

© 2007 LISA • All rights reserved

52

• LISA Globalization Industry Primer •

© 2007 LISA • All rights reserved

• LISA Globalization Industry Primer •53

About LISA
What is LISA?
Founded in 1990 in Switzerland as a private, non-profit association, LISA is
the premier organization for the GILT (Globalization, Internationalization,
Localization, and Translation) business communities. Over 400 members
from leading IT manufacturers and solutions providers, along with industry professionals and an increasing number of corporations from various
vertical market segments with an international business focus, have helped
establish LISA best practice guidelines and language-technology standards
for enterprise globalization. The Association is managed by a full-time Director and support staff and advised by an Executive Committee elected
from amongst its corporate members.
What Are Its Goals?
LISA defines its mission as “promoting the localization and internationalization industry and providing a mechanism and services to enable companies
to exchange and share information on the development of processes, tools,
technologies and business models connected with localization, internationalization and related topics”. One of the main vehicles for this are the LISA
Forums, at which members can listen to acknowledged industry experts and
exchange news and views, thus ensuring that multilingual software, documentation and other products are manufactured worldwide to the highest
possible standards. In addition, LISA gathers, processes and distributes a
wide range of information on the industry and relevant issues.
What Are LISA’s Values and Principles?
LISA seeks to promote the following values in the globalization industry
and among its members:
© 2007 LISA • All rights reserved

54

• LISA Globalization Industry Primer •
•

•

•

•

Global Responsibility. Companies doing business around the
world have a responsibility to respect the nations and cultures with
which they do business. Localization provides the means by which
companies can enter multiple markets with sensitivity and respect.
Global Entrepreneurship. Globalization allows for the spreading
of prosperity across national boundaries and the extension of benefits around the world. By taking a leading role in global entrepreneurship, LISA’s members are in a position to promote the benefits
of globalization
Global Leadership. LISA’s members represent companies taking
a lead in global business. LISA members understand the value of
global business and localization and are in a position to lead their
partners and others into responsible global business practices.
Global Cooperation. LISA promotes cooperation on a global scale,
with companies and individuals coming together to work on areas
of common interest.

What Services Does LISA Offer?
Services provided by LISA to its members include the following:
•
•

•

•
•

Regular LISA Forums in different venues throughout the world
Regular LISA Workshops offering hands-on skills training and indepth discussion for translation tools, Machine Translation, multiple language workflow, and similar topics
Strategic seminars geared to education decisions makers in the private and public sectors, business consultants and the media about
the importance of globalization and localization
Special Interest Groups (SIGs) for consultation and work on specific topics like terminology and standards
Industry and member surveys, plus information from standards
bodies and other sources

© 2007 LISA • All rights reserved

• LISA Globalization Industry Primer •55
•

A constantly updated web site of online resources and industry updates with archive service for previous forums, presentations, surveys, and special reports

How Do I Join LISA?
LISA offers a variety of membership plans to suit the needs of different
organizations and individuals. For more information on LISA membership,
please visit the LISA web site.

© 2007 LISA • All rights reserved

56

• LISA Globalization Industry Primer •

© 2007 LISA • All rights reserved

• LISA Globalization Industry Primer •57

Additional Resources

The following resources will aid anyone interested in learning more about
globalization. No claims are made to comprehensiveness and LISA does
not assume responsibility for any non-LISA resources listed.
The LISA Web Site – www.lisa.org
The LISA web site is LISA’s primary portal for information on events, publications, members and activities. While much of the information is available to the public, some materials are available only to LISA members.
Globalization Insider – www.localization.org
The Globalization Insider from LISA brings you the business perspective
of operating in a knowledge-based economy. Ranging from interviews with
thought leaders to special reports on implementing new technologies, workflows and standards, the Globalization Insider is your ticket to a greater understanding of what is crucial to managing multilingual information and
increasing your company’s international business performance.
LISA QA Model
3.1
The LISA QA Model offers a standardized quality assurance model for
product localization that covers everything from documentation, help and
software to packaging and CBT tutorials. The QA Model features a standalone, user-friendly user interface. Copies of the LISA QA Model can be
ordered through the LISA web site.

© 2007 LISA • All rights reserved

58

• LISA Globalization Industry Primer •

Surveys
LISA surveys cover many areas of interest in globalization and are available
for sale or download via the LISA web site. Recent surveys include the following:
•
•

•
•
•
•
•

Global Business Practices Survey (2006) – an examination of
global business trends related to translation and localization
Taking Software to the World: The Global Software Survey
(2005) – a study of the impact of quality issues in localized software on customer satisfaction and retention
Terminology Management Survey (2005) – terminology management best practices and trends
LISA/OSCAR Translation Memory Survey (2004) – trends in
the use of translation memory technologies and standards
GILT Industry Salary Survey (2003) – pay levels for globalization professionals
LISA/OASIS Global eBusiness Survey (2003) – global eBusiness trends and adoption of key technologies
CCID/ECCS/SMP/LISA Asian Globalization Resources Report (2003) – in-depth examination of the Chinese globalization
services market

Other Standards Bodies
The following bodies are active in areas related to globalization technologies
and practices:
•

•

The Unicode Consortium is a non-profit organization founded to
develop, extend and promote use of the Unicode Standard, which
specifies the representation of text in modern software products
and standards. www.unicode.org
The w3c Internationalization Activity works with w3c working
groups and liaises with other organizations to make it possible to
© 2007 LISA • All rights reserved

• LISA Globalization Industry Primer •59

•

•

use web technologies with different languages, scripts, and cultures.
www.w3c.org/International/
OASIS is a not-for-profit global consortium that drives the development, convergence and adoption of e-business standards.
www.oasis-open.org
IDEAlliance (International Digital Enterprise Alliance) is a notfor-profit membership organization whose programs and activities
enable its members to participate in the development of standards
and best practices, influence the development of tools and technologies, develop strategies and partnerships to deploy technology
solutions, and position themselves as industry leaders. www.idealliance.org

Books
The following books deal with the technical aspects of globalization:
•
•
•
•
•
•
•

Bean, James. Engineering Global e-Commerce Sites. Elsevier Science.
2003.
Dunne, Keiran J. Perspectives on Localization. John Benjamins.
2006.
Dr. International. Developing International Software. Microsoft
Press. 2002
Esselink, Bert. A Practical Guide to Localization. John Benjamins.
2000.
Gillam, Richard. Unicode Demystified: A Practical Programmer’s
Guide to the Encoding Standard. Addison-Wesley. 2002.
Lunde, Ken. CJKV Information Processing. O’Reilly & Associates.
1998.
O’Connell, Fergus. How to Run Successful Projects II. Prentice Hall.
1996.

© 2007 LISA • All rights reserved

60

• LISA Globalization Industry Primer •
•

•

•
•

•
•

O’Hagan, Minako, and David Ashworth. Translation-Mediated
Communication in a Digital World: Facing the Challenges of Globalization and Localization. Multilingual Matters. 2002.
Rätzmann, Manfred, and Clifton De Young. Galileo Computing
Software Testing and Internationalization. (Available as a free PDF
download exclusively through LISA)
Savourel, Yves. XML Internationalization and Localization. Sams.
2001.
Sprung, Robert (ed.). Translating into Success: Cutting Edge Strategies for Going Multilingual in a Global Age. John Benjamins Publishing. 2000.
Unicode Consortium. The Unicode Standard, Version 5.0. AddisonWesley. 2006.
Yunker, John. Beyond Borders: Web Globalization Strategies. New
Riders. 2002.

© 2007 LISA • All rights reserved

Amsterdam • Arlington • Beijing • Berlin
• Chicago • Copenhagen • Dromoland • D
London • Luxembourg • Madrid • Mainz
Beach • Paris • Prague • Runnymede • Sa
Shanghai • Singapore • St. Petersburg • Th
• Warsaw • Washington DC • Windsor •
Beijing • Berlin • Boston • Brussels • Bud
• Dromoland • Dublin • Estoril • Geneva
Madrid • Mainz • Monterey • Mountain
• Runnymede • Salt Lake City • San Franc
St. Petersburg • The Hague • Tokyo • Val
DC • Windsor • Yokohama • Amsterdam
Published in January 2007 by the Localization Industry Standards
Brussels
• Budapest • Cairo • Chicago • Co
Association. Written by Arle R. Lommel. Edited by Rebecca Ray.
• Geneva • Heidelberg • London • Luxem
ISBN: 978-92-9228-025-3 (PDF) • 978-92-9228-026-0 (Soft cover)
Mountain View • Newport Beach • Paris
• San Francisco • San Jose • Shanghai • S
Localization Industry Standards Association
TokyoThe
• Valbonne
• Vienna • Warsaw • W
www.lisa.org
Amsterdam • Arlington • Beijing • Berlin
• Chicago • Copenhagen • Dromoland •
Domaine en Praël • CH-1323 Romainmôtier • Switzerland • Tel: +41 24 453 2310 • Fax: +41 24 453 2312
© 2007 LISA. All Rights Reserved

