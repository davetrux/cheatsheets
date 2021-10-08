# Linux commands

## File System

### Compress a directory

```
tar -zcvf outputFileName folderToCompress
```

### Extract a directory

```
tar -xzvf some.file
```

### Download a file
```
curl -O http://some/url

```

### Permission Numbers for a Directory

```
stat -c "%a %n" <directoryName>
```

### Remove a Directory

```
rm -rf letters/
```

### Base64 encoding

```
echo -n <yourStringHere> | base64
```

### Get file permission info

```
stat somefile.ext
```

### Create a Symbolic link

```
ln -s /path/to/file /path/to/symlink
```

### Find the full path of a symbolic link

```
readlink -f $(which java)
```

### Folder Sizes
[Relevant article](http://www.cyberciti.biz/faq/how-do-i-find-the-largest-filesdirectories-on-a-linuxunixbsd-filesystem/)

```
cd /path/to/some/where
du -h
du -h --max-depth=1 | sort -hr
du -ah directoryname/
du -hsx * | sort -rh | head -10
```

### Drive space

```
df -h
```

## Maintenance

### Ubuntu

#### Remove a package

```
apt-get --purge remove <package>
```

#### Updates 

```
sudo apt-get update
sudo apt-get upgrade
sudo apt-get dist-upgrade
```

### CentOS/RHEL

#### Updates

```
sudo yum makecache fast
sudo yum update
```

#### Install a package by RPM

```
sudo rpm -Uvh filename.rpm
```

## System

### Users

```
useradd <username>
passwd <username>
```

### Add SSH Key

scp key to home directory

```
mv keyname.pub .ssh/
cat keyname.pub >> authorized_keys
```

### Run as another user

```
sudo su - username
```

### Run combined commands as root

```
sudo -i
then some commands
```

### Re-Load Profile After Edits

```
source ~/.bash_profile
```

### Set Timezone (CentOS)

```
cp /etc/localtime /root/old.timezone
rm /etc/localtime
ln -s /usr/share/zoneinfo/America/Detroit /etc/localtime
```

### Update Time

```
ntpdate pool.ntp.org
```

### Traffic on Port 80

```
tcpdump -i port 80`
```

### Running Processes

```
ps -ef|grep <processName>`
```

Where <processName> is something like `httpd`

### List Running Services

```
service --status-all`
```

### Services at Startup

```
ntsysv
```

### Sort Processes by Memory Usage

```
ps aux | sort -rnk 4
```

### Sort Processes by CPU Usage

```
ps aux | sort -rnk 3
```

### Cron jobs
[Relevant Article](http://www.cyberciti.biz/faq/linux-show-what-cron-jobs-are-setup/)

```
crontab -l
```

## Applications

### MySQL

#### Login

```
mysql -u root -p
```

#### Backup

```
mysqldump -u root -p database_name > database_name.sql
```

#### Restore a backup

```
mysql -u root -p database_name < database_name.sql
```


### Upgrade node.js

```
sudo npm cache clean -f
sudo npm install -g n
sudo n stable
```

### nginx tomcat permissions problem

```
/usr/sbin/setsebool httpd_can_network_connect -P true 
```

### Delete Jenkins Jobs

```
CRUMB=$(curl -s 'https://<username>:<keyhere>@<jenkinsurl>/crumbIssuer/api/xml?xpath=concat(//crumbRequestField,":",//crumb)')

curl -X POST -H "$CRUMB" POST https://<username>:<keyhere>@<jenkinsurl>/job/Cloud-Speech-Android/[1-9]/doDelete
```



### Android list installed packages

```
$ANDROID_HOME/tools/bin/sdkmanager --list  | sed -e '/Available Packages/q'
```

