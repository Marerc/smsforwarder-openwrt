# smsforwarder-openwrt
a simple sms forwarder tool which can configured manmually runs in openwrt.
因为smstool3不支持那些只能使用text的电信卡托，所以自己就写了一个小应用来实现短信转发。
它默认将收到短信和未接来电保存到本机，可以通过配置邮件或者server酱id将收到的短信或者来电转发到你的微信里。

这是一个简单的，通过openwrt挂3g/4g上网卡，来转发短信或者未接来电到指定邮件，或者到微信server酱的工具。
它实现的功能：
  1、默认，保存收到的短信和未接来电到本机的特定位置
  2、可以配置，收到的邮件可以转发到特定的邮箱（需要配置），或者转发到server酱
  3、可以配置，外挂脚本可以配置将收到的短信和未接来电进行其他操作
  4、不可以：不可以发送短信，不可以接听电话（接听了也没有声音），不可以使用电话本（简化功能）

它的特点如下
  1、可以配过配置文件自定义配置与模块通信的不同的at指令。
  2、收到的短信或者未接来电通过外置脚本指定
  
工作原理流程：
读取配置-->打开串口-->识别设备-->保持通讯-->收到短信、电话-->保存（邮件，转发-->保持通讯
