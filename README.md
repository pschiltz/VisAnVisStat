# SAS Software Installation Roadmap  

Welcome!  We are happy you have chosen **SAS Office Analytics**.  This guide will walk you through the process of installation and usage, including reserving the required virtual machine from Azure (if required).  We have done our best to make this guide as easy and thorough as possible through scripts and automation wherever possible.  You will find that choices have been made such as machine size, name, userid and passwords.  We call this the *happy path* :relaxed:!  Feel free, if you are comfortable, to over-ride the defaults.  
  
<ins>The only requirements for getting started is your SAS Software Order email.</ins>

**Securing Azure hardware (if applicable)**

If you plan to deploy to Azure, we have provided easy steps for securing the instance that will be your SAS Server.  You may have received a SAS Sizing Recommendation from your SAS Account Team, use that recommendation to select the instance type.  The default provided in the ARM template is the very smallest instance, used for example purposes, and should not be used for production deployment.

   Option 1: [Create Azure VM using Cloud Shell and ARM template](Create_Azure_VM_using_Cloud_Shell.md)  
   Option 2: [Create Azure VM using the Azure Portal](Create_VM_using_Azure_Portal.md)

**Installing and configuring SAS Office Analytics**

1. [Connect to your SAS-Server VM and create required users](Connect_to_VM.md)
2. [Pre-installation tasks: Create required users and groups](Pre-install.md)
3. [Download the SAS Software Depot](Download_the_SAS_Software_Depot.md)
4. [Deploy and Configure SAS](Deploy_and_Configure.md)
5. [Invoke and Login to SAS Enterprise Guide](Enterprise_Guide.md)
   
(Post-installation Tasks)
* [Create and Add Users](Add_Users.md)
* [Environment Overview](Environment_Overview.md)
  
