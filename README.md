# Hetzner (EX Series) with encrypted HDD incl. Software RAID1 and Debian 9 (Stretch)
Hetzner root server full disk encryption with cryptsetup LUKS and SWRAID1 on NVME storage


### Boot into rescue mode and OS installation

1. Set your root server into rescue mode in Hetzner Robot (https://robot.your-server.de).
<br>After login via ssh, you can install your favorite OS - in this tutorial we will use Debian 9 (Stretch).
```
installimage
```

2. Edit Hetzner OS configuration
```
# Partitioning
SWRAID 1                   # 0 = No RAID; 1 = RAID
SWRAIDLEVEL 1              # 0 = Striping; 1 = Mirrorin

# Hostname
HOSTNAME your.hostname

# Partition
PART /boot ext4 512M
PART / ext4 all
```

3. After that start the install routine with `F2 (save)` + `F10 (quit editor)` and confirm with `OK`.

### Beginn encryption
