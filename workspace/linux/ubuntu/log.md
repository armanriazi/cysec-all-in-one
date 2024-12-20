
#### Log OS

##### Journal

```bash
systemd status systemd-journald.service
sudo journalctl -f
journalctl -u docker
journalctl -u etcd-member -f
journalctl –f
fleetctl list-machines
journalctl -r */realtime
journalctl -b */boot 
journalctl -k */kernel
journalctl --since "today"
cat /etc/systemd/journald.conf
```bash

#### Kernel logs

```bash
tail -20 /var/log/boot.log
dmesg | tail 20
cat /etc/logrotate.conf
```