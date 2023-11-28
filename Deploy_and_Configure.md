### Deploy and Configure SAS Office Analytics

This GitHub project contains a response file that was previously recorded from a typical Office Analytics install.  You will download and use this recorded response file in order to minimize the amount of interaction you will have during the installation.  The default decisions that were made are explained on this page.  **If you have made changes to the defaults in prior steps, you will need to [alter the response file accordingly](#adjustments-required-for-non-default-values).**

1.  Download the response file stored in this GitHub repository to the SAS-Server using the link below in the Edge browser of the VM
```
https://pschiltz.github.io/SASEval/sdwresponse.properties
```
2.  Download the required JUnit jar file in the same manner
```
https://repo1.maven.org/maven2/junit/junit/4.13.2/junit-4.13.2.jar
```
3.  Execute the install by pasting this command into a Command Prompt window (if not still up, type <kdb>cmd</kdb> in the search area of your command bar) 
```
"C:\SAS Software Depot\setup.exe" -quiet -wait -responsefile "C:\Users\sasadm\Downloads\sdwresponse.properties"
```
4.  The command will execute and return.  But the install and configuration will take approximately 30 minutes.  You can monitor the XXXXX process in Task Manager to determine if it is still running.  You can also watch for the presence of c:\program files\sashome and c:\sas\config.

### Adjustments Required for Non-Default Values

If you did not take default values for the name of your VM, admin account, SAS required accounts, or any of the passwords, please edit your sdwresponse.properties file using Powershell and the commands below:
  
* To change the server name from SAS-Server (replace XXXXX with your selected server name)
```
(Get-Content c:\users\sasadm\downloads\sdwresponse.properties) -replace 'SAS-Server', 'XXXXX' | Set-Content c:\users\sasadm\downloads\sdwresponse.properties
```
* To change the SASSRV and SASDEMO passwords from Orion123 (replace XXXXX with your selected password)
```
(Get-Content c:\users\sasadm\downloads\sdwresponse.properties) -replace '{sas002}1D57933958C580064BD3DCA81A33DFB2', 'XXXXX' | Set-Content c:\users\sasadm\downloads\sdwresponse.properties

```
* To change the SASADM password from letstrySASon! (replace XXXXX with your selected password)
```
(Get-Content c:\users\sasadm\downloads\sdwresponse.properties) -replace '{SAS002}80EA45163DAA60753AE8F0491F4AA89657541A6257A55A57', 'XXXXX' | Set-Content c:\users\sasadm\downloads\sdwresponse.properties
```
note to self... these are lines that must be addressed.  
add a command after depot download that copies sid_files\sas*.txt sid.txt
replace localhost to sas-trial
ensure i have used sas-trial everywhere or use sas-server, i think i like that best actually

# Specify SAS Installation Data File
# Specify the full path to your SAS installation data file.
#SAS_INSTALLATION_DATA=<full path to file>
 SAS_INSTALLATION_DATA=c:\sas software depot\sid_files\SAS94_9CWKW3_70311680_Win_X64_Srv.txt

# Local Machine Name
# Specify the local host name information.
#os.localhost.fqdn.host.name=<text value - leave blank or remove to default on the machine where the SAS Deployment Wizard is running>
 os.localhost.fqdn.host.name=localhost
#os.localhost.host.name=<text value - leave blank or remove to default on the machine where the SAS Deployment Wizard is running>
 os.localhost.host.name=localhost

# External Account: Installer
# Specify external account credentials for the Installer account, used only to initialize the SAS Metadata Server. The credentials for this account are not persisted.
#oma.person.installer.login.userid=<user name value>
 oma.person.installer.login.userid=SAS-Trial\sasadm
#oma.person.installer.login.passwd=<password value>
 oma.person.installer.login.passwd={sas002}C7678D151D540E430D35B49715F796FF3DD47A382F2DAAD0

# External Account: SAS Spawned Servers Account
# Specify credentials for the SAS Spawned Servers account, used to launch back-end stored process and pooled workspace servers.
#oma.person.gensrvusr.login.userid=<user name value>
 oma.person.gensrvusr.login.userid=sas-trial\sassrv
#oma.person.gensrvusr.login.passwd=<password value>
 oma.person.gensrvusr.login.passwd=Orion123

# External Account: First User
# Specify an external user ID for the First User identity. The SAS Deployment Wizard does not validate credentials for this identity, so you do not enter a password.
#oma.person.demo.login.userid=<user name value>
 oma.person.demo.login.userid=sas-trial\sasdemo


# SAS Deployment Tester Server
# Specify SAS Deployment Tester Server connection information.
#server.dproserver.port=<port number value>
 server.dproserver.port=10021
#server.dproserver.junitlocation=<full path to file (optional)>
 server.dproserver.junitlocation=C:\Users\sasadm\Downloads\junit-4.13.2.jar

