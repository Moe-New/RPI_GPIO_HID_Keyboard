# RPI_GPIO_HID_Keyboard
使用树莓派 GPIO 控制的模拟键盘！

## 项目介绍：

这是一个简单的键盘模拟脚本。

从 Raspberry Pi 的 GPIO 读取按键状态，然后发送定义的 KeyCode 到 /dev/hidg0 触发 HID 键盘的输入。

使用的是机械键盘的任意轴体，两脚分别连接到 0v 和任意 PIN 口。

启动脚本时会将目标 PIN 调为 HIGH 模式，然后循环检测该 PIN 口状态。

轴体被按下时两脚将被短接，PIN 口会变成 LOW 模式，写入对应 KeyCode 后发送。

关于 HID Keyboard 具体原理请参考：[使用树莓派 Zero 实现带回显的新型 Bad USB](http://shumeipai.nxez.com/2018/06/26/using-raspberry-pi-zero-to-implement-new-bad-usb-with-echo.html)


## 依赖项目：

初始化 HID 设备：[Moe-New/P4wnP1](https://github.com/Moe-New/P4wnP1)（非必须，只要能初始化 HID 设备并控制就可以）

GPIO 控制：[RPi.GPIO · PyPI](https://pypi.org/project/RPi.GPIO/)（必须，python 控制 GPIO 的库）


## 适用设备：

Raspberry Pi Zero （未测试）

Raspberry Pi Zero W （当前主要测试环境）

或者其他支持作为 HID Device 的设备...


## 一些附加资料：

键值定义表：[10 keyboard keypad page (0x07)](http://d1.amobbs.com/bbs_upload782111/files_47/ourdev_692986N5FAHU.pdf)

键值在线查询：[USB HID Keyboard Scan Codes](https://serverhelfer.de/usb-hid-keyboard-scan-codes/)
