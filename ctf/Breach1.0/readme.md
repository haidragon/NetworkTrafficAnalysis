1.修改密码 https://blog.csdn.net/justloveyou_/article/details/78540990

2.修改成动态ip
修改/etc/network/interfacs
sudo nano（gedit） /etc/network/interfaces

将里面
auto eth0
iface eth0 inet DHCP
这样就可以，其他的去掉