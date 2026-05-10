---
title: "Example 5-12.txt"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/zdroje/Java Int/JavaIntExamples/Chapter 5/Example 5-12.txt"
date: 2001-03-29
type: TXT
---

String fileName = "foo";
int spellingMistakes = 3;

Object[] arguments = { new Integer(spellingMistakes), fileName };
String out = MessageFormat.format(resources.getString("WarningMsg"), arguments);
System.out.println(out);

