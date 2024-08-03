## how to extend root or /var
```
sudo fdsik /dev/sdx
mkfs.ext4 /dev/sdx
sudo vgextend ubuntu-vg /dev/sdx
```

```
sudo lvextend -l +50%FREE /dev/mapper/lv-0
sudo resize2fs /dev/mapper/lv-0
```

## how to extend /home/user/backup
### vgcreate
```
sudo vgcreate lv-ubuntu /dev/sdx
```
### lvcreate
```
sudo lvcreate -n backup -l 100%FREE lv-ubuntu
```
### mkfs
```
sudo mkfs.ext4 /dev/mapper/lv-ubuntu-backup
```
### mount
``` 
sudo mount -rw /de/mapper/lv-ubuntu-backup /home/user/backup
```
