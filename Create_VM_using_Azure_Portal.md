### Create Azure VM to use as your trial environment using the Cloud Shell and ARM template files
1. Login to the [Azure Portal](https://portal.azure.com/#create/Microsoft.VirtualMachine-ARM) **Create a Virtual Machine** page 
2. It is suggested that you create a new Resource Group for your trial resouces but this is not required if you desire to add them to an existing group

<kbd>![ ](images/resource_group.png)</kbd>

3. For the Instance Details accept defaults except:
	* Virtual machine name:  **SAS-Server**
	* Image: **Windows Server 2022 Datacenter: Azure Edition - x64 Gen2**
	* User:  **sasadm**
	* Password:  **letstrySASon!**

   :heavy_exclamation_mark: It is strongly suggested that you use these **exact values**, as the scripts that make up this resource have been coded accordingly.  If you chose to deviate, you will have the opportunity to edit the files supplied, but this could lead to deployment failures.

<kbd>![](images/image_details.png)</kbd>

4. Select **Review+Create**
5. At this point you my select **Create**, or optionally modify before selecting Create
	* Networking:  Delete public IP and NIC when VM is deleted
	* Management:  Auto-shutdown
