# Creating file system for Longhorn
The next step is to create a new logical volume with the Logical Volume Managemen.

First, you need to create a new physical volume. In our case the second disk is called vdb. Use this as longhorn volume.
```
pvcreate /dev/vdb
```
After the physical volume is created, create a volume group called vgdata:
```
vgcreate vgdata /dev/vdb
```
Now create the logical volume; use 100% of the disk.
```
lvcreate -n lvlonghorn -l100%FREE vgdata
```
On the logical volume, create the XFS file system. You do not need to create a partion on top of it.

```
mkfs.xfs /dev/vgdata/lvlonghorn
```
Before you can mount the device, you need to create the directory structure.
```
mkdir -p /var/lib/longhorn
```
Add an entry to fstab to ensure that the mount of the file system is persistent:
```
echo -e "/dev/vgdata/lvlonghorn /var/lib/longhorn xfs defaults 0 0" >> /etc/fstab
```
Finally, you can mount the file system as follows:
```
mount -a
```
