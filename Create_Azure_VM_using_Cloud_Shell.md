### Create Azure VM to use as your trial environment using the Cloud Shell and ARM template files
1. Login to your subscription of Azure (portal.azure.com)  
2. (optional) Create resource group for the trial environment  
3. Open a Cloud Shell:  Select the Cloud Shell tool off of the menu on the top right section of the Portal screen.
![alt text](images/cloud_shell_icon.png)  
5. Download two .json files that make up the Azure Resource Manager (ARM) template by pasting the *git clone* command into the shell. 
```
git clone https://github.com/pschiltz/SASEval.git
```
5. Ensure the ARM has no errors by running the **az deployment** command with the **what-if** option replacing **<YOUR_RESOURCE_GROUP>** with the value of the resource group to which you want to place the SAS-Server VM.
```
az deployment group what-if --resource-group "<YOUR_RESOURCE_GROUP>" --template-file SASEval/azuredeploy.json --parameters SASEval/azuredeploy.parameters.json
```
6. Create the resources by running the **az deployment** command with the **create** option, replacing **<YOUR_RESOURCE_GROUP>** with the value of the resource group to which you want to place the SAS-Server VM  
```
az deployment group create --resource-group "<YOUR_RESOURCE_GROUP>" --template-file SASEval/azuredeploy.json --parameters SASEval/azuredeploy.parameters.json
```
Go to Step 2 [Connect to your SAS-Server VM and create required users](Connect_to_VM.md)
