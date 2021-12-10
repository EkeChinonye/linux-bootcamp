# Lab 2: Manage Linux VMs with the Azure CLI

1. Create resource group
2. Create virtual machine
3. Connect to VM
4. Understand VM images
5. Understand VM sizes
6. VM power states
7. Management tasks

### Notes:

Quickstart: Create a Linux VM
* https://docs.microsoft.com/en-us/azure/virtual-machines/linux/tutorial-manage-vm

Quickstart for Bash in Azure Cloud Shell
* https://docs.microsoft.com/en-us/azure/cloud-shell/quickstart



# MY COMMENTS

1. It was very easy creating resource group, vm, and conneccting the vm.
2. The Azure marketplace includes many images that can be used to create VMs. I used the az vm image list command to view the most commonly used vm images.
3. The az vm list-sizes command was very useful in understaning the vm sizes.
4. A VM size can be selected at creation time using az vm create and the --size argument.
5. I was able to view the current of size of my VM with az vm show.
