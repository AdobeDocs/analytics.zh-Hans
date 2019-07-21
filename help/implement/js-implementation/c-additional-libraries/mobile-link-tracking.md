---
description: 'null'
keywords: Analytics实施；链接引用；redir
seo-description: 'null'
seo-title: 移动协议上的自定义链接测量
solution: Analytics
title: 移动协议上的自定义链接测量
topic: 开发人员和实施
uuid: eb82de26-da2 e-41c2-8924-59b6 b5 ccf28
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 移动协议上的自定义链接测量

许多移动设备用户都会将播客、铃声及类似文件下载到自己的设备中。因为许多移动设备不支持 JavaScript，所以必须通过重定向实施链接测量。要使用重定向，必须修改 html 中的 href 链接来包含 REDIR 元素。自定义链接的常规格式如下所示：

```
https://<your_Namespace>.112.2o7.net/b/ss/<RSID>/4/REDIR/
?url=<destination_URL>&pe=<link_type>&pev1=<current_URL>&pev2=<link_name>
```

创建链接引用时，请记住以下事项：

* URL 值必须采用 URL 编码。
* 应设置一个 pageName 或页面 URL (g) 参数。
* 动态变量可以读取 URL 参数，但无法对其进行设置。
* 如果未设置任何 Cookie，Adobe 服务器会执行常规 Cookie 握手。
* 要跟踪链接，必须包含 pe、pev1 和 pev2 参数。

自定义链接测量 URL 如下所示：

```
<a href=" https://johnny_appleseed.122.2o7.net/b/ss/appleseedpodcasts/4/REDIR/
?url=http%3A%2F%2Fwww.johnny_appleseed.org%2Fmpegs%2Fplanting_apple_trees.mpeg&pe=lnk_d
&pev1=http%3A%2F%2Fwww.johnny_appleseed.org%2Fmpegs%2Fplanting_apple_trees.mpeg&pev2=pl anting_apple_trees&">Planting an Apple Tree</a>
```

有关更多信息，请参阅[“退出链接跟踪重定向”白皮书](https://marketing.adobe.com/resources/help/en_US/whitepapers/redirects/)。
