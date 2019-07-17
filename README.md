# Deploy Topshelf windows service using Azure DevOps

This article describes deployment of Windows Service ( Topshelf ) using Azure DevOps pipleline to azure virtual machine.

` At It's core we will be using Windows Service Manager azure marketplace plug in for service deployment task inside the pipeline.`

### Install Windows Service Manager Plugin
Go to visual studio marketplace and [Install WSM Plugin](https://marketplace.visualstudio.com/items?itemName=MDSolutions.WindowsServiceManagerWindowsServiceManager).

![alt text](https://raw.githubusercontent.com/msatmsft/topshelf-windows-service-azure-devops/master/img/1.png)

![alt text](https://raw.githubusercontent.com/msatmsft/topshelf-windows-service-azure-devops/master/img/2.png)

![alt text](https://raw.githubusercontent.com/msatmsft/topshelf-windows-service-azure-devops/master/img/3.png)

### Create Deployment Group in Azure DevOps
Once plugin is install let's create Deployment Group in Azure DevOps.

![alt text](https://raw.githubusercontent.com/msatmsft/topshelf-windows-service-azure-devops/master/img/4.png)

![alt text](https://raw.githubusercontent.com/msatmsft/topshelf-windows-service-azure-devops/master/img/5.png)

`Make sure to check the box "Use a personal access token in the script for authentication" and click Copy Script to the Clipboard button.`

### Run the Powershell script on Deployment VM
You'll need to register the agent using powershell script provided in previous step.  The advantage of deployment group machine registration is you no longer need to provide crednetails for virtual machine in the DevOps pipeline.

Log in to your deployment VM and open Powershell ( Not Powershell ISE) and run the script

### Azure DevOps Build Pipleline
I am using .NET Desktop template to create build pipeline. See Below.

![alt text](https://raw.githubusercontent.com/msatmsft/topshelf-windows-service-azure-devops/master/img/6.png)

### Azure DevOps Release Pipeline

Click on Releases tab and create new release pipeline. Select Empty Job.

Add a Deployment Group Job and select a Deployment group we configured earlier.

Add a task and search for "Windows Service Manager"

![alt text](https://raw.githubusercontent.com/msatmsft/topshelf-windows-service-azure-devops/master/img/7.png)

![alt text](https://raw.githubusercontent.com/msatmsft/topshelf-windows-service-azure-devops/master/img/8.png)

### Trigger Build & Release
Once everything in place, trigger the build and release and verify the topshelf service deployed to your deployment group registered vm.