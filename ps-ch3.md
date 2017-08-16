## Notes/Workings from chapter

reference point: 3.1

Noted in the preaching that they say strictly that only Get-Help is to be used by default. Noting that 90% of the troubles are easily resolvable by prompt.

reference point: 3.2

When updating help, it can only be done by the Systems Administrator. other updates are not allowed.

For controlled environments (government networks), Save-Help is used to obtain the latest version and push it to other clients. 

## Chapter Lab

Q1) Run Update-Help and ensure that it completes without errors, so that you have a copy of the help on your local computer. You need an internet connection, and the shell needs to run under elevated privileges (which means Administrator must appear in the shell window’s title bar).

```
default
.\System32> Update-Help

form file
 .\System32> Update-Help -SourcePath [folderpath]
```

Q2) Windows-only: can you find any cmdlets capable of converting other cmdlets output into HTML?

```
> example
...
