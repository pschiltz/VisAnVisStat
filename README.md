# SAS Software Evaluation Roadmap  

Welcome!  We are happy you have chosen to evaluate **SAS Office Analytics**.  This guide will walk you through the process of installation and usage, including securing the required virtual machine from Azure.  We have done our best to make this guide as easy and thorough as possible through scripts and automation wherever possible.  You will find that choices have been made such as machine size, name, userid and passwords.  We call this the *happy path* :relaxed:!  Feel free, if you are comfortable, to over-ride the defaults.  
  
<ins>The only requirements for getting started are an Azure subscription and a SAS Software Order email.</ins>

These are steps needed to get your SAS software installed and configured:
1. Create appropriate resources either manually using the Azure Portal or using the ARM template provided in this GitHub repository:

   Option 1: [Create Azure VM using Cloud Shell and ARM template](Create_Azure_VM_using_Cloud_Shell.md)  
   Option 2: [Create Azure VM using the Azure Portal](Create_VM_using_Azure_Portal.md)
2. [Connect to your SAS-Server VM and create required users](Connect_to_VM.md)
3. [Download the SAS Software Depot](Download_the_SAS_Software_Depot.md)
4. [Deploy and Configure SAS](Deploy_and_Configure.md)
5. [Invoke and Login to SAS Enterprise Guide](Enterprise_Guide.md)
   
(Optional)
* [Create and Add Users](Add_Users.md)
* [Environment Overview](Environment_Overview.md)
* [Delete Resources at Trial completion](Delete_Resources.md)
