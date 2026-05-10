---
title: "Example 5-4.txt"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/zdroje/Java Int/JavaIntExamples/Chapter 5/Example 5-4.txt"
date: 2001-03-29
type: TXT
---

Calendar JO_cal = Calendar.getInstance(new Locale("ar", "JO"));
Calendar FR_cal = Calendar.getInstance(Locale.FRANCE);
Calendar CA_cal = Calendar.getInstance(Locale.CANADA);

DateFormatSymbols dfs = new DateFormatSymbols();
String weekdays[] = dfs.getWeekdays();

System.out.println(weekdays[JO_cal.getFirstDayOfWeek()]);
System.out.println(weekdays[FR_cal.getFirstDayOfWeek()]);
System.out.println(weekdays[CA_cal.getFirstDayOfWeek()]);

