---
title: zip
description: 在报表包设置允许时手动填充“邮政编码”维度。
feature: Appmeasurement Implementation
exl-id: 1acf4bf7-3788-46bd-bcdb-9885c7b93b59
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/dv564yEz9tChaxot0w65ZGIc1T0Jqdnp1Mua0QUbn5Y'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 275
ht-degree: 81%

---

# zip

通过 `zip` 变量，您可以在报表包设置中的[!UICONTROL 邮政编码选项]允许时手动填充“邮政编码”维度。 在 Adobe Analytics 的先前版本中，通常只有在零售网站上输入送货信息时才能手动设置此变。 Adobe Analytics 的改进允许您能够使用地理位置数据自动设置此变量。 此变量不会在设置的点击之外继续存在。

>[!IMPORTANT]
>
>确保将报表包设置中的[!UICONTROL 邮政编码选项]设置为所需的值。 如果始终使用[!UICONTROL 地域zip]，则不能使用此变量。 有关详细信息，请参阅《管理员用户指南》中的[一般帐户设置](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)。

## 使用Web SDK的邮政编码

邮政编码映射到以下变量：

* [XDM对象](/help/implement/aep-edge/xdm-var-mapping.md)： `xdm.placeContext.geo.postalCode`
* [数据对象](/help/implement/aep-edge/data-var-mapping.md)： `data.__adobe.analytics.zip`

## 使用Adobe Analytics扩展的邮政编码

您可以在配置Analytics扩展时（全局变量）或根据规则设置邮政编码。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
2. 单击所需的标记属性。
3. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
4. 在[!UICONTROL 操作]下，单击现有的 [!UICONTROL Adobe Analytics - 设置变量]操作或单击“+”图标。
5. 将[!UICONTROL 扩展]下拉列表设置为 Adobe Analytics，将[!UICONTROL 操作类型]设置为[!UICONTROL 设置变量]。
6. 找到[!UICONTROL 邮政编码]部分。

您可以将“邮政编码”设置为任何字符串值，包括数据元素。

## AppMeasurement 和 Analytics 扩展代码编辑器中的 s.zip

`s.zip` 变量是一个字符串，通常包含邮政编码，但也可以包含长度不超过 50 字节的任何所需值。

```js
s.zip = "84043";
```
