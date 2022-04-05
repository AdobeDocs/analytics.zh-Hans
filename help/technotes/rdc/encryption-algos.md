---
title: 支持的 HTTPS 加密算法
description: 在 2022 年 6 月 23 日，我们将为密码安全级别设置为“高”的客户取消对使用 SHA1 或 CBC 的 TLS 1.2 密码的支持。
feature: Regional Data Collection
exl-id: f1cbb0cb-fd65-4f22-8594-0d97b6906698
source-git-commit: a1ae98d6907960135c1dfa03ed10738eac8bec0d
workflow-type: ht
source-wordcount: '273'
ht-degree: 100%

---

# 支持的 HTTPS 加密算法

Adobe 提供两种密码安全级别，以满足客户对第一方数据收集安全性的不同需求。这些级别决定了与我们服务器的 HTTPS 连接支持哪些加密算法。客户默认使用“标准”，它仅支持现代加密算法。对于更关心这些连接的客户，“高”支持较小的加密算法列表。对于这两个安全级别，Adobe 会根据当前的安全实践定期更新支持的算法集。如果您想更改密码安全设置，请联系客户关怀部门。

在 2022 年 6 月 23 日，我们将为密码安全级别设置为“高”的客户取消对使用 SHA1 或 CBC 的 TLS 1.2 密码的支持。此更改将影响最终用户在旧操作系统上的安全数据收集。

将不再支持以下 TLS 1.2 密码：

* TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA
* TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA
* TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA
* TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA
* TLS_RSA_WITH_AES_128_CBC_SHA
* TLS_RSA_WITH_AES_256_CBC_SHA

已知以下客户端会受到此更改的影响，因为它们缺乏对当前加密标准的支持：

* Windows 8.1 及更早版本（最后更新于 2018 年）
* Windows Phone 8.1 及更早版本（最后更新于 2016 年）
* OS X 10.10 及更早版本（最后更新于 2017 年）
* iOS 8.4 及更早版本（最后更新于 2015 年）

Android 设备不受此更改的影响。

密码安全级别设置为“标准”的客户不受此更改的影响。
