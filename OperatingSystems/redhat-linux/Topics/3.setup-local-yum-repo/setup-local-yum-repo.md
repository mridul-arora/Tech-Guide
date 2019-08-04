<p align="center">
  <img width="100%" src="https://github.com/mridul-arora/Tech-Guide/blob/master/OperatingSystems/redhat-linux/redhat-linux.jpg">
  <img width="100%" src="https://github.com/mridul-arora/Tech-Guide/blob/master/OperatingSystems/redhat-linux/Topics/3.setup-local-yum-repo/1.jpg">
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