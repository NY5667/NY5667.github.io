---
layout: post
title:  'Setting up an Apache Reverse Proxy'
date:   2023-09-08 15:11:06 +0800
categories: NY5667 update
---

1. 确保已经安装并正确配置了Apache HTTP服务器。
2. 打开 Apache 的配置文件，通常为 `httpd.conf` 文件。该文件通常位于 Apache 安装目录下的 `conf` 目录中。
3. 在配置文件中找到 `mod_proxy` 模块的相关行，确保该模块已经启用。您可以通过取消注释以下行来启用该模块（去除前面的 `#` 符号）：
```
LoadModule proxy_module modules/mod_proxy.so
LoadModule proxy_http_module modules/mod_proxy_http.so
```
4. 在配置文件的末尾添加以下代理设置（假设您希望将所有请求都转发到 `10.54.4.21:8080`）：
![](https://cdn.jsdelivr.net/gh/NY5667/CDN/images/Snipaste_2023-09-21_16-56-33.png)  
如果您只想将特定路径下的请求进行反向代理，可以将 `/` 替换为相应的路径。
5. 增加 `Listen` 配置项，指定反向代理要用的端口
```
#Listen 12.34.56.78:80
Listen 80
Listen 81
Listen 8081
Listen 9000
```
6. 保存并关闭配置文件。
7. 重启 Apache 服务器，以使配置更改生效。  
8. Apache 的配置文件[https://github.com/ny5667/apache-reverse-proxy/blob/main/httpd.conf][httpd.conf]

[httpd.conf]: https://github.com/ny5667/apache-reverse-proxy/blob/main/httpd.conf