### Connect to your Virtual Machine using Remote Desktop Connection
Alternately, use any RDP emulation package.  There are many available such as MobaXterm, but MS Remote Desktop Connection is part of any Windows desktop or server OS.
1. Locate the IP address that was assigned to your new SAS-Server instance.  Look in the Azure Portal for a Virtual Machine named **SAS-Server**.   Select it and then go the the **Connect** settings.
Note the **Public IP** address there for Step 3.
3. Go to Start on your desktop and locate the **Remote Desktop Connection** utility.
4. In the General tab provide the following:
	* Computer: **<the IP address found in step 1>**
	* User name:  **localhost\sasadm**
	* Check "Allow me to save credentials"
5. Click **Connect**
6. You will be prompted for the sasadm password, which is **letstrySASon!**
<kbd>![](images/rdp.png)</kdb>
