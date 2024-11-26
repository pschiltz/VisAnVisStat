### Pre-installation Tasks

1. For the rest of these instructions you will need to open Powershell:
	  (type **power** on the Windows search bar and then click the Windows PowerShell app displayed in the results).  Each command can be copied with the widget on the rightmost edge of the command box.  It can be pasted into Powershell with the right mouse button.
2.  SAS requires one external account.  This SAS General Servers User is used to start specific SAS sessions that are used by your end users.  The common practice is to make this user local to the SAS Server and name it SASSRV.
      * Define the password you would like to assign to SASSRV:
      ```
      $Env:sassrv_pass = '<define SASSRV password here>'
      ```
      * Create SASSRV:
      ```
      net user sassrv $Env:sassrv_pass /add /expires:never /passwordchg:no /fullname:"SAS Server Invoker"
      ```
3. Additionally, we suggest making a SAS Demo User for testing and validation.  It will have the userid of **SASDEMO** and will share the same password that was used for SASSRV.
```
net user sasdemo $Env:sassrv_pass /add /expires:never /passwordchg:no /fullname:"SAS Demo User"
```
4. For ease of administration, we will make a SAS Server Users group and place both of our users into that group.
```
net localgroup "SAS Server Users" /add
net localgroup "SAS Server Users" sasdemo /add
net localgroup "SAS Server Users" sassrv /add
```
5. In your PowerShell window, paste the commands below to grant the SAS Server Users group to the local security policy of **Logon as a Batch Job**.
    Answer **Y** to the two prompts and then hit <kbd>Enter</kbd> to execute the last command.  
```
Install-Module -Name 'Carbon' -AllowClobber
Import-Module 'Carbon'
Grant-CPrivilege -Identity "SAS Server Users" -Privilege SeBatchLogonRight
```

Now, once the depot has completely downloaded, **Go to Step 3.** [Deploy and Configure SAS](Deploy_and_Configure.md)
