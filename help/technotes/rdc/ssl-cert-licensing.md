---
title: SSL 证书许可
description: 受客户管理的证书的证书过程
feature: Regional Data Collection
exl-id: 7d1373c8-6f7b-4ce7-a555-d3d506e08d17
role: Admin
source-git-commit: d3d5b01fe17f88d07a748fac814d2161682837c2
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 100%

---

# SSL/TLS 证书许可

Adobe 建议您通过 [Adobe Managed Certificate Program](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=zh-Hans) 管理您的证书，这样不会产生额外费用。Adobe Managed Certificate Prorgram 是完全自动的，可确保及时继订证书，从而不会由于证书过期而受到影响。

如果您选择不使用 [Adobe Managed Certificate Prorgram](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=zh-Hans)，则您负责提供用于第一方 Cookie 的 SSL/TLS 证书。

如果您自行提供证书，则您负责购买和维护该证书。您的 SSL/TLS 证书必须包含无限制的服务器许可证。

为确保证书安全性，请从 Adobe 获取证书签名请求 [CSR]，并安排所需的证书颁发机构对证书进行签名。向 Adobe 提供用于实施的已签名证书。通过执行此过程，可维护证书密钥的安全性。Adobe 客户关怀将在此过程中提供协助。

作为证书维护的一部分，应至少在证书到期前一个月，安排您所需的证书颁发机构获取续订的证书并将其提供给 Adobe。此证书应使用以前使用的相同 CSR。如果您需要 CSR 的副本或希望使用新密钥生成新 CSR，请联系 Adobe。

可通过 customercare@adobe.com 或 1-800-497-0335 联系客户关怀团队。

常用的证书颁发机构包括 DigiCert、Comodo 和 GeoTrust。
