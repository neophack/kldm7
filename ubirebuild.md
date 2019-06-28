```
nn@nn-W65KJ1-KK1:~$ sudo modprobe mtd
[sudo] nn 的密码： 
nn@nn-W65KJ1-KK1:~$ sudo modprobe mtdblock
nn@nn-W65KJ1-KK1:~$ sudo modprobe nandsim first_id_byte=0x20 second_id_byte=0xa2 third_id_byte=0x00 fourth_id_byte=0x15
nn@nn-W65KJ1-KK1:~$ cat /proc/mtd
dev:    size   erasesize  name
mtd0: 04000000 00020000 "NAND simulator partition 0"


nn@nn-W65KJ1-KK1:/media/nn/D/binwalk-master$ sudo dd if=xaa of=/dev/mtd0
[sudo] nn 的密码： 
记录了122880+0 的读入
记录了122880+0 的写出
62914560 bytes (63 MB, 60 MiB) copied, 2.13541 s, 29.5 MB/s

nn@nn-W65KJ1-KK1:/media/nn/D/binwalk-master$ sudo modprobe ubi
nn@nn-W65KJ1-KK1:/media/nn/D/binwalk-master$ sudo ubiattach /dev/ubi_ctrl -m 0 -O 2048
UBI device number 0, total 512 LEBs (65011712 bytes, 62.0 MiB), available 107 LEBs (13586432 bytes, 13.0 MiB), LEB size 126976 bytes (124.0 KiB)

nn@nn-W65KJ1-KK1:/media/nn/D/binwalk-master$ sudo mount -t ubifs ubi0_0 /mnt/ubi/
```
