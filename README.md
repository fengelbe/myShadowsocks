

https://teddysun.com/342.html


Shadowsocks Python版一键安装脚本

[CentOS下shadowsocks一键安装脚本]

本脚本适用环境：
系统支持：CentOS 6，7，Debian，Ubuntu
内存要求：≥128M
日期：2015年08月28日

关于本脚本：
一键安装 Python 版 shadowsocks 的最新版，同时安装了 Python 包管理工具 pip。
友情提示：如果你有问题，请先参考这篇《Shadowsocks Troubleshooting》后再问。

默认配置：
服务器端口：自己设定（如不设定，默认为8989）
客户端端口：1080
密码：自己设定（如不设定，默认为teddysun.com）
备注：脚本默认创建单用户配置文件，如需配置多用户，安装完毕后参照下面的教程 sample 手动修改配置文件后重启即可。

客户端下载：
http://sourceforge.net/projects/shadowsocksgui/files/dist/

使用方法：
使用root用户登录，运行以下命令：

wget --no-check-certificate https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks.sh
chmod +x shadowsocks.sh
./shadowsocks.sh 2>&1 | tee shadowsocks.log

安装完成后，脚本提示如下：

Congratulations, shadowsocks install completed!
Your Server IP:your_server_ip
Your Server Port:your_server_port
Your Password:your_password
Your Local IP:127.0.0.1
Your Local Port:1080
Your Encryption Method:aes-256-cfb

Welcome to visit:http://teddysun.com/342.html
Enjoy it!

卸载方法：
使用root用户登录，运行以下命令：

./shadowsocks.sh uninstall

单用户配置文件 Sample（2015 年 08 月 28 日修正）：
配置文件路径：/etc/shadowsocks.json

{
    "server":"0.0.0.0",
    "server_port":8989,
    "local_address":"127.0.0.1",
    "local_port":1080,
    "password":"yourpassword",
    "timeout":300,
    "method":"aes-256-cfb",
    "fast_open": false
}

多用户多端口配置文件 Sample（2015 年 08 月 28 日修正）：
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
    "method":"aes-256-cfb",
    "fast_open": false
}

使用命令（2015 年 08 月 28 日修正）：
启动：/etc/init.d/shadowsocks start
停止：/etc/init.d/shadowsocks stop
重启：/etc/init.d/shadowsocks restart
状态：/etc/init.d/shadowsocks status

更多版本 shadowsocks 安装：
CentOS 下 Shadowsocks-libev 一键安装脚本
Debian 下 Shadowsocks-libev 一键安装脚本
Shadowsocks-go 一键安装脚本（CentOS，Debian，Ubuntu）

参考链接：
http://teddysun.com/339.html

更新日志：
（2015年08月28日）
1、修正控制脚本 /etc/init.d/shadowsocks 在 CentOS 7 无法查看 status 的问题；
（2015年08月01日）
1、新增自定义服务器端口功能（如不设定，默认端口为 8989）；
（2015年03月10日）
1、新增在 Debian、Ubuntu 下的一键安装；
（2015年01月21日）
1、修正配置文件，与官方给出的 Sample 一致；
2、修改启动脚本，使用官方给出的后台启动和停止命令。
（2014年10月10日）
跟作者反馈了多用户多端口问题，作者已更新 Wiki 页面。本教程新增多用户多端口配置文件的 sample 。
（2014年09月24日）
如何配置多用户？详见：这里
备注：Shadowsocks 已经支持多用户，在配置文件中增加不同的端口，对应不同的密码即可。
（2014年09月18日）
1、安装完成一段时间后，执行下面的命令可以升级到最新版本。

pip install -U shadowsocks

注意升级完成后需要再重启一下。
（2014年07月12日）
1、修正获取公网 IP 时的一个问题。建议不要使用共享公网 IP 的 VPS 来搭建 Shadowsocks 服务。
（2014年05月29日）
1、增加 chkconfig 配置，实现 service 命令。
2、配置文件名从 /etc/config.json 改为 /etc/shadowsocks.json（与官方的命名一致）。
3、配置文件中新增 workers ，值默认为 1（与官方配置同步）。
（2014年05月27日）
1、修正开机自启动失效的问题。
2、优化是否后台启动成功的判断逻辑。
（2014年05月04日）
1、修正对增加防火墙端口逻辑的判断bug，对于已经放行 8989 端口的情况下，则无需再次增加。
2、修正获取服务器 IP 的判断bug，对于多 IP 的 VPS 或服务器，默认只取第一个公网 IP 写到配置文件（/etc/config.json）里。
3、加入开机自启动。

特别说明：
1、已安装旧版本的 shadowsocks 需要升级的话，直接运行

pip install -U shadowsocks

 即可升级。完成后需重启。