# 深圳大学-校园网络-ipv6配置


## 1. 在 [https://supes.top/](https://supes.top/)下载或定制适用于您设备的OpenWrt固件，记得必须勾选ipv6
![输入图片说明](/jpg/1.jpg)

## 2. 刷入固件，网页登录后台管理界面，进入“网络==>接口==>接口”
![输入图片说明](/jpg/2.jpg)
可以看到有三个网口lan、wan、wan6
其中wan6显示ipv6地址

进入“网络==>网络诊断”，测试ipv6能否使用
![输入图片说明](/jpg/3.jpg)

![输入图片说明](/jpg/4.jpg)
可以看到wan6虽然分配了ipv6但是还是不能直接使用ipv6


## 3. 进入“网络==>接口==>接口”，选择“wan6==>编辑==>DHCP服务器==>ipv6设置”
按下图设置
![输入图片说明](/jpg/5.jpg)
点击保存退出

## 4. 同样进入“网络==>接口==>接口”，选择“lan==>编辑==>DHCP服务器==>ipv6设置”
按下图设置
![输入图片说明](/jpg/6.jpg)
点击保存退出

## 5. 进入“网络==>防火墙”，按照下图配置，将入站数据、转发改成接受，并勾选“Enable full clone NAT6”
![输入图片说明](/jpg/7.jpg)

将拒绝全部改成接受
![输入图片说明](/jpg/8.jpg)

## 6. 进入“网络==>防火墙==>通行规则”，添加规则
![输入图片说明](/jpg/9.jpg)
![输入图片说明](/jpg/10.jpg)
再添加规则
![输入图片说明](/jpg/11.jpg)
![输入图片说明](/jpg/12.jpg)
保存应用
## 7. 重启路由器
