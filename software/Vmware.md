# VMware虚拟机安装Ubuntu16-18系统超详细过程含下载地址(https://blog.csdn.net/davidhzq/article/details/102575343)
注意事项：
+ VMware安装VMware Workstation pro
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

## vim
```
sudo apt-get update
sudo apt-get upgrade
sudo apt-get remove vim-common
sudo apt-get install vim
```
注意vim进入要先按i才进入编辑模式！
## 重启虚拟机网络命令
```
service network-manager restart
```
## Ubuntu终端的创建目录命令和创建文件命令不要混淆
+ 创建目录命令：
```
mkdir
```
+ 创建文件命令：
```
vim 新建文件名
```

## 切换root 和普通用户(我密码都是1）
```
su root
su 用户名
```
## 后面带~的是备份文件
别用gedit 创建文件，会自动创建备份文件，占据空间。目前我还没弄懂删除备份文件的方法。

推荐用vim创建文件
## 安装vim 插件
### 安装vim插件管理器：Vundle
主要参考以下3.(官方文档):
1. https://segmentfault.com/a/1190000019484603 (有许多错误内容）
2. https://blog.csdn.net/zhangpower1993/article/details/52184581
3. https://github.com/VundleVim/Vundle.vim

其中1.安装git 和curl部分应改为：
可以先
```
curl --version
```
然后按照提示安装
```
sudo apt install curl
```
然后
```
sudo git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
```
Then
```
vim ~/.vimrc
```
写入以下内容：
```vim
set nocompatible              " be iMproved, required
filetype off                  " required

" set the runtime path to include Vundle and initialize
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()
" alternatively, pass a path where Vundle should install plugins
"call vundle#begin('~/some/path/here')

" let Vundle manage Vundle, required
Plugin 'VundleVim/Vundle.vim'

" The following are examples of different formats supported.
" Keep Plugin commands between vundle#begin/end.
" plugin on GitHub repo
Plugin 'tpope/vim-fugitive'
" plugin from http://vim-scripts.org/vim/scripts.html
" Plugin 'L9'
" Git plugin not hosted on GitHub
Plugin 'git://git.wincent.com/command-t.git'
" git repos on your local machine (i.e. when working on your own plugin)
Plugin 'file:///home/gmarik/path/to/plugin'
" The sparkup vim script is in a subdirectory of this repo called vim.
" Pass the path to set the runtimepath properly.
Plugin 'rstacruz/sparkup', {'rtp': 'vim/'}
" Install L9 and avoid a Naming conflict if you've already installed a
" different version somewhere else.
" Plugin 'ascenator/L9', {'name': 'newL9'}

" All of your Plugins must be added before the following line
call vundle#end()            " required
filetype plugin indent on    " required
" To ignore plugin indent changes, instead use:
"filetype plugin on
"
" Brief help
" :PluginList       - lists configured plugins
" :PluginInstall    - installs plugins; append `!` to update or just :PluginUpdate
" :PluginSearch foo - searches for foo; append `!` to refresh local cache
" :PluginClean      - confirms removal of unused plugins; append `!` to auto-approve removal
"
" see :h vundle for more details or wiki for FAQ
" Put your non-Plugin stuff after this line
```
安装插件：
```
sudo vim +PluginInstall +qall
```
### 安装vim插件YouCompleteMe
主要参考：
https://zhuanlan.zhihu.com/p/98344227

```
sudo apt-get install gcc make python3-dev cmake g++
cd ~/.vim/bundle
sudo git clone https://github.com/ycm-core/YouCompleteMe.git
```

+ 安装python3.7
先安装依赖项：
```
sudo apt-get install libffi-dev libssl-dev libreadline-dev zlibc zlib1g zlib1g-dev -y
```
再按照https://www.codenong.com/cs107056617/ 设置系统默认python为python3.7。(尝试配置虚拟环境，参考文章https://blog.csdn.net/zhanghm1995/article/details/106467497 的方法2，pip版本问题以及sudo权限问题让我头大，结果没能成功 ，下面是命令行历史记录： 
  312  sudo -H pip3 install virtualenv virtualenvwrapperCollecting virtualenv
  313  pip install --upgrade virtualenv
  314  pip3 install --upgrade virtualenv
  315  sudo pip3 install virtualenv virtualenvwrapper
  316  sudo -H pip3 install virtualenv
  317  sudo -H pip3 install --upgrade virtualenv
  318  pip install --upgrade pip3
  319  pip3 install --upgrade pip3
  320  pip3 install --upgrade pip
  321  pip install --upgrade pip
  322  sudo -H pip3 install --upgrade pip
  323  sudo -H pip3 install virtualenvwrapper
  324  pip --version
  325  wget https://bootstrap.pypa.io/3.5/get-pip.py
  326  python3 get-pip.py
  327  wget https://bootstrap.pypa.io/pip/3.5/get-pip.py
  328  python3 get-pip.py
  329  python2 -V
  330  python3 -V
  331  which python
  332  cd /usr/bin/python
  333  ls
  334  cd /usr/bin/python/
  335  cd /Downloads
  336  cd ./Downloads
  337  ls
  338  cd ./Python-3.7.9
  339  ls
  340  ./configure
  341  make
  342  sudo make install
  343  python3.7
  344  cd /etc
  345  ls
  346  vim profile
  347  cd ~
  348  mv /usr/bin/python /usr/bin/python.bak
  349  sudo mv mv /usr/bin/python /usr/bin/python.bak
  350  sudo mv /usr/bin/python /usr/bin/python.bak
  351  ln -s /usr/local/bin/python3.7  /usr/bin/python
  352  sudo ln -s /usr/local/bin/python3.7  /usr/bin/python
  353  sudo mv /usr/bin/pip /usr/bin/pip.bak
  354  sudo ln -s /usr/local/bin/pip3.7 /usr/bin/pip
  355  python
  356  sudo update-alternatives --config python
  357  python3
  358  cd ~/.vim/bundle/YouCompleteMe
  359  python install.py --all
  360  git submodule update --init --recursive
  361  sudo git submodule update --init --recursive
  362  vim ~/.vimrc
）

然后：
```
cd ~/.vim/bundle/YouCompleteMe
python install.py --all
```
配置~/.vimrc

这个步骤官方上面没有说，但是需要做的，打开之前的~/.vimrc
```
vim ~/.vimrc
```
然后增加如下的语句。
```
Plugin 'VundleVim/YouCompleteMe'
```
注意要在两个call vundle之间，这两个call vundle之间是调用vundle的配置，所以肯定在这一部分加。

6.按理说这个时候用python差不多就可以了，但是我（ta）写C++的时候发现提醒~/.vim下缺少ycm_extra_conf.py，在YouCompleteMe下找到了这个文件，copy了一份到那个提醒的路径下就没报错了，但是我还没有弄清楚这个怎么回事，有时间搞搞看看。
####安装完vim系统找不到vim的解决办法
https://github.com/chxuan/vimplus/issues/130#issuecomment-766366105
