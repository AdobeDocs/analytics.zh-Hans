---
title: dynamicVariablePrefix
description: 允许您自定义标识动态变量的字符串。
translation-type: tm+mt
source-git-commit: 03a4c0d5e080219a7fd96dff33ce122669351ac3

---


# dynamicVariablePrefix

动态变量是一个简化的概念，允许您将值从一个变量复制到另一个变量。 它们对于较长的变量值很有价值，因为它们有助于缩短图像请求的URL长度。 有关此 [概念的更多信息](../page-vars/dynamic-variables.md) ，请参阅动态变量。

默认情况下，动态变量使用前缀 `D=`。 该变 `dynamicVariablePrefix` 量允许您自定义标识动态变量的字符串。 区分大小写。

## Adobe Experience Platform Launch中的动态变量前缀

动态变量前缀是配置Adobe Analytics扩展时“ [!UICONTROL 全局变量] ”折叠面板下的字段。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到“扩 [!UICONTROL 展] ”选项卡，然后单击Adobe Analytics [!UICONTROL 下的] “配置”按钮。
4. 展开“全 [!UICONTROL 局变量] ”折叠面板，该面板显示“动态 [!UICONTROL 变量前缀”字段] 。

默认情况下，此字 `D=` 段包含内容。 如果要使用其他动态变量前缀，可以更改该值。 只要值与站点上的字符编码匹配，您就可以使用所需的任何值。

## AppMeasurement和Launch自定义代码编辑器中的s.dynamicVariablePrefix

该 `s.dynamicVariablePrefix` 变量是可以包含任意字符序列的字符串。 如果未定义此变量，AppMeasurement默认使用字 `D=` 符串。

```js
// An example that changes the dynamic variable prefix
s.dynamicVariablePrefix="..";

// This eVar uses the above customized dynamic variable prefix to set eVar to page URL
s.eVar1="..g";
```
