
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
> Get-Process

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id  SI ProcessName
-------  ------    -----      ----- -----   ------     --  -- -----------
    149       9     5664       7704 ...95     0.17   3916   0 audiodg
    133      11     4692      13828 ...45     0.13    872   1 conhost
    298      11     1100       3044 ...99     0.53    580   0 csrss
    234      14     1128       4276 ...97     0.73    652   1 csrss
    307      15     2456       8288 ...91     0.08   2816   0 dasHost
    213      13     3416       9296 ...04     0.28   2552   0 dllhost
    222      19    40800      42152 ...48     0.83    956   1 dwm
   1264      52    17084      59700 ...64     3.13   1468   1 explorer
      0       0        0          4     0               0   0 Idle
    765      19     3576      10416 ...95     1.64    760   0 lsass
    188      12     2372       6740 ...98     0.08   2848   0 msdtc
    467      63   103536      61188 ...03   124.78   1196   0 MsMpEng
    179     169     4352       2808 ...00     0.50   2616   0 NisSrv
    389      29    26476      30612   250     0.58   3960   1 OneDrive
    588      42   140412     157540 ...84     9.67   4016   1 powershell
    367      22     8068      29812 ...99     2.52   3556   1 RuntimeBroker
    601      37    18712      22196 ...88    50.16   3432   0 SearchIndexer
    620      47    40764      82180 ...97     1.48   1440   1 SearchUI
    242       9     2448       5692 ...71     0.89    752   0 services
    535      24    14828      45468 ...07     0.69    572   1 ShellExperienceHost
    365      13     3996      17268 ...44     1.13   2136   1 sihost
    238      13     3824       3164    95     0.22   2232   1 SkypeHost
     49       2      356        928 ...58     0.23    500   0 smss
    468      27     8252      11780 ...55     0.28   1636   0 spoolsv
    323      24     6052      19300 ...84     0.41    296   1 svchost
   1572      64    66504      40348 ...09    83.72    512   0 svchost
    423      25     4104      11440 ...43     0.59    556   0 svchost
    479      22    53236      64208 ...63    53.75    564   0 svchost
    542      41    14812      17692 ...00     2.69    584   0 svchost
    690      27    12480      22636 ...43     2.63    656   0 svchost
    625      20     5932      18096 ...30     2.03    824   0 svchost
    540      15     3452       8328 ...90     1.83    856   0 svchost
    962      33     7656      17564 ...57     1.14    880   0 svchost
    512      33     5872      13512 ...46     0.72   1408   0 svchost
    315      20     5076      18712 ...95     0.63   1876   0 svchost
    182      21     4348      16156 ...35     0.91   2000   0 svchost
    982       0      332      14400    69    82.33      4   0 System
    258      26     4516      13152 ...70     0.16   1368   1 taskhostw
    131      11     4504       5904    77     0.13   1960   0 VGAuthService
     94       7     1148       4920    56     0.05   1100   0 vmacthlp
    340      23     7936      14400   100     1.77   1980   0 vmtoolsd
    360      24    11136      27452   151     6.17   3936   1 vmtoolsd
     87       8      820       4112 ...95     0.08    640   0 wininit
    197       9     1908      10856 ...13     0.33    708   1 winlogon
     48       4      600       3160 ...70     0.00   1952   0 wlms
    215      13     5096      12488 ...99     6.27   2700   0 WmiPrvSE
    347       8     1660       4708 ...81     0.59   1236   0 WUDFHost
```


Q2: **(Windows Only - NO Get-WinEvent)** Display the 100 most recent entries from the Application event log (Don't use Get-WinEvent for this. We've shown you another command that will do this task)

```
Get-EventLog -LogName Application -Newest 100

Index Time          EntryType   Source                 InstanceID Message
----- ----          ---------   ------                 ---------- -------
 3253 Sep 14 12:07  0           Software Protecti...   1073742727 The Software Protection service has stopped....
 3252 Sep 14 12:07  Information Software Protecti...   1073758208 Successfully scheduled Software Protection serv...
 3251 Sep 14 12:07  0           Software Protecti...   1073742726 The Software Protection service has started....
 3250 Sep 14 12:07  Information Software Protecti...   2147484685 Time-based license remaining validity time 7926...
 3249 Sep 14 12:07  Information Software Protecti...   1073742827 The Software Protection service has completed l...
 3248 Sep 14 12:07  Information Software Protecti...   1073742890 Initialization status for service objects....
 3247 Sep 14 12:07  Information Software Protecti...   1073742724 The Software Protection service is starting....
 3246 Sep 14 11:51  Information Windows Error Rep...         1001 Fault bucket , type 0...
 3245 Sep 14 11:51  Information Windows Error Rep...         1001 Fault bucket , type 0...
 3244 Sep 14 11:51  Information Windows Error Rep...         1001 Fault bucket , type 0...
 3243 Sep 14 11:51  Information Windows Error Rep...         1001 Fault bucket , type 0...
 3242 Sep 14 11:51  Information Windows Error Rep...         1001 Fault bucket , type 0...
 3241 Sep 14 11:45  Information Wlclntfy               2147489648 The winlogon notification subscriber <SessionEn...
 3240 Sep 14 11:45  Information Wlclntfy               2147489651 The winlogon notification subscriber <SessionEn...
 3239 Sep 14 11:44  Information Windows Error Rep...         1001 Fault bucket , type 0...
 3238 Sep 14 11:44  Information Windows Error Rep...         1001 Fault bucket , type 0...
 3237 Sep 14 11:44  Information Windows Error Rep...         1001 Fault bucket , type 0...
 3236 Sep 14 11:44  Information Windows Error Rep...         1001 Fault bucket , type 0...
 3235 Sep 14 11:44  Information Windows Error Rep...         1001 Fault bucket , type 0...
 3234 Sep 14 11:37  0           Software Protecti...   1073742727 The Software Protection service has stopped....
 3233 Sep 14 11:37  Information Software Protecti...   1073758208 Successfully scheduled Software Protection serv...
 3232 Sep 14 11:37  0           Software Protecti...   1073742726 The Software Protection service has started....
 3231 Sep 14 11:37  Information Software Protecti...   2147484685 Time-based license remaining validity time 7929...
 3230 Sep 14 11:37  Information Software Protecti...   1073742827 The Software Protection service has completed l...
 3229 Sep 14 11:37  Information Software Protecti...   1073742890 Initialization status for service objects....
 3228 Sep 14 11:37  Information Software Protecti...   1073742724 The Software Protection service is starting....
 3227 Sep 14 11:15  Information Microsoft-Windows...         1000 Performance counters for the WmiApRpl (WmiApRpl...
 3226 Sep 14 11:15  Information Microsoft-Windows...         1001 Performance counters for the WmiApRpl (WmiApRpl...
 3225 Sep 14 11:10  Information VSS                          8224 The VSS service is shutting down due to idle ti...
 3224 Sep 14 11:10  Information Windows Error Rep...         1001 Fault bucket , type 0...
 3223 Sep 14 11:10  Information Windows Error Rep...         1001 Fault bucket , type 0...
 3222 Sep 14 11:09  0           Software Protecti...   1073742727 The Software Protection service has stopped....
 3221 Sep 14 11:09  Information Software Protecti...   1073758208 Successfully scheduled Software Protection serv...
 3220 Sep 14 11:09  Information Windows Search Se...   1073742827 The Windows Search Service started....
 3219 Sep 14 11:09  Information ESENT                         326 SearchIndexer (3432) Windows: The database engi...
 3218 Sep 14 11:09  0           Software Protecti...   1073742726 The Software Protection service has started....
 3217 Sep 14 11:09  Information ESENT                         105 SearchIndexer (3432) Windows: The database engi...
 3216 Sep 14 11:09  Information Software Protecti...   2147484685 Time-based license remaining validity time 7931...
 3215 Sep 14 11:09  Information Software Protecti...   1073742827 The Software Protection service has completed l...
 3214 Sep 14 11:09  Information ESENT                         102 SearchIndexer (3432) Windows: The database engi...
 3213 Sep 14 11:09  Information Software Protecti...   1073742890 Initialization status for service objects....
 3212 Sep 14 11:09  Information SecurityCenter                  1 The Windows Security Center Service has started.
 3211 Sep 14 11:09  Information Software Protecti...   1073742724 The Software Protection service is starting....
 3210 Sep 14 11:07  0           Software Protecti...   1073742727 The Software Protection service has stopped....
 3209 Sep 14 11:07  Information Software Protecti...   1073758208 Successfully scheduled Software Protection serv...
 3208 Sep 14 11:07  Information MSDTC 2                1073746026 The description for Event ID '1073746026' in So...
 3207 Sep 14 11:07  Information VMUpgradeHelper               271 Restored network configuration.
 3206 Sep 14 11:07  Information VMUpgradeHelper               258 Restoring network configuration.
 3205 Sep 14 11:07  Information Microsoft-Windows...         5617 Windows Management Instrumentation Service subs...
 3204 Sep 14 11:07  Information COM+                   1073742605 The description for Event ID '1073742605' in So...
 3203 Sep 14 11:07  0           Software Protecti...   1073742726 The Software Protection service has started....
 3202 Sep 14 11:07  Information Software Protecti...   2147484685 Time-based license remaining validity time 7932...
 3201 Sep 14 11:07  Information Software Protecti...   1073742827 The Software Protection service has completed l...
 3200 Sep 14 11:07  Information Software Protecti...   1073742890 Initialization status for service objects....
 3199 Sep 14 11:07  Information Software Protecti...   1073742724 The Software Protection service is starting....
 3198 Sep 14 11:07  Information Microsoft-Windows...         5615 Windows Management Instrumentation Service star...
 3197 Sep 14 11:07  Information VMTools                       105 The service was started.
 3196 Sep 14 11:07  Information Microsoft-Windows...         1531 The User Profile Service has started successful...
 3195 Sep 14 11:07  Information EventSystem            1073746449 The description for Event ID '1073746449' in So...
 3194 Sep 14 11:06  Information Microsoft-Windows...         1532 The User Profile Service has stopped.  ...
 3193 Sep 14 11:06  Information Microsoft-Windows...         1530 Windows detected your registry file is still in...
 3192 Sep 14 11:06  Information VMTools                       108 The service was stopped.
 3191 Sep 14 11:06  Information VMUpgradeHelper               272 Saved network configuration.
 3190 Sep 14 11:06  Information VMUpgradeHelper               260 Saving network configuration.
 3189 Sep 14 11:06  Information Wlclntfy               2147489648 The winlogon notification subscriber <SessionEn...
 3188 Sep 14 10:46  0           Software Protecti...   1073742727 The Software Protection service has stopped....
 3187 Sep 14 10:46  Information Software Protecti...   1073758208 Successfully scheduled Software Protection serv...
 3186 Sep 14 10:45  Information Windows Error Rep...         1001 Fault bucket , type 0...
 3185 Sep 14 10:45  Information Windows Error Rep...         1001 Fault bucket , type 0...
 3184 Sep 14 10:45  Information Windows Error Rep...         1001 Fault bucket , type 0...
 3183 Sep 14 10:45  Information Windows Error Rep...         1001 Fault bucket , type 0...
 3182 Sep 14 10:45  Information Windows Error Rep...         1001 Fault bucket , type 0...
 3181 Sep 14 10:45  0           Software Protecti...   1073742726 The Software Protection service has started....
 3180 Sep 14 10:45  Information Software Protecti...   2147484685 Time-based license remaining validity time 7934...
 3179 Sep 14 10:45  Information Software Protecti...   1073742827 The Software Protection service has completed l...
 3178 Sep 14 10:45  Information Software Protecti...   1073742890 Initialization status for service objects....
 3177 Sep 14 10:45  Information Software Protecti...   1073742724 The Software Protection service is starting....
 3176 Sep 14 10:42  Information Microsoft-Windows...         1000 Performance counters for the WmiApRpl (WmiApRpl...
 3175 Sep 14 10:42  Information Microsoft-Windows...         1001 Performance counters for the WmiApRpl (WmiApRpl...
 3174 Sep 14 10:41  Information VSS                          8224 The VSS service is shutting down due to idle ti...
 3173 Sep 14 10:40  Information Wlclntfy               2147489648 The winlogon notification subscriber <SessionEn...
 3172 Sep 14 10:40  Information Wlclntfy               2147489651 The winlogon notification subscriber <SessionEn...
 3171 Sep 14 10:40  0           Software Protecti...   1073742727 The Software Protection service has stopped....
 3170 Sep 14 10:40  Information Software Protecti...   1073758208 Successfully scheduled Software Protection serv...
 3169 Sep 14 10:40  Information Windows Search Se...   1073742827 The Windows Search Service started....
 3168 Sep 14 10:40  Information ESENT                         326 SearchIndexer (3916) Windows: The database engi...
 3167 Sep 14 10:40  Information ESENT                         105 SearchIndexer (3916) Windows: The database engi...
 3166 Sep 14 10:40  Information ESENT                         102 SearchIndexer (3916) Windows: The database engi...
 3165 Sep 14 10:40  Information SecurityCenter                  1 The Windows Security Center Service has started.
 3164 Sep 14 10:40  0           Software Protecti...   1073742726 The Software Protection service has started....
 3163 Sep 14 10:40  Information Software Protecti...   2147484685 Time-based license remaining validity time 7934...
 3162 Sep 14 10:40  Information Software Protecti...   1073742827 The Software Protection service has completed l...
 3161 Sep 14 10:40  Information Software Protecti...   1073742890 Initialization status for service objects....
 3160 Sep 14 10:40  Information Software Protecti...   1073742724 The Software Protection service is starting....
 3159 Sep 14 10:39  0           Software Protecti...   1073742727 The Software Protection service has stopped....
 3158 Sep 14 10:39  Information Software Protecti...   1073758208 Successfully scheduled Software Protection serv...
 3157 Sep 14 10:38  Information Software Protecti...   1073750054 The rules engine successfully re-evaluated the ...
 3156 Sep 14 10:38  0           Software Protecti...   1073742726 The Software Protection service has started....
 3155 Sep 14 10:38  Information Software Protecti...   2147484685 Time-based license remaining validity time 7935...
 3154 Sep 14 10:38  Information Software Protecti...   1073742827 The Software Protection service has completed l...
```

Q3: Display a list of all commands that are of the cmdlet type. (this is tricky-we've shown you Get-Command, but you'er going to have to read the help to find out how to narrow down the list as we've asked)

```
> Get-Command -CommandType Cmdlet

CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Add-AppxPackage                                    2.0.0.0    Appx
Cmdlet          Add-AppxProvisionedPackage                         3.0        Dism
Cmdlet          Add-AppxVolume                                     2.0.0.0    Appx
Cmdlet          Add-BitsFile                                       2.0.0.0    BitsTransfer
Cmdlet          Add-CertificateEnrollmentPolicyServer              1.0.0.0    PKI
Cmdlet          Add-Computer                                       3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Add-Content                                        3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Add-History                                        3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Add-JobTrigger                                     1.1.0.0    PSScheduledJob
Cmdlet          Add-KdsRootKey                                     1.0.0.0    Kds
Cmdlet          Add-Member                                         3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Add-PSSnapin                                       3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Add-SignerRule                                     1.0        ConfigCI
Cmdlet          Add-Type                                           3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Add-WindowsCapability                              3.0        Dism
Cmdlet          Add-WindowsDriver                                  3.0        Dism
Cmdlet          Add-WindowsImage                                   3.0        Dism
Cmdlet          Add-WindowsPackage                                 3.0        Dism
Cmdlet          Checkpoint-Computer                                3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Clear-Content                                      3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Clear-EventLog                                     3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Clear-History                                      3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Clear-Item                                         3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Clear-ItemProperty                                 3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Clear-KdsCache                                     1.0.0.0    Kds
Cmdlet          Clear-MsmqOutgoingQueue                            1.0.0.0    MSMQ
Cmdlet          Clear-MsmqQueue                                    1.0.0.0    MSMQ
Cmdlet          Clear-RecycleBin                                   3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Clear-Tpm                                          2.0.0.0    TrustedPlatformModule
Cmdlet          Clear-Variable                                     3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Clear-WindowsCorruptMountPoint                     3.0        Dism
Cmdlet          Compare-Object                                     3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Complete-BitsTransfer                              2.0.0.0    BitsTransfer
Cmdlet          Complete-DtcDiagnosticTransaction                  1.0.0.0    MsDtc
Cmdlet          Complete-Transaction                               3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Confirm-SecureBootUEFI                             2.0.0.0    SecureBoot
Cmdlet          Connect-PSSession                                  3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Connect-WSMan                                      3.0.0.0    Microsoft.WSMan.Management
Cmdlet          ConvertFrom-CIPolicy                               1.0.0.0    CIPolicy
Cmdlet          ConvertFrom-Csv                                    3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          ConvertFrom-Json                                   3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          ConvertFrom-SecureString                           3.0.0.0    Microsoft.PowerShell.Security
Cmdlet          ConvertFrom-String                                 3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          ConvertFrom-StringData                             3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Convert-Path                                       3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Convert-String                                     3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          ConvertTo-Csv                                      3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          ConvertTo-Html                                     3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          ConvertTo-Json                                     3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          ConvertTo-SecureString                             3.0.0.0    Microsoft.PowerShell.Security
Cmdlet          ConvertTo-TpmOwnerAuth                             2.0.0.0    TrustedPlatformModule
Cmdlet          ConvertTo-Xml                                      3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Copy-Item                                          3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Copy-ItemProperty                                  3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Debug-Job                                          3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Debug-Process                                      3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Debug-Runspace                                     3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Disable-AppBackgroundTaskDiagnosticLog             1.0.0.0    AppBackgroundTask
Cmdlet          Disable-ComputerRestore                            3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Disable-JobTrigger                                 1.1.0.0    PSScheduledJob
Cmdlet          Disable-PSBreakpoint                               3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Disable-PSRemoting                                 3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Disable-PSSessionConfiguration                     3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Disable-RunspaceDebug                              3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Disable-ScheduledJob                               1.1.0.0    PSScheduledJob
Cmdlet          Disable-TlsCipherSuite                             2.0.0.0    TLS
Cmdlet          Disable-TlsSessionTicketKey                        2.0.0.0    TLS
Cmdlet          Disable-TpmAutoProvisioning                        2.0.0.0    TrustedPlatformModule
Cmdlet          Disable-WindowsErrorReporting                      1.0        WindowsErrorReporting
Cmdlet          Disable-WindowsOptionalFeature                     3.0        Dism
Cmdlet          Disable-WSManCredSSP                               3.0.0.0    Microsoft.WSMan.Management
Cmdlet          Disconnect-PSSession                               3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Disconnect-WSMan                                   3.0.0.0    Microsoft.WSMan.Management
Cmdlet          Dismount-AppxVolume                                2.0.0.0    Appx
Cmdlet          Dismount-WindowsImage                              3.0        Dism
Cmdlet          Edit-CIPolicyRule                                  1.0        ConfigCI
Cmdlet          Enable-AppBackgroundTaskDiagnosticLog              1.0.0.0    AppBackgroundTask
Cmdlet          Enable-ComputerRestore                             3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Enable-JobTrigger                                  1.1.0.0    PSScheduledJob
Cmdlet          Enable-MsmqCertificate                             1.0.0.0    MSMQ
Cmdlet          Enable-PSBreakpoint                                3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Enable-PSRemoting                                  3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Enable-PSSessionConfiguration                      3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Enable-RunspaceDebug                               3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Enable-ScheduledJob                                1.1.0.0    PSScheduledJob
Cmdlet          Enable-TlsCipherSuite                              2.0.0.0    TLS
Cmdlet          Enable-TlsSessionTicketKey                         2.0.0.0    TLS
Cmdlet          Enable-TpmAutoProvisioning                         2.0.0.0    TrustedPlatformModule
Cmdlet          Enable-WindowsErrorReporting                       1.0        WindowsErrorReporting
Cmdlet          Enable-WindowsOptionalFeature                      3.0        Dism
Cmdlet          Enable-WSManCredSSP                                3.0.0.0    Microsoft.WSMan.Management
Cmdlet          Enter-PSHostProcess                                3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Enter-PSSession                                    3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Exit-PSHostProcess                                 3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Exit-PSSession                                     3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Expand-WindowsCustomDataImage                      3.0        Dism
Cmdlet          Expand-WindowsImage                                3.0        Dism
Cmdlet          Export-Alias                                       3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Export-BinaryMiLog                                 1.0.0.0    CimCmdlets
Cmdlet          Export-Certificate                                 1.0.0.0    PKI
Cmdlet          Export-Clixml                                      3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Export-Console                                     3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Export-Counter                                     3.0.0.0    Microsoft.PowerShell.Diagnostics
Cmdlet          Export-Csv                                         3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Export-FormatData                                  3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Export-ModuleMember                                3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Export-PfxCertificate                              1.0.0.0    PKI
Cmdlet          Export-PSSession                                   3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Export-StartLayout                                 1.0.0.0    StartLayout
Cmdlet          Export-TlsSessionTicketKey                         2.0.0.0    TLS
Cmdlet          Export-WindowsDriver                               3.0        Dism
Cmdlet          Export-WindowsImage                                3.0        Dism
Cmdlet          Find-Package                                       1.0.0.1    PackageManagement
Cmdlet          Find-PackageProvider                               1.0.0.1    PackageManagement
Cmdlet          ForEach-Object                                     3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Format-Custom                                      3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Format-List                                        3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Format-SecureBootUEFI                              2.0.0.0    SecureBoot
Cmdlet          Format-Table                                       3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Format-Wide                                        3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-Acl                                            3.0.0.0    Microsoft.PowerShell.Security
Cmdlet          Get-Alias                                          3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-AppLockerFileInformation                       2.0.0.0    AppLocker
Cmdlet          Get-AppLockerPolicy                                2.0.0.0    AppLocker
Cmdlet          Get-AppxDefaultVolume                              2.0.0.0    Appx
Cmdlet          Get-AppxPackage                                    2.0.0.0    Appx
Cmdlet          Get-AppxPackageManifest                            2.0.0.0    Appx
Cmdlet          Get-AppxProvisionedPackage                         3.0        Dism
Cmdlet          Get-AppxVolume                                     2.0.0.0    Appx
Cmdlet          Get-AuthenticodeSignature                          3.0.0.0    Microsoft.PowerShell.Security
Cmdlet          Get-BitsTransfer                                   2.0.0.0    BitsTransfer
Cmdlet          Get-Certificate                                    1.0.0.0    PKI
Cmdlet          Get-CertificateAutoEnrollmentPolicy                1.0.0.0    PKI
Cmdlet          Get-CertificateEnrollmentPolicyServer              1.0.0.0    PKI
Cmdlet          Get-CertificateNotificationTask                    1.0.0.0    PKI
Cmdlet          Get-ChildItem                                      3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Get-CimAssociatedInstance                          1.0.0.0    CimCmdlets
Cmdlet          Get-CimClass                                       1.0.0.0    CimCmdlets
Cmdlet          Get-CimInstance                                    1.0.0.0    CimCmdlets
Cmdlet          Get-CimSession                                     1.0.0.0    CimCmdlets
Cmdlet          Get-CIPolicy                                       1.0        ConfigCI
Cmdlet          Get-CIPolicyInfo                                   1.0        ConfigCI
Cmdlet          Get-Clipboard                                      3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Get-CmsMessage                                     3.0.0.0    Microsoft.PowerShell.Security
Cmdlet          Get-Command                                        3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Get-ComputerRestorePoint                           3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Get-Content                                        3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Get-ControlPanelItem                               3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Get-Counter                                        3.0.0.0    Microsoft.PowerShell.Diagnostics
Cmdlet          Get-Credential                                     3.0.0.0    Microsoft.PowerShell.Security
Cmdlet          Get-Culture                                        3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-DAPolicyChange                                 2.0.0.0    NetSecurity
Cmdlet          Get-Date                                           3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-Event                                          3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-EventLog                                       3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Get-EventSubscriber                                3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-ExecutionPolicy                                3.0.0.0    Microsoft.PowerShell.Security
Cmdlet          Get-FormatData                                     3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-Help                                           3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Get-History                                        3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Get-Host                                           3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-HotFix                                         3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Get-Item                                           3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Get-ItemProperty                                   3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Get-ItemPropertyValue                              3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Get-Job                                            3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Get-JobTrigger                                     1.1.0.0    PSScheduledJob
Cmdlet          Get-KdsConfiguration                               1.0.0.0    Kds
Cmdlet          Get-KdsRootKey                                     1.0.0.0    Kds
Cmdlet          Get-Location                                       3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Get-Member                                         3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-Module                                         3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Get-MsmqCertificate                                1.0.0.0    MSMQ
Cmdlet          Get-MsmqOutgoingQueue                              1.0.0.0    MSMQ
Cmdlet          Get-MsmqQueue                                      1.0.0.0    MSMQ
Cmdlet          Get-MsmqQueueACL                                   1.0.0.0    MSMQ
Cmdlet          Get-MsmqQueueManager                               1.0.0.0    MSMQ
Cmdlet          Get-MsmqQueueManagerACL                            1.0.0.0    MSMQ
Cmdlet          Get-Package                                        1.0.0.1    PackageManagement
Cmdlet          Get-PackageProvider                                1.0.0.1    PackageManagement
Cmdlet          Get-PackageSource                                  1.0.0.1    PackageManagement
Cmdlet          Get-PfxCertificate                                 3.0.0.0    Microsoft.PowerShell.Security
Cmdlet          Get-PfxData                                        1.0.0.0    PKI
Cmdlet          Get-Process                                        3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Get-PSBreakpoint                                   3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-PSCallStack                                    3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-PSDrive                                        3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Get-PSHostProcessInfo                              3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Get-PSProvider                                     3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Get-PSReadlineKeyHandler                           1.1        PSReadline
Cmdlet          Get-PSReadlineOption                               1.1        PSReadline
Cmdlet          Get-PSSession                                      3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Get-PSSessionCapability                            3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Get-PSSessionConfiguration                         3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Get-PSSnapin                                       3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Get-Random                                         3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-Runspace                                       3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-RunspaceDebug                                  3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-ScheduledJob                                   1.1.0.0    PSScheduledJob
Cmdlet          Get-ScheduledJobOption                             1.1.0.0    PSScheduledJob
Cmdlet          Get-SecureBootPolicy                               2.0.0.0    SecureBoot
Cmdlet          Get-SecureBootUEFI                                 2.0.0.0    SecureBoot
Cmdlet          Get-Service                                        3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Get-SystemDriver                                   1.0        ConfigCI
Cmdlet          Get-TlsCipherSuite                                 2.0.0.0    TLS
Cmdlet          Get-Tpm                                            2.0.0.0    TrustedPlatformModule
Cmdlet          Get-TpmEndorsementKeyInfo                          2.0.0.0    TrustedPlatformModule
Cmdlet          Get-TpmSupportedFeature                            2.0.0.0    TrustedPlatformModule
Cmdlet          Get-TraceSource                                    3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-Transaction                                    3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Get-TroubleshootingPack                            1.0.0.0    TroubleshootingPack
Cmdlet          Get-TypeData                                       3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-UICulture                                      3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-Unique                                         3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-Variable                                       3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-WIMBootEntry                                   3.0        Dism
Cmdlet          Get-WinAcceptLanguageFromLanguageListOptOut        2.0.0.0    International
Cmdlet          Get-WinCultureFromLanguageListOptOut               2.0.0.0    International
Cmdlet          Get-WinDefaultInputMethodOverride                  2.0.0.0    International
Cmdlet          Get-WindowsCapability                              3.0        Dism
Cmdlet          Get-WindowsDriver                                  3.0        Dism
Cmdlet          Get-WindowsEdition                                 3.0        Dism
Cmdlet          Get-WindowsErrorReporting                          1.0        WindowsErrorReporting
Cmdlet          Get-WindowsImage                                   3.0        Dism
Cmdlet          Get-WindowsImageContent                            3.0        Dism
Cmdlet          Get-WindowsOptionalFeature                         3.0        Dism
Cmdlet          Get-WindowsPackage                                 3.0        Dism
Cmdlet          Get-WindowsSearchSetting                           1.0.0.0    WindowsSearch
Cmdlet          Get-WinEvent                                       3.0.0.0    Microsoft.PowerShell.Diagnostics
Cmdlet          Get-WinHomeLocation                                2.0.0.0    International
Cmdlet          Get-WinLanguageBarOption                           2.0.0.0    International
Cmdlet          Get-WinSystemLocale                                2.0.0.0    International
Cmdlet          Get-WinUILanguageOverride                          2.0.0.0    International
Cmdlet          Get-WinUserLanguageList                            2.0.0.0    International
Cmdlet          Get-WmiObject                                      3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Get-WSManCredSSP                                   3.0.0.0    Microsoft.WSMan.Management
Cmdlet          Get-WSManInstance                                  3.0.0.0    Microsoft.WSMan.Management
Cmdlet          Group-Object                                       3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Import-Alias                                       3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Import-BinaryMiLog                                 1.0.0.0    CimCmdlets
Cmdlet          Import-Certificate                                 1.0.0.0    PKI
Cmdlet          Import-Clixml                                      3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Import-Counter                                     3.0.0.0    Microsoft.PowerShell.Diagnostics
Cmdlet          Import-Csv                                         3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Import-LocalizedData                               3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Import-Module                                      3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Import-PackageProvider                             1.0.0.1    PackageManagement
Cmdlet          Import-PfxCertificate                              1.0.0.0    PKI
Cmdlet          Import-PSSession                                   3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Import-StartLayout                                 1.0.0.0    StartLayout
Cmdlet          Import-TpmOwnerAuth                                2.0.0.0    TrustedPlatformModule
Cmdlet          Initialize-Tpm                                     2.0.0.0    TrustedPlatformModule
Cmdlet          Install-Package                                    1.0.0.1    PackageManagement
Cmdlet          Install-PackageProvider                            1.0.0.1    PackageManagement
Cmdlet          Invoke-CimMethod                                   1.0.0.0    CimCmdlets
Cmdlet          Invoke-Command                                     3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Invoke-DscResource                                 1.1        PSDesiredStateConfiguration
Cmdlet          Invoke-Expression                                  3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Invoke-History                                     3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Invoke-Item                                        3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Invoke-RestMethod                                  3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Invoke-TroubleshootingPack                         1.0.0.0    TroubleshootingPack
Cmdlet          Invoke-WebRequest                                  3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Invoke-WmiMethod                                   3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Invoke-WSManAction                                 3.0.0.0    Microsoft.WSMan.Management
Cmdlet          Join-DtcDiagnosticResourceManager                  1.0.0.0    MsDtc
Cmdlet          Join-Path                                          3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Limit-EventLog                                     3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Measure-Command                                    3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Measure-Object                                     3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Merge-CIPolicy                                     1.0        ConfigCI
Cmdlet          Mount-AppxVolume                                   2.0.0.0    Appx
Cmdlet          Mount-WindowsImage                                 3.0        Dism
Cmdlet          Move-AppxPackage                                   2.0.0.0    Appx
Cmdlet          Move-Item                                          3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Move-ItemProperty                                  3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Move-MsmqMessage                                   1.0.0.0    MSMQ
Cmdlet          New-Alias                                          3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          New-AppLockerPolicy                                2.0.0.0    AppLocker
Cmdlet          New-CertificateNotificationTask                    1.0.0.0    PKI
Cmdlet          New-CimInstance                                    1.0.0.0    CimCmdlets
Cmdlet          New-CimSession                                     1.0.0.0    CimCmdlets
Cmdlet          New-CimSessionOption                               1.0.0.0    CimCmdlets
Cmdlet          New-CIPolicy                                       1.0        ConfigCI
Cmdlet          New-CIPolicyRule                                   1.0        ConfigCI
Cmdlet          New-DtcDiagnosticTransaction                       1.0.0.0    MsDtc
Cmdlet          New-Event                                          3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          New-EventLog                                       3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          New-Item                                           3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          New-ItemProperty                                   3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          New-JobTrigger                                     1.1.0.0    PSScheduledJob
Cmdlet          New-Module                                         3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          New-ModuleManifest                                 3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          New-MsmqMessage                                    1.0.0.0    MSMQ
Cmdlet          New-MsmqQueue                                      1.0.0.0    MSMQ
Cmdlet          New-NetIPsecAuthProposal                           2.0.0.0    NetSecurity
Cmdlet          New-NetIPsecMainModeCryptoProposal                 2.0.0.0    NetSecurity
Cmdlet          New-NetIPsecQuickModeCryptoProposal                2.0.0.0    NetSecurity
Cmdlet          New-Object                                         3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          New-PSDrive                                        3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          New-PSRoleCapabilityFile                           3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          New-PSSession                                      3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          New-PSSessionConfigurationFile                     3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          New-PSSessionOption                                3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          New-PSTransportOption                              3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          New-PSWorkflowExecutionOption                      2.0.0.0    PSWorkflow
Cmdlet          New-ScheduledJobOption                             1.1.0.0    PSScheduledJob
Cmdlet          New-SelfSignedCertificate                          1.0.0.0    PKI
Cmdlet          New-Service                                        3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          New-TimeSpan                                       3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          New-TlsSessionTicketKey                            2.0.0.0    TLS
Cmdlet          New-Variable                                       3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          New-WebServiceProxy                                3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          New-WindowsCustomImage                             3.0        Dism
Cmdlet          New-WindowsImage                                   3.0        Dism
Cmdlet          New-WinEvent                                       3.0.0.0    Microsoft.PowerShell.Diagnostics
Cmdlet          New-WinUserLanguageList                            2.0.0.0    International
Cmdlet          New-WSManInstance                                  3.0.0.0    Microsoft.WSMan.Management
Cmdlet          New-WSManSessionOption                             3.0.0.0    Microsoft.WSMan.Management
Cmdlet          Optimize-WindowsImage                              3.0        Dism
Cmdlet          Out-Default                                        3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Out-File                                           3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Out-GridView                                       3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Out-Host                                           3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Out-Null                                           3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Out-Printer                                        3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Out-String                                         3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Pop-Location                                       3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Protect-CmsMessage                                 3.0.0.0    Microsoft.PowerShell.Security
Cmdlet          Publish-DscConfiguration                           1.1        PSDesiredStateConfiguration
Cmdlet          Push-Location                                      3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Read-Host                                          3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Receive-DtcDiagnosticTransaction                   1.0.0.0    MsDtc
Cmdlet          Receive-Job                                        3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Receive-MsmqQueue                                  1.0.0.0    MSMQ
Cmdlet          Receive-PSSession                                  3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Register-ArgumentCompleter                         3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Register-CimIndicationEvent                        1.0.0.0    CimCmdlets
Cmdlet          Register-EngineEvent                               3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Register-ObjectEvent                               3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Register-PackageSource                             1.0.0.1    PackageManagement
Cmdlet          Register-PSSessionConfiguration                    3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Register-ScheduledJob                              1.1.0.0    PSScheduledJob
Cmdlet          Register-WmiEvent                                  3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Remove-AppxPackage                                 2.0.0.0    Appx
Cmdlet          Remove-AppxProvisionedPackage                      3.0        Dism
Cmdlet          Remove-AppxVolume                                  2.0.0.0    Appx
Cmdlet          Remove-BitsTransfer                                2.0.0.0    BitsTransfer
Cmdlet          Remove-CertificateEnrollmentPolicyServer           1.0.0.0    PKI
Cmdlet          Remove-CertificateNotificationTask                 1.0.0.0    PKI
Cmdlet          Remove-CimInstance                                 1.0.0.0    CimCmdlets
Cmdlet          Remove-CimSession                                  1.0.0.0    CimCmdlets
Cmdlet          Remove-CIPolicyRule                                1.0        ConfigCI
Cmdlet          Remove-Computer                                    3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Remove-Event                                       3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Remove-EventLog                                    3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Remove-Item                                        3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Remove-ItemProperty                                3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Remove-Job                                         3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Remove-JobTrigger                                  1.1.0.0    PSScheduledJob
Cmdlet          Remove-Module                                      3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Remove-MsmqCertificate                             1.0.0.0    MSMQ
Cmdlet          Remove-MsmqQueue                                   1.0.0.0    MSMQ
Cmdlet          Remove-PSBreakpoint                                3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Remove-PSDrive                                     3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Remove-PSReadlineKeyHandler                        1.1        PSReadline
Cmdlet          Remove-PSSession                                   3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Remove-PSSnapin                                    3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Remove-TypeData                                    3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Remove-Variable                                    3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Remove-WindowsCapability                           3.0        Dism
Cmdlet          Remove-WindowsDriver                               3.0        Dism
Cmdlet          Remove-WindowsImage                                3.0        Dism
Cmdlet          Remove-WindowsPackage                              3.0        Dism
Cmdlet          Remove-WmiObject                                   3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Remove-WSManInstance                               3.0.0.0    Microsoft.WSMan.Management
Cmdlet          Rename-Computer                                    3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Rename-Item                                        3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Rename-ItemProperty                                3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Repair-WindowsImage                                3.0        Dism
Cmdlet          Reset-ComputerMachinePassword                      3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Resolve-DnsName                                    1.0.0.0    DnsClient
Cmdlet          Resolve-Path                                       3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Restart-Computer                                   3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Restart-Service                                    3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Restore-Computer                                   3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Resume-BitsTransfer                                2.0.0.0    BitsTransfer
Cmdlet          Resume-Job                                         3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Resume-MsmqOutgoingQueue                           1.0.0.0    MSMQ
Cmdlet          Resume-Service                                     3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Save-Help                                          3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Save-Package                                       1.0.0.1    PackageManagement
Cmdlet          Save-WindowsImage                                  3.0        Dism
Cmdlet          Select-Object                                      3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Select-String                                      3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Select-Xml                                         3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Send-DtcDiagnosticTransaction                      1.0.0.0    MsDtc
Cmdlet          Send-MailMessage                                   3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Send-MsmqQueue                                     1.0.0.0    MSMQ
Cmdlet          Set-Acl                                            3.0.0.0    Microsoft.PowerShell.Security
Cmdlet          Set-Alias                                          3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Set-AppBackgroundTaskResourcePolicy                1.0.0.0    AppBackgroundTask
Cmdlet          Set-AppLockerPolicy                                2.0.0.0    AppLocker
Cmdlet          Set-AppxDefaultVolume                              2.0.0.0    Appx
Cmdlet          Set-AppXProvisionedDataFile                        3.0        Dism
Cmdlet          Set-AuthenticodeSignature                          3.0.0.0    Microsoft.PowerShell.Security
Cmdlet          Set-BitsTransfer                                   2.0.0.0    BitsTransfer
Cmdlet          Set-CertificateAutoEnrollmentPolicy                1.0.0.0    PKI
Cmdlet          Set-CimInstance                                    1.0.0.0    CimCmdlets
Cmdlet          Set-CIPolicyVersion                                1.0        ConfigCI
Cmdlet          Set-Clipboard                                      3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Set-Content                                        3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Set-Culture                                        2.0.0.0    International
Cmdlet          Set-Date                                           3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Set-DscLocalConfigurationManager                   1.1        PSDesiredStateConfiguration
Cmdlet          Set-ExecutionPolicy                                3.0.0.0    Microsoft.PowerShell.Security
Cmdlet          Set-HVCIOptions                                    1.0        ConfigCI
Cmdlet          Set-Item                                           3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Set-ItemProperty                                   3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Set-JobTrigger                                     1.1.0.0    PSScheduledJob
Cmdlet          Set-KdsConfiguration                               1.0.0.0    Kds
Cmdlet          Set-Location                                       3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Set-MsmqQueue                                      1.0.0.0    MSMQ
Cmdlet          Set-MsmqQueueACL                                   1.0.0.0    MSMQ
Cmdlet          Set-MsmqQueueManager                               1.0.0.0    MSMQ
Cmdlet          Set-MsmqQueueManagerACL                            1.0.0.0    MSMQ
Cmdlet          Set-PackageSource                                  1.0.0.1    PackageManagement
Cmdlet          Set-PSBreakpoint                                   3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Set-PSDebug                                        3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Set-PSReadlineKeyHandler                           1.1        PSReadline
Cmdlet          Set-PSReadlineOption                               1.1        PSReadline
Cmdlet          Set-PSSessionConfiguration                         3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Set-RuleOption                                     1.0        ConfigCI
Cmdlet          Set-ScheduledJob                                   1.1.0.0    PSScheduledJob
Cmdlet          Set-ScheduledJobOption                             1.1.0.0    PSScheduledJob
Cmdlet          Set-SecureBootUEFI                                 2.0.0.0    SecureBoot
Cmdlet          Set-Service                                        3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Set-StrictMode                                     3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Set-TpmOwnerAuth                                   2.0.0.0    TrustedPlatformModule
Cmdlet          Set-TraceSource                                    3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Set-Variable                                       3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Set-WinAcceptLanguageFromLanguageListOptOut        2.0.0.0    International
Cmdlet          Set-WinCultureFromLanguageListOptOut               2.0.0.0    International
Cmdlet          Set-WinDefaultInputMethodOverride                  2.0.0.0    International
Cmdlet          Set-WindowsEdition                                 3.0        Dism
Cmdlet          Set-WindowsProductKey                              3.0        Dism
Cmdlet          Set-WindowsSearchSetting                           1.0.0.0    WindowsSearch
Cmdlet          Set-WinHomeLocation                                2.0.0.0    International
Cmdlet          Set-WinLanguageBarOption                           2.0.0.0    International
Cmdlet          Set-WinSystemLocale                                2.0.0.0    International
Cmdlet          Set-WinUILanguageOverride                          2.0.0.0    International
Cmdlet          Set-WinUserLanguageList                            2.0.0.0    International
Cmdlet          Set-WmiInstance                                    3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Set-WSManInstance                                  3.0.0.0    Microsoft.WSMan.Management
Cmdlet          Set-WSManQuickConfig                               3.0.0.0    Microsoft.WSMan.Management
Cmdlet          Show-Command                                       3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Show-ControlPanelItem                              3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Show-EventLog                                      3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Sort-Object                                        3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Split-Path                                         3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Split-WindowsImage                                 3.0        Dism
Cmdlet          Start-BitsTransfer                                 2.0.0.0    BitsTransfer
Cmdlet          Start-DscConfiguration                             1.1        PSDesiredStateConfiguration
Cmdlet          Start-DtcDiagnosticResourceManager                 1.0.0.0    MsDtc
Cmdlet          Start-Job                                          3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Start-Process                                      3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Start-Service                                      3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Start-Sleep                                        3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Start-Transaction                                  3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Start-Transcript                                   3.0.0.0    Microsoft.PowerShell.Host
Cmdlet          Stop-Computer                                      3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Stop-DtcDiagnosticResourceManager                  1.0.0.0    MsDtc
Cmdlet          Stop-Job                                           3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Stop-Process                                       3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Stop-Service                                       3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Stop-Transcript                                    3.0.0.0    Microsoft.PowerShell.Host
Cmdlet          Suspend-BitsTransfer                               2.0.0.0    BitsTransfer
Cmdlet          Suspend-Job                                        3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Suspend-MsmqOutgoingQueue                          1.0.0.0    MSMQ
Cmdlet          Suspend-Service                                    3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Switch-Certificate                                 1.0.0.0    PKI
Cmdlet          Tee-Object                                         3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Test-AppLockerPolicy                               2.0.0.0    AppLocker
Cmdlet          Test-Certificate                                   1.0.0.0    PKI
Cmdlet          Test-ComputerSecureChannel                         3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Test-Connection                                    3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Test-DscConfiguration                              1.1        PSDesiredStateConfiguration
Cmdlet          Test-KdsRootKey                                    1.0.0.0    Kds
Cmdlet          Test-ModuleManifest                                3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Test-Path                                          3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Test-PSSessionConfigurationFile                    3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Test-WSMan                                         3.0.0.0    Microsoft.WSMan.Management
Cmdlet          Trace-Command                                      3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Unblock-File                                       3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Unblock-Tpm                                        2.0.0.0    TrustedPlatformModule
Cmdlet          Undo-DtcDiagnosticTransaction                      1.0.0.0    MsDtc
Cmdlet          Undo-Transaction                                   3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Uninstall-Package                                  1.0.0.1    PackageManagement
Cmdlet          Unprotect-CmsMessage                               3.0.0.0    Microsoft.PowerShell.Security
Cmdlet          Unregister-Event                                   3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Unregister-PackageSource                           1.0.0.1    PackageManagement
Cmdlet          Unregister-PSSessionConfiguration                  3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Unregister-ScheduledJob                            1.1.0.0    PSScheduledJob
Cmdlet          Update-FormatData                                  3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Update-Help                                        3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Update-List                                        3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Update-TypeData                                    3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Update-WIMBootEntry                                3.0        Dism
Cmdlet          Use-Transaction                                    3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Use-WindowsUnattend                                3.0        Dism
Cmdlet          Wait-Debugger                                      3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Wait-Event                                         3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Wait-Job                                           3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Wait-Process                                       3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Where-Object                                       3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Write-Debug                                        3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Write-Error                                        3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Write-EventLog                                     3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Write-Host                                         3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Write-Information                                  3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Write-Output                                       3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Write-Progress                                     3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Write-Verbose                                      3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Write-Warning                                      3.1.0.0    Microsoft.PowerShell.Utility
```

Q4: Display a list of all aliases

```
> Get-Alias

CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           % -> ForEach-Object
Alias           ? -> Where-Object
Alias           ac -> Add-Content
Alias           asnp -> Add-PSSnapin
Alias           cat -> Get-Content
Alias           cd -> Set-Location
Alias           CFS -> ConvertFrom-String                          3.1.0.0    Microsoft.PowerShell.Utility
Alias           chdir -> Set-Location
Alias           clc -> Clear-Content
Alias           clear -> Clear-Host
Alias           clhy -> Clear-History
Alias           cli -> Clear-Item
Alias           clp -> Clear-ItemProperty
Alias           cls -> Clear-Host
Alias           clv -> Clear-Variable
Alias           cnsn -> Connect-PSSession
Alias           compare -> Compare-Object
Alias           copy -> Copy-Item
Alias           cp -> Copy-Item
Alias           cpi -> Copy-Item
Alias           cpp -> Copy-ItemProperty
Alias           curl -> Invoke-WebRequest
Alias           cvpa -> Convert-Path
Alias           dbp -> Disable-PSBreakpoint
Alias           del -> Remove-Item
Alias           diff -> Compare-Object
Alias           dir -> Get-ChildItem
Alias           dnsn -> Disconnect-PSSession
Alias           ebp -> Enable-PSBreakpoint
Alias           echo -> Write-Output
Alias           epal -> Export-Alias
Alias           epcsv -> Export-Csv
Alias           epsn -> Export-PSSession
Alias           erase -> Remove-Item
Alias           etsn -> Enter-PSSession
Alias           exsn -> Exit-PSSession
Alias           fc -> Format-Custom
Alias           fhx -> Format-Hex                                  3.1.0.0    Microsoft.PowerShell.Utility
Alias           fl -> Format-List
Alias           foreach -> ForEach-Object
Alias           ft -> Format-Table
Alias           fw -> Format-Wide
Alias           gal -> Get-Alias
Alias           gbp -> Get-PSBreakpoint
Alias           gc -> Get-Content
Alias           gcb -> Get-Clipboard                               3.1.0.0    Microsoft.PowerShell.Management
Alias           gci -> Get-ChildItem
Alias           gcm -> Get-Command
Alias           gcs -> Get-PSCallStack
Alias           gdr -> Get-PSDrive
Alias           ghy -> Get-History
Alias           gi -> Get-Item
Alias           gjb -> Get-Job
Alias           gl -> Get-Location
Alias           gm -> Get-Member
Alias           gmo -> Get-Module
Alias           gp -> Get-ItemProperty
Alias           gps -> Get-Process
Alias           gpv -> Get-ItemPropertyValue
Alias           group -> Group-Object
Alias           gsn -> Get-PSSession
Alias           gsnp -> Get-PSSnapin
Alias           gsv -> Get-Service
Alias           gu -> Get-Unique
Alias           gv -> Get-Variable
Alias           gwmi -> Get-WmiObject
Alias           h -> Get-History
Alias           history -> Get-History
Alias           icm -> Invoke-Command
Alias           iex -> Invoke-Expression
Alias           ihy -> Invoke-History
Alias           ii -> Invoke-Item
Alias           ipal -> Import-Alias
Alias           ipcsv -> Import-Csv
Alias           ipmo -> Import-Module
Alias           ipsn -> Import-PSSession
Alias           irm -> Invoke-RestMethod
Alias           ise -> powershell_ise.exe
Alias           iwmi -> Invoke-WmiMethod
Alias           iwr -> Invoke-WebRequest
Alias           kill -> Stop-Process
Alias           lp -> Out-Printer
Alias           ls -> Get-ChildItem
Alias           man -> help
Alias           md -> mkdir
Alias           measure -> Measure-Object
Alias           mi -> Move-Item
Alias           mount -> New-PSDrive
Alias           move -> Move-Item
Alias           mp -> Move-ItemProperty
Alias           mv -> Move-Item
Alias           nal -> New-Alias
Alias           ndr -> New-PSDrive
Alias           ni -> New-Item
Alias           nmo -> New-Module
Alias           npssc -> New-PSSessionConfigurationFile
Alias           nsn -> New-PSSession
Alias           nv -> New-Variable
Alias           ogv -> Out-GridView
Alias           oh -> Out-Host
Alias           popd -> Pop-Location
Alias           ps -> Get-Process
Alias           pushd -> Push-Location
Alias           pwd -> Get-Location
Alias           r -> Invoke-History
Alias           rbp -> Remove-PSBreakpoint
Alias           rcjb -> Receive-Job
Alias           rcsn -> Receive-PSSession
Alias           rd -> Remove-Item
Alias           rdr -> Remove-PSDrive
Alias           ren -> Rename-Item
Alias           ri -> Remove-Item
Alias           rjb -> Remove-Job
Alias           rm -> Remove-Item
Alias           rmdir -> Remove-Item
Alias           rmo -> Remove-Module
Alias           rni -> Rename-Item
Alias           rnp -> Rename-ItemProperty
Alias           rp -> Remove-ItemProperty
Alias           rsn -> Remove-PSSession
Alias           rsnp -> Remove-PSSnapin
Alias           rujb -> Resume-Job
Alias           rv -> Remove-Variable
Alias           rvpa -> Resolve-Path
Alias           rwmi -> Remove-WmiObject
Alias           sajb -> Start-Job
Alias           sal -> Set-Alias
Alias           saps -> Start-Process
Alias           sasv -> Start-Service
Alias           sbp -> Set-PSBreakpoint
Alias           sc -> Set-Content
Alias           scb -> Set-Clipboard                               3.1.0.0    Microsoft.PowerShell.Management
Alias           select -> Select-Object
Alias           set -> Set-Variable
Alias           shcm -> Show-Command
Alias           si -> Set-Item
Alias           sl -> Set-Location
Alias           sleep -> Start-Sleep
Alias           sls -> Select-String
Alias           sort -> Sort-Object
Alias           sp -> Set-ItemProperty
Alias           spjb -> Stop-Job
Alias           spps -> Stop-Process
Alias           spsv -> Stop-Service
Alias           start -> Start-Process
Alias           sujb -> Suspend-Job
Alias           sv -> Set-Variable
Alias           swmi -> Set-WmiInstance
Alias           tee -> Tee-Object
Alias           trcm -> Trace-Command
Alias           type -> Get-Content
Alias           wget -> Invoke-WebRequest
Alias           where -> Where-Object
Alias           wjb -> Wait-Job
Alias           write -> Write-Output
```

Q5: (Windows Only, Linux with wine installs okay) Make a new alias, so you can run np to launch Notepad form a PowerShell Prompt.

```
> Set-Alias -Name np notepad.exe

used np to boot Notepad
```

Q6: (again Windows Only) Display a list of services that begin with the letter M. Again, read the help for the necessary command-and don't forget the asterisk is a near universal wildcard in PowerShell.

```
> Get-Service -Name M*

Status   Name               DisplayName
------   ----               -----------
Stopped  MapsBroker         Downloaded Maps Manager
Stopped  MozillaMaintenance Mozilla Maintenance Service
Running  MpsSvc             Windows Firewall
Running  MSDTC              Distributed Transaction Coordinator
Stopped  MSiSCSI            Microsoft iSCSI Initiator Service
Stopped  msiserver          Windows Installer
```

Q7: (Windows Only, Firewall rules) Display a list of all Windows Firewall rules. You'll need to use Help or Get-Command to discover the necessary cmdlet.

```

```

Q8: (Windows Only, Firewall rules) Display a list only of inbound Windows Firewall rules. you can use the same cmdlet as in the previous task, but you'll need to read its help to discover the necessary parameter and its allowable values.

```

```

Document Made By: Corey John Clayton  
Derived From: Chapter 4, Learn Windows PowerShell in a Month of Lunches, Third Edition. Don Jones and Jeffery Hicks  
Completed On: 20170914

Copyright 2017, Manning Publications Co. All Rights Reserved
