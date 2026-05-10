---
title: "Example 5-6.txt"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/zdroje/Java Int/JavaIntExamples/Chapter 5/Example 5-6.txt"
date: 2001-03-29
type: TXT
---

String parseMe = "1.234,56";
NumberFormat numParser = NumberFormat.getInstance(Locale.GERMANY);

try {
  Number result = numParser.parse(parseMe);
  System.out.println(result);
} catch(ParseException e) {
  // handle error condition
}
