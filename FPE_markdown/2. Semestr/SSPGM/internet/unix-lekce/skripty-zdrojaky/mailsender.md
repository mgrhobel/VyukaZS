---
title: "mailsender.txt"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/internet/unix-lekce/skripty-zdrojaky/mailsender.txt"
date: 2009-05-01
type: TXT
---

#!/bin/perl -w

# assumes we have sendmail installed
open(SENDMAIL, "|/usr/lib/sendmail -oi -t -odq") or
  die "Can't fork for sendmail: $!\n";
  
print SENDMAIL <<"EOF";
From: User Originating Mail <me\@host>
To: Final Destination <you\@otherhost>
Subject: A relevant subject line

Body of the message goes here after the blank line
in as many lines as you like.
EOF

close(SENDMAIL) or warn "sendmail didn't close nicely";