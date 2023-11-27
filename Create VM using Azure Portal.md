1. Login to the [Azure Portal](https://portal.azure.com/#create/Microsoft.VirtualMachine-ARM) to begin the creation of a Virtual Machine
2. It is suggested that you create a new Resource Group for your trial resouces but this is not required if you desire to add them to an existing group

<kbd>![ ](images/resource_group.png)</kbd>

3. For the Instance Details accept defaults except:
	* Supply a "Virtual machine name" of your choosing
	* Image: Windows Server 2022 Datacenter: Azure Edition - x64 Gen2
	* User:  sasadm
	* Password:  letstrySASon!

<kbd>![](images/image_details.png)</kbd>

4. Select **Review+Create**
5. At this point you my select **Create**, or optionally modify before selecting Create
	* Networking:  Delete public IP and NIC when VM is deleted
	* Management:  Auto-shutdown
