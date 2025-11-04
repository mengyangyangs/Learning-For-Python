# adb常用命令
1.上传文件到设备
adb push pc端文件名 设备路径

2.从设备拉取文件
adb pull 设备文件名 pc端路径

3.下载程序
adb install <path_to_apk>   参数：-r 覆盖安装

4.删除程序
adb uninstall <pakeage_name> 参数：-k 可以保存应用数据，卸载app

5.查看已连接设备
adb devices

6.进入shell
adb shell

7.重启设备
adb reboot 

8.查看实时日志，也可以把日志输出到pc端文件中
adb logcat / adb logcat > pc端文件的路径

9.清除日志
adb logcat -c

10.启动adb服务
adb start-server

11.终止adb服务
adb kill-server

12.获取管理员权限
adb root

13.查看adb版本
adb version

14.获取帮助
adb help

15.查看app的路径
adb shell pm path <pack_age_name>

# 常用linux命令行解释：
ls - Linux 中最常用的列出目录的命令	例如：ls 
pwd - 在 Linux 中打印工作目录命令	例如：pwd
cd - 用于浏览目录的 Linux 命令		例如：cd /etc
mkdir - 用于在 Linux 中创建目录的命令	例如：mkdir test
mv - 在 Linux 中移动或重命名文件	例如：（1）重命名 mv test test1 （2）移动 mv test1 /etc
cp - 与 mv 类似的用法，但用于在 Linux 中复制文件	例如：cp /mnt/test1 /etc/log  表示把/mnt目录下的test1文件，复制到/etc/log
rm - 删除文件或目录					例如：rm -rf /etc/log/test1  -rf表示强制删除递归目录文件
touch - 创建空白/空文件				例如：touch 1.txt
ln - 创建指向其他文件的符号链接（快捷方式）		例如：ln -s test1 tes  -s表示创建符号链接（软链接）
cat - 在终端上显示文件内容			例如：cat 1.txt
clear - 清除终端显示				例如：clear
echo - 打印命令后面的任何文本		例如：echo “Hello”
less - Linux 命令在终端中显示分页输出	例如：less 1.txt
man - 访问所有 Linux 命令的手册页	例如：man ls
uname - 用于显示系统信息，包括操作系统名称、主机名、内核版本	例如：uname -a   -a表示显示所有信息，包括操作系统名称、主机名、内核版本、内核发布日期、机器硬件名称、处理器类型、硬件平台和操作系统版本
whoami - 获取活动用户名				例如：whoami
tar - 在 Linux 中提取和压缩文件的命令	例如：tar cvf archive.tar example_dir  把_dir 变成 .tar
grep - 在输出中搜索字符串			例如：grep "hello" 1.txt
head - 从顶部返回指定的行数			例如：head 1.txt
tail - 从底部返回指定的行数			例如：tail 1.txt
diff - 查找两个文件之间的差异		例如：diff 1.txt 2.txt
cmp - 用于比较两个文件的内容，并报告它们之间的差异，cmp 主要用于二进制文件的比较			例如：cmp 1.txt 2.txt
comm - 用于比较两个已排序的文件，并输出它们之间的差异			例如：comm 1.txt 2.txt
sort - Linux 命令，用于在输出时对文件内容进行排序	例如：sort -o 1.txt
export - 在 Linux 中导出环境变量	例如：export MY_VER=“Hello”    export variable_name=value
zip - 压缩文件和目录的命令行工具	例如：zip 12.zip 1.txt 2.txt   把1.txt 和 2.txt 压缩成12.zip
unzip - 在 Linux 中解压缩文件		例如：unzip -d 12.zip /指定路径/  -d 表示指定路径   
ssh - Linux 中用于安全远程登录和其他网络服务的协议	例如：ssh example.com 或者 ssh -p 2222 user@example.com   -p表示指定连接的端口
service - 用于启动和停止服务的 Linux 命令	例如：service nginx start 或 service nginx stop
ps - 显示活动进程					例如：ps
kill and kill all - 按进程 ID 或名称终止活动进程	例如：kill PID 或 kill -9 PID  -9表示强制结束
df - 显示磁盘文件系统信息			例如：df -h   -h表示以人类可读的格式显示磁盘使用情况
mount - 在 Linux 中挂载文件系统		例如：mount -t ntfs /dev/sda1  /mnt/sde   -t表示指定文件系统类型
chmod - 更改文件权限的命令			例如：chmod 777 文件名 
chown - 用于授予文件或文件夹所有权的命令	例如：chown root：yyy 1.txt  表示将文件1.txt的所有者更改为root，所属组为yyy
ifconfig - 显示网络接口和 IP 地址	例如：ifconfig
traceroute - 跟踪数据包在网络中从源主机到目标主机的路径		例如：traceroute www.baidu.com 
wget - 从互联网直接下载文件,支持 HTTP、HTTPS 和 FTP 协议	例如：wget https://example.com/file.zip		表示下载一个文件并保存为默认文件名   -O表示指定保存文件名 wget -O yyy.zip https://example.com/file.zip
ufw - 是一个用于管理 Linux 系统防火墙的工具					例如：ufw enable 表示开启ufw防火墙
iptables - 用于设置、维护和检查 IP 数据包过滤规则的工具		例如：iptables -L  表示列出所有链的规则
apt， pacman， yum， rpm - 软件包管理器取决于发行版			例如：安装 yum install -y <packeage_name> / apt install <packe_name> / pacman <packeage_name> -S /  rpm -ivh <package_rpm>   
																  卸载：apt remove <packeage_name> / pacman -R <packeage_name> / yum remove <packeage_name> / rpm -e <packeage_name>
sudo - 允许普通用户在不切换到 root 用户的情况下执行需要更高权限的命令			例如：sudo apt update
cal - 查看命令行日历				例如：cal 表示查看当前月份日历
alias - 为常用命令创建自定义快捷方式				例如：alias ll="ls -la"  表示创建简单的别名
dd - 用于备份、恢复、创建启动盘、转换文件格式		例如：dd if=input.txt of=output.txt    表示将一个文件复制到另一个文件  if表示指定输入文件 of表示指定输出文件
whereis - 查找命令、源代码和手册页的命令			例如：whereis ls 表示查看ls的位置路径
whatis - 快速查找命令或程序的简短描述的命令					例如：whatis ls  表示查找ls的命令描述
top - 实时监控系统性能和进程的命令行工具					例如：top 
useradd and usermod - 添加新用户或更改现有用户数据			例如：useradd -m newuser   表示创建一个名为 newuser 的用户，并自动创建主目录  -m表示创建用户的主目录（如果指定的目录不存在）    
																  usermod -d /home/newuser2 newuser   表示将用户 newuser 的主目录修改为 /home/newuser2  -d表示修改用户的主目录
passwd - 为现有用户创建或更新密码					例如：passwd     passwd yyy 表示更改yyy的密码
