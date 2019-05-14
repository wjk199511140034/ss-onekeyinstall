本脚本适用环境：
系统支持：CentOS 6，7，Debian，Ubuntu
内存要求：≥128M
日期：2018 年 02 月 07 日

关于本脚本：
一键安装 Python 版 Shadowsocks 的最新版。
友情提示：如果你有问题，请先参考这篇《Shadowsocks Troubleshooting》后再问。


默认配置：
服务器端口：自己设定（如不设定，默认从 9000-19999 之间随机生成）
密码：自己设定（如不设定，默认为 teddysun.com）
加密方式：自己设定（如不设定，默认为 aes-256-gcm）
备注：脚本默认创建单用户配置文件，如需配置多用户，安装完毕后参照下面的教程示例手动修改配置文件后重启即可。

Shadowsocks for Windows 客户端下载：
https://github.com/shadowsocks/shadowsocks-windows/releases

使用方法：
使用root用户登录，运行以下命令：

wget --no-check-certificate -O shadowsocks.sh https://raw.githubusercontent.com/wjk199511140034/ss-onekeyinstall/master/shadowsocks.sh
chmod +x shadowsocks.sh
./shadowsocks.sh 2>&1 | tee shadowsocks.log
安装完成后，脚本提示如下：

Congratulations, Shadowsocks-python server install completed!
Your Server IP        :your_server_ip
Your Server Port      :your_server_port
Your Password         :your_password
Your Encryption Method:your_encryption_method

Welcome to visit:https://teddysun.com/342.html
Enjoy it!
卸载方法：
使用root用户登录，运行以下命令：

./shadowsocks.sh uninstall
单用户配置文件示例（2015 年 08 月 28 日修正）：
配置文件路径：/etc/shadowsocks.json

{
    "server":"0.0.0.0",
    "server_port":your_server_port,
    "local_address":"127.0.0.1",
    "local_port":1080,
    "password":"your_password",
    "timeout":300,
    "method":"your_encryption_method",
    "fast_open": false
}
多用户多端口配置文件示例（2015 年 08 月 28 日修正）：
配置文件路径：/etc/shadowsocks.json

{
    "server":"0.0.0.0",
    "local_address":"127.0.0.1",
    "local_port":1080,
    "port_password":{
         "8989":"password0",
         "9001":"password1",
         "9002":"password2",
         "9003":"password3",
         "9004":"password4"
    },
    "timeout":300,
    "method":"your_encryption_method",
    "fast_open": false
}
使用命令（2015 年 08 月 28 日修正）：
启动：/etc/init.d/shadowsocks start
停止：/etc/init.d/shadowsocks stop
重启：/etc/init.d/shadowsocks restart
状态：/etc/init.d/shadowsocks status

更多版本 Shadowsocks 服务端一键安装脚本：
ShadowsocksR 版一键安装脚本（CentOS，Debian，Ubuntu）
CentOS 下 Shadowsocks-libev 一键安装脚本
Debian 下 Shadowsocks-libev 一键安装脚本
Shadowsocks-go 一键安装脚本（CentOS，Debian，Ubuntu）
Shadowsocks 一键安装脚本（四合一）

参考链接：
https://teddysun.com/339.html

更新日志
（2018 年 02 月 07 日）
1、修改：将默认端口从 8989 改为从 9000-19999 之间随机生成。

（2017 年 07 月 21 日）
1、修正：默认加密方式从 aes-256-cfb 改为 aes-256-gcm（官方原版客户端支持该加密方式）；
2、新增：安装时可选 16 种加密方式的其中之一。如下所示：

aes-256-gcm
aes-192-gcm
aes-128-gcm
aes-256-ctr
aes-192-ctr
aes-128-ctr
aes-256-cfb
aes-192-cfb
aes-128-cfb
camellia-128-cfb
camellia-192-cfb
camellia-256-cfb
chacha20-ietf-poly1305
chacha20-ietf
chacha20
rc4-md5
（2016 年 08 月 18 日）
1、修正：默认安装 Github 上 master 分支最新版本（目前为 2.9.0）。
2、修正：由于原作者已经不再更新 pip 下的源代码，故不再使用 pip 安装 Shadowsocks，而是改为下载 Github 的 master 分支来安装。如果在一段时间后，版本升级了，则先卸载，并再次执行本脚本就可以升级为最新版。

（2016 年 05 月 12 日）
1、新增在 CentOS 7 下的防火墙规则设置。

（2015 年 08 月 28 日）
1、修正控制脚本 /etc/init.d/shadowsocks 在 CentOS 7 无法查看 status 的问题。

（2015 年 08 月 01 日）
1、新增自定义服务器端口功能（如不设定，默认端口为 8989）；

（2015 年 03 月 10 日）
1、新增在 Debian、Ubuntu 下的一键安装；

（2015 年 01 月 21 日）
1、修正配置文件，与官方给出的 Sample 一致；
2、修改启动脚本，使用官方给出的后台启动和停止命令。

（2014 年 10 月 10 日）
跟作者反馈了多用户多端口问题，作者已更新 Wiki 页面。本教程新增多用户多端口配置文件的 sample 。

（2014 年 09 月 24 日）
如何配置多用户？详见：这里
备注：Shadowsocks 已经支持多用户，在配置文件中增加不同的端口，对应不同的密码即可。

（2014 年 07 月 12 日）
1、修正获取公网 IP 时的一个问题。建议不要使用共享公网 IP 的 VPS 来搭建 Shadowsocks 服务。

（2014 年 05 月 29 日）
1、增加 chkconfig 配置，实现 service 命令。
2、配置文件名从 /etc/config.json 改为 /etc/shadowsocks.json（与官方的命名一致）。
3、配置文件中新增 workers ，值默认为 1（与官方配置同步）。

（2014 年 05 月 27 日）
1、修正开机自启动失效的问题。
2、优化是否后台启动成功的判断逻辑。

（2014 年 05 月 04 日）
1、修正对增加防火墙端口逻辑的判断bug，对于已经放行 8989 端口的情况下，则无需再次增加。
2、修正获取服务器 IP 的判断bug，对于多 IP 的 VPS 或服务器，默认只取第一个公网 IP 写到配置文件（/etc/config.json）里。
3、加入开机自启动。