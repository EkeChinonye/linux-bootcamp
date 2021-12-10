# Lab 1: Create a Linux virtual machine with the AWS CLI

1. Launch AWS Cloud Shell
3. Create virtual machine
4. Open port 80 for web traffic
5. Connect to virtual machine
6. Install web server
7. View the web server in action

### Notes:

Quickstart: Create a Linux VM
* https://aws.amazon.com/getting-started/launch-a-virtual-machine-B-0/

Quickstart for AWS CloudShell
* https://docs.aws.amazon.com/cloudshell/latest/userguide/working-with-cloudshell.html




# What I learnt from working with AWS CLI


[cloudshell-user@ip-10-0-74-230 ~]$ aws ec2 run-instances --image-id ami-0d718c3d715cec4a7 --instance-type t2.micro --key-name webserver_key
{
    "Groups": [],
    "Instances": [
        {
            "AmiLaunchIndex": 0,
            "ImageId": "ami-0d718c3d715cec4a7",
            "InstanceId": "i-0b633da3cb8a6c948",
            "InstanceType": "t2.micro",
            "KeyName": "webserver_key",
            "LaunchTime": "2021-11-25T00:28:27+00:00",
            "Monitoring": {
                "State": "disabled"
            },
            "Placement": {
                "AvailabilityZone": "us-east-2a",
                "GroupName": "",
                "Tenancy": "default"
            },
            "PrivateDnsName": "ip-172-31-1-162.us-east-2.compute.internal",
            "PrivateIpAddress": "172.31.1.162",
            "ProductCodes": [],
            "PublicDnsName": "",
            "State": {
                "Code": 0,
                "Name": "pending"
            },
:Lost your connection to the environment.
Press any key to reconnect and continue using AWS CloudShell
Your session timed out due to inactivity and has been terminated.
Connection is lost. Please refresh the browser to re-establish the connection.
Preparing your terminal...
[cloudshell-user@ip-10-0-96-213 ~]$ 
[cloudshell-user@ip-10-0-96-213 ~]$ sudo yum update -y
Loaded plugins: ovl, priorities
amzn2-core                                      | 3.7 kB     00:00     
Resolving Dependencies
--> Running transaction check
---> Package amazon-linux-extras.noarch 0:2.0.0-1.amzn2 will be updated
---> Package amazon-linux-extras.noarch 0:2.0.1-1.amzn2 will be an update
---> Package glibc.x86_64 0:2.26-54.amzn2 will be updated
---> Package glibc.x86_64 0:2.26-56.amzn2 will be an update
---> Package glibc-common.x86_64 0:2.26-54.amzn2 will be updated
---> Package glibc-common.x86_64 0:2.26-56.amzn2 will be an update
---> Package glibc-langpack-en.x86_64 0:2.26-54.amzn2 will be updated
---> Package glibc-langpack-en.x86_64 0:2.26-56.amzn2 will be an update
---> Package glibc-minimal-langpack.x86_64 0:2.26-54.amzn2 will be updated
---> Package glibc-minimal-langpack.x86_64 0:2.26-56.amzn2 will be an update
---> Package libcrypt.x86_64 0:2.26-54.amzn2 will be updated
---> Package libcrypt.x86_64 0:2.26-56.amzn2 will be an update
---> Package system-release.x86_64 1:2-13.amzn2 will be updated
---> Package system-release.x86_64 1:2-14.amzn2 will be an update
--> Finished Dependency Resolution

Dependencies Resolved

=======================================================================
 Package                  Arch     Version          Repository    Size
=======================================================================
Updating:
 amazon-linux-extras      noarch   2.0.1-1.amzn2    amzn2-core    38 k
 glibc                    x86_64   2.26-56.amzn2    amzn2-core   3.3 M
 glibc-common             x86_64   2.26-56.amzn2    amzn2-core   772 k
 glibc-langpack-en        x86_64   2.26-56.amzn2    amzn2-core   288 k
 glibc-minimal-langpack   x86_64   2.26-56.amzn2    amzn2-core    32 k
 libcrypt                 x86_64   2.26-56.amzn2    amzn2-core    52 k
 system-release           x86_64   1:2-14.amzn2     amzn2-core    18 k

Transaction Summary
=======================================================================
Upgrade  7 Packages

Total download size: 4.5 M
Downloading packages:
Delta RPMs disabled because /usr/bin/applydeltarpm not installed.
(1/7): amazon-linux-extras-2.0.1-1.amzn2.noarch.r |  38 kB   00:00     
(2/7): glibc-common-2.26-56.amzn2.x86_64.rpm      | 772 kB   00:00     
(3/7): glibc-2.26-56.amzn2.x86_64.rpm             | 3.3 MB   00:00     
(4/7): glibc-minimal-langpack-2.26-56.amzn2.x86_6 |  32 kB   00:00     
(5/7): libcrypt-2.26-56.amzn2.x86_64.rpm          |  52 kB   00:00     
(6/7): glibc-langpack-en-2.26-56.amzn2.x86_64.rpm | 288 kB   00:00     
(7/7): system-release-2-14.amzn2.x86_64.rpm       |  18 kB   00:00     
-----------------------------------------------------------------------
Total                                      15 MB/s | 4.5 MB  00:00     
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  Updating   : glibc-2.26-56.amzn2.x86_64                         1/14 
  Updating   : glibc-common-2.26-56.amzn2.x86_64                  2/14 
  Updating   : glibc-minimal-langpack-2.26-56.amzn2.x86_64        3/14 
  Updating   : 1:system-release-2-14.amzn2.x86_64                 4/14 
  Updating   : amazon-linux-extras-2.0.1-1.amzn2.noarch           5/14 
  Updating   : glibc-langpack-en-2.26-56.amzn2.x86_64             6/14 
  Updating   : libcrypt-2.26-56.amzn2.x86_64                      7/14 
  Cleanup    : glibc-langpack-en-2.26-54.amzn2.x86_64             8/14 
  Cleanup    : amazon-linux-extras-2.0.0-1.amzn2.noarch           9/14 
  Cleanup    : libcrypt-2.26-54.amzn2.x86_64                     10/14 
  Cleanup    : 1:system-release-2-13.amzn2.x86_64                11/14 
  Cleanup    : glibc-minimal-langpack-2.26-54.amzn2.x86_64       12/14 
  Cleanup    : glibc-2.26-54.amzn2.x86_64                        13/14 
  Cleanup    : glibc-common-2.26-54.amzn2.x86_64                 14/14 
  Verifying  : amazon-linux-extras-2.0.1-1.amzn2.noarch           1/14 
  Verifying  : glibc-common-2.26-56.amzn2.x86_64                  2/14 
  Verifying  : glibc-langpack-en-2.26-56.amzn2.x86_64             3/14 
  Verifying  : 1:system-release-2-14.amzn2.x86_64                 4/14 
  Verifying  : glibc-2.26-56.amzn2.x86_64                         5/14 
  Verifying  : glibc-minimal-langpack-2.26-56.amzn2.x86_64        6/14 
  Verifying  : libcrypt-2.26-56.amzn2.x86_64                      7/14 
  Verifying  : 1:system-release-2-13.amzn2.x86_64                 8/14 
  Verifying  : glibc-langpack-en-2.26-54.amzn2.x86_64             9/14 
  Verifying  : glibc-common-2.26-54.amzn2.x86_64                 10/14 
  Verifying  : amazon-linux-extras-2.0.0-1.amzn2.noarch          11/14 
  Verifying  : libcrypt-2.26-54.amzn2.x86_64                     12/14 
  Verifying  : glibc-minimal-langpack-2.26-54.amzn2.x86_64       13/14 
  Verifying  : glibc-2.26-54.amzn2.x86_64                        14/14 

Updated:
  amazon-linux-extras.noarch 0:2.0.1-1.amzn2                           
  glibc.x86_64 0:2.26-56.amzn2                                         
  glibc-common.x86_64 0:2.26-56.amzn2                                  
  glibc-langpack-en.x86_64 0:2.26-56.amzn2                             
  glibc-minimal-langpack.x86_64 0:2.26-56.amzn2                        
  libcrypt.x86_64 0:2.26-56.amzn2                                      
  system-release.x86_64 1:2-14.amzn2                                   

Complete!


[cloudshell-user@ip-10-0-96-213 ~]$ sudo yum install -y httpd
Loaded plugins: ovl, priorities
amzn2-core                                      | 3.7 kB     00:00     
Resolving Dependencies
--> Running transaction check
---> Package httpd.x86_64 0:2.4.51-1.amzn2 will be installed
--> Processing Dependency: httpd-tools = 2.4.51-1.amzn2 for package: httpd-2.4.51-1.amzn2.x86_64
--> Processing Dependency: httpd-filesystem = 2.4.51-1.amzn2 for package: httpd-2.4.51-1.amzn2.x86_64
--> Processing Dependency: system-logos-httpd for package: httpd-2.4.51-1.amzn2.x86_64
--> Processing Dependency: mod_http2 for package: httpd-2.4.51-1.amzn2.x86_64
--> Processing Dependency: httpd-filesystem for package: httpd-2.4.51-1.amzn2.x86_64
--> Processing Dependency: /etc/mime.types for package: httpd-2.4.51-1.amzn2.x86_64
--> Processing Dependency: libaprutil-1.so.0()(64bit) for package: httpd-2.4.51-1.amzn2.x86_64
--> Processing Dependency: libapr-1.so.0()(64bit) for package: httpd-2.4.51-1.amzn2.x86_64
--> Running transaction check
---> Package apr.x86_64 0:1.7.0-9.amzn2 will be installed
---> Package apr-util.x86_64 0:1.6.1-5.amzn2.0.2 will be installed
--> Processing Dependency: apr-util-bdb(x86-64) = 1.6.1-5.amzn2.0.2 for package: apr-util-1.6.1-5.amzn2.0.2.x86_64
---> Package generic-logos-httpd.noarch 0:18.0.0-4.amzn2 will be installed
---> Package httpd-filesystem.noarch 0:2.4.51-1.amzn2 will be installed
---> Package httpd-tools.x86_64 0:2.4.51-1.amzn2 will be installed
---> Package mailcap.noarch 0:2.1.41-2.amzn2 will be installed
---> Package mod_http2.x86_64 0:1.15.19-1.amzn2.0.1 will be installed
--> Running transaction check
---> Package apr-util-bdb.x86_64 0:1.6.1-5.amzn2.0.2 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

=======================================================================
 Package              Arch    Version                Repository   Size
=======================================================================
Installing:
 httpd                x86_64  2.4.51-1.amzn2         amzn2-core  1.3 M
Installing for dependencies:
 apr                  x86_64  1.7.0-9.amzn2          amzn2-core  122 k
 apr-util             x86_64  1.6.1-5.amzn2.0.2      amzn2-core   99 k
 apr-util-bdb         x86_64  1.6.1-5.amzn2.0.2      amzn2-core   19 k
 generic-logos-httpd  noarch  18.0.0-4.amzn2         amzn2-core   19 k
 httpd-filesystem     noarch  2.4.51-1.amzn2         amzn2-core   24 k
 httpd-tools          x86_64  2.4.51-1.amzn2         amzn2-core   88 k
 mailcap              noarch  2.1.41-2.amzn2         amzn2-core   31 k
 mod_http2            x86_64  1.15.19-1.amzn2.0.1    amzn2-core  149 k

Transaction Summary
=======================================================================
Install  1 Package (+8 Dependent packages)

Total download size: 1.9 M
Installed size: 5.2 M
Downloading packages:
(1/9): apr-1.7.0-9.amzn2.x86_64.rpm               | 122 kB   00:00     
(2/9): apr-util-bdb-1.6.1-5.amzn2.0.2.x86_64.rpm  |  19 kB   00:00     
(3/9): apr-util-1.6.1-5.amzn2.0.2.x86_64.rpm      |  99 kB   00:00     
(4/9): generic-logos-httpd-18.0.0-4.amzn2.noarch. |  19 kB   00:00     
(5/9): httpd-filesystem-2.4.51-1.amzn2.noarch.rpm |  24 kB   00:00     
(6/9): httpd-2.4.51-1.amzn2.x86_64.rpm            | 1.3 MB   00:00     
(7/9): httpd-tools-2.4.51-1.amzn2.x86_64.rpm      |  88 kB   00:00     
(8/9): mailcap-2.1.41-2.amzn2.noarch.rpm          |  31 kB   00:00     
(9/9): mod_http2-1.15.19-1.amzn2.0.1.x86_64.rpm   | 149 kB   00:00     
-----------------------------------------------------------------------
Total                                     8.1 MB/s | 1.9 MB  00:00     
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  Installing : apr-1.7.0-9.amzn2.x86_64                            1/9 
  Installing : apr-util-bdb-1.6.1-5.amzn2.0.2.x86_64               2/9 
  Installing : apr-util-1.6.1-5.amzn2.0.2.x86_64                   3/9 
  Installing : httpd-tools-2.4.51-1.amzn2.x86_64                   4/9 
  Installing : generic-logos-httpd-18.0.0-4.amzn2.noarch           5/9 
  Installing : mailcap-2.1.41-2.amzn2.noarch                       6/9 
  Installing : httpd-filesystem-2.4.51-1.amzn2.noarch              7/9 
  Installing : mod_http2-1.15.19-1.amzn2.0.1.x86_64                8/9 
  Installing : httpd-2.4.51-1.amzn2.x86_64                         9/9 
  Verifying  : apr-util-1.6.1-5.amzn2.0.2.x86_64                   1/9 
  Verifying  : httpd-2.4.51-1.amzn2.x86_64                         2/9 
  Verifying  : apr-util-bdb-1.6.1-5.amzn2.0.2.x86_64               3/9 
  Verifying  : httpd-filesystem-2.4.51-1.amzn2.noarch              4/9 
  Verifying  : apr-1.7.0-9.amzn2.x86_64                            5/9 
  Verifying  : mailcap-2.1.41-2.amzn2.noarch                       6/9 
  Verifying  : generic-logos-httpd-18.0.0-4.amzn2.noarch           7/9 
  Verifying  : mod_http2-1.15.19-1.amzn2.0.1.x86_64                8/9 
  Verifying  : httpd-tools-2.4.51-1.amzn2.x86_64                   9/9 

Installed:
  httpd.x86_64 0:2.4.51-1.amzn2                                        

Dependency Installed:
  apr.x86_64 0:1.7.0-9.amzn2                                           
  apr-util.x86_64 0:1.6.1-5.amzn2.0.2                                  
  apr-util-bdb.x86_64 0:1.6.1-5.amzn2.0.2                              
  generic-logos-httpd.noarch 0:18.0.0-4.amzn2                          
  httpd-filesystem.noarch 0:2.4.51-1.amzn2                             
  httpd-tools.x86_64 0:2.4.51-1.amzn2                                  
  mailcap.noarch 0:2.1.41-2.amzn2                                      
  mod_http2.x86_64 0:1.15.19-1.amzn2.0.1  
  
TO QUARY THE MACHINE META DATA

[ec2-user@ip-172-31-20-214 ~]$ ls
[ec2-user@ip-172-31-20-214 ~]$ curl http://169.254.169.254/latest/meta-data/instance-id

i-026cc25780423e262[ec2-user@ip-172-31-20-214 ~]$
[ec2-user@ip-172-31-20-214 ~]$ curl http://169.254.169.254/latest/meta-data/instance-id
i-026cc25780423e262[ec2-user@ip-172-31-20-214 ~]$ ls
[ec2-user@ip-172-31-20-214 ~]$ ls /var/www/html
[ec2-user@ip-172-31-20-214 ~]$ sudo su
[root@ip-172-31-20-214 ec2-user]# ls /var/www/html
[root@ip-172-31-20-214 ec2-user]# instanceId=$(curl http://169.254.169.254/latest/meta-data/instance-id)
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100    19  100    19    0     0   3800      0 --:--:-- --:--:-- --:--:--  3800
[root@ip-172-31-20-214 ec2-user]# echo "<h4> hello world from $instanceId</h4>" > /var/www/html/index.html
[root@ip-172-31-20-214 ec2-user]#
[root@ip-172-31-20-214 ec2-user]# cat /var/www/html/index.html
<h4> hello world from i-026cc25780423e262</h4>
[root@ip-172-31-20-214 ec2-user]#
