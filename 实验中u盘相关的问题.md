### u盘挂载时出现的u盘文件系统格式问题

该虚拟机只支持fat格式，没有安装exFAT以及NTFS格式驱动

![exfat.png](https://github.com/hughie-hy/USB-Driver/blob/main/image/exfat.png)

![image-20210107000813016](https://github.com/hughie-hy/USB-Driver/blob/main/image/ntfs.png)

64GG和64GG以上的Ｕ盘，在系统格式化里面没有Fat32格式的选择。可以通过其它软件或者批处理命令格式化成FAT32格式；这是由于FAT32格式不支持单个文件4GB以上容量，只有NTFS才支持；

64G以下U盘：

<img src="https://github.com/hughie-hy/USB-Driver/blob/main/image/haoyu.png" alt="haoyu.png" style="zoom:80%;" />

大于等于64G U盘

<img src="https://github.com/hughie-hy/USB-Driver/blob/main/image/pb.png" alt="pb.png" style="zoom:80%;" />



### 驱动装载时出现的段错误问题

驱动是因为在 `insmod` 的时候出现 `NULL` 指针异常, 导致驱动虽然被加载了( `myudisk` 驱动的结点已经被插入到内核设备树中), 但是驱动运行过程中却导致内核段错误 , 设备引用计数没有被正确释放掉, 而且也不可能被主动释放, 但是我们的驱动已经挂掉了

### U盘驱动中的U盘容量问题

u盘容量大于等于16G会出现段错误

