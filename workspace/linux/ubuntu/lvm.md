
## LVM-Disk

> Notice

**partprobe**
> to force the kernel to re-read the partition table so that it is not necessary to perform a reboot.

### Get Status

- [x] lsblk -f

- [x] pvscan

- [x] vgs -o +devices,lv_path

- [x] vgdisplay

- [x] lvmdiskscan

### Add Disk

```bash
fdisk /dev/sdX
```

- Regular disk: n => (Enter All)=>p => t => 8e = changes to LVM partition type=>w
- Swap disk: n => (Enter All)=>p => t => 82 = changes to SWAP partition type=>w

### Create Partition

```bash
pvcreate /dev/sdX1
```

### Create Logical Volume

```bash
lvcreate -l 100%FREE -n lvubuntu vgubuntu
```

```bash
vgextend vgubuntu /dev/sdX
```

To enable logical volumes before mount LVs to the path eg., `/mnt/docker`

```bash
vgchange -an vg
```

> For Regular Disk

When you have made a LV, it is not assigned to the FSTYPE, so we need to assign `mkfs.ex4`

```bash
# mkfs -t ext4 /dev/vgubuntu/lvubuntu
sudo mkfs.ext4 /dev/vgubuntu/lvdocker
mount -t ext4 /dev/vgubuntu/lvubuntu /mnt/X/
```

To check is the FSTYPE assigned or not

```bash
lsblk --output NAME,KNAME,TYPE,SIZE,MOUNTPOINT,FSTYPE
```

Output similarity:

```md
NAME                  KNAME TYPE  SIZE MOUNTPOINT  FSTYPE
sda                   sda   disk   50G
├─sda1                sda1  part    1M
└─sda2                sda2  part   50G /           ext4
sdb                   sdb   disk  100G
├─sdb1                sdb1  part   50G             LVM2_member
│ └─vgubuntu-lvubuntu dm-0  lvm   100G
└─sdb2                sdb2  part   50G             LVM2_member
  └─vgubuntu-lvubuntu dm-0  lvm   100G
sdc                   sdc   disk   50G             LVM2_member
└─vgubuntu-lvdocker   dm-1  lvm    50G /mnt/docker ext4
```

Final step is mounting:

```bash
sudo mount /dev/vgubuntu/lvdocker /mnt/docker
```

> For Swap Disk

```bash
mkswap /dev/vgubuntu/swap
mkswap /dev/mapper/vgubuntu-swap
swapon -v /dev/vgubuntu/swap
```

```bash
partprobe
swapon -va
cat /proc/swaps
Free -h
```

### Fstab Boot

```bash
sudo nano /etc/fstab
```

```md
# <file system> <mount point>   <type>  <options>       <dump>  <pass>
/dev/mapper/vgubuntu-root /               ext4    errors=remount-ro 0       1
/dev/mapper/vgubuntu-swap   swap     swap    defaults     0 0
# /boot/efi was on /dev/sda1 during installation
UUID=9fd9c344-09a7-4bbf-af88-9b4e1c24955d       /mnt/docker    ext4    defaults        0       2
/dev/mapper/vgubuntu-home /mnt/home ext4 errors=remount-ro,x-gvfs-show,x-udisks-auth,x-gvfs-name=mnt-home 0 1
/dev/mapper/vgubuntu-sub /mnt/sub ext4 errors=remount-ro,x-gvfs-show,x-udisks-auth,x-gvfs-name=mnt-sub 0 1
```
