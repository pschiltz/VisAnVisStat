# SASEval
SAS Software Evaluation Roadmap
1. [ ] (Create Azure VM using Cloud Shell.md)
2. (optional) Create resource group
3. Click on the dots beside your avatar on the top right corner and selelct Cloud Shell, or select the Cloud Shell tool off of the menu
4. git clone ---- to get the 2 .json files, template and parameters
5. cd SASEval
7. az deployment group what-if --resource-group <RESOURCE_GROUP> --template-file <file> --parameters <file>
8. az deployment group create --resource-group <RESOURCE_GROUP> --template-file azuredeploy.json --parameters azuredeploy.parameters.json
