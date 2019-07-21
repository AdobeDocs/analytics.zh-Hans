---
description: 此信息适用于熟悉报表和实施的高级用户。如果不清楚后果，请不要尝试编辑实施。如果您要对实施进行更改，请联系贵组织的客户经理。
keywords: Analytics 实施
seo-description: 此信息适用于熟悉报表和实施的高级用户。如果不清楚后果，请不要尝试编辑实施。如果您要对实施进行更改，请联系贵组织的客户经理。
seo-title: 跨不同的实施类型跟踪
solution: Analytics
title: 跨不同的实施类型跟踪
topic: 开发人员和实施
uuid: a0a3229a-79a2-4dc2-b0 be-4b8 fox3 a
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 跨不同的实施类型跟踪

此信息适用于熟悉报表和实施的高级用户。如果不清楚后果，请不要尝试编辑实施。如果您要对实施进行更改，请联系贵组织的客户经理。

如果您使用多种类型的实施（例如 JavaScript 和硬编码图像请求），请确保指定以下变量并且相互匹配：

* *`s_account`*
* *`s.visitorNamespace`*
* *`s.trackingServer`*
* *`s.trackingServerSecure`* (如果使用SSL)

如果其中某个变量在实施中不匹配，可作为单独访客跟踪用户。
