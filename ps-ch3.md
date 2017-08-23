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
