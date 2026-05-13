---
title: dynamicVariablePrefix
description: 允许您自定义标识动态变量的字符串。
feature: Appmeasurement Implementation
exl-id: fe208723-0cf2-4899-be7a-8f23c6501c11
role: Admin, Developer
TQID: https://experienceleague.adobe.com/4NlOgI1maQuMHenSZHUnc7ESvlbst09v4CmOMlBbfEE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 279
ht-degree: 71%

---

# dynamicVariablePrefix

动态变量是一种速记概念，允许您将值从一个变量复制到另一个变量。 这些变量对于较长的变量值很有用，因为它们有助于缩短图像请求的 URL 长度。 有关此概念的更多信息，请参阅[动态变量](../page-vars/dynamic-variables.md)。

默认情况下，动态变量使用前缀 `D=`。 `dynamicVariablePrefix` 变量允许您自定义标识动态变量的字符串。 该变量区分大小写。

## 使用Web SDK的动态变量前缀

Web SDK不使用动态变量格式。 相反，您可以使用数据流映射来使用单个Source字段填充多个目标字段。 有关详细信息，请参阅[使用Web SDK的动态变量](../page-vars/dynamic-variables.md#dynamic-variables-using-the-web-sdk)。

如果您在不符合架构的情况下将数据直接发送到Adobe Analytics，则它会使用以下变量：

* [数据对象](/help/implement/aep-edge/data-var-mapping.md)： `data.__adobe.dynamicVariablePrefix`

## 使用Adobe Analytics扩展的动态变量前缀

“动态变量前缀”是配置 Adobe Analytics 扩展时位于[!UICONTROL 全局变量]折叠面板下的字段。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 单击所需的标记属性。
1. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的&#x200B;**配置**&#x200B;按钮。
1. 展开[!UICONTROL 全局变量]折叠面板，这会显示[!UICONTROL 动态变量前缀]字段。

默认情况下，此字段包含 `D=`。 如果要使用其他动态变量前缀，可以更改该值。 只要值与网站上的字符编码匹配，您就可以使用所需的任何值。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.dynamicVariablePrefix

`s.dynamicVariablePrefix` 变量是可以包含任意字符序列的字符串。 如果未定义此变量，AppMeasurement 默认使用字符串 `D=`。

```js
// An example that changes the dynamic variable prefix
s.dynamicVariablePrefix="..";

// This eVar uses the above customized dynamic variable prefix to set eVar to page URL
s.eVar1="..g";
```
