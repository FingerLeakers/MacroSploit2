Macrosploit - Multi Operating System Social Engineering / Penetration Testing Payload
===========

This Microsoft Word Macro works as a social engineering payload for penetration testers. This does not actually use any exploits, it uses the intended functionality of a macro for unintended purposes. If you can trick a user into enabling Macros then this will work.

Tested and working on the following:

Windows 7 Pro x64 - Microsoft Office Professional Plus 2010

OSX 10.9.5 - Microsoft Word for Mac 2011 14.2.0

Features:

Automatically runs on document open when Macros are enabled

OSX Persistent Reverse Shell using Bash

Bypasses built in OSX GateKeeper Security

What it does:

On Mac it will create a reverse shell connection to the listener that you must specify
It uses the plist method of persistance so that a new reverse shell is attempted ever 120 seconds (WARNING: You must manually remove the com.apple.video2.plist file or unload plist to remove this persistance). The Macro first tries runs as the user, sets up a reverse shell with user privileges, and sets up persistance for that user. The Macro then tries to run as with administrator privileges which pops up a login prompt asking for the administrative user's password. This will set up a reverse shell with administrator privileges and sets up persistence for all users. 

On Windows it will execute VB shellcode of your choice this could be a reverse shell, Meterpreter, or Beacon if you have access to Cobalt Strike (www.advancedpentest.com).

How to use it:

For the Mac payload just change the reverse shell listener to your listener IP address, change the port (currently 4444) to your listener port. E.g. nc -lvp 1234 (or use the generic/shell_reverse_tcp in Metasploit). For the Windows payload change the shellcode to the VB shellcode of your choice.

Future Plans

Test on Libre Office / Open Office for Linux reverse shell so that one payload can work on Windows, OSX, Linux and Unix.

