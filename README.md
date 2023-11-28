# SAS Software Evaluation Roadmap  

Welcome!  We are happy you have chosen to evaluate **SAS Office Analytics**.  This guide will walk you through the process of installation and usage, including securing the required virtual machine from Azure.  We have done our best to make this guide as easy and thorough as possible through scripts and automation wherever possible.  You will find that choices have been made such as machine size, name, userid and passwords.  We call this the *happy path* :relaxed:!  Feel free, if you are comfortable, to over-ride the defaults.  
  
<ins>The only requirements for getting started are an Azure subscription and a SAS Software Order email.</ins>

These are steps needed to get your SAS software installed and configured:
* Create appropriate resources either manually using the Azure Portal or using the ARM template provided in this GitHub repository:

  * Option 1: [Create Azure VM using Cloud Shell and ARM template](Create_Azure_VM_using_Cloud_Shell.md) 
  * Option 2: [Create Azure VM using the Azure Portal](Create_VM_using_Azure_Portal.md)
* [Connect to your SAS-Server VM and create required users](Connect_to_VM.md)
* [Download the SAS Software Depot](Download_the_SAS_Software_Depot.md)
* [Deploy and Configure SAS](Deploy_and_Configure.md)
* Invoke and Configure SAS Enterprise Guide
* (Optional) Create and Add Users
* [Environment Overview](Environment_Overview.md)
