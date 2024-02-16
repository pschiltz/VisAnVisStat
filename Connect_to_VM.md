### Connect to your Virtual Machine using Remote Desktop Connection
Alternately, use any RDP emulation package.  There are many available such as MobaXterm, but MS Remote Desktop Connection is part of any Windows desktop or server OS.   
  
In this section we will login to the SAS-Server VM in order to create some required user accounts that SAS uses during the deployment.  They will be added to a SAS Server Users group and that group will be granted a priviedge on the server to allow a remote connection.
1. Locate the IP address that was assigned to your new SAS-Server instance.  Look in the Azure Portal for a Virtual Machine named **SAS-Server**.   Select it and then go the the **Connect** options located on the left panel of the portal.
2. Copy the **Public IP** address found there.
3. Go to the Seach area of your Start menu bar and search for (and open) the **Remote Desktop Connection** utility.
4. Click the "Show Options" arrow to show more input areas.  In the General tab provided enter the following:
	* Computer: **<the IP address found in step 1>**
	* User name:  **SAS-Server\sasadm**
	* Check "Allow me to save credentials"
5. Click **Connect**
6. You will be prompted for the sasadm password, which is **letstrySASon!**
<kbd>![](images/rdp.png)</kdb>
7. Once the server displays, you can exit out of the "Manage Server" screen

