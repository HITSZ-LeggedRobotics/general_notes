根据硬件接口（串口，USB或者ACM）来配置/etc/udev/rules.d中的udev文件，分别实现rplidar和stm32串口的设备绑定： 首先插入USB设备，
```bash
  $ lsusb
```
可以查看Vendor和Product的 ID，然后创建并配置/etc/udev/rules.d/rplidar.rules文件

`KERNEL=="ttyUSB*", ATTRS{idVendor}=="10c4", ATTRS{idProduct}=="ea60", MODE:="0777", SYMLINK+="rplidar"`

```bash
$ sudo service udev reload
$ sudo service udev restart
```
Vendor和Product的ID是一样的,一般可以用串口号不同（serial）作为属性来区分
```bash
udevadm info --attribute-walk --name=/dev/video0
```

```
SUBSYSTEM=="usb", ATTR{serial}=="68974689267119892", ATTR{idVendor}=="1871", ATTR{idProduct}=="0101", SYMLINK+="camera0"
SUBSYSTEM=="usb", ATTR{serial}=="12345698798725654", ATTR{idVendor}=="1871", ATTR{idProduct}=="0101", SYMLINK+="camera1"
```
