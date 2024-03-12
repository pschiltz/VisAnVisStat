### Pre-installation Tasks

1. For the rest of these instructions you will need to open 3 applications:
	* Microsoft Edge
	* Powershell  (type **power** on the Windows search bar and then click the Windows PowerShell app displayed in the results)
	* Command Prompt (type **cmd** on the Windows search bar and then click the Command Prompt app displayed in the results)
2. SAS requires one external account.  This SAS General Servers User is used to start specific SAS sessions that are used by your end users.  The common practice is to make this user local to the SAS Server and name it SASSRV.  Use the commands below in Command Prompt or Powershell to create SASSRV with a default password of Orion123.  Edit the userid or password as desired.
```
net user sassrv Orion123 /add /expires:never /passwordchg:no /fullname:"SAS Server Invoker"
```
3. Additionally, we suggest making a SAS Demo User for testing and validation.
```
net user sasdemo Orion123 /add /expires:never /passwordchg:no /fullname:"SAS Demo User"
```
4. For ease of administration, we will make a SAS Server Users group and place both of our users into that group.
```
net localgroup "SAS Server Users" /add
net localgroup "SAS Server Users" sasdemo /add
net localgroup "SAS Server Users" sassrv /add
```
3. In your PowerShell window, paste the commands below to grant the SAS Server Users group to the local security policy of **Logon as a Batch Job**.
    Answer **Y** to the two prompts and then hit <kbd>Enter</kbd> to execute the last command.  
```
Install-Module -Name 'Carbon' -AllowClobber
Import-Module 'Carbon'
Grant-CPrivilege -Identity "SAS Server Users" -Privilege SeBatchLogonRight
```

Go to [Download the SAS Software Depot](Download_the_SAS_Software_Depot.md)
