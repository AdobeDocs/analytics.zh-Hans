---
title: visitorID
description: 使用自定义访客 ID。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# visitorID

Adobe 使用多种不同的方法识别您网站上的访客。`visitorID` 变量将覆盖所有其他访客识别方法。

>[!IMPORTANT] Adobe 建议不要使用此变量。请改用 [Adobe Experience Cloud 身份服务](https://docs.adobe.com/content/help/zh-Hans/id-service/using/home.html)。

## Adobe Experience Platform Launch 中的“访客 ID”

[!UICONTROL Visitor ID] 是配置Adobe Analytics扩展 [!UICONTROL Cookies] 时accordion下的字段。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. 展开可 [!UICONTROL Cookies] 折叠面板，以显示 [!UICONTROL Visitor ID] 字段。

将此字段分配给包含您的自定义访客 ID 的数据元素。请勿将此字段设置为静态值。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.visitorID

`s.visitorID` 变量是一个字符串，其中包含访客的自定义唯一标识符。有效值包括最多 100 字节的字母数字字符。避免在此变量中使用虚线、空格、下划线或符号。

>[!WARNING] 如果在访问过程中设置 `visitorID` 变量，则数据将生成两个单独的独特访客。

```js
s.visitorID = "abc123";
```
