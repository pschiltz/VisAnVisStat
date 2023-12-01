### Deploy and Configure SAS Office Analytics

This GitHub project contains a response file that was previously recorded from a typical Office Analytics install.  You will download and use this recorded response file in order to minimize the amount of interaction you will have during the installation.  

:heavy_exclamation_mark: **If you did not accept default names, passwords, or locations in prior steps, you will need to [alter the response file accordingly](#adjustments-required-for-non-default-values).**

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
copy "C:\SAS Software Depot\sid_files\sas*.txt" "C:\SAS Software Depot\sid_files\sid.txt"
"C:\SAS Software Depot\setup.exe" -quiet -wait -responsefile "C:\Users\sasadm\Downloads\sdwresponse.properties"
```
4.  The command will execute and return.  But the install and configuration will take approximately 30 minutes.  You can monitor the **SDW window launcher application** process in Task Manager to determine if it is still running.  You can also watch for the presence of c:\program files\sashome and c:\sas\config.
   
![](images/sdw.png)

**Congratulations!**  Your SAS Deployment is complete and you are ready to get started on your trial of **SAS Office Analytics**.
Suggested next steps:
* EG
* Add Users
* Tour of Environment
  
***
### Adjustments Required for Non-Default Values

If you did not take default values for the name of your VM, admin account, SAS required accounts, or any of the passwords, please edit your sdwresponse.properties file using Powershell and the commands below:
  
* To change the server name from **SAS-Server** (replace XXXXX with your selected server name)
```
(Get-Content c:\users\sasadm\downloads\sdwresponse.properties) -replace 'SAS-Server', 'XXXXX' | Set-Content c:\users\sasadm\downloads\sdwresponse.properties
```
* To change the SASSRV and SASDEMO passwords from **Orion123** (replace XXXXX with your selected password)
```
(Get-Content c:\users\sasadm\downloads\sdwresponse.properties) -replace '{sas002}1D57933958C580064BD3DCA81A33DFB2', 'XXXXX' | Set-Content c:\users\sasadm\downloads\sdwresponse.properties

```
* To change the SASADM password from **letstrySASon!** (replace XXXXX with your selected password)
```
(Get-Content c:\users\sasadm\downloads\sdwresponse.properties) -replace '{SAS002}80EA45163DAA60753AE8F0491F4AA89657541A6257A55A57', 'XXXXX' | Set-Content c:\users\sasadm\downloads\sdwresponse.properties
```
* To change the location of the **JUnit jar file** (replace XXXXX with your path including the .jar filename)
```
(Get-Content c:\users\sasadm\downloads\sdwresponse.properties) -replace 'C:\Users\sasadm\Downloads\junit-4.13.2.jar', 'XXXXX' | Set-Content c:\users\sasadm\downloads\sdwresponse.properties
```


