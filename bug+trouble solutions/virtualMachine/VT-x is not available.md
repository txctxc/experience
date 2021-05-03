# Win10 10月更新 VirtualBox VT-x is not available (VERR_VMX_NO_VMX). 解决

imilano 2018-10-13 14:59:50  33967  收藏 13
分类专栏： 问题一堆堆
版权
使用 VirtualBox 打开之前新建的虚拟电脑不能用了，使用 VMWare 发现也不可以。其中virtualbox 报错如下：

VT-x is not available (VERR_VMX_NO_VMX).  返回 代码: E_FAIL (0x80004005) 组件: ConsoleWrap 界面: IConsole {872da645-4a9b-1727-bee2-5585105b9eed}
1
猜测是win10 10月更新的锅（摊手.jpg）

关闭 Hyper-V 并重启并没有解决问题。最后在VirtualBox社区找到如下解决方案：

+ 首先，管理员身份打开提示符。

+ 输入 bcdedit 并回车，找到hypervisorlaunchtype选项发现为auto

+ 输入命令bcdedit /set hypervisorlaunchtype off

+ 重启电脑

+ 问题解决。

bcdedit是什么？
bcdedit 是一个启动选项编辑工具，用来管理启动设置。

BCDEdit 不是一个运行于图形界面下的程序，而是一个命令行工具，该文件 (Bcdedit.exe) 位于 “\Windows\System32” 目录下。通过命令行工具 Bcdedit ，我们可以添加、删除及修改 BCD (Boot Configuration Data) 中的对象。在 BCD 中，每个对象均具有唯一的 GUID (Globally Unique Identifier : 全局唯一标识符 ) ，如系统中的每块硬盘、每个分区的 GUID ( 全局唯一标识符 ) 均不相同。

Hyper-V 是什么？
Hyper-V是微软的一款虚拟化产品，是微软第一个采用类似Vmware和Citrix开源Xen一样的基于hypervisor的技术。这也意味着微软会更加直接地与市场先行者VMware展开竞争，但竞争的方式会有所不同。
Hyper-V是微软提出的一种系统管理程序虚拟化技术，能够实现桌面虚拟化 [1] 。

————————————————
版权声明：本文为CSDN博主「imilano」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/imilano/article/details/83038682
