

https://teddysun.com/342.html


Shadowsocks Python��һ����װ�ű�

[CentOS��shadowsocksһ����װ�ű�]

���ű����û�����
ϵͳ֧�֣�CentOS 6��7��Debian��Ubuntu
�ڴ�Ҫ�󣺡�128M
���ڣ�2015��08��28��

���ڱ��ű���
һ����װ Python �� shadowsocks �����°棬ͬʱ��װ�� Python �������� pip��
������ʾ������������⣬���Ȳο���ƪ��Shadowsocks Troubleshooting�������ʡ�

Ĭ�����ã�
�������˿ڣ��Լ��趨���粻�趨��Ĭ��Ϊ8989��
�ͻ��˶˿ڣ�1080
���룺�Լ��趨���粻�趨��Ĭ��Ϊteddysun.com��
��ע���ű�Ĭ�ϴ������û������ļ����������ö��û�����װ��Ϻ��������Ľ̳� sample �ֶ��޸������ļ����������ɡ�

�ͻ������أ�
http://sourceforge.net/projects/shadowsocksgui/files/dist/

ʹ�÷�����
ʹ��root�û���¼�������������

wget --no-check-certificate https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks.sh
chmod +x shadowsocks.sh
./shadowsocks.sh 2>&1 | tee shadowsocks.log

��װ��ɺ󣬽ű���ʾ���£�

Congratulations, shadowsocks install completed!
Your Server IP:your_server_ip
Your Server Port:your_server_port
Your Password:your_password
Your Local IP:127.0.0.1
Your Local Port:1080
Your Encryption Method:aes-256-cfb

Welcome to visit:http://teddysun.com/342.html
Enjoy it!

ж�ط�����
ʹ��root�û���¼�������������

./shadowsocks.sh uninstall

���û������ļ� Sample��2015 �� 08 �� 28 ����������
�����ļ�·����/etc/shadowsocks.json

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

���û���˿������ļ� Sample��2015 �� 08 �� 28 ����������
�����ļ�·����/etc/shadowsocks.json

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

ʹ�����2015 �� 08 �� 28 ����������
������/etc/init.d/shadowsocks start
ֹͣ��/etc/init.d/shadowsocks stop
������/etc/init.d/shadowsocks restart
״̬��/etc/init.d/shadowsocks status

����汾 shadowsocks ��װ��
CentOS �� Shadowsocks-libev һ����װ�ű�
Debian �� Shadowsocks-libev һ����װ�ű�
Shadowsocks-go һ����װ�ű���CentOS��Debian��Ubuntu��

�ο����ӣ�
http://teddysun.com/339.html

������־��
��2015��08��28�գ�
1���������ƽű� /etc/init.d/shadowsocks �� CentOS 7 �޷��鿴 status �����⣻
��2015��08��01�գ�
1�������Զ���������˿ڹ��ܣ��粻�趨��Ĭ�϶˿�Ϊ 8989����
��2015��03��10�գ�
1�������� Debian��Ubuntu �µ�һ����װ��
��2015��01��21�գ�
1�����������ļ�����ٷ������� Sample һ�£�
2���޸������ű���ʹ�ùٷ������ĺ�̨������ֹͣ���
��2014��10��10�գ�
�����߷����˶��û���˿����⣬�����Ѹ��� Wiki ҳ�档���̳��������û���˿������ļ��� sample ��
��2014��09��24�գ�
������ö��û������������
��ע��Shadowsocks �Ѿ�֧�ֶ��û����������ļ������Ӳ�ͬ�Ķ˿ڣ���Ӧ��ͬ�����뼴�ɡ�
��2014��09��18�գ�
1����װ���һ��ʱ���ִ�����������������������°汾��

pip install -U shadowsocks

ע��������ɺ���Ҫ������һ�¡�
��2014��07��12�գ�
1��������ȡ���� IP ʱ��һ�����⡣���鲻Ҫʹ�ù����� IP �� VPS ��� Shadowsocks ����
��2014��05��29�գ�
1������ chkconfig ���ã�ʵ�� service ���
2�������ļ����� /etc/config.json ��Ϊ /etc/shadowsocks.json����ٷ�������һ�£���
3�������ļ������� workers ��ֵĬ��Ϊ 1����ٷ�����ͬ������
��2014��05��27�գ�
1����������������ʧЧ�����⡣
2���Ż��Ƿ��̨�����ɹ����ж��߼���
��2014��05��04�գ�
1�����������ӷ���ǽ�˿��߼����ж�bug�������Ѿ����� 8989 �˿ڵ�����£��������ٴ����ӡ�
2��������ȡ������ IP ���ж�bug�����ڶ� IP �� VPS ���������Ĭ��ֻȡ��һ������ IP д�������ļ���/etc/config.json���
3�����뿪����������

�ر�˵����
1���Ѱ�װ�ɰ汾�� shadowsocks ��Ҫ�����Ļ���ֱ������

pip install -U shadowsocks

 ������������ɺ���������