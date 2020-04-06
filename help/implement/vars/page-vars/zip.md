---
title: zip
description: 在报表包设置允许时手动填充“邮政编码”维度。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# zip

The `zip` variable allows you to manually populate the &#39;Zip Code&#39; dimension if the [!UICONTROL Zip Option] in report suite settings allows it. 在 Adobe Analytics 的先前版本中，通常只有在零售网站上输入送货信息时才能手动设置此变。Adobe Analytics 的改进允许您能够使用地理位置数据自动设置此变量。此变量不会在设置的点击之外继续存在。

>[!IMPORTANT] 确保将报 [!UICONTROL Zip Option] 表包中的设置设置为所需的值。 You cannot use this variable if [!UICONTROL geo zip] is always used. 有关详细信息，请参阅管理员用户指南中的[一般帐户设置](/help/admin/admin/general-acct-settings-admin.md)。

## Adobe Experience Platform Launch 中的邮政编码

您可以在配置 Analytics 扩展时（全局变量）或根据规则设置邮政编码。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. 在下 [!UICONTROL Actions]面，单击现有 [!UICONTROL Adobe Analytics - Set Variables] 操作或单击“+”图标。
5. 将下拉 [!UICONTROL Extension] 列表设置为Adobe Analytics，将其设置为 [!UICONTROL Action Type] to [!UICONTROL Set Variables]。
6. 找到该 [!UICONTROL Zip] 部分。

您可以将“邮政编码”设置为任何字符串值，包括数据元素。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.zip

`s.zip` 变量是一个通常包含邮政编码的字符串，但可以包含长度不超过 50 字节的任何所需值。

```js
s.zip = "84043";
```
