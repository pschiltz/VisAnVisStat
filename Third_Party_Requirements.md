### Installing required 3rd party software - JUnit and Python

1.  Download the  JUnit jar file using commands below in your PowerShell command window.
```
mkdir "c:\program files\junit"
wget https://repo1.maven.org/maven2/junit/junit/4.13.2/junit-4.13.2.jar -outfile "c:\program files\junit\junit-4.13.2.jar"
$Env:junit_path='c:\program files\junit\junit-4.13.2.jar'
```
2.  Download and execute the Python installation file using commands below in your PowerShell command window..  
```
wget https://www.python.org/ftp/python/3.13.0/python-3.13.0-amd64.exe -outfile "c:\sas software depot\python_installer.exe"
```
```
& "c:\sas software depot\python_installer.exe" /quiet InstallAllUsers=1 PrependPath=1 Include_test=0
$Env:python_path='C:\Program Files\Python313'
$filePath = "C:\Program Files\Python313\Scripts\pip.exe"
$startTime = Get-Date
while (!(Test-Path -Path $filePath)) {
    if ((New-TimeSpan -Start $startTime -End (Get-Date)).TotalSeconds -gt 300) {
        Write-Error "Timeout waiting for file '$filePath'."
        break
    }
    Start-Sleep -Seconds 1
}
```
```
& "C:\Program Files\Python313\Scripts\pip.exe" install --trusted-host pypi.org --trusted-host pypi.python.org --trusted-host files.pythonhosted.org pywin32
```
```
 & "C:\Program Files\Python313\python.exe" "C:\Program Files\Python313\Scripts\pywin32_postinstall.py" -install
```
Now, once the depot has completely downloaded, **Go to Step 4.** [Deploy and Configure SAS](Deploy_and_Configure.md)
