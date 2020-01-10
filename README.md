# UnblockNetEaseMusic 海外网易云音乐代理

#### 服务器信息</br>
    158.199.142.239 music.163.com
    158.199.142.239:8889 #Socks5方式

#### 使用方法

Windows:(不保证能用)
打开命令提示符（管理员权限），执行该命令

    echo 158.199.142.239 music.163.com >> C:\WINDOWS\System32\drivers\etc\hosts

Mac:</br>
打开终端，sudo vi /etc/hosts ，然后将以下添加进文件末尾</br>
    158.199.142.239 music.163.com

#### 实现原理

服务器上通过Nginx修改数据头部以被服务器认为国内IP，因为TLS的验证问题，遂无法在不安装证书的情况下提供代理服务。虽然可以通过SNIPROXY实现，但要一个国内IP开放80/443端口的难度我觉得太大了。
Nginx配置文件：

    server {
        listen 80;
        listen 443;
        server_name music.163.com;
    
        location / {
            proxy_pass https://music.163.com;
        }
    
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP #这里填入任意一个可用国内IP#;
        proxy_set_header X-Forwarded-For #这里填入任意一个可用国内IP#;  
    }
现新增Socks5方式，将网易云音乐的代理设置为Socks5代理后，所有流量将经由服务器，满足*.163.com *.126.net 的数据包将经由中国服务器出去，其他数据包则会被遗弃，因此请勿使用全局方式。

#### 备注
如果你有Quantumult/Surge/Shadowrocket，可以添加服务器和规则后解决iOS设备上的网易云音乐/MOO音乐的区域限制。

    //Netease  
    USER-AGENT,NeteaseMusic*,China  
    USER-AGENT,%E7%BD%91%E6%98%93%E4%BA%91%E9%9F%B3%E4%B9%90*,China  
    DOMAIN-SUFFIX,music.126.net,China  
    DOMAIN-SUFFIX,music.163.com,China  
    //Tencent  
    USER-AGENT,MOO%E9%9F%B3%E4%B9%90*,China  
    USER-AGENT,QQ%E9%9F%B3%E4%B9%90,China  
    DOMAIN-SUFFIX,qqmusic.qq.com,China  
    DOMAIN-SUFFIX,y.qq.com,China  
    DOMAIN,aqqmusic.tc.qq.com,China`
