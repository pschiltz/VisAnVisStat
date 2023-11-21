# SASEval
SAS Software Evaluation Roadmap
1. Login to your subscription of Azure (portal.azure.com)
2. Click on the dots beside your avatar on the top right corner and selelct Cloud Shell, or select the Cloud Shell tool off of the menu
3. git clone ---- to get the 2 .json files, template and parameters
4. Creat resource group
5. az deployment group what-if --resource-group SAS9Gold --template <file> --parameters <file>
6. az deployment group create --resource-group SAS_Trial --template-file azuredeploy.json --parameters azuredeploy.parameters.json
