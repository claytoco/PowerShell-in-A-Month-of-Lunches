# Notes/Workings from chapter

reference point: 3.1

Noted in the preaching that they say strictly that only Get-Help is to be used by default. Noting that 90% of the troubles are easily resolvable by prompt.

reference point: 3.2

When updating help, it can only be done by the Systems Administrator. other updates are not allowed.

For controlled environments (government networks), Save-Help is used to obtain the latest version and push it to other clients.

Ctrl+C is strictly the stop button. and More has no effect in the ISE version.

reference point: 3.4

Remember the * when using Get-Help

when using the Get-Help with the asterisk, it highlights the name, category and Module of the item that you requested.

reference point: 3.5

when Get-Help is used with a cmdlet (like Get-EventLog), it provides details on the variables that it uses. enforceable parameters are not enclosed in square brackets. Optional versions are enclosed however. for examples, use -full in the cmdlet.  

reference point: 3.6

when arrays are mentioned, they are prefixed with about_*.

reference point: 3.7

the latest version is available online through the -online parameter

## Note: Microsoft has Open-Sourced the help files since April 2016, see github.com/PowerShell for details

# Chapter Lab

Q1) Run Update-Help and ensure that it completes without errors, so that you have a copy of the help on your local computer. You need an internet connection, and the shell needs to run under elevated privileges (which means Administrator must appear in the shell window’s title bar [or System32 at the end of the path when it starts]).

```
default
.\System32> Update-Help

form file
 .\System32> Update-Help -SourcePath [folderpath]
```
Note: client PC and main was updated 17 August 2017


Q2) Windows-only: can you find any cmdlets capable of converting other cmdlets output into HTML?

```
> Get-Help *HTML

NAME
    ConvertTo-Html

SYNTAX

ALIASES
    None


REMARKS
    None

Get-Help ConvertTo-Html | Out-File c:\Users\client\converttohtml.txt
```
See converttohtml.txt for result of file

Q3: Partially Windows-only: are there any cmdlets that can redirect output into a file or to a printer?
```
> Get-Help *File

Name                              Category  Module                    Synopsis
----                              --------  ------                    --------
Import-PowerShellDataFile         Function  Microsoft.PowerShell.U...
New-TemporaryFile                 Function  Microsoft.PowerShell.U... Creates a temporary file.
New-PSSessionConfigurationFile    Cmdlet    Microsoft.PowerShell.Core Creates a file that defines a session configur...
New-PSRoleCapabilityFile          Cmdlet    Microsoft.PowerShell.Core Creates a file that defines a set of capabilit...
Test-PSSessionConfigurationFile   Cmdlet    Microsoft.PowerShell.Core Verifies the keys and values in a session conf...
Out-File                          Cmdlet    Microsoft.PowerShell.U... Sends output to a file.
Unblock-File                      Cmdlet    Microsoft.PowerShell.U... Unblocks files that were downloaded from the I...
Add-BitsFile                      Cmdlet    BitsTransfer              Add-BitsFile...
Set-AppXProvisionedDataFile       Cmdlet    Dism                      Set-AppXProvisionedDataFile...
Get-NetConnectionProfile          Function  NetConnection             ...
Set-NetConnectionProfile          Function  NetConnection             ...
Get-NetFirewallProfile            Function  NetSecurity               ...
Set-NetFirewallProfile            Function  NetSecurity               ...
Disable-NetIPHttpsProfile         Function  NetworkTransition         ...
Enable-NetIPHttpsProfile          Function  NetworkTransition         ...
Get-SmbOpenFile                   Function  SmbShare                  ...
Close-SmbOpenFile                 Function  SmbShare                  ...


Get-Help Out-File | Out-File c:\Users\client\outfile.txt
```
See outfile.txt for details

Q4: How many cmdlets are available for working with processes (Hint: remember that cmdlets all use a singular noun)
```
> Get-Help *process

Name                              Category  Module                    Synopsis
----                              --------  ------                    --------
Enter-PSHostProcess               Cmdlet    Microsoft.PowerShell.Core Connects to and enters into an interactive ses...
Exit-PSHostProcess                Cmdlet    Microsoft.PowerShell.Core Closes an interactive session with a local pro...
Debug-Process                     Cmdlet    Microsoft.PowerShell.M... Debugs one or more processes running on the lo...
Get-Process                       Cmdlet    Microsoft.PowerShell.M... Gets the processes that are running on the loc...
Start-Process                     Cmdlet    Microsoft.PowerShell.M... Starts one or more processes on the local comp...
Stop-Process                      Cmdlet    Microsoft.PowerShell.M... Stops one or more running processes.
Wait-Process                      Cmdlet    Microsoft.PowerShell.M... Waits for the processes to be stopped before a...
```

Q5: What cmdlet might you use to write to a event log? (This one's possible on non-Windows operating systems, but you'll get a different answer.)

Windows Version Used
```
> Get-Help *log

Name                              Category  Module                    Synopsis
----                              --------  ------                    --------
Clear-EventLog                    Cmdlet    Microsoft.PowerShell.M... Clears all entries from specified event logs o...
Get-EventLog                      Cmdlet    Microsoft.PowerShell.M... Gets the events in an event log, or a list of ...
Limit-EventLog                    Cmdlet    Microsoft.PowerShell.M... Sets the event log properties that limit the s...
New-EventLog                      Cmdlet    Microsoft.PowerShell.M... Creates a new event log and a new event source...
Remove-EventLog                   Cmdlet    Microsoft.PowerShell.M... Deletes an event log or unregisters an event s...
Show-EventLog                     Cmdlet    Microsoft.PowerShell.M... Displays the event logs of the local or a remo...
Write-EventLog                    Cmdlet    Microsoft.PowerShell.M... Writes an event to an event log.
Disable-AppBackgroundTaskDiagn... Cmdlet    AppBackgroundTask         Disable-AppBackgroundTaskDiagnosticLog...
Enable-AppBackgroundTaskDiagno... Cmdlet    AppBackgroundTask         Enable-AppBackgroundTaskDiagnosticLog...
Get-AppxLog                       Function  Appx                      ...
Export-BinaryMiLog                Cmdlet    CimCmdlets                Export-BinaryMiLog...
Import-BinaryMiLog                Cmdlet    CimCmdlets                Import-BinaryMiLog...
Get-MpThreatCatalog               Function  Defender                  ...
Get-DtcLog                        Function  MsDtc                     ...
Reset-DtcLog                      Function  MsDtc                     ...
Set-DtcLog                        Function  MsDtc                     ...
Clear-PcsvDeviceLog               Function  PcsvDevice                ...
Get-PcsvDeviceLog                 Function  PcsvDevice                ...
Start-StorageDiagnosticLog        Function  Storage                   ...
Stop-StorageDiagnosticLog         Function  Storage                   ...
Get-WindowsUpdateLog              Function  WindowsUpdate             ...
```

Q6: You've learned that aliases are nicknames for cmdlets; what cmdlets are available to create, modifiy, export or import aliases?

```
> Get-Help *alias

Name                              Category  Module                    Synopsis
----                              --------  ------                    --------
Export-Alias                      Cmdlet    Microsoft.PowerShell.U... Exports information about currently defined al...
Get-Alias                         Cmdlet    Microsoft.PowerShell.U... Gets the aliases for the current session.
Import-Alias                      Cmdlet    Microsoft.PowerShell.U... Imports an alias list from a file.
New-Alias                         Cmdlet    Microsoft.PowerShell.U... Creates a new alias.
Set-Alias                         Cmdlet    Microsoft.PowerShell.U... Creates or changes an alias for a cmdlet or ot...
Alias                             Provider  Microsoft.PowerShell.Core Provides access to the Windows PowerShell alia...
```
Q7: Is there a way to keep a transcript pf everything you type in shell and save that transcript to a text file?
```
> Get-Help *transcript

Name                              Category  Module                    Synopsis
----                              --------  ------                    --------
Start-Transcript                  Cmdlet    Microsoft.PowerShell.Host Start-Transcript...
Stop-Transcript                   Cmdlet    Microsoft.PowerShell.Host Stop-Transcript...

> Get-Help Start-Transcript | Out-File c:\Users\client\starttranscript.txt
```
See starttranscript.txt for reference.

Q8: Windows-only: it can tale a long time to retrieve all the entries form the Security event log. How can you get only the 100 most recent entries?
```
Get-Help Get-EventLog -parameter Newest

-Newest <Int32>
    Specifies the maximum number of events that this cmdlet gets. This cmdlet gets the specified number of events,
    beginning with the newest event in the log.

    Required?                    false
    Position?                    named
    Default value                None
    Accept pipeline input?       False
    Accept wildcard characters?  false
```

Q9: Windows-only: is there a way to retrieve a list of the services that are installed on a remote computer?
```
> Get-Help *service


Name                              Category  Module                    Synopsis
----                              --------  ------                    --------
Get-Service                       Cmdlet    Microsoft.PowerShell.M... Gets the services on a local or remote computer.
New-Service                       Cmdlet    Microsoft.PowerShell.M... Creates a new Windows service.
Restart-Service                   Cmdlet    Microsoft.PowerShell.M... Stops and then starts one or more services.
Resume-Service                    Cmdlet    Microsoft.PowerShell.M... Resumes one or more suspended (paused) services.
Set-Service                       Cmdlet    Microsoft.PowerShell.M... Starts, stops, and suspends a service, and cha...
Start-Service                     Cmdlet    Microsoft.PowerShell.M... Starts one or more stopped services.
Stop-Service                      Cmdlet    Microsoft.PowerShell.M... Stops one or more running services.
Suspend-Service                   Cmdlet    Microsoft.PowerShell.M... Suspends (pauses) one or more running services.

>Get-Help Get-Service | Out-File c:\Users\client\getservice.txt
```
see getservice.txt for results.

Q10: Is there a way to see what processes are running on a remote computer (you can find the answer on non-Windows operating systems, but the command itself might not work for you.)
```
>Get-Help *process

Name                              Category  Module                    Synopsis
----                              --------  ------                    --------
Enter-PSHostProcess               Cmdlet    Microsoft.PowerShell.Core Connects to and enters into an interactive ses...
Exit-PSHostProcess                Cmdlet    Microsoft.PowerShell.Core Closes an interactive session with a local pro...
Debug-Process                     Cmdlet    Microsoft.PowerShell.M... Debugs one or more processes running on the lo...
Get-Process                       Cmdlet    Microsoft.PowerShell.M... Gets the processes that are running on the loc...
Start-Process                     Cmdlet    Microsoft.PowerShell.M... Starts one or more processes on the local comp...
Stop-Process                      Cmdlet    Microsoft.PowerShell.M... Stops one or more running processes.
Wait-Process                      Cmdlet    Microsoft.PowerShell.M... Waits for the processes to be stopped before a...

> Get-Help Get-Process | Out-File c:\Users\client\getprocess.txt
```
see getprocess.txt for details.

Q11: Examine the help file for the Out-File cmdlet. The files created by this cmdlet default to a width of how many characters? Is there a parameter that would enable you to change the width?
