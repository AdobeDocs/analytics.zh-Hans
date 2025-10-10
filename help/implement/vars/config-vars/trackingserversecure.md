---
title: trackingServerSecure
description: 用于通过HTTPS向Adobe发送数据的域。
feature: Appmeasurement Implementation
exl-id: d5b112f9-f3f6-43ac-8ee5-d9ad8062e380
role: Admin, Developer
source-git-commit: 7918b18e73618368543a996ca121b64b7afb33ab
workflow-type: tm+mt
source-wordcount: '743'
ht-degree: 13%

---

# trackingServerSecure

`trackingServerSecure`变量可确定AppMeasurement用于通过HTTPS向Adobe发送数据的域。 如果未正确定义此变量，则您的实施可能会丢失数据。

在[Adobe Experience Cloud Identity服务](https://experienceleague.adobe.com/en/docs/id-service/using/home)之前，此变量还确定第三方Cookie的设置位置。 Adobe强烈建议尽可能在所有实施中使用ID服务。

## 使用Web SDK扩展的Edge域

Web SDK使用[!UICONTROL Edge域]处理跟踪服务器和安全跟踪服务器。 配置Web SDK扩展时，您可以设置所需的[!UICONTROL Edge域]值。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 选择所需的标记属性。
1. 转到[!UICONTROL 扩展]选项卡，然后选择&#x200B;**[!UICONTROL Adobe Experience Platform Web SDK]**&#x200B;下的[!UICONTROL 配置]按钮。
1. 设置所需的&#x200B;**[!UICONTROL Edge域]**&#x200B;文本字段。

有关详细信息，请参阅Web SDK文档中的[配置Adobe Experience Platform Web SDK扩展](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=zh-Hans)。

>[!TIP]
>
>如果您的组织从AppMeasurement或Analytics扩展实施移至Web SDK，则此字段可以使用`trackingServerSecure`（或`trackingServer`）中包含的相同值。

## Edge域手动实施Web SDK

使用[`edgeDomain`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/edgedomain)配置SDK。 字段是一个字符串，可确定要将数据发送到的域。

```json
alloy("configure", {
  "edgeDomain": "data.example.com"
});
```

## 使用Adobe Analytics扩展的SSL Tracking Server

[!UICONTROL SSL 跟踪服务器]是配置 Adobe Analytics 扩展时位于[!UICONTROL 常规]折叠面板下的字段。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 选择所需的标记属性。
1. 转到[!UICONTROL 扩展]选项卡，然后选择Adobe Analytics下的&#x200B;**[!UICONTROL 配置]**&#x200B;按钮。
1. 展开[!UICONTROL 常规]折叠面板，这会显示[!UICONTROL SSL 跟踪服务器]字段。

如果此字段留空，则默认为[!UICONTROL 跟踪服务器]中的值。 如果[!UICONTROL SSL跟踪服务器]和[!UICONTROL 跟踪服务器]均为空，则默认为`[rsid].data.adobedc.net`。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.trackingServerSecure

`s.trackingServerSecure`变量是一个字符串，其中包含要向Adobe发送数据的域。 它只是域；省略协议、路径、端口和斜杠。 如果此变量为空，它将使用`s.trackingServer`变量中的值。 如果`s.trackingServerSecure`和`s.trackingServer`都为空，则默认为`[rsid].2o7.net`。

```js
// Example value when participating in the Adobe-managed certificate program
s.trackingServerSecure = "data.example.com";

// Example value sending data directly to Adobe
s.trackingServerSecure = "example.data.adobedc.net";
```

## 确定`trackingServerSecure`值的注意事项

您为`trackingServerSecure`（或`edgeDomain`）使用的值取决于几个因素：

* 您参与了[Adobe管理的证书计划](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/adobe-managed-cert)
* 如果已实施并正确设置[Adobe Experience Cloud Identity服务](https://experienceleague.adobe.com/en/docs/id-service/using/home)

**如果您的组织参与了Adobe管理的证书计划**，请将该值设置为设置证书时选择的第一方域。 通常此值是您的组织拥有的子域。 例如：`data.example.com`。贵组织中的CNAME记录将该数据重定向到Adobe。

**如果不参与证书计划**，则将该值设置为`data.adobedc.net`的子域。 Adobe建议使用贵组织的公司ID来保持一致性。 例如：`example.data.adobedc.net`。使用以下步骤可确定您的公司ID：

1. 使用您的Adobe ID凭据登录[experience.adobe.com](https://experience.adobe.com)。
1. 在Experience Cloud界面中的任意位置，按`[Cmd]` + `[I]` (iOS)或`[Ctrl]` + `[I]` (Windows)。
1. 出现&#x200B;**[!UICONTROL 用户数据调试器]**。 选择&#x200B;**[!UICONTROL 分配的组织]**&#x200B;选项卡。
1. 展开所需的IMS组织。
1. 找到&#x200B;**[!UICONTROL 租户]**&#x200B;字段。 建议使用`data.adobedc.net`的子域使用此值。

>[!NOTE]
>
>请勿使用比 `example.data.adobedc.net` 更深的子域。例如，`custom.example.data.adobedc.net` 不是有效的跟踪服务器。

较旧的实施可能具有诸如`sc.omtrdc.net`或`2o7.net`之类的值。 这些服务器主要用于 Adobe Analytics 以前的版本并且仍有效。

Adobe强烈建议在[解决方案设计文档](../../prepare/solution-design.md)中维护此信息，以保持整个组织的一致性。

## 不使用访客ID服务所产生的后果

Adobe强烈建议在所有实施中使用[Adobe Experience Cloud Identity服务](https://experienceleague.adobe.com/en/docs/id-service/using/home)。 ID服务可以通过多种不同的方式进行实施：

* 手动AppMeasurement实施使用`VisitorAPI.js`并调用`getInstance`方法。 有关详细信息，请参阅[实施适用于Analytics的Experience Cloud Identity服务](https://experienceleague.adobe.com/en/docs/id-service/using/implementation/setup-analytics)。
* 使用Adobe Analytics标记扩展的实施使用[Adobe Experience Cloud ID服务标记扩展](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/id-service/overview)。 添加后，无需其他配置。
* 使用任何形式的Web SDK(`alloy.js`或Web SDK标记扩展)的实施已经以本机方式装载了ID服务。 设置`edgeDomain`值后无需进行配置。

**如果您的实施未使用Identity服务**，请考虑对您的实施产生以下影响：

* 如果不使用标识服务，`trackingServerSecure`将确定Cookie位置。 将此变量设置为第三方域会强制AppMeasurement使用回退Cookie，因为大多数现代浏览器会拒绝第三方Cookie。
* 内部链接跟踪和Activity Map可能不太可靠。
