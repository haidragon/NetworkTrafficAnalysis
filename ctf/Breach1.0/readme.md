# 配置
* 修改密码 https://blog.csdn.net/justloveyou_/article/details/78540990
* 修改地方 
* ![avatar](https://github.com/haidragon/NetworkTrafficAnalysis/blob/master/ctf/Breach1.0/images/%E4%BF%AE%E6%94%B9%E5%AF%86%E7%A0%81.jpg)
* 修改成动态ip
`
vi/etc/network/interfacs
sudo nano（gedit） /etc/network/interfaces

将里面
auto eth0
iface eth0 inet DHCP
这样就可以，其他的去掉
`
# 教程
* https://www.freebuf.com/articles/system/171318.html
