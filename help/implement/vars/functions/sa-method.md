---
title: sa
description: 在您的实施中随时更改报表包。
feature: Appmeasurement Implementation
exl-id: 524857a7-c820-4985-86c7-fcf21a0809bd
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 42%

---

# sa

`sa()` 方法可让您随时在页面上动态更改报表包。如果要在不重新加载页面的情况下将数据发送到不同的报表包，则可以使用此方法。

## 使用Web SDK处理报表包

Web SDK通过向特定数据流发送数据来运行，该数据流将数据转发到所需的Analytics报表包。 单个数据流可以将数据转发到多个报表包。 此部分适用于Web SDK扩展和手动实施Web SDK。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 单击左侧的&#x200B;**[!UICONTROL 数据流]**。
1. 单击所需的数据流，或单击&#x200B;**[!UICONTROL 新建数据流]**。
1. 单击&#x200B;**[!UICONTROL 添加服务]**，然后选择&#x200B;**[!UICONTROL Adobe Analytics]**。
1. 输入所需的报表包ID。 如果要将相同的数据发送到多个报表包，请单击&#x200B;**[!UICONTROL 添加报表包]**。
1. 输入所有所需的报表包后，单击&#x200B;**[!UICONTROL 保存]**。

## 使用Web SDK扩展设置所需的数据流

Web SDK扩展为每个环境提供了一个数据流下拉列表。 或者，您可以手动输入数据流ID。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 单击所需的标记属性。
1. 转到[!UICONTROL 扩展]选项卡，然后单击&#x200B;**[!UICONTROL Adobe Experience Platform Web SDK]**&#x200B;下的[!UICONTROL 配置]按钮。
1. 在[!UICONTROL 数据流]下，从每个环境的下拉列表中选择所需的数据流。
1. 单击&#x200B;**[!UICONTROL 保存]**。

## 手动设置所需的数据流以实施Web SDK

将`datastreamId`配置变量设置为数据流ID。 在Adobe Experience Platform数据收集中查看数据流时，可在右侧找到数据流ID。

```js
alloy("configure", {
  datastreamId: "example-a01f-4458-8cec-ef61de241c93",
  orgId: "ADB3LETTERSANDNUMBERS@AdobeOrg"
});
```

有关详细信息，请参阅Web SDK文档中的[配置Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=zh-Hans)。

## 使用Adobe Analytics扩展更改报表包

界面中没有提供任何灵活的方法来更改报表包。配置 Adobe Analytics 扩展时，可以在[!UICONTROL 库管理]折叠面板下设置报表包。但是，您不能使用规则更改或更新报表包。如果要在设置报表包值后更新这些值，请按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.sa()

调用 `s.sa()` 方法以更改目标报表包。其唯一参数是包含报表包 ID 或以逗号分隔的多个报表包 ID 的字符串。报表包 ID 参数为必需参数。请勿在字符串参数中使用空格。

```js
s.sa("examplersid");
```

例如，如果用户在您的网站上执行特定操作，则可以更改报表包。

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// If the visitor plays a video, you can add a video report suite
s.sa("examplersid,videorsid");

// Then send an image request
s.t();
```
