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
3.  Execute the install by pasting this command into your Powershell window (or a Command Prompt window)
```
"C:\SAS Software Depot\setup.exe" -quiet -responsefile "C:\Users\sasadm\Downloads\sdwresponse.properties"
```
