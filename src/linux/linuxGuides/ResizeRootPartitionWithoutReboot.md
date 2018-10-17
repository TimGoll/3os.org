title: Linux - Resize Root Partition Without Reboot
description: Linux - Resize Root Partition Without Reboot how to, guides, examples, and simple usage

# Resize Root Partition Without Reboot

Resize HD size in VC Run: (replace the device if needed)

```bash
echo 1 > /sys/class/scsi_device/2\:0\:0\:0/device/rescan
run fdisk:
```

print the old partition and save the output delete the root partition create a new partition using the SAME start block and make sure that the end block is higher than previous one (enter, enter, enter…) write changes (ignore error) run:

```bash
partx -u /dev/sda
resize2fs -f /dev/sda3
```

Make sure everything is OK:

```bash
df -h
```