---
title: zip
description: 在报表包设置允许时手动填充“邮政编码”维度。
feature: Variables
exl-id: 1acf4bf7-3788-46bd-bcdb-9885c7b93b59
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 100%

---

# zip

通过 `zip` 变量，您可以在报表包设置中的[!UICONTROL 邮政编码选项]允许时手动填充“邮政编码”维度。在 Adobe Analytics 的先前版本中，通常只有在零售网站上输入送货信息时才能手动设置此变。Adobe Analytics 的改进允许您能够使用地理位置数据自动设置此变量。此变量不会在设置的点击之外继续存在。

>[!IMPORTANT]
>
>确保将报表包设置中的[!UICONTROL 邮政编码选项]设置为所需的值。如果始终使用[!UICONTROL 地区邮政编码]，则不能使用此变量。有关详细信息，请参阅《管理员用户指南》中的[一般帐户设置](/help/admin/admin/general-acct-settings-admin.md)。

## 使用 Adobe Experience Platform 中的标记的“邮政编码”

您可以在配置 Analytics 扩展时（全局变量）或根据规则设置邮政编码。

1. 使用您的 Adobe ID 凭据登录[数据收集 UI](https://experience.adobe.com/data-collection)。
2. 单击所需的属性。
3. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
4. 在[!UICONTROL 操作]下，单击现有的 [!UICONTROL Adobe Analytics - 设置变量]操作或单击“+”图标。
5. 将[!UICONTROL 扩展]下拉列表设置为 Adobe Analytics，将[!UICONTROL 操作类型]设置为[!UICONTROL 设置变量]。
6. 找到[!UICONTROL 邮政编码]部分。

您可以将“邮政编码”设置为任何字符串值，包括数据元素。

## AppMeasurement 和自定义代码编辑器中的 s.zip

`s.zip` 变量是一个通常包含邮政编码的字符串，但可以包含长度不超过 50 字节的任何所需值。

```js
s.zip = "84043";
```
