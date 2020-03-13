---
title: 将数据层对象映射到数据元素
description: 将启动项配置为从数据层读取。
translation-type: tm+mt
source-git-commit: 283fcd5832abe4c09caa332c2ebc3a22029e6707

---


# 将数据层对象映射到数据元素

在您的组织在站点上建立并实施了数据层后，您可以在Launch中将数据层对象映射到数据元素。

## 先决条件

[创建数据层](../prepare/data-layer.md):确保站点上存在数据层。 虽然从技术上讲，您可以映射任何JavaScript对象或直接从页面中刮取CSS元素，但Adobe建议将此做法作为最后手段。 如果站点布局发生更改，则启动项中使用的CSS选择器停止工作，导致数据丢失。

## 使用Adobe Experience Platform Launch创建数据元素

[数据元素](https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/data-elements.html#create-a-data-element) 是Launch中的组件，您可以在工具中使用它。 您可以使用数据元素在Adobe Analytics扩展中分配变量值。

1. 转到 [Adobe Experience Platform Launch](https://launch.adobe.com)，并在出现提示时登录。
1. 单击所需的启动项属性。
1. Click the [!UICONTROL Data Elements] tab, then click [!UICONTROL Add Data Element].

   ![创建数据元素](assets/createelement.png)

1. 为数据元素输入名称。 它可以是一个简单的标签，它对应于您要跟踪的数据层中的JavaScript变量。
1. 在下拉列 [!UICONTROL Extension] 表中，选择 [!UICONTROL Core]。
1. 在下拉列 [!UICONTROL Data Element Type] 表中，选择 [!UICONTROL JavaScript Variable]。 右侧会显示一个文本字段，允许您输入JavaScript变量以映射到此数据元素。
1. 通常在数据层中输入所需的Javascript变量。 例如，如果贵组织的数据层与Adobe的建议做法紧密匹配，则值可能为 `digitalData.page.pageInfo.pageName`。 您可以使用浏览器的控制台验证JavaScript变量语法和值。
1. 单击 [!UICONTROL Save].

## 后续步骤

[将数据元素映射到Analytics变量](elements-to-variable.md):将数据元素分配给Analytics变量，以便在Analysis Workspace中将它们用作维。
