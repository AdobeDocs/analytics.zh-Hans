---
title: 将数据层对象映射到数据元素
description: 将标记配置为从数据层读取。
feature: Tags
exl-id: b7594084-cb5f-408e-8a76-0a0815cc7553
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 94%

---

# 将数据层对象映射到数据元素

您的组织在网站上建立并实施数据层后，您可以将数据层对象映射到标记内的数据元素。

## 先决条件

[创建数据层](../prepare/data-layer.md)：确保网站上存在数据层。虽然从技术上讲，您可以直接从页面映射任何 JavaScript 对象或抓取 CSS 元素，但是 Adobe 建议只有在万不得已时才使用此做法。如果网站版面发生更改，则标记中使用的 CSS 选择器会停止工作，进而导致数据丢失。

## 使用标记创建数据元素

[数据元素](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html?lang=zh-Hans)是 Adobe Experience Platform 数据收集中的组件，您可以在整个工具中使用这些组件。您可以使用数据元素在 Adobe Analytics 扩展中分配变量值。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 单击所需的标记属性。
1. 单击&#x200B;**[!UICONTROL 数据元素]**&#x200B;选项卡，然后单击&#x200B;**[!UICONTROL 添加新数据元素]**。

   ![创建数据元素](assets/createelement.png)

1. 输入数据元素的名称。它可以是一个简单标签，对应于要跟踪的数据层中的 JavaScript 变量。
1. 在 **[!UICONTROL 扩展名]** 下拉列表，选择 **[!UICONTROL 核心]**.
1. 在 **[!UICONTROL 数据元素类型]** 下拉列表，选择 **[!UICONTROL JavaScript变量]**. 右侧会显示一个文本字段，允许您输入要映射到此数据元素的 JavaScript 变量。
1. 通常情况下，在数据层中输入所需的 Javascript 变量。例如，如果贵组织的数据层比较符合 Adobe 的建议做法，则该值可能为 `digitalData.page.pageInfo.pageName`。您可以使用浏览器的控制台来验证 JavaScript 变量语法和值。
1. 单击&#x200B;**[!UICONTROL 保存]**。

## 后续步骤

[将数据元素映射到 Analytics 变量](elements-to-variable.md)：将数据元素分配给 Analytics 变量，以便在 Analysis Workspace 中可以将这些变量用作维度。
