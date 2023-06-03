---
title:       "【git错误】Error: Failed to connect to github.com port 443 after 21074 ms: Timed out"
subtitle:    ""
description: ""
date:        2023-04-30
author:      "施艳春"
image:       ""
tags:        ["tag1", "tag2"]
categories:  ["Tech" ]
---
# 操作
1. 查询github的ip地址
打开https://www.ipaddress.com/，查询github.com
```bash
140.82.114.4 github.com
```
2. 修改host文件
- 打开文件夹C:\Windows\System32\drivers\etc，找到hosts文件，右键属性-安全里面修改权限。  
- 把 hosts 文件移动到桌面，打开方式选择记事本，在文末添加 ip 地址和域名（之间加一个空格），保存文件并重新移动回C:\Windows\System32\drivers\etc。  
- 最后打开浏览器设置，清空浏览器缓存，即可访问。

# 原理
Hosts文件简介:  
Hosts是一个没有扩展名的系统文件，主要作用是定义IP地址和主机名的映射关系，是一个映射IP地址和主机名的规定。当用户在浏览器中输入一个需要登录的网址时，系统会首先自动从Hosts文件中寻找对应的IP地址，一旦找到，浏览器会立即打开对应网页，如果没有找到，则浏览器会将网址提交DNS服务器进行IP地址解析。Hosts文件可以用文本文件打开！修改电脑和手机 Hosts 文件，可以绕过 DNS 为域名指定正确的 IP 地址，这也是快速打开网页的方法

# 参考资料
- [hosts文件位置以及如何修改hosts文件【Windows】【以github为例】](https://blog.csdn.net/pijiguai/article/details/122353357)
