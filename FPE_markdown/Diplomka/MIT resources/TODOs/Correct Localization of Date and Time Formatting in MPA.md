---
title: "Correct Localization of Date and Time Formatting in MPA.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/MIT resources/TODOs/Correct Localization of Date and Time Formatting in MPA.doc"
date: 2010-03-11
type: DOC
---

\

**\-\-\-\-\-\-\-\-- 27.3.2009 14:28:22 by Josef Hobel:**

partly done with change 264491

\

**\-\-\-\-\-\-\-\-- 11.3.2009 18:45:19 by Josef Hobel:**

The code snippet from **at.co.systema.app.view.TerminView** I found in
**at.co.systema.app.view.TerminViewAttrSupport**.

\

**\-\-\-\-\-\-\-\-- 09/03/2009 10:53:00 by Christoph Bimminger:**

My remarks, as sent to Igor by E-Mail:

\

**at.co.systema.ui.l2control.calendar2.L2Calendar2**

 

    private String dataStringFormat = \"dd. MM. yyyy\";

 

\@Igor

This has to be consulted with Christoph Bimminger! 

 

//christoph1: the dataStringFormat is an alternative value
representation of the components. Values using the format may be
persisted e.g. in  the database. The value can be modified by
customizing (is part of component\'s BeanInfo); but the default value is
important when de-externalizing such a component. In my opinion, this
value can currently be canged safely anyway, because nobody uses this
feature as far as I know. Currently usages use data format Timestamp,
Date or GregorianCalendar, where the dataStringFormat is irrelevant. I
hope, there is no different usage in CDR projects or Labor. It would be
great if the date format is the same as used when saving any date/time
information into a String field on database, as converted by our

 

 

**at.co.systema.ui.l2control.calendar2.L2Calendar2Popup**

 

    private String dataStringFormat = \"dd.MM.yyyy\"; //für

 

\@Igor

This has to be consulted with Christoph Bimminger! 

 

//christoph1: exactly the same as in L2Calendar2.dataStringFormat! 

 

 

**at.co.systema.wfl.app.ProzessPlanner**

 

            SimpleDateFormat F_format;

            if (P_termin.isTimeDependent())

            {

                F_format = new SimpleDateFormat(\"dd.MMM.yyyy, HH.mm\");

            }

            else

            {

                F_format = new SimpleDateFormat(\"dd.MMM.yyyy\");

            }

 

\@Igor

This has to be consulted with Christoph Bimminger!

This Strings will be written into DB! So, no change is possible.

Analysis needed, in which form the dates will be displayed. Some code
changes maybe needed.

 

 //christoph1: used \_only\_ for PlanningNotificationCustomFunctionTask.
The string is used in the planning notification message, and can be
canged to any \"long\" date format. The date has to display Time with a
granularity of at least minutes in first case, and must not display any
time related information in second case.

 

\

This code I have found in rel_3.8.3.

I cannot find it so easy in the release 3.11. Please hlelp.

**Search for the missing code.**

**at.co.systema.app.view.TerminView**

 

            if (timeFormat == null)

            {

                String F_timePattern =
MpaResourceBundle.getStringIgnoreNullIgnoreTestMode(\"dateFormat.time\",
\"at.co.systema.app\");

                if (F_timePattern == null)

                {

                    logger.warn(\"did not find
at.co.systema.app.MessageBundle entry \'dateFormat.time\'. Using
fallback\...\");

                    F_timePattern = \"HH:mm\";

                }

               

                timeFormat = new SimpleDateFormat(F_timePattern);

            }

 

            if (longTimeFormat == null)

            {

                String F_longTimePattern =
MpaResourceBundle.getStringIgnoreNullIgnoreTestMode(\"dateFormat.dateTime\",
\"at.co.systema.app\");

                if (F_longTimePattern == null)

                {

                    logger.warn(\"did not find
at.co.systema.app.MessageBundle entry \'dateFormat.dateTime\'.\" +

                            \"Using fallback\...\");

                    F_longTimePattern = \"dd.MM.yyyy HH:mm\";

                }

               

                longTimeFormat = new
SimpleDateFormat(F_longTimePattern);

            }

 

Code changed here, find out where it is on 3.11!!!! 

 

//christoph1: Think this was moved to TerminViewMouseListener? The text
is used for the TerminView data, as displayed in the TerminView, or its
ToolTip. The representation can be changed, but should need only little
space - so it should not display the date-related info, only the time.
seconds are not needed here. It should e.g. depend on language settings,
if a 12h with AM/PM suffix or 24h time format is used.

 

\

**\-\-\-\-\-\-\-\-- 12.01.2009 23:09:06 by Igor Böhm:**

At first small introduction into right I18N date/time formatting:

\

[https://java.sun.com/docs/books/tutorial/i18n/format/dateintro.html]{.underline}

\

All examples in this introduction can be found in:

![](Correct%20Localization%20of%20Date%20and%20Time%20Formatting%20in%20MPA_html_1302c25b.png){#Image1
align="bottom" width="114" height="47" border="0"} \-\-\--\> (output)
![](Correct%20Localization%20of%20Date%20and%20Time%20Formatting%20in%20MPA_html_8249eb57.gif){#Image2
align="bottom" width="137" height="47" border="0"}

\

\

For weekdays and months names formatting see ^(1)^*[Todo 43133: Weekdays
and Month Names in MPA, correct Internationalization]{.underline}*.

\

Other related todo: ^(2)^*[Todo 43180: Localization of
MultiPatternDateFormatPatterns class]{.underline}*

\

\

**New Interface/Implementation for class DefaultSettings should be used
by correct localization of date where possible, see**

^**(3)**^*[**Todo 43222: Correct Localization of class DefaultSettings
(Refactorization)**]{.underline}*

That means, mostly the **predefined formats** should be used. Use
**customizing formats** only in exceptional cases.

\

\

**Using Predefined Formats (see** ^**(4)**^*[Todo 43222: Correct
Localization of class DefaultSettings (Refactorization)]{.underline}*
**for correct implementation in MPA)**

\

**DateFormat class allows you to format dates and times with predefined
styles in a locale sensitive manner**.

\

\

[**General Considerations**]{.underline}

\

[**Dates**]{.underline}

\

Formatting dates with the DateFormat class is a two-step process. First,
you create a formatter with the getDateInstance method. Second, you
invoke the format method, which returns a String containing the
formatted date. The following example formats today\'s date by calling
these two methods:

\

Date today;

String dateOut;

DateFormat dateFormatter;

\

dateFormatter = DateFormat.getDateInstance(DateFormat.DEFAULT,

currentLocale);

// this call is compatible with

// dateFormatter = DateFormat.getDateInstance()

// which works for Locale.getDefault(). This is set in MPA always
correct to currently chosen language.

\

today = new Date();

**dateOut = dateFormatter.format(today);**

\

System.out.println(\"Locale: \" + currentLocale.toString() + \" \"

\+ currentLocale.getDisplayName() + \" \" + dateOut);

\

The output generated by this code see below. Notice that the formats of
the dates vary with Locale. Since DateFormat is Locale sensitive, it
takes care of the formatting details for each Locale.

\

Display Default Date

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

Locale: de_DE Deutsch (Deutschland) 17.12.2008

Locale: de_AT Deutsch (Österreich) 17.12.2008

Locale: en_US Englisch (Vereinigte Staaten von Amerika) Dec 17, 2008

Locale: en_GB Englisch (Vereinigtes Königreich) 17-Dec-2008

Locale: fr_FR Französisch (Frankreich) 17 déc. 2008

Locale: cs_CZ Tschechisch (Tschechische Republik) 17.12.2008

Locale: sk_SK Slowakisch (Slowakei) 17.12.2008

Locale: sr_RS Serbisch (Serbien) 17.12.2008.

Locale: hr_HR Kroatisch (Kroatien) 2008.12.176

\

The preceding code example specified the DEFAULT formatting style. The
DEFAULT style is just one of the predefined formatting styles that the
DateFormat class provides, as follows:

\

**\* DEFAULT**

\* SHORT

\* MEDIUM

\* LONG

\* FULL

\

**DateFormat class uses MEDIUM style as DEFAULT style.**

\

The following table shows how dates are formatted for each style for
some locales:

\

DateFormatter

\-\-\-\-\-\-\-\-\-\-\-\--

\

Locale: de_DE Deutsch (Deutschland)

\

DEFAULT: (dd.MM.yyyy) 16.12.2008

SHORT: (dd.MM.yy) 16.12.08

MEDIUM: (dd.MM.yyyy) 16.12.2008

LONG: (d. MMMM yyyy) 16. Dezember 2008

FULL: (EEEE, d. MMMM yyyy) Dienstag, 16. Dezember 2008

\

Locale: de_AT Deutsch (Österreich)

\

DEFAULT: (dd.MM.yyyy) 17.12.2008

SHORT: (dd.MM.yy) 17.12.08

MEDIUM: (dd.MM.yyyy) 17.12.2008

LONG: (dd. MMMM yyyy) 17. Dezember 2008

FULL: (EEEE, dd. MMMM yyyy) Mittwoch, 17. Dezember 2008

\

Locale: en_US Englisch (Vereinigte Staaten von Amerika)

\

DEFAULT: (MMM d, yyyy) Dec 16, 2008

SHORT: (M/d/yy) 12/16/08

MEDIUM: (MMM d, yyyy) Dec 16, 2008

LONG: (MMMM d, yyyy) December 16, 2008

FULL: (EEEE, MMMM d, yyyy) Tuesday, December 16, 2008

\

Locale: en_GB Englisch (Vereinigtes Königreich)

\

DEFAULT: (dd-MMM-yyyy) 16-Dec-2008

SHORT: (dd/MM/yy) 16/12/08

MEDIUM: (dd-MMM-yyyy) 16-Dec-2008

LONG: (dd MMMM yyyy) 16 December 2008

FULL: (EEEE, d MMMM yyyy) Tuesday, 16 December 2008

\

Locale: cs_CZ Tschechisch (Tschechische Republik)

\

DEFAULT: (d.M.yyyy) 16.12.2008

SHORT: (d.M.yy) 16.12.08

MEDIUM: (d.M.yyyy) 16.12.2008

LONG: (d. MMMM yyyy) 16. prosinec 2008

FULL: (EEEE, d. MMMM yyyy) Úterý, 16. prosinec 2008

\

Locale: hr_HR Kroatisch (Kroatien)

\

DEFAULT: (yyyy.MM.dd) 2008.12.16

SHORT: (yyyy.MM.dd) 2008.12.16

MEDIUM: (yyyy.MM.dd) 2008.12.16

LONG: (yyyy. MMMM dd) 2008. prosinac 16

FULL: (yyyy. MMMM dd) 2008. prosinac 16

\

[**Times**]{.underline}

\

Date objects represent both dates and times. Formatting times with the
DateFormat class is similar to formatting dates, except that you create
the formatter with the getTimeInstance method, as follows:

\

DateFormat timeFormatter =

**DateFormat.getTimeInstance(DateFormat.DEFAULT,**

**currentLocale);**

\

The table that follows shows the various predefined format styles for
some locales:

\

TimeFormatter

\-\-\-\-\-\-\-\-\-\-\-\--

\

Locale: de_DE Deutsch (Deutschland)

\

DEFAULT: (HH:mm:ss) 13:13:20

SHORT: (HH:mm) 13:13

MEDIUM: (HH:mm:ss) 13:13:20

LONG: (HH:mm:ss z) 13:13:20 CET

FULL: (H.mm\' Uhr \'z) 13.13 Uhr CET

\

Locale: de_AT Deutsch (Österreich)

\

DEFAULT: (HH:mm:ss) 15:53:37

SHORT: (HH:mm) 15:53

MEDIUM: (HH:mm:ss) 15:53:37

LONG: (HH:mm:ss z) 15:53:37 CET

FULL: (HH:mm\' Uhr \'z) 15:53 Uhr CET

\

Locale: en_US Englisch (Vereinigte Staaten von Amerika)

\

DEFAULT: (h:mm:ss a) 1:13:20 PM

SHORT: (h:mm a) 1:13 PM

MEDIUM: (h:mm:ss a) 1:13:20 PM

LONG: (h:mm:ss a z) 1:13:20 PM CET

FULL: (h:mm:ss a z) 1:13:20 PM CET

\

Locale: en_GB Englisch (Vereinigtes Königreich)

\

DEFAULT: (HH:mm:ss) 13:13:20

SHORT: (HH:mm) 13:13

MEDIUM: (HH:mm:ss) 13:13:20

LONG: (HH:mm:ss z) 13:13:20 CET

FULL: (HH:mm:ss \'o\'\'clock\' z) 13:13:20 o\'clock CET

\

Locale: cs_CZ Tschechisch (Tschechische Republik)

\

DEFAULT: (H:mm:ss) 13:13:20

SHORT: (H:mm) 13:13

MEDIUM: (H:mm:ss) 13:13:20

LONG: (H:mm:ss z) 13:13:20 CET

FULL: (H:mm:ss z) 13:13:20 CET

\

Locale: sr_RS Serbisch (Serbien)

\

DEFAULT: (HH.mm.ss) 13.13.20

SHORT: (HH.mm) 13.13

MEDIUM: (HH.mm.ss) 13.13.20

LONG: (HH.mm.ss z) 13.13.20 CET

FULL: (HH.mm.ss z) 13.13.20 CET

\

\

[**Both Dates and Times**]{.underline}

\

To display a date and time in the same String, create the formatter with
the getDateTimeInstance method. The first parameter is the date style,
and the second is the time style. The third parameter is the Locale .
Here\'s a quick example:

\

**DateFormat formatter =**

**DateFormat.getDateTimeInstance(DateFormat.LONG,**

**DateFormat.LONG,**

**currentLocale);**

\

The table that follows shows the various predefined format styles for
some locales:

\

DateTimeFormatter

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

Locale: de_DE (Deutsch (Deutschland))

\

DEFAULT: (dd.MM.yyyy HH:mm:ss) 16.12.2008 13:13:20

SHORT: (dd.MM.yy HH:mm) 16.12.08 13:13

MEDIUM: (dd.MM.yyyy HH:mm:ss) 16.12.2008 13:13:20

LONG: (d. MMMM yyyy HH:mm:ss z) 16. Dezember 2008 13:13:20 CET

FULL: (EEEE, d. MMMM yyyy H.mm\' Uhr \'z) Dienstag, 16. Dezember 2008
13.13 Uhr CET

\

Locale: de_AT (Deutsch (Österreich))

\

DEFAULT: (dd.MM.yyyy HH:mm:ss) 17.12.2008 15:53:37

SHORT: (dd.MM.yy HH:mm) 17.12.08 15:53

MEDIUM: (dd.MM.yyyy HH:mm:ss) 17.12.2008 15:53:37

LONG: (dd. MMMM yyyy HH:mm:ss z) 17. Dezember 2008 15:53:37 CET

FULL: (EEEE, dd. MMMM yyyy HH:mm\' Uhr \'z) Mittwoch, 17. Dezember 2008
15:53 Uhr CET

\

Locale: en_US (Englisch (Vereinigte Staaten von Amerika))

\

DEFAULT: (MMM d, yyyy h:mm:ss a) Dec 16, 2008 1:13:20 PM

SHORT: (M/d/yy h:mm a) 12/16/08 1:13 PM

MEDIUM: (MMM d, yyyy h:mm:ss a) Dec 16, 2008 1:13:20 PM

LONG: (MMMM d, yyyy h:mm:ss a z) December 16, 2008 1:13:20 PM CET

FULL: (EEEE, MMMM d, yyyy h:mm:ss a z) Tuesday, December 16, 2008
1:13:20 PM CET

\

Locale: en_GB (Englisch (Vereinigtes Königreich))

\

DEFAULT: (dd-MMM-yyyy HH:mm:ss) 16-Dec-2008 13:13:20

SHORT: (dd/MM/yy HH:mm) 16/12/08 13:13

MEDIUM: (dd-MMM-yyyy HH:mm:ss) 16-Dec-2008 13:13:20

LONG: (dd MMMM yyyy HH:mm:ss z) 16 December 2008 13:13:20 CET

FULL: (EEEE, d MMMM yyyy HH:mm:ss \'o\'\'clock\' z) Tuesday, 16 December
2008 13:13:20 o\'clock CET

\

Locale: cs_CZ (Tschechisch (Tschechische Republik))

\

DEFAULT: (d.M.yyyy H:mm:ss) 16.12.2008 13:13:20

SHORT: (d.M.yy H:mm) 16.12.08 13:13

MEDIUM: (d.M.yyyy H:mm:ss) 16.12.2008 13:13:20

LONG: (d. MMMM yyyy H:mm:ss z) 16. prosinec 2008 13:13:20 CET

FULL: (EEEE, d. MMMM yyyy H:mm:ss z) Úterý, 16. prosinec 2008 13:13:20
CET

\

Locale: sr_RS (Serbisch (Serbien))

\

DEFAULT: (dd.MM.yyyy. HH.mm.ss) 16.12.2008. 13.13.20

SHORT: (d.M.yy. HH.mm) 16.12.08. 13.13

MEDIUM: (dd.MM.yyyy. HH.mm.ss) 16.12.2008. 13.13.20

LONG: (dd.MM.yyyy. HH.mm.ss z) 16.12.2008. 13.13.20 CET

FULL: (EEEE, dd.MMMM.yyyy. HH.mm.ss z) ??????, 16.????????.2008.
13.13.20 CET

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\

**The recommended way would be to use** **DateFormat.DEFAULT, which
correspond in GERMAN well known formatting with** **dd.MM.yyyy** **and**
**HH:mm:ss.**

\

**Thus for right Date formatting following code should be used in
standard Java programs**

dateFormatter = DateFormat.getDateInstance() // this is Formatter for
default (current) locale and Default Format, which is equal to MEDIUM

\

today = new Date(); // only Example of some date

**dateOut = dateFormatter.format(today);**

\

\

**The same for formatting with Time and DateTime Formatter.**

\

**NO DEPENDENCY ON SOME HARD CODED (OR SOFT CODED IN MESSAGE BUNDLES)
formats like \"dd.MM.yyyy HH.mm.ss\" should be used in MPA.**

\

**There could be only some exceptions in Calendar GUI (App Book etc.),
where maybe some \"place problems\" could arise.**

**Second \"legal\" situation would be some export/import modules they
would have to export date/time values in some predefined format (see
AGFADefs.java,**

**AbstractFileImportProcessor and many others).**

\

\

**Again, in MPA should be used the default formatting interface of class
DefaultSettings, see** ^**(5)**^*[**Todo 43222: Correct Localization of
class DefaultSettings (Refactorization).**]{.underline}*

\

\

**Following \"fix\" formats have been found in MPA code:**

\

HH:mm:ss.SSS \--\> corresponds to
**DefaultSettings.getDefaultTimeFormatWithMillis()**

dd.MMM yyyy HH:mm:ss.SSS \--\> corresponds to
**DefaultSettings.getDefaultTimestampFormatWithMillis()**

dd.MM.yyyy-HH:mm:ss.SS \--\> should be replaced by
**DefaultSettings.getDefaultTimestampFormatWithHundredths()**

HH:mm:ss.SS \--\> should be replaced by
**DefaultSettings.getDefaultTimeFormatWithHundredths()**

\

\

For following formats some decision must be made, if some predefined
format could be used.

Only as \"last alternative\" the SimpleDateFormat should be used.

\

MM.dd HH:mm:ss.SSS (TimeMetaField, could be this parametrized or have it
to be fixed?)

EE d MMM yyyy HH:mm

dd. MM. yyyy / HH:mm

EEE dd.MM.yyyy

EEE, d MMM yyyy HH:mm:ss

dd.MMM.yyyy

dd.MMM.yyyy, HH.mm

\

\

**Following code \"snippets\" use function CalendarUtils.date2String
(direct formatting too)**

\

**At first general remark:**

**at.co.systema.gf.util.CalendarUtils.date2String method should not be
generally used for standard output formatting**

**of date/times (exceptions from this rule again as already above
mentioned, like export/import etc.)**

\

**public static String date2String(java.util.Date P_date, String
Ps_dateFormat)**

**{**

String Fs_ret;

**java.text.DateFormat F_dtf = new
java.text.SimpleDateFormat(Ps_dateFormat);**

F_dtf.setTimeZone(TimeZone.getDefault());

Fs_ret = F_dtf.format(P_date);

return Fs_ret;

**}**

\

\

**Here the list of classes/methods using this method. All of them can be
easily replaced**

**with standard DateFormat.getDateInstance().format() method, or better
with DefaultSettings methods (see** ^**(6)**^*[Todo 43222: Correct
Localization of class DefaultSettings
(Refactorization)]{.underline}*[**)**]{.underline}

\

**done**

**at.co.systema.dl.view.DLInvalidTemplateKeyWorkArea**

\

private void \_checkCatalog (java.sql.Date P_date, UDIRecord Pr_catalog,
String Ps_msgKey)

{

if(Pr_catalog == null)

{

String Fs_date = CalendarUtils.date2String(P_date, \"dd.MM.yyyy\");

String Fs_msg = MpaResourceBundle.getString(Ps_msgKey,

new Object\[\]{Fs_date}, \"at.co.systema.dl\");

\

Assert.FAIL (Fs_msg);

}

}

\

**done**

**at.co.systema.dl.DiagnoseKatalog**

if(Fr_katalog == null)

{

String Fs_date = CalendarUtils.2String(P_datum, \"dd.MM.yyyy\");

String Fs_msg =
MpaResourceBundle.getString(\"DiagnoseKatalog.ungueltig\",

new Object\[\]{Fs_date}, \"at.co.systema.dl\");

\

**done**

**at.co.systema.dl.LeistungsKatalog**

private static void \_error (java.sql.Date P_datum, String Ps_msgKey,
int Pi_size)

{

String Fs_date = CalendarUtils.date2String(P_datum, \"dd.MM.yyyy\");

String Fs_msg = MpaResourceBundle.getString(Ps_msgKey,

new Object\[\]{Fs_date, new Integer (Pi_size)}, \"at.co.systema.dl\");

\

\

**done**

**at.co.systema.sap.pat.view.SAPAufnahmeVVValidator**

\

String Fs_date = CalendarUtils.date2String(F_date, \"dd.MM.yyyy\");

String Fs_gVon = CalendarUtils.date2String(F_gVon, \"dd.MM.yyyy\");

\

if (Fr_vv.getField(\"selbstzahler\").getValue().equals(\"X\"))

{

Fs_vvBez = \"SZ\";

\

Fs_msg = MpaResourceBundle.getString(\"VV.SZ.GBisVorGVon\",

new Object\[\]{Fs_vvBez, Fs_gVon, Fs_date},\"at.co.systema.sap\");

\

\

\

\

**Following code \"snippets\" of \"hardwired\" SimpleDateFormat() in
MPA**

\

\

**done**

**at.co.systema.wfl.WFLUtilities.java:**

private static SimpleDateFormat dateFormat = new
SimpleDateFormat(\"HH:mm:ss.SSS\");

\

public static String getCurrentTimeString()

{

return dateFormat.format(new Date(System.currentTimeMillis()));

}

\

or

\

**done**

**at.co.systema.gf.schedule.Period.java:**

public String toString()

{

java.text.SimpleDateFormat F_df = new
java.text.SimpleDateFormat(\"dd.MMM yyyy HH:mm:ss.SSS\");

\

\

**skipped**

**at.co.systema.wfl.DeploymentInitializer**

F_cva = new SimpleColumnViewAttr(Fs_tableName, \"zeit\",
java.sql.Date.class, \"Zeit\", 15);

F_cva.setOutputFormatierung(\"MM.dd HH:mm:ss.SSS\"); -\> skip this in
all DeploymentInitalizers in case of OutputFormatierung - it will be
solved by special transformation table during i18n export-import

P_helper.addColumnViewAttr(F_cva);

\

**done**

**at.co.systema.wfl.svr.LogginSupport**

if (dateFormat == null)

{

dateFormat = new SimpleDateFormat(\"HH:mm:ss.SSS\");

}

\

**done**

**at.co.systema.gf.schedule.SplitPeriod**

\

public String toString()

{

java.text.SimpleDateFormat F_df = new
java.text.SimpleDateFormat(\"dd.MMM yyyy HH:mm:ss.SSS\");

return getClass().getName() + \" \[Start = \" + F_df.format(start) + \",
End = \"

\+ F_df.format(end) + \", interval = \" + interval + \", splitInterval =
\"

\+ secureInterval + \"\]\";

}

\

**Igor takes care about it.**

**at.co.systema.wfl.TimeMetaField**

\

protected DateFormat getDateFormat()

{

if (dateFormat == null)

{

dateFormat = new SimpleDateFormat(\"MM.dd HH:mm:ss.SSS\");

}

\

return dateFormat;

\

**done**

**at..co.systema.app.view.AppointmentProposalWorkArea**

\

private DateFormat getDateFormat()

{

if (dateFormat == null)

{

dateFormat = new SimpleDateFormat(\"EE d MMM yyyy HH:mm\",
Locale.getDefault());

}

\

return dateFormat;

}

\

**done**

**at.co.systema.bm.BMBettMgrImpl**

\

**// Misusing of SimpleDateFormat. Here should be used standard Calender
functions**

**// because somebody wants only generate Date instance with 1.1.2000
and 31.12.2099**

\

**Good example:**

**private static final Date MIN_DATE = SqlDateFactory.create (1,
Calendar.JANUARY, 1);**

**private static final Date MAX_DATE = SqlDateFactory.create (9999,
Calendar.DECEMBER, 31);**

\

**\@Please correct it in this way**

\

DateFormat F_format = new SimpleDateFormat(\"ddMMyyyy\");

\

Date F_validFrom = new Date(F_format.parse(\"01012000\").getTime());

F_bett.getUDIRecord().setFieldValue(\"gueltigVon\", F_validFrom);

\

Date F_validTo = new Date(F_format.parse(\"31122099\").getTime());

F_bett.getUDIRecord().setFieldValue(\"gueltigBis\", F_validTo);

\

**done**

**at.co.systema.tstrip.view.itemviewer.BackGround**

**// we can here probably use default DateFormat as described above,
because**

**// this is only formatting of some output string.**

\

if (P_currStep.get(Calendar.HOUR_OF_DAY) == 0)

{

return DateUtils.formatDate(\"dd.MMM.yyyy\",

P_currStep.getTime());

**done**

**at.co.systema.ui.l2control.calendar2.data.CalendarKeyMoment**

**\@ask Christoph if we can change this format to standard DateTime
format or this format has some special purpose**

public String toString() {

SimpleDateFormat F_dateFormat = new SimpleDateFormat(\"dd. MM. yyyy /
HH:mm\");

return F_dateFormat.format(this.getTime());

}

\

\

**done**

**at.co.systema.sap.pat.svr.CheckObjectDeps**

\

public void serverStateChangeOccurred(JCO.Server server, int old_state,
int new_state)

{

DateFormat F_dtf = new SimpleDateFormat(\"dd.MM.yyyy HH.mm.ss:\");

String Fs_date = F_dtf.format(new
java.util.Date(System.currentTimeMillis()));

\

**done**

**at.co.systema.sap.pat.svr.CheckObjectDepsServiceImpl**

\

public void serverStateChangeOccurred(JCO.Server server, int old_state,
int new_state)

{

DateFormat F_dtf = new SimpleDateFormat(\"dd.MM.yyyy HH.mm.ss:\");

String Fs_date = F_dtf.format(new
java.util.Date(System.currentTimeMillis()));

\

**done**

**at.co.systema.ui.l2control.calendar2.data.ComparableGregorian**

\

public String toString() {

SimpleDateFormat F_dateFormat = new SimpleDateFormat(\"dd. MM. yyyy /
HH:mm\");

return F_dateFormat.format(this.getTime());

}

\

**done**

**at.co.systema.gf.mvc.view.DateComponentValueAccessor**

\

UIFormatDateField F_fld = (UIFormatDateField)getControl();

if (F_fld.getInputVerifier() == null)

{

F_fld.setInputVerifier(new DateInputVerifier(\"dd.MM.yyyy\"));

}

\

**done**

**at.co.systema.gf.viewer.DateEditor**

\

else if(P_obj instanceof java.sql.Time){

field.setValueModel(new SqlTimeValueModel());

L2DateValidator F_vali = new L2DateValidator(java.sql.Time.class);

F_vali.setMask(\"HH:mm:ss\"); // Default ist ohne Sekunden

field.setValidator(F_vali);

}

else if(P_obj instanceof java.sql.Timestamp){

field.setValueModel(new SqlTimestampValueModel());

\

L2DateValidator F_vali = new L2DateValidator(java.sql.Timestamp.class);

F_vali.setMask(\"dd.MM.yyyy HH:mm:ss\"); // Default ist ohne Sekunden

field.setValidator(F_vali);

\

\

**done**

**at.co.systema.gf.viewer.DatePropertyEditor**

\

L2DateValidator F_ret = new L2DateValidator(F_format);

F_ret.setMask(\"dd.MM.yyyy HH:mm:ss\");

\

\

**Igor takes care about it.**

**at.co.systema.app.DeploymentInitializer**

\

public void initExpressionMgr(ExpressionMgr.InitHelper P_helper)

{

P_helper

.addExprFieldString(\"Termin\",

\"startZeitAsString\",

\"IF ( Termin.timeDependent , DATE2STRING ( Termin.startZeit ,
\\\"dd.MM.yyyy HH:mm:ss\\\") , DATE2STRING ( Termin.startZeit ,
\\\"dd.MM.yyyy\\\" ) )\");

\

\@Igor

It must by clarified, if we may delete these formats, because by using
of DATE2STRING(date) without formatting pattern, the default local
dependent pattern will be taken (which is correct).

\

\

**Igor takes care about it.**

**at.co.systema.ui.DeploymentInitializer**

\

F_sList.add(new SimpleEnumPropertyValue(\"dd.MM.yyyy\",

new Integer(L2Calendar2Popup.DEFAULTPATTERN_DATE)));

F_sList.add(new SimpleEnumPropertyValue(\"dd.MM.yyyy hh:mm\",

new Integer(L2Calendar2Popup.DEFAULTPATTERN_DATETIME)));

\

\@Igor

Current solution could be that the localized format will be used already
in DeploymentInitializer.

The consequence \--\> After changing of Counry must be made: cleanRepo
-syst -syst and RepoInit

\

\

**Igor takes care about it.**

**at.co.systema.lab.DeploymentMvcDictInitializer**

\

private void
\_addLaborMessReagenzColumnViewAttr(ColumnViewAttrMgr.InitHelper
P_helper)

{

String Fs_tableName = LabO.MREAG;

\

P_helper.addColumnViewAttr(Fs_tableName, \"chargeGueltigVon\",

\"gültig von\", 10, true, \"dd.MM.yyyy\", \"dd.MM.yyyy\");

P_helper.addColumnViewAttr(Fs_tableName, \"chargeGueltigBis\",

\"gültig bis\", 10, true, \"dd.MM.yyyy\", \"dd.MM.yyyy\");

\

and other ca. 40 places!

\

\

**at.co.systema.dl.view.DiagnoseTextSearchMultiBrowser**

**and**

**at.co.systema.dl.view.LeistungsTextSearchMultiBrowser**

\

String Fs_dateProp = BaseRuntime.getProperty(\"dl.KatalogCheckDate\");

if (Fs_dateProp != null)

{

try

{

DateFormat F_df = new SimpleDateFormat(\"dd.MM.yyyy\");

F_date.setTime((F_df.parse(Fs_dateProp)).getTime());

F_codingDate = F_date;

}

\

\@Igor

Do not change the above code. The customer.property
\"dl.KatalogCheckDate\" has the (documented) format dd.MM.yyyy!

\

\

**at.co.systema.gf.mvc.dict.DictColumnViewAttrGebDatumMMEgal**

\

public DictColumnViewAttrGebDatumMMEgal(String Ps_tableName, String
Ps_columnName) throws DictException

{

super(Ps_tableName, Ps_columnName);

super.setExplizitValidatorClassName(\"at.co.systema.ui.l2control.validator.GebDatumMMEgalValidator\");

super.setInputFormatierung(\"dd.MM.yyyy\");

\

\@Igor

Do not change the above code. The validator should be used only in
Austria.

\

\

**at.co.systema.novacom.gf.dict.DynamicLogObjectFactory**

\

public static final String FS_DATETIME_DATE1 = \"dd.MM.yyyy\";

public static final String FS_DATETIME_DATE2 = \"MM.yyyy\";

public static final String FS_DATETIME_DATE3 = \"ww.yyyy\";

public static final String FS_DATETIME_TIME = \"HH:mm\";

public static final String FS_DATETIME_TIMESTAMP = \"dd.MM.yyyy HH:mm\";

\

\

\

\@Igor

Do not change the above code. The code is Novacom (Vendor) specific.

\

\

**at.co.systema.dl.qa.gedowin.properties.GeDoWinProperties**

\

setFormatDate(\"dd.mm.yyyy\");

setFormatTime(\"hh:nn\");

\

\

\@Igor

Do not change the above code. The code is GeoDoWin specific.

\

\

**at.co.systema.dl.kodip.KodipUtilities**

\

public static String getKodipDatumForJavaDate(Date P_date)

{

DateFormat F_format = new SimpleDateFormat(\"dd.MM.yyyy\");

return F_format.format(P_date);

}

\

\@Igor

Do not change the above code. The code is Kodip specific.

\

\

**done**

**at.co.systema.ui.l2control.calendar2.L2Calendar2**

\

private String dataStringFormat = \"dd. MM. yyyy\";

\

\@Igor

This has to be consulted with Christoph Bimminger!

\

\

**done**

**at.co.systema.ui.l2control.calendar2.L2Calendar2Popup**

\

private String dataStringFormat = \"dd.MM.yyyy\"; //für

\

\@Igor

This has to be consulted with Christoph Bimminger!

\

\

**done**

**at.co.systema.lab.ord.view.LaborAnforderungEditor**

\

SimpleDateFormat F_dateFormat = new SimpleDateFormat(\"dd.MM.yyyy\");

\

\

**done**

**at.co.systema.lab.util.LaborLogFileWriter**

\

SimpleDateFormat F_dateFormat = new
SimpleDateFormat(\"dd.MM.yyyy-HH:mm:ss.SS\");

String Fs_date =
F_dateFormat.format((Timestamp)P_rec.getFieldValue(\"modZeitpunkt\"));

\

\

SimpleDateFormat F_dateFormat = new SimpleDateFormat(\"dd.MM.yyyy\");

String Fs_oldGebDatum =
F_dateFormat.format((Date)F_oldPat.getFieldValue(\"gebDatum\"));

String Fs_newGebDatum =
F_dateFormat.format((Date)F_newPat.getFieldValue(\"gebDatum\"));

String Fs_anfoDatum =
F_dateFormat.format((Date)P_newAnfo.getFieldValue(\"anfoDatum\"));

\

F_dateFormat.applyPattern(\"HH:mm:ss.SS\");

String Fs_timeNow = F_dateFormat.format(new
Time(System.currentTimeMillis()));

String Fs_anfoZeit =
F_dateFormat.format(P_newAnfo.getFieldValue(\"anfoZeit\"));

\

F_dateFormat.applyPattern(\"dd.MM.yyyy HH:mm:ss.SS\");

\

SimpleDateFormat F_dateFormat = new SimpleDateFormat(\"HH:mm:ss.SS\");

String Fs_timeNow = F_dateFormat.format(new
Time(System.currentTimeMillis()));

String Fs_anfoZeit =
F_dateFormat.format((Time)P_anfo.getFieldValue(\"anfoZeit\"));

\

F_dateFormat.applyPattern(\"dd.MM.yyyy\");

\

\

**done**

**at.co.systema.labor.LaborOrderSuchdialog**

\

cal = Calendar.getInstance();

**cal.setTimeZone( TimeZone.getTimeZone(\"MET\") ); // this is highly
incorrect!, I guess we can take it out**

cal.setTime( new Date() );

\

calSpinField = new JCCalendarSpinField( new Date() );

calSpinField.setFormat( \"EEE dd.MM.yyyy\" );

\

**Igor takes care about it.**

**at.co.systema.lab.pro.LaborProbeID**

\

public String createArchivKennungFor()

{

SimpleDateFormat F_formater = new SimpleDateFormat(\"d.MM.yyyy\");

java.sql.Date F_aktDatum = new
java.sql.Date(System.currentTimeMillis());

String Fs_date =
LaborUtils.truncateLeadingZeros(F_formater.format(F_aktDatum));

String Fs_ret = Fs_date + \":\" + rec.getFieldValue(\"probenId\");

if(Fs_ret.length() \> 17)

\

\@Igor

This has to be consulted with Labor group, Probably no change allowed.

\

\

**done**

**at.co.systema.gf.junit.MPATestSuiteSupport**

\

// Datum und aktuelle Uhrzeit merken (wird dann ins Logfile geschrieben)

Date F_currDate = new Date();

SimpleDateFormat F_dateFormat = new SimpleDateFormat(\"EEE, d MMM yyyy
HH:mm:ss\");

String Fs_formattedDate = F_dateFormat.format(F_currDate);

\

\

**Igor takes care about it.**

**at.co.systema.cos.cdr.chart.MultiItemSingleSeriesChartTablemitPatient**

\

private DateFormat defaultDate=new SimpleDateFormat(\"dd.MM.yyyy\");

\

\@Igor

This has to be consulted with somebody responsible for COS/CDR, if
change allowed.

\

**done**

**at.co.systema.doc.wizard.OnlineScanningDocumentNewWizardPanel**

\

SimpleDateFormat F_dateFormat = new SimpleDateFormat(\"dd.MM.yyyy\");

\

**done**

**at.co.systema.ser.view.OnlineScanningDokumentNeuDialog**

\

JLabel F_label = new JLabel(\"Dokumentdatum: \"); // TODO: I18N

SimpleDateFormat F_format = new SimpleDateFormat(\"dd.MM.yyyy\");

\

\

**done**

**at.co.systema.gf.schedule.Period**

public String toString()

{

java.text.SimpleDateFormat F_df = new
java.text.SimpleDateFormat(\"dd.MMM yyyy HH:mm:ss.SSS\");

\

\@Igor

Consulted with Christoph Bimminger.

**This can be converted to default datetime format.**

\

**done**

**at.co.systema.wfl.app.ProzessPlanner**

\

SimpleDateFormat F_format;

if (P_termin.isTimeDependent())

{

F_format = new SimpleDateFormat(\"dd.MMM.yyyy, HH.mm\");

}

else

{

F_format = new SimpleDateFormat(\"dd.MMM.yyyy\");

}

\

\@Igor

This has to be consulted with Christoph Bimminger!

This Strings will be written into DB! So, no change is possible.

Analysis needed, in which form the dates will be displayed. Some code
changes maybe needed.

\

**Igor takes care about it.**

**at.co.systema.cos.projekte.medication.view.RegularMedicationOrderingEditor**

\

SimpleDateFormat formatter = new SimpleDateFormat(\"dd.MM.yyyy\");

String Fs_currentDate = formatter.format(F_curentDate);

\

\

**Analysis of code, there are some strange formats**

**at.co.systema.tstrip.view.navigator.RubberBandNavigator**

\

if (getGUIModel().getZoomLevel().equals(ZoomLevel.HOUR_ZOOM)

\|\| getGUIModel().getZoomLevel()

.equals(ZoomLevel.MINUTE_ZOOM))

{

F_format = \"HH:mm dd. MMM\";

}

else if (getGUIModel().getZoomLevel().equals(ZoomLevel.SECOND_ZOOM))

{

F_format = \"HH:mm.ss dd.\";

}

else

{

F_format = \"dd. MMM yyyy\";

}

\

\_drawToolTip(P_g, DateUtils.formatDate(\"d.MM.yyyy\",

etc.

\

**done**

**at.co.systema.pat.patindex.server.sap.SAPJCOLooper**

\

public void serverStateChangeOccurred(JCO.Server server, int old_state,
int new_state)

{

String Fs_server = ((MyServer)server).getName();

DateFormat F_dtf = new SimpleDateFormat(\"dd.MM.yyyy HH.mm.ss:\");

String Fs_date = F_dtf.format(new
java.util.Date(System.currentTimeMillis()));

\

public void timeElapsed(MaintenanceTimer t)

{

long Fl_threshold = sapTimeThreshold \* 1000;

Set\<Map.Entry\<String, SearchTable\>\> entrySet =
searchTables.entrySet();

Iterator\<Map.Entry\<String, SearchTable\>\> iter = entrySet.iterator();

try

{

DateFormat F_dtf = new SimpleDateFormat(\"dd.MM.yyyy HH.mm.ss:\");

String Fs_date = F_dtf.format(new
java.util.Date(System.currentTimeMillis()));

\

\

\

**done**

**at.co.systema.sap.hl7.SAPRfcModule**

\

DateFormat F_dtf = new SimpleDateFormat(\"dd.MM.yyyy HH.mm.ss\");

String Fs_date = F_dtf.format(new Date(System.currentTimeMillis()));

\

**done**

**at.co.systema.sap.gf.bapi.SAPRfcModule**

\

DateFormat F_dtf = new SimpleDateFormat(\"dd.MM.yyyy HH.mm.ss\");

String Fs_date = F_dtf.format(new Date(System.currentTimeMillis()));

\

**done**

**at.co.systema.svg.SVGChart**

\

private static final String DAY_FORMAT = \"dd.MM.yyyy\";

private static final String TIME_FORMAT = \"dd.MM.yyyy HH:mm\";

\

**done**

**at.co.systema.sap.gf.conn.SapConnectionImpl**

\

DateFormat F_dtf = new SimpleDateFormat(\"dd.MM.yyyy HH.mm.ss\");

String Fs_date = F_dtf.format(new java.util.Date(System

.currentTimeMillis()));

\

DateFormat F_dtf = new SimpleDateFormat(\"dd.MM.yyyy HH.mm.ss\");

String Fs_date = F_dtf.format(new java.util.Date(System

.currentTimeMillis()));

\

DateFormat F_dtf = new SimpleDateFormat(\"dd.MM.yyyy HH.mm.ss\");

String Fs_date = F_dtf.format(new java.util.Date(System

.currentTimeMillis()));

\

**done**

**at.co.systema.wfl.app.SimpleWFLAppointmentClient**

private void \_handlePlanningDate(TerminBelegungBase P_tb,

final Date P_wish,

final String Ps_name)

final SimpleDateFormat F_dateFormat;

if (Fb_withoutTime)

{

**F_dateFormat = new SimpleDateFormat(\"EE d MMM yyyy\");**

}

else

{

**F_dateFormat = new SimpleDateFormat(\"EE d MMM yyyy HH:mm\");**

}

final String Fs_startZeitString = F_dateFormat.format(F_startZeit);

\

MessageBox output, so please format it right with \"LONG\" format.

\

\

**done**

**at.co.systema.app.view.TerminBuchUICalendarPopup**

\

public void setTimeVisible(boolean Pb_visible)

{

if (Pb_visible)

{

**setFormat(\"EE d MMM yyyy HH:mm\");**

}

else

{

**setFormat(\"EE d MMM yyyy\");**

}

}

\

Component is deprecated! So no changes please.

\

**done**

**at.co.systema.app.view.TerminView**

\

if (timeFormat == null)

{

String F_timePattern =
MpaResourceBundle.getStringIgnoreNullIgnoreTestMode(\"dateFormat.time\",
\"at.co.systema.app\");

if (F_timePattern == null)

{

logger.warn(\"did not find at.co.systema.app.MessageBundle entry
\'dateFormat.time\'. Using fallback\...\");

F_timePattern = \"HH:mm\";

}

timeFormat = new SimpleDateFormat(F_timePattern);

}

\

if (longTimeFormat == null)

{

String F_longTimePattern =
MpaResourceBundle.getStringIgnoreNullIgnoreTestMode(\"dateFormat.dateTime\",
\"at.co.systema.app\");

if (F_longTimePattern == null)

{

logger.warn(\"did not find at.co.systema.app.MessageBundle entry
\'dateFormat.dateTime\'.\" +

\"Using fallback\...\");

F_longTimePattern = \"dd.MM.yyyy HH:mm\";

}

longTimeFormat = new SimpleDateFormat(F_longTimePattern);

}

\

**done**

**at.co.systema.cos.cdr.chart.UDIRCItemTableDataModel**

\

private DateFormat defaultDate=new SimpleDateFormat(\"dd.MM.yyyy,
HH:mm\");

\

\

**done**

**at.co.systema.wfl.stats.WFLStatisticGenerator**

\

private void \_printStats(Double P_execTime)

{

if (from != null && to != null)

{

SimpleDateFormat F_dateFormater = new SimpleDateFormat(\"dd-MM-yyyy\");

logger.info(\"Date range from \" + F_dateFormater.format(from) + \" to
\"

\+ F_dateFormater.format(to));

}

else

{

logger.info(\"Date range from \" + from + \" to \" + to);

}

\

\

\

\

[**Following Keys in MessageBundles describe formatting of date/time in
some MPA modules**]{.underline}

\

All of them should be cleared with authors of the code. Where not needed
(maybe after the correction of above code snippets), then

the keys should be deleted from MessageBundles.

\

\

**at.co.systema.MessageBundle.properties**

dateFormating=dd.MMM yyyy

dateFormatingWithDay=EE, dd.MMM yyyy

\

#date/time format, as used e.g. for tool tip of TerminView

**at.co.systema.app.MessageBundle.properties**

dateFormat.time=HH:mm - app.view.TerminViewAttrSupport,
med.surgery.view.randerbit.LastSurgeryTimeRanderbit

dateFormat.dateTime=dd.MM.yyyy HH:mm - TVAS

\

**at.co.systema.wfl.server.mbean.MessageBundle.properties**

WFLStatisticsForTimeSlice.startDate=Startzeit (YYYY-MM-DD-HH-MM)
-wfl.server.mbean.state.ShowWflStatisticsForTimeSlice

WFLStatisticsForTimeSlice.endDate=Endzeit (YYYY-MM-DD-HH-MM)

WFLStatisticsForTimeSlice.wrongDateFormat=Ein Datumswert hat eine
falsche Formatierung: \"{0}\", \"{1}\"\<br\>Richtig wäre
YYYY-MM-DD-HH-MM!

\

**at.co.systema.gf.MessageBundle.properties**

gf.print.ReportMgr.HeaderText=Druckdatum: \\{D,d.MMM.yyyy\\}
\\{T,HH:mm\\} - gf.print.reportMgr

gf.print.ReportMgr.FooterText=Seite \\{P\\} von \\{N\\}

\

\

\

**at.co.systema.lab.view.MessageBundle.properties**

Ein anderer Benutzer hat {0} geändert - Ihre Änderungen wurden NICHT
gespeichert.\\n\\

Zeit: {1, date, EEEE, dd. MMMM yyyy - HH:mm:ss}

LaborUDIEditor.saveErrorRowChanged.modUserDate=\\

Ein anderer Benutzer hat {0} geändert - Ihre Änderungen wurden NICHT
gespeichert.\\n\\

Benutzer: {1}\\n\\

Zeit: {2, date, EEEE, dd. MMMM yyyy - HH:mm:ss}

\

LaborUDIEditor.saveErrorRowChanged.ask.noinfo=\\

Ein anderer Benutzer hat {0} geändert - Ihre Änderungen wurden NICHT
gespeichert.\\n\\

\\n\\

Soll {0} neu geladen werden?

LaborUDIEditor.saveErrorRowChanged.ask.modUser=\\

Ein anderer Benutzer hat {0} geändert - Ihre Änderungen wurden NICHT
gespeichert.\\n\\

Benutzer: {1}\\n\\

\\n\\

Soll {0} neu geladen werden?

LaborUDIEditor.saveErrorRowChanged.ask.modDate=\\

Ein anderer Benutzer hat {0} geändert - Ihre Änderungen wurden NICHT
gespeichert.\\n\\

Zeit: {1, date, EEEE, dd. MMMM yyyy - HH:mm:ss}\\n\\

\\n\\

Soll {0} neu geladen werden?

LaborUDIEditor.saveErrorRowChanged.ask.modUserDate=\\

Ein anderer Benutzer hat {0} geändert - Ihre Änderungen wurden NICHT
gespeichert.\\n\\

Benutzer: {1}\\n\\

Zeit: {2, date, EEEE, dd. MMMM yyyy - HH:mm:ss}\\n\\

\\n\\

\

\

\

\
