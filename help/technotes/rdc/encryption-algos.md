---
title: 支持的 HTTPS 加密算法
description: TLS密码安全设置和证书类型。
feature: Regional Data Collection
exl-id: f1cbb0cb-fd65-4f22-8594-0d97b6906698
source-git-commit: 299de03c05f6a8af4f6c5d98c76bae54eec4c088
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 30%

---

# 支持的 HTTPS 加密算法

## 密码安全级别

Adobe 提供两种密码安全级别，以满足客户对第一方数据收集安全性的不同需求。这些级别决定了与我们服务器的 HTTPS 连接支持哪些加密算法。Adobe会根据当前的安全实践定期审查和更新一组受支持的算法。 如果要更改密码安全设置，请联系客户关怀团队。

“Standard”需要TLS 1.2或更高版本以及至少128位加密。 它旨在提供最广泛的设备兼容性，同时保持安全加密。

“高”密码安全级别需要TLS 1.2或更高版本，并且不再支持较弱的密码。 它专为那些希望获得最强加密并且不关心对旧设备支持的客户而设计。

已知以下客户端无法与密码安全设置为“High”（高）的密码安全连接。

* Windows 8.1 及更早版本（最后更新于 2018 年）
* Windows Phone 8.1 及更早版本（最后更新于 2016 年）
* OS X 10.10 及更早版本（最后更新于 2017 年）
* iOS 8.4 及更早版本（最后更新于 2015 年）

## 支持的HTTPS证书类型

Adobe支持RSA和ECC证书类型，以满足不同客户的需求。 RSA证书在客户端得到更广泛的支持，但ECC证书在服务器端和客户端上的处理量较少。 对于Adobe管理的证书，提供了RSA和ECC。 对于客户管理的证书，建议同时使用RSA和ECC。 现代客户端支持RSA和ECC。 已知以下客户端仅支持RSA证书：

* Windows Vista及更早版本（上次更新于2012年）
* Windows Phone 8.0 及更早版本（最后更新于 2014 年）
* OS X 10.8 及更早版本（最后更新于 2013 年）
* iOS 5.1 及更早版本（最后更新于 2012 年）
* Android 4.3及更早版本（上次更新日期：2013年）
