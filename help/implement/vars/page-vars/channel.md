---
title: channel
description: 填充“网站区域”维。
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# channel

该 `channel` 变量通常存储给定页面所在的站点的部分。 确定最受欢迎的站点组很有帮助。 此变量填充“站点区域”维。

## Adobe Experience Platform Launch中的渠道

您可以在配置Analytics扩展时（全局变量）或根据规则设置渠道。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到“规 [!UICONTROL 则] ”选项卡，然后单击所需的规则（或创建规则）。
4. 在“ [!UICONTROL 操作]”下，单击现有  Adobe Analytics —— 设置变量操作或单击“+”图标。
5. 将“扩 [!UICONTROL 展] ”下拉列表设置为Adobe Analytics，将“操作类 [!UICONTROL 型] ”设置为“ [!UICONTROL 设置变量”]。
6. 找到“渠 [!UICONTROL 道] ”部分。

可以将channel设置为任何字符串值或数据元素。

## AppMeasurement中的s.channel和启动自定义代码编辑器

变 `s.channel` 量是一个字符串，通常包含页面的站点部分。 最大值为100字节；长值被截断。

```js
s.channel = "Example site section";
```
