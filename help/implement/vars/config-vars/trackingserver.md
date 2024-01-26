---
title: trackingServer
description: 确定发送图像请求的位置。
feature: Variables
exl-id: bcc23286-4dd5-45ac-ac6f-7b60e95cb798
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 72%

---

# trackingServer

Adobe 通过接收访客生成的图像请求来收集您网站上的数据。`trackingServer` 变量可确定发送图像请求的位置。如果未正确定义此变量，则您的实施可能会丢失数据。

>[!WARNING]
>
>更改此值会使 AppMeasurement 在其他位置查找 Cookie。当在新位置设置访客 Cookie 时，报表中的独特访客计数可能会暂时激增。

## 使用Web SDK扩展的Edge域

Web SDK使用 [!UICONTROL 边缘域] 处理跟踪服务器和安全跟踪服务器。 您可以设置所需的 [!UICONTROL 边缘域] 值。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 单击所需的标记属性。
1. 转到 [!UICONTROL 扩展] 选项卡，然后单击 **[!UICONTROL 配置]** 按钮位于 [!UICONTROL Adobe Experience Platform Web SDK].
1. 设置所需的 **[!UICONTROL 边缘域]** 文本字段。

请参阅 [配置Adobe Experience Platform Web SDK扩展](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=zh-Hans) 有关更多信息，请参阅Web SDK文档。

>[!TIP]
>
>如果您的组织从AppMeasurement或Analytics扩展实施移至Web SDK，则此字段可以使用中包含的相同值 `trackingServerSecure` (或 `trackingServer`)。

## 边缘域手动实施Web SDK

使用配置SDK [`edgeDomain`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=zh-Hans). 字段是一个字符串，可确定要将数据发送到的域。

```json
alloy("configure", {
  "edgeDomain": "data.example.com"
});
```

## 使用Adobe Analytics扩展的Tracking Server

“跟踪服务器”是配置 Adobe Analytics 扩展时位于[!UICONTROL 常规]折叠面板下的字段。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
2. 单击所需的标记属性。
3. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的&#x200B;]**配置**[!UICONTROL &#x200B;按钮。
4. 展开[!UICONTROL 常规]折叠面板，这会显示[!UICONTROL 跟踪服务器]字段。

如果此字段留空，则默认为 `[rsid].data.adobedc.net`。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.trackingServer

`s.trackingServer` 变量是一个字符串，其中包含要发送数据的位置。

## 确定值 `trackingServer`

此变量的值取决于您是使用第一方 Cookie 还是第三方 Cookie。Adobe 强烈建议在您的实施中使用第一方 Cookie。

### 第一方 Cookie

如果您使用第一方 Cookie 实施，则表示贵组织中的某人可能已经完成了第一方 Cookie 流程。有关第一方 Cookie 流程的更多信息，请参阅《核心服务用户指南》中的 [Experience Cloud 中的第一方 Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=zh-Hans)。

最初配置第一方 Cookie 实施的人员还会定义所使用的域和子域。例如：

```js
s.trackingServer = "data.example.com";
```

### 第三方 Cookie

>[!TIP]
>
>现代浏览器中增加的隐私权惯例使第三方 Cookie 变得不那么可靠。Adobe 建议遵循第一方 Cookie 工作流程。

如果您使用第三方 Cookie 实施，则 `trackingServer` 的值是 `data.adobedc.net` 的子域。例如：

```js
s.trackingServer = "example.data.adobedc.net";
```

选择贵组织独有而使用 Adobe Analytics 的其他组织不太可能选择的子域。建议使用分配给您组织的访客命名空间。确保贵组织中的所有实施都使用相同的跟踪服务器。在[解决方案设计文档](../../prepare/solution-design.md)中维护此信息可能会有所帮助。

您的组织可能已经在 `sc.omtrdc.net` 或 `2o7.net` 域中使用第三方跟踪服务器。这些服务器主要用于 Adobe Analytics 以前的版本并且仍有效。

>[!NOTE]
>
>请勿使用比 `example.data.adobedc.net` 更深的子域。例如，`custom.example.data.adobedc.net` 不是有效的跟踪服务器。
