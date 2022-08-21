如何在一个新机器上配置git

1、下载git

linux:直接apt-get install git

windows：下载安装gitbash  https://www.git-scm.com/download/win

2、git 配置

git config --global user.name "name"

git config --global user.email "email"

3、配置公钥

ssh-keygen 生成密钥对

将公钥添加到github上