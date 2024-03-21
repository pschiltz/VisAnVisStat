### Deploy and Configure SAS Office Analytics

This GitHub project contains a response file that was previously recorded from a typical Office Analytics install.  You will download and use this recorded response file in order to remove all interaction with the SAS Deployment Wizard.

1.  Download the response file stored in this GitHub repository.  This file will be edited using environment variables set in future steps.  This response file will feed these values to the SAS Deployment Wizard. 
```
$Env:sas_depot='<INSERT THE FULL PATH TO YOUR SAS DEPOT HERE>'
wget -outfile "$Env:sas_depot\sdwresponse.properties" https://pschiltz.github.io/OfficeAnalytics/sdwresponse.properties
```
2.  Download the required JUnit jar file in the same manner
```
mkdir "c:\program files\junit"
wget https://repo1.maven.org/maven2/junit/junit/4.13.2/junit-4.13.2.jar -outfile "c:\program files\junit\junit-4.13.2.jar"
$Env:junit_path='c:\program files\junit\junit-4.13.2.jar'
```
3.  Create environment variables to store the values for your specific settings.  These will be used to edit the response file.
      * Define your configuration directory.  This directory will be created during the install.  Most commonly used:``` $Env:sas_config='C:\SAS\Config'```
      ```
      $Env:sas_config='<configuration path>'
      ```
      * Define your SAS Home directory.  This directory will be created for you.  Most commonly used:``` $Env:sashome_path='C:\Program Files\SASHome'```
      ```
      $Env:sashome_path='<installation path>'
      ```
      * Define the host name of your server.  This can be the IP address, short, or fully qualified name.  Example:```  $Env:SAS_Server='sas-server.win.sas.com'```
      ```
      $Env:SAS_Server='<server name>'
      ```
      * Define the installer account, the account that you are currently logged in as.   Example:```  $Env:installer_account='Administrator'```
      ```
      $Env:installer_account='<username>'
      ```
      * Define the password of the installer account.  Example: ``` $Env:install_pass='Orion123'```
      ```
      $Env:install_pass='<password>'
      ```
      * Define a password to set for your internal SAS accounts, including the SAS Administrator account, that are created during the configuration.  Example:```  $Env:sas_internal_pass='Orion123'```
      ```
      $Env:sas_internal_pass='<provide a password for your internal SAS accounts>'
      ```
      
5.  Make substitutions in the response file using the environment variables set above.  You should not have to edit this code.
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
   
6.  Execute the install:  
```
copy "$Env:sas_depot\sid_files\sas*.txt" "$Env:sas_depot\sid_files\sid.txt"
& "$Env:sas_depot\setup.exe" -quiet -wait -responsefile "$Env:sas_depot\sdwresponse.properties"
```
The command will execute and return.  But the install and configuration will take approximately 60 minutes.  You can monitor the **SDW window launcher application** process in Task Manager to determine if it is still running.  You can also watch for the population of your SAS installation and configuration directories.
   
![](images/sdw.png)

**Congratulations!**  Your SAS Deployment is complete and you are ready to start using **SAS Office Analytics**.
Suggested next steps:
* [Add Users](Add_Users.md)
* [Tour the Environment](Environment_Overview.md)
* [Login to SAS Enterprise Guide](Enterprise_Guide.md)
  

