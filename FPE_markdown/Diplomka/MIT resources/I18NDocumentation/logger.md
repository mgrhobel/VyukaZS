---
title: "logger.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/MIT resources/I18NDocumentation/logger.doc"
date: 2010-03-07
type: DOC
---

^(1)^[**?**]{.underline} [**Programmer Guide - Overview:**]{.underline}
[**I18N-Programming Guideline**]{.underline}

\

^(2)^ Programmer Guide Use Case: Schaffen einer I18N-Testumgebung

^(3)^ Programmer Guide Use Case: Texte in ResourceBundles
definieren/abholen

**Description:**

This is the collection document for I18N MPA programming guidelines.

**Details:**

\

**Using of MessageBundles**

Every \"coded\" texts (texts of graphical components in views) shown to
the user should come from MessageBundle property files.

new JButton(\"someText\"); // incorrect

new JButton(MpaResourceBundle.getString(MY_RB_TEXT_KEY)); // correct

\

More about using of MessageBundles see ^(4)^*[Documentation 3682:
Define/Get Texts in/from ResourceBundles]{.underline}*

\

\

**Special Case Service**

It is not meaningful to put the texts into MessageBundles, otherwise we
will not be able to support our customers, because we will be not able
to understand the messages.

The best solution would be to implement all text outputs in english. We
assume that the customer admins understand basic english.

\

\

\

**Showing User Messages on Screen**

\

**Using of MsgVisualizer**

Information, warning and error messages to be shown to the user, should
be implemented by means of **ui.message.MsgVisualizer** or in case of
exception by means of **gf.exception.ExceptionManager** (^(5)^) .

Both these help classes support using of MessageBundle files. General
hints for using of MessageBundles see^(6)^*[Documentation 3682:
Define/Get Texts in/from ResourceBundles]{.underline}*.

\

Note for using of **package specific MessageBuild.proerties, resp.
ExceptionBundle properties**.

\

If somebody uses such package specific bundles, he should use right
methods of these helper classes with information about package name.

Bad solution: At first get the translated value from ResourceBundle and
then call MsgVisualizer::\...WithoutTranslation().

\

If the MsgVisualizer looks for the key and find the prhase, not only
found text will be logged, but the MessageBundle and Lookup-Key will be
logged too.

So the developer should be able to find out which messages were shown on
customer site.

\

\

**Error Messages (Exceptions) on the Screen**

\

Exceptions should not be localized. They should come in english into the
logfile. If some dialog in one GUI programm should be shown, so starting
with change ^(7)^ we can use the ExceptionMgr to do it. It has 2 areas
to be shown:

1\. One localized error message which could be hopefully understood by
user

2.) By means of click on \"Detail\" button the exception stack could be
shown. This one is and stay unlocalized.

\

**Logging Output**

\

Logging output should be not localized, as already mentioned. It should
be expressed in plain english. If you use for logging the same string as
for MessageBundle entry, make please the english texts to be constand.
Most suitable solution would be to use such classes as DocDefs, DLDefs
or WFLConstands. To ensure that these classes stay clearly arrange, you
can use some inner Interface (e.g. LogMsgs), which constains only such
constants.

\

**see also:**

Testing Guide, if the localized texts are used anywhere. see ^(8)^

\

\

\
\

\
\

\
\
