---
title: 跟踪选择禁用的原因
description: 预览如果启用了“隐私设置”，将排除哪些数据。
feature: Dimensions
exl-id: f0521f4f-b11e-4ce3-b0fe-60788be6b120
TQID: https://experienceleague.adobe.com/mFYYrj4iBWBi87sErHnWTYXce3lUhV0pwUt63x3vfnY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 281
ht-degree: 11%

---

# 跟踪选择禁用的原因

*此页面引用了[维度](overview.md)，通过该维度，您可以查看启用某些报表包设置可能会产生的数据影响。 它与[Adobe Experience Cloud ID选择加入服务](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=zh-Hans)无关。*

“跟踪选择退出原因”维度充当在您启用隐私设置时将排除的数据的预览。 此维度主要用于确定如果您在报表包设置下启用[隐私设置](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html)，您的实施是否会受到负面影响。

如果尚未启用隐私设置，则典型实施会在此维度下看到其总报表包流量的1%或更少。 所有流量中高于1%的百分比表明可能存在导致AppMeasurement无法设置第一方Cookie的实施问题。

## 使用数据填充此维度

此维度可开箱即用于所有尚未启用[隐私设置](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html)的实施。 如果贵组织已经为桌面浏览器和移动设备浏览器启用了&#x200B;**[!UICONTROL 删除已阻止所有Cookie]**&#x200B;设置的用户，则此维度不包含数据。

## 维度项目

维度项目包括 `"Cookies disabled by Desktop Browser"` 和 `"Cookies disabled by Mobile Browser"`。

* **桌面浏览器禁用的Cookie**：访客使用桌面浏览器阻止了Cookie，并且&#x200B;**[!UICONTROL 删除已禁用桌面浏览器上所有Cookie的用户]**。
* **移动设备浏览器禁用的Cookie**：访客使用移动设备浏览器阻止了Cookie，并且&#x200B;**[!UICONTROL 删除已禁用移动设备浏览器上所有Cookie的用户]**。
