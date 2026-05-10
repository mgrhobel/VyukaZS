---
title: "logger.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/MIT resources/TODOs/logger.doc"
date: 2010-03-07
type: DOC
---

Done

\

\'Set FIltered Level\' is not stored into MITProperties because change
of level could be done in configuration file.

msg logger (MSGVisualizer) is controlled by checkbox -\> logging is
either allowed or not allowed. In order it is its level se to TRACE.

\

\

**\-\-\-\-\-\-\-\-- 13.7.2009 15:39:24 by Jiri Kiml:**

\

Original verison done here: ^(1)^*[Todo 45967: MIT - log viewer
tab]{.underline}*

\

\

1\. if level of logger for at.co.systema.gf.i18n is set to WARN (default
settings) then no messages are displayed even if I set filtering to
TRACE.

I understand why (no messages are sent to our appender), but I think it
will be unclear to user. We should add posibility to set default level

for -at.co.systema.gf.i18n logger here too. So add similar combobox like
we have for \"Set Filtered Level\" to be able set at.co.systema.gf.i18n
logger

level here. This setting IS NOT STORED to mit.properties.

\

2\. I think that all status bar messages should be displayed in logger
view tab too. Add checkbox (something like \"display status bar
messages\")

to logger view tab and if it is checked then display status messages in
logger view text area too.

Maybe it is so simple like adding our appender (LogEntryFinderAppender
in LogViewerTab) to logger used in GuiMsgVisualizer.

\
