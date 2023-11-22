### Create Azure VM to use as your trial environment using the Cloud Shell and ARM template files
1. Login to your subscription of Azure (portal.azure.com)  
2. (optional) Create resource group for the trial environment  
3. Click on the dots beside your avatar on the top right corner and selelct Cloud Shell, or select the Cloud Shell tool off of the menuOpen Cloud Shell from the Azure Portal  
4. Download two .json files that make up the Azure Resource Manager (ARM) template  
```
git clone https://github.com/pschiltz/SASEval.git
```
5. Ensure the ARM has no errors by running with the **what-if** option  
```
az deployment group what-if --resource-group "<YOUR_RESOURCE_GROUP>" --template-file SASEval/azuredeploy.json --parameters SASEval/azuredeploy.parameters.json
```
6. Create the resources by running with the **create** option  
```
az deployment group create --resource-group "<YOUR_RESOURCE_GROUP>" --template-file SASEval/azuredeploy.json --parameters SASEval/azuredeploy.parameters.json
```
