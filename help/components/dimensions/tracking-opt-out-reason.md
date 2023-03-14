---
title: 跟踪选择退出的原因
description: 预览如果启用了隐私设置，将排除哪些数据。
feature: Dimensions
exl-id: f0521f4f-b11e-4ce3-b0fe-60788be6b120
source-git-commit: b7209b914695423099266f5c507eaa34c2b98bc5
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 9%

---

# 跟踪选择退出的原因

*此页面引用了一个维度，通过该维度，您可以查看启用某些报表包设置可能会产生的数据影响。 它与 [Adobe Experience Cloud ID选择加入服务](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=zh-Hans).*

“跟踪选择退出原因”维度可以预览如果启用隐私设置，则将排除的数据。 此维度主要用于确定如果启用了，您的实施是否会受到负面影响 [隐私设置](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html) 在报表包设置下。

如果尚未启用隐私设置，则典型实施会在此维度下看到其整体报表包流量的1%或更少。 所有流量中高于1%的百分比表明可能存在导致AppMeasurement无法设置第一方Cookie的实施问题。

## 使用数据填充此维度

此维度可开箱即用于尚未启用的所有实施 [隐私设置](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html). 如果您的组织已启用 **[!UICONTROL 删除已阻止所有Cookie的用户]** 适用于桌面浏览器和移动设备浏览器的设置，此维度不包含数据。

## 维度项目

维度项目包括 `"Cookies disabled by Desktop Browser"` 和 `"Cookies disabled by Mobile Browser"`。

* **桌面浏览器禁用的Cookie**：访客使用桌面浏览器阻止了Cookie，并且 **[!UICONTROL 删除在桌面浏览器中阻止所有Cookie的用户]** 已禁用。
* **移动设备浏览器禁用的Cookie**：访客使用移动设备浏览器阻止了Cookie，并且 **[!UICONTROL 删除在移动浏览器中阻止所有Cookie的用户]** 已禁用。
