## Common commands

### Installer

```bash

cat proc/version
cat /etc/apt sources.list or sources.list.d
apt-get update
apt-get install npm
apt-get apache2 vim
```

### Modules

```bash
*# find /lib/modules/${kernelVersion} -name ip_vs.ko -o -name ip_vs_rr.ko -o -name ip_vs_wrr.ko -o -name ip_vs_sh.ko -o -name nf_conntrack_ipv4.ko
*lsmod | grep ip_vs
modprobe -- nf_conntrack_ipv4 ip_vs_sh ip_vs_wrr ip_vs ip_vs_rr nf_conntrack_ipv4 ip_vs_sh ip_vs_wrr ip_vs ip_vs_rr nf_conntrack_ipv4 ip_vs_sh ip_vs_wrr ip_vs ip_vs_rr
```

### Loop

```bash
while true;do curl https://10.10.240.93 -d @rpc/version.json; sleep 1; done
./bin/down
./bin/revert
./bin/up
```
