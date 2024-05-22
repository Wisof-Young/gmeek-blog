![](https://oceanum.oss-cn-chengdu.aliyuncs.com/image/6c6e614eb8c110eb59c87ddce63bc726.jpeg)

## 安装系统

从 istoreos 官网上下载固件，使用 balenaEtcher 进行烧录

## 更改 IP

我打算将 R2S 作为旁路由使用，因此将主路由的 lan 口与 R2S 的 lan 口连接，插入烧录好的 TF 卡，通电开机，大约 2 分钟后进入系统。

istoreos 的默认 IP 一般是`192.168.100.1`，而我的主路由的 IP 为`192.168.0.1`，因此需要更改旁路由 IP。连接上主路由的 Wi-Fi，将电脑的 IP 设置为与旁路由同网段的地址，例如`192.168.100.10`，网关设置为旁路由 IP。浏览器输入`192.168.100.1`进入旁路由后台管理界面。

istoreos 有个很方便的功能叫「网络向导」：

![](https://oceanum.oss-cn-chengdu.aliyuncs.com/image/b924c21dbe02b18234572de3884b1866.jpeg)

点击「配置为旁路由」—「手动配置」，设置 IP 为主路由网段下任意 IP，网关和 dns 指向主路由。

## 互换网口

R2S 的 默认 lan 口是 usb 转接出来的，可能会对性能有影响，因此需要将 wan 口和 lan 口位置互换。在网络—接口中将设置改成这样：

![](https://oceanum.oss-cn-chengdu.aliyuncs.com/image/5d50bde002d12127a118f8c09a5a4dcd.png)

## 安装 passwall2

istoreos 不自带科学上网，因此需要自己手动安装。进入[https://github.com/AUK9527/Are-u-ok](https://github.com/AUK9527/Are-u-ok)，我选择下载 passwall2，得到一个后缀为`.run`的文件。进入 istoreos 后台，点击 istore，选择手动安装即可。

### passwall2 配置

我是参考的这篇文章：[https://www.right.com.cn/forum/thread-8325875-1-1.html](https://www.right.com.cn/forum/thread-8325875-1-1.html)

配置完成之后，将需要科学上网的设备的网关和 dns 都设为旁路由 ip 即可。

## 安装 xiaoya

istoreos 自带 docker，因此我安装了小雅 alist 作为自己的影视资源库。github 上有人做了一键脚本：[https://github.com/DDS-Derek/xiaoya-alist](https://github.com/DDS-Derek/xiaoya-alist)，非常方便。

<!-- ##{"timestamp":1714093961}## -->