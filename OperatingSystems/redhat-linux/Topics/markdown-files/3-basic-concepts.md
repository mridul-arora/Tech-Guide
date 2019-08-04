<p align="center">
  <img src="https://github.com/mridul-arora/Tech-Guide/blob/master/OperatingSystems/redhat-linux/redhat-linux.jpg">
</p>

<p align="center">
  <img src="https://github.com/mridul-arora/Tech-Guide/blob/master/OperatingSystems/redhat-linux/Topics/Infographs/3-basic-concepts/1.jpg">
</p>

You can download all the softwares you will be needing for Red-Hat-Linux from [here](https://drive.google.com/drive/folders/1KfSNLBGaEfTLVgLFIrZGA0ZtUnnbiC29?usp=sharing).
<br><br>

## Concept 1: Setup VirtualBox & Virtual Machine
<p align="center">
  <img src="https://github.com/mridul-arora/Tech-Guide/blob/master/OperatingSystems/redhat-linux/Topics/Infographs/3-basic-concepts/2.jpg">
</p>

Resources you will need here are:
1. rhel-server-7.5-x86_64-dvd.iso
2. Oracle_VM_VirtualBox_Extension_Pack-5.2.18.vbox-extpack

***Note: You don't need to download any software from the internet. Everything is available [here](https://drive.google.com/drive/folders/1zYxkQMhYTCF0PA8dKuSDAqE9X8zMO37o?usp=sharing) with you.***

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

## Concept 2: Transfer Resource files using WinSCP
<p align="center">
  <img src="https://github.com/mridul-arora/Tech-Guide/blob/master/OperatingSystems/redhat-linux/Topics/Infographs/3-basic-concepts/3.jpg
">
</p>
Here Resource files are to be transferred from Windows(base OS) to Linux(virtual OS) using WinSCP software. Resources you will need here are:<br>
1. WinSCP.exe<br>
2. python_lib directory<br>
3. rhel7_5_rpm_extras directory<br>
4. rhel7_5_software_extras directory

### Step 1:
Follow this [video](https://youtu.be/HUHBwU5FHag) and drag and drop the python_lib, rhel7_5_rpm_extras & the rhel7_5_software_extras directories to Linux Desktop.

## Concept 3: Setting up a local YUM Repository
<p align="center">
  <img src="https://github.com/mridul-arora/Tech-Guide/blob/master/OperatingSystems/redhat-linux/Topics/Infographs/3-basic-concepts/4.jpg">
</p>

### Step 1:
In the bottom right corner of the VirtualBox VM Window there are a few icons. Right Click on the second icon which is in the shape of a disk and select the RHEL ISO file. A Disk icon will be displayed on the Desktop. Right click on that icon and select Open in Terminal.

```Bash
[root@localhost RHEL-7.5 Server.x86_64]# pwd
/run/media/root/RHEL-7.5 Server.x86_64
```
Copy the 2nd line i.e. /run/media/root/RHEL-7.5 Server.x86_64

### Step 2:
Go to terminal and type
```Bash
[root@localhost RHEL-7.5 Server.x86_64]# cd
[root@localhost ~]# cd /etc/yum.repos.d/
[root@localhost yum.repos.d]# vi dvd.repo
```
A new file is created named dvd.repo which will act as a link to access the local repository.

### Step 3:
Adding RHEL DVD as repository.

A vim editor will open. Press 'i' button to insert. Then type the following lines. Paste that copied line here after 'file:/'. Here, baseurl doesnot accept spaces, therefore we add a frontslash after 7.5

```Bash
[dvd]
baseurl=file:///run/media/root/RHEL-7.5\ Server.x86_64
gpgcheck=0
```

Adding other extra redhat packages as repository
```Bash
[rpm_extras]
baseurl=file:///root/Desktop/rhel7_5_rpm_extras
gpgcheck=0

[extra_new_rpm]
baseurl=file:///root/Desktop/rhel7_extra_new_rpm
gpgcheck=0
```
Press Esc. Type :wq to save and exit. 

* [repo_id] : square brackets signifies the ID of the repository<br>
* baseurl : baseurl identifies the location i.e. from where to download and install all the packages. Where exactly the software is available.<br>
* file : the file protocol to access the local folders<br>
* gpgcheck : gpgcheck stands for signature verification. If it is successful then you ae sure about the security. If gpgcheck's value is set to 1, then then it asks for signature verification else when set to 0 it doesn't.

To verify the repositories type command
```bash
[root@localhost ~]# yum repolist
```

## Some more Linux commands

1. redhat package manager: to query out whether the package is installed or not.
```bash
[root@localhost ~]# rpm -q firefox
firefox-52.7.0-1.el7_4.x86_64
[root@localhost ~]# rpm -q vlc
package vlc is not installed
```

2. To find from which package did date came from
```bash
[root@localhost ~]# yum whatprovides date
```

3. present working directory
```bash
[root@localhost RHEL-7.5 Server.x86_64]# pwd
/run/media/root/RHEL-7.5 Server.x86_64
```

4. make directory 
```bash
[root@localhost ~]# mkdir 'Linux World' 
```
OR
```bash
[root@localhost ~]# mkdir Linux\ World
```

5. To check how much RAM is being used
```bash
[root@localhost ~]# free -m 
```

6. To find the location of the file
```bash
[root@localhost ~]# which firefox
/usr/bin/firefox
```

### Done :smile: