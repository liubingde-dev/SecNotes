如何在一个新的ubuntu操作系统上安装yum

1、可以直接使用sudo  apt-get install yum安装

但是安装过程中可能会遇到“无法定位软件包的问题，可能是源配置的有问题”，所以需要添加和更新下源



当前使用的源为如下，亲测可以安装成功

> deb http://archive.ubuntu.com/ubuntu/ trusty main universe restricted multiverse
>
> deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ jammy main restricted universe multiverse
>  deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ jammy main restricted universe multiverse
> deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ jammy-updates main restricted universe multiverse
> deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ jammy-updates main restricted universe multiverse
> deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ jammy-backports main restricted universe multiverse
> deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ jammy-backports main restricted universe multiverse
> deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ jammy-security main restricted universe multiverse
> deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ jammy-security main restricted universe multiverse





具体更新源的步骤如下

1、修改/etc/apt/sources.list文件（可以先将之前的备份一下）

2、使用sudo apt-get update将sources.list的内容应用



这个过程可能会遇到证书问题（由于没有公钥，无法验证下列签名： NO_PUBKEY），可以按照以下方法解决

使用以下命令（更换为具体的值）

sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 76F1A20FF987672F

