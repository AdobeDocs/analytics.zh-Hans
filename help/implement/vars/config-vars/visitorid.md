---
title: visitorID
description: 使用自定义访客 ID。
feature: Appmeasurement Implementation
exl-id: cb336042-01a1-4a66-a947-a221a7919c1b
role: Admin, Developer
source-git-commit: de98bf68c57f5453b6662f6e6e57312d8fd3e642
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 19%

---

# visitorID

Adobe使用多种方法来[识别您网站上的访客](../../id/overview.md)。 **变量`visitorID`将覆盖所有其他访客识别方法。**

>[!IMPORTANT]
>
>Adobe 建议不要使用此变量。请改用 [Adobe Experience Cloud 身份标识服务](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hans)。

## Analytics如何使用`visitorID`

此变量是手动访客ID覆盖，可替换所有其他形式的访客识别。 要计为单个访客，人员的每次点击都必须使用相同的`visitorID`值。

* 省略`visitorID`的点击将回退到其他访客识别方法，并被视为单独的访客。
* 使用多个`visitorID`值的点击将被视为单独的访客。
* Adobe不会将使用不同访客ID的点击拼合在一起。

有关识别优先级的详细信息以及混合标识符会夸大访客计数的原因，请参阅Adobe Analytics中的[访客识别](../../id/overview.md)。

>[!WARNING]
>
>只有在您可以保证在每次点击时为该人员设置`visitorID`并且值永不更改的情况下，才设置。 仅在某些点击上设置它，在访问过程中引入它（例如身份验证），或在点击之间更改它会将单个访客的活动拆分为多个访客。

>[!CAUTION]
>
>自定义访客ID值无效可能会导致数据不正确和报告性能不佳。 如果此变量包含默认值或占位符值（如`"0"`或`"NULL"`），Adobe会将这些点击视为相同的访客。 这种情况会导致数据不正确，人为造成访客计数偏低，并且访客级别的区段无法按预期工作。 未正确实施的自定义访客ID也会给处理服务器带来沉重的负载，增加[延迟](/help/technotes/latency.md)并降低报表性能。

## 使用Adobe Analytics扩展的访客ID

[!UICONTROL 访客 ID] 是配置 Adobe Analytics 扩展时位于 [!UICONTROL Cookie] 折叠面板下的字段。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
2. 选择所需的标记属性。
3. 转到[!UICONTROL 扩展]选项卡，然后选择Adobe Analytics下的&#x200B;**[!UICONTROL 配置]**&#x200B;按钮。
4. 展开 [!UICONTROL Cookie] 折叠面板，这会显示[!UICONTROL 访客 ID]字段。

将此字段分配给包含您的自定义访客 ID 的数据元素。**请勿将此字段设置为所有访客的单个静态值。**&#x200B;使用按访客解析并在所有点击中保持不变的数据元素。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.visitorID

`s.visitorID` 变量是一个字符串，其中包含访客的自定义唯一标识符。有效值包括最多100字节的字母数字字符。 避免在此变量中使用虚线、空格、下划线或符号。

```js
s.visitorID = "abc123";
```

## 使用Web SDK的访客ID

Adobe Experience Platform Edge Network允许您使用XDM的[身份映射](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/overview.html#using-identitymap)提供多个标识符。 “身份映射”中的每个身份具有不同的命名空间。 您可以指定哪个命名空间应该用于访客ID，作为[数据流配置](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html#analytics)的一部分。 一旦配置了此字段，当您发送具有为此命名空间指定的值的事件时，它会自动用作Analytics中的访客ID。
