
1) What are different artifacts you need to create - name of the artifacts and its purpose
- Visual Studio - to create ARM templates
- Azure repo - to store ARM templates 
- Azure Devops Serices - to build CI/CD pipeline and releases

2) List the tools you will to create and store the ARM templates.
- I use visual studio to build/test ARM templates 
- Azure repos can be used here to store. As we are trying to build CI/CD pipeline with Azure Devops. 

3) Explain the process and steps to create automated deployment pipeline.
- Create a project in azure devops 
- Store the ARM template in Azure Repos
- Create a CI Pipeline
	- In YAML action file use Copy to files. This will copy the deployment and parameter json file to artificate folder drop
	- Add new step to Publish to artifacts
- Create the CD pipeline (release)
	- Add the task to deploy ARM resource group 
	- Add variable is any 
	- Save & Run the release pipeline 
	
4) Create a sample ARM template you will use to deploy a Windows VM of any size
- ARM template azuredeploy.json with azuredeploy.parameters.json updated on git hub 

5) Explain how will you access the password stored in Key Vault and use it as Admin Password in the VM ARM template.
- Create a key vault service in azure resource group with naming convention 
- Check box to provide access to azure resource manager for template deployment  
- create a secret with naming 
- get the resource id of the vault using powershell 
- In parameter file update the reference with the vault resource id and name of the secret
  
