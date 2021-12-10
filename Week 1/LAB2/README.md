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

SEP=,
NAME,SUBSCRIPTION,RESOURCE GROUP,LOCATION,STATUS,OPERATING SYSTEM,SIZE,PUBLIC IP ADDRESS,DISKS,
"myVM","Azure subscription 1","myresourcegroupdisk","East US","Running","Linux","Standard_DS2_v2","20.119.50.119","4"
"webserver","Azure subscription 1","chisfunplace","East US","Running","Linux","Standard_DS1_v2","20.124.9.238","2"
"webserver","Azure subscription 1","nonye_gp","East US","Stopped (deallocated)","Linux","Standard_DS1_v2","-","2" 
