---
title: 将数据层对象映射到数据元素
description: 将标记配置为从数据层读取。
feature: Tags
exl-id: b7594084-cb5f-408e-8a76-0a0815cc7553
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/MmwNCdmt9TwNojJEyzbfTukeh4sKITk06gY-EBzjZPw'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: df312454-73c4-43f6-a90e-18f5043f074c
    internal-label: Tags
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 7151dca7425bfb99271db71a3132485f85941a5e
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 46%
---
# 将数据层对象映射到数据元素

您的组织在网站上建立并实施数据层后，您可以将数据层对象映射到标记内的数据元素。

## 先决条件

[创建数据层](../prepare/data-layer.md)：确保网站上存在数据层。 虽然从技术上讲，您可以直接从页面映射任何 JavaScript 对象或抓取 CSS 元素，但是 Adobe 建议只有在万不得已时才使用此做法。 如果网站版面发生更改，则标记中使用的 CSS 选择器会停止工作，进而导致数据丢失。

## 使用标记创建数据元素

[数据元素](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html?lang=zh-Hans)是 Adobe Experience Platform 数据收集中的组件，您可以在整个工具中使用这些组件。 您可以使用数据元素在 Adobe Analytics 扩展中分配变量值。

以下步骤使用[Adobe Client Data Layer扩展](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/extensions/client/client-data-layer/overview)，该扩展必须安装在标记属性中。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 选择所需的标记属性。
1. 选择&#x200B;**[!UICONTROL 数据元素]**&#x200B;选项卡，然后选择&#x200B;**[!UICONTROL 添加数据元素]**。

   ![创建数据元素](assets/createelement.png)

1. 输入数据元素的名称，如`Page name`。
1. 在&#x200B;**[!UICONTROL 扩展]**&#x200B;下拉列表下，选择&#x200B;**[!UICONTROL Adobe Client Data Layer]**。
1. 在&#x200B;**[!UICONTROL 数据元素类型]**&#x200B;下拉列表下，选择&#x200B;**[!UICONTROL 数据层计算状态]**。
1. 在&#x200B;**[!UICONTROL 返回值]**&#x200B;下，选择&#x200B;**[!UICONTROL 特定路径]**，然后输入数据层中值的路径，如`page.name`。 要验证路径，请在浏览器的控制台中运行`adobeDataLayer.getState("page.name")`。
1. 选择&#x200B;**[!UICONTROL 保存]**。

在扩展的&#x200B;**[!UICONTROL 数据层推送]**&#x200B;事件触发的规则中使用这些数据元素，以便数据层已加载并包含来自推送的数据。 请参阅[数据元素类型](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/extensions/client/client-data-layer/data-element-types#computed-state)。

### 基于对象的数据层 {#object-based}

如果数据层是JavaScript对象（如CEDDL `digitalData`对象），请改用&#x200B;**[!UICONTROL Core]**&#x200B;扩展中的&#x200B;**[!UICONTROL JavaScript Variable]**&#x200B;数据元素类型。 输入值的路径，如`digitalData.page.pageInfo.pageName`。 此数据元素类型无法读取Adobe Client Data Layer，后者将其数据存储在计算状态而不是对象属性中。

## 后续步骤

[将数据元素映射到 Analytics 变量](elements-to-variable.md)：将数据元素分配给 Analytics 变量，以便在 Analysis Workspace 中可以将这些变量用作维度。
