---
title: "Example 5-2.txt"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/zdroje/Java Int/JavaIntExamples/Chapter 5/Example 5-2.txt"
date: 2001-03-29
type: TXT
---

// Instantiate the formatter using a pattern
SimpleDateFormat sdf = new SimpleDateFormat("EEEE, MMMM d yyyy G");

// Define a date using the GregorianCalendar.
GregorianCalendar anniv = new GregorianCalendar(1999,Calendar.OCTOBER,4);

// format the date using the SimpleDateFormat formmatter
String theDate = sdf.format(anniv.getTime());

// print the output to standard out
System.out.println(theDate);
