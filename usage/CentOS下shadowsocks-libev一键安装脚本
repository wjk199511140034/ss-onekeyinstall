本脚本适用环境：
系统支持：CentOS
内存要求：≥128M
日期：2018 年 06 月 01 日

关于本脚本：
一键安装 libev 版的 Shadowsocks 最新版本。该版本的特点是内存占用小（600k左右），低 CPU 消耗，甚至可以安装在基于 OpenWRT 的路由器上。
友情提示：如果你有问题，请先参考这篇《Shadowsocks Troubleshooting》后再问。


默认配置：
服务器端口：自己设定（如不设定，默认从 9000-19999 之间随机生成）
密码：自己设定（如不设定，默认为 teddysun.com）
加密方式：自己设定（如不设定，默认为 aes-256-gcm）

Shadowsocks for Windows 客户端下载：
https://github.com/shadowsocks/shadowsocks-windows/releases

使用方法：
使用root用户登录，运行以下命令：

wget --no-check-certificate -O shadowsocks-libev.sh https://raw.githubusercontent.com/wjk199511140034/ss-onekeyinstall/master/shadowsocks-libev.sh
chmod +x shadowsocks-libev.sh
./shadowsocks-libev.sh 2>&1 | tee shadowsocks-libev.log
安装完成后，脚本提示如下：

Congratulations, Shadowsocks-libev server install completed!
Your Server IP        :your_server_ip
Your Server Port      :your_server_port
Your Password         :your_password
Your Encryption Method:your_encryption_method

Welcome to visit:https://teddysun.com/357.html
Enjoy it!
卸载方法：
使用 root 用户登录，运行以下命令：

./shadowsocks-libev.sh uninstall
其他事项：
客户端配置的参考链接：https://teddysun.com/339.html

安装完成后即已后台启动 Shadowsocks-libev ，运行：

/etc/init.d/shadowsocks status
可以查看进程是否启动。
本脚本安装完成后，会将 Shadowsocks-libev 加入开机自启动。

使用命令：
启动：/etc/init.d/shadowsocks start
停止：/etc/init.d/shadowsocks stop
重启：/etc/init.d/shadowsocks restart
查看状态：/etc/init.d/shadowsocks status

更多版本 Shadowsocks 安装：
ShadowsocksR 版一键安装脚本（CentOS，Debian，Ubuntu）
Shadowsocks Python 版一键安装脚本（CentOS，Debian，Ubuntu）
Debian 下 Shadowsocks-libev 一键安装脚本
Shadowsocks-go 一键安装脚本（CentOS，Debian，Ubuntu）
Shadowsocks 一键安装脚本（四合一）

更新日志
2018 年 06 月 01 日：
1、新增：配置文件新增 fast_open 字段，并根据系统的内核版本，判断大于 3.7.0 时启用，否则不启用；
2、修正：在使用 /etc/init.d/shadowsocks restart 命令重启服务端时，偶尔出现的 “bind: Address already in use” 问题；
3、修正：移除配置文件中的 local_address 字段；
4、修改：不再默认使用 root 用户启动，改为使用 nobody 用户启动服务端 ss-server；
5、升级：mbedtls 到版本 2.9.0；
6、修改：启动脚本中的 -u 参数（即同时启用 TCP 和 UDP 模式），改到配置文件里配置为 “mode”: “tcp_and_udp”；
7、修改：配置文件的内置 NameServers 为 8.8.8.8，默认是从 /etc/resolv.conf 中取得。

2018 年 02 月 07 日：
1、修改：将默认端口从 8989 改为从 9000-19999 之间随机生成。

2017 年 09 月 16 日：
1、修正：Shadowsocks-libev 版 v3.1.0 使用 libc-ares 替换 libudns 依赖包，解决了依赖问题；
2、升级：mbedtls 到版本 2.6.0。

2017 年 07 月 22 日：
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
2017 年 02 月 24 日：
1、恢复： 通过 Github API 自动获取 Shadowsocks-libev 的最新 release 版本的功能（v3.0.3）。

2017 年 02 月 13 日：
1、更新：升级版本到 3.0.2。

2017 年 02 月 12 日：
1、更新：升级版本到 3.0.1（请下载最新的脚本来安装）。

2016 年 11 月 05 日：
1、新增：判断是否已安装，若已安装，则获取版本号与最新版比较，然后可以升级覆盖安装；
2、修正：未安装时获取最新版本号的问题。

2016 年 09 月 23 日：
1、修正：偶尔自动获取版本号失败的问题；
2、新增：自动判断如果 VPS 存在 IPv6 地址，则在配置文件里添加监听 IPv6 地址。

2016 年 09 月 17 日：
1、重构代码，自动获取 Github 上最新版来安装，不再手动修改版本号；
2、自动检测本机是否已经安装，若已安装则正常退出（若要安装新版，则需先卸载）；
3、改为下载 tar.gz 包来安装，不用依赖 unzip 命令。

2016 年 09 月 12 日：
1、更新：升级版本到 2.5.2。

2016 年 09 月 11 日：
1、更新：升级版本到 2.5.1。

2016 年 08 月 29 日：
1、更新：升级版本到 2.5.0；
2、修正：由于安装时文件名的更新，卸载时文件名改为一致。

2016 年 07 月 14 日：
1、更新：升级版本到 2.4.7。

2016 年 07 月 05 日：
1、修正：新增的依赖 xmlto、asciidoc；
2、修正：由于安装时文件名的更新，卸载时文件名改为一致。

2016 年 05 月 12 日：
1、新增：在 CentOS 7 下的防火墙规则设置。

2015 年 08 月 01 日：
1、新增：自定义服务器端口功能（如不设定，默认为 8989）。

2015 年 04 月 30 日：
1、修正：配置文件 /etc/shadowsocks-libev/config.json 同时启用 IPv4 与 IPv6 支持：

{
    "server":["[::0]","0.0.0.0"],
    "server_port":your_server_port,
    "local_address":"127.0.0.1",
    "local_port":1080,
    "password":"your_password",
    "timeout":600,
    "method":"aes-256-cfb"
}
2、Shadowsocks libev 版不能通过修改配置文件来多端口（只能开启多进程），如果你需要多端口请安装 Python 或 Go 版；

特别说明：
1、已安装旧版本的 shadowsocks 需要升级的话，需下载本脚本的最新版，直接运行即可自动升级

./shadowsocks-libev.sh
参考链接：
https://github.com/shadowsocks/shadowsocks-libev