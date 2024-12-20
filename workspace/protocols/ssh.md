
[Helper](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

Known Fingerprint is use to verify the server's identity to the client

## Install

```bash
sudo apt-get install openssh-server
sudo apt install openssh-client
sudo apt-get  update
```

```bash
sudo service ssh start
Install the SSH public key on the node#
sudo cat $HOME/.ssh/id_rsa.pub | ssh rke@172.18.3.10 "tee -a /home/rke/.ssh/authorized_keys"
```

## Banner Login/Logout

```bash
/etc/issue.net
# write:
# Unauthorized access to this server is prohibited. All the activites are being logged
# exit
/etc/ssh/sshd_config
# add:
Banner /etc/issue.net
PrintMotd yes
# exit
nano /etc/motd
/etc/init.d/ssh restart
ssh user@ip
```

## Disable root connection

```bash
sudo nano /etc/ssh/sshd_config
PermitRootLogin #yes/no/without-password
```

## Blacklist users from ssh

```bash
/etc/ssh/sshd_config
# search AllowUser
AllowUsers     arman user1
# exit nano
/etc/init.d/ssh restart
```

## Example scp

```bash
scp/home/ubuntu1604rzero/MyIndexRancher/Scripts/MyScriptUpWorker.sh ubuntu1604rthree@172.18.3.17:~/
sudo ssh-keygen -t rsa -b 4096 -C rke@172.18.3.10
sudo ssh-keygen -t rsa -b 2048 -C rke@172.18.3.10
```

```bash
sudo cat /home/rke/.ssh/id_rsa.pub
sudo cat /home/rke/.ssh/id_rsa.pub >> $HOME/.ssh/authorized_keys
```

```bash
sudo ssh -i $HOME/.ssh/id_rsa rke@172.18.3.10 docker version
ssh-keyscan -p 22 172.18.3.10
ssh-keyscan -p 22 k8s-master
```

```bash
sudo ssh-copy-id -i /home/rke/.ssh/id_rsa master@172.18.3.10
```

```bash
sudo ssh rke@172.18.3.10 -v -i $HOME/.ssh/id_rsa
sudo ssh -i $HOME/.ssh/id_rsa rke@172.18.3.10
eval $(ssh-agent) OR sudo exec ssh-agent bash
ssh-add $HOME/.ssh/id_rsa
echo $SSH_AGENT_SOCK
ssh-add -K -S
ssh-add -X #unlock
ssh-add -l ssh-add -L ssh-add -K ssh-add -D
sudo ssh workertwo@172.18.3.16
```

```bash
.\ssh-keygen.exe -l -f "c:\cert\ssh\my-vsts" -E sha256
ssh -T git@github.com

sudo gedit /etc/ssh/sshd_config

PermitRootLogin yes=>to file :/etc/ssh/sshd_config

#If you have any issues and need to fix permissions issues, run the following comand:
tail -f /var/log/secure
tail -f /var/log/auth.log
restorecon -R -v /root/.ssh
```
