### 免拆卡 在线全新刷机指南

**注意：全新刷机会丢失所有数据和设置！**

全新刷机适合于以下情形：
* 误删系统文件，但还可以启动。
* 切换其他的编译版本。
* 彻底重置系统。

全新刷机不是安全擦除，无法确保MicroSD卡上的所有数据不被数据恢复软件或数据恢复专家恢复或访问。

#### gz格式压缩包
1. 首先确保`pv`、`dd`和`gunzip`均已安装，并且可以调用。（`gunzip`是`gzip`包的调用名称）
2. 使用Web管理页面的文件传输功能，或者其他你熟悉的文件传输方式，将固件文件（gz压缩包）上传到`/tmp`目录或其子目录下。
3. 使用下面的命令刷机。注意一旦出现进度条，千万**不可以**使用`Ctrl`+`C`组合键中断该过程。

```bash
echo 1 > /proc/sys/kernel/sysrq
echo u > /proc/sysrq-trigger || umount /
pv /tmp/upload/FriendlyWrt_20200425_NanoPi-R2S_arm64_sd.img.gz | gunzip -dc | dd of=/dev/mmcblk0 conv=fsync
echo b > /proc/sysrq-trigger
```
#### zst格式压缩包
大致步骤与上面相同。  
1. 需要确保`pv`、`dd`和`zstdcat`均已安装，并且可以调用（`zstdcat`是`zstd`包的一个调用名称）。
2. 上传固件文件。
3. 然后使用下面的命令刷机（仅第三行不一样）。
```bash
echo 1 > /proc/sys/kernel/sysrq
echo u > /proc/sysrq-trigger || umount /
pv /tmp/upload/FriendlyWrt_20200425_NanoPi-R2S_arm64_sd.img.zst | zstdcat | dd of=/dev/mmcblk0 conv=fsync
echo b > /proc/sysrq-trigger
```
