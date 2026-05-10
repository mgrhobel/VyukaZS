---
title: "exceptions displaying.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/MIT resources/TODOs/exceptions displaying.doc"
date: 2010-03-07
type: DOC
---

done

\

MessageBox with excpetion has been already concerned in MITToollkit
application. There are two necessary contructions to work this
MessageBox. Application must be run in EventDispatchingThread and
setBatch muset be set to default value -\> false.

\

For changing cursor was created new private class
at.co.systema.gf.i18n.internal.view.CursorController - so control for
the hourglass cursor is contained in one place. For this has been
changed the implementation of ActionListener doActionButton in
AvstractResourceBundleExportImportTab. The modified ActionListener takes
care of cursor control amd also performs the same action processing as
the original ActionListener.

\

**\-\-\-\-\-\-\-\-- 25.6.2009 14:02:02 by Veronika Hnizdilova:**

When an exception arise during export/import in MITToolkit application,
let user know with some dialog. Export/import should be able to start
again. Loo

\

\
