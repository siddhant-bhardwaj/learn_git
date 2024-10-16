# Bandit-Practice

## Level 5:

### Question:
Level Goal
The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:

human-readable
1033 bytes in size
not executable
Commands you may need to solve this level
ls , cd , cat , file , du , find

### Code :
```
bandit5@bandit:~$ ls
inhere
bandit5@bandit:~$ cd ./inhere
bandit5@bandit:~/inhere$ ls
maybehere00  maybehere03  maybehere06  maybehere09  maybehere12  maybehere15  maybehere18
maybehere01  maybehere04  maybehere07  maybehere10  maybehere13  maybehere16  maybehere19
maybehere02  maybehere05  maybehere08  maybehere11  maybehere14  maybehere17
bandit5@bandit:~/inhere$ find . -size 1033c
./maybehere07/.file2
bandit5@bandit:~/inhere$ cd ./maybehere07/
bandit5@bandit:~/inhere/maybehere07$ ls
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3
bandit5@bandit:~/inhere$ cd ..
bandit5@bandit:~/inhere$ ls
maybehere00  maybehere02  maybehere04  maybehere06  maybehere08  maybehere10  maybehere12  maybehere14  maybehere16  maybehere18
maybehere01  maybehere03  maybehere05  maybehere07  maybehere09  maybehere11  maybehere13  maybehere15  maybehere17  maybehere19
bandit5@bandit:~/inhere$ find . -readable -1033c
find: unknown predicate `-1033c'
bandit5@bandit:~/inhere$ find . -size 1033c -readable
./maybehere07/.file2
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
```

### Learnings:
- The -find command and how it operates
- We can use -size to specify the size of the file we are looking for.
- we can use -readable to specify if the file is human readable or not.

## Level 6:
### Question: 
Level Goal
The password for the next level is stored somewhere on the server and has all of the following properties:

owned by user bandit7
owned by group bandit6
33 bytes in size
Commands you may need to solve this level
ls , cd , cat , file , du , find , grep

### Code:
```
bandit6@bandit:~$ find -size 33c -group bandit6 -user bandit7
bandit6@bandit:~$ ls
bandit6@bandit:~$ cd /
bandit6@bandit:/$ find -size 33c -group bandit6 -user bandit7
find: ‘./drifter/drifter14_src/axTLS’: Permission denied
find: ‘./root’: Permission denied
find: ‘./snap’: Permission denied
find: ‘./tmp’: Permission denied
find: ‘./proc/tty/driver’: Permission denied
find: ‘./proc/2589662/task/2589662/fd/6’: No such file or directory
find: ‘./proc/2589662/task/2589662/fdinfo/6’: No such file or directory
find: ‘./proc/2589662/fd/5’: No such file or directory
find: ‘./proc/2589662/fdinfo/5’: No such file or directory
find: ‘./home/bandit31-git’: Permission denied
find: ‘./home/ubuntu’: Permission denied
find: ‘./home/bandit5/inhere’: Permission denied
find: ‘./home/bandit30-git’: Permission denied
find: ‘./home/drifter8/chroot’: Permission denied
find: ‘./home/drifter6/data’: Permission denied
find: ‘./home/bandit29-git’: Permission denied
find: ‘./home/bandit28-git’: Permission denied
find: ‘./home/bandit27-git’: Permission denied
find: ‘./lost+found’: Permission denied
find: ‘./etc/polkit-1/rules.d’: Permission denied
find: ‘./etc/multipath’: Permission denied
find: ‘./etc/stunnel’: Permission denied
find: ‘./etc/xinetd.d’: Permission denied
find: ‘./etc/credstore.encrypted’: Permission denied
find: ‘./etc/ssl/private’: Permission denied
find: ‘./etc/sudoers.d’: Permission denied
find: ‘./etc/credstore’: Permission denied
find: ‘./dev/shm’: Permission denied
find: ‘./dev/mqueue’: Permission denied
find: ‘./var/log/amazon’: Permission denied
find: ‘./var/log/unattended-upgrades’: Permission denied
find: ‘./var/log/chrony’: Permission denied
find: ‘./var/log/private’: Permission denied
find: ‘./var/tmp’: Permission denied
find: ‘./var/spool/cron/crontabs’: Permission denied
find: ‘./var/spool/bandit24’: Permission denied
find: ‘./var/spool/rsyslog’: Permission denied
find: ‘./var/cache/ldconfig’: Permission denied
find: ‘./var/cache/apt/archives/partial’: Permission denied
find: ‘./var/cache/pollinate’: Permission denied
find: ‘./var/cache/private’: Permission denied
find: ‘./var/cache/apparmor/2425d902.0’: Permission denied
find: ‘./var/cache/apparmor/baad73a1.0’: Permission denied
find: ‘./var/lib/polkit-1’: Permission denied
find: ‘./var/lib/amazon’: Permission denied
./var/lib/dpkg/info/bandit7.password
find: ‘./var/lib/apt/lists/partial’: Permission denied
find: ‘./var/lib/chrony’: Permission denied
find: ‘./var/lib/snapd/void’: Permission denied
find: ‘./var/lib/snapd/cookie’: Permission denied
find: ‘./var/lib/private’: Permission denied
find: ‘./var/lib/ubuntu-advantage/apt-esm/var/lib/apt/lists/partial’: Permission denied
find: ‘./var/lib/update-notifier/package-data-downloads/partial’: Permission denied
find: ‘./var/lib/udisks2’: Permission denied
find: ‘./var/crash’: Permission denied
find: ‘./boot/efi’: Permission denied
find: ‘./boot/lost+found’: Permission denied
find: ‘./sys/kernel/tracing’: Permission denied
find: ‘./sys/kernel/debug’: Permission denied
find: ‘./sys/fs/pstore’: Permission denied
find: ‘./sys/fs/bpf’: Permission denied
find: ‘./run/lock/lvm’: Permission denied
find: ‘./run/systemd/inaccessible/dir’: Permission denied
find: ‘./run/systemd/propagate/systemd-udevd.service’: Permission denied
find: ‘./run/systemd/propagate/systemd-resolved.service’: Permission denied
find: ‘./run/systemd/propagate/systemd-networkd.service’: Permission denied
find: ‘./run/systemd/propagate/irqbalance.service’: Permission denied
find: ‘./run/systemd/propagate/systemd-logind.service’: Permission denied
find: ‘./run/systemd/propagate/chrony.service’: Permission denied
find: ‘./run/systemd/propagate/polkit.service’: Permission denied
find: ‘./run/systemd/propagate/ModemManager.service’: Permission denied
find: ‘./run/systemd/propagate/fwupd.service’: Permission denied
find: ‘./run/systemd/propagate/bolt.service’: Permission denied
find: ‘./run/lvm’: Permission denied
find: ‘./run/log/journal/ec2dd69f90c4a6285216f71caca9bbca’: Permission denied
find: ‘./run/cryptsetup’: Permission denied
find: ‘./run/multipath’: Permission denied
find: ‘./run/screen/S-bandit20’: Permission denied
find: ‘./run/screen/S-bandit27’: Permission denied
find: ‘./run/screen/S-bandit28’: Permission denied
find: ‘./run/screen/S-bandit24’: Permission denied
find: ‘./run/screen/S-bandit17’: Permission denied
find: ‘./run/screen/S-bandit12’: Permission denied
find: ‘./run/screen/S-bandit29’: Permission denied
find: ‘./run/screen/S-bandit23’: Permission denied
find: ‘./run/screen/S-bandit1’: Permission denied
find: ‘./run/screen/S-bandit31’: Permission denied
find: ‘./run/screen/S-bandit21’: Permission denied
find: ‘./run/screen/S-bandit22’: Permission denied
find: ‘./run/screen/S-bandit19’: Permission denied
find: ‘./run/screen/S-bandit30’: Permission denied
find: ‘./run/screen/S-bandit33’: Permission denied
find: ‘./run/screen/S-bandit25’: Permission denied
find: ‘./run/screen/S-bandit16’: Permission denied
find: ‘./run/sudo’: Permission denied
find: ‘./run/user/11000’: Permission denied
find: ‘./run/user/11012’: Permission denied
find: ‘./run/user/11001’: Permission denied
find: ‘./run/user/11013’: Permission denied
find: ‘./run/user/11023’: Permission denied
find: ‘./run/user/11016’: Permission denied
find: ‘./run/user/11028’: Permission denied
find: ‘./run/user/11024’: Permission denied
find: ‘./run/user/11027’: Permission denied
find: ‘./run/user/11005’: Permission denied
find: ‘./run/user/11015’: Permission denied
find: ‘./run/user/11003’: Permission denied
find: ‘./run/user/11020’: Permission denied
find: ‘./run/user/11004’: Permission denied
find: ‘./run/user/11032’: Permission denied
find: ‘./run/user/11025’: Permission denied
find: ‘./run/user/11002’: Permission denied
find: ‘./run/user/11026’: Permission denied
find: ‘./run/user/20000’: Permission denied
find: ‘./run/user/11006/systemd/inaccessible/dir’: Permission denied
find: ‘./run/user/11008’: Permission denied
find: ‘./run/user/11014’: Permission denied
find: ‘./run/user/11009’: Permission denied
find: ‘./run/user/11011’: Permission denied
find: ‘./run/user/11007’: Permission denied
find: ‘./run/user/11019’: Permission denied
find: ‘./run/user/11029’: Permission denied
find: ‘./run/user/11017’: Permission denied
find: ‘./run/user/11018’: Permission denied
find: ‘./run/user/11031’: Permission denied
find: ‘./run/user/11022’: Permission denied
find: ‘./run/user/11010’: Permission denied
find: ‘./run/user/8006’: Permission denied
find: ‘./run/chrony’: Permission denied
find: ‘./run/udisks2’: Permission denied
bandit6@bandit:/$ cat ./var/lib/dpkg/info/bandit7.password
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
```

### Learnings:
- how to use the find function and a few more arguments
- use of the man command to find these arguments

## Level 7:

### Question:
Level Goal
The password for the next level is stored in the file data.txt next to the word millionth

Commands you may need to solve this level
man, grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

### Code:
```
bandit7@bandit:~$ ls
data.txt
bandit7@bandit:~$ cat data.txt | grep "millionth"
millionth       dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
```
### Learnings:
- more practice on piping
- grep usage

## Level 8:

### Question:
Level Goal
The password for the next level is stored in the file data.txt and is the only line of text that occurs only once

Commands you may need to solve this level
grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

Helpful Reading Material
Piping and Redirection

### Code:
```
bandit8@bandit:~$ ls
data.txt
bandit8@bandit:~$ cat data.txt | sort | uniq -u
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
```
### Learnings:
-better understanding on piping.
-using the uniq command to find unique test

## Level 9:

### Question:
The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.

Commands you may need to solve this level
grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

### Code:

