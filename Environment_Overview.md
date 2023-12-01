### Environment Overview

<ins>ADMINISTRATION</ins>
* All SAS Software was installed to C:\Program Files\SASHome
* The configuration files were deployed to C:\SAS\Config\Lev1.  This location is referred to as your SAS Configuration Directory in the SAS Admin Documentation.
* There is an administrative document, Instructions.html (file:///C:/SAS/Config/Lev1/Documents/Instructions.html), that describes every deployed application, with details regarding ports, logs, and validation steps.
* You have one Unrestricted Admin user that is intended for server administration.  The tool for administration is *SAS Management Console* and you can create a profile in that utility that uses the SAS Admin account:
  * User:  sasadm@saspw
  * Password:  Orion123
* You have one Demo User that can be used when testing out the software interfaces.
  * User: sasdemo
  * Password:  Orion123
* There are many SAS Services that run to enable SAS products and processes.  They can be found in the Services tool of the Windows Server.  All SAS services begin with *SAS [Config-Lev1]*.  The all start automatically after a reboot.  A reboot will require approximately 30 minutes to complete if you are using SAS Studio.  If end users are not accessing the web server of SAS, the system will be ready in minutes.
 
<ins>USAGE</ins>
* The most common user interface for Office Analytics is **SAS Enterprise Guide**, you will find in in Start > SAS.  You can login to Enterprise Guide with SASDEMO or any local account that you add to the server and to the system.  
* [SAS Studio](http://sas-server/SASStudio) is another popular user interface.  
   
