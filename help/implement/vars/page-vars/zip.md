---
title: zip
description: 如果报表包设置允许，手动填充“邮政编码”维。
translation-type: tm+mt
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# zip

如果 `zip` 报表包设置中的“压缩选项”允许，该变量允许您手动填充 [!UICONTROL “邮政编码”维] 。 在Adobe Analytics的先前版本中，此变量只能手动设置，通常在零售站点上输入送货信息时才能设置。 Adobe Analytics的改进使此变量能够使用地理位置数据自动设置。 此变量不会在设置的点击之外继续存在。

> [!IMPORTANT] 确保将报 [!UICONTROL 表包设置中的] “Zip选项”设置为所需的值。 如果始终使用geo zip  ，则不能使用此变量。 See [General Account Settings](/help/admin/admin/general-acct-settings-admin.md) in the Admin user guide for more information.

## Adobe Experience Platform Launch中的Zip

您可以在配置Analytics扩展时（全局变量）或根据规则设置邮政编码。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到“规 [!UICONTROL 则] ”选项卡，然后单击所需的规则（或创建规则）。
4. 在“ [!UICONTROL 操作]”下，单击现有  Adobe Analytics —— 设置变量操作或单击“+”图标。
5. 将“扩 [!UICONTROL 展] ”下拉列表设置为Adobe Analytics，将“操作类 [!UICONTROL 型] ”设置为“ [!UICONTROL 设置变量”]。
6. 找到 [!UICONTROL Zip] 部分。

您可以将邮政编码设置为任何字符串值，包括数据元素。

## AppMeasurement中的s.zip和启动自定义代码编辑器

变 `s.zip` 量是一个字符串，通常包含邮政编码，但可以包含长度不超过50字节的任何所需值。

```js
s.zip = "84043";
```
