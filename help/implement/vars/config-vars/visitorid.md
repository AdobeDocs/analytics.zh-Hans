---
title: visitorID
description: 使用自定义访客ID。
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# visitorID

Adobe使用多种不同的方法识别您网站上的访客。 该变 `visitorID` 量将覆盖所有其他访客识别方法。

> [!IMPORTANT] Adobe建议不要使用此变量。 请改 [用Adobe Experience Cloud Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html) 。

## Adobe Experience Platform Launch中的访客ID

[!UICONTROL 访客ID] 是配置Adobe Analytics扩展时 [!UICONTROL Cookies] accordion下的字段。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到“扩 [!UICONTROL 展] ”选项卡，然后单击Adobe Analytics [!UICONTROL 下的] “配置”按钮。
4. 展开 [!UICONTROL Cookies折叠] ，该面板显示访 [!UICONTROL 客ID字段] 。

将此字段分配给包含您的自定义访客ID的数据元素。 请勿将此字段设置为静态值。

## AppMeasurement中的s.visitorID和启动自定义代码编辑器

变 `s.visitorID` 量是一个字符串，其中包含访客的自定义唯一标识符。 有效值包括最多100字节的字母数字字符。 避免在此变量中使用虚线、空格、下划线或符号。

> [!WARNING] 如果在访问中设 `visitorID` 置变量部分路径，则数据会生成两个单独的唯一访客。

```js
s.visitorID = "abc123";
```
