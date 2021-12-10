# Lab 1: Create a Linux virtual machine with the Azure CLI

1. Launch Azure Cloud Shell
2. Create a resource group
3. Create virtual machine
4. Open port 80 for web traffic
5. Connect to virtual machine
6. Install web server
7. View the web server in action

### Notes:

Quickstart: Create a Linux VM
* https://docs.microsoft.com/en-us/azure/virtual-machines/linux/quick-create-cli

Quickstart for Bash in Azure Cloud Shell
* https://docs.microsoft.com/en-us/azure/cloud-shell/quickstart




#COMMENTS
1. I was able to successfully launch azure cloud shell.
2. I created a resourse group called nonye_gp using the az group create command. I understand that an Azure resource group is a logical container where Azure resources are deployed and managed.
3. I created a virtual machine using the az vm create command.
4. I used the az vm open-port to open TCP port 80 for web traffic
5. I connected to my vm using ssh webserver@ the public ip of my vm
6. I installed the web server and exited ssh
