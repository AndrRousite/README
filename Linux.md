## Shell Command
1. 设置系统时区、时间
     ```apple js
     // 确定所在时区的编号
    liufeng@ubuntu:~$ tzselect
       ... 
    // 设置localtime
    liufeng@ubuntu:~$ sudo cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
    ```
2. 添加和删除用户
    ```apple js
    1. 添加
    sudo adduser xxx 这样的命令会在home目录下添加一个帐号
    sudo useradd xxx 仅仅是添加用户， 不会在home目录添加帐号
    （1） 打开终端 输入 sudo -r useradd 用户名 /* -r 参数建立系统用户
    （2） 输入 sudo useradd -g root 用户名 /*这一行的命令是让你的刚刚建立的 用户 划分到 root 权限组下
    （3）sudo passwd 用户名 /*设置你刚刚建立的密码
    2. 删除
     终端方法：以下用newuser代替想要删除的用户账户
     在root用户下：userdel -r newuser
     在普通用户下：sudo userdel -r newuser
     因为你需要彻底删除用户，所以加上-r的选项，在删除用户的同时一起把这个用户的宿主目录和邮件目录删除。
    ```
3. 搭建git局域网服务器
    ```apple js
       1. sudo apt-get install git
       2. 在任意目录初始化仓库
           git init --bare [repositories name].git
           修改git仓库的权限
           sudo chown -R liufeng:liufeng [repositories name].git
       3. Windows下clone仓库
           git clone git@192.168.11.175:/[repositories name].git的绝对路径
           如果出现Please make sure you have the correct access rights and the repository exists.
           那么ubuntu需要安装ssh
           sudo apt-get install openssh-client
    ```