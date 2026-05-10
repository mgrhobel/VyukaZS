---
title: "Weekdays and Month Names in MPA, correct Internationalizatio.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/MIT resources/TODOs/Weekdays and Month Names in MPA, correct Internationalizatio.doc"
date: 2010-03-11
type: DOC
---

\

**\-\-\-\-\-\-\-\-- 10.2.2009 15:10:52 by Josef Hobel:**

done

\

**\-\-\-\-\-\-\-\-- 21/01/2009 8:38:19 by Christoph Bimminger:**

Please note that the AppSeriesDialog (mentioned in list of pending
changes below) was changed with ^(1)^*[Todo 41389: Applix:
Aufwandschätzung Default-Feld-Änderungen in Termin]{.underline}*; we now
have a fully customizable view (AppSeriesEntrer)

\

**\-\-\-\-\-\-\-\-- 13.1.2009 6:44:56 by Jiri Kiml:**

\

I think it is candidate for Josef Hobel.

\

\

**\-\-\-\-\-\-\-\-- 12.01.2009 22:47:00 by Igor Böhm:**

Short introduction into official JAVA implementation of Weekdays in
JAVA:

\

Class **DateFormatSymbols** contains 4 important functions:

\

DateFormatSymbols symbols;

String\[\] defaultDays;

String\[\] defaultMonths;

\

**symbols = new DateFormatSymbols(currentLocale);**

**defaultDays = symbols.getShortWeekdays();**

**defaultDays = symbols.getWeekdays();**

\

**defaultMonths = symbols.getShortMonths();**

**defaultMonths = symbols.getMonths();**

\

See output from following test programm;

\

![](Weekdays%20and%20Month%20Names%20in%20MPA,%20correct%20Internationalizatio_html_1302c25b.png){#Image1
align="bottom" width="114" height="47" border="0"} \--\>
![](Weekdays%20and%20Month%20Names%20in%20MPA,%20correct%20Internationalizatio_html_4239e501.gif){#Image2
align="bottom" width="137" height="47" border="0"}

\

For Date, Time and DateTime formatting see ^(2)^*[Todo 43072: Correct
Localization of Date and Time Formatting in MPA]{.underline}*.

\

\

\

**WeekDaysFormatter**

**\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--**

\

**Locale: de_DE**

\

**Short Days**

Mo Di Mi Do Fr Sa So

**Long Days**

Montag Dienstag Mittwoch Donnerstag Freitag Samstag Sonntag

**Short Months**

Jan Feb Mrz Apr Mai Jun Jul Aug Sep Okt Nov Dez

**Long Months**

Januar Februar März April Mai Juni Juli August September Oktober
November Dezember

\

**EEE\... Formats:**

E: Mo

EE: Mo

EEE: Mo

EEEE: Montag

EEEEE: Montag

\

**Locale: de_AT Deutsch (Österreich)**

\

Short Days

Mo Di Mi Do Fr Sa So

Long Days

Montag Dienstag Mittwoch Donnerstag Freitag Samstag Sonntag

Short Months

**Jän** Feb **Mär** Apr Mai Jun Jul Aug Sep Okt Nov Dez

Long Months

**Jänner** Februar März April Mai Juni Juli August September Oktober
November Dezember

\

EEE\... Formats:

E: Mi

EE: Mi

EEE: Mi

EEEE: Mittwoch

EEEEE: Mittwoch

\

**Locale: en_US**

\

**Short Days**

Sun Mon Tue Wed Thu Fri Sat

**Long Days**

Sunday Monday Tuesday Wednesday Thursday Friday Saturday

**Short Months**

Jan Feb Mar Apr May Jun Jul Aug Sep Oct Nov Dec

**Long Months**

January February March April May June July August September October
November December

\

**EEE\... Formats:**

E: Mon

EE: Mon

EEE: Mon

EEEE: Monday

EEEEE: Monday

\

**Locale: en_GB**

\

**Short Days**

Mon Tue Wed Thu Fri Sat Sun

**Long Days**

Monday Tuesday Wednesday Thursday Friday Saturday Sunday

**Short Months**

Jan Feb Mar Apr May Jun Jul Aug Sep Oct Nov Dec

**Long Months**

January February March April May June July August September October
November December

\

**EEE\... Formats:**

E: Mon

EE: Mon

EEE: Mon

EEEE: Monday

EEEEE: Monday

\

**Locale: fr_FR (french)**

\

**Short Days**

lun. mar. mer. jeu. ven. sam. dim.

**Long Days**

lundi mardi mercredi jeudi vendredi samedi dimanche

**Short Months**

janv. févr. mars avr. mai juin juil. aout sept. oct. nov. déc.

**Long Months**

janvier février mars avril mai juin juillet aout septembre octobre
novembre décembre

\

**EEE\... Formats:**

E: lun.

EE: lun.

EEE: lun.

EEEE: lundi

EEEEE: lundi

\

**Locale: cs_CZ (czech)**

\

**Short Days**

Po Út St ?t Pá So Ne

**Long Days**

Pond?lí Úterý St?eda ?tvrtek Pátek Sobota Ned?le

**Short Months**

I II III IV V VI VII VIII IX X XI XII

**Long Months**

leden únor b?ezen duben kv?ten ?erven ?ervenec srpen zá?í ?íjen listopad
prosinec

\

**EEE\... Formats:**

E: Po

EE: Po

EEE: Po

EEEE: Pond?lí

EEEEE: Pond?lí

\

**Locale: sk_SK (slovak)**

\

**Short Days**

Po Ut St Št Pi So Ne

**Long Days**

Pondelok Utorok Streda Štvrtok Piatok Sobota Nede?a

**Short Months**

jan feb mar apr máj jún júl aug sep okt nov dec

**Long Months**

január február marec apríl máj jún júl august september október november
december

\

**EEE\... Formats:**

E: Po

EE: Po

EEE: Po

EEEE: Pondelok

EEEEE: Pondelok

\

**Locale: sr_RS (serbian)**

\

**Short Days**

??? ??? ??? ??? ??? ??? ???

**Long Days**

????????? ?????? ????? ???????? ????? ?????? ??????

**Short Months**

??? ??? ??? ??? ??? ??? ??? ??? ??? ??? ??? ???

**Long Months**

?????? ??????? ???? ????? ??? ??? ??? ?????? ????????? ??????? ????????
????????

\

**EEE\... Formats:**

E: ???

EE: ???

EEE: ???

EEEE: ?????????

EEEEE: ?????????

\

Be aware of following problem with serbian

^(3)^*[Todo 43346: Implement DateFormatSymbolsProvider Class for Serbian
Locale]{.underline}*

\

Here explained just for info:

\

The problem with serbian month/weekday names is that serbian language is
officially based on

Cyrillic (similar to russian), so completely other charset is running on
our computers and System.out.println()

as default does not work.

\

But in the IT reality serbian poeple do not use Cyrillic, but Latin for
East Europe (the same charset as croatian,

czech or slovak).

That means we have to generate LocaleServiceProvider class for
Locale(\"sr\"), see following code from DateFormatSymbols class:

\

/\*\*

\* Gets the \<code\>DateFormatSymbols\</code\> instance for the
specified

\* locale. This method provides access to
\<code\>DateFormatSymbols\</code\>

**\* instances for locales supported by the Java runtime itself as
well**

**\* as for those supported by installed**

**\* {@link java.text.spi.DateFormatSymbolsProvider
DateFormatSymbolsProvider}**

**\* implementations.**

\* \@param locale the given locale.

\* \@return a \<code\>DateFormatSymbols\</code\> instance.

\* \@exception NullPointerException if \<code\>locale\</code\> is null

\* \@since 1.6

\*/

public static final DateFormatSymbols getInstance(Locale locale) {

\

// Check whether a provider can provide an implementation that\'s closer

// to the requested locale than what the Java runtime itself can
provide.

LocaleServiceProviderPool pool =

LocaleServiceProviderPool.getPool(DateFormatSymbolsProvider.class);

if (pool.hasProviders()) {

DateFormatSymbols providersInstance = pool.getLocalizedObject(

DateFormatSymbolsGetter.INSTANCE, locale);

if (providersInstance != null) {

return providersInstance;

}

}

\

return new DateFormatSymbols(locale);

}

\

\

See \--\>
http://www.j2ee.me/docs/books/tutorial/i18n/locale/services.html

\

See \--\>
http://www.docjar.org/docs/api/java/util/spi/LocaleServiceProvider.html

\

\

\

**Locale: hr_HR**

\

**Short Days**

pon uto sri ?et pet sub ned

**Long Days**

ponedjeljak utorak srijeda ?etvrtak petak subota nedjelja

**Short Months**

sij vel ožu tra svi lip srp kol ruj lis stu pro

**Long Months**

sije?anj velja?a ožujak travanj svibanj lipanj srpanj kolovoz rujan
listopad studeni prosinac

\

**EEE\... Formats:**

E: pon

EE: pon

EEE: pon

EEEE: ponedjeljak

EEEEE: ponedjeljak

\

\

**\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--**

\

***By using of SimpleDateFormat in form of:***

\

***formatter = new SimpleDateFormat(\"EEE\", symbols);***

***today = new Date();***

***result = formatter.format(today);***

***System.out.println(\"EEE: \" + result);***

\

***can you format weekdays either in \"short\" or \"long\" form.***

***Every format having 3 and less \"E\" leeds to \"short\" form of
weekdays (E, EE, EEE).***

***Every format having more thant 3 \"E\"\'s leeds to \"long\" form of
weekdays (EEEE, \...).***

\

**Generally, using of SimpleDateFormat** **should be used only for
special purposes,**

**maybe in Appointment Book area, generally** **using of DateFormat for
Date, Time and DateTime**

**formats is suggested, see DateFormatDemo.java**

**\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--**

\

**Some arts of Date Format contain implicitly names of weekdays or
months**

\

Locale: de_DE

\

LONG:15. Dezember 2008

FULL:Montag, 15. Dezember 2008

\

Locale: en_US

\

MEDIUM:Dec 15, 2008

LONG:December 15, 2008

FULL:Monday, December 15, 2008

\

Locale: en_GB

\

MEDIUM:15-Dec-2008

LONG:15 December 2008

FULL:Monday, 15 December 2008

\

Locale: cs_CZ

\

LONG:15. prosinec 2008

FULL:Pond?lí, 15. prosinec 2008

\

Locale: sk_SK

\

LONG:Pondelok, 2008, december 15

FULL:Pondelok, 2008, december 15

\

Locale: sr_RS

\

FULL:?????????, 15.????????.2008

\

Locale: hr_HR

\

LONG:2008. prosinac 15

FULL:2008. prosinac 15

\

**\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--**

\

**Important localisation (L10N) difference between various countries is
the \"first day of week\", see**

\

Calendar cal = Calendar.getInstance(currentLocale);

int firstDayOfWeek = cal.getFirstDayOfWeek();

\

**In most countries the firstDayOfWeek =** **2 (Monday).**

But there are some countries of interest for MPA (see below), where
firstDayOfWeek **= 1 (Sunday).**

(naturally additionally all english, japanish and chinesish speaking
countries)

\

**bg_BG (Bulgarisch (Bulgarien)) FirstDayOfWeek = 1**

**ro_RO (Rumänisch (Rumänien)) FirstDayOfWeek = 1**

sq_AL (Albanisch (Albanien)) FirstDayOfWeek = 1

mk_MK (Mazedonisch (Mazedonien)) FirstDayOfWeek = 1

sl_SI (Slowenisch (Slowenien)) FirstDayOfWeek = 1

lv_LV (Lettisch (Lettland)) FirstDayOfWeek = 1

be_BY (Belorussisch (Belarus)) FirstDayOfWeek = 1

\

Just for information: in all arabic speaking countries, the first day of
week = **7 (Saturday)**.

\

**See following code for the right output of week days, starting with
first day of week**

(see again DateFormatDemo.java)

\

symbols = new DateFormatSymbols(currentLocale);

defaultDays = symbols.getShortWeekdays();

System.out.println(\"Short Days\");

\

**for (int i = firstDayOfWeek; i \< defaultDays.length; i++)**

{

System.out.print(defaultDays\[i\] + \" \");

}

**for (int i = 0; i \< firstDayOfWeek; i++)**

{

System.out.print(defaultDays\[i\] + \" \");

\

Output for **German or Austria** is as usual:

**Short Days**

Mo Di Mi Do Fr Sa So

\

Output for **en_US (USA**) is

**Short Days**

Sun Mon Tue Wed Thu Fri Sat

\

Output for en_GB (Great Britain) is

**Short Days**

Mon Tue Wed Thu Fri Sat Sun

\

\

**For correct coding of days in graphical interfaces we have often to
know, if some day is exactly Sunday, Monday etc.**

(because the business logic depends on it).

In this case you can use following constants:

\

Calendar.SUNDAY; // = 1

Calendar.MONDAY; // = 2

comparing with

Calendar cal = Calendar.getInstance(currentLocale);

cal.get(Calendar.DAY_OF_WEEK)

\

**\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--**

**Following code pieces in MPA should be changed.**

\

**1.)**

**at.co.systema.app.view.AppSeriesDialog**

\

\_text.put(TX_SUNDAY, MpaResourceBundle.getString(\"sunday\"));

\_text.put(TX_MONDAY, MpaResourceBundle.getString(\"monday\"));

\_text.put(TX_TUESDAY, MpaResourceBundle.getString(\"tuesday\"));

\_text.put(TX_WEDNESDAY, MpaResourceBundle.getString(\"wednesday\"));

\_text.put(TX_THURSDAY, MpaResourceBundle.getString(\"thursday\"));

\_text.put(TX_FRIDAY, MpaResourceBundle.getString(\"friday\"));

\_text.put(TX_SATURDAY, MpaResourceBundle.getString(\"saturday\"));

\

**Although we have in at.co.systema.MessageBundle.properties the keys
for long week days (monday, tuesday etc.)**

**and in at.co.systema.ui.MessageBundle.properties the keys for short
week days (Mo, Tu, \...),** **this is not the preferred way!**

\

Here following function can be used directly:

String\[\] defaultDays;

\

**symbols = new DateFormatSymbols(currentLocale);**

**defaultDays = symbols.getWeekdays();**

\

**2.)**

**at.co.systema.ui.l2control.calendar2.util.CalendarUtil**

\

Methods

**public static String getDayShortName(int Pi_ix) {**

String F_key;

switch(Pi_ix) {

case Calendar.MONDAY:

F_key=\"day.mo\";

break;

case Calendar.TUESDAY:

F_key=\"day.tu\";

break;

case Calendar.WEDNESDAY:

F_key=\"day.we\";

break;

case Calendar.THURSDAY:

F_key=\"day.th\";

break;

case Calendar.FRIDAY:

F_key=\"day.fr\";

break;

case Calendar.SATURDAY:

F_key=\"day.sa\";

break;

case Calendar.SUNDAY:

F_key=\"day.su\";

break;

default:

F_key=\"undefined\";

}

return MpaResourceBundle.getString(F_key, \"at.co.systema.ui\");

}

**Here similar situation, only the parameter Pi_ix starts with 1
(Calendar.SUNDAY) and ends with 7 (Calendar.SATURDAY),**

**so the array symbols.getWeekdays() can be accessed directly with
\"shift one\" ;-)**

\

/\*\*

\* Ermittelt den Monatsnamen aus den I18N Infos (MessageBundle)

\* \@param Pi_ix Index des zu übergebenden Monats (Zero-Based)

\* \@return Liefert den Monatsnamen.

\*/

**public static String getMonthName(int Pi_ix) {**

String F_key;

switch(Pi_ix) {

case Calendar.JANUARY:

F_key=\"month.january\";

break;

case Calendar.FEBRUARY:

F_key=\"month.february\";

break;

case Calendar.MARCH:

F_key=\"month.march\";

break;

case Calendar.APRIL:

F_key=\"month.april\";

break;

case Calendar.MAY:

F_key=\"month.may\";

break;

case Calendar.JUNE:

F_key=\"month.june\";

break;

case Calendar.JULY:

F_key=\"month.july\";

break;

case Calendar.AUGUST:

F_key=\"month.august\";

break;

case Calendar.SEPTEMBER:

F_key=\"month.september\";

break;

case Calendar.OCTOBER:

F_key=\"month.october\";

break;

case Calendar.NOVEMBER:

F_key=\"month.november\";

break;

case Calendar.DECEMBER:

F_key=\"month.december\";

break;

default:

F_key=\"undefined\";

}

return MpaResourceBundle.getString(F_key, \"at.co.systema.ui\");

}

**Here the array symbols.getWeekdays() can be used directly, becuase
Calendar.JANUARY = 0.**

\

**3.)**

**at.co.systema.tstrip.utils.DateUtils**

\

Implementation of following functions must be correctly
internationalized

\

**public static String getDayOfWeekForNumber(int P_dayOfWeek)**

**public static String getDayOfWeekForNumberShort(int P_dayOfWeek)**

**public static String getMonthForNumber(int P_month)**

**public static String getMonthForNumberShort(int P_month)**

\

**Then remove no longer needed keys from following MessageBundle (and
all language variations)**

at.co.systema.tstrip.MessageBundle.properties

\

\

\

**4.)**

**at.co.systema.gf.schedule.JythonCalendarRule**

\

public static Map getUsableVariables()

{

Map F_ret = new OrderPreservingHashtable();

F_ret.put(\"date\", \"contains the current date\");

F_ret.put(\"year\", \"contains the current year\");

F_ret.put(\"month\", \"contains the current month of the year\");

F_ret.put(\"day\", \"contains the current day of the month\");

F_ret.put(\"monday\", \"determines whether the current weekday is a
monday\");

F_ret.put(\"tuesday\", \"determines whether the current weekday is a
tuesday\");

F_ret.put(\"wednesday\", \"determines whether the current weekday is a
wednesday\");

F_ret.put(\"thursday\", \"determines whether the current weekday is a
thursday\");

F_ret.put(\"friday\", \"determines whether the current weekday is a
friday\");

F_ret.put(\"saturday\", \"determines whether the current weekday is a
saturday\");

F_ret.put(\"sunday\", \"determines whether the current weekday is a
sunday\");

F_ret.put(\"feiertag\", \"determines whether the current date is a
holyday\");

F_ret.put(\"max_day_of_month\", \"contains the number of days of the
current month\");

F_ret.put(\"julianDay\", \"contains the julian-day-number of the current
date\");

F_ret.put(\"dateFrom\", \"optional - contains the beginn date\");

F_ret.put(\"dateTo\", \"optional - contains the end date\");

F_ret.put(AUFENTHALT_VAR, \"contains the UDIRecord of an case\");

\

return F_ret;

}

\

Look in JythonCalendarRuleEditor which MessageBundle is used
(at.co.systema.gf).

Put the new keys for Map values into that MessageBundle.

**Look out! Do not internationalize KEY VALUES of the Map
getUsableVariables()!**

\

\

**5.)**

**at.co.systema.app.view.PraesenzEditorControlsForViewerFactory**

\

public Map getControls()

UICheckBox F_cb = new
UICheckBox(MpaResourceBundle.getString(\"monday\"));

F_cb.setName(PraesenzEditor.MONDAY_NAME);

F_cb.setSize(F_cbDim);

F_cb.setPreferredSize(F_cbDim);

F_ret.put(\"Single day Controls.setDays.Monday\", F_cb);

\

F_cb = new UICheckBox(MpaResourceBundle.getString(\"tuesday\"));

F_cb.setName(PraesenzEditor.TUESDAY_NAME);

F_cb.setSize(F_cbDim);

F_cb.setPreferredSize(F_cbDim);

F_ret.put(\"Single day Controls.setDays.Tuesday\", F_cb);

\

F_cb = new UICheckBox(MpaResourceBundle.getString(\"wednesday\"));

F_cb.setName(PraesenzEditor.WEDNESDAY_NAME);

F_cb.setSize(F_cbDim);

F_cb.setPreferredSize(F_cbDim);

F_ret.put(\"Single day Controls.setDays.Wednesday\", F_cb);

\

F_cb = new UICheckBox(MpaResourceBundle.getString(\"thursday\"));

F_cb.setName(PraesenzEditor.THURSDAY_NAME);

F_cb.setSize(F_cbDim);

F_cb.setPreferredSize(F_cbDim);

F_ret.put(\"Single day Controls.setDays.Thursday\", F_cb);

\

F_cb = new UICheckBox(MpaResourceBundle.getString(\"friday\"));

F_cb.setName(PraesenzEditor.FRIDAY_NAME);

F_cb.setSize(F_cbDim);

F_cb.setPreferredSize(F_cbDim);

F_ret.put(\"Single day Controls.setDays.Friday\", F_cb);

\

F_cb = new UICheckBox(MpaResourceBundle.getString(\"saturday\"));

F_cb.setName(PraesenzEditor.SATURDAY_NAME);

F_cb.setSize(F_cbDim);

F_cb.setPreferredSize(F_cbDim);

F_ret.put(\"Single day Controls.setDays.Saturday\", F_cb);

\

F_cb = new UICheckBox(MpaResourceBundle.getString(\"sunday\"));

F_cb.setName(PraesenzEditor.SUNDAY_NAME);

F_cb.setSize(F_cbDim);

F_cb.setPreferredSize(F_cbDim);

F_ret.put(\"Single day Controls.setDays.Sunday\", F_cb);

\

**Do not forget that the \"monday\" (obviously first day of week in
Europe) does not correspond**

**to the first (index 0) day of week in Java. The first day is Sunday.**

\

\

\
