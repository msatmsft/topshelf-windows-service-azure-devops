# Deploy Topshelf windows service using Azure DevOps

This article describes deployment of Windows Service ( Topshelf ) using Azure DevOps pipleline to azure virtual machine.

` At It's core we will be using Windows Service Manager azure marketplace plug in for service deployment task inside the pipeline.`

### Install Windows Service Manager Plugin
Go to visual studio marketplace and [Install WSM Plugin](https://marketplace.visualstudio.com/items?itemName=MDSolutions.WindowsServiceManagerWindowsServiceManager).

![alt text](https://raw.githubusercontent.com/msatmsft/topshelf-windows-service-azure-devops/master/img/1.png)

![alt text](https://raw.githubusercontent.com/msatmsft/topshelf-windows-service-azure-devops/master/img/2.png)

![alt text](https://raw.githubusercontent.com/msatmsft/topshelf-windows-service-azure-devops/master/img/3.png)

Once plugin is install let's create Deployment Group in Azure DevOps.

![alt text](https://raw.githubusercontent.com/msatmsft/topshelf-windows-service-azure-devops/master/img/4.png)

![alt text](https://raw.githubusercontent.com/msatmsft/topshelf-windows-service-azure-devops/master/img/5.png)

Make sure to check the box "Use a personal access token in the script for authentication" and click Copy Script to the Clipboard button.

