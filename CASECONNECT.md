## Introduction
Case-Connect is a program to import liabilities received from credit reports from [CreditKit](https://credit.counselkit.com) into Best Case.  CounselKit client firms receive credit reports from iCreditVision via a webservice provided by CreditKit.  Most of these firms use Best Case Bankruptcy to manage some aspect of the bankruptcy matter lifecycle - particularly electronic filing.  Best Case charges a hefty fee (> $20/ea) to import credit reports from third parties because this is also one of the service ~~CIN~~ Stretto provides.  CounselKit member firms, and potentially other clients of iCreditVision would like a means of importing these credit reports into a schedule D, E or F within Best Case programatically.  This reduces the potential for human error due to typos and may dramatically increase the speed of the process and thus the value of the iCreditVision report.

## Minimum Requirements
It is imperative that the minimum requirements are meant before running the installation script.  Case Connect is a scripted solution which requires .NET, PowerShell, Windows, ODBC, TopSpeed ODBC driver and a modern and supported Windows operating system.  If any of the following requirements are not met it is almost certain that the installation script will fail.  CounselKit support staff can do custom installs on older Operating Systems or in situations where remediation needs to take place (e.g. upgrading .NET or PowerShell or AWS PowerShell modules).  These minimum requirements and specifications are for the Windows Server/Workstation which hosts the Best Case application - it is the server or workstation where you can find the executable "winbfs.exe" on a local drive.  Many firms share that local installation as a network drive to other workstations or servers.  Those workstations and servers will not be able to run the Case Connect application.  Before attempting to install Case Connect please ensure that you know the following:

1. Administrator access to the Windows Server/Workstation/Instance where
   Best Case is hosted
1. That the Server/Workstation/Instance is running Windows 2012 OS or later
1. .NET 4.7.2 or newer is
   (installed)[https://docs.microsoft.com/en-us/dotnet/framework/migration-guide/how-to-determine-which-versions-are-installed]
1. PowerShell
   (v5.1+)[https://docs.microsoft.com/en-us/powershell/scripting/install/installing-windows-powershell?view=powershell-5.1] is running
1. and finally, send CounselKit Support Staff the location of the Best Case install (e.g. C:\BestCase\ or "D:\Apps\BestCase" or whether it is inshalled) so that it can be added to the appropriate lines in the settings.json file.

## Installation
The steps to install are as follows:

1. ensure that Best Case is available locally and not via a network drive
1. ensure that the user who will run case-connect has permissions to create ODBC connections (any user can create a DSN ODBC connection as long as there isn't a Group Policy Object preventing this)
1. ensure that the **TopSpeed ODBC driver** is installed.  It can be downloaded from [here](http://softvelocity.cachefly.net/todbc/Setup_TS-ODBC-5.10.28.zip) The install key is `~~redacted~~`
1. download the installation script file from the provision URL you received via email.  The install script is named "Install-CaseConnect.ps1" and is a PowerShell script which must be run as Administrator on the Server or Workstation or instance where Best Case is locally hosted.
1. have CounselKit staff run tests to ensure connectivity to the CounselKit application resources.


## Notes
Jon Consumer
999-99-9990
10655 N Birch St
Burbank CA 91502

It may be necessary to create a local user with logon as batch user privileges.  Carbon is a PowerShell module that may be of assistance.

* [Carbon](https://www.powershellgallery.com/packages/Carbon/2.7.0)
* [granting privileges](http://get-carbon.org/Grant-Privilege.html)
