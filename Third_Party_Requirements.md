1.  Download the required JUnit jar file in the same manner
```
mkdir "c:\program files\junit"
wget https://repo1.maven.org/maven2/junit/junit/4.13.2/junit-4.13.2.jar -outfile "c:\program files\junit\junit-4.13.2.jar"
$Env:junit_path='c:\program files\junit\junit-4.13.2.jar'
```
2.  Download required Python installatio
```
& "C:\Users\sas\AppData\Local\Programs\Python\Python313\Scripts\pip.exe" install --trusted-host pypi.org --trusted-host pypi.python.org --trusted-host files.pythonhosted.org pywin32
