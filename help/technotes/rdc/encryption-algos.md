---
title: 支持的HTTPS加密算法
description: 2022年6月23日，我们将删除对TLS 1.2加密的支持，这些加密对密码安全级别设置为“高”的客户使用SHA1或CBC。
feature: Regional Data Collection
source-git-commit: ce607610516a94e4d0fbbc53a1f8f53f5977a777
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 0%

---


# 支持的HTTPS加密算法

Adobe提供两个密码安全级别，以满足客户对第一方数据收集安全性的不同需求。 这些级别决定了与我们服务器的HTTPS连接支持哪些加密算法。 客户默认使用“标准”，该标准仅支持现代加密算法。 对于更关注这些连接的客户，“高”支持较少的加密算法列表。 对于这两个安全级别，Adobe会根据当前的安全实践定期更新一组受支持的算法。 如果要更改密码安全设置，请联系客户关怀团队。

2022年6月23日，我们将删除对TLS 1.2加密的支持，这些加密对密码安全级别设置为“高”的客户使用SHA1或CBC。  此更改将影响旧操作系统上最终用户的安全数据收集。

将不再支持以下TLS 1.2密码：

* TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA
* TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA
* TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA
* TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA
* TLS_RSA_WITH_AES_128_CBC_SHA
* TLS_RSA_WITH_AES_256_CBC_SHA

已知以下客户端会受此更改的影响，因为它们不支持当前加密标准：

* Windows 8.1及更早版本（上次更新于2018年）
* Windows Phone 8.1及更早版本（上次更新日期：2016年）
* OS X 10.10及更早版本（上次更新日期：2017年）
* iOS 8.4及更早版本（上次更新日期：2015年）

Android设备不受此更改的影响。

将密码安全级别设置为“标准”的客户不会受到此更改的影响。

