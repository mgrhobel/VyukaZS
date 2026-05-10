---
title: "Example 5-7.txt"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/zdroje/Java Int/JavaIntExamples/Chapter 5/Example 5-7.txt"
date: 2001-03-29
type: TXT
---

double d = 1234567.89;
double n = -1234567.89;

// a pattern for both positive and negative numbers
// that displays the local currency symbol and formats
// using both local group and decimal separators.
String pattern = "¤#,###.##;(¤#,###.##)";

NumberFormat nf = NumberFormat.getInstance();
if (nf instanceof DecimalFormat) {
  DecimalFormat df = (DecimalFormat)nf;
  df.applyPattern(pattern);
  System.out.println(df.format(d));
  System.out.println(df.format(n));
}

