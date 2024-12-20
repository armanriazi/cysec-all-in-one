

```bash
# enable using back slash
echo -e ""
# write to a file
echo "aaa" > filename
```

```bash
history
cat .bash_history
```

# Access to files

```bash
# Show line no. and desc
cat a.txt -n | more
# Easy Show each paraph with $ sign
cat a.txt -e
# Input to file a text
cat > a.txt
# Copy a file content/Ovveride
cat a.txt >> empty.txt
```

```bash
# move some file
mv a.txt b.txt /Desktop
# Hidden file
mv a.txt .a.txt
# UnHidden file
mv .a.txt a.txt
```

```bash
# Copy and make a hidden file
cp a.txt /Desktop/.a.txt
cp -r ...
```

```bash
# make 3 directory 
mkdir -p /a/b/c
```

```bash
# Force remove all tree 
rm -r -f /a/b/
```

```bash
gzip filename
gunzip filename
```

```bash
uname -s -r -v -o
hostname
loginame
```

## Symbolic

```bash
# Shortcut file or folder
ln -s ~/Video/ ~/Desktop
```


## FileSystem

```bash
du -sh ./*
df -h ./*
df -lh
ls -li .
ls -ld /dev
df -hT # mounted file systems
cd /home
ls or dir
ls -al armanriazi/
su armanriazi
cd ~/
pwd
touch text.txt
mv text.txt test.txt
cat test.txt =>Show contain of file  or for web content=>curl yourip
vi index.html =>for create and editable file,manipulate file content
rmdir foo =>OR rm Rv data/
:qa! =>OR :wq  at the end of edit file for exit

lsattr testfile
chattr +a testfile
echo "1" >>testfile

swapon -s

umask
```

#### VFS

```bash
uname -ra
ls -l /proc/ | more
cat /proc/cpuinfo
cat /proc/meminfo | more
cat /proc/swaps
cat /proc/partitions

# Special File:
# Block File :
Ls –la /dev |grep ‘^b’

#Then Type:
stat /dev/sda

#Character File:
Ls –la /dev |grep ‘^c’

#Symbolic Link:
Ls –la /dev |grep ‘^l’

#Pipes:
Ls –la /dev |grep ‘^p’

#Socket:
Ls –la /dev |grep ‘^s’

# Directory:
ls –lha /home |grep ‘^d’

/dev/zero od -An -N1 -i /dev/zero
/dev/random od -An -N1 -i /dev/zero
/dev/null cp /*.txt ~ 2>/dev/null


lsblk
ls -i

find / -inum 2435

```