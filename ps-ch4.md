
# Notes/Workings from chapter

Reference point 4.1  
PS scripts are marked by .PS1 at the end.

Reference point 4.2  
The common syntax is as follows:
```
cmdlet -parameter(s) [value] -switch-parameter
```
Note that PS is case-insensitive, spaces are needed between values and parameters

Reference point 4.3  
Pounced "command-let", Cmlets are typically reconised by the use of verb and noun names (like Get-Help). the common verbs are "get", "set", "new" and "pause". (page has noted the lack of a Get-Noun cmdlet, blame the devs.)

Also makes a friendly reminder to RTFGHF ~~(read the ________ Get-Help File)~~

Reference point 4.4  
non-common aliases are avoided to limit the need to reassign them.


# Chapter Lab
**NOTICE: results Current on winclient.lab.internal.local as at 201708(date pending)**

Q1: Display a list of running processes
```

```


Q2: **(Windows Only - NO Get-WinEvent)** Display the 100 most recent entries from the Application event log (Don't use Get-WinEvent for this. We've shown you another command that will do this task)

```

```

Q3: Display a list of all commands that are of the cmdlet type. (this is tricky-we've shown you Get-Command, but you'er going to have to read the help to find out how to narrow down the list as we've asked)

```

```

Q4: Display a list of all aliases

```

```

Q5: (Windows Only, Linux with wine installs okay) Make a new alias, so you can run np to launch Notepad form a PowerShell Prompt.

```

```

Q6: (again Windows Only) Display a list of services that begin with the letter M. Again, read the help for the necessary command-and don't forget the asterisk is a near universal wildcard in PowerShell.

```

```

Q7: (Windows Only, Firewall rules) Display a list of all Windows Firewall rules. You'll need to use Help or Get-Command to discover the necessary cmdlet.

```

```

Q8: (Windows Only, Firewall rules) Display a list only of inbound Windows Firewall rules. you can use the same cmdlet as in the previous task, but you'll need to read its help to discover the necessary parameter and its allowable values.

```

```

Document Made By: Corey John Clayton  
Derived From: Chapter 4, Learn Windows PowerShell in a Month of Lunches, Third Edition. Don Jones and Jeffery Hicks  
Completed On:  

Copyright 2017, Manning Publications Co. All Rights Reserved
