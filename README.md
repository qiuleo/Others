# Others
## virtualbox linux shared folders(linux server版共享文件夹)
### 1、创建目录
* mkdir -p /data/www /mnt/cdrom
* 安装增强功能
	+ mount /dev/sr0 /mnt/cdrom
	+ cd /mnt/cdrom & sh ./VBoxLinuxAdditions.run
	+ 若提示错误:`yum安装或更新kernel-deve`、`检查uname -r 与  /usr/src/kernels/[version]是否一致，不一致则通过yum update更新为一致，然后重启生效`
### 2、关闭虚拟机并创建共享文件夹
### 3、挂载
	+ cd /data & mount -t vboxsf -o rw,uid=501,gid=501 www ./www
	+ 说明：………………略
	+ 开机自动挂载 /etc/fstab (注意：virtualbox文件共享设置里，自动挂载选项不可以钩选)
    + www /data/www vboxsf rw,gid=501,uid=501,auto 0 0
