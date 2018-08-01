# UnblockNetEaseMusic 海外网易云音乐代理

目前本服务运行于日本Cloudcore服务器，国内节点为移动。

#### 服务器信息</br>
`158.199.142.239 music.163.com`

~~iOS PAC</br>
`http://ming.moe/163.pac`~~

#### 使用方法

Windows:
打开命令提示符（管理员权限），执行该命令

`echo 158.199.142.239 music.163.com p1.music.126.net p2.music.126.net p3.music.126.net p4.music.126.net >> C:\WINDOWS\System32\drivers\etc\hosts`

Mac:</br>
打开终端，sudo vi /etc/hosts ，然后将以下添加进文件末尾</br>
`158.199.142.239 music.163.com p1.music.126.net p2.music.126.net p3.music.126.net p4.music.126.net`

iPhone:</br>
~~设置>WIFI，选择连接中的WiFi右边的按钮，在设置最下面选择自动，并填入以下字段</br>
http://ming.moe/163.pac</br>
如果需要于Cellular下使用，请购买shadowrocket并导入配置文件。</br>~~
~~现在iOS的客户端处理方式变得极为复杂，而且高度依赖HTTPS协议，在没有找到更好的解决方法之前建议使用Mac客户端~~
找到一个解决方法，需要Surge等软件配合。</br>
[Proxy]</br>
CloudMusic = http, 158.199.142.239, 80,,</br>
[Rule]</br>
USER-AGENT,NeteaseMusic*,CloudMusic</br>
[Host] #非必须，但建议加上，有助于图片加载</br>
p1.music.126.net = 158.199.142.239</br>
p2.music.126.net = 158.199.142.239</br>
p3.music.126.net = 158.199.142.239</br>
p4.music.126.net = 158.199.142.239</br>
