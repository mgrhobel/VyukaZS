---
title: "Example 5-8.txt"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/zdroje/Java Int/JavaIntExamples/Chapter 5/Example 5-8.txt"
date: 2001-03-29
type: TXT
---

NumberFormat nf = NumberFormat.getInstance();
if (nf instanceof DecimalFormat) {
  DecimalFormat df = (DecimalFormat)nf;

  // get the DecimalFormatSymbols from DecimalFormat
  DecimalFormatSymbols dfs = df.getDecimalFormatSymbols();

  // modify some parameters on DecimalFormatSymbols
  dfs.setCurrencySymbol("AD$");

  // put the DecimalFormatSymbols object back again
  df.setDecimalFormatSymbols(dfs);

  // apply a pattern - remember \u00a4 == ¤
  df.applyPattern("\u00a4#,###.##");
}

System.out.println(nf.format(1234.56));

