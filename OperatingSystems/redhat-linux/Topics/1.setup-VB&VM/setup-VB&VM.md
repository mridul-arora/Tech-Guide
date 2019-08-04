<p align="center">
  <img width="100%" src="https://github.com/mridul-arora/Tech-Guide/blob/master/OperatingSystems/redhat-linux/redhat-linux.jpg">
  <img width="100%" src="https://github.com/mridul-arora/Tech-Guide/blob/master/OperatingSystems/redhat-linux/Topics/1.setup-VB&VM/1.jpg">
</p>

Resources you will need here are:
1. rhel-server-7.5-x86_64-dvd.iso
2. Oracle_VM_VirtualBox_Extension_Pack-5.2.18.vbox-extpack

***Note: You don't need to download any software from the internet. Everything is available [here](https://drive.google.com/drive/folders/1KfSNLBGaEfTLVgLFIrZGA0ZtUnnbiC29?usp=sharing) with you.***

### Step 1: 
Follow the [video](https://youtu.be/mflqkyO00EI) to setup the RHEL virtual machine. Allocate 50 GB instead of 20 GB in the size of your virtual hard disk with half of the RAM you have in your base system. 
### Step 2:
Then install VirtualBox Extension Pack from [here](https://youtu.be/mwKmxxRbvws) and use the extension pack from resources.
### Step 3:
Lastly, change your network setting from NAT to Bridge-Adapter by watching this [video](https://youtu.be/ATp2yWjLKa8) till 1:10.
### Step 4: 
After configuring bridge-adapter type these two commands
```bash
[root@localhost ~]# systemctl restart network
[root@localhost ~]# dhclient
```
dhclient : provides a means for configuring one or more network interfaces using the Dynamic Host Configuration Protocol

<p align="center">
    <img  src="https://github.com/mridul-arora/Tech-Guide/blob/master/OperatingSystems/redhat-linux/next.png">
    Transfer directories &amp; files using WinSCP
</p>