## 板端程序
### 蓝牙连接imu && socket转发到pc


### 使用方法
启动蓝牙：确保蓝牙已经启动
在X3派中，每次开机后需要手动启动一次蓝牙
sudo /usr/bin/startbt6212.sh

连接imu：
python3 imu_node.py [蓝牙MAC地址] [PC的ip]

我们有两个imu，一个是IM900,一个是IM948,两个蓝牙的MAC地址是固定不变的。

* 对于IM900
python3 imu_node.py 7B:1D:DE:EA:17:49 127.0.0.1

* 对于IM948
python3 imu_node.py E0:E1:DD:8E:06:13 127.0.0.1

// 上面ip地址是根据PC的ip地址来输入的。 也可以不输入ip地址启动

支持两个imu设备同时接入

### 依赖安装
bluez
libbluetooth-dev
```
hciconfig
bluetoothctl
Agent registered
[CHG] Controller 8C:F8:C5:51:6D:95 Pairable: yes
[bluetooth]# scan on

```
注意修改port
通过``if a``查询host ip
如果启用Clash则port=7890
