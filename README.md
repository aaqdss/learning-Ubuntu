# learning-Ubuntu
一个菜鸟学习Ubuntu的经历
##简单记录一下安装使用经历
###1、Ubuntu基础命令
安装软件: sudo dpkg -i xxx.deb

更新命令 :sudo apt-get update

从网络获得软件:sudo apt-get install xxx

获得root权限：sudo su

安装修复关系：sudo apt-get -f install

software安装unity tweak tool可以实现启动栏置于下方和点击最小化

sudo do-release-upgrade -d

apt-cache search xxx搜索含有xxx的软件包名称

apt-cache depends xxx列出与xxx有依赖关系的软件包

apt-get -h 列出apt-get完整用法

###2、文件权限更改
sudo chmod 600 ××× （只有所有者有读和写的权限）
sudo chmod 644 ××× （所有者有读和写的权限，组用户只有读的权限）
sudo chmod 700 ××× （只有所有者有读和写以及执行的权限）
sudo chmod 666 ××× （每个人都有读和写的权限）
sudo chmod 777 ××× （每个人都有读和写以及执行的权限）

###3、解决问题

无法获得锁 /var/lib/dpkg/lock - open (11: 资源临时不可用)

解决：
其实这是因为有另外一个程序在运行，导致锁不可用。原因可能是上次运行更新或安装没有正常完成。解决办法是杀死此进程
sudo rm /var/cache/apt/archives/lock
sudo rm /var/lib/dpkg/lock



sudo dpkg --configure -a
dpkg：错误：正在解析文件 '/var/lib/dpkg/updates/0012' 第 0 行附近:
 在字段名 #padding 中发现换行符


解决如下：

sudo rm /var/lib/dpkg/updates/*
sudo apt-get update
sudo apt-get upgrade
