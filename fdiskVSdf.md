## df fdisk -l 显示的磁盘容量有区别
购买的vps，执行df 和 fdisk -l 显示磁盘容量不同

```
Disk /dev/vda: 21.5 GB, 21474836480 bytes
255 heads, 63 sectors/track, 2610 cylinders
Units = cylinders of 16065 * 512 = 8225280 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disk identifier: 0x000084f7

   Device Boot      Start         End      Blocks   Id  System
/dev/vda1   *           1        2481    19920704   83  Linux
/dev/vda2            2481        2611     1048576   82  Linux swap / Solaris
```

而df的空间只有2G左右

命令：
resize2fs /dev/vda1

问题解决。