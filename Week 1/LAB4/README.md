# Lab 4: Create and use an SSH public-private key pair for Linux VMs in Azure

1. Supported SSH key formats
2. Create an SSH key pair
3. Provide an SSH public key when deploying a VM
4. SSH into your VM

### Notes:

Quickstart: SSH for Linux VMs
* https://docs.microsoft.com/en-us/azure/virtual-machines/linux/mac-create-ssh-keys

Quickstart for Bash in Azure Cloud Shell
* https://docs.microsoft.com/en-us/azure/cloud-shell/quickstart




# MY COMMENTS

# 1. Create an SSH key pair

chinonye@Azure:$ mkdir mynewRsa
chinonye@Azure:$ ls
clouddrive mynewRsa
chinonye@Azure:$ cd mynewRsa
chinonye@Azure:/mynewRsa$ ls
chinonye@Azure:/mynewRsa$ ssh-keygen -m PEM -t rsa -b 4096
Generating public/private rsa key pair.
Enter file in which to save the key (/home/chinonye/.ssh/id_rsa): mynewRsa
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in mynewRsa.
Your public key has been saved in mynewRsa.pub.
The key fingerprint is:
SHA256:RpJL6m1mxqZ68FPKvObUkOglXGpFSKV7isYWEvkojpI chinonye@cc-dfeb9e8b-6cffc8f975-k76x5
The key's randomart image is:
+---[RSA 4096]----+
| ..oo |
| ..o . |
|o . o + . |
| = * + + |
|+.O * . S |
|=o =.. |
|E=o=ooX |
|+ .OB |
| .=+o |
+----[SHA256]-----+
chinonye@Azure:/mynewRsa$




# 2. Create an SSH key pair
chinonye@Azure:$ mkdir mynewRsa
chinonye@Azure:$ ls
clouddrive mynewRsa
chinonye@Azure:$ cd mynewRsa
chinonye@Azure:/mynewRsa$ ls
chinonye@Azure:~/mynewRsa$ ssh-keygen -m PEM -t rsa -b 4096
Generating public/private rsa key pair.
Enter file in which to save the key (/home/chinonye/.ssh/id_rsa): mynewRsa
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in mynewRsa.
Your public key has been saved in mynewRsa.pub.
The key fingerprint is:
SHA256:RpJL6m1mxqZ68FPKvObUkOglXGpFSKV7isYWEvkojpI chinonye@cc-dfeb9e8b-6cffc8f975-k76x5
The key's randomart image is:
+---[RSA 4096]----+
| ..oo |
| ..o . |
|o . o + . |
| = * + + |
|+.O * . S |
|=o =.. |
|E=o=ooX |
|+ .OB |
| .=+o |
+----[SHA256]-----+ 


# 3. Provide an SSH public key when deploying a VM
chinonye@Azure:~/mynewRsa$ cat /.ssh/id_rsa.pub
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDJ+DqE0Lq0BT3sFQ+avkixeDDaXRrPZIMxhbs721oUYMsL4s6CdIjj9cxygXUYKdBeF6eJyfuJ2ULXd0vES4YL1sh5jecScnItXE7Xopk/I05aQWX9CpudBLZDa25rFTyoJF8wv31GDQzZsKBWI0gBD71RvNE8F7ssW4rRhJPMnXQR9mDoCj/mQWAkOgNbtQF768UFmMErkTzJp82keaXSzzAVey/0rO0oEuPkfy1w18IvQ93ywg6JmNj+mbus5URsPOliV9oI5OPCmkkGOjJQiJFU+IwsZFKXFUDWq2gu5131wT/mKgMUELZt+pl1xgCcJjSRx1uguI3COiSxaOxdchinonye@Azure:/mynewRsa$

chinonye@Azure:/mynewRsa$ ls
mynewRsa mynewRsa.pub
chinonye@Azure:/mynewRsa$
