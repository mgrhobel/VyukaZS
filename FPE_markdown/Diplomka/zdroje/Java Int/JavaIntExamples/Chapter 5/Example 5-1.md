---
title: "Example 5-1.txt"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/zdroje/Java Int/JavaIntExamples/Chapter 5/Example 5-1.txt"
date: 2001-03-29
type: TXT
---

// instantiate a GregorianCalendar with a given date
GregorianCalendar cal = new GregorianCalendar(1965, Calendar.JUNE, 16);

// get a DateFormat object using a LONG style and French locale
DateFormat df;
df = DateFormat.getDateInstance(DateFormat.LONG, Locale.FRANCE);

// format the date
String frDate = df.format(cal.getTime());

// parse must be called inside a try block.
try {
  // parse the French formatted date using the DateFormat object
  // we instantiated earlier.
  Date theDate = df.parse(frDate);

  // format the Date object using the default locale and a FULL style
  String result;

  result = DateFormat.getDateInstance(DateFormat.FULL).format(theDate);
} catch (ParseException e) {
  System.out.println("Error parsing date");
}

