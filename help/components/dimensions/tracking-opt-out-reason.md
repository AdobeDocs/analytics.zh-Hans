---
title: 跟踪选择退出的原因
description: 预览在启用“隐私设置”后将排除的数据。
feature: Dimensions
exl-id: f0521f4f-b11e-4ce3-b0fe-60788be6b120
source-git-commit: b7209b914695423099266f5c507eaa34c2b98bc5
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 9%

---

# 跟踪选择退出的原因

*本页介绍的维度允许您查看启用某些报表包设置对数据的潜在影响。 它与 [Adobe Experience Cloud ID选择加入服务](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=zh-Hans).*

“跟踪选择退出原因”维度用作在启用隐私设置时将被排除的数据的预览。 此维度主要用于确定在您启用的情况下，您的实施是否会受到负面影响 [隐私设置](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html) 下。

如果尚未启用隐私设置，则典型实施会在此维度下看到其总报表包流量的1%或更少。 高于所有流量1%的百分比表明存在潜在的实施问题，该问题会阻止AppMeasurement设置第一方Cookie。

## 使用数据填充此维度

此维度可开箱即用于所有尚未启用的实施 [隐私设置](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html). 如果贵组织已启用 **[!UICONTROL 删除已阻止所有Cookie的用户]** 为桌面浏览器和移动设备浏览器进行设置时，此维度不包含数据。

## 维度项目

维度项目包括 `"Cookies disabled by Desktop Browser"` 和 `"Cookies disabled by Mobile Browser"`。

* **桌面浏览器禁用的Cookie**:访客使用桌面浏览器阻止了Cookie，并且 **[!UICONTROL 删除在桌面浏览器中阻止所有Cookie的用户]** 已禁用。
* **移动设备浏览器禁用的Cookie**:访客使用移动设备浏览器阻止了Cookie，并且 **[!UICONTROL 删除在移动设备浏览器中阻止所有Cookie的用户]** 已禁用。
