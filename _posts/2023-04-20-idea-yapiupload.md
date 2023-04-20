---
layout: post
title:  "YapiUpload"
date:   2023-04-20 13:17:06 +0800
categories: NY5667 update
---

# 相关资源联接

[https://github.com/xujiaji/YapiIdeaUploadPlugin][YapiIdeaUploadPlugin]

[https://plugins.jetbrains.com/plugin/21322-yapiuploadpro][yapiuploadpro]

[https://juejin.cn/post/6883102559054888973][6883102559054888973]

[https://blog.csdn.net/Eddision/article/details/116042984][116042984]

# 一、 IDEA安装YapiUpload插件

![](http://zaq1.cloud/images/Snipaste_2023-04-20_13-31-47.png?imageslim)

安装后重启idea生效

# 二、在misc.xml中进行配置

配置内容

```
<component name="项目名">
    <option name="projectToken">YApi中项目的token</option>
    <option name="projectId">YApi中项目的id</option>
    <option name="yapiUrl">部署的YApi地址</option>    <option name="projectType">api</option>
    <option name="attachUploadUrl">上传java类zip的url</option>
 </component>
```

YApi中获取配置内容

1. 项目id

![](http://zaq1.cloud/images/Snipaste_2023-04-20_13-22-36.png?imageslim)

2. token

![](http://zaq1.cloud/images/Snipaste_2023-04-20_13-22-49.png?imageslim)

3. menu

![](http://zaq1.cloud/images/Snipaste_2023-04-20_13-23-07.png?imageslim)

4. 配置后效果

![](http://zaq1.cloud/images/Snipaste_2023-04-20_13-27-38.png?imageslim)

# 三、上传接口至YApi

![](http://zaq1.cloud/images/Snipaste_2023-04-20_13-23-55.png?imageslim)


[YapiIdeaUploadPlugin]: https://github.com/xujiaji/YapiIdeaUploadPlugin
[yapiuploadpro]: https://plugins.jetbrains.com/plugin/21322-yapiuploadpro
[6883102559054888973]: https://juejin.cn/post/6883102559054888973
[116042984]: https://blog.csdn.net/Eddision/article/details/116042984