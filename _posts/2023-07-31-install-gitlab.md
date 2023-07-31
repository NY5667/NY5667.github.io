---
layout: post
title:  'How to Install Gitlab on Ubuntu 23.04'
date:   2023-07-31 09:26:06 +0800
categories: NY5667 update
---

# Gitlab安装步骤

[https://wiki.crowncloud.net/index.php?How_to_Install_Gitlab_on_Ubuntu_23_04][How_to_Install_Gitlab_on_Ubuntu_23_04]

# 修改Gitlab端口

[https://forum.gitlab.com/t/how-change-port-of-gitlab/8582?utm_source=pocket_saves][how-change-port-of-gitlab]

```
/etc/gitlab/gitlab.rb
```

```
external_url 'http://myIPadress:8080'
```

# 查看Gitlab默认密码

[https://www.grepper.com/answers/506064/gitlab+default+password][gitlab_default_password]

```sh
/etc/gitlab/initial_root_password
```

[How_to_Install_Gitlab_on_Ubuntu_23_04]: https://wiki.crowncloud.net/index.php?How_to_Install_Gitlab_on_Ubuntu_23_04
[how-change-port-of-gitlab]: https://forum.gitlab.com/t/how-change-port-of-gitlab/8582?utm_source=pocket_saves
[gitlab_default_password]: https://www.grepper.com/answers/506064/gitlab+default+password