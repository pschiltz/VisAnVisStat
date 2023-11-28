# SAS Software Evaluation Roadmap  

Welcome!  We are happy you have chosen to evaluate **SAS Office Analytics**.  This guide will walk you through the process of installation and usage, including securing the required virtual machine from Azure.  We have done our best to make this guide as easy and thorough as possible through scripts and automation wherever possible.  You will find that choices have been made such as machine size, name, userid and passwords.  We call this the *happy path* :relaxed:!  Feel free, if you are comfortable, to over-ride the defaults.  
  
<ins>The only requirements for getting started are an Azure subscription and a SAS Software Order email.</ins>

These are steps needed to get your SAS software installed and configured:
* Create appropriate resources either manually using the Azure Portal or using the ARM template provided in this GitHub repository:

  * Option 1: [Create Azure VM using Cloud Shell and ARM template](https://github.com/pschiltz/SASEval/blob/main/Create%20Azure%20VM%20using%20Cloud%20Shell.md) 
  * Option 2: [Create Azure VM using the Azure Portal](https://github.com/pschiltz/SASEval/blob/Create%20VM%20using%20Azure%20Portal.md)
* [Connect to your SAS-Server VM and create required users](https://github.com/pschiltz/SASEval/blob/main/Create%20VM%20using%20Azure%20Portal.md)
* [Download the SAS Software Depot](https://github.com/pschiltz/SASEval/blob/main/Download%20the%20SAS%20Software%20Depot.md)
* [Deploy and Configure SAS](https://github.com/pschiltz/SASEval/blob/main/Deploy%20and%20Configure.md)
* Invoke and Configure SAS Enterprise Guide
* (Optional) Create and Add Users
