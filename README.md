pwsafe
======
Password manager for the console. This password manager uses gpg to store
all your passwords. It can automatically copy the password to your clipboard
manager without showing it on the console. 
If you use "usegit" in config file it will automatically push the password
file after an update.

Prerequisite
============
	File::Grep
	Clipboard
	Term::ReadKey
	Config::Simple
	File::Basename


Configuration
=============
Configfile: ~/.pwsafe.conf

	[file]
	pwfile = "~/.passwords"
	cipher = "AES256"
	
	[options]
	toclip = 1
	debug = 0
	usegit = 0

Usage
=====
	pwsafe.pl [-c <config>] -o <option> [-l <lookup pattern>] [-d] [-h] [-t <0|1>]
	
	-c, --config    config file to use
	-o, --option    option can be "edit", "get", "add", "delete"a
	-l, --lookup    pattern to search in the password database
	-t, --toclip    0 or 1 
	                0 will disable copy to clipboard
	                1 will enable copy to clipboard
	-h, --help      this help message

Passwordfile format
===================
The format in your password file will look like this

	#Name  ;Username  ;Password  ;Sitetype;Sitelink  ;;;;
