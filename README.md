### 百问网提供的 S3C2440 通用的 u-boot 源码 

拷贝 jz2440 的 uboot 源码和 patch 文件到 ubuntu 下

    user@vmware:~/workspace/mini2440/100ask$ ls
    u-boot-1.1.6.tar.bz2   u-boot-1.1.6_jz2440.patch

解压 uboot 并打补丁

    user@vmware:~/workspace/mini2440/100ask$ tar xjf u-boot-1.1.6.tar.bz2
    user@vmware:~/workspace/mini2440/100ask$ cd u-boot-1.1.6/
    user@vmware:~/workspace/mini2440/100ask/u-boot-1.1.6$ patch -p1 < ../u-boot-1.1.6_jz2440.patch 

配置编译 uboot

    user@vmware:~/workspace/mini2440/100ask/u-boot-1.1.6$ make 100ask24x0_config 
    Configuring for 100ask24x0 board...
    user@vmware:~/workspace/mini2440/100ask/u-boot-1.1.6$ make

下载 uboot 到开发板

    C:\Users\Administrator>oflash 0 1 0 0 0 Z:\mini2440\100ask\u-boot-1.1.6\u-boot.bin