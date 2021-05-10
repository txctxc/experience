# VMware虚拟机安装Ubuntu16-18系统超详细过程含下载地址(https://blog.csdn.net/davidhzq/article/details/102575343)
注意事项：
+ VMware安装VMware Workstation Player16
+ 安装前关掉360安全卫士和360杀毒
+ 使用清华镜像https://mirrors.tuna.tsinghua.edu.cn/ubuntu-releases/和迅雷下载
+ 不用管VMware运行卡慢愿因分析及解决办法大全这篇博客，只要关掉Windows系统的360安全卫士和360杀毒，计算机速度就很快了:joy:。

# Ubuntu使用注意事项

## 返回Windows快捷键：
Ctrl+Alt
## 窗口适应问题：
+ Ubuntu报错：Could not apply the stored configuration for monitors  https://blog.csdn.net/qq_36743482/article/details/78862352
+ 在Ubuntu的设置里选择displays，将Resolution改为1364*709,再点Apply.
+ 使用虚拟机上方菜单栏的全屏模式
## Linux应用快捷键汇集（整理）  https://blog.csdn.net/dodobibibi/article/details/83418340
+ 调出terminal(终端) crtl+alt+t
+ 关闭当前窗口： Alt+F4
+ 关机：在终端输入：shutdown -h now
## linux shutdown 命令关机重启：
https://blog.csdn.net/q_l_s/article/details/44855817
## how to see all files in Ubuntu
+ Method1: press ctrl+h in file browser
+ Method2: use
```
ls -a
```
in terminal.
## how to copy a file's content to clipboard
```
$ sudo apt-get update
$ sudo apt-get install xclip
# Downloads and installs xclip. If you don't have `apt-get`, you might need to use another installer (like `yum`)

$ xclip -selection clipboard < ~/.ssh/id_ed25519.pub
# Copies the contents of the id_ed25519.pub file to your clipboard
```
## 安装chrome
https://www.itzgeek.com/how-tos/linux/ubuntu-how-tos/install-google-chrome-on-ubuntu-16-04.html

## Ubuntu 解压zip 文件到指定文件夹
```
sudo apt-get install unzip
unzip file.zip -d destination_folder
```
## qv2ray 下载安装遇到的坑
不要使用sudo 创建文件夹，不要使用sudo 移动文件，不要使用sudo 解压文件。
+ https://qv2ray.net/lang/zh/getting-started/step2.html#%E4%B8%8B%E8%BD%BD-v2ray-%E6%A0%B8%E5%BF%83%E6%96%87%E4%BB%B6
