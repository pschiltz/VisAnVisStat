### Environment Overview

<ins>ADMINISTRATION</ins>
* All SAS Software was installed to C:\Program Files\SASHome
* The configuration files were deployed to C:\SAS\Config\Lev1.  This location is referred to as your SAS Configuration Directory in the SAS Admin Documentation.
* There is an administrative document, Instructions.html (sas_config/Lev1/Documents/Instructions.html), that describes every deployed application, with details regarding ports, logs, and validation steps.
* You have one Unrestricted Admin user that is intended for server administration.  The tool for administration is *SAS Management Console* and you can create a profile in that utility that uses the SAS Admin account:
  * User:  sasadm@saspw
  * Password:  <defined on Step 4.2 as sas_internal_pass>
* You have one Demo User that can be used when testing out the software interfaces.
  * User: sasdemo
  * Password:  <defined on Step 2.3>
* There are many SAS Services that run to enable SAS products and processes.  They can be found in the Services tool of the Windows Server.  All SAS services begin with *SAS [Config-Lev1]*.  The all start automatically after a reboot.  A reboot will require approximately 30 minutes to complete if you are using SAS Studio.  For users of Enterprise Guide, the server will be ready 5-10 minutes after reboot.
 
<ins>USAGE</ins>
*  You can login to SAS clients with SASDEMO or any local account that you add to the server and to the system.
*  Locate your Instructions.html file in sas_config\Lev1\Documents.  This file also displays in your default browser when the installation completes.  It contans links to your web-based clients in the section labeled **Web Applications**.
* **SAS Enterprise Guide**: This is a point-and-click or coding interface to the sas server compute capabilities.
* [SAS Studio](http://sas-server/SASStudio):  This is a web-based interface primarily for coders.  There are a small number of code-gen tools such as built-in Tasks and Code Snippets to get non-coders started.
* **SAS Visual Analytics and Visual Statistics**:  These are web-based, highly interactive, tools for analytics, modeling, and visualization.
   
