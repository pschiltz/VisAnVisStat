# SAS Software Installation Roadmap  ** UNDER DEVELOPMENT **

Welcome!  We are happy you have chosen **SAS Office Analytics**.  This guide will walk you through the process of installation and usage, including reserving the required virtual machine from Azure (if required).  The process described in this guide is taken from the [Office Analytics 2-Machine Installation Manual](https://go.documentation.sas.com/api/docsets/oatmig/7.4/content/oatmig.pdf).
  
<ins>The only requirements for getting started is your SAS Software Order email.</ins>

**Installing and configuring SAS Office Analytics**

1. [Pre-installation tasks: Create required users and groups](Pre-install.md)
2. [Download the SAS Software Depot](Download_the_SAS_Software_Depot.md)
3. [Deploy and Configure SAS](Deploy_and_Configure.md)
4. [Invoke and Login to SAS Enterprise Guide](Enterprise_Guide.md)
   
(Post-installation Tasks)
* [Create and Add Users](Add_Users.md)
* [Environment Overview](Environment_Overview.md)
  
(Optional:  Securing a server on Azure)
If you plan to deploy to Azure, we have provided easy steps for securing the instance that will be your SAS Server.  You may have received a SAS Sizing Recommendation from your SAS Account Team, use that recommendation to select the instance type.  The default provided in the ARM template is the very smallest instance, used for example purposes, and should not be used for production deployment.

   Option 1: [Create Azure VM using Cloud Shell and ARM template](Create_Azure_VM_using_Cloud_Shell.md)  
   Option 2: [Create Azure VM using the Azure Portal](Create_VM_using_Azure_Portal.md)
