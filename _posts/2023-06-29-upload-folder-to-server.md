---
layout: post
title:  "upload files to an ftp server"
date:   2023-06-29 15:17:06 +0800
categories: NY5667 update
---

# Windows使用WinSCP.com连接服务器，并执行相关指令

![](https://cdn.jsdelivr.net/gh/NY5667/cdn/images/Snipaste_2023-06-30_09-06-16.png)

![](https://cdn.jsdelivr.net/gh/NY5667/cdn/images/Snipaste_2023-06-30_09-06-51.png)

```
@echo off

"C:\Program Files (x86)\WinSCP\WinSCP.com" ^
  /log="C:\writable\path\to\log\WinSCP.log" /ini=nul ^
  /command ^
    "open sftp://user:123456@192.168.176.76/ -hostkey=""ssh-ed25519 255 GaAcQIKVdSE2YUMXF92bau6sAbJOtoGAbVuuylvBSQE"" -rawsettings ProxyPort=0" ^
    "Your command 1" ^
    "Your command 2" ^
    "exit"

set WINSCP_RESULT=%ERRORLEVEL%
if %WINSCP_RESULT% equ 0 (
  echo Success
) else (
  echo Error
)

exit /b %WINSCP_RESULT%
```

连接服务器

```
open ftp://username:password@ftp_ip_address/
```

上传文件到服务器

```
synchronize remote c:\my-local-folder /my-server-folder/
```

从服务器下载文件到本地

```
get /my-server-folder c:\my-local-folder
```

# Ubuntu 使用lftp命令连接到服务器，并执行命令

从服务器下载文件到本地
```
lftp -u "$USER","$PASSWORD" $HOST <<EOF
mirror --use-pget-n=10 $REMOTE_DIR $LOCAL_DIR;
exit
EOF
```

把本地文件上传到服务器
```
#!/bin/bash

# 设置变量
local_directory="/path/to/local/directory"
remote_directory="/path/to/remote/directory"
server="ftp.example.com"
username="ftp_username"
password="ftp_password"

# 连接到FTP服务器并上传文件夹
lftp -e "open $server; user $username $password; cd $remote_directory; mirror --reverse $local_directory; quit"
```

# 文件上传下载链接资源

[https://www.baeldung.com/linux/ftp-download-all-files][ftp-download-all-files]

[https://winscp.net/eng/docs/scripting][winscp-scripting]

[ftp-download-all-files]: https://www.baeldung.com/linux/ftp-download-all-files
[winscp-scripting]: https://winscp.net/eng/docs/scripting