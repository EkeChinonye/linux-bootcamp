# Lab 3: Manage Azure disks with the Azure CLI

1. Default Azure disks
2. Azure data disks
3. VM disk types
4. Launch Azure Cloud Shell
5. Create and attach disks
6. Prepare data disks
7. Take a disk snapshot

### Notes:

Quickstart: Manage Azure disks
* https://docs.microsoft.com/en-us/azure/virtual-machines/linux/tutorial-manage-disks

Quickstart for Bash in Azure Cloud Shell
* https://docs.microsoft.com/en-us/azure/cloud-shell/quickstart



# MY COMMENTS AND WHAT I LEARNT FROM MANAGING AZURE DISKS WITH THE AZURE CLI
# 1. Default Azure disks
When an Azure virtual machine is created, two disks are automatically attached to the virtual machine.
# Operating system disk
Operating system disks can be sized up to 2 TB, and hosts the VMs operating system. The OS disk is labeled /dev/sda by default. The disk caching configuration of the OS disk is optimized for OS performance. Because of this configuration, the OS disk should not be used for applications or data. For applications and data, use data disks, which are detailed later in this tutorial.
# Temporary disk
Temporary disks use a solid-state drive that is located on the same Azure host as the VM. Temp disks are highly performant and may be used for operations such as temporary data processing. However, if the VM is moved to a new host, any data stored on a temporary disk is removed. The size of the temporary disk is determined by the VM size. Temporary disks are labeled /dev/sdb and have a mountpoint of /mnt.

# 2. Azure data disks
To install applications and store data, additional data disks can be added. Data disks should be used in any situation where durable and responsive data storage is desired. The size of the virtual machine determines how many data disks can be attached to a VM.


# 3. VM disk types
Azure provides two types of disks.
# Standard disks
This is backed by HDDs, and delivers cost-effective storage while still being performant. Standard disks are ideal for a cost effective dev and test workload.
# Premium disks
This is backed by SSD-based, high-performance, low-latency disk. Perfect for VMs running production workload. VM sizes with an S in the size name, typically support Premium Storage. For example, DS-series, DSv2-series, GS-series, and FS-series VMs support premium storage. When you select a disk size, the value is rounded up to the next type. For example, if the disk size is more than 64 GB, but less than 128 GB, the disk type is P10.

# 4. Launch Azure Cloud Shell
# 5. Create and attach disks
# 6. Prepare data disks
# 7. Take a disk snapshot
