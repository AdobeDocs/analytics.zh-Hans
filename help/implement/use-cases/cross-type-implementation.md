---
title: 跨不同的实施类型跟踪
description: 使用不同的实施类型并在不同实施类型之间无缝跟踪访客。
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '102'
ht-degree: 100%

---

# 跨不同的实施类型跟踪

此信息适用于熟悉报表和实施的高级用户。如果不清楚后果，请不要尝试编辑实施。如果您要对实施进行更改，请联系贵组织的客户经理。

如果您使用多种类型的实施（例如 JavaScript 和硬编码图像请求），请确保指定以下变量并且相互匹配：

* *`s_account`*
* *`s.visitorNamespace`*
* *`s.trackingServer`*
* *`s.trackingServerSecure`*（如果使用 SSL）

如果其中某个变量在实施中不匹配，可作为单独访客跟踪用户。
