### Deploy and Configure SAS Office Analytics

This GitHub project contains a response file that was previously recorded from a typical Office Analytics install.  You will download and use this recorded response file in order to minimize the amount of interaction you will have during the installation.  

1.  Download the response file stored in this GitHub repository.  This file will be edited and will eventually feed values to the SAS Deployment Wizard.
```
$Env:sas_depot='c:\sas software depot'
wget -outfile "$Env:sas_depot\sdwresponse.properties" https://pschiltz.github.io/OfficeAnalytics/sdwresponse.properties
```
2.  Download the required JUnit jar file in the same manner
```
mkdir "c:\program files\junit"
wget https://repo1.maven.org/maven2/junit/junit/4.13.2/junit-4.13.2.jar -outfile "c:\program files\junit\junit-4.13.2.jar"
$Env:junit_path='c:\program files\junit\junit-4.13.2.jar'
```
3.  Create environment variables to store the values for your specific settings.  These will be used to edit the response file.
```
$Env:sas_config='<insert drive and directory to locate your configuration files>'
```
Example:``` $Env:sas_config='C:\SAS\Config'```
This directory will be created for you.
```
$Env:sashome_path='<insert drive and directory to locate your installation files>'
```
Example:``` $Env:sashome_path='C:\Program Files\SASHome'```
This directory will be created for you.
```
$Env:SAS_Server='<insert fully qualified server name here>'
```
Example:```  $Env:SAS_Server='sas-server.win.sas.com'```
```
$Env:installer_account='<insert username of installer account that you are currently logged in as>'
```
Example:```  $Env:installer_account='Administrator'```
```
$Env:install_pass='<insert password of installer account>'
```
Example: ``` $Env:install_pass='Orion123'```
```
$Env:sas_internal_pass='<provide a password for your internal SAS accounts>'
```
Example:```  $Env:sas_internal_pass='Orion123'```
This password will be set for your SASADM@SASPW admin account and other internal accounts as well during the configuration.
4.  Make substitutions in the response file using the environment variables set above.  You should not have to edit this code.
```
(Get-Content $Env:sas_depot\sdwresponse.properties) -replace 'SAS-Server', $Env:SAS_Server | Set-Content $Env:sas_depot\sdwresponse.properties
(Get-Content $Env:sas_depot\sdwresponse.properties) -replace 'sas_depot', $Env:sas_depot | Set-Content $Env:sas_depot\sdwresponse.properties
(Get-Content $Env:sas_depot\sdwresponse.properties) -replace 'sas_config', $Env:sas_config | Set-Content $Env:sas_depot\sdwresponse.properties
(Get-Content $Env:sas_depot\sdwresponse.properties) -replace 'installer_account', $Env:installer_account | Set-Content $Env:sas_depot\sdwresponse.properties
(Get-Content $Env:sas_depot\sdwresponse.properties) -replace 'install_pass', $Env:install_pass | Set-Content $Env:sas_depot\sdwresponse.properties
(Get-Content $Env:sas_depot\sdwresponse.properties) -replace 'sas_internal_pass', $Env:sas_internal_pass | Set-Content $Env:sas_depot\sdwresponse.properties
(Get-Content $Env:sas_depot\sdwresponse.properties) -replace 'sassrv_pass', $Env:sassrv_pass | Set-Content $Env:sas_depot\sdwresponse.properties
(Get-Content $Env:sas_depot\sdwresponse.properties) -replace 'junit_path', $Env:junit_path | Set-Content $Env:sas_depot\sdwresponse.properties
(Get-Content $Env:sas_depot\sdwresponse.properties) -replace 'sashome_path', $Env:sashome_path | Set-Content $Env:sas_depot\sdwresponse.properties
```
   
5.  Execute the install:  
```
copy "$Env:sas_depot\sid_files\sas*.txt" "$Env:sas_depot\sid_files\sid.txt"
& "$Env:sas_depot\setup.exe" -quiet -wait -responsefile "$Env:sas_depot\sdwresponse.properties"
```
5.  The command will execute and return.  But the install and configuration will take approximately 30 minutes.  You can monitor the **SDW window launcher application** process in Task Manager to determine if it is still running.  You can also watch for the presence of c:\program files\sashome and c:\sas\config.
   
![](images/sdw.png)

**Congratulations!**  Your SAS Deployment is complete and you are ready to get started on your trial of **SAS Office Analytics**.
Suggested next steps:
* EG
* Add Users
* Tour of Environment
  

