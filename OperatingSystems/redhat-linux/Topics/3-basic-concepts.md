<p align="center">
  <img width="100%" src="https://github.com/mridul-arora/Tech-Guide/blob/master/OperatingSystems/redhat-linux/redhat-linux.jpg">
</p>

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