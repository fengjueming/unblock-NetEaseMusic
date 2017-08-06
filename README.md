# UnblockNeteastMusic 海外网易云音乐代理

目前本服务运行于日本Cloudcore服务器，国内节点为移动。

#### 服务器信息</br>
`158.199.142.239 music.163.com`

iOS PAC</br>
`http://ming.moe/163.pac`

#### 使用方法

Windows:
打开命令提示符（管理员权限），执行该命令

`echo 158.199.142.239 music.163.com p1.music.126.net p2.music.126.net p3.music.126.net p4.music.126.net >> C:\WINDOWS\System32\drivers\etc\hosts`

Mac:</br>
打开终端，sudo vi /etc/hosts ，然后将以下添加进文件末尾</br>
`158.199.142.239 music.163.com p1.music.126.net p2.music.126.net p3.music.126.net p4.music.126.net`

iPhone:</br>
设置>WIFI，选择连接中的WiFi右边的按钮，在设置最下面选择自动，并填入以下字段</br>
http://ming.moe/163.pac</br>
如果需要于Cellular下使用，请购买shadowrocket并导入配置文件。</br>

有任何使用上的问题及其他需求，请联系fengjueming[at]gmail.com

#### 更新：</br>
8.6 更新shadowrocket配置文件，强制网易云音乐API走代理  
6.25 国内服务器爆炸，折腾了一下，直接换到放国内家里的服务器上去了  
5.31 优化日本节点，更换国内节点  
1.5 增加shadowrocket配置文件  
12.13 国内节点更换为景安，封面缓存也走服务器中转
