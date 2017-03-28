# FinalSpeed
FinalSpeed是高速双边加速软件,可加速所有基于tcp协议的网络服务,在高丢包和高延迟环境下,仍可达到90%的物理带宽利用率,即使高峰时段也能轻松跑满带宽.

### 安装教程
[客户端安装说明](https://udpspeed.com/installclient)
<br />
[服务端安装说明](https://udpspeed.com/installserver)

### 说明


finalspeed作者开始卖收费版了，所以停止了免费版的更新，并且删除了所有代码。不过还好我fork了一份。。作为Openvz的救星，还是有不少人对finalspeed有需求的。


github地址：https://github.com/zmatsh/NSS



### NSS操作命令

编译： mvn clean package

运行: java -jar NSS.jar 

### socket5

tcpspeed 已经整合了socket5 ，finalspeed 没有整合，作为一个开发者我看不下去了。

NSS socket通讯部分采用 OSGI的方式集成的，配置信息在conf/config.xml内

socket 5 通讯端口 兼容 ss服务端。

```xml

<?xml version="1.0" encoding="UTF-8" ?>
<config>
	<ip_addr>127.0.0.1</ip_addr>
	<port>1085</port> 
	<local_ip_addr>127.0.0.1</local_ip_addr>
	<local_port>1081</local_port>
	<method>aes-256-cfb</method>
	<password>1111111111111</password>
</config>


```

### 友情提示：
    在实际情况影响下，tcpspeed 与 NSS 速度一致。
    搬瓦工服务器512M服务器能跑满北京联通100M宽带
    
### 快速启动：
```text
docker run -d --restart=always -e 'SS_PASSWORD=1111111111111111' -p 8338:8338/tcp -p 150:150/udp -p 150:150/tcp --name=my-fs-ss firshme/nssserver:latest
```
### ub2系统支持的docker比较好

#欢迎fork star

## 端口已经默认配置好了 只需要修改密码即可 socket Port 1081


