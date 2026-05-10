---
title: "chapter01_02_14_planning.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/zdroje/Nemocnicni inf. system/chapter01_02_14_planning.pdf"
date: 2010-01-28
type: PDF (text-based)
---

Design and
implementation of
health information
systems

Design and
implementation of
health
information
systems
Edited by
Theo Lippeveld
Director of Health Information Systems, John Snow Inc.,
Boston, MA, USA

Rainer Sauerborn
Director of the Department of Tropical Hygiene and Public Health,
University of Heidelberg, Germany

Claude Bodart
Project Director, German Development Cooperation, Manila, Philippines

World Health Organization
Geneva
2000

WHO Library Cataloguing in Publication Data
Design and implementation of health information systems / edited by Theo Lippeveld,
Rainer Sauerborn, Claude Bodart.
1.Information systems—organization and administration 2.Data collection—methods
I.Lippeveld, Theo II.Sauerborn, Rainer III.Bodart, Claude
ISBN 92 4 1561998

(NLM classification: WA 62.5)

The World Health Organization welcomes requests for permission to reproduce or translate its publications, in part or in full. Applications and enquiries should be addressed to the Office of Publications, World Health Organization, Geneva, Switzerland, which will be glad to provide the latest
information on any changes made to the text, plans for new editions, and reprints and translations
already available.
© World Health Organization 2000
Publications of the World Health Organization enjoy copyright protection in accordance with the
provisions of Protocol 2 of the Universal Copyright Convention. All rights reserved.
The designations employed and the presentation of the material in this publication do not imply
the expression of any opinion whatsoever on the part of the Secretariat of the World Health Organization concerning the legal status of any country, territory, city or area or of its authorities, or
concerning the delimitation of its frontiers or boundaries.
The mention of specific companies or of certain manufacturers’ products does not imply that they
are endorsed or recommended by the World Health Organization in preference to others of a similar
nature that are not mentioned. Errors and omissions excepted, the names of proprietary products
are distinguished by initial capital letters.
The editors alone are responsible for the views expressed in this publication.
Typeset in Hong Kong
Printed in France
99/12 706—Best-set/CD-COM/Granchamp-7000

Contents

Chapter 1

Chapter 2

Chapter 3

Chapter 4

Foreword

ix

Acknowledgements

x

Introduction
by Rainer Sauerborn and Theo Lippeveld
Why health information systems?
Definitions
What is wrong with current health information systems?
Efforts to reform health information systems
Review of the literature on health information systems reform
Scope of the book
Organization of the book
References

1

A framework for designing health information systems
by Theo Lippeveld and Rainer Sauerborn
Developing a “systems approach” for health information systems
The health information system structure
The relationship between the health information system and the
health system at large
Matching the health information system restructuring process
with the health services system
Conclusion
References
Using information to make decisions
by Rainer Sauerborn
The problem
Defining information use
How are decisions made?
Ways to enhance the use of information in decision-making
Outlook and sketch of a research agenda
Conclusion
References
Identifying information needs and indicators
by Claude Bodart and Laura B. Shrestha
Introduction
A general framework for defining information needs and indicators
Performing a functional analysis at each management level
of the health services system
Identifying information needs
Defining and classifying essential indicators
Selecting essential indicators
Summary
References

1
2
3
5
7
8
10
10
15
15
16
17
24
30
31
33
33
33
34
38
46
47
47
49
49
50
51
51
56
60
70
71
v

Design and implementation of health information systems

Chapter 5

Chapter 6

Chapter 7

Chapter 8

Chapter 9

Chapter 10

vi

Assessing health information systems
by Steve Sapirie
Introduction
Assessment as a step in the development and implementation
of the health information system
A framework for assessing the health information system
Reasons for health information system assessment
Basic steps of health information system assessment
Conclusion
References
Routine data collection methods
by Theo Lippeveld
Use of routine versus nonroutine data collection methods
Types of routine data collection methods
Data collection instruments
Data collection instruments for system management
Design and implementation of routine data collection
systems
Conclusion
References
Nonroutine data collection methods: an overview
by Rainer Sauerborn
Definition and classification
Rapid assessment procedures
Participant observation
Individual interviews
Focus groups
WHO’s rapid evaluation method
Surveys
Demographic surveillance systems
Link between nonroutine and routine methods: triangulation
References
Data transmission, data processing, and data quality
by Laura B. Shrestha and Claude Bodart
Introduction
Data transmission
Data processing
Data quality
Threats to data quality from poor recording and reporting
Conclusion
References
Population-based community health information systems
by David Marsh
Introduction
History: population-based community approaches
Rationale
Development of population-based community health
information systems
Conclusion
References
Management of health information systems
by Eckhard Kleinau

73
73
73
74
76
77
85
87
88
88
90
95
103
105
110
111
114
114
115
117
117
118
119
119
121
126
127
128
128
128
133
137
138
144
145
146
146
150
154
159
170
173
176

Contents

Introduction
Resource requirements
Resource requirements for a hospital health information
system
Organizational rules
Conclusion
References
Chapter 11

Chapter 12

Chapter 13

Chapter 14

Using computers in health information systems
by Randy Wilson
Historical overview
Rationale for using computers in health information
systems
Key issues to resolve with respect to computerization
Software and hardware options
References
Geographic information systems
by Rainer Sauerborn and Marc Karam
Why are geographic information systems a useful supplement
to health information systems?
What are geographic information systems and how can we
use them in the context of health information systems?
How much do geographic information systems cost?
Applications of geographic information systems within health
information systems
Who uses maps?
Research agenda
Summary
References
The context of health information system reform
by Theo Lippeveld
Introduction
Health information system reform: a policy analysis
Strategies for health information system reform
References
Approaches to strengthening health information systems
by Theo Lippeveld and Steve Sapirie
Introduction
Restructuring routine health information systems: what
works and what does not work?
An agenda for further health information system development
experiences and research
References

176
176
187
190
197
197
198
198
199
200
205
211
213

213
214
218
219
221
222
223
223
225
225
226
236
241
243
243
244
250
252

Annexes
Annex 1
Annex 2
Annex 3
Annex 4
Annex 5
Annex 6
Annex 7

Classes of indicators and their major attributes
National lists of indicators: the trade-off between conciseness
and completeness
Health information subsystem: issue framework
Examples of assessment questions and recording formats
Examples of assessment data tables
Mother health card, Chandigarh, India
Child health register

253
256
258
259
261
263
264
vii

Design and implementation of health information systems

Annex 8
Annex 9
Annex 10
Annex 11
Annex 12
Annex 13

viii

Example of tally sheet
Hospital daily attendance sheet
Population chart of catchment area
Example of supervisory checklist
HMIS/FLCF monthly report: section on mother care activities
Data collection instrument pre-test review form

265
266
267
268
269
270

Foreword

This project was proposed by Theo Lippeveld and Rainer Sauerborn to
address what was a huge gap in the health development literature: concepts and experiences in developing national health information systems.
The editors were able quickly to agree on the basic orientation and
content of the book—to address the information needs of routine services
management. The health professionals who were called upon to contribute chapters have extensive experience in health information
systems development and use in many different situations.
Yet the task proved to be more daunting than we anticipated. There was,
for instance, a need for a common conceptual framework. WHO has
placed emphasis on addressing priority health and service problems, but
emphasis on strengthening service performance—particularly at the
peripheral level—proved to be a common principle among the contributors to this book. Only a few conceptual nuances, terms and styles of
presentation required negotiation.
The development of health information systems is a fast-moving ﬁeld.
Not only is information technology changing rapidly, but concepts and
methods for making the best use of existing data for managing health
services and resources are quickly evolving. Efﬁciency in information
management is becoming increasingly essential because of the concern
for cost control in services and the way service staff spend their time.
Approaches such as the use of health indicators are rapidly becoming the
norm rather than the exception in order to reduce data handling, while
increasing validity and timeliness. Efﬁcient use of minimum data for
managing cases, clinics and community health is essential, and it is
toward this end that this book has been designed.
WHO is pleased to present this collection of health information system
concepts, experiences and examples. We encourage public health administrators to react to these chapters and share with us, and with each
other, new methods and techniques for health information system development and use that have proved effective in their countries.
Dr Stephen Sapirie
Director, Information for Management Program, Management Sciences
for Health, Boston, USA

ix

Acknowledgements

The editors wish to acknowledge the contributions of the co-authors,
without whose efforts this unique volume would not have been possible.
Particular thanks go to Ronald Wilson, Steve Sapirie and the Strengthening of Country Health Information team of WHO. Their careful review
of the manuscripts was extremely helpful.
The Harvard Institute for International Development in Cambridge
(USA) generously provided a grant to fund some of the time of the editors
and other administrative costs.
The editors also wish to thank Laraine and Don Lippincott for their editorial work. Nawal Birdaha in Morocco and Sarah Newberry and Deirdre
Pierotti in the USA provided copy-editing assistance.

About the editors
Theo Lippeveld, MD, MPH is currently Director of Health Information
Systems at John Snow Inc., Boston, USA. Between 1985 and 1997 he
was Research Associate and later on Development Advisor at the
Harvard Institute for International Development. He lectured at the
Harvard School of Public Health, USA, in courses on “Health Information Systems”. In the last 20 years, he assisted ministries of health in
health information system restructuring in Cameroon, Chad, Pakistan,
Eritrea, Niger, Palestine, and recently also in Morocco.
Rainer Sauerborn, MD, MSc(MCH), MPH, DrPH is Director of the
Department of Tropical Hygiene and Public Health at Heidelberg University, Germany. Until 1996, he was an Institute Associate at the
Harvard Institute for International Development, USA. He lectured at
the Harvard School of Public Health in courses on “Health Information
Systems”, “Community Epidemiology” and “Health Care Financing”. In
addition, he taught a course on “International Health” at Tufts University, Boston, USA, where he was an Associate Clinical Professor. His
experience as a health practitioner at the district level dates back to the
years 1979-1983, when he worked as a district health physician in
Burkina Faso.
Claude Bodart, MD, MPH, is currently working for the German Development Cooperation in the Philippines. He has been involved in health
sector reform in several Central and West African countries since
1983. Between 1994 and 1996 he served as a public health specialist
in the Africa Technical Department of the World Bank in Washington,
DC, USA. From 1989 to 1994, as Project Associate for the Harvard Institute for International Development, USA, he assisted the Ministry of
Health of Cameroon in reorganizing the country’s national health care
system.

x

Acknowledgements

Co-authors
Steve Sapirie, DrPH, MBA, is Director of the Information for Management Program of Management Sciences for Health, Boston, MA, USA.
He was formerly Chief of the Unit for Strengthening Country Health
Information in the Health Situation and Trend Assessment Programme
of the World Health Organization, Geneva, Switzerland. Dr. Sapirie has
30 years of experience in developing, applying and transferring methods
in health planning, health programme evaluation and enhancing health
information systems at global, regional and country levels.
Laura B. Shrestha, PhD, is employed by the World Bank, Human Development Department, based in Washington, DC, USA, as Operations
Officer for Health, Nutrition, and Population. Ms Shrestha holds a PhD
in demography from the University of Pennsylvania’s Population Studies
Center and a degree in economics from the University of Hawaii/East
West Center. Her research interests are in the areas of monitoring and
evaluation, health and mortality, and ageing.
David R. Marsh, MD, MPH is currently the Epidemiologist at the Health,
Population and Nutrition Office for International Programs of Save the
Children/USA. As a pediatrician and public health physician, he taught
epidemiology and health systems development at the Aga Khan University, Karachi, Pakistan, and presently develops, monitors, evaluates, and
documents primary health care programs in Africa, Asia, and Latin
America.
Eckhard Kleinau, DrPH, MD, MS is Deputy Director for Evaluation and
Management Information Systems at the BASICS Project in Arlington,
VA, USA. Dr. Kleinau has more than 15 years of experience as a manager
and consultant in public health and primary health care in Africa, Asia,
Central America and the USA. His work includes the analysis and development of Health Management Information Systems for the World Bank
and United States Agency for International Development (USAID).
Randy Wilson, MPH, is a Systems Analyst who is currently serving as
the Logistics/MIS Specialist in Madagascar with the USAID-funded
APPROPOP family planning support project. Over the past 20 years, his
career has combined public health work and information system development in a variety of developing countries. He is one of the principal
instructors in the MIS training courses organized by MSH, Boston, MA,
USA.
Marc Karam, MD, was involved in tropical diseases projects in West
Africa in the 1970s, in association with the University of Paris VI,
France. He joined the epidemiological evaluation unit of the Onchocerciasis Control Programme in West Africa in 1980 and carried out field
epidemiological studies as well as biomedical research. He subsequently
joined the WHO Global Programme on AIDS in Geneva, first in the epidemiological research unit and then in the clinical research and drug
development unit. He is currently in charge of certification of elimination and eradication of diseases in the Communicable Diseases cluster
at WHO.

xi

1

Introduction
Rainer Sauerborn and Theo Lippeveld

Why health information systems?
Good management is a prerequisite for increasing the efﬁciency of health
services. The need to do more with less is especially important because
the health sector faces ever increasing demands while receiving stagnant
or decreasing resources.
Good management is also a prerequisite for increasing the effectiveness
of health services. There is ample evidence that interventions lose a great
deal of their theoretical effectiveness, also called efﬁcacy, if they are
delivered by poorly run health services (Tanner & Lemgeler, 1993;
Tugwell et al., 1985). As an example, the effectiveness of polio vaccines
may be diminished by breakdowns of the cold chain, incorrect assessment of the age of the child, failure to follow up on children who do not
come for booster shots, and other such ﬂaws. The challenge for health
systems is to optimize the management of service delivery in a way that
minimizes losses in effectiveness.
The World Health Organization (WHO) has long identiﬁed health information systems as critical for achieving health for all by the year 2000
(Mahler, 1986). A report of a WHO meeting (1987) clearly links improved
management to improved health information systems: “Of the major
obstacles to effective management, information support is the one most
frequently cited.” Unger and Dujardin (1992) and Lippeveld et al. (1992),
recently stressed the need for well-designed routine information systems
for ensuring that services are delivered according to standards.
For information to inﬂuence management in an optimal way, it has to
be used by decision-makers at each point of the management spiral.
Examples of these decision points include undertaking situational analysis, setting priorities, or implementing a programmed activity (see Fig.
1). Information is crucial at all management levels of the health services,
from the periphery to the centre. It is crucial for patient/client management, for health unit management, as well as for health system planning and management. This means that not only policymakers and
managers need to make use of information in decision making but also
care providers, including doctors, health technicians, and community
health workers. Unless this occurs, the considerable opportunity costs
involved in set-up and maintenance of health information systems can
be difﬁcult to justify.
Helfenbein et al. (1987) rightly stated that “changing the way information is gathered, processed, and used for decision-making implies changing the way an organization operates”. Or as Newbrander and Thomason
1

Design and implementation of health information systems

Fig. 1

Information support to each step in the management cycle

Source: modified from Green (1992)

(1988) pointed out in their article on health information systems in
Papua New Guinea: “The enhanced development of the health information system has been used as the entry point for the improvement of
managerial capabilities in the health system”. Similarly, our hypothesis
is that the development of rationally structured routine information
systems, closely adapted to the information needs of health services at
the district, health centre, and community levels, can potentially contribute to the overall improvement of health service management.

Deﬁnitions
A “system” is conveniently deﬁned as any collection of components that
work together to achieve a common objective. The objective in the case
of a health information system then is to improve health services management through optimal information support. We deﬁne “information”
as a meaningful collection of facts or data.
While consensus on the deﬁnition of “system” and “information” is
quickly established, deﬁning the term “health information system” is less
obvious. At the outset, health information systems were oriented to
collect information on diseases (“surveillance”) and on health service
output. While these functions are certainly important, we prefer to start
from the deﬁnition of information systems as commonly used in industry. Hurtubise (1984) describes them as systems that provide speciﬁc
2

Introduction

information support to the decision-making process at each level of an
organization. The ultimate objective of health information systems is
therefore not “to gain information” but “to improve action”. Applied to
the health sector, we can now deﬁne health information systems as a set
of components and procedures organized with the objective of generating information which will improve health care management decisions
at all levels of the health system.
The widely used term “health management information system” could be
misleading, since it may suggest that there are different information
systems for different functions, for example management information
systems, epidemiological surveillance systems, and administrative information systems. We consider all these as “subsystems” (see also Chapter
2) of a uniﬁed health information system and therefore prefer the latter
term.
In summary, health information systems integrate data collection, processing, reporting, and use of the information necessary for improving
health service effectiveness and efﬁciency through better management
at all levels of health services.

What is wrong with current health information systems?
Unfortunately, health information systems in most countries are
inadequate in providing the needed management support (WHO, 1987;
Lippeveld, Foltz & Mahouri, 1992). Most health care providers in developing countries equate information systems with ﬁlling endless registers
with names and addresses of patients, compiling information on diseases
(e.g. sex and age of patients) every week or every month, and sending
out reports without adequate feedback. Furthermore, the data received
are often not helpful for management decision making because they
are incomplete, inaccurate, untimely, obsolete, and unrelated to priority
tasks and functions of local health personnel. In other words, information systems tend to be “data-driven” instead of “action-driven”
(Sandiford, Annett & Cibulskis, 1992). A large part of the data collected
passes to the national level without being analysed and used, and frequently ends up on the dusty shelves of an ofﬁce in the Ministry of Health
(Smith, Hansen & Karim, 1988; Becht, 1986; Frere, 1987; Ho, 1985;
Kiafﬁ, 1988; WHO, 1988a; de Kadt, 1989). Current health information
systems are therefore widely seen as management obstacles rather than
as tools. The reasons can be summarized in ﬁve points:

Irrelevance of the information gathered
According to a WHO Expert Committee (1994), “Many of the data
recorded and reported by the health service staff are not needed for the
tasks the staff perform”. Data collection tends to focus on disease reporting and only partially addresses management objectives at the health
unit level or at the patient/client level. Yet data that are needed are frequently not collected. For example, appropriate indicators to monitor
continuity of care of individual patients or clients are rarely included in
health information systems.
The common denominator of these two observations is a lack of a consensus between producers and users of data at each level of the health
care system regarding the information needed.
3

Design and implementation of health information systems

Poor quality of data
Data requirements are frequently chosen without taking into account the
technical skills of the health workers collecting the data, or the available
diagnostic equipment in peripheral health facilities (Nordberg, 1988;
Lippeveld, Foltz & Mahouri, 1992; Frere, 1987). For example, at the ﬁrst
level of care, auxiliary health staff without laboratory or X-ray facilities
are required to report on diseases such as leishmaniasis, diphtheria,
and peptic ulcer. Furthermore, health workers receive little if any training in data collection methods (Murthy & Patel, 1988; Kiafﬁ, 1988;
Nordberg, 1988), and rarely have standardized instructions on how to
collect the data (Frere, 1987; Foreit et al., 1988; Jaravaza et al., 1982;
WHO, 1994).
Another reason data quality is low is lack of motivation among health
services personnel. Since health services supervisors and peripheral
health workers rarely receive feedback on the data reported to higher
levels (Smith, Hansen & Karim, 1988; de Kadt, 1989; Frere, 1987; Ho,
1985; Mitchell & Cromwell, 1982), they have little incentive to ensure
the quality of the collected data and to comply with reporting requirements (Smith, Hansen & Karim, 1988; Frere, 1987; Ho, 1985; Mitchell,
1983; Helfenbein et al., 1987; Stinson, 1983; Murthy & Patel, 1988).

Duplication and waste among parallel health
information systems
Historically, national reporting systems, even in developed countries, are
rarely the result of a coordinated effort to address information needs of
health planners and managers. Often, donor agencies or national programmes within the Ministry of Health developed their own specialized
information system (Mitchell & Cromwell, 1982; Lippeveld, Foltz &
Mahouri, 1992; Foreit et al., 1988; WHO, 1994), mostly under pressure
and with ﬁnancial assistance from external donor agencies.
Designed as vertically structured “empires”, these programmes replaced
line managers with programme directors who managed separate categories of personnel, facilitated separate training programmes, and
created separate “programme information systems” which tended to
focus on one speciﬁc disease (e.g. diarrhoea), a specialized service (e.g.
“family planning information systems”), or a management subsystem
(e.g. “drug management information system”) instead of addressing management functions in a comprehensive way. These programme information systems existed side by side and in addition to the general routine
health information system, which was considered insufﬁcient and incapable of delivering the data needed for programme management. While
these separate systems could indeed provide real information support for
programmatic decisions, and the quality of information generated tended
to be better than that of the general information system (WHO, 1994),
the net result was that routine health information systems became
chaotic and bothersome (Ho, 1985; Foreit et al., 1988; Kiafﬁ, 1988;
Murthy & Patel, 1988).
The literature reveals several design and implementation problems.
Reporting and transmission within each system is usually designed with
minimal involvement of the line managers and providers of the health services (Frere, 1987; Mitchell & Cromwell, 1982; Stinson, 1983). The result
is that health workers are drowned in a multitude of reports to be com4

Introduction

pleted every month (Ho, 1985; Murthy & Patel, 1988; Kiafﬁ, 1988; Stinson,
1983). Since the data are not cross-referenced among the different systems, health care providers and systems managers spend a considerable
amount of time collecting redundant and overlapping information (Smith,
Hansen & Karim, 1988; Ho, 1985; Foreit et al., 1988; Rodrigues and Israel,
1995). Furthermore, data transmission does not follow the hierarchical
lines of communication, so that reports often do not reach their destination (Frere, 1987; Ho, 1985; Lippeveld, Foltz & Mahouri, 1992). Elimination of duplication and waste requires a uniﬁed system rather than better
coordination among the existing parallel structures.

Lack of timely reporting and feedback
The process of transmitting, compiling, analysing, and presenting the
data is usually so tedious that by the time a report is prepared, the data
are frequently obsolete and decisions are often made without any information input. Planners and managers face deadlines and time constraints in their daily decision making. Outdated information, even if of
high quality, is of low value to them. Delays in data transmission and
lack of feedback at the district level are often caused by the presence of
strong vertical programmes. Health facilities report data directly to
national programme managers, and line managers at the district level
receive outdated feedback reports, if any.

Poor use of information
Despite the evidence that much of the generated data is irrelevant, of
poor quality, redundant, or obsolete, there are nonetheless some useful
data sets available. Unfortunately, researchers have not adequately
evaluated or documented information use, and the prevailing sentiment
that information is poorly used is based mainly on anecdotal evidence.
However, a few existing studies do point to some of the culprits. For
example, information use was found to be especially weak at the district,
health centre, and community levels (Smith, Hansen & Karim, 1988;
WHO, 1988b; de Kadt, 1989), given the centralization of many health
systems and, hence, health information systems. This raises serious concerns, given the current effort to decentralize decision making and build
capacity at the district level.
Dunn (1980) revealed another impediment to ensuring use of information: the difference in “culture” between data people and decisionmakers, which is difﬁcult to bridge. Consequently, planning and
management staff rely primarily on “gut feelings” to formulate ad hoc
decisions rather than seek pertinent data. We will explore the factors
that lead to the failure to use information and provide suggestions for
solving this problem in Chapter 3.

Efforts to reform health information systems
The chaotic status and inefﬁciency of most existing information systems
in developing countries are linked to the structural weakness of the
system and lack of integration in the overall health system. This can be
explained by the fact that historically, as in most developed countries,
information systems were not intentionally planned to provide management support to the health services in an integrated way. Foltz (1993)
5

Design and implementation of health information systems

explains: “They differ from country to country depending upon historical
accident and the interests of policy makers, administrators and
researchers”.
The ﬁrst efforts to systematically collect, analyse, and report data for
improved management in developing countries were undertaken by
national programme managers of vertically structured “empires”, as discussed above. This was due to the fact that foreign assistance to the
health sector was typically focused on programmes rather than the entire
health system. Since such projects were accountable to their respective donors, information on performance had to be collected. Targeting
ﬁnancial resources on disease control programmes or programmes
addressing a group of speciﬁc “health problems” was indeed attractive
to the donors because the quantiﬁable success of these programmes
justiﬁed the use of their funds. This vertical approach to health care
delivery, and thus to health information systems, was considered even
more justiﬁed in the early eighties because of the prevailing “ideology”
of selective primary health care (Walsh & Warren, 1979). However, apart
from their effect on health information systems, these vertical programmes were undermining the development of a sustainable primary
health care-based health infrastructure. In recent years great efforts
were made in many countries to integrate the Expanded Programme for
Immunization, the Control of Diarrhoeal Disease Programme, onchocerciasis control, and other vertical programmes into existing health structures, thus strengthening them.
The problems with health information systems were not lost on national
policymakers and donors. Many countries decided to attack the information problem at its roots and planned for a more integrated approach
to improving health information systems. Comprehensive restructuring
efforts in countries such as Cameroon (see Sauerborn, 1991; Berg, 1988;
Weber, 1989), Chad (see Lippeveld, Foltz & Mahouri, 1992; Unger, 1989),
and Pakistan (see Ministry of Health, 1994) concentrated on the routine
health information system for ﬁrst-level care facilities. In Cameroon,
health information system restructuring was complementary to an
overall reform of the health services, building on a decentralized district
health system based on primary health care. In Chad and Pakistan,
restructuring of the health information system was done as a separate
project.
In other countries, health information systems reform was done using
a more gradual approach which consisted of either the reform of subsystems, such as epidemic disease surveillance (e.g. Burkina Faso) or
routine services reporting (e.g. Niger). Table 1 gives an illustrative list
of countries where national health information systems reform efforts
took place recently or are still underway.
The drive for the reform of health information systems coincided with a
revolution in information and communications technology. The computer
has made its entry even in the most reluctant ministry of health. Doctors
and nurses discuss hardware, databases, and spreadsheets. Low-cost
powerful microcomputers and modems can efﬁciently store, process, and
transmit enormous amounts of data. “User-friendly” desktop publishing
and graphics software permit timely, speciﬁc, and action-oriented feedback to managers at different levels of the health services. With this
state-of-the-art technology combined with pressure from the computer
industry, most recently created or restructured health information
6

Introduction

Table 1

Illustrative list of published reports on national health information systems reform projects
Country

Reference

Bangladesh
Burma
Bolivia
Cameroon
Chad
Eritrea
Ghana
Nigeria
Niger
Pakistan
Papua New Guinea
Philippines
Swaziland
Thailand

Reynolds, 1988
Reynolds, 1988
Cardenas, 1992
Sauerborn, 1991; Berg, 1988; Weber, 1989
Lippeveld, Foltz & Mahouri, 1992; Unger, 1989; Foltz, 1993
Tekle et al., 1995
Campbell, Adjei & Heywood, 1996
Lecky, 1991
Kiaffi, 1988
Ministry of Health, 1994
Campos-Outcalt, 1991
Magnani, 1990
Ministry of Health, 1990
Reynolds, 1988

systems are computerized to various degrees. But introducing computer
technology in the development of improved health information systems
is not necessarily the “silver bullet” that solves the efﬁciency problem of
the health services (Sandiford, Annett & Cibulskis, 1992). On the contrary, lack of appropriately trained staff, a hostile climate, and hardware
and software maintenance problems sometimes result in the decay and
obsolescence of expensive computer equipment.

Review of the literature on health information
systems reform
The scientiﬁc literature on how to develop appropriate health information systems in support of basic health services is relatively scanty,
despite the general consensus that these systems should be restructured.
Before 1985, most of the literature on management information systems
focused on the use of computer technology rather than organizational
aspects of information handling, information systems for large tertiary
hospitals rather than basic health services, and survey methodology
rather than routine health unit-based information systems. Other publications have underlined the importance of the development of such
information systems, but without detailing how they could be developed.
One of these publications is the report on an international workshop on
management information systems and primary heath care organized by
the Aga Khan Foundation in Lisbon (Portugal) in 1987 (Wilson et al.,
1988), which covers most of the issues cited. Most publications have
focused on a single aspect of the development of health management
information systems (see Table 2).
Somewhat more comprehensive, the publications of Stinson (1983) and
Helfenbein et al. (1987) provide a fair amount of detail on available
methodologies and technologies for the development of routine health
unit-based information systems in developing countries, but they
reached a limited target audience and date from 1983 and 1987, respectively. The Aga Khan Foundation published the Primary Health Care
Management Advancement Program series (Wilson & Sapanuchart,
7

Design and implementation of health information systems

Table 2

Speciﬁc aspects of health information systems development in
the literature
Aspect of health information
systems

Reference

Information needs for national
health planning
Disease surveillance systems
Development of computerized
data processing systems
Programmatic information
systems
Data collection methods

White, 1977; WHO, 1981; WHO, 1994

Epidemiological techniques
Community involvement
Measurement of quality of care
and health information systems
Politics of health information
systems reform

Klaucke et al., 1988; Thacker, Parrish & Trowbridge, 1988
Brodman, 1986; Bussell, 1993; Rodrigues & Israel, 1995
Ho, 1985; Newbrander, Carrin & Le Touze, 1994; Pelletier,
1994
Anker, 1991; Frerichs, 1988; Guhasapir, 1991; Hill, Zlotnik
& Trussell 1981; Kielmann, Janovsky & Annett, 1995;
Kroeger, 1983; Lanata & Black, 1991; Oranga
& Nordberg, 1993; Scrimshaw et al., 1992; Seltzer,
1990; Valadez, 1991
Vaughan & Morrow, 1995
Husein et al., 1993; O’Neill, 1993; Scott, 1988
Garnick et al., 1994; Roemer & Montoya-Aguilar,
1988
Foltz & Foltz, 1991

1993). Conceived as a set of ﬁeld guides to strengthen the quality and
utility of health data organized around nine thematic modules, the Management Advancement Program series helps primary health care managers at the local level to collect and use information for managing the
health services under their supervision. Also, more recently, two WHO
documents on the development of district-based routine health information systems were published, the ﬁrst titled Information support for
new public health action at district level (1994), and the second, by the
Pan American Health Organization titled Conceptual framework and
guidelines for the establishment of district-based information systems
(Rodrigues & Israel, 1995). The ﬁrst document is a report of a WHO
Expert Committee, summarizing problems and strategies related to the
development of district routine health information systems. The second
publication, by Rodrigues and Israel, gives an excellent treatment of the
design of district-based health information systems, with a strong
emphasis on computer software and hardware.

Scope of the book
This book responds to an urgent need in the public health community to
gather in one publication the state of the art of designing and implementing health information systems, particularly in developing countries. It especially addresses the question of how to transform existing
information systems into management support systems.
The focus is on routine health unit-based information systems. The rationale behind this approach is based on several conditions which exist in
the basic health services in most developing countries. First, the problems of inefﬁcient and chaotic data collection and use of information in
peripheral health units as previously described typically apply to routine
health unit-based information systems. Many government agencies and
8

Introduction

donors tend to “use . . . general and special-purpose surveys to capture
data that should be part of routine reporting” (WHO, 1994). But these
problems do not solely originate from the methodological attributes of
routine information systems. They also reﬂect poor general management
capability of the basic health services. Our hypothesis is that the development of rationally structured routine information systems will also
contribute to the overall improvement of the management capability of
the basic health services, particularly if a consensus-building design
process is used. Second, routine health unit-managed information
systems are the only way to generate data for patient and client management decisions. They are especially suited for routine managerial
decisions, such as those related to ordering supplies, or supervision of
health personnel. Considering the fact that data collection is performed
mainly by health care providers as part of their health care tasks, marginal cost is low. Finally, the development of routine health information
systems, compared with surveys and other nonroutine methods, has been
less well described in the scientiﬁc literature.
Most of the analysis and strategies on health information systems development discussed in this book will pertain to government-managed
health services because this is the most common health services system
in developing countries. Yet one of the roles of the district management
team is to coordinate and supervise nongovernment and private health
services within the district (WHO, 1988b). We will therefore also discuss
in the following chapters means and strategies to involve private sector
health care services in health information systems development.
The strength of the book lies in the case material distilled from information systems which the authors have helped to design and maintain.
In the last 10 years, the authors have gathered broad and varied experience in the development of health information systems through projects and advisory services in developing countries throughout the world:
Bolivia, Burkina Faso, Cameroon, Chad, Costa Rica, the Democratic
Republic of the Congo, Eritrea, Malawi, Niger, and Pakistan. Some of
these efforts involved overall restructuring of health information systems, such as in Cameroon, Chad, Eritrea, and Pakistan. Other efforts
were limited to more speciﬁc aspects of health information systems development, such as the introduction of lot quality assurance sampling as a
tool to improve quality of care in Costa Rica, the use of geographic information systems in Bolivia, and production of annual feedback reports for
district managers in Niger. These experiences, combined with those of
the guest authors and the team of the Strengthening Country Information System unit of WHO/Geneva, provide a unique opportunity to bring
together in book form lessons learned about the development of health
information systems.
The book targets professionals not only in the health sector but also in
related sectors involved in planning and managing health services at
national and intermediate levels, particularly government health services and of nongovernmental organizations. Our focus on decentralized,
district level-operated health services makes it a valuable guidebook for
district health managers. The presentation of case studies and the continuous link in the text between concepts presented and actual implementation in the ﬁeld are intended as a resource for teachers and
students in programmes related to planning and managing health services in developing countries, and more speciﬁcally to developing health
information systems.
9

Design and implementation of health information systems

Organization of the book
The chapters of the book have been grouped under four parts. The theme
of the ﬁrst part with two chapters is information for decision making. In
Chapter 2, we lay the groundwork for health information systems design
by providing a health services system framework closely linked to the
health information systems restructuring process. Chapter 3 deals with
use of information, analysing the reasons information is rarely used by
decision-makers and suggesting ways and means to improve its use.
The second part of the book has six chapters examining step by step how
health information systems should be structured so that they can provide
information useful to decision making at all levels of the health services.
Chapter 4 deals with the ﬁrst step, information needs and indicators and
how to deﬁne them through consensus building. In Chapter 5, the author
proposes a health information system assessment methodology to identify weak elements in the existing health information system and set the
agenda for the restructuring process. Chapter 6 contrasts the different
routine data collection methods, while Chapter 7 gives an overview of
nonroutine data collection tools. Data transmission and processing are
the focus of Chapter 8, with particular emphasis on assessing and assuring data quality. Chapter 9 applies these health information systems
restructuring principles to population-based community health information systems.
The three chapters of the third part of the book deal with resources and
tools required for a well-functioning health information system. Chapter
10 provides a comprehensive view of the health information system
resource base: stafﬁng, training, and supervision; procurement and distribution systems of printed supplies; purchase and maintenance of
hardware and software; and budgeting for recurrent health information
system costs. Chapter 11 analyses the strengths and weaknesses of computer use in health information systems. Chapter 12 highlights one particular computer application: geographic information systems and their
potential usefulness in health services planning and management.
Whereas the ﬁrst three parts of the book provide the principles and technical content of health information systems for decision making, the two
chapters of the last part are about the process of health information
systems restructuring. Chapter 13 focuses on the politics of change,
analysing how different interest groups and contextual factors can
inﬂuence the design and implementation of new health information
systems in a positive or negative way, and proposing health information
systems design strategies to deal with these factors. Finally, in Chapter
14, the authors, based on their experience, summarize health information systems development approaches which almost certainly will fail,
and those, on the contrary, which will lead most likely to successful
health information systems restructuring. The chapter also identiﬁes
areas for future research and development experience.

References
Anker M (1991). Epidemiological and statistical methods for rapid health assessment: introduction. World health statistics quarterly, 44(3):94–98.
Becht JN (1986). Management information systems: lessons from evaluations of
ten private voluntary organization (PVO) health programs. In Management

10

Introduction

issues in health in the developing world. Washington, DC, National Council
for International Health: 105–112.
Berg H (1988). Surveys and health management information systems (prepared
for the GTZ primary health care project in the North-West Province of
Cameroon). Heidelberg, Heidelberg University School of Public Health.
Brodman JZ (1986). Using microcomputers to improve decision-making in Third
World governments. Development Discussion Papers. Cambridge, MA,
Harvard Institute of International Development: 1–46 (Development Discussion Papers, No. 231).
Bussell KE (1993). Computer applications for health information systems.
Atlanta, GA, Centers for Disease Control and Prevention: 1–120.
Campos-Outcalt D (1991). Microcomputers and health information in Papua
New Guinea: a two year follow-up evaluation. Health policy and planning,
6:348–353.
Campbell B, Adjei S, Heywood A (1996). From data to decision making in health:
the evolution of a health management information system. Amsterdam, Royal
Tropical Institute.
Cardenas CO et al. (1992). Bolivia information system (training manual for management of the national health information subsystem). La Paz, Ministry of
Social Welfare and Public Health.
de Kadt E (1989). Making health policy management intersectorial: issues of
information analysis and use in less developed countries. Social science and
medicine, 29:503–514.
Dunn WN (1980). The two-communities metaphor and models of knowledge use:
an exploratory case survey. Knowledge, 1:515–536.
Foltz A, Foltz W (1991). The politics of health reform in Chad. In: Perkins D,
Roemer M, eds. Reforming economic systems in developing countries. Cambridge, MA, Harvard Institute for International Development.
Foltz AM (1993). Modeling technology transfer in health information systems—
learning from the experience of Chad. International journal of technology
assessment in health care, 1993, 9:345–361.
Foreit K et al. (1988). Automating Ecuador’s health information system. Paper
presented at the 116th Annual Meeting of the American Public Health Association, Boston: 1–7.
Frere JJ (1987). Health and management information system for child survival
project in Pakistan. Washington, DC, Technologies for Primary Health Care
Project, United States Agency for International Development: 1–23.
Frerichs RR (1988). Rapid microcomputer surveys. Journal of tropical pediatrics,
34:147–149.
Garnick DW, Hendricks AM, Comstock CB (1994). Measuring quality of care:
fundamental information from administrative datasets. International journal
for quality in health care, 6:163–177.
Green A (1992). An introduction to health planning in developing countries.
Oxford, Oxford University Press.
Guhasapir D (1991). Rapid assessment of health needs in mass emergencies:
review of current concepts and methods. World health statistics quarterly,
44:171–181.
Helfenbein S et al. (1987). Technologies for management information systems in
primary health care. Geneva, World Federation of Public Health Associations
(Issue Paper, Information for Action Series).
Hill K, Zlotnik H, Trussell J (1981). Demographic estimation: a manual on indirect techniques. Washington, DC, National Academy of Sciences: 1–52.
Ho TJ (1985). Managing health and family planning delivery through a management information system. Washington, DC, World Bank.
Hurtubise R (1984). Managing information systems: concepts and tools. West
Hartford, CT, Kumarian Press: 1–168.
Husein K et al. (1993). Developing a primary health care management information system that supports the pursuit of equity, effectiveness, and affordability. Social science and medicine, 36:585–596.

11

Design and implementation of health information systems

Jaravaza VS et al. (1982). Uniﬁed national health information system. Central
African journal of medicine, 28:25–170.
Kiafﬁ A (1988). Rapport d’évaluation du nouveau système de collecte de données.
[Report of the evaluation of a new data collection system.] Niamey, Ministry
of Public Health: 1–26.
Kielmann AA, Janovsky K, Annett H (1995). Assessing district health needs, services, and systems: protocols for rapid data collection and analysis. London,
Macmillan Education.
Klaucke DN et al. (1988). Guidelines for evaluating surveillance systems. Morbidity and mortality weekly report, 37:1–18.
Kroeger A (1983). Anthropological and socio-medical health care research in
developing countries. Social science and medicine, 17:147–161.
Lanata CF, Black RE (1991). Lot quality assurance sampling techniques in
health surveys in developing countries: advantages and current constraints.
World health statistics quarterly, 44:133–139.
Lecky MY (1991). Strengthening and integrating the health information system
for decision making in Nigeria. Cambridge, MA, Harvard School of Public
Health (Working Paper No. 2).
Lippeveld TJ, Foltz A, Mahouri YM (1992). Transforming health facility-based
reporting systems into management information systems: lessons from the
Chad experience. Cambridge, MA, Harvard Institute of International Development: 1–27 (Development Discussion Papers, No. 430).
Magnani RJ (1990). Information systems development at the Republic of the
Philippines Department of Health. Manila, Department of Health: 1–20.
Ministry of Health of Swaziland (1990). Swaziland outpatient health information system. Mbabane, Ministry of Health: 1–110.
Ministry of Health of Pakistan (1994). Health management information system
for ﬁrst level care facilities: instruction manual. Islamabad, Ministry of
Health.
Mitchell JB, Cromwell J (1982). Physician behavior under the Medicare assignment option. Journal of health economics, 1:245–264.
Mitchell M (1983). Provincial health plan, 1983–1987. Port Moresby, Papua New
Guinea Division of Health.
Murthy N, Patel KG (1988). A computer based information system for health and
family welfare: the Bavala experiment. Ahmedabad, Indian Institute of
Management.
Newbrander W, Thomason JA (1988). Computerizing a national health system
in Papua New Guinea. Health policy and planning, 3:255–259.
Newbrander W, Carrin G, Le Touze D (1994). Health expenditure information:
what exists and what is needed? Health policy and planning, 9(4):396–408.
Nordberg E (1988). Household health surveys in developing countries: could
more use be made of them in planning? Health policy and planning, 3:32–39.
O’Neill K (1993). Community based surveillance: a critical examination of nine
case studies. London, London School of Hygiene and Tropical Medicine: 1–84.
Oranga HM, Nordberg E (1993). The Delphi panel method for generating health
information. Health policy and planning, 8(4):405–412.
Pelletier DL, Shrimpton R (1994). The role of information in the planning, management and evaluation of community nutrition programmes. Health policy
and planning, 9:171–184.
Reynolds J (1988). Overview: current perspectives on management information
systems in primary health care. In: Wilson RG et al., eds. Management information systems and microcomputers in primary health care. Geneva, Aga
Khan Foundation: 67–70.
Rodrigues RJ, Israel K (1995). Conceptual framework and guidelines for the
establishment of district-based information systems. Barbados, Pan American
Health Organization, Ofﬁce of the Caribbean Program Coordination (document PAHO/CPC/3.1/95.1).
Roemer MI, Montoya-Aguilar C (1988). Quality assessment and assurance in
primary health care. Geneva, World Health Organization: 1–78 (WHO offset
publication, No. 105).

12

Introduction

Sandiford P, Annett H, Cibulskis R (1992). What can information systems do for
primary health care? An International Perspective. Social science and medicine, 34:1077–1087.
Sauerborn R (1991). Propositions pour un système d’information pour le projet
SESA. [Proposals for an information system for the SESA project.] Cambridge, MA, Harvard Institute of International Development: 1–117.
Scott W (1988). Community-based health reporting. World health statistics quarterly, 41:26–32.
Scrimshaw NS, Gleason GR, eds. (1992). Rapid assessment procedures—
qualitative methodologies for planning and evaluation of health related
programmes. Boston, MA, International Nutrition Foundation for Developing Countries.
Seltzer JB (1990). Handbook for conducting local rapid assessments. Boston,
Management Sciences for Health: 1–25.
Smith DL, Hansen H, and Karim MS (1988). Management information support
for district health systems based on primary health care. In: Wilson RG
et al., eds. Management information systems and microcomputers in primary
health care. Geneva, Aga Khan Foundation: 89–110.
Stinson W (1983). Information systems in primary health care. Washington, DC,
American Public Health Association, 1:1–76.
Tanner M, Lengeler C (1993). From the efﬁcacy of disease control tools to community effectiveness. Transactions of the Royal Society of Tropical Medicine
and Hygiene, 87:518–523.
Tekle DI et al. (1995). Health information system assessment study: ﬁndings and
recommendations. Asmara, Ministry of Health.
Thacker BS, Parrish RG, Trowbridge FL (1988). A method for evaluating
systems of epidemiological surveillance. World health statistics quarterly,
41:11–19.
Tugwell P et al. (1985). The measurement iterative loop: a framework for the
critical appraisal of need, beneﬁts, and costs of health interventions. Journal
of chronic diseases, 38:339–351.
Unger JP (1989). Evaluation du système national d’information du secteur santé.
[Evaluating a national information system for the health sector.] N’Djamena,
Ministry of Public Health: 1–25.
Unger JP, Dujardin B (1992). Epidemiology’s contribution to health service management and planning in developing countries: a missing link. Bulletin of the
World Health Organization, 70:487–497.
Valadez JJ (1991). Assessing child survival programs in developing countries:
testing lot quality assurance sampling. Cambridge, MA, Harvard University
Press (Harvard Series on Population and International Health).
Vaughan JP, Morrow RH (1995). Manual of epidemiology for district health management. Geneva, World Health Organization.
Walsh JA, Warren KS (1979). Selective primary health care. Social science and
medicine, 1979, 301:967–974.
Weber W (1989). Health management information system: Bamenda, Cameroon.
Yaounde, GTZ: 1–60.
White KL et al. (1977). Health services concepts and information for national
planning and management. Geneva, World Health Organization: 103–106
(Public Health Papers, No. 67).
Wilson R, Sapanuchart T (1993). Primary health care management advancement
programme. Washington, DC, Aga Khan Foundation.
Wilson RG et al. (1988). Management information systems and microcomputers
in primary health care. Geneva, Aga Khan Foundation.
World Health Organization (1981). Information support. In: Managerial process
for national health development. Geneva, World Health Organization: 57–60
(Health for all series, No. 5).
World Health Organization (1987). Report of the Interregional Meeting on
Strengthening District Health Systems, Based on Primary Health Care,
Harare, Zimbabwe 3–7 August 1987. Geneva, World Health Organization:
1–42 (unpublished document WHO/SHS/DHS/87.13; available on request

13

Design and implementation of health information systems

from Evidence and Information for Policy, World Health Organization, 1211
Geneva 27, Switzerland).
World Health Organization (1988a). The challenge of implementation: district
health systems for primary care. Geneva, World Health Organization (unpublished document WHO/SHS/DHS/88.1; available on request from Evidence
and Information for Policy, World Health Organization, 1211 Geneva 27,
Switzerland).
World Health Organization (1988b). Household surveys on health and nutrition.
In: Anderson JG, Aydin CE, Jay SJ, eds. Evaluation health care information
systems: methods and applications. Thousand Oaks, CA, Sage.
World Health Organization (1994). Information support for new public health
action at the district level. Report of a WHO Expert Committee. Geneva, World
Health Organization: 1–31 (WHO Technical Report Series, No. 845).

14

2

A framework for designing
health information systems
Theo Lippeveld and Rainer Sauerborn

Developing a “systems approach” for health
information systems
The need for improved routine health information systems is unequivocal
and well documented (WHO, 1986; de Kadt, 1989; Sandiford, Annett &
Cibulskis 1992; Lippeveld, Foltz & Mahouri, 1992). While there is a
general consensus that health information systems should be restructured, very few publications have focused on how to develop such systems.
It has even been argued that health information systems are idiosyncratic to the countries that develop them, and that no appropriate models
exist that can be applied to all countries (Foltz, 1993). A health information system in a largely urban country with a literacy rate of more
than 80%, a GNP per capita of more than US$1000, and mostly privately
operated health services will certainly be different from one in an
extremely poor country where the majority of the rural population is illiterate, and with predominantly government-managed health services. It
is obvious that each country has to develop or restructure its own speciﬁc
system, tailored to the prevailing socioeconomic, political, and administrative context. There are some common elements, however, which can
be adapted to create more effective and efﬁcient systems. Each health
information system has, at the minimum, some sort of informationgenerating process whereby data are transformed into information; and
to run this process, a more or less organized structure is present where
persons interact with resources, such as data collection instruments, or
with machines, such as computers.
This chapter intends to provide public health professionals with a
“systems approach” towards the development of health information
systems. How can the common elements be combined in such a way that
information is or becomes a real “resource” to solve health problems at
all levels of the health services system? What kind of system will
generate and disseminate information to support management rather
than to block it? In order to answer these questions, this chapter ﬁrst
examines the health information system structure and its breakdown
into components. We then describe an organizational model of the health
services with concentration levels from the periphery to the centre. Management functions at each level are discussed. Finally, we propose a
health information systems restructuring process in six steps, carefully
matching each step with the proposed health services model.

15

Design and implementation of health information systems

The health information system structure
In order to explain the conceptual link between health information
systems and the health services system at large, we start from the
generic deﬁnition of a management information system, as we previously
indicated in Chapter 1. Speciﬁcally, it is “a system that provides speciﬁc
information support to the decision-making process at each level of an
organization” (Hurtubise, 1984, p. 28). A health information system ﬁrst
of all is a “system” (Helfenbein et al., 1987, p. 2). Like each system, it
has an organized set of interrelating components which can be grouped
under two entities: the information process, and the health information
system management structure (see Fig. 2). Through the information
process, raw data (inputs) are transformed into information in a “usable”
form for management decision making (outputs). The information
process can be broken down in the following components: (i) data collection, (ii) data transmission, (iii) data processing, (iv) data analysis, and
(v) presentation of information for use in planning and managing the
health services.
Monitoring and evaluating the process ensures that the right mixture of
inputs produces the right type of outputs in a timely fashion. For
example, the information needed is continuously changing with changing planning and management needs. This will in turn affect data collection and other components of the information process. A health
information system can generate adequate and relevant information only
insofar as each of the components of the information process has been
adequately structured.

Fig. 2

16

Components of a health information system

A framework for designing health information systems

The unfolding of this stepwise process in space and time is not necessarily the same in all situations. Sometimes data collected are used
immediately and locally for a decision, with little processing or analysis.
For example, by asking patients how well they responded to treatment
(data collection), care providers can decide if follow-up visits are necessary (use of the information). Also, the decision-making process for daily
management tasks often consists of a set of “routine procedures”, where
data are immediately linked to a series of actions. This is the case with
standardized treatment guidelines, or with standard procedures for drug
management. In other situations, each of the steps in the informationgenerating process takes place in a different location and at a different
time. For example, data on the use of preventive services is collected at
the time of the patient/client visits, aggregated every month and transmitted from the health facilities to the district, and processed at the
provincial level. Each year, based on this data, coverage for preventive
services is calculated and communicated to the district level for further
analysis and action.
In order to make the information process efﬁcient, a health information
system management structure is required to ensure that resources are
used in such a way that the information process produces high-quality
information in a timely fashion. This structure can be further broken
down into two components: (i) health information systems resources, and
(ii) a set of organizational rules. Health information system resources
include persons (e.g. planners, managers, statisticians, epidemiologists,
data collectors); hardware (e.g. registers, telephones, computers); software (e.g. carbon paper, report forms, data-processing programs); and
ﬁnancial resources. Organizational rules (e.g. the use of diagnostic and
treatment standards, deﬁnition of staff responsibilities, supply management procedures, computer maintenance procedures) ensure efﬁcient use
of health information system resources.
Thus designing or redesigning health information systems will need to
address in a systematic manner each of these components of both the
information process and the management structure. The ultimate objective is that health information systems provide speciﬁc information
support to the decision-making process within the health system at large.

The relationship between the health information system
and the health system at large
A health information system cannot exist by itself but is a functional
entity within the framework of a comprehensive health system that
offers integrated health services, including curative care, rehabilitative
care, disease prevention, and health promotion services. The health
information system structure should permit generation of the necessary
information for rational decision making at each level of the health services system. This health system is composed of various levels between
the centre and the periphery, each with different management functions,
health services provision, and resource availability. Ideally, services and
resources should be as available as possible to the periphery, to optimize
access by the population. But there are limits to the degree of decentralization related to the provision of technical competence (technical
limit); or to the efﬁcient use of equipment (economic limit); or to the distribution of power (administrative limit). For example, it is neither possible nor desirable that every patient with a urinary infection be treated
17

Design and implementation of health information systems

Fig. 3

Organizational model of the health services

by a urologist; or that each ﬁrst-level care clinic has ultrasound equipment. We therefore call these levels “concentration levels”. Classically,
three concentration levels are described: the primary level, the secondary
level, and the tertiary level. The primary level is the point of contact
between the system and the population to whom health care is delivered.
The other levels—the secondary or district level, and the tertiary level—
provide specialized services as well as planning and management
support. In many countries the tertiary level is further divided into
regional (or provincial) and central levels.
Each of these levels has speciﬁc functions, implicating a series of speciﬁc
decisions to be made, ultimately leading to improvement of the health
of the population. From a management perspective, functions can
be grouped in three types of management functions, related to
(i) patient/client management, (ii) health unit management, and
(iii) health system management (see Fig. 3). Patient/client and health
unit management functions are directly related to the delivery of promotional, preventive, and curative health services to the population.
They include all interactions between the health unit staff and communities in their catchment areas. The health system management functions consist in the provision of coordination and management support
to the service delivery levels. Decisions to be made under each of these
types of management functions are different. The management information systems literature would call the patient/client and health unit
management decisions “operational”, and the system management decisions “strategic planning” or “management control” decisions.
The organizational model of the health services described above and
depicted in Fig. 3 will allow us to identify at each concentration level
what the speciﬁc management functions are, who the information users
are, and what decisions they have to make. This in turn will permit us,
at each level, to deﬁne information needs and to develop or restructure
data collection methods and instruments, data transmission and processing procedures, as well as appropriate feedback reports.

18

A framework for designing health information systems

Patient/client management functions
The main patient/client management function is to provide quality care
to patients and clients, curative as well as preventive and healthpromotional, at the ﬁrst level as well as at the referral level. A vast literature has been produced on how to deﬁne quality of care. An excellent
semantic discussion is given in a World Bank Technical Paper by De
Geyndt (1994). Quality of care assessment, according to the conceptual
model of De Geyndt, should look at the inputs (“structure”) of health care,
at the process, and at the outcome. In the context of this book, we want
to relate the provision of quality care to a series of decisions that care
providers (and their supervisors) have to take at each level of the health
services. How can an information system support these decisions in the
most relevant and effective way? We prefer to focus on a process-oriented
deﬁnition of quality care.
As explained before, quality care will be deﬁned differently depending
on the concentration level. Quality care at the ﬁrst level is comprehensive, integrated, and continuous; it focuses on patients and clients in
their immediate sociocultural environment (Public Health Research and
Training Unit, 1980). Quality care at the referral level is much more
dependent on the input of human and technical resources, and can therefore be deﬁned in terms of technical excellence according to the “state of
the art”.
The user of information at the patient/client level is the care provider—
the doctor, the health auxiliary, the midwife, but also the community
health worker or the traditional birth attendant. A well-designed health
information system can be a major tool in improving the quality of care
delivered by care providers, by generating the information they need to
make appropriate decisions, as in the following illustrations:

• The date, ﬁndings, and treatment prescribed during the last visit will
help the care provider to make better decisions for a tuberculosis
patient visiting a rural health centre (continuity of care).
• A child of 2 years is brought by his mother because of a skin rash and
diarrhoea. Does the care provider have the necessary information
support to know whether the child has already had measles or
whether he was vaccinated (integration of care)?
• In order to decide what vaccine to administer to an 8-month-old child
brought to the clinic, the health auxiliary needs to know what type of
vaccines the child has already received and on what dates (continuity
of care).
• The pathology results of a biopsy specimen of the cervix will assist the
surgeon to decide whether to perform a hysterectomy.

Health unit management functions
The general management objective of a health unit is to provide health
care to a deﬁned population in the catchment area surrounding the
health unit with a given amount of resources. Health units can be
classiﬁed according to the level of concentration of resources: ﬁrst-level
care units, and referral-level care units. Management functions are
speciﬁc for each type of health unit. They can be further subdivided into
service delivery functions and administrative functions.

19

Design and implementation of health information systems

Service delivery functions are deﬁned based on the health needs of the
communities served by the health units. First level care units provide a
package of general health care services. There is a great deal of variation in the setting of a ﬁrst level care health unit, as shown by the various
forms of such units: dispensary, clinic, health centre, basic health unit,
rural health centre, sub-health centre, ﬁrst aid post, community health
post, and so on. These different facilities may also cover differences in
functions. Until quite recently, most of these units provided only curative care, as indicated by the name “dispensary”. In some instances, ﬁrstlevel care health units have been given specialized functions and
activities: maternal and child health centres, tuberculosis centres, sexually transmitted disease clinics, family planning clinics. Often the availability of personnel determines the types of activities delivered at the
ﬁrst level. For example, if ﬁrst-level care units are operated by a doctor,
they probably can offer a wider range of services than if they are operated by a community-based health worker trained in 3 months. Also,
material resources limitations can be at the origin of the range of services provided. For example, without refrigeration equipment, ﬁrst-level
care facilities cannot provide immunization services.
Since the conference in Alma Ata in 1978, most countries in the world
have adopted the strategy of primary health care. This implies that a
package of essential health care, including curative as well as preventive and promotional activities, should be provided to as large a segment
of the population as possible. This package focuses on priority health
problems in the community, for which simple and effective technologies
exist, and which can be solved by general health care providers with
essential equipment and drugs, taking into account the available
resources in the country. The World Bank in its 1993 World development
report suggests that, based on cost-effectiveness studies, the “minimum
package” should include at least the following activities: prenatal and
delivery care, family planning services, management of the sick child,
treatment of tuberculosis, and case management of sexually transmitted
diseases (World Bank, 1993). Most of these activities are housed in a
ﬁrst-level care unit.
At the referral level, hospitals and specialized outpatient clinics provide
services and techniques for which the technical complexity and costs are
not justiﬁed at ﬁrst level care units. The district hospital is the ﬁrst referral unit or secondary care unit. Provincial and national hospitals are
mostly tertiary care units. Again, which speciﬁc services and techniques
will be offered at what level will vary from country to country, or even
from region to region. For example, in some countries, district hospitals
do not offer ophthalmological surgery, while in other countries they do.
Table 3 provides a list of service delivery functions adopted by the
Ministry of Health in Chad in 1989. In support of the service delivery
functions, health units also have administrative functions, such as
personnel management and training, ﬁnancial management, drugs and
supplies management, and information management. Obviously, such
functions will increase in complexity with the size of facilities, from a
ﬁrst-level care unit staffed by a health auxiliary and a midwife, to a tertiary care hospital with hundreds of beds and staff.
Once functions and activities of the different types of health units in a
given health services system have been clearly deﬁned, we can easily
identify the information needed for decision-making:
20

A framework for designing health information systems

Table 3

Service delivery functions in health units in Chad
First level (dispensaries, infirmaries):
— to provide curative care services for the most common health problems
— to provide prenatal care services
— to organize under-5 clinics (including immunizations)
— to provide follow-up services for chronic diseases
— to organize nutritional rehabilitation clinics
— to provide family planning services
— to ensure communication with the population in the catchment area.
Secondary (or first referral) level (centres medicaux):
— to manage medical and surgical emergencies
— to provide X-ray and laboratory services
— to organize outpatient referral clinics
— to provide inpatient services (medicine, surgery, paediatrics, and gynaecology/obstetrics)
— to manage complicated deliveries.
Tertiary level (hôpitaux de préfecture, hôpital national):
In addition to the functions of secondary level,
— to provide all types of surgical interventions
— to provide specialized care.
Source: Translated and adapted from Unger (1989).

• A health centre is supposed to provide treatment to tuberculosis
patients. The ofﬁcer in charge would like to know how many patients
out of those who started treatment in the health centre abandoned
their treatment prematurely (dropout rate). This information can
prompt the health ofﬁcer to improve follow-up of tuberculosis patients.
• One of the functions of a health centre is to provide prenatal care to
all pregnant women in the catchment area, and to refer those at risk
for delivery to the district hospital. In the last few months, several
women from surrounding villages are reported to have died in childbirth or shortly thereafter. The ofﬁcer in charge and the midwife of
the health centre would like to know how many women out of the total
expected pregnancies in the catchment area of the health centre
receive prenatal care. This information will guide the midwife in reorganizing prenatal care activities in a more effective way.
• A district hospital with 200 beds provides inpatient care to a population of 200,000. For about a year, beds have been constantly full, and
patients are hospitalized on improvised ﬂoor beds. The superintendent would like to know the average length of stay of the
patients in each department in order to decide whether more beds
are needed, or whether alternative discharge procedures could solve
the problem.
• A tertiary hospital functions with a given annual budget. Revenues
come from government subsidies, from health insurance payments,
and from user fees. In order to prepare an annual budget, the ﬁnancial
director of the hospital will need data of the previous year on revenues
by source and on expenditures by cost centre.

Health systems management functions
The objective of health systems management is to coordinate and provide
planning and management support to the service delivery levels. Some
examples of generally accepted health systems management functions
are:
21

Design and implementation of health information systems

— establishment of health policies and legislation;
— intersectoral coordination;
— strategic planning and programming;
— budgeting and ﬁnancial resource allocation;
— organization of the system, including referral mechanisms;
— personnel development including continuing education;
— resource management, including ﬁnance, personnel, and information;
— distribution and management of equipment, supplies, and drugs;
— disease surveillance;
— protection of the environment;
— supervision of the health services.
Health system management functions vary for each concentration level.
Their distribution from the periphery (classically the “health district” is
the most peripheral health system unit) to the centre (regional and
national levels) and, consequently, their decision-making power depends
on the way the health system has been administratively organized in
each country.
The main poles between which most national health systems can be situated are centralized and decentralized systems; government and private
sector-managed systems; and horizontally managed health services
systems and health services systems managed predominantly by vertical programmes. For example, budgeting and decisions on ﬁnancial
resource allocation will be made at the national level in a centralized
health system; in other health systems, these functions have been delegated to the district level. In a country with a predominantly private
sector-managed health system, most of the listed functions are performed
by private institutions, whereas the government has only a regulatory
role, setting policies and making legislation. In a health system managed
mainly through vertically organized health programmes, programme
managers have taken over responsibilities in resource management and
supervision from the line managers. Table 4 lists management functions
at central, regional, and district levels in a decentralized health services
system as proposed by WHO (1988).
Again, based on the speciﬁc health system management functions at each
concentration level, information needs can be rationally determined and
data collection procedures developed to generate the required information. Health planners and managers can use a variety of information
sources, but should be sure that the amount and nature of the data to
be reported by the operational levels of the health services are reasonable to avoid burdening health care providers. Ideally, health services
staff should only report data which are useful for patient/client management or for health unit management. All other information required
at this level could be generated by data sources other than health unitbased reporting.

Essential public health management functions
More recently, as part of the “health for all” renewal effort and the discussions on the role of the state versus the private sector in health care
provision, another group of management functions has been proposed—
“essential public health functions”. These functions have been deﬁned as
“a set of fundamental and indispensable activities carried out to protect
the population’s health and treat disease through means which are targeted at the environment and the community” (Sapirie, 1997). Typical
22

A framework for designing health information systems

Table 4

Health system management functions in a decentralized health
service system
The central level (Ministry of Health) is responsible for:
— health policy formulation, including policy on intersectoral activities;
— production of national health plans and regional and local planning guidelines;
— advisory role on allocation of resources, particularly capital funds;
— source of high level technical advice for specific programmes;
— control over purchasing pharmaceuticals and distribution of supplies;
— training and regulation of health personnel development;
— regulation of private profit and nonprofit health organizations;
— control of national health organizations and research institutes;
— liaison with international health organizations and aid agencies.
Regions and/or provinces are responsible for:
— regional health planning and programme monitoring;
— coordination of all regional health activities;
— employment and control of part or all of the health personnel;
— budgeting and auditing of health expenditure;
— approval and financing of large-scale capital projects;
— managerial and technical supervision of district health teams and district;
heads of specific health programmes;
— provision of supplies and other logistical support.
Districts are given the following main functions:
— organizing and running the district hospital services;
— managing all other government health facilities;
— implementing all community-based health programmes;
— managing and controlling local health budgets;
— coordinating and supervising all government, nongovernment and private
health services within the district;
— promoting active links with local government departments;
— promoting community participation in local health service planning;
— preparing an annual health plan;
— raising additional local funds;
— in-service training of health workers;
— supervising and controlling all community health workers in the district;
— collecting and compiling routine health information and forwarding it to regions and ministries
of health.
Source: WHO (1988).

examples of such functions are disease surveillance and protection of the
environment.
A working group on essential public health functions has further proposed to classify management functions according to three categories:
personal health care, health system management, and public health
(Sapirie, 1997). While the health system management category is very
similar, the categories of this classiﬁcation are difﬁcult to compare with
the one proposed earlier. As illustrated by the examples given in Box 1,
this classiﬁcation is particularly suited to ensure that during health
system reform efforts essential public health functions are preserved
somewhere in the system.
The design and implementation of an effective and efﬁcient health information system are intimately linked with and have to ﬁt into the organization of the health system for which it generates information. In this
book, when discussing the different health information system elements,
we will consider different organizational structures of health services
systems, particularly when presenting country cases. Nevertheless, in a
23

Design and implementation of health information systems

Box 1

Essential public health and health system reform

A recent meeting on primary health care systems provided an opportunity to introduce the concept of essential public health and to attempt to create a map of the
evolving concept of overall health systems in functional terms. There are some who
view public health as falling within the broadened definition of primary health care.
Without debating this point, an effort has been made to present the simplest possible view of the health system in terms of three categories of functions:
Health system management (health system maintenance and development)
This category would include such functions as health policy formulation; programme planning; resource mobilization and allocation; programme implementation, monitoring and evaluation; human resource development and management;
management of health research.
Public health
These functions include maintenance of information about the health of the population, protection of the environment, prevention and control of disease, health promotion and education, health legislation and regulation, and specific public health
services such as school health, occupational health, veterinary health services, and
public health laboratories.
Personal health care
This category would include all personal health care services, whether public
or private, possible organized in the traditional referral levels: primary, secondary,
tertiary, and specialized care.
As health systems undergo reform processes, such a functional map can assist
system designers in assuring that essential functions are preserved somewhere in
the system. This does not belabour the question of where or what primary health
care is, but instead attempts to depict specific, important health system functions.
Source: Adapted from Sapirie (1997).

more generic way we will base our approach for the development of
health information systems on the model of a health services system as
outlined above: a decentralized health system based on primary health
care, with district level decision making and active involvement of the
community, as put forward by WHO (1988).

Matching the health information system restructuring
process with the health services system
Effective health information systems provide information support to the
decision-making process at all levels of the health services. Thus health
information systems should ﬁt into the overall management structure of
the health services system. The question then is, how, in a very practical way, can existing inadequate routine health information systems be
transformed into effective management tools?

24

A framework for designing health information systems

The health information system restructuring process itself is a challenging and complex undertaking, particularly in the context of government bureaucracies in developing countries (Sandiford, Annett &
Cibulskis, 1992; de Kadt, 1989). Failures tend to be more common than
successes. In addition to purely methodological factors, the actual political, sociocultural, and administrative context can inﬂuence the outcome
of the reform process. In this chapter we focus particularly on the
methodological aspects of health information system restructuring. An
in-depth analysis of the impact of contextual factors on the health information system restructuring process is provided in Chapter 13.
The previously proposed health services model based on concentration
levels with different patient/client, health unit, and system management
functions as explained in previous paragraphs (see Fig. 3) is an excellent
framework on which to build or rebuild health information systems. All
along the health information system restructuring process, this model
will provide conceptual guidance on the different steps of the process.
Health information system restructuring rarely involves a total overhaul
of the system in a particular country or region. In fact, comprehensive
restructuring efforts often fail. Rather, health information system
restructuring should focus on the least functional aspects of the system,
or be planned in connection with ongoing health system reforms. For
example, reform of the ﬁnancial management system of the health
services requires particular health information system restructuring
focused on ﬁnancial information. Prior to any health information system
restructuring process, an in-depth assessment is required to identify
strengths and weaknesses of the existing system and to focus health
information system restructuring on those areas that are the least functional or constitute particular country priorities.
In order to undertake a systematic assessment of the existing health
information system, WHO proposes to categorize the health information
system under ﬁve interrelated “subsystems”:
— epidemiological surveillance for notiﬁable infectious diseases, certain
environmental conditions, and risk factors;
— routine service reporting from the basic health services at community
level, health centres, ﬁrst referral hospitals, and tertiary hospitals;
— special programme reporting systems, such as tuberculosis control,
maternal and child health, and school health;
— administrative systems, including health care ﬁnancing systems,
health personnel systems, drugs and logistic systems, ﬁnancial management systems, health-training programmes, health research programmes, and health documentation management;
— vital registration systems for births, deaths, and migratory
movements.
Chapter 5 provides a detailed methodological description of the initial
health information system assessment.
The health information system restructuring process itself can be broken
down into six steps addressing each of the health information system
components presented earlier. The four initial steps deal with the development of the information-generating process: (i) identifying information
needs and indicators, (ii) deﬁning data sources and developing data

25

Design and implementation of health information systems

collection instruments, (iii) developing data transmission and dataprocessing procedures, and (iv) ensuring use of the information. The two
last steps involve setting up the health information system management
structure necessary to ensure generation and use of the information: (v)
planning for the required health information system resources and (vi)
developing a set of organizational rules for health information system
management. The approach we propose is to carefully match each of the
health information system restructuring steps with the existing health
services system. Within the chosen subsystem and for each of the health
information system restructuring steps, particular attention needs to be
given to ensure that the information can be made available and is used
for decision making at the appropriate concentration level (from the
periphery to the centre) and for the identiﬁed management functions
(patient/client, health unit, and health system).

• Step 1: Identifying information needs and feasible indicators. The
amount of effort and time needed for this initial step will depend upon
the degree to which management functions have been deﬁned at the
time of health information system restructuring as part of the regular
health services planning and programming activities. Therefore,
initial health information system assessment should include a functional analysis of the health services, focusing on patient/client management, health unit management, and system management. Based
on the results of this functional analysis, it may be necessary to ﬁrst
agree upon a clear set of management functions. For patient/client
management, this could mean, for example, establishing standardized
service procedures; or for system management, delineating functions
between the district, regional, and national levels.
With clearly deﬁned management functions, identifying the information needed to make appropriate decisions at each management level
will become relatively easy. The real challenge at this step is to set
priorities and to select a limited number of feasible indicators, or
variables that measure change, taking into account the available
resources at each level, and without overburdening peripheral health
workers with data collection. Most important, selected indicators
have to be action-oriented and contribute directly to decision-making
by care providers, as well as by health planners and managers.
Chapter 4 will further detail this important step in the restructuring
process.
• Step 2: Deﬁning data sources and developing data collection instruments for each of the indicators selected. Most data for service delivery and resource management can be collected through the routine
health information system. At the system management level, for
policy setting and health planning indicators, data reported by health
units can be complemented with data from other sources such as
surveys or from other sectors. Data collection procedures need to be
standardized and adapted to the technical skills of the health workers
and the diagnostic equipment available. Data collection instruments
should be designed to promote, to a maximum degree, immediate use
of the information at the service delivery levels.
Again, it will be important to make sure that the procedural interaction between different concentration levels and for different management functions is consistent and minimizes duplication. For example,
standardized case deﬁnitions will ensure that epidemiological information at the primary level and at the referral levels is comparable.
Or data reported through the monthly report forms should be easily
retrievable from the patient/client record cards. Chapters 6 and 7 will
26

A framework for designing health information systems

provide a detailed overview of routine and nonroutine data collection
sources, methods, and instruments.
• Step 3: Developing a data transmission and processing system. The
data transmission system should respect established management
channels of the health services system and be responsive to the need
for intensive information exchange between different concentration
levels, between the community and the health services, and between
ﬁrst-level care and referral-level care institutions. Data processing
mechanisms will also vary depending on management needs: for
example, in a small health unit, data can be processed manually,
whereas in big tertiary hospitals and for system management, computers will be required. Whatever the mechanics, data processing
should generate information of acceptable quality for each management function and at all concentration levels (see Chapter 8).
• Step 4: Ensuring use of the information generated. Using information
is the ultimate objective of each information system. The combined
result of the ﬁrst three steps of the health information system design
process should be relevant and quality information. The most important step is to ensure that, based on appropriately designed feedback
mechanisms and innovative approaches in data presentation, this
information will be used to provide high-quality promotional, preventive, and curative services to patients, clients, and the community; in
managing of ﬁrst-level care centres as well as referral hospitals; in
planning and managing the health services system from the district
up to the national level; and in ensuring essential public health functions such as environmental protection and disease surveillance.
The main challenge of this step is to convince decision-makers at
central as well as at peripheral levels that quality information really
can help them to make informed decisions for patients and clients,
health units, and health system management, in other words, to
create an “information culture”. Succeeding in this endeavour,
particularly at the peripheral levels, will also result in better quality
of the data generated. Chapter 3 provides an in-depth discussion of
potential strategies to improve information use.
• Steps 5 and 6: Planning for health information system resources and
developing a set of organizational rules for health information system
management. Health information system efﬁciency and sustainability
will depend for a large part on the availability of human and physical resources and their organization into a well-designed management
structure. This health information system management structure
needs to be adapted to the physical and organizational realities of the
health services system: organizational procedures; personnel planning
and training; ﬁnancial allocations; equipment procurement and maintenance; and stock management of printed and computer supplies.
Again, the health services functions for patient/client management,
for health unit management, and for system management should be
the starting point for planning health information system resources
and for developing organizational rules for health information system
management. For example, training of health unit staff in data collection procedures should as much as possible be integrated with
training in clinical procedures for patient/client management. Or,
when designing a district level computerized system, the procedures
for the production of feedback reports should be linked to the supervisory timetables of the district management team.
As was pointed out before, health information system restructuring does
not necessarily address all concentration levels or all management
27

Design and implementation of health information systems

functions. The initial health information system assessment will reveal
the particular focus of restructuring. For example, if assessment of the
epidemiological surveillance system shows that case ﬁnding is functioning in a satisfactory manner, restructuring can be limited to improving
the transmission and processing of case information from the health unit
to the national level. As an example, Table 5 gives a list of illustrative
tasks for each step of the health information system restructuring
process to ensure its ﬁt with the health services system, focusing on the
routine service reporting subsystem. The third and fourth columns
indicate the link of the task with a particular concentration level or
management function within the health services system.
Box 2 shows how practically the health information system restructuring process has been intimately linked to the existing health services

Box 2

Pakistan: design of a health management
information system for first level care facilities

A general assessment of the existing health information system undertaken at the
request of the Ministry of Health of Pakistan pointed out that the system did not
provide adequate information for decision making, either to health managers for
system planning and management, or to health workers for facility or patient management. The reasons were multiple:
• Overall health information system management was weak.
• Indicators did not always respond to specific information needs at different levels
in the health system.
• Data collection in health facilities was poorly organized.
• Information flows were fragmented, because most national programmes had set
up separate reporting systems and, often, separate supervisory systems.
• Data consolidation and processing, mostly done manually, were time-consuming
and error-prone.
• Use of the information generated was greatly limited by the quality of the data
collected, by the fragmented flow of information, and by the lack of feedback
mechanisms.
After 20 years of “patching-up” interventions, the ministry felt that a more structured effort was necessary to transform the existing routine data collection system
into a management tool. It wanted an information system that would provide all the
necessary indicators for decision making at different management levels of the
health services: the patient/client management level, the health unit management
level, and the health system management level. A national workshop on health information systems was organized in May 1991 in Islamabad to decide on the content
and process of restructuring the health information system. A general consensus
was reached between federal and provincial health officials to transform the
existing routine reporting system in government-managed first-level care facilities
into a comprehensive and integrated health management information system
(HMIS/FLCF). Priority was given to first-level care facilities because most priority
health problems of mothers and children could be resolved at this level. Also, the
quality of the information system in referral-level facilities was considered acceptable. Although the private for-profit sector provides a significant portion of curative
care in Pakistan, it was felt that at least in an initial phase only governmentmanaged institutions should be included. The United States Agency for International Development (USAID) and the United Nations Children’s Fund (UNICEF)
28

A framework for designing health information systems

provided funding for technical assistance during the design phase and the initial
start-up costs of the system.
The design phase followed a stepwise process, first revising the informationgenerating process based on the information needs for first-level care facilities,
and then planning for the required resources to manage the information system. It
used a consensus-building approach involving a wide range of future HMIS user
groups. First the participants agreed on a standard comprehensive package of
health care services and resource management activities that had to be performed
in every first-level care facility. For each of these services and activities, essential
indicators were defined. Relevant data collection instruments were revised or newly
designed if necessary, with the help of experts. Then the participants agreed upon
reporting procedures and data flows within the health services system. In addition,
for the first time ever in Pakistan, participants decided to computerize the reports
sent by the first-level care facilities, in an initial phase at the divisional level, and
later on also at the district level. To this end, customized data processing software
was developed. About a year later, after several months of field testing in a sample
of health facilities, the Ministry of Health and the provincial health departments
approved the newly designed HMIS/FLCF. The following are the main features of
the system:
• HMIS/FLCF indicators were chosen based on the need for appropriate decision
making related to first level care services and activities.
• The system called for determining catchment areas around each FLCF and collecting population data for all villages in each catchment area. This resulted in
a population denominator that permitted calculation of coverage for preventive
maternal and child health services in the targeted risk groups.
• Case definitions for the main health problems were standardized. To ensure uniformity and reliability of data, complete instructions on how to collect, record,
and report data were provided to the care providers through a comprehensive
instruction manual available in English and in Urdu.
• Data collection instruments were simplified and reduced to a strict minimum. For
example, instead of 18 registers previously maintained by the FLCF staff for managing maternal and child health services, only 3 registers were needed under
the new system to record preventive services for mothers and children.
• Only indicators needed for health system management were routinely reported
through a single comprehensive monthly report. The report was designed in
such a way that the health unit manager could directly use the aggregated information for better planning and management in the health facility in question.
Also, whereas epidemic diseases were reported through the immediate report,
the yearly report served to update demographic and infrastructural information.
• Feedback reports on the main health problems, on services performed, and on
resources used were to be produced through simple customized database management software.
• A supervisory checklist was developed to assist district supervisors in assessing the quality of care given to patients and clients in the FLCFs and in providing supportive supervision to the FLCF staff.
HMIS/FLCF implementation started in 1993 through a massive inservice training
programme for health managers and care providers. Although it is still too early to
conclusively evaluate the system, the first results are encouraging. Care providers
say that the new data collection instruments are easy to use and provide the information they need for daily management of their activities. HMIS/FLCF is also an
invaluable tool in ongoing implementation of a decentralized district-managed
health services system in Pakistan. District managers use the information in the
recently established district level-planning process.

29

Design and implementation of health information systems

Table 5

The health information system restructuring process of the
routine services reporting system

Restructuring steps

Fit with the health services system

Step 1: Identifying information needs
and indicators

Illustrative tasks

CL

MF

• Identify information needs for follow-up of a pregnant woman in
a primary level clinic
• Identify indicators to ensure efficient drug management in a
referral hospital
• Identify indicators to monitor the quality of supervision by the
district management team

1

PC

2

HU

2

HS

3

PC

1

HU

Step 2: Defining data sources and
developing data collection
instruments

• Develop an appropriate record form for follow-up of
haemodialysis patient in a tertiary care hospital
• Develop a monthly reporting form for activities performed in a
primary level clinic
• Define data sources for a situational analysis at the district level

2

HS

Step 3: Develop data transmission and
data processing procedures

• Structure the information flow on pregnant women between the
traditional birth attendant and midwife in the health centre
• Ensure that monthly report forms from health centres are entered
in the district computer in a timely and accurate manner

1

PC

2

HS

• Develop user-friendly feedback formats for regional managers on
the utilization of inpatient services in the region
• Train health auxiliaries in follow-up procedures for hypertensive
patients using a standard record form

3

HS

1

PC

2

HS

3

HS

All
1

All
HU

2

HS

Step 4: Ensure the use of the
information

Step 5: Plan for the required health
information system resources

Step 6: Develop a set of organizational
rules

• Create positions of computer operators in cases where districtlevel data processing is computerized
• Submit revised recurrent cost budgets based on proposed new
data collection procedures
• Develop standard case definitions
• Change the job description of doctors in cases where health
information system restructuring involves their active
participation in data collection
• Develop an instruction manual for computer operators

CL = concentration levels, 1 = primary level, 2 = secondary level, 3 = tertiary level, MF = management function, PC =
patient/client, HU = health unit, HS = health system.

system framework during the design of an improved routine reporting
system for ﬁrst level care facilities in Pakistan in 1991–1992.

Conclusion
The proposed health information system restructuring approach will
assist system developers in addressing the weaknesses of existing
routine health information systems in developing countries in at least
three ways. First, it is adaptive to the information needs of health services at different strategic planning and operational levels, with particular consideration of care providers. If the information system
provides information directly useful for patient/client and health unit
management, care providers will be motivated to improve the quality of
the data collected for transmission to higher levels. Second, it permits
the development of a health information system in support of the health
services system in its entirety, rather than fragmented systems in
support of separate disease-oriented vertical programmes. Such a com30

A framework for designing health information systems

prehensive information system is much more effective in ensuring a continuous and bidirectional ﬂow of information between health services
levels. This exchange of information is the basis of patient referral and
counter-referral systems, supervisory systems, management support
systems such as drugs and supplies distribution systems, and the organization of essential public health functions such as disease surveillance.
Finally, and most important, as a result of the improved information
process and health information system management structure, more relevant and better quality information will be produced that is also more
likely to be used in the decision-making process at all levels and for all
management functions of the health system.
Using health information system development as a strategy to improve
the general management environment, as mentioned in Chapter 1,
makes the match of the information system with the existing or planned
health services system even more imperative. For example, in Pakistan,
building a population-based indicator such as maternal mortality into
the newly restructured health management information system for ﬁrst
level care facilities motivated the health unit staff to seek more active
community participation, a policy actively promoted by the national and
provincial governments. Or the creation of a comprehensive monthly
activity report combining previously separate report forms reinforced the
effort to integrate the health services, a strategy that was part of the
national health plan. Also, a well functioning intrasectoral health information system, established in a decentralized district health system with
the active participation of the population, can be the starting point for
the gradual development of an intersectoral health information system,
as proposed by de Kadt (1989).

References
De Geyndt W (1994). Managing the quality of health care in developing countries. Washington, DC, World Bank (World Bank Technical Paper, No. 258).
de Kadt E (1989). Making health policy management intersectorial: issues of
information analysis and use in less developed countries. Social science and
medicine, 29:503–514.
Foltz AM (1993). Modeling technology transfer in health information systems—
learning from the experience of Chad. International journal of technology
assessment in health care, 9:345–361.
Helfenbein S et al. (1987). Technologies for management information systems in
primary health care. Geneva, World Federation of Public Health Associations
(Issue Paper, Information for Action Series).
Hurtubise R (1984). Managing information systems: concepts and tools. West
Hartfort, CT, Kumarian Press: 1–168.
Lippeveld TJ, Foltz A, Mahouri YM (1992). Transforming health facility-based
reporting systems into management information systems: lessons from the
Chad experience. Cambridge, MA, Harvard Institute of International Development: 1–27 (Development Discussion Papers, No. 430).
Public Health Research and Training Unit (1980). Organisation des services de
santé: résumé. Material for an international course in health promotion.
Antwerp, Institute for Tropical Medicine.
Sandiford P, Annett H, Cibulskis R (1992). What can information systems do for
primary health care? An international perspective. Social science and medicine, 34:1077–1087.
Sapirie S, Essential Public Health Functions Working Group (1997). Primary
health care and essential public health functions: critical interactions. Paper
presented at the International Conference of the Council of International
Organizations of Medical Sciences, Geneva, 12–14 March 1997.

31

Design and implementation of health information systems

Unger JP (1989). Evaluation du système national d’information du secteur santé.
[Evaluating a national information system for the health sector.] N’Djamena,
Ministry of Public Health: 1–25.
World Bank (1993). World development report 1993: investing in health. New
York, Oxford University Press.
World Health Organization (1986). Improving health care through decisionlinked research: application in health systems and manpower development.
Part II: Options for implementation. Geneva, World Health Organization
(unpublished document HMD/86.4.2; available on request from Evidence
and Information for Policy, World Health Organization, 1211 Geneva 27,
Switzerland).
World Health Organization (1988). The challenge of implementation: district
health systems for primary care. Geneva, World Health Organization (unpublished document WHO/SHS/DHS/88.1; available on request from Evidence
and Information for Policy, World Health Organization, 1211 Geneva 27,
Switzerland).

32

14

Approaches to strengthening
health information systems
Theo Lippeveld and Steve Sapirie

Introduction
Information is crucial for decision-making at all levels of the health services. Policymakers need information for better allocation of scarce
resources; planners for the design of more effective programmes; district
managers for monitoring and evaluation of the health facilities under
their responsibility; health unit managers to ensure the community equitable access to the services offered; and, most of all, care providers to
provide quality care to their clients. In the last 2 decades, increasing
need for efﬁcient use of scarce resources has put information even higher
in demand. Cost recovery, quality management, and the development of
decentralized systems are all heavily dependent on well-functioning
health information systems.
The focus of this book has been on routine health unit-based information
systems. Routine health information systems, more than nonroutine
methods such as surveys or rapid assessment methods, are the main data
source in most countries. Yet they have the infamous reputation for
producing a plethora of irrelevant or low-quality data. Therefore, most
health managers, as a rule, do not use the information generated and
make decisions based on “gut feeling”.
By their nature, routine health information systems are intimately
linked with the health services structure. The hypothesis that restructuring routine health information systems can have a direct impact on
improved service delivery served as a major impetus for the authors to
write this book. Routine health information systems, to live up to this
potential, need to be more responsive to information needs of the health
services at all levels—particularly at the service delivery levels, where
the data are generated. This book, therefore, provides a health services
model based on concentration levels, where, from the periphery to the
centre, three types of management functions can be distinguished:
patient/client management, health unit management, and system management. Restructuring of routine health information systems means
better matching these management functions with the various components of the information-generating process and of the health information system management structure (see Chapter 2). Once routine health
information systems fulﬁl their support role to the decision-making
process at all levels, many expensive surveys can be eliminated, or at
least redirected to generate data that are not captured by routine
systems. In addition, such restructured facility-based systems can more
easily be linked to population-based community health information
systems as described in Chapter 9.

243

Design and implementation of health information systems

Although a clear conceptual model is helpful to the process of restructuring routine health information systems, it cannot provide all the practical approaches and strategies for successful health information system
design and implementation. It is for this reason that in the subsequent
chapters of the book, the authors integrate the text with country experiences in which they have been actively involved. This ﬁnal chapter
summarizes the lessons learned and sets an agenda for further development experiences.

Restructuring routine health information systems: what
works and what does not work?
The materials in this book have been assembled by a number of experienced professionals who have worked within health information system
development efforts around the world for over 20 years. Throughout the
book, these authors make frequent references to the many difﬁculties
that impede the development and successful use of routine health information systems or subsystems. Their collected observations conﬁrm that
a number of prerequisites must be satisﬁed to ensure that health data
generation and use will succeed. Conversely, there are also a number of
approaches and conditions that will almost certainly lead to failure. This
chapter identiﬁes both the prerequisites for success as well as the
approaches that do not seem to work, and proposes alternative strategies that may increase the chances of success.

Preconditions for success
High-level interest and sponsorship: in search of a “saint”
All health development efforts require the support of senior managers
and decision-makers, but nowhere is it more important than for the
restructuring of health information systems. Health information system
development touches all Ministry of Health departments, programmes,
and institutions, both technical and administrative, as well as other government departments. High-level direction and coordination are imperative for the success of a health information system development effort.
Eventually, a senior decision-maker, such as a director-general or deputy
minister, should be identiﬁed as the project director, or, as Peterson et
al. (1994) deﬁne him, as the “saint”. In order to fulﬁl their role as “system
development protectors” and to decrease resistance, directors should (i)
be committed to the health information system restructuring process, (ii)
be ready to take the necessary risks, and (iii) have the right political connections. The presence of a project director will facilitate participation
and cooperation from all departments and programmes, which in turn
will minimize duplication of data being recorded and reported, as well
as help to establish systemwide data standards and procedures. In addition, distribution of a policy statement and strategy description can also
give the development effort a certain legitimacy and clear deﬁnition of
purpose.
Broad agreement with the principle of “information for action”
at all levels
Early in successful health information system development efforts, managers and health workers at all levels must understand and acknowledge the importance of the linkage between management and
information. One critical principle is that all information generated by

244

Approaches to strengthening health information systems

the new system must serve the process of action taking at all levels:
within communities, for case management, for health unit management,
for district management, for central level programme management, and
for policy and planning at higher levels of the health system. Another
principle is that no data should be requested from a service level which
is not necessary and useful for managing the delivery of health care and
performing other public health functions. This principle will help prevent
the expansion of reporting requirements and ensure relevant monitoring
and evaluation of the health status and service performance by higher
health system levels.
Health information system development strongly linked to the
overall health system development and reform process
If a health information system is a functional entity within the framework of the health services as a whole, it is obvious that health information system restructuring can only succeed if it is narrowly linked
with reform at other levels of the health care system. For example, effective ﬂow of information within the health care system depends upon the
organizational structure of the health care system (organizational
reform). Similarly, without a clear set of priorities (programmatic
reform), managers and policymakers will ﬁnd it difﬁcult to agree upon a
set of essential indicators for the health information system. And, of
course, it is meaningless to restructure health information system for
health services that are not used by the population (systemic reform).
Efforts to implement more accessible decentralized district health
systems are now underway in several developed as well as developing
countries. Health information system restructuring is part of this effort,
as was stated by the WHO Expert Committee on Information Support
for New Public Health Action at the District Level: “Health information
is not only an essential resource for the development of district health
systems, but also an integral component of that development” (WHO,
1994).
Availability of a core health information system
development team
Successful health information system restructuring requires broad participation by future users at critical steps of the development process
such as the selection of essential health indicators or the standardization of case deﬁnitions. However, successful efforts are always spearheaded by a small group of experts who carry out the staff work needed
to develop standards, design criteria, and prototype databases. Moreover,
high-level sponsorship and support as proposed earlier may not be available from the outset. The health information system development team
may have to prove the worth of the proposed strategies by developing
modest products early, even while the development plans are still being
formulated.
Ideally, the health information system development team is multidisciplinary and includes, at a minimum, a health planner/epidemiologist, a
computer expert, and a skilled trainer. Such staff may come from institutes of public health or epidemiological units, but placing such groups
within the ministry of health during the entire health information
system development process is usually an advantage. In this way, they
can maintain communication with all services and programmes, and help
ensure institutionalization of the restructured system. It is extremely

245

Design and implementation of health information systems

important to keep the staff of the health information system development team in position during the entire health information system
reform period.

Characteristics of health information system development
approaches that are likely to fail
The folly of pursuing the grand design
Often the best-intentioned health information system projects fail
because their managers and system designers are too ambitious, wanting
to create an entirely new system that satisﬁes all user felt needs. The
result is a health information system project that attempts to revise all
data generation and reporting processes, whether they need improvement or not. Such efforts often attempt to integrate the generation and
maintenance of health data at all levels, whether or not such integration
is justiﬁed. These full system design efforts are intended to be systematic and efﬁcient, because they are led by systems analysts who know
how to normalize data. But the sheer difﬁculty of total system redesign
and implementation normally exceeds the technical and management
capabilities of most public sector health administrations. Such efforts are
seen to be expensive and time-consuming, and often result in the operation of parallel systems of reporting, due to the difﬁculty and ineffectiveness of the new system and its procedures.
Health information system restructuring for central-level
data accumulation
Traditionally, routine health information systems have been designed to
provide epidemiological and statistical data to the central administration and programmes in the ministry of health. While it is true that
central decision-makers need relevant information for policy and planning, the designers of such reporting systems often forget the important
principle that all data to be recorded and reported should, ﬁrst and foremost, be useful at the service delivery level. Even patient/client record
forms sometimes contain data which have no use in the care process, but
have been included because some central level ofﬁce feels they need the
data to monitor health or performance trends and produce annual
reports. Often this practice is reinforced by international donor agencies
which promote their own indicators while providing ﬁnancial assistance
in order to develop routine recording systems for capturing the necessary data. Such health information system restructuring methods wreak
havoc on information use at all levels: not only do care providers, discouraged by the burden of data collection, make little use of the data for
health unit and case management, but they also report incomplete and
invalid data to higher levels, making them useless for policy and planning actions.
Forms review and revision without conﬁrming the service
information needs
Related to the previous issue, there is a tendency for many health information system development projects to review and revise registers,
records, and forms used in service facilities, presumably to increase the
validity, relevance, and completeness of reports to higher levels. Even if
health information system developers start with proper identiﬁcation of
central level information needs, the result is usually only limited
improvement of the information generated, in spite of the extensive
resources and staff time consumed. Most important, these approaches
fail to improve the relevance and usefulness of the information gen246

Approaches to strengthening health information systems

erated to support service staff in delivering clinical and outreach services
to their patients and communities. Designers should place forms revision late in the health information system development plan of action,
after the identiﬁcation of information needs at all levels, and particularly at service delivery levels. Furthermore, they should only include
those recording improvements which reinforce the performance of proper
clinical and outreach procedures.
Information needs based on detailed decisions
New systems are often referred to as “management information systems”
which are intended to support managers in decision-making. Designers
therefore try to break down functions and activities into a list of decisions for which information needs are deﬁned. For this purpose, senior
service managers are carefully interviewed, but seldom do they know
what data are most useful for decision-making. In truth, speciﬁc day-today decisions are rarely made consciously, and are often based on
subjective feelings and experience. In any case, the designers’ and planners’ efforts generally produce long lists of data elements which are then
incorporated into the new design. The result is an overly complex system
which is even more burdensome to the care providers than the
“inefﬁcient” system it is intended to replace. One of the main assets of a
well-designed routine health information system is a simple but essential set of indicators able to identify key problems. If needed, additional
data and information to solve these problems can be generated through
ad hoc data collection or nonroutine methods.
Mistaking computerization for health information
system restructuring
One of the main objectives of many typical health information system
development projects is the computerization of important data to be
managed, monitored and analysed, and reported. In all countries,
there are always numerous opportunities to apply computers in new or
improved ways. However, whenever computerization becomes the
primary objective of a health information system development effort, the
more important purpose of serving the data needs of the care providers
may be lost. Registers and records will be redesigned for facilitating data
capture and entry, rather than reinforcing proper action for planning,
management, and service delivery. Computers are, ﬁrst and foremost, a
support tool for data processing, data analysis, and data presentation
and should be employed only if it is cost-effective to do so.
Donor-driven health information system restructuring
In the last decade, governments of developing countries have been under
pressure from multilateral and bilateral donor agencies to increase the
efﬁciency (and, less frequently, the equity) of their health care delivery
systems. Health care reforms have been imposed as “conditionalities” for
further disbursement of funds. In several countries, such external donor
pressure has been the real impetus for getting health information system
restructuring on the agenda. Although health information system
restructuring in these countries is, in actuality, key for improving planning and management of the health services, it is obvious that without
mobilizing national support, such projects ultimately cannot be sustained and may actually damage the existing routine health information
system.
Most of these “donor-driven” health information system restructuring
efforts include the redesign of the recording and reporting system, the
247

Design and implementation of health information systems

development of integrated databases, the training of national staff locally
and abroad, the abroad, the provision of computers, and the sponsorship
of on-site expertise. Sometimes these projects succeed in getting a new
recording and reporting system up and running within a 2-year period.
But often, once the project is terminated, the situation rapidly deteriorates with accumulation of software and hardware maintenance problems, incomplete and delayed reporting, and the lack of continuity of
national staff for managing the system. Part of the problem is the time
constraint facing the donor agency. It must deliver its support within a
ﬁxed period of time, whether the necessary prerequisites such as
national involvement and management capability are in place or not. A
second problem is that such projects have to be planned in their entirety
at the outset, with limited opportunity for revision in content and timing.
A third problem arises when several agencies support the health information system development process. Each agency has its own approach
and may ﬁnd it difﬁcult to collaborate with others. The national administration may ﬁnd it difﬁcult to act as the coordinator of the effort when
most of the resources, both ﬁnancial and human, are provided by the
donor agencies, often as a grant. While external support can bring useful
technical expertise and visibility from a political perspective, institutionalized and sustained health information system restructuring can
only happen if the national administration “owns” the reform process,
and therefore has full control over the content, the process, and the
resources required.

Characteristics of health information system development
approaches that are likely to succeed
Start every health information system development effort with
the deﬁnition of indicators based on a conceptually sound
health services system and speciﬁc management functions
within the services
If the ﬁnal outcome of health information system restructuring is
to ensure better information support to the health services system, then
the ﬁrst requirement for any health information system designer is to
have a clear understanding of how a health services system is structured
and which management functions are involved. The model proposed
in Chapter 2 categorizes management functions in three groups:
patient/client, health unit, and system management. Management functions further vary according to the concentration level: from periphery
to centre. They address curative, preventive, and promotional services,
personal care as well as public health services. When restructuring is
based on a conceptually sound health system model, information support
can be more easily translated into relevant and appropriate indicators.
The ﬁrst activity of health information system restructuring, therefore,
is the selection of indicators for health services support, health services
monitoring and management. This should be done through a consensusbuilding process involving health services managers at various levels,
such as senior executives, programme managers, and district service
staff. In countries where such a process has never taken place, the ﬁrst
step should be the development of a set of “essential” indicators. Such
indicators address well-deﬁned priority health problems, the services
required to control those problems, and the resources critical for service
delivery. They may also be used to monitor progress in health system
reform and management.

248

Approaches to strengthening health information systems

Apply an evolutionary, problem-directed approach for
improving the health information system
At the outset of a new initiative to strengthen the health information
system, the health administration may not have a clear view of all the
steps that need to be taken. In these cases, the early steps may involve
different types of assessments that conﬁrm where there are opportunities for improving the generation, use, and communication of important health data. Sometimes these assessments focus on speciﬁc types of
data and communications processes, such as the disease surveillance
system or the generation and use of clinic data. Planners and designers
can undertake overall assessments of health information subsystems to
uncover the cause of speciﬁc service and management issues or deﬁciencies. From such assessments, designers can use the ﬁndings to identify
the information-related problems that most need early attention. They
can then formulate short-term plans of action which include activities
needed to address some of the problems found. As the implementation proceeds, they can extend the plan of action to include more of the
components of the information system in need of strengthening. This
evolutionary approach to health information system development
allows for adjustment to accommodate new issues and opportunities for
improvement.
Include policy analysis as a full part of health information
system assessment
The success of health information system reform depends not only on
technical improvements but also on in-depth understanding of political,
sociocultural, and administrative factors. An essential question for
health information system designers is how “to add rationality while still
accommodating the interests of diverse constituencies and value
systems” (Reinke, 1988). As described in Chapter 13, we suggest undertaking an in-depth policy analysis as part of any health information
system restructuring process. Following the model proposed by Walt and
Gilson (1994), such analysis includes (i) identiﬁcation of all actors with
stakes in the health information system reform (political mapping), and
(ii) research on contextual political, socioeconomic, and administrative
factors likely to inﬂuence the outcome of the health information system
reform.
Enable broad participation in the health information system
design process, but ensure technical soundness throughout by
the use of a health information system design team
Everyone in the health sector cannot participate in all aspects of the
design and implementation of health information systems, but based on
careful policy analysis, the design team should at least ensure participation of key actors in the process and thereby foster their understanding
and ultimate support during the implementation. Selected programme
managers and service staff should be involved in the selection of essential health indicators. In addition, programme and service staff should
participate in rapid assessments of health information system performance, as well as oversee speciﬁc functions such as disease surveillance
and control, and clinic diagnosis and recording. The results of such
assessments as well as options for improvement can be presented to
larger groups of future users, and ultimately create broad ownership of
the restructured health information system. This applies particularly to
the establishment of standard case deﬁnitions and of standard treatment
guidelines. Nevertheless, a considerable amount of health information
system design and development work must be carried out by specialists
249

Design and implementation of health information systems

belonging to the health information system development team. Report
design, reporting procedures, database design, and the design of recording formats and registers need to be carried out by system analysts,
epidemiologists, clinical specialists, and computer specialists, drawing on
the inputs of programme and service staff.
Introduce information technology in an effective, efﬁcient, and
sustainable manner
Successful projects make judicious use of computer and communications
technology at points in the system that will most beneﬁt from this technology. The expansion of computer use, particularly at subnational
levels, is undertaken gradually, and fully involves staff who will be
required to enter data and use the resulting information. The development of databases and software is carried out within the country, with
the full involvement of the staff who will be required to maintain and
further develop the computer system. Hardware systems, even if
ﬁnanced by external sources, should take into account the local capacity
to bear the recurrent costs generated by such systems. Imported software applications should be avoided. If commercial support is received
in the development of the software, local ﬁrms should be used to ensure
that maintenance capability is on hand. Both computer and communications hardware should have local sources of maintenance.
Attempt to produce useful, new information processes and
products early in the development effort
The evolutionary health information system development strategy must
insure that useful products are generated early in order to gain the
conﬁdence and support of senior managers, programme managers, and
service staff. The conﬁrmation of essential indicators is often one such
product, and it leads naturally to others. Frequently, countries recognize
that their clinicians are not applying standard case deﬁnitions in their
recording of diagnoses. Sometimes such standard case deﬁnitions are not
known or promulgated in the services. Establishing standard deﬁnitions
for common and important health problems and conditions is a useful
early product in health information system development. Frequently
underuse of existing information is a major lacuna which can be
addressed early through processes such as district or facility level
problem-solving exercises. Before designers create solutions or interventions addressing these lacunas, they often request service staff to analyse
their existing records and reports to assess performance and to understand the cause of operational problems. If carried out effectively, such
activities inspire interest and ideas for further improvements of the
information system.

An agenda for further health information system
development experiences and research
While the experiences of health information system restructuring efforts
in various countries have permitted the authors to propose a list of useful
health information system development strategies, many questions
regarding the development of relevant health information systems
remain unanswered and need further experience and research. We conclude this book by inviting interested health system developers and
researchers to address such questions through carefully set up health
information system projects and research studies. The list of questions
presented in Box 39 is certainly not exhaustive, but hopefully it will
250

Approaches to strengthening health information systems

Box 39

Future directions

General health information system development questions
• How can service providers and particularly communities as key information
users be more actively involved in health information system development
efforts?
• What is the ideal process and level for development of interdisciplinary social
information systems, through which interactions between health, education, and
economic development can be identified in an action-oriented manner?
• Given the benefits of a population-based community health information system,
as described in Chapter 9, how can it effectively be linked to the facility-based
routine health information system?
• Can health information system reform by itself have a direct impact on improved
functioning of the health services, and if so, how?
Questions on indicator selection
• What are relevant and operational indicators for management support systems
such as financial systems, personnel planning and management systems, building and equipment management systems (in addition to health problem and
health services indicators for which extensive experience is available)?
• How can qualitative information be operationalized in a routine health information system (e.g. the quality of interpersonal relations between the care providers
and the patients)?
Questions of data collection
• How can patient/client data recording be improved in order to help care
providers to monitor and maintain the quality of their services?
• What innovative structural interventions can be proposed to better link routine
service statistics with other nonroutine data collection systems (surveys, vital
events registration, rapid assessments methods, etc.)
Questions of data transmission
• In hierarchical vertical transmission systems (still the most common data transmission system in many countries), how can the speed of data transfer be
improved?
• What is the most efficient way to provide feedback to lower levels in systems
where data are compiled at higher levels?
Questions on the use of information
• What is the relationship between the format in which information is displayed
(maps, action-oriented graphs, etc.) and its use in management decisions?
• How can one design and conduct training that effectively improves the actual
use of information for health services planning and management?
Questions on computerization in the health sector
• Is there an approach for determining where computerization is likely to pay the
greatest dividends?
• What is an efficient strategy for designing and testing computer support for
important components of the health information system such as hospital data,
surveillance data, and various types of administrative information such as supplies, budget, and human resources management?

251

Design and implementation of health information systems

further contribute to establishing health information systems responsive
to the management needs of effective and efﬁcient health services
systems in both developed and developing countries.

References
Peterson S et al. (1994). Computerizing personnel information systems in African
bureaucracies: lessons from Kenya. Cambridge, MA, Harvard Institute for
International Development: 1–25 (Development Discussion Paper, No. 496).
Reinke WA (1988). Industrial sampling plans: prospects for public health applications. Baltimore, MD, Johns Hopkins University School of Hygiene and
Public Health, Institute for International Programs: 1–36.
Walt G, Gilson L (1994). Reforming the health sector in developing countries:
the central role of policy analysis. Health policy and planning, 353–370.
World Health Organization (1994). Information support for new public health
action at the district level. Report of a WHO Expert Committee. Geneva, World
Health Organization: 1–31 (WHO Technical Report Series, No. 845).

252

ANNEX

1

Classes of indicators and their major attributes

The matrix below outlines the four classes of indicators, that is input,
process, output, and outcome, and their major attributes. The deﬁnition
and an example of an indicator are given for each attribute. Finalization
of a set of indicators for a health management information system will
require that the concise set of selected indicators be balanced as a set.
As described by Bulatao (1995), “Balance in a set of indicators requires
even-handed coverage of different [health system] goals and proportionate attention to key [health system] processes. Imbalance is often easy
to identify, even in a large set of indicators: the 103 proposed by Bertrand
et al. (1994), for example, lack any indicator relating to reproductive
health outcomes or to program costs, though these are promised for later
editions of their handbook. Balance is more critical, and often more
difﬁcult to achieve, the smaller the set of indicators. A small set cannot
afford to overlook important attributes. This may mean relaxing some of
the criteria highlighted . . . for the identiﬁcation of ‘good’ indicators at
points. Not all aspects of the [health system] are well-researched, and
some weak indicators may have to be provisionally accepted”.

Classes of indicators
and their attributes
INPUTS
Availability of
resources

Health determinants
(risk factors)

PROCESS
Service delivery and
support activities

Definition

Example

Inputs are the human and financial resources, physical facilities,
equipment, operational policies, and organizational
arrangements that enable services to be delivered in the
health system. This definition encompasses both the
availability of resources, as well as the organizational
structure of the system. The organizational arrangements, in
turn, reflect authority–responsibility relationships,
organizational design features, governance and
empowerment issues, proximity of financial responsibility to
operational accountability, the degree of decentralized
decision making, and what kinds of decisions are
delegated (De Geyndt, 1994). Donabedian (1980) considers
structural inputs like physical inputs, staffing, money, and
organizational arrangements as measuring quality of care.
Determinants refer to conditions that contribute to or are
precursors of disease such as human behavioural factors or
unhealthy environmental conditions. It includes factors such
as cigarette smoking, alcohol use, obesity, low birth weight,
and so on which have a negative impact on health.

• Indicator for availability of
resources: trained nurses
per 10,000 population.

Service delivery and support activities represent the bulk of the
process indicators. In Cameroon, the information system
provides indicators for the following support activities at the
primary health care level:
— community participation;
— supervision;

• Indicator for support
activities: proportion of
health districts that
have at least one trained
professional for IUD
(intrauterine device)
insertion.

• Indicator of risk factor:
proportion of live-born
infants weighing less
than 2500 g at birth.

253

Design and implementation of health information systems

Classes of indicators
and their attributes

Quality of services
and support
activities

Definition

— human resources (training, incentives);
— financial management (public funding and cost recovery);
— drug management;
— maintenance.
Quality of service indicators seek to address how well the staff
perform their curative, preventive, and promotive tasks, as well
as whether appropriate medical supplies and medications are
available at the facilities. The quality of support activities is
checked by measuring how well the support activities are
carried out.

Financial
accessibility

Financial accessibility measures the extent to which people are
able to pay for care. This is usually measured through a
community-based willingness and ability to pay survey.

Geographical
accessibility

Geographical accessibility measures the extent to which
services are available and accessible to the population. It is,
of course, linked to the distribution of infrastructure in a given
region but also to the actual offering of these services at
these facilities. Geographical accessibility will vary according
to local means of transportation, as well as the local
topography. In developing countries, services are generally
considered accessible if they can be reached within a 1-hour
walk. Accessibility can also be expressed in terms of distance
(population living less than 15 km from the facility).
Indicators of cultural accessibility consider whether access to
health services are impeded by cultural taboos. Three
examples are provided: (i) Can women use reproductive
health services if all of the physicians in the facility are male?
(ii) Will persons who belong to an ethnic minority use services
that are staffed by the majority population? (iii) Will persons
use health services for processes that are considered
“natural”, that is without the need for health intervention (such
as pregnancy)?

Cultural
accessibility

OUTPUT
Use

Use is the expression of the demand for services.

Coverage

Coverage measures the proportion of a target group that has
received a particular service.

Financial
performance

Financial performance measures the financial viability of the
organization.

Acceptability
(perceived
quality)

Acceptability or perceived quality considers the extent to which
patients are satisfied with the services offered. A patient’s
perception of the quality of care typically reflects the
congeniality of the providers and waiting times, in addition to
the technical competence of the facility staff.

254

Example

• Indicator of quality of
services: proportion of
women delivering at the
health centre who are
effectively immunized
against tetanus.
• Indicator of support
activities: proportion of
refrigerators in the district
that are out of order.
• Indicator of financial
accessibility: proportion
of people who are able
to pay for a particular
service, considering both
personal contributions
and health insurance.
• Indicator of geographical
accessibility: proportion
of the population living
within walking distance of
less than an hour from a
health centre.

• Indicator of cultural
accessibility: proportion
of pregnant women in a
catchment area who can
independently choose
(and afford) to go to a
clinic for treatment of a
sexually transmitted
disease.

• Indicator of use: number
of curative care episodes
per 1000 population.
• Indicator of coverage:
proportion of pregnant
women who received at
least two antenatal care
visits of appropriate
quality while pregnant.
• Indicator of financial
performance: proportion
of total costs actually
recovered by the costsharing programme.
• Indicator of perceived
quality: proportion of
patients who are satisfied
with the service provided
and would return to the
provider for future care.

Annex 1

Classes of indicators
and their attributes

Definition

Example

Behavioural
changes

Indicators of behavioural output consider whether clients change
their health-related conduct as a result of contact with a
health-care facility or its information, education, and
communication campaigns. It should be noted that
Donabedian (1988) classifies behavioural changes as
outcomes.

• Indicator of behavioural
changes: proportion of
mothers breastfeeding
babies up to 18 months
of age, before/after an
intervention.

These indicators measure the mortality and the morbidity
(disability) for certain health conditions. Since facility-based
health management information systems give only a limited
perspective on the health status of a population, facility
records should be supplemented with information from
community-based surveys, vital registration, censuses, and
other data collection instruments to fully understand health
outcomes within a population. Health outcome indicators from
a routine information system are important, though, because
they monitor the conditions that impact on the management
of health services and help managers to make resource
allocation decisions.
Effectiveness is the extent to which objectives are achieved.

• Indicator of health
outcome: number of
deaths from pregnancyrelated and puerperal
causes during a given
year divided by the
number of live births
during the same year per
100,000 pregnant women
(the maternal mortality
ratio).

OUTCOME
Health outcomes

Effectiveness

Efficiency

Sustainability

Equity

Efficiency is the extent to which objectives are achieved by
minimizing the use of resources. Cost is a major concern in
both developed and developing countries.
Sustainability is the ability or prospect to continue, prolong,
keep something up (Wilson & Sapanuchart, 1993).
Equity, or whether health services are provided “justly” within a
population, is difficult to measure since it carries moral and
political connotations. For this reason, few indicators have
been unanimously agreed upon. Indicators include
accessibility of health services, use of health services by
demographic groups, inequalities in mortality and morbidity
among different subgroups of the population, unequal
distribution of health resources, and so on.

• Indicator of effectiveness:
proportion of children
under 1 year of age that
are immunized against
measles (compared with
the national objectives of
80% coverage).
• Indicator of efficiency:
cost per child
vaccinated.
• Indicator of sustainability:
proportion of donor
funding to total funding.
• Indicator of equity:
proportion of selected
categories of health
personnel to the
population in different
provinces or districts.

References
Bertrand JT et al. (1994). Handbook of indicators for family planning program
evaluation. Chapel Hill, NC, University of North Carolina at Chapel Hill.
Bulatao RA (1995). Key indicators for family planning projects. Washington, DC,
World Bank (World Bank Technical Paper, No. 297).
De Geyndt W (1994). Managing the quality of health care in developing countries.
Washington, DC, World Bank (World Bank Technical Paper, No. 258).
Donabedian A (1980). Exploration in quality: assessment and monitoring. Vol. 1:
The definition of quality and approaches to its assessment. Ann Arbor, MI,
Health Administration Press, School of Public Health, University of
Michigan.
Wilson R, Sapanuchart T, eds. (1993). Primary health care management
advancement program. Geneva, Aga Khan Foundation.

255

ANNEX

2

National lists of indicators: the trade-off between
conciseness and completeness

We draw the attention of the reader to the fact that there is a need to
make a trade-off between conciseness (limiting the number of indicators)
and completeness (targeting all attributes) in the selection of indicators.
As an illustration of conciseness, the following list of indicators was
selected for assessing community health status and monitoring progress
towards the year 2000 in the United States.

Progress towards the year 2000 objectives:
consensual agreement by expert committees
Indicators of processes
• Proportion of children under 2 years of age who have been immunized with the
basic series (as defined by the Immunization Practice Advisory Committee)
• Proportion of adults aged 65 years or older who have been immunized for pneumoccocal pneumonia and influenza
• Proportion of assessed rivers, lakes, and estuaries that support beneficial uses
(fishing and swimming approved)
• Proportion of women receiving a Papanicolaou smear at an interval appropriate
for their age
• Proportion of women receiving a mammogram at an interval appropriate for their
age
• Proportion of the population uninsured for medical care
• Proportion of the population without a regular source of primary care (including
dental services)
Indicators of health status outcome
• Race/ethnicity-specific infant mortality, as measured by the rate (per 1000 live
births) of deaths among infants less than 1 year of age
• Death rates (per 100,000 population) for:
— motor vehicle crashes; work-related injury; suicide; lung cancer; breast
cancer; cardiovascular disease; homicide; all causes
• Reported incidence (per 100,000 population) of:
— AIDS; measles; tuberculosis; primary and secondary syphilis; percentage of
children under 5 years of age who are tested and have blood lead levels
exceeding 15 mg/dl; incidence of viral hepatitis B, per 100,000; proportion of
children aged 6–8 and 15 years with one or more decayed primary or permanent teeth
256

Annex 2

Indicators of risk factors
• Incidence of low birth weight, as measured by percentage of total number of
live-born infants weighing less than 2500 g at birth
• Births to adolescents (females aged 10–17 years) as a percentage of total live
births
• Prenatal care, as measured by the proportion of children under 15 years of age
living in families at or near the poverty level
• Proportion of persons living in countries exceeding US Environmental Protection
Agency standards for air quality during the previous year
Indicators of risk factors (age-specific prevalence rates)
• Cigarette smoking; alcohol use; obesity; hypertension; hypercholesterolaemia;
confirmed abuse and neglect of children
Source: The Nation’s Health, Journal of the American Public Health Association, September 1991.

257

258

Inadequate
response to
disease
outbreaks and
notifications

Non-use of routine
service reports
for resource
allocation

Service Reporting
Case Monitoring
Task Performance

Use of
Information
—
Decisions and
Actions

Problems of using
standard computer
applications for
data management
and analysis

Inappropriateness
of data
processing and
presentation of
computer
software
Delays in report
preparation and
submission

Data Analysis
—
Transmission
Reporting

HIS components of assessment

Inefficiency of
data collection
procedures

Lack of standard
case definitions

Data Input
—
Recording and
Collection

Inadequate and
uncoordinated
funding for health
activities

Lack of a regular
budget for
hardware and
software purchase
and staff training

Financial Resources

Inadequate staff
training and job
descriptions at
all levels of the
health system

Lack of
supervision of
surveillance
activities

Inadequate staff
training in
computer use
and database
development

Staff Availability
and Capabilities

INFORMATION SYSTEM RESOURCES

Health information subsystem: issue framework

Epidemiological
Surveillance

HEALTH
INFORMATION
SUBSYSTEMS
TO BE ASSESSED

3

ANNEX

Suboptional use
of equipment

Lack of
established
procedures for
equipment
maintenance

Material and
Facilities

Lack of computer
facilities for
emergency
management
monitoring and
performance
analysis

Inadequacy of
computer facilities
for surveillance data
management and
communication

Computer Use

Poor data
communication
among health care
system levels

Lack of a clear
structure and
function of the
management
information system

HIS management and
its support to
epidemiological
surveillance unclear

Information Systems
Management
Coordination and
Networking

ANNEX

Examples of assessment questions and
recording formats

4

Does the staff know or can they calculate the following population target
groups?
Yes

No

Size

Proportion of total

Purpose

Women of reproductive age (15–45)
No. of pregnant women expected
No. of births expected
Infants 0 to 11 months
Infants 0 to 23 months
Infants 9 to 23 months
Children 0 to 3 years

What is the trend in the following three diseases over the past 6 months?
Increasing

Decreasing

Variable (no trend)

True or False

Don’t know

Diarrhoea
Measles
Meningitis

Verify the trend in cases by extracting data from the registers
Jan.

Feb.

Mar.

Apr.

May

June

Diarrhoea
Measles
Meningitis

259

Design and implementation of health information systems

Determine whether the cases reported in the last annual report agree with
the monthly registers
Disease

Number of cases

Percentage difference

Total from monthly registers

Total in the annual report

Malaria
Diarrhoeal diseases
Acute respiratory infection
Meningitis
Measles
Anaemla
Tuberculosis

Awareness/availability of data on hospital personnel situation
Tables/registers are available with data on
Sanctioned posts by staff type
Filled and vacant posts by staff type
List of in-service training received last year
List of impending retirements by year

260

Hospital Director

Chief Matron

Personnel Office

ANNEX

5

Examples of assessment data tables

Staff knowledge of target population groups
Health facilities

Target groups

Dispensary

Health
centre

Yes

Yes

No

No

Hospitals

District/
Regional
Office

Yes

Yes

Yes

No.

No

No

Total
No

%

No.

%

Total population served
Women of reprod. age
Number of expected births
Infants 0 to 11 months
Infants 0 to 23 months
Infants 9 to 23 months
Children 0 to 3 years
Children 0 to 5 years

Availability and consistency of data on disease cases and trends
Variables

Health facilities
Dispensary

Health
centre

Yes

Yes

No

No

Hospitals

District/
Regional
Office

Yes

Yes

Yes

No.

No

No

Total
No

%

No.

%

Knowledge of disease
trends
Data available in monthly
registers and reports
Data from the registers
and reports agree

261

Design and implementation of health information systems

Data on malnutrition and security stock of supplies
Variables

Data are available on the
number of children
found to be
malnourished during
growth monitoring
Staff are able to calculate
the percentage of
children 0 to 3 who are
malnourished
Staff are able to calculate
the amount of security
stock required for:
FeS and folic acid
Measles vaccine

262

Health facilities
Dispensary

Health
centre

Yes

Yes

No

Hospital

No

Yes

No

District/
Regional
Office

Yes

Yes

No.

No

Total
No

%

No.

%

ANNEX

6

Mother health card, Chandigarh, India

Source: Home-based maternal records: guidelines for development, adaptation and evaluation. Geneva, WHO (1994)

263

ANNEX

7

Child health register

Source: Ministry of Public Health, Pakistan (1993)

264

ANNEX

8

Example of tally sheet

Source: Primary Health Care Management Advancement Programme,
Module 3, Aga Khan Foundation, Geneva (1993)

265

ANNEX

9

Hospital daily attendance sheet

Source: Ministry of Health, Republic of Chad (1986)

266

ANNEX

10

Population chart of catchment area

Source: Ministry of Public Health, Pakistan (1993)

267

ANNEX

11

Example of supervisory checklist

Source: Primary Health Care Management Advancement Programme,
Module 6, Aga Khan Foundation, Geneva (1993)

268

ANNEX

12

HMIS/FLCF monthly report: section on mother
care activities

Source: Ministry of Public Health, Pakistan

269

ANNEX

13

Data collection instrument pre-test review form

Source: Pakistan Child Survival Project, 1993

270

