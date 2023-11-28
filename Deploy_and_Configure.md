### Deploy and Configure SAS Office Analytics

This GitHub project contains a response file that was previously recorded from a typical Office Analytics install.  You will download and use this recorded response file in order to minimize the amount of interaction you will have during the installation.  The default decisions that were made are explained on this page.  If you have made changes to the defaults in prior steps, you will need to alter the response file accordingly.

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

## Adjustments Required for Non-Default Values 

If you did not take default values for the name of your VM, admin account, SAS required accounts, or any of the passwords, please edit your sdwresponse.properties file as highlighted below:

