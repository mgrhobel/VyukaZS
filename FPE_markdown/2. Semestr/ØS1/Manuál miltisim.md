---
title: "Manuál miltisim.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/ØS1/Manuál miltisim.pdf"
date: 2008-08-24
type: PDF (text-based)
---

Electronics
Workbench

TM

Multisim 9 Simulation and Capture
TM

Educators Manual
TitleShort-Hidden (cross reference text)

February 2006
371588B-01

Support
Worldwide Technical Support and Product Information
ni.com
National Instruments Corporate Headquarters
11500 North Mopac Expressway

Austin, Texas 78759-3504

USA Tel: 512 683 0100

Worldwide Offices
Australia 1800 300 800, Austria 43 0 662 45 79 90 0, Belgium 32 0 2 757 00 20, Brazil 55 11 3262 3599,
Canada 800 433 3488, China 86 21 6555 7838, Czech Republic 420 224 235 774, Denmark 45 45 76 26 00,
Finland 385 0 9 725 725 11, France 33 0 1 48 14 24 24, Germany 49 0 89 741 31 30, India 91 80 41190000,
Israel 972 0 3 6393737, Italy 39 02 413091, Japan 81 3 5472 2970, Korea 82 02 3451 3400,
Lebanon 961 0 1 33 28 28, Malaysia 1800 887710, Mexico 01 800 010 0793, Netherlands 31 0 348 433 466,
New Zealand 0800 553 322, Norway 47 0 66 90 76 60, Poland 48 22 3390150, Portugal 351 210 311 210,
Russia 7 095 783 68 51, Singapore 1800 226 5886, Slovenia 386 3 425 4200, South Africa 27 0 11 805 8197,
Spain 34 91 640 0085, Sweden 46 0 8 587 895 00, Switzerland 41 56 200 51 51, Taiwan 886 02 2377 2222,
Thailand 662 278 6777, United Kingdom 44 0 1635 523545
For further support information, refer to the Technical Support Resources and Professional Services page. To comment
on National Instruments documentation, refer to the National Instruments Web site at ni.com/info and enter the
info code feedback.
© 2005–2006 National Instruments Corporation. All rights reserved.

Important Information
Warranty
The media on which you receive National Instruments software are warranted not to fail to execute programming instructions, due to defects
in materials and workmanship, for a period of 90 days from date of shipment, as evidenced by receipts or other documentation. National
Instruments will, at its option, repair or replace software media that do not execute programming instructions if National Instruments receives
notice of such defects during the warranty period. National Instruments does not warrant that the operation of the software shall be
uninterrupted or error free.
A Return Material Authorization (RMA) number must be obtained from the factory and clearly marked on the outside of the package before
any equipment will be accepted for warranty work. National Instruments will pay the shipping costs of returning to the owner parts which are
covered by warranty.
National Instruments believes that the information in this document is accurate. The document has been carefully reviewed for technical
accuracy. In the event that technical or typographical errors exist, National Instruments reserves the right to make changes to subsequent
editions of this document without prior notice to holders of this edition. The reader should consult National Instruments if errors are suspected.
In no event shall National Instruments be liable for any damages arising out of or related to this document or the information contained in it.
EXCEPT AS SPECIFIED HEREIN, NATIONAL INSTRUMENTS MAKES NO WARRANTIES , EXPRESS OR IMPLIED, AND SPECIFICALLY DISCLAIMS ANY WARRANTY OF
MERCHANTABILITY OR FITNESS FOR A PARTICULAR PURPOSE . C USTOMER’S RIGHT TO RECOVER DAMAGES CAUSED BY FAULT OR NEGLIGENCE ON THE PART OF
NATIONAL INSTRUMENTS SHALL BE LIMITED TO THE AMOUNT THERETOFORE PAID BY THE CUSTOMER. NATIONAL INSTRUMENTS WILL NOT BE LIABLE FOR
DAMAGES RESULTING FROM LOSS OF DATA, PROFITS, USE OF PRODUCTS, OR INCIDENTAL OR CONSEQUENTIAL DAMAGES, EVEN IF ADVISED OF THE POSSIBILITY
THEREOF. This limitation of the liability of National Instruments will apply regardless of the form of action, whether in contract or tort, including
negligence. Any action against National Instruments must be brought within one year after the cause of action accrues. National Instruments
shall not be liable for any delay in performance due to causes beyond its reasonable control. The warranty provided herein does not cover
damages, defects, malfunctions, or service failures caused by owner’s failure to follow the National Instruments installation, operation, or
maintenance instructions; owner’s modification of the product; owner’s abuse, misuse, or negligent acts; and power failure or surges, fire,
flood, accident, actions of third parties, or other events outside reasonable control.

Copyright
Under the copyright laws, this publication may not be reproduced or transmitted in any form, electronic or mechanical, including photocopying,
recording, storing in an information retrieval system, or translating, in whole or in part, without the prior written consent of National
Instruments Corporation.
National Instruments respects the intellectual property of others, and we ask our users to do the same. NI software is protected by copyright and other
intellectual property laws. Where NI software may be used to reproduce software or other materials belonging to others, you may use NI software only
to reproduce materials that you may reproduce in accordance with the terms of any applicable license or other legal restriction.

Trademarks
National Instruments, NI, ni.com, and LabVIEW are trademarks of National Instruments Corporation. Refer to the Terms of Use section
on ni.com/legal for more information about National Instruments trademarks.
Other product and company names mentioned herein are trademarks or trade names of their respective companies.
Members of the National Instruments Alliance Partner Program are business entities independent from National Instruments and have no
agency, partnership, or joint-venture relationship with National Instruments.

Patents
For patents covering National Instruments products, refer to the appropriate location: Help»Patents in your software, the patents.txt file
on your CD, or ni.com/patents.
Some portions of this product are protected under United States Patent No. 6,560,572.

WARNING REGARDING USE OF NATIONAL INSTRUMENTS PRODUCTS
(1) NATIONAL INSTRUMENTS PRODUCTS ARE NOT DESIGNED WITH COMPONENTS AND TESTING FOR A LEVEL OF
RELIABILITY SUITABLE FOR USE IN OR IN CONNECTION WITH SURGICAL IMPLANTS OR AS CRITICAL COMPONENTS IN
ANY LIFE SUPPORT SYSTEMS WHOSE FAILURE TO PERFORM CAN REASONABLY BE EXPECTED TO CAUSE SIGNIFICANT
INJURY TO A HUMAN.
(2) IN ANY APPLICATION, INCLUDING THE ABOVE, RELIABILITY OF OPERATION OF THE SOFTWARE PRODUCTS CAN BE
IMPAIRED BY ADVERSE FACTORS, INCLUDING BUT NOT LIMITED TO FLUCTUATIONS IN ELECTRICAL POWER SUPPLY,
COMPUTER HARDWARE MALFUNCTIONS, COMPUTER OPERATING SYSTEM SOFTWARE FITNESS, FITNESS OF COMPILERS
AND DEVELOPMENT SOFTWARE USED TO DEVELOP AN APPLICATION, INSTALLATION ERRORS, SOFTWARE AND
HARDWARE COMPATIBILITY PROBLEMS, MALFUNCTIONS OR FAILURES OF ELECTRONIC MONITORING OR CONTROL
DEVICES, TRANSIENT FAILURES OF ELECTRONIC SYSTEMS (HARDWARE AND/OR SOFTWARE), UNANTICIPATED USES OR
MISUSES, OR ERRORS ON THE PART OF THE USER OR APPLICATIONS DESIGNER (ADVERSE FACTORS SUCH AS THESE ARE
HEREAFTER COLLECTIVELY TERMED “SYSTEM FAILURES”). ANY APPLICATION WHERE A SYSTEM FAILURE WOULD
CREATE A RISK OF HARM TO PROPERTY OR PERSONS (INCLUDING THE RISK OF BODILY INJURY AND DEATH) SHOULD
NOT BE RELIANT SOLELY UPON ONE FORM OF ELECTRONIC SYSTEM DUE TO THE RISK OF SYSTEM FAILURE. TO AVOID
DAMAGE, INJURY, OR DEATH, THE USER OR APPLICATION DESIGNER MUST TAKE REASONABLY PRUDENT STEPS TO
PROTECT AGAINST SYSTEM FAILURES, INCLUDING BUT NOT LIMITED TO BACK-UP OR SHUT DOWN MECHANISMS.
BECAUSE EACH END-USER SYSTEM IS CUSTOMIZED AND DIFFERS FROM NATIONAL INSTRUMENTS' TESTING
PLATFORMS AND BECAUSE A USER OR APPLICATION DESIGNER MAY USE NATIONAL INSTRUMENTS PRODUCTS IN
COMBINATION WITH OTHER PRODUCTS IN A MANNER NOT EVALUATED OR CONTEMPLATED BY NATIONAL
INSTRUMENTS, THE USER OR APPLICATION DESIGNER IS ULTIMATELY RESPONSIBLE FOR VERIFYING AND VALIDATING
THE SUITABILITY OF NATIONAL INSTRUMENTS PRODUCTS WHENEVER NATIONAL INSTRUMENTS PRODUCTS ARE

Preface
Congratulations on choosing Multisim 9 from Electronics Workbench. We are confident that
it will deliver years of increased productivity and superior designs.
Electronics Workbench is the world’s leading supplier of circuit design tools. Our products
are used by more customers than those of any other EDA vendor, so we are sure you will be
pleased with the value delivered by Multisim 9, and by any other Electronics Workbench
products you may select.

Installation
For complete installation instructions, refer to the installation chapter of the Multisim 9 User
Guide.

Documentation Conventions
When Multisim 9 guides refer to a toolbar button, an image of the button appears in the left
column.
Multisim 9 guides use:
•
•
•

the convention Menu/Item to indicate menu commands. For example, “File/Open” means
choose the Open command from the File menu.
an arrow () to indicate the start of procedural information.
the construction CTRL-KEY and ALT-KEY to indicate when you need to hold down the
“Ctrl” or “Alt” key on your keyboard and press another key.

The Multisim 9 Documentation Set
All Multisim 9 Education edition users receive PDF versions of the Multisim 9 User Guide,
the Multisim 9 for Educators guide, the Component Reference Guide and online help.

User Guide
The User Guide describes Multisim 9 and its many functions in detail. It is organized based
on the stages of circuit design, and explains all aspects of using Multisim 9, in detail. It also
contains a tutorial that will introduce you to Multisim’s many features.

Multisim 9 for Educators
The Multisim 9 for Educators guide describes functions that are specific to the Education
edition of Multisim 9.

Online Help
Multisim offers a full helpfile system to support your use of the product.
Choose Help/Multisim Help to display the helpfile that explains the Multisim program in
detail, or choose Help/Component Reference to display the helpfile that contains details on the
components families provided with Multisim. Both are standard Windows helpfiles, offering
a table of contents and index.
In addition, you can display context-sensitive help by pressing F1 from any command or
window, or by clicking the Help button on any dialog box that offers it.

Adobe PDF Files
The Multisim 9 User Guide, Multisim 9 for Educators and the Component Reference Guide
are provided on the documentation CD as Adobe PDF files.

License Agreement
Please read the license agreement found at www.electronicsworkbench.com carefully before
installing and using the software contained in this package. By installing and using the
software, you are agreeing to be bound by the terms of this license. If you do not agree to the
terms of this license, simply return the unused software within ten days to the place where you
obtained it and your money will be refunded.

Table of Contents
1. Educators’ Guide
1.1

Circuit Creator’s Name . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 1-1

1.2

Assigning Faults to Components . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 1-2
1.2.1
Setting a Placed Component’s Faults . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 1-2
1.2.2
Using the Auto Fault Option . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 1-3

1.3

Using Restrictions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 1-4
1.3.1
Setting Global Restrictions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 1-4
1.3.1.1 General Global Restrictions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 1-5
1.3.1.2 Simplified Version. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 1-6
1.3.1.3 Global Analyses Restrictions . . . . . . . . . . . . . . . . . . . . . . . . . . . . 1-8
1.3.2
Setting Circuit Restrictions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 1-9
1.3.3
Setting Passwords for Restrictions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 1-12

1.4

Link to Education Resources . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 1-13

2. Breadboarding
2.1

Breadboarding Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 2-2

2.2

Setting up the Breadboard . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 2-2
2.2.1
Breadboard Settings . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 2-2
2.2.2
3D Options . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 2-3

2.3

Placing Components on the Breadboard . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 2-4

2.4

Wiring Placed Components . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 2-7
2.4.1
Placing a Jumper . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 2-8
2.4.2
Changing Jumper Wire Color . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 2-9

2.5

Viewing Component Information . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 2-9

2.6

Manipulating the Breadboard View . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 2-11

2.7

Breadboard Netlist dialog box . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 2-12

2.8

DRC and Connectivity Check . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 2-13

Multisim 9 for Educators

i

3. Virtual ELVIS
3.1

Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .3-1

3.2

The Virtual ELVIS Schematic . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .3-2

3.3

Placing Components on the Prototyping Board . . . . . . . . . . . . . . . . . . . . . . . . . . . . .3-8

3.4

Wiring Placed Components . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .3-10

4. Ladder Diagrams
4.1

Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .4-1

4.2

Creating a Ladder Diagram . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .4-2

4.3

AND Rungs and OR Rungs . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .4-5

4.4

Sample Circuits . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .4-7
4.4.1
Holding Tank . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .4-7
4.4.2
Conveyor Belt . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .4-12
4.4.3
Traffic Light . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .4-17

Appendix A - Education Edition Parts
A.1

ii

Rated Virtual Components. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-1
A.1.1
Rated 555 Timer . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-1
A.1.2
Rated BJTs . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-2
A.1.3
Rated Capacitors . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-3
A.1.4
Rated Diodes . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-4
A.1.5
Rated Fuses . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-4
A.1.6
Rated Inductors . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-5
A.1.7
Rated LEDs . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-5
A.1.8
Rated DC Motor . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-6
A.1.9
Rated Relay . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-7
A.1.10 Rated Opamp . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-8
A.1.11 Rated Photodiode . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-9
A.1.12 Rated Phototransistor . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-9
A.1.13 Rated Potentiometer . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-10
A.1.14 Rated Pullup . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-11
A.1.15 Rated Resistor . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-11
A.1.16 Rated Transformers . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-12

Electronics Workbench

A.1.17 Rated Variable Capacitor . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-13
A.1.18 Rated Variable Inductor . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-14
A.1.19 Rated Virtual Components Toolbar. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-15
A.2

3D Virtual Parts . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-15
A.2.1
3D 555 Timer . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-15
A.2.2
3D BJT . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-16
A.2.3
3D Capacitors . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-16
A.2.4
3D 74LS160N Counter . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-17
A.2.5
3D Diode . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-17
A.2.6
3D Inductor . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-18
A.2.7
3D LED . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-18
A.2.8
3D MOSFET . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-19
A.2.9
3D DC Motor . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-19
A.2.10 3D Opamp . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-19
A.2.11 3D Potentiometer . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-20
A.2.12 3D AND Gate . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-20
A.2.13 3D Resistor . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-21
A.2.14 3D Shift Register. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-21
A.2.15 3D Switch . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-21
A.2.16 3D Components toolbar . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-22

A.3

Ladder Diagram Parts . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-22
A.3.1
Ladder Rungs . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-22
A.3.1.1 L1 and L2 . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-22
A.3.2
Ladder I/O Modules . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-23
A.3.2.1 Input Module. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-23
A.3.2.2 Output Module . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-23
A.3.3
Ladder Relay Coils . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-24
A.3.3.1 Relay Coil . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-24
A.3.3.2 Negated Relay Coil . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-24
A.3.3.3 Set Coil . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-24
A.3.3.4 Reset Coil . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-25
A.3.3.5 Pulsed Relay Coil . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-25
A.3.4
Ladder Contacts . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-25
A.3.4.1 Input Contact NC . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-25
A.3.4.2 Input Contact NO . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-26
A.3.4.3 Relay Contact NC . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-26
A.3.4.4 Relay Contact NO . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-27
A.3.5
Ladder Counters . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-27
A.3.5.1 Count Off . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-27
A.3.5.2 Count Off Hold . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-28
A.3.5.3 Count Off Reset . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-28

Multisim 9 for Educators

iii

A.3.6

A.3.7

iv

A.3.5.4 Count Off Up Down . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-29
A.3.5.5 Count On . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-29
A.3.5.6 Count On Hold . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-30
A.3.5.7 Count On Reset . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-30
A.3.5.8 Count On Up Down . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-31
Ladder Timers . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-31
A.3.6.1 Timer TOFF . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-31
A.3.6.2 Timer TON . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-32
A.3.6.3 Timer TON Retention . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-32
A.3.6.4 Timer TON Retention Reset . . . . . . . . . . . . . . . . . . . . . . . . . . . A-33
A.3.6.5 Timer TON Retention Hold Reset . . . . . . . . . . . . . . . . . . . . . . A-33
Ladder Output Coils . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-34
A.3.7.1 Output Coil . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-34
A.3.7.2 Output Coil Negated . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-34

A.4

Miscellaneous Peripherals . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-35
A.4.1
Holding Tank . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-35
A.4.2
Conveyor Belt . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-36
A.4.3
Traffic Light . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-37
A.4.4
Single Traffic Light . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-37

A.5

Virtual ELVIS Components . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-38
A.5.1
NI ELVIS Function Generator . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-38
A.5.2
NI ELVIS Power Supply . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . A-39

Electronics Workbench

Chapter
1
Educators’ Guide
In addition to the many features that have made Multisim a favorite with professional users,
there are also a number of education-specific features that are outlined in this guide.
This chapter describes the tools that Multisim offers to let you exercise greater control over
the program’s interface and functionality when sharing circuits with students, as well as to set
certain aspects of a circuit’s behavior for instructional purposes. These features include
assigning faults to components in a circuit and setting global and circuit restrictions.
Some of the features described in this chapter may not be available in your edition of
Multisim 9. Refer to the release notes for a description of the features available in your
edition.
The following are described in this chapter.

1.1

Subject

Page No.

Circuit Creator’s Name

1-1

Assigning Faults to Components

1-2

Using Restrictions

1-4

Link to Education Resources

1-13

Circuit Creator’s Name
Multisim provides a feature by which the name of the creator of each circuit is stored with that
circuit. Educators can take advantage of this feature to identify the student who, for example,
created the circuit being submitted as the answer to an assignment (provided that the student
uses his/her own copy of the program to create the circuit). The name appears on the
Circuit Restrictions dialog box, which you can view as long as no passwords have been set —
see “1.3.2 Setting Circuit Restrictions” on page 1-9 for more information.

Multisim 9 for Educators

1-1

Educators’ Guide

1.2

Assigning Faults to Components
You may want to assign faults to components for instructional purposes, such as
troubleshooting exercises. You can manually assign faults to individual components in a
circuit or let Multisim randomly assign faults to various components across a circuit.

1.2.1

Setting a Placed Component’s Faults
You can assign a fault to any terminal of the placed component using the Fault tab of that
component’s properties dialog box.
 To assign a fault to a placed component:
1. Double-click on the component. The component’s properties dialog box appears.
2. Click the Fault tab:
Shows the terminals
of the placed
component — varies
depending on
component type.

Choose which
type of fault to
assign to the
selected terminals

Note Refer to the Multisim 9 User Guide for information on the other tabs in the above
dialog box.
3. Select the terminals to which the fault should apply.

1-2

Electronics Workbench

Assigning Faults to Components

4. Enable the type of fault you want assigned to a terminal. The options are:
Option

Description

None

No fault.

Open

Assigns a very high resistance to the terminal, as if the wire leading to the
terminals was broken.

Short

Assigns a very low resistance to the terminal, so the component has no
measurable affect on the circuit.

Leakage

Assigns the resistance value specified in the fields below the option, in
parallel with the selected terminals. This causes the current to leak past the
terminals instead of going through them.

5. To cancel your changes, click Cancel. To save your changes, click OK.

1.2.2

Using the Auto Fault Option
Note This function is hidden when the simplified version option is selected. For details, see
“1.3.1.2 Simplified Version” on page 1-6.
When you use the Auto Fault option, you specify the number of any type of fault or,
optionally, the number of faults per different type of fault, that you want Multisim to assign to
placed components in the circuit.
 To use the auto fault option:
1. Choose Simulate/Auto Fault Option. The Auto Fault dialog box appears:

Note The Auto Fault option is disabled until a component is placed on the workspace.

Multisim 9 for Educators

1-3

Educators’ Guide

2. Use the up/down arrow keys or enter numerical values directly in the Short, Open, and
Leak fields, or enter a numerical value in the Any field to let Multisim randomly select the
type of faults to assign (in the quantity entered).
3. If you specify a number of leaks, enter a number and unit of measurement in the
Specify Leak Resistance fields.
4. Click OK to apply the faults, or Cancel to cancel, and return to the circuit window.

1.3

Using Restrictions
Restrictions are useful in a number of ways:
•

when you are designing circuits for demonstration purposes and want to limit the
functionality available to students
• when you are sharing circuits with students and want:
• to prevent them from being able to edit the circuit in any way
• to limit the types of modifications they can make to a circuit
• to limit the types of analyses they can perform on it
• to limit the information they can see about certain parts of the circuit (for example, the
value of a resistor you want them to calculate).
You can set global-level restrictions, which become default Multisim settings, or circuit-level
restrictions, which affect only specific circuits.
To ensure that only you can set or modify restrictions, you use passwords which can protect
both global and circuit restrictions. It is important that you set passwords immediately when
using restrictions that you want to keep secure against any modification by students. The
password for global restrictions is encrypted and stored in the Multisim program file. The
password for circuit restrictions (for restricting only a particular circuit) is encrypted and
stored in the circuit file.

1.3.1

Setting Global Restrictions
Use global restrictions to set the basic level of functionality of Multisim available to students
in all circuits with which they will work. You can select a default path where circuits are to be
saved, hide databases and the In Use List, and determine whether students may edit
components or place instruments.
You can also hide complicated instruments and analysis options from the menus by using the
simplified version. See “1.3.1.2 Simplified Version” on page 1-6.
Note Global restrictions are overridden by circuit restrictions if the circuit restrictions are
saved with the circuit. See “1.3.2 Setting Circuit Restrictions” on page 1-9 for
information.

1-4

Electronics Workbench

Using Restrictions

1.3.1.1 General Global Restrictions
 To set general global restrictions:
1. Choose Options/Global restrictions. The Password dialog box appears.

Note The above dialog also appears if you select Options/Circuit restrictions, if you have
previously set a password by clicking Password from the Circuit restrictions dialog
box. For details on the Circuit restrictions dialog box, see “1.3.2 Setting Circuit
Restrictions” on page 1-9.
2. Enter the default password “Rodney” (this is case sensitive) and click OK.
The Global Restrictions dialog box appears.
Note You can, and should, change the default password. (See “1.3.3 Setting Passwords for
Restrictions” on page 1-12 for more information).
3. If it is not displayed, click the General tab:
Enable these
checkboxes to
disallow
component
editing, to hide
parts bins,
databases, and
the In Use List.

Click here to select a
default path/location to
store circuits.

Optionally, click to erase
circuit path.

See “1.3.1.2
Simplified Version”
on page 1-6.

Multisim 9 for Educators

1-5

Educators’ Guide

4. Select from the following options:
Circuit Path

Sets the default path and location where students find
and save files.

Disable database editing

Ensures that students cannot edit components in the
database.

Disable Instruments toolbar

Makes instruments unavailable to be placed in the
circuit.

Disable In-Use List toolbar

Hides the In Use List.

Disable Master DB component
access

Hides the Multisim Master database and parts groups
and families from the interface.

Disable User DB component
access

Hides the “user” database and parts groups and families
from the interface.

Disable Corporate DB
component access

Hides the corporate database and parts groups and
families from the interface.

5. Click OK.
Your options are immediately set for all circuits, unless you have set circuit restrictions. (See
“1.3.2 Setting Circuit Restrictions” on page 1-9.)

1.3.1.2 Simplified Version
The simplified version restricts students to only certain instruments and analyses. The
simplified version can also be locked, preventing students from turning it off with
Options/Simplified Version and having access to all analyses and instruments.

1-6

Electronics Workbench

Using Restrictions
 To set up the simplified version:
1. Display the General tab of the Global Restrictions dialog box:

Disables the
Options/Simplified
Version menu
option.

Enable to turn on
simplified version.

Enable to set the full
version without
restrictions.

2. Set your options by enabling one of the following options:
Simplified version

Changes the interface display by hiding the more
complex functions and restricting the available
instruments and analyses. If the simplified version is
restricted, it will be greyed out in the Options menu.

Full version

Displays the full default interface without restrictions.

3. Click OK.
Your options are immediately set for all circuits, unless you have set circuit restrictions. (See
“1.3.2 Setting Circuit Restrictions” on page 1-9.)

Multisim 9 for Educators

1-7

Educators’ Guide

1.3.1.3 Global Analyses Restrictions
 To set global analyses restrictions:
1. From the Global Restrictions dialog box, click the Analysis tab.

2. Enable the desired analyses by selecting the appropriate checkboxes and click OK. Only
the analyses you check will be enabled in the Simulate/Analyses menu or when the student
clicks the Grapher/Analyses List button in the Main toolbar.
Note See Chapter 11, “Analyses”, in the Multisim 9 User Guide for more information on
analyses.
These options are immediately set for all circuits, unless you have set circuit restrictions. (See
“1.3.2 Setting Circuit Restrictions” on page 1-9.)

1-8

Electronics Workbench

Using Restrictions

1.3.2

Setting Circuit Restrictions
Use circuit restrictions to set restrictions on individual circuits. Circuit restrictions override
global restrictions. They are saved with your circuit and invoked each time the circuit is
loaded. In addition to hiding databases and setting available analyses, you can set a schematic
to be read-only (not editable by students), you can hide components’ values, faults and uses in
analyses, and you can lock subcircuits to make them unavailable for opening by students.
Note Remember that circuit restrictions only apply to the current circuit; when you create a
new circuit, only the global restrictions will apply (see “1.3.1 Setting Global
Restrictions” on page 1-4 for details). If you want circuit restrictions to apply to a new
circuit, you will need to reset those restrictions each time you create a new circuit.
 To set general circuit restrictions:
1. Choose Options/Circuit Restrictions. If you have created a password, you will be prompted
for it. (See “1.3.3 Setting Passwords for Restrictions” on page 1-12 for more information.)
Enter your password in the Password dialog box, and click OK. The Circuit Restrictions
dialog box appears.
2. If it is not displayed, click the General tab:
The creator of the circuit. (This
information is taken from the
operating system.)

Enable to set the schematic as
“read-only”.

Enable to set the circuit
description box as “read-only”.

Enable checkboxes to hide
component properties and lock
subcircuits.
Enable the appropriate
checkboxes to disable desired
toolbars, databases, and the
In-Use List.

Multisim 9 for Educators

1-9

Educators’ Guide

3. Set the desired options by enabling the appropriate checkboxes. Select from the following
options:
Schematic read-only

Prevents students from saving the circuit, and hides
Parts Bins. Students will only be able to draw wires
between instruments and an open pin on an existing
connector. Also, they can only remove wires that are
between an instrument and a connector.

Circuit description readonly

Prevents students from changing the contents of the
Circuit Description box.

Hide component values

Marks the Values tab of components’ “properties” dialog
boxes with an “X” and hides values. You may wish to
provide false values using labels.

Hide component faults

Marks the Faults tab of components’ “properties” dialog
boxes with an “X”, and hides faults.

Lock subcircuits

Prevents students from opening subcircuits and seeing
their contents. Students must measure the input and
output of a hidden subcircuit to determine its contents.

Disable Instruments toolbar

Makes instruments unavailable to be placed on the
circuit.

Disable In-Use List toolbar

Disables the In-Use List for the current circuit.

Disable Multisim Master
DB component access

Hides the Multisim Master database and parts groups
and families from the current circuit.

Disable User DB
component access

Hides the “user” database and parts groups and families
from the current circuit.

Disable Corporate DB
component access

Hides the corporate database and parts groups and
families from the interface.

4. Click OK. The options you select are immediately invoked in the circuit.
5. To have the restrictions apply each time the circuit is opened, choose File/Save to save the
restrictions in the circuit file.

1-10

Electronics Workbench

Using Restrictions
 To set circuit analyses restrictions:
1. From the Circuit Restrictions dialog box, click the Analysis tab:

2. Enable the desired analyses by selecting the appropriate checkboxes and click OK. Only
the analyses you check will be enabled in the Simulate/Analyses menu or when the student
clicks the Grapher/Analyses List button in the Main toolbar.
Note See Chapter 11, “Analyses”, in the Multisim 9 User Guide for more information on
analyses.
3. To have these analyses apply each time the circuit is opened, choose File/Save to save the
restrictions.

Multisim 9 for Educators

1-11

Educators’ Guide
 To set circuit breadboard restrictions:
1. From the Circuit Restrictions dialog box, click the Breadboard tab.

Disable if you do not wish to see
where the targets for jumper wires
are when placing them on the
breadboard.

Disable if you do not wish
components and wires on the
schematic to change color as they
are placed and wired on the
breadboard.

2. Enable the desired analyses by selecting the appropriate checkboxes and click OK.
Note For details on breadboarding, refer to Chapter 2, “Breadboarding”.

1.3.3

Setting Passwords for Restrictions
When using restrictions, you should create a password immediately to ensure that your
settings are secure.
 To create/change a password:
1. For global restrictions, choose Options/Global restrictions. For circuit restrictions, choose
Options/Circuit restrictions. Enter a password if prompted to do so.
Note The default password for global restrictions is “Rodney” (this is case sensitive).
Circuit restrictions do not have a default password.

1-12

Electronics Workbench

Link to Education Resources

2. From the restrictions dialog box that appears, click Password. The Change Password dialog
box appears:

3. If you are choosing a password for the first time, leave the Old password field blank.
If you are changing a password, enter the old password in the Old password field.
4. Enter your (new) password in the New password field.
5. Confirm your password by entering it again in the Confirm password field.
6. Click OK to return to the dialog box, or Cancel to begin again.
Note If you want to change global or circuit restrictions, you will need to enter the
respective password. Be sure to keep your passwords for both the Global restrictions
and Circuit restrictions dialogs written down and in a safe place, as you will not be able
to retrieve them from the program or circuit files, where they are stored in encrypted
form.
Note A circuit password is not automatically transferred to a new circuit when you go to set
circuit restrictions for it, so you will need to recreate the password every time you
create circuit restrictions that you want to keep secure.

1.4

Link to Education Resources
Note This function is hidden when the simplified version option is selected. For details, see
“1.3.1.2 Simplified Version” on page 1-6.
 To go to the Electronics Workbench Education website:
1. Click on the Educational Website button or select Tools/Education Webpage.

Multisim 9 for Educators

1-13

Chapter
2
Breadboarding
This chapter describes Multisim 9’s breadboarding feature.
Some of the features described in this chapter may not be available in your edition of
Multisim 9. Refer to the release notes for a description of the features available in your
edition.
The following are described in this chapter.
Subject

Page No.

Breadboarding Overview

2-2

Setting up the Breadboard
Breadboard Settings
3D Options

2-2
2-2
2-3

Placing Components on the Breadboard

2-4

Wiring Placed Components
Placing a Jumper
Changing Jumper Wire Color

2-7
2-8
2-9

Viewing Component Information

2-9

Manipulating the Breadboard View

2-11

Breadboard Netlist dialog box

2-12

DRC and Connectivity Check

2-13

Multisim 9 for Educators

2-1

Breadboarding

2.1

Breadboarding Overview
The Breadboarding feature provides a technical aid for educators who wish to illustrate
breadboarding as a means of prototyping circuit designs. It also gives students exposure to the
breadboarding process, and shows in 3D what the resulting breadboard will look like when
completed.

2.2

Setting up the Breadboard

2.2.1

Breadboard Settings
The default breadboard is shown in the screen capture below. If you wish to change the
default settings, use the following procedure.
 To change the breadboard’s settings:
1. Select Tools/Show Breadboard from the main Multisim menu. The Breadboard View
displays. The default breadboard appears as shown below.
Top strip

One slat with two rows

Right strip

Bottom strip

Left strip

The default breadboard contains: one slat with two rows; one left strip; one right strip;
one bottom strip; one top strip.

2-2

Electronics Workbench

Setting up the Breadboard

2. Select Options/Breadboard Settings to display the following dialog box.

3. Enter the desired parameters for the breadboard and click OK. The view of the breadboard
changes to reflect your changes.

2.2.2

3D Options
The 3D viewing options for the Breadboard View are set in the 3D Options tab of the
Preferences dialog box.
 To change the 3D options:
1. Select Options/Preferences and click on the 3D Options tab.
2. Optionally, click on Background Color to display a standard Color dialog box where you
can adjust the background color as desired.
3. In the Info Box area:
• Info Box — disable this checkbox if you do not wish to see the box at the top of the
breadboard view that shows parts information.
• Left — places parts information box at top-left.
• Center — places parts information box at top-center.
• Right — places parts information box at top-right.
4. Disable the Show Target Holes checkbox if you do not wish to see where the targets for
jumper wires are when placing them. (For details, see “2.4.1 Placing a Jumper” on page 28).
5. Disable the Show Completion Feedback checkbox if you do not wish components and wires
on the schematic to change color as they are placed and wired on the breadboard.
6. In the 3D Performance box:
• Move the slider as desired to improve graphic performance. More Details will result in
a slower screen refresh rate.
• Enable the User Defined checkbox and disable the 3D features that you do not wish to
see.
Tip Disabling Show Breadboard Numbers will result in a much quicker refresh rate.

Multisim 9 for Educators

2-3

Breadboarding

2.3

Placing Components on the Breadboard
 To place components on a breadboard:
1. Create a schematic diagram of the desired circuit in the usual manner. (For details, on
schematic capture, refer to the Multisim 9 User Guide).
2. Select Tools/Show Breadboard from the main Multisim menu. The Breadboard View
displays similar to the following example.
Hover the cursor over a
component to see its
description in this box.

Place Component Bar - components waiting to be
placed on the breadboard appear in this area

2-4

View other components by
clicking on these arrows.

Electronics Workbench

Placing Components on the Breadboard

3. Click on a component in the Place Component Bar and drag it to the desired location on the
breadboard. As the component passes over the breadboard, sockets change color as shown
below.

Red sockets indicate
where the component’s
pins will be placed when
the mouse button is
released.

All of these sockets are
connected. Green indicates
sockets that are internally
connected to the red socket
in the same row on the
breadboard.

Tip Select CTRL-R to rotate a selected component 90 degrees clockwise or CTRL-SHIFT-R to
rotate it 90 degrees counter-clockwise.
4. Release the mouse button to place the component. Notice that the colored (red and green)
sockets on the breadboard no longer appear.

5. Return to the schematic view and note that the color of the placed component has changed
as shown in the example below.
Placed component has
changed color.

Multisim 9 for Educators

2-5

Breadboarding

6. Continue placing the circuit’s components on the breadboard. When all the components
have been placed, the Place Component Bar collapses as shown below.

Place Component Bar collapses when all
components are placed on the breadboard.

Tip Where pins of components are connected on the schematic, you can place them in
connected sockets on the breadboard as shown below. This technique can reduce the
number of jumper wires required. For details on jumpers, see “2.4.1 Placing a Jumper”
on page 2-8.

Connected pins

2-6

Electronics Workbench

Wiring Placed Components

Appearance of 3D Components
The appearance of the 3D component is dependant on the footprint that is selected from the
Select a Component browser during schematic capture.

Selected footprint
determines 3D
appearance in
breadboard view.

Some virtual parts have a default 3D view that appears as a blue 3D rectangle or cube. “Real”
parts that have pin pitch (spacing) that does not fit the pin pitch on the breadboard will also
appear as 3D rectangles or cubes, with properly spaced pins. (See below).
Footprint with pin
pitch that matches
breadboard.

Footprint with pin
pitch that does not
match breadboard.

AC Power Supply
(virtual part) appears
as rectangle

Note Certain virtual components, including 3D parts also appear as 3D rectangles or cubes.
Note To view footprint information, hover the cursor over the desired component. For
details, see “2.5 Viewing Component Information” on page 2-9.

2.4

Wiring Placed Components
By placing component pins that are connected on the schematic into sockets that are internally
connected, much of the “wiring” can be done at the same time components are placed.
However, in most circuits, it will also be necessary to place jumpers to complete the wiring of
the placed components.

Multisim 9 for Educators

2-7

Breadboarding

2.4.1

Placing a Jumper
 To place a jumper wire:
1. Click on a socket connected to the pin where you wish to start the jumper and begin
moving the cursor. Legitimate “target” pins display as shown below.

Target pins display once one
end of the jumper is placed.
You must move the cursor to
see the targets.

2. Click to place the jumper in the desired socket.

3. Return to the schematic view and note that the color of the wire connecting the two pins
has changed to green to indicate a connection has been made.

Green wire shows connection on breadboard

Note If a net contains more than two connections, all must be connected before any of the
wires in the net change color.

2-8

Electronics Workbench

Viewing Component Information

4. Continue placing jumpers until all schematic connections have been made.
Tip Run a Design Rules and Connectivity Check to see if there are any errors in your
breadboard. Refer to “2.8 DRC and Connectivity Check” on page 2-13.

2.4.2

Changing Jumper Wire Color
 To change jumper wire color:
1. Select Edit/Breadboard Wire Color.
2. Select the desired color from the dialog box that appears.
Note The color of previously placed wires is not affected. The new color will be applied to
any subsequently placed wires.

2.5

Viewing Component Information
 To view information about a specific component:
1. Hover the cursor over the component. The information box is populated as shown below.

Multisim 9 for Educators

2-9

Breadboarding
 To see pin information:
1. Hover the cursor over the “metal” part of the desired pin. The information box now
includes the pin name and the schematic net to which the pin should be connected.

Two-terminal Components
Two-terminal non-directional components like resistors have pin names (1 and 2) that will
automatically swap if they are connected the “wrong way” according to the pin name that is
on the schematic.
 To view the pin names for all devices on the schematic:
1. Select Options/Sheet Properties and click the Circuit tab of the Sheet Properties dialog box.

Click until the checkmark
is a solid black color.

2-10

Electronics Workbench

Manipulating the Breadboard View

2. Enable the Pin names checkbox as shown above and click OK to close the dialog.
Pin 1 of R1 on schematic.

Pin 1 of R1 on breadboard.

In the above example, if Pin 1 is connected to a pin that should be receiving Pin 2, the pin
names will automatically swap. (Pin 1 will become Pin 2 and vice versa).

2.6

Manipulating the Breadboard View
You can manipulate the view of the breadboard in a number of ways.
 To make the breadboard appear larger:
1. Select View/Zoom in.
 To make the breadboard appear smaller:
1. Select View/Zoom out.
Tip Use your mouse’s center wheel to zoom in or out. (This must be set up in the General tab
of the Preferences dialog box. For details, refer to the Multisim 9 User Guide).
 To view the entire breadboard:
1. Select View/Zoom Full.
 To rotate the breadboard 180 degrees:
1. Select View/Rotate 180 Degrees
Or
Press SHIFT-R on your keyboard.

Multisim 9 for Educators

2-11

Breadboarding

Tip Rotate the breadboard in any direction by dragging the mouse from a blank area of the
Breadboard View. You can also rotate the breadboard by using the arrow keys on your
keyboard.
 To pan the breadboard:
1. Hold down the SHIFT key on your keyboard and use any of the arrow keys.
Or
Press CTRL-SHIFT and drag the mouse.
Or
Hold down your mouse-wheel and drag the mouse.

2.7

Breadboard Netlist dialog box
 To display a netlist for the placed components and jumpers:
1. Select Tools/Show Breadboard Netlist. The Breadboard Netlist dialog box appears.
Breadboard
Net
RefDes
Pin Name

2. Optionally, click Save to save the breadboard netlist as a .txt or .csv file.
Note These nets are breadboard connections, and are not necessarily numbered in
correspondence to the schematic nets.

2-12

Electronics Workbench

DRC and Connectivity Check

2.8

DRC and Connectivity Check
You can run a Design Rules and Connectivity Check to see if there are any errors in your
breadboard.
 To run a DRC and Connectivity Check:
1. Select Tools/DRC and Connectivity Check. The results appear in the Results tab of the
Spreadsheet View.

Design Rule Errors — indicate connections that are on the breadboard that are not on the

schematic.
Connectivity Errors — indicate component pins that are not connected to fully-completed

schematic nets.

Multisim 9 for Educators

2-13

Chapter
3
Virtual ELVIS
This chapter describes the Multisim 9 Virtual ELVIS feature.
Some of the features described in this chapter may not be available in your edition of
Multisim 9. Refer to the release notes for a description of the features available in your
edition.
The following are described in this chapter.

3.1

Subject

Page No.

Overview

3-1

The Virtual ELVIS Schematic

3-2

Placing Components on the Prototyping Board

3-8

Wiring Placed Components

3-10

Overview
Electronic Workbench’s Virtual ELVIS emulates much of the behavior of its real-world
counter-part, the NI Educational Laboratory Virtual Instrumentation Suite (NI ELVIS).
Planning, prototyping and testing of instructor’s projects can be carried out on the student’s
PC before moving on to the real NI ELVIS workstation in the lab.

Multisim 9 for Educators

3-1

Virtual ELVIS

3.2

The Virtual ELVIS Schematic
A Virtual ELVIS schematic contains a number of unique items that correspond to elements of
the real-world NI ELVIS workstation. The connection and control of these elements is
described in this section.
 To create a new Virtual ELVIS schematic:
1. Select File/New/ELVIS Schematic. When first opened, a Virtual ELVIS schematic appears
as shown below.

Note The Ground connector that appears at the bottom left of the diagram is the reference
point for measurements taken during simulation, and should therefore not be removed.
2. Place and wire components in the Virtual ELVIS schematic in the same manner as other
Multisim schematics. For details, refer to the Multisim 9 User Guide.
The prototyping board rows found to the left and right of the main workspace correspond to
rows in the real-world version of NI ELVIS and are labelled in the same manner.
Rows that are shown with green labels are not enabled for simulation in Multisim. However,
they can be used for schematic capture and viewing of the completed Virtual ELVIS
schematic in the 3D view. Unlike other Multisim components, these rows cannot be moved to
other places on the workspace.

3-2

Electronics Workbench

The Virtual ELVIS Schematic

Oscilloscope

Upper-left Rows

The connections to Virtual ELVIS’s oscilloscope are found in the upper-left prototyping rows.
 To connect the oscilloscope:
1. Place wires from the points in your schematic that you wish to measure with the
oscilloscope to any of the pins on the CH A+, CH A-, CH B+, CH B- or TRIGGER rows
beside “Oscilloscope”. These rows correspond to the terminals of the oscilloscope.
•
•
•
•
•

CH A+ — positive input of channel A.
CH A- — negative input of channel A.
CH B+ — positive input of channel B.
CH B- — negative input of channel B.
TRIGGER — trigger input signal.

 To access the oscilloscope’s controls:
1. Double-click on the the word “Oscilloscope” in the upper-left prototyping rows. The
instrument face for Multisim’s virtual oscilloscope displays.
2. Refer to the Multisim 9 User Guide for details on the use of this instrument.

Multisim 9 for Educators

3-3

Virtual ELVIS

IV Analyzer and Multimeter

Lower-left Rows

When a new Virtual ELVIS schematic is opened, the IV Analyzer is disabled, and the
Ammeter is enabled as indicated above.
 To disable the Ammeter and enable the IV Analyzer, double-click where indicated on the
Virtual ELVIS schematic.
 To disable the IV Analyzer and enable the Ammeter, double-click again.
Note When the IV Analyzer is enabled, there is a slight delay when simulation is started
while a DC sweep is performed. If the Ammeter is enabled, there is no delay.

3-4

Electronics Workbench

The Virtual ELVIS Schematic
 To connect the IV Analyzer:
1. Place wires from the component you wish to measure to the pins on the 3-WIRE,
CURRENT HI and CURRENT LO rows. These rows correspond to the inputs of the
IV Analyzer. See below for connections to specific component types.

 To connect the Ammeter:
1. Place wires from the points in the circuit you wish to measure to the pins on the
CURRENT HI and CURRENT LO rows.
CURRENT HI corresponds to the + terminal of the ammeter and CURRENT LO
corresponds to the - terminal.
 To access the controls for the enabled instrument:
1. Double-click just above the letters “DMM”. If you have enabled the IV Analyzer as
described earlier, that instrument’s face appears. If you have enabled the Ammeter, an
instrument containing the Ammeter function of a multimeter appears.
2. Refer to the Multisim 9 User Guide for details on the use of these instruments.
 To connect the Volt/Ohmmeter:
1. Place wires from the points in the circuit you wish to measure to the pins on the
VOLTAGE HI and VOLTAGE LO rows.
VOLTAGE HI corresponds to the + terminal of the meter and VOLTAGE LO corresponds
to the - terminal.

Multisim 9 for Educators

3-5

Virtual ELVIS
 To access the controls for the Voltmeter and Ohmmeter:
1. Double-click just below the letters “DMM”. An instrument containing the Voltmeter and
Ohmmeter functions of a multimeter appears.
2. Refer to the Multisim 9 User Guide for details on the use of this instrument.

Function Generator
 To connect the Function Generator:
1. Place wires from the pins on the FUNC OUT, SYNC OUT, AM IN and FM IN rows to the
desired points in your schematic.
• FUNC OUT — output signal.
• SYNC OUT — outputs a TTL-compatible clock signal of the same frequency as the
output waveform.
• AM IN — a signal input here controls the amplitude of the signal at FUNC OUT.
• FM IN — a signal input here controls the frequency of the signal at FUNC OUT and
SYNC OUT.
 To access the controls for the Function Generator:
1. Double-click on “Function Generator”. The properties dialog for the NI ELVIS Function
Generator appears.
2. Click on the Value tab and enter the desired output parameters.
3. Click OK to close the Function Generator’s properties dialog box.
Note For details on the user-settable parameters, see “A.5.1 NI ELVIS Function Generator”
on page A-38.

Power Supplies
The lower-left prototyping rows contain the following fixed DC Power Supplies:
• +15 V
• -15 V
• +5 V (also found in the lower-right prototyping rows).
Variable Power Supplies are also available:
•
•

SUPPLY + (+12 V max)
SUPPLY - (-12 V max).

 To connect to any of the power supplies, place wires from the pin on the corresponding row to
the desired point in the circuit.
 To access the controls for the variable power supplies:
1. Double-click on “Variable Power Supplies”. The properties dialog box for the NI ELVIS
power supply appears.

3-6

Electronics Workbench

The Virtual ELVIS Schematic

2. Click on the Value tab and enter the desired parameters.
3. Click OK to close the properties dialog box.
Note For details on the user-settable parameters, see “A.5.2 NI ELVIS Power Supply” on
page A-39.

LEDs
Connections to the seven LEDs on the right side of the ELVIS schematic are found in the
lower-right prototyping rows. During simulation, any of these LEDs that are correctly
connected will light.

 To connect to an LED:
1. Place a wire from one of the LED rows (LED 0 through LED 7) to the desired point in
your schematic.

Multisim 9 for Educators

3-7

Virtual ELVIS

There are also three LEDs in the lower-left section of any Virtual ELVIS schematic.

During simulation, these LEDs will light whether or not connections have been made to their
corresponding pins in the prototyping rows.

3.3

Placing Components on the Prototyping
Board
Once you have completed the Virtual ELVIS schematic, you are ready to place the
components on the 3D rendering of the prototyping board.

Note The controls that appear on the front of the 3D Virtual ELVIS are inactive. Interactive
simulation of Virtual ELVIS is accomplished via the schematic view. For details on
simulation, refer to the Multisim 9 User Guide or the Multisim helpfile.

3-8

Electronics Workbench

Placing Components on the Prototyping Board
 To place components on the 3D prototyping board:
2. Select Tools/Show Breadboard from the main Multisim menu.
Hover the cursor over a component
to see its description in this box.

Place Component Bar - components waiting to be
placed on the breadboard appear in this area

View other components by
clicking on these arrows.

Note 3D viewing options are set in the Preferences dialog box. For details, see “2.2.2 3D
Options” on page 2-3. See also, “2.6 Manipulating the Breadboard View” on page 2-11
for useful viewing information.
3. Click on a component in the Place Component Bar and drag it to the desired location on the
board. As the component passes over the board, sockets change color as indicated below:
Red sockets indicate
where the component’s
pins will be placed when
the mouse button is
released.

All of these sockets are
connected. Green indicates
sockets that are internally
connected to the red socket
in the same row on the
board.

Tip Select CTRL-R to rotate a selected component 90 degrees clockwise or CTRL-SHIFT-R to
rotate it 90 degrees counter-clockwise.
4. Release the mouse button to place the component. The colored (red and green) sockets on
the board no longer appear.

Multisim 9 for Educators

3-9

Virtual ELVIS

5. Return to the schematic view and note that the color of the placed component has changed
as shown in the example below.
Placed component has
changed color.

6. Continue placing the circuit’s components on the board. When all the components have
been placed, the Place Component Bar collapses.
Tip Where pins of components are connected on the schematic, you can place them in
connected sockets as shown below. This technique can reduce the number of jumper
wires required.

Connected pins

Note See also, “ Appearance of 3D Components” on page 2-7.

3.4

Wiring Placed Components
By placing component pins that are connected on the schematic into sockets that are internally
connected, much of the “wiring” can be done at the same time components are placed.
However, in most circuits, it will also be necessary to place jumpers to complete the wiring of
the placed components.
 To place a jumper wire:
1. Click on a socket connected to the pin where you wish to start the jumper and begin
moving the cursor. Legitimate “target” pins (green) display as you move the cursor.
2. Click to place the jumper in the desired socket.

3-10

Electronics Workbench

Wiring Placed Components

3. Return to the schematic view and note that the color of the wire connecting the two pins
has changed to green to indicate a connection has been made.

Green wire shows connection done in 3D view

Note If a net contains more than two connections, all must be connected before any of the
wires in the net change color.
4. Continue placing jumpers until all schematic connections have been made.
Tip Run a Design Rules and Connectivity Check to see if there are any errors in your board.
Refer to “2.8 DRC and Connectivity Check” on page 2-13.
Note See also “2.5 Viewing Component Information” on page 2-9 and “2.7 Breadboard
Netlist dialog box” on page 2-12.

Multisim 9 for Educators

3-11

Chapter
4
Ladder Diagrams
This chapter describes the ladder diagram functionality that Multisim contains.
Some of the features described in this chapter may not be available in your edition of
Multisim 9. Refer to the release notes for a description of the features available in your
edition.
The following are described in this chapter.

4.1

Subject

Page No.

Overview

4-1

Creating a Ladder Diagram

4-2

AND Rungs and OR Rungs

4-5

Sample Circuits
Holding Tank
Conveyor Belt
Traffic Light

4-7
4-7
4-12
4-17

Overview
The Education edition of Multisim lets you capture and simulate Ladder Diagrams. These
diagrams are electrically based, as opposed to the binary/digital representations employed by
ladder logic. Diagrams of this type are used extensively for industrial motor control circuits.
Ladder Diagrams are able to drive output devices or take input data from regular schematics

and embed the instructions on how input states affect output states in either the same
schematic or separate hierarchical blocks or subcircuits that contain the Ladder Diagram.
Note Refer to the Multisim 9 User Guide for a complete description of hierarchical blocks
and subcircuits.

Multisim 9 for Educators

4-1

Ladder Diagrams

4.2

Creating a Ladder Diagram
This section describes the steps required to make a simple Ladder Diagram. The concepts
described here should be understood before reviewing the more complex circuits found in this
chapter.
This section describes how to build the Ladder Diagram that is reviewed in “4.3 AND Rungs
and OR Rungs” on page 4-5.

Note For details on all ladder diagram components, refer to “A.3 Ladder Diagram Parts” on
page A-22.
Circuit Notes:
•

•
•
•
•
•

The relays (X1-X4) are normally open relays. When their controlling coils (M1or M2) are
energized they close. (The controlling coils are set in the Value tab of each relay’s
properties dialog box. For details, see “A.3.4.4 Relay Contact NO” on page A-27).
Both X1 AND X2 must be closed for the lamp in the AND rung (X5) to light up.
Either X3 OR X4 must be closed for the lamp in the OR rung (X6) to light up.
Coil M1 controls the relays with M1 as their reference. (X1 and X3).
Coil M2 controls the relays with M2 as their reference. (X2 and X4).
Use keys 1 and 2 on your keyboard to open and close switches J1 and J2.

 To add the diagram’s rungs:
1. Select Place/Ladder Rungs. The cursor appears with the rung’s left and right terminators
attached.

4-2

Electronics Workbench

Creating a Ladder Diagram

2. Click to place the first rung and continue clicking and placing until you have placed four
rungs as shown below. Right-click to stop placing rungs.

 To add components to the rungs:
1. Select Place/Component, navigate to the Normally Open Relay Contact
(RELAY_CONTACT_NO) click OK.
Note This device is found in the Ladder Diagrams Group - Ladder Contacts Family.
2. Drop the relay contact directly onto the first rung.

Multisim 9 for Educators

4-3

Ladder Diagrams

3. Continue in this manner until all relay contacts have been placed. (X4 must be placed and
then wired separately).

4. Place the lamps (Group - Indicators; Family - Lamp).

5. Place relay coils M1 and M2 on the third and fourth rungs (Group - Ladder Diagrams;
Family - Ladder Relay Coils).

6. Place switches J1 and J2.

4-4

Electronics Workbench

AND Rungs and OR Rungs

7. Double-click on each switch, select the Value tab, and change the key for J1 to 1 and the
key for J2 to 2.

 To change the controlling device reference for X2 and X4:
1. Double-click on X2 and click the Value tab.
2. Enter M2 in the Controlling Device Reference field and click OK.
Repeat for X4. The completed Ladder Diagram appears as shown below.

4.3

AND Rungs and OR Rungs
This section illustrates the difference between AND rungs and OR rungs that are found in
Ladder Diagrams. The concepts described here should be understood before reviewing the
more complex circuits found in this chapter.

Multisim 9 for Educators

4-5

Ladder Diagrams

 To activate the lamp in the OR rung:
1. Select Simulate/Run to start simulation of the circuit.
2. Press 1 on your keyboard to close J1. Lamp X6 lights as described below.

2.
All relays with M1
as their reference
are energized.

3.
X6 lights because
only X3 OR X4 need
to be energized to
complete the circuit.

1.
Pressing 1 closes J1
which activates coil M1.

If you press 2 on your keyboard, J2 closes which activates coil M2. X6 lights because X4
is energized.
 To active the lamp in the AND rung:
1. Select Simulate/Run to start simulation of the circuit.

4-6

Electronics Workbench

Sample Circuits

2. Press 1 and 2 on your keyboard to close J1 and J2. Lamps X5 and X6 light as described
below.

3.
All relays with M1
and M2 as their
references are
energized.

5.
X5 lights because X1
AND X2 are energized
and the circuit is
complete.
4.
X6 lights because X3
OR X4 is energized and
the circuit is complete.
1.
Pressing 1 closes J1
which activates coil M1.
2.
Pressing 2 closes J2
which activates coil M2.

4.4

Sample Circuits

4.4.1

Holding Tank
This section contains an example of a logic diagram that drives a circuit that fills and then
empties a fluid holding tank.

For details on the user-settable
parameters for the Holding Tank,
Input Module and Output Module,
see “A.3 Ladder Diagram Parts”
on page A-22

Multisim 9 for Educators

4-7

Ladder Diagrams

The Ladder Diagram is contained in a separate
Hierarchical Block called HoldingTankLogic.
For details on hierarchical blocks, refer to the
Multisim 9 User Guide.

 To activate this circuit:
1. Select Simulate/Run to begin simulation.
2. Press P on your keyboard to activate the Power temporary switch. This sends 5 V to pin
IN4 of Input Module U2 (Input Module Base Address = 100) which in turn energizes Input

4-8

Electronics Workbench

Sample Circuits

Contact X1 in the Power Lock-up Rung of the ladder diagram. Relay Coil M1 is
energized, causing all Relay Contacts with Relay Device Reference = M1 to energize.

 To run the holding tank circuit:
1. Activate the circuit as described above.
2. Press R on your keyboard to activate the Run temporary switch.
Tip Select Window/Tile Vertical to view the ladder diagram and the circuit at the same time.
Observe the interaction between the ladder diagram and the circuit as the simulation
proceeds.

Multisim 9 for Educators

4-9

Ladder Diagrams

3. As the simulation proceeds, the tank begins to fill.

Moving arrow
indicates direction
of fluid flow.

4. When the level of the fluid in the tank gets to the Set Point, fluid stops being pumped.

4-10

Electronics Workbench

Sample Circuits

5. After a delay of five seconds, the tank begins to empty.

6. When the tank is empty, the flow stops.

Multisim 9 for Educators

4-11

Ladder Diagrams
 To turn off the power at any point in the simulation:
1. Press K on your keyboard to activate the Kill temporary switch. This sends 5 V to pin IN3
of Input Module U2 (Input Module Base Address = 100) which in turn energizes Input
Contact X2 (the contact opens). The continuity in the Power Lock-up Rung is broken and
Relay Coil M1 is de-energized, which in turn switches off all Relay Contacts with Relay
Device Reference = M1.
When you press K, X20 is also temporarily energized, which in turn temporarily energizes
Output Coil Y2, which sends a pulse to pin Out3 of Output Module U3. This is wired to
the Stop pin of the holding tank, so the tank stops filling or emptying (depending on which
is currently occuring).

4.4.2

Conveyor Belt
This section contains an example of a Ladder Diagram that drives a conveyor belt.

For details on the user-settable
parameters for the Conveyor Belt,
Input Module and Output Module,
see “A.3 Ladder Diagram Parts”
on page A-22

4-12

Electronics Workbench

Sample Circuits

The Ladder Diagram is contained in a separate
Hierarchical Block called ConveyorLogic. For
details on hierarchical blocks, refer to the
Multisim 9 User Guide.

 To activate this circuit:
1. Select Simulate/Run to begin simulation.
2. Press P on your keyboard to activate the Power temporary switch. This sends 5 V to pin
IN2 of Input Module U4 (Input Module Base Address = 101) which in turn energizes Input

Multisim 9 for Educators

4-13

Ladder Diagrams

Contact X1 in the Power Lock-up Rung of the ladder diagram. Relay Coil M1 is
energized, causing all Relay Contacts with Relay Device Reference = M1 to energize.

 To run the conveyor belt:
1. Activate the circuit as described earlier.
2. Press R on your keyboard to activate the Run temporary switch.
Tip Select Window/Tile Vertical to view the ladder diagram and the circuit at the same time.
Observe the interaction between the ladder diagram and the circuit as the simulation
proceeds.

4-14

Electronics Workbench

Sample Circuits

3. As the simulation proceeds, the box moves along the conveyor belt to Position Sensor 2
(PS2). The box stops moving and balls begin dropping from the hopper into the box.

PS2

4. When five balls have dropped into the box (counted by Count sensor and C1), the hopper
stops dropping balls.

Count Sensor

Multisim 9 for Educators

4-15

Ladder Diagrams

5. The conveyor continues moving and stops when the box gets to Position Sensor 3 (PS3).

PS3

 To turn off the power at any point in the simulation:
1. Press K on your keyboard to activate the Kill temporary switch. This sends 5 V to pin IN3
of Input Module U4 (Input Module Base Address = 101) which in turn energizes Input
Contact X3 (the contact opens). The continuity in the Power Lock-up Rung is broken and
Relay Coil M1 is de-energized, which in turn switches off all Relay Contacts with Relay
Device Reference = M1.
When you press K, X19 is also temporarily energized, which in turn temporarily energizes
Output Coil Y2, which sends a pulse to pin Out3 of Output Module U2. This is wired to
the Stop pin of the conveyor belt, so the belt stops.

4-16

Electronics Workbench

Sample Circuits

4.4.3

Traffic Light
The ladder diagram in this section runs two traffic lights.

The Ladder Diagram is contained in a separate
Hierarchical Block called TrafficLightLogic.
For details on hierarchical blocks, refer to the
Multisim 9 User Guide.

 To run the traffic lights:
1. Select Simulate/Run.
2. Press P on your keyboard to activate the Power momentary switch.

Multisim 9 for Educators

4-17

Ladder Diagrams

Tip Select Window/Tile Vertical to view the ladder diagram and the circuit at the same time.
Observe the interaction between the ladder diagram and the circuit as the simulation
proceeds.
3. The red and green lights in traffic lights U1 and U3 light as shown below.

4. After 15 seconds, the green lights turn amber.

4-18

Electronics Workbench

Sample Circuits

5. After 5 more seconds, the amber lights turn red and the red lights turn green.

6. After 15 seconds, the green lights turn amber.

Multisim 9 for Educators

4-19

Ladder Diagrams

7. After 5 more seconds, the amber lights turn red and the red lights turn green.

8. The cycle continues in this way until you stop the simulation, or press K to activate the
Kill momentary switch.

4-20

Electronics Workbench

Appendix A - Education Edition Parts
This appendix contains a description of the parts that are unique to the Education edition of
Multisim 9.

A.1

Rated Virtual Components
This component family contains a number of virtual components that can be rated to “blow” if
pre-set tolerance(s) are exceeded when the circuit is simulated. These tolerances are set in the
Values tab of each component’s properties window.
Tip “Rated” values in a component’s Value tab define behavior and design. “Maximum”
values impose limits that, when exceeded, cause the component to “blow”.
The rated virtual components are found in the Basic Group in the Rated Virtual.

A.1.1 Rated 555 Timer

The 555 timer is an IC chip that is commonly used as an astable multivibrator, a monostable
multivibrator or a voltage-controlled oscillator. The 555 timer consists basically of two
comparators, a resistive voltage divider, a flip-flop and a discharge transistor. It is a two-state
device whose output voltage level can be either high or low. The state of the output can be

Multisim 9 for Educators

A-1

controlled by proper input signals and time-delay elements connected externally to the 555
timer.
Note Refer to the Component Reference Guide for a more detailed discussion of the
555 timer.
 To adjust the component’s tolerances:
1. Double-click on the placed component and click the Value tab.
2. Change the following values as desired:
• Animation Delay Factor — increase this number to slow the speed of animation of the
symbol blowing. This is not a real-time value.
• Maximum Supply Voltage — the maximum supply voltage allowed. If this is exceeded
during simulation, the timer’s VCC pin blows.
• Maximum Output Current — the maximum output current allowed. If this is exceeded
during simulation, the timer’s OUT pin blows.
3. Click OK.

A.1.2 Rated BJTs

A bipolar junction transistor, or BJT, is a current-based valve used for controlling electronic
current. BJTs are operated in three different modes, depending on which element is common
to input and output: common base, common emitter or common collector. The three modes
have different input and output impedances and different current gains, offering individual
advantages to a designer.
Note Refer to the Component Reference Guide for a more detailed discussion of BJTs.
 To adjust the component’s tolerances:
1. Double-click on the placed component and click the Value tab.
2. Change the following values as desired:
• Animation Delay Factor — increase this number to slow the speed of animation of the
symbol blowing. This is not a real-time value.
• Maximum Collector-Emitter Voltage — the maximum collector-emitter voltage
allowed. If this value is exceeded during simulation, the BJT blows.
• Maximum Collector-Base Voltage — the maximum collector-base voltage allowed. If
this value is exceeded during simulation, the BJT blows.

A-2

Electronics Workbench

Rated Virtual Components

• Maximum Emitter-Base Voltage — the maximum emitter-base voltage allowed. If this
value is exceeded during simulation, the BJT blows.
• Maximum Collector Current — the maximum collector current allowed. If this value is
exceeded during simulation, the BJT blows.
• Saturation Current — the maximum saturation current allowed. If this value is
exceeded during simulation, the BJT blows.
• Maximum Forward Beta — the maximum forward beta allowed. If this value is
exceeded during simulation, the BJT blows.
3. Click OK.

A.1.3 Rated Capacitors

A capacitor stores electrical energy in the form of an electrostatic field. Capacitors are widely
used to filter or remove AC signals from a variety of circuits. In a DC circuit, they can be used
to block the flow of direct current while allowing AC signals to pass.
A capacitor’s capacity to store energy is called its capacitance, C, which is measured in
farads. It can have any value from pF to mF.
The variable capacitor is simulated as an open circuit with a current across the capacitor
forced to zero by a large impedance value.
The polarized capacitor must be connected with the right polarity. Otherwise, an error
message will appear.Its capacitance, measured in farads, can be any value from pF to F.
Note Refer to the Component Reference Guide for a more detailed discussion of capacitors.
 To adjust the component’s tolerances:
1. Double-click on the placed component and click the Value tab.
2. Change the following values as desired:
• Animation Delay Factor — increase this number to slow the speed of animation of the
symbol blowing. This is not a real-time value.
• Capacitance — set the capacitance as desired.
• Voltage Rating (Pk) — the maximum peak voltage across the capacitor allowed. If this
value is exceeded during simulation, the capacitor blows.
• Initial Conditions — the initial charge across the capacitor, before simulation begins.
3. Click OK.

Multisim 9 for Educators

A-3

A.1.4 Rated Diodes

Diodes allow current to flow in only one direction and can therefore be used as simple
solid-state switches in AC circuits, being either open (not conducting) or closed (conducting).
Terminal A is called the anode and terminal K is called the cathode.
Note Refer to the Component Reference Guide for a more detailed discussion of diodes.
 To adjust the component’s tolerances:
1. Double-click on the placed component and click the Value tab.
2. Change the following values as desired:
• Animation Delay Factor — increase this number to slow the speed of animation of the
symbol blowing. This is not a real-time value.
• Reverse Breakdown Voltage — set as desired.
• Current at Breakdown Voltage — set as desired.
• Saturation Current — the maximum current through the capacitor allowed. If this
value is exceeded during simulation, the diode blows.
• Transit Time (sec) — used to model charge storage effects - pertains to the electrons
lifetime, alternately the hole lifetime at the p-n junction.
3. Click OK.

A.1.5 Rated Fuses

This is a resistive component that protects against power surges and current overloads.
A fuse will blow (open) if the current in the circuit goes above Imax, the maximum current
rating. Imax can have any value from mA to kA.
Note Refer to the Component Reference Guide for a more detailed discussion of fuses.
 To adjust the component’s tolerances:
1. Double-click on the placed component and click the Value tab.

A-4

Electronics Workbench

Rated Virtual Components

2. Change the following values as desired:
• Animation Delay Factor — increase this number to slow the speed of animation of the
symbol blowing. This is not a real-time value.
• Maximum Current (Imax) — the maximum current allowed through the fuse. If this
value is exceeded during simulation, the fuse blows.
3. Click OK.

A.1.6 Rated Inductors

An inductor stores energy in an electromagnetic field created by changes in current through it.
Its ability to oppose a change in current flow is called inductance, L, and is measured in
Henrys. An inductor can have any value from µH to H.
Note Refer to the Component Reference Guide for a more detailed discussion of inductors.
 To adjust the component’s tolerances:
1. Double-click on the placed component and click the Value tab.
2. Change the following values as desired:
• Animation Delay Factor — increase this number to slow the speed of animation of the
symbol blowing. This is not a real-time value.
• Inductance — the coil’s inductance. Set as desired.
• Coil Resistance — set as desired.
• Current Rating (Pk) — the maximum peak current allowed through the inductor. If this
value is exceeded during simulation, the inductor blows.
• Initial Conditions — the initial current through the inductor, before simulation begins.
3. Click OK.

A.1.7 Rated LEDs

Multisim 9 for Educators

A-5

This diode emits visible light when forward current through it, Id, exceeds the turn-on current,
Ion. The electrical model of the LED is the same as the diode model.
Note Refer to the Component Reference Guide for a more detailed discussion of LEDs.
 To adjust the component’s tolerances:
1. Double-click on the placed component and click the Value tab.
2. Change the following values as desired:
• Animation Delay Factor — increase this number to slow the speed of animation of the
symbol blowing. This is not a real-time value.
• On Current (Ion) — the current required to switch the LED on.
• Forward Voltage Drop (Vf) — the voltage drop across the LED when it is conducting.
• Reverse Breakdown Voltage — set as desired.
• Maximum Rated Power (Watts) — the maximum power dissipation across the LED
allowed. If this value is exceeded during simulation, the inductor blows.
3. Click OK.

A.1.8 Rated DC Motor

The component is a universal model of an ideal DC motor which can be used to model the
behavior of a DC motor excited in parallel, in series or separately.
Note Refer to the Component Reference Guide for a more detailed discussion of DC motors.
 To adjust the component’s tolerances:
1. Double-click on the placed component and click the Value tab.
2. Change the following values as desired:
• Animation Delay Factor — increase this number to slow the speed of animation of the
symbol blowing. This is not a real-time value.
• Rated Armature Voltage (Van) — set as desired.
• Maximum Armature Voltage — the maximum voltage across the armature allowed. If
this value is exceeded during simulation, the motor blows.
• Rated Armature Current (Ian) — set as desired.
• Maximum Armature Current — the maximum current through the armature allowed. If
this value is exceeded during simulation, the motor blows.
• Rated Field Voltage (Vfn) — set as desired.

A-6

Electronics Workbench

Rated Virtual Components

• Maximum Field Voltage — the maximum field voltage allowed. If this value is
exceeded during simulation, the motor blows.
• Armature Resistance (Ra) — set as desired.
• Armature Inductance (La) — set as desired.
• Field Resistance (Rf) — set as desired.
• Field Inductance (Lf) — set as desired.
Tip To view the following fields, click in a blank space in the Value tab and drag the mouse
upward.
• Shaft Friction (Bf) — set as desired.
• Rotational Inertia (J) — set as desired.
• Rated Rotational Speed (NN) — set as desired.
• Load Torque (Tl) — set as desired.
3. Click OK.

A.1.9 Rated Relay

The magnetic relay is a coil with a specified inductance that causes a contact to open or close
when a specified current (Ion) charges it.
Note Refer to the Component Reference Guide for a more detailed discussion of relays.
 To adjust the component’s tolerances:
1. Double-click on the placed component and click the Value tab.
2. Change the following values as desired:
• Animation Delay Factor — increase this number to slow the speed of animation of the
symbol blowing. This is not a real-time value.
• Coil Inductance — set as desired.
• Coil Resistance — set as desired.
• On Current (Ion) — set as desired.
• Off Current (Ioff) — set as desired .
• Maximum Rated Voltage — the maximum voltage allowed. If this value is exceeded
during simulation, the relay blows.
• Maximum Rated Current — the maximum current allowed. If this value is exceeded

Multisim 9 for Educators

A-7

during simulation, the relay blows.
3. Click OK.

A.1.10 Rated Opamp

An ideal operational amplifier (Opamp) is an amplifier with infinite gain, infinite input
impedance and zero output impedance. With the application of negative feedback, Opamps
can be used to implement functions such as addition, subtraction, differentiation, integration,
averaging and amplification.
An opamp can have a single input and single output, a differential input and single output, or
a differential input and differential output.
Note Refer to the Component Reference Guide for a more detailed discussion of opamps.
 To adjust the component’s tolerances:
1. Double-click on the placed component and click the Value tab.
2. Change the following values as desired:
• Animation Delay Factor — increase this number to slow the speed of animation of the
symbol blowing. This is not a real-time value.
• Maximum Supply Voltage (+/-) — the maximum voltage (+/) allowed. If this value is
exceeded during simulation, the opamp blows.
• Maximum Input Voltage (+/-) — the maximum input voltage (+/) allowed. If this value
is exceeded during simulation, the opamp blows.
• Maximum Differential Input Voltage — the maximum differential input voltage
allowed. If this value is exceeded during simulation, the opamp blows.
• Maximum Sink/Source Output Current — If this value is exceeded during simulation,
the opamp blows.
3. Click OK.

A-8

Electronics Workbench

Rated Virtual Components

A.1.11 Rated Photodiode

The photodiode emits a source of infrared light which is detected by the phototransistor.
These devices are intended to be used in pairs.
You must specify a light channel in each of these paired parts (photodiode and
phototransistor). This is done in the Value tab of the component’s properties screen. Each
diode must have a different value for its light channel, however, the phototransistor can share
the same value with several other phototransistors.
 To adjust the component’s tolerances:
1. Double-click on the placed component and click the Value tab.
2. Change the following values as desired:
• Animation Delay Factor — increase this number to slow the speed of animation of the
symbol blowing. This is not a real-time value.
• Light Channel (Integer) — set to match the light channel for the corresponding
phototransistor(s).
• On Current (Ion) — set as desired.
• Forward Voltage Drop (Vf) — set as desired.
• Reverse Breakdown Voltage — set as desired.
• Maximum Rated Power (Watts) — If this value is exceeded during simulation, the
photodiode blows.
3. Click OK.

A.1.12 Rated Phototransistor

The photodiode emits a source of infrared light which is detected by the phototransistor.
These devices are are intended to be used in pairs.

Multisim 9 for Educators

A-9

You must specify a light channel in each of these paired parts (photodiode and
phototransistor). This is done in the Value tab of the component’s properties screen. Each
diode must have a different value for its light channel, however, the phototransistor can share
the same value with several other phototransistors.
 To adjust the component’s tolerances:
1. Double-click on the placed component and click the Value tab.
2. Change the following values as desired:
• Animation Delay Factor — increase this number to slow the speed of animation of the
symbol blowing. This is not a real-time value.
• Light Channel (Integer) — set to match the light channel for the corresponding
photodiode.
• Maximum Collector-Emitter Voltage — If this value is exceeded during simulation, the
phototransistor blows.
• Maximum Collector Current — If this value is exceeded during simulation, the
phototransistor blows.
3. Click OK.

A.1.13 Rated Potentiometer

This component acts much like a tapped/split resistor, except that you can, with a single
keystroke, adjust its resistance.
Note Refer to the Component Reference Guide for a more detailed discussion of
potentiometers.
 To adjust the component’s tolerances:
1. Double-click on the placed component and click the Value tab.
2. Change the following values as desired:
• Key — enter the key that will increase the resistance by the amount set in the Increment
field.
• Increment — enter the amount by which the resistance will increase when the key set
in the Key field is pressed.
• Animation Delay Factor — increase this number to slow the speed of animation of the

A-10

Electronics Workbench

Rated Virtual Components

symbol blowing. This is not a real-time value.
• Resistance — the maximum resistance of the potentiometer.
• Maximum Rated Power (Watts) — If this value is exceeded during simulation, the
potentiometer blows.
3. Click OK.

A.1.14 Rated Pullup

This component is used to raise the voltage of a circuit to which it is connected. One end is
connected to Vcc. The other end is connected to a point in a logic circuit that needs to be
raised to a voltage level closer to Vcc.
 To adjust the component’s tolerances:
1. Double-click on the placed component and click the Value tab.
2. Change the following values as desired:
• Animation Delay Factor — increase this number to slow the speed of animation of the
symbol blowing. This is not a real-time value.
• Voltage (V) — set as desired.
• Resistance — set as desired.
• Maximum Rated Power (Watts) — If this value is exceeded during simulation, the
pullup blows.
3. Click OK.

A.1.15 Rated Resistor

Resistors come in a variety of sizes, related to the power they can safely dissipate.
Note Refer to the Component Reference Guide for a more detailed discussion of resistors.

Multisim 9 for Educators

A-11

 To adjust the component’s tolerances:
1. Double-click on the placed component and click the Value tab.
2. Change the following values as desired:
• Animation Delay Factor — increase this number to slow the speed of animation of the
symbol blowing. This is not a real-time value.
• Resistance — set as desired.
• Maximum Rated Power (Watts) — If this value is exceeded during simulation, the
resistor blows.
• Temperature — set as desired.
• Temperature Coefficient 1 — set as desired.
• Temperature Coefficient 2 — set as desired.
• Nominal Temperature — set as desired.
3. Click OK.

A.1.16 Rated Transformers

The transformer is one of the most common and useful applications of inductance. It can step
up or step down an input primary voltage (V1) to a secondary voltage (V2). The relationship
is given by V1/V2 = n, where n is the ratio of the primary turns to the secondary turns.
Note Refer to the Component Reference Guide for a more detailed discussion of
transformers.
 To adjust the component’s tolerances:
1. Double-click on the placed component and click the Value tab.
2. Change the following values as desired:
• Animation Delay Factor — increase this number to slow the speed of animation of the
symbol blowing. This is not a real-time value.
• Maximum Primary Voltage — If this value is exceeded during simulation, the resistor
blows.
• Maximum Primary Current — If this value is exceeded during simulation, the resistor
blows.
• Maximum Secondary 1 Voltage — If this value is exceeded during simulation, the

A-12

Electronics Workbench

Rated Virtual Components

resistor blows.
• Maximum Secondary 1 Current — If this value is exceeded during simulation, the
resistor blows.
• Maximum Secondary 2 Voltage — If this value is exceeded during simulation, the
resistor blows.
• Maximum Secondary 2 Current — If this value is exceeded during simulation, the
resistor blows.
• Maximum Output Power (kVA) — If this value is exceeded during simulation, the
resistor blows.
• Primary-to-Secondary Turns Ratio — set as desired.
• Leakage Inductance (Le) — set as desired.
• Magnetizing Inductance (Lm) — set as desired.
Tip To view the following fields, click in a blank space in the Value tab and drag the mouse
upward.
• Primary Winding Resistance — set as desired.
• Secondary Winding Resistance — set as desired.
3. Click OK.

A.1.17 Rated Variable Capacitor

This component acts much like a regular capacitor, except that you can, with a single
keystroke, adjust its capacitance.
Note Refer to the Component Reference Guide for a more detailed discussion of capacitors.
 To adjust the component’s tolerances:
1. Double-click on the placed component and click the Value tab.
2. Change the following values as desired:
• Key — enter the key that will increase the capacitance by the amount set in the
Increment field.
• Increment — enter the amount by which the capacitance will increase when the key set
in the Key field is pressed.
• Animation Delay Factor — increase this number to slow the speed of animation of the
symbol blowing. This is not a real-time value.

Multisim 9 for Educators

A-13

• Capacitance — the maximum capacitance of the variable capacitor.
• Initial Conditions — the charge across the capacitor that is present before simulation
starts.
• Voltage Rating (Pk) — If this value is exceeded during simulation, the capacitor blows.
3. Click OK.

A.1.18 Rated Variable Inductor

This component acts much like a regular inductor, except that you can, with a single
keystroke, adjust its inductance.
Note Refer to the Component Reference Guide for a more detailed discussion of inductors.
 To adjust the component’s tolerances:
1. Double-click on the placed component and click the Value tab.
2. Change the following values as desired:
• Key — enter the key that will increase the inductance by the amount set in the
Increment field.
• Increment — enter the amount by which the inductance will increase when the key set
in the Key field is pressed.
• Animation Delay Factor — increase this number to slow the speed of animation of the
symbol blowing. This is not a real-time value.
• Inductance — the maximum inductance of the variable inductor.
• Coil Resistance — set as desired.
• Initial Conditions — the current through the inductor that is present before simulation
starts.
• Current Rating (Pk) — If this value is exceeded during simulation, the inductor blows.
3. Click OK.

A-14

Electronics Workbench

3D Virtual Parts

A.1.19 Rated Virtual Components Toolbar

Some of the more commonly-used rated virtual components can be placed using the
Rated Virtual Components toolbar.
 To display the Rated Virtual Components toolbar, click the Show Rated Family button in the
Virtual toolbar (refer to the Multisim 9 User Guide for Virtual toolbar information).
The buttons (from left to right) in the Rated Virtual Components toolbar place the following
virtual components: NPN transistor; PNP transistor; Capacitor; Diode; Inductor; Motor;
normally closed relay; normally open relay; combination relay; resistor.

A.2

3D Virtual Parts
This family contains a number of 3D parts. These components function normally when the
circuit is simulated, but appear like the real component on the circuit schematic.
The 3D virtual components are found in the Basic Group in the 3D Rated Virtual family.

A.2.1 3D 555 Timer

The 555 timer is an IC chip that is commonly used as an astable multivibrator, a monostable
multivibrator or a voltage-controlled oscillator. The 555 timer consists basically of two
comparators, a resistive voltage divider, a flip-flop and a discharge transistor. It is a two-state
device whose output voltage level can be either high or low. The state of the output can be
controlled by proper input signals and time-delay elements connected externally to the 555
timer.
Note Refer to the Component Reference Guide for a more detailed discussion of the
555 timer.

Multisim 9 for Educators

A-15

A.2.2 3D BJT

A bipolar junction transistor, or BJT, is a current-based valve used for controlling electronic
current. BJTs are operated in three different modes, depending on which element is common
to input and output: common base, common emitter or common collector. The three modes
have different input and output impedances and different current gains, offering individual
advantages to a designer.
Note Refer to the Component Reference Guide for a more detailed discussion of BJTs.

A.2.3 3D Capacitors

A capacitor stores electrical energy in the form of an electrostatic field. Capacitors are widely
used to filter or remove AC signals from a variety of circuits. In a DC circuit, they can be used
to block the flow of direct current while allowing AC signals to pass.
Note Refer to the Component Reference Guide for a more detailed discussion of capacitors.

A-16

Electronics Workbench

3D Virtual Parts

A.2.4 3D 74LS160N Counter

This synchronous, presettable decade counter features an internal carry look-ahead for fast
counting.
Note Refer to the Component Reference Guide for a more detailed discussion of the
74LS160N counter.

A.2.5 3D Diode

Diodes allow current to flow in only one direction and can therefore be used as simple
solid-state switches in AC circuits, being either open (not conducting) or closed (conducting).
Terminal A is called the anode and terminal K is called the cathode.
Note Refer to the Component Reference Guide for a more detailed discussion of diodes.

Multisim 9 for Educators

A-17

A.2.6 3D Inductor

An inductor stores energy in an electromagnetic field created by changes in current through it.
Its ability to oppose a change in current flow is called inductance, L, and is measured in
Henries. An inductor can have any value from µH to H.
Note Refer to the Component Reference Guide for a more detailed discussion of inductors.

A.2.7 3D LED

This diode emits visible light when forward current through it, Id, exceeds the turn-on current,
Ion. The electrical model of the LED is the same as the diode model.
Note Refer to the Component Reference Guide for a more detailed discussion of LEDs.

A-18

Electronics Workbench

3D Virtual Parts

A.2.8 3D MOSFET

A MOSFET is a Metal-Oxide-Semiconductor FET. This transistor is a type of FET that uses
an induced electrical field to control current through the device. Either negative or positive
gate voltages can be applied to control the current.
Note Refer to the Component Reference Guide for a more detailed discussion of MOSFETs.

A.2.9 3D DC Motor

The component is a universal model of an ideal DC motor which can be used to model the
behavior of a DC motor excited in parallel, in series or separately.
Note Refer to the Component Reference Guide for a more detailed discussion of DC motors.

A.2.10 3D Opamp

Multisim 9 for Educators

A-19

An ideal operational amplifier (Opamp) is an amplifier with infinite gain, infinite input
impedance and zero output impedance. With the application of negative feedback, Opamps
can be used to implement functions such as addition, subtraction, differentiation, integration,
averaging and amplification.
Note Refer to the Component Reference Guide for a more detailed discussion of opamps.

A.2.11 3D Potentiometer

This component acts much like a regular resistor, except that you can, with a single keystroke,
adjust its resistance.
Note Refer to the Component Reference Guide for a more detailed discussion of
potentiometers.

A.2.12 3D AND Gate

This device contains four independent 2-input AND gates.
Note Refer to the Component Reference Guide for a more detailed discussion of the 74LS08
Quad AND gate.

A-20

Electronics Workbench

3D Virtual Parts

A.2.13 3D Resistor

Resistors come in a variety of sizes, depending on the power they can safely dissipate. A
resistor's resistance, R, is measured in ohms.
Note Refer to the Component Reference Guide for a more detailed discussion of resistors.

A.2.14 3D Shift Register

This serial shift-register shifts the data in the direction of QA toward QH when clocked. To
load the data at the 8-inputs into the device, apply a low level at the shift/load input. This
register is equipped with a complementary output at the eighth bit.
Note Refer to the Component Reference Guide for a more detailed discussion of the
74LS165N shift register.

A.2.15 3D Switch

This component is a SPST (single-pole, single-throw) switch.
Note Refer to the Component Reference Guide for a more detailed discussion of switches.

Multisim 9 for Educators

A-21

A.2.16 3D Components toolbar

Some of the more commonly-used 3D components can be placed using the 3D Components
toolbar.
 To display the 3D Components toolbar, click the Show 3D Family button in the Virtual toolbar
(refer to the Multisim 9 User Guide for Virtual toolbar information).
The buttons (from left to right) in the 3D Components toolbar place the following virtual
components: NPN transistor; PNP transistor; 100 uF capacitor; 10 pF capacitor; 100 pF
capacitor; 74LS160N counter; Diode ; 1 uH inductor; 1 uH inductor; Red LED; Yellow LED;
Green LED; MOSFET; DC motor; 741 OPAMP; Potentiometer; Quad AND gate;
1.1 k Resistor; Shift Register 74LS165N; Switch.

A.3

Ladder Diagram Parts

A.3.1 Ladder Rungs
A.3.1.1 L1 and L2

L1 is a Rung Starter and L2 is a Rung Terminator. Continuity between L1 and L2 is required
to activate/energize devices placed between them.

A-22

Electronics Workbench

Ladder Diagram Parts

A.3.2 Ladder I/O Modules
A.3.2.1 Input Module

This device is an input module for ladder diagrams and is available in various input voltages.
It is used to bring external stimulus into a ladder diagram.
 To set the Input Module’s base address:
1. Double-click on the module and select the Value tab.
2. Enter the desired value in the Input Module Base Address field. The default value is 100, as
shown in the above diagram.

A.3.2.2 Output Module

This device is an output module for ladder diagrams and is available in various output
voltages. It allows external circuit elements to be manipulated by the logic contained in a
ladder diagram.
 To set the Output Module’s base address:
1. Double-click on the module and select the Value tab.
2. Enter the desired value in the Output Module Base Address field. The default value is 200,
as shown in the above diagram.

Multisim 9 for Educators

A-23

A.3.3 Ladder Relay Coils
A.3.3.1 Relay Coil

This device is a relay coil for ladder diagrams. When this coil is energized, corresponding
contact(s) which reference this device will change their state. (For example, a normally open
contact will close).
 To set the coil reference for this device:
1. Double-click on the relay coil and select the Value tab.
2. Enter the desired value in the Coil Reference field.

A.3.3.2 Negated Relay Coil

This device is a negated relay coil for ladder diagrams.
 To set the coil reference for this device:
1. Double-click on the relay coil and select the Value tab.
2. Enter the desired value in the Coil Reference field.

A.3.3.3 Set Coil

This device is a latch relay coil for ladder diagrams (requires a reset coil to operate).
 To set the coil reference for this device:
1. Double-click on the relay coil and select the Value tab.
2. Enter the desired value in the Coil Reference field.

A-24

Electronics Workbench

Ladder Diagram Parts

A.3.3.4 Reset Coil

This device is an unlatch relay coil for ladder diagrams, used to reset timers, counters and set
coils.
 To set the target device for this coil:
1. Double-click on the set coil and select the Value tab.
2. Enter the desired value in the Target Device Reference field.

A.3.3.5 Pulsed Relay Coil

This device is a positive pulse relay coil, produce a positive pulse of user-definable duration.
 To set the parameters for this coil:
1. Double-click on the positive pulse relay coil and select the Value tab.
2. Enter the desired values in the Coil Reference and Pulse Duration fields.

A.3.4 Ladder Contacts
A.3.4.1 Input Contact NC
This device is a normally closed input contact for ladder diagrams. It responds to the status at
the specified input on the referenced input module.
 To set the parameters for this device:
1. Double-click on the input contact and select the Value tab.
2. Enter the address of the input module associated with this contact (see “A.3.2.1 Input
Module” on page A-23) in the Input Module Base Address field.

Multisim 9 for Educators

A-25

3. Enter the number of the input on the input module which will control this input contact in
the Input Number field.

Input Number
Input Module Base Address

A.3.4.2 Input Contact NO
This device is a normally open input contact for ladder diagrams. It responds to the status at
the specified input on the referenced input module.
 To set the parameters for this device:
1. Double-click on the input contact and select the Value tab.
2. Enter the address of the input module associated with this contact (see “A.3.2.1 Input
Module” on page A-23) in the Input Module Base Address field.
3. Enter the number of the input on the input module which will control this input contact in
the Input Number field.

Input Number
Input Module Base Address

A.3.4.3 Relay Contact NC

This device is a normally closed relay contact for ladder diagrams. This contact will open
when the controlling device (coil, counter or timer) is energized.
 To set the parameters for this device:
1. Double-click on the NC contact and select the Value tab.
2. Enter the desired value in the Controlling Device Reference field.

A-26

Electronics Workbench

Ladder Diagram Parts

A.3.4.4 Relay Contact NO

This device is a normally open relay contact for ladder diagrams.
 To set the parameters for this device:
1. Double-click on the relay contact and select the Value tab.
2. Enter the desired value in the Controlling Device Reference field.

A.3.5 Ladder Counters
A.3.5.1 Count Off

This device is a count OFF counter with preset, for ladder diagrams. The contact associated
with this device will be energized at simulation start. The contact will be de-energized when
the counter “Set Value” is reached.
This device does not retain its count out state and will automatically reset after count out
occurs on the next action.
 To set the parameters for this device:
1. Double-click on the counter and select the Value tab.
2. Enter the following parameters:
• Set Value — the counter’s count out value.
• Preset Value — the count starting point.
• Counter Reference — set to the device’s RefDes by default. You can enter any other
identifying string.

Multisim 9 for Educators

A-27

A.3.5.2 Count Off Hold

This device is a count OFF and hold counter with preset, for ladder diagrams. The contact
associated with this device will be energized at simulation start. The contact will be
de-energized when the counter “Set Value” is reached.
Once the count out state is reached, the counter status is held until simulation is restarted.
 To set the parameters for this device:
1. Double-click on the counter and select the Value tab.
2. Enter the following parameters:
• Set Value — the counter’s count out value.
• Preset Value — the count starting point.
• Counter Reference — set to the device’s RefDes by default. You can enter any other
identifying string.

A.3.5.3 Count Off Reset

This device is a count OFF and hold until reset counter with preset, for ladder diagrams. The
contact associated with this device will be energized at simulation start. The contact will be
de-energized when the counter “Set Value” is reached.
You can reset this counter using a reset coil at any time during simulation, regardless of the
current counter state.
 To set the parameters for this device:
1. Double-click on the counter and select the Value tab.
2. Enter the following parameters:
• Set Value — the counter’s count out value.
• Preset Value — the count starting point.
• Counter Reference — set to the device’s RefDes by default. You can enter any other

A-28

Electronics Workbench

Ladder Diagram Parts

identifying string.

A.3.5.4 Count Off Up Down

This device is a resettable up/down count OFF and hold until reset counter with preset, for
ladder diagrams. This bi-directional counter increments the count via the “U” input, and
decrements the count via the “D” input.
 To set the parameters for this device:
1. Double-click on the counter and select the Value tab.
2. Enter the following parameters:
• Set Value — the counter’s count out value.
• Preset Value — the count starting point.
• Counter Reference — set to the device’s RefDes by default. You can enter any other
identifying string.

A.3.5.5 Count On

This device is a count ON counter with preset, for ladder diagrams. The contact associated
with this device will be de-energized at simulation start. The contact will be re-energized
when the counter “Set Value” is reached.
This device does not retain its count out state and will automatically reset after count out
occurs on the next action.
 To set the parameters for this device:
1. Double-click on the counter and select the Value tab.
2. Enter the following parameters:
• Set Value — the counter’s count out value.
• Preset Value — the count starting point.

Multisim 9 for Educators

A-29

• Counter Reference — set to the device’s RefDes by default. You can enter any other
identifying string.

A.3.5.6 Count On Hold

This device is a count ON and hold counter with preset, for ladder diagrams. The contact
associated with this device will be de-energized at simulation start. The contact will be
energized when the counter “Set Value” is reached.
Once the count out state is reached, the counter status is held until simulation is restarted.
 To set the parameters for this device:
1. Double-click on the counter and select the Value tab.
2. Enter the following parameters:
• Set Value — the counter’s count out value.
• Preset Value — the count starting point.
• Counter Reference — set to the device’s RefDes by default. You can enter any other
identifying string.

A.3.5.7 Count On Reset

This device is a count ON and hold until reset counter with preset, for ladder diagrams. The
contact associated with this device will be de-energized at simulation start. The contact will
be energized when the counter “Set Value” is reached.
You can reset this counter using a reset coil at any time during simulation, regardless of the
current counter state.
 To set the parameters for this device:
1. Double-click on the counter and select the Value tab.

A-30

Electronics Workbench

Ladder Diagram Parts

2. Enter the following parameters:
• Set Value — the counter’s count out value.
• Preset Value — the count starting point.
• Counter Reference — set to the device’s RefDes by default. You can enter any other
identifying string.

A.3.5.8 Count On Up Down

This device is a resettable up/down count ON and hold until reset counter with preset, for
ladder diagrams. This bi-directional counter increments the count via the “U” input, and
decrements the count via the “D” input.
 To set the parameters for this device:
1. Double-click on the counter and select the Value tab.
2. Enter the following parameters:
• Set Value — the counter’s count out value.
• Preset Value — the count starting point.
• Counter Reference — set to the device’s RefDes by default. You can enter any other
identifying string.

A.3.6 Ladder Timers
A.3.6.1 Timer TOFF

This device is a TOFF timer for ladder diagrams. The associated contact is energized at the
start of simulation, and is de-energized when this device “times out”. Any interuption in

Multisim 9 for Educators

A-31

continuity on the rung in which this timer is located causes the time value to be reset to zero.
(This occurs whether or not the timer has timed out).
 To set the parameters for this device:
1. Double-click on the timer and select the Value tab.
2. Enter the following parameters:
• Delay Time — the timer’s time out value.
• Timer Reference — set to the device’s RefDes by default. You can enter any other
identifying string.

A.3.6.2 Timer TON

This device is a TON timer for ladder diagrams. The associated contact is de-energized at the
start of simulation, and is energized when this device “times out”. Any interuption in
continuity on the rung in which this timer is located causes the time value to be reset to zero.
(This occurs whether or not the timer has timed out).
 To set the parameters for this device:
1. Double-click on the timer and select the Value tab.
2. Enter the following parameters:
• Delay Time — the timer’s time out value.
• Timer Reference — set to the device’s RefDes by default. You can enter any other
identifying string.

A.3.6.3 Timer TON Retention

This device is a TON timer with retention capabilities, for ladder diagrams. Once continuity is
established, the timer starts. If continuity is broken, the timer retains the accumulated time and
will continue from this time when continuity is re-established, until time out. Once timed out,
the timer will reset if continuity is broken, and will start accumulated time at zero.

A-32

Electronics Workbench

Ladder Diagram Parts
 To set the parameters for this device:
1. Double-click on the timer and select the Value tab.
2. Enter the following parameters:
• Delay Time — the timer’s time out value.
• Timer Reference — set to the device’s RefDes by default. You can enter any other
identifying string.

A.3.6.4 Timer TON Retention Reset

This device is a TON timer with retention and reset capabilities, for ladder diagrams. Once
continuity is established, the timer starts. If continuity is broken, the timer retains the
accumulated time and will continue from this time when continuity is re-established, until
time out. Once timed out, the timer will reset automatically if continuity is removed. This
device can be reset by a reset coil at any time before time out.
 To set the parameters for this device:
1. Double-click on the timer and select the Value tab.
2. Enter the following parameters:
• Delay Time — the timer’s time out value.
• Timer Reference — set to the device’s RefDes by default. You can enter any other
identifying string.

A.3.6.5 Timer TON Retention Hold Reset
This device is a TON timer with retention, hold and reset capabilities, for ladder diagrams.
Once continuity is established, the timer starts. If continuity is broken, the timer retains the
accumulated time and will continue from this time when continuity is re-established, until
time out. Once timed out, the timer will not reset automatically when continuity is removed.
This device can be reset by a reset coil at any time.
 To set the parameters for this device:
1. Double-click on the timer and select the Value tab.
2. Enter the following parameters:
• Delay Time — the timer’s time out value.
• Timer Reference — set to the device’s RefDes by default. You can enter any other
identifying string.

Multisim 9 for Educators

A-33

A.3.7 Ladder Output Coils
A.3.7.1 Output Coil
This device is an output coil for ladder diagrams.
 To set the parameters for this device:
1. Double-click on the output coil and select the Value tab.
2. Enter the address for the output module associated with this device in the Output Module
Base Address field.
3. Enter the number of the output on the output module that this device will drive in the
Output Number field.

Output Number
Output Module Base Address

A.3.7.2 Output Coil Negated
This device is a negated output coil for ladder diagrams.
 To set the parameters for this device:
1. Double-click on the output coil and select the Value tab.
2. Enter the address for the output module associated with this device in the Output Module
Base Address field.
3. Enter the number of the output on the output module that this device will drive in the
Output Number field.

Output Number
Output Module Base Address

A-34

Electronics Workbench

Miscellaneous Peripherals

A.4

Miscellaneous Peripherals

A.4.1 Holding Tank

This device is a liquid holding tank for use in ladder diagrams.
 To set the parameters for this device:
1. Double-click on the relay coil and select the Value tab.
2. Set the following parameters as desired:
• Tank Volume (litres) — capacity of the tank in litres.
• Level Detector Set Point (litres) — the level of the SP (set point) marker (see above
screen capture).
• Maximum Pump Flow Rate (litres/second) — the maximum speed at which the liquid is
pumped into the holding tank. If the Flow pin of the holding tank (see above screen
capture) is unconnected, the liquid only flows at this speed.
• Flow Rate Full Scale Voltage — if the Flow pin of the holding tank is connected, this is
the voltage required at the Flow pin to make the liquid move at the maximum speed set
in the Maximum Pump Flow Rate field. For example, if you enter 5 V in this field, and
then apply 5 V to the Flow pin, the liquid will flow at 1 litre/second if the value in the
Maximum Pump Flow Rate field is 1. If you apply 2.5 V to the Flow pin, the liquid will
flow at half that speed (0.5 litre/second).
• Sensor Full Scale Voltage — the sensor voltage that equates to a full tank. As the tank
fills, the voltage shown in the Sensor field of the holding tank (see above screen
capture) increases.
Note For an example of this component in a complete circuit, refer to“4.4.1 Holding Tank”
on page 4-7.

Multisim 9 for Educators

A-35

A.4.2 Conveyor Belt

Sensor 1

Sensor 3

Sensor 2

This device is a conveyor belt for use in ladder diagrams.
 To set the parameters for this device:
1. Double-click on the relay coil and select the Value tab.
2. Set the following parameters as desired:
• Belt Length (meters) — the length of the conveyor belt in meters.
• Max. Belt Speed (meters/sec) — the maximum speed the belt moves. If the Speed pin of
the conveyor belt (see above screen capture) is unconnected, the belt only moves at
this speed.
• Speed Control Full Scale Voltage — if the Speed pin of the conveyor belt is connected,
this is the voltage required at the Speed pin to make the belt move at the maximum
speed set in the Max. Belt Speed field. For example, if you enter 5 V in this field, and
then apply 5 V to the Speed pin, the belt will move at 0.5 meters/second if the value in
the Max. Belt Speed field is 0.5. If you apply 2.5 V to the Speed pin, the belt will move
at half that speed (0.25 meters per second).
• Sensor 1 Position (meters) — the position of Sensor 1 from the left edge of the belt.
• Sensor 2 Position (meters) — the position of Sensor 2 from the left edge of the belt.
• Sensor 3 Position (meters) — the positionof Sensor 3 from the left edge of the belt. Do
not set greater than the Belt Length value.
Note For an example of this component in a complete circuit, see “4.4.2 Conveyor Belt” on
page 4-12.

A-36

Electronics Workbench

Miscellaneous Peripherals

A.4.3 Traffic Light

These pins drive the
lights on the left side
of the traffic light.
These pins drive the lights on the
right side of the traffic light.

This component has no parameters that need to be set up in the Value tab.
Note For an example of this component in a complete circuit, see “4.4.3 Traffic Light” on
page 4-17.

A.4.4 Single Traffic Light

This device is similar to the double traffic light (see “A.4.3 Traffic Light” on page A-37)
except that it contains a single bank of lights.

Multisim 9 for Educators

A-37

A.5

Virtual ELVIS Components
Virtual ELVIS components are special devices that are ony accessible from special rows on
the Virtual ELVIS prototyping schematic.

A.5.1 NI ELVIS Function Generator
This component emulates the behavior of a function generator, and is accessed from the left
row of the Virtual ELVIS prototyping schematic.

 To set the parameters for the function generator:
1. Double-click on “Function Generator” in the Virtual ELVIS schematic. The properties
dialog for the NI ELVIS Function Generator appears.
2. Click on the Value tab and set the following parameters as desired:
•
•
•
•

Waveform — choose 1 for a sine wave; 2 for a triangle wave; 3 for a square wave.
Frequency — the frequency and unit of measure of the function generator output.
Amplitude — the peak voltage and its unit of measure.
Voltage Offset — controls the DC level about which the alternating signal varies. An

offset of 0 positions the waveform along the oscilloscope's x-axis (provided its Y POS
setting is O). A positive value shifts the DC level upward, while a negative value shifts
it downward. Offset uses the units set for Amplitude.
• Duty Cycle — the ratio of on-period to off-period. A sine wave is not affected by this
setting.
Note See also, “3.2 The Virtual ELVIS Schematic” on page 3-2.

A-38

Electronics Workbench

Virtual ELVIS Components

A.5.2 NI ELVIS Power Supply
This component is accessed from the left row of the Virtual ELVIS prototyping schematic.

 To set the parameters for this device:
1. Double-click on “Variable Power Supplies”. The properties dialog box for the NI ELVIS
power supply appears.
2. Click on the Value tab and set the following parameters as desired:
• Positive Supply Control Key — select a key to press on the keyboard to increase or
decrease the output of the positive variable power supply by the amount set in the
Increment Value field. Maximum output is +12 VDC.
• Negative Supply Control Key — select a key to press on the keyboard to increase or
decrease the output of the negative variable power supply by the amount set in the
Increment Value field. Maximum output is -12 VDC.
• Increment Value — the size of steps by which the power supply’s output is increased or
decreased as the control key is pressed on the keyboard.
Note See also, “3.2 The Virtual ELVIS Schematic” on page 3-2.

Multisim 9 for Educators

A-39

Index
Numerics
3D Components
555 timer A-15
74LS160N counter A-17
BJT A-16
capacitor A-16
DC motor A-19
diode A-17
inductor A-18
LED A-18
MOSFET A-19
opamp A-20
potentiometer A-20
resistor A-21
shift register A-21
3D Components toolbar A-22

A
assigning faults to components 1-2
Auto Fault option 1-3

B
Breadboard Netlist dialog box 2-12
Breadboard Settings 2-3

C
circuit restrictions
setting 1-9
components
assigning faults 1-2
Auto Fault option 1-3
Conveyor Belt A-36
Count Off A-27
Count Off Hold A-28
Count Off Reset A-28
Count Off Up Down A-29
Count On A-29
Count On Hold A-30

Multisim 9 for Educators

Count On Reset A-30
Count On Up Down A-31

F
faults, assigning to components 1-2

G
global restrictions
passwords 1-12
setting 1-4

I
Input Module A-23

L
Liquid Holding Tank A-35

N
Negated Output Coil A-34
Negated Relay Coil A-24
NI ELVIS Function Generator A-38
NI ELVIS Power Supply A-39
Normally Closed Input Contact A-25
Normally Closed Relay Contact A-26
Normally Open Input Contact A-26
Normally Open Relay Contact A-27

O
Output Coil A-34
Output Module A-23

P
passwords, creating/changing 1-12
Pulsed Relay Coil A-25

R
Rated Components

i

555 timer A-1
BJT A-2
capacitor A-3
DC motor A-6
diode A-4
fuse A-4
inductor A-5
LED A-6
opamp A-8
Photodiode A-9
Phototransistor A-9
potentiometer A-10
pullup A-11
relay A-7
transformer A-12
variable capacitor A-13
variable inductor A-14
Rated Virtual Components toolbar A-15
Relay Coil A-24
Reset Coil A-25
restrictions
about 1-4
setting circuit 1-9
setting global 1-4

3D prototyping board 3-8
ammeter 3-5
function generator 3-6
IV Analyzer 3-5
oscilloscope 3-3
overview 3-1
power supplies 3-6
prototyping board LEDs 3-7
schematic 3-2
Volt/Ohmmeter 3-5

S
Set Coil A-24
setting circuit restrictions 1-9
setting global restrictions 1-4
Simplified Version 1-4

T
TOFF timer A-31
TON timer A-32
TON timer with retention A-32
TON timer with retention and reset A-33
TON timer with retention, hold and reset A-33
Traffic Light A-37

V
Virtual ELVIS

ii

Electronics Workbench

Technical Support and Professional Services
Visit the following sections of the National Instruments Web site at
ni.com for technical support and professional services:
•

Support—Online technical support resources at ni.com/support
include the following:
–

Self-Help Resources—For answers and solutions, visit the
award-winning National Instruments Web site for software drivers
and updates, a searchable KnowledgeBase, product manuals,
step-by-step troubleshooting wizards, thousands of example
programs, tutorials, application notes, instrument drivers, and
so on.

–

Free Technical Support—All registered users receive free Basic
Service, which includes access to hundreds of Application
Engineers worldwide in the NI Developer Exchange at
ni.com/exchange. National Instruments Application Engineers
make sure every question receives an answer.
For information about other technical support options in your
area, visit ni.com/services or contact your local office at
ni.com/contact.

•

Training and Certification—Visit ni.com/training for
self-paced training, eLearning virtual classrooms, interactive CDs,
and Certification program information. You also can register for
instructor-led, hands-on courses at locations around the world.

•

System Integration—If you have time constraints, limited in-house
technical resources, or other project challenges, National Instruments
Alliance Partner members can help. To learn more, call your local
NI office or visit ni.com/alliance.

If you searched ni.com and could not find the answers you need, contact
your local office or NI corporate headquarters. Phone numbers for our
worldwide offices are listed at the front of this manual. You also can visit
the Worldwide Offices section of ni.com/niglobal to access the branch
office Web sites, which provide up-to-date contact information, support
phone numbers, email addresses, and current events.

