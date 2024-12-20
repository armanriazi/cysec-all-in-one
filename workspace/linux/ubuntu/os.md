


## Resources

```bash
free m
nano /etc/anacrontab 
watch free -m cd /var/log/
du -h --max-depth=1
cd du -h --max-depth=1
cd du -h --max-depth=1
iostat vmstat
vmstat -M
vmstat -s -M
vmstat -S -M
vmstat -S M
ps -eo pcpu,pid,user,args 1 sort -k 1 -r 1 head -10
ps aux 1 grep rsyslog
ps aux 1 grep init 
uptime date lsof /home/carmen
lsof -c rsyslig 
lsof -c rsyslog
history 1 grep logrotate 
```

### Linux-System

```bash
cat /etc/issue => get version
man pgrep
pgrep firefox
ps j | more
ps aux

tty = > action => alt+ctl+f7

top

kill -l (signals)
kill -SIGSTOP 2375
kill -SIGCONT (OR 18 base on kill -l) 2375
kill -SIGKILL 2375

chage -l username

apt search axel
apt show axel
```

### OS

```bash
systemctl status kubelet
systemctl cat kubelet.service
systemctl restart systemd-logind.service
sudo /etc/init.d/docker restart
```

### Run level / Target: systemctl get-default

```bash
ls /etc/systemd/system
nano /etc/default/graub
pstree | more
man systemctl
systemctl list-units
systemctl list-units --type=service --state=running
systemctl is-enabled docker.service
systemctl is-active docker.service
systemctl reload docker.service
systemctl reload-or-restart docker.service
systemctl list-dependencies --after/before docker.service
systemctl status sshd.service
systemctl status logrotate.service
systemctl status crond.service
systemctl mask/umask docker.service
sudo apt update  
```