---
title: visitorID
description: 使用自定义访客 ID。
feature: Variables
exl-id: cb336042-01a1-4a66-a947-a221a7919c1b
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 72%

---

# visitorID

Adobe 使用多种不同的方法识别您网站上的访客。`visitorID` 变量将覆盖所有其他访客识别方法。

>[!IMPORTANT]
>
>Adobe 建议不要使用此变量。请改用 [Adobe Experience Cloud 身份服务](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hans)。

## 使用Adobe Analytics扩展的访客ID

[!UICONTROL 访客 ID] 是配置 Adobe Analytics 扩展时位于 [!UICONTROL Cookie] 折叠面板下的字段。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
2. 单击所需的标记属性。
3. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的&#x200B;]**配置**[!UICONTROL &#x200B;按钮。
4. 展开 [!UICONTROL Cookie] 折叠面板，这会显示[!UICONTROL 访客 ID]字段。

将此字段分配给包含您的自定义访客 ID 的数据元素。请勿将此字段设置为静态值。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.visitorID

`s.visitorID` 变量是一个字符串，其中包含访客的自定义唯一标识符。有效值包括最多 100 字节的字母数字字符。避免在此变量中使用虚线、空格、下划线或符号。

>[!WARNING]
>
>如果在访问过程中设置 `visitorID` 变量，则数据将生成两个单独的独特访客。

```js
s.visitorID = "abc123";
```

>[!CAUTION]
>
>自定义访客 ID 的无效实施，可能会导致数据不正确和报告性能不佳。如果此变量包含默认值（例如 `"0"` 或 `"NULL"`），Adobe 会将这些点击视为相同的访客。这种情况导致数据不正确，访客计数低且访客级别的区段无法按预期工作。未正确实施的自定义访客 ID 也会给处理服务器带来沉重的负载，增加[延迟](/help/technotes/latency.md)并降低报告性能。

## 使用Web SDK和Experience Edge的访客ID

Experience Edge允许您使用XDM的 [标识映射](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/overview.html?lang=en#using-identitymap). “身份映射”中的每个身份具有不同的命名空间。 您可以指定哪个命名空间应该用于访客ID，作为的一部分 [数据流配置](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=en#analytics). 配置完毕后，在发送一个事件（其中包含为此命名空间指定的值）时，系统会自动将其用作Analytics中的访客ID。
