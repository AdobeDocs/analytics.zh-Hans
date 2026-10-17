---
title: trackingServerSecure
description: 用于通过HTTPS向Adobe发送数据的域。
feature: Appmeasurement Implementation
exl-id: d5b112f9-f3f6-43ac-8ee5-d9ad8062e380
role: Admin, Developer
TQID: https://experienceleague.adobe.com/8-M-5apvXuUfQyxdd4Es8Lr5LkgXPK2UNHrhpTzT8xE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
  - id: df312454-73c4-43f6-a90e-18f5043f074c
    internal-label: Tags
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 832a3752ab758d573e5b15b2dc38dad120fe8300
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 11%
---
# trackingServerSecure

`trackingServerSecure`变量可确定AppMeasurement用于通过HTTPS向Adobe发送数据的域。 如果未正确定义此变量，则您的实施可能会丢失数据。

>[!NOTE]
>
>[`trackingServer`](configuration-variables.md#retired-configuration-variables)是此变量的已弃用变量。 它指定通过HTTP发送的数据的域；如果普遍使用HTTPS，请改用`trackingServerSecure`。 如果`s.trackingServerSecure`为空，则AppMeasurement回退到`s.trackingServer`值。

## 使用Web SDK扩展的Edge域

Web SDK使用[!UICONTROL Edge域]处理跟踪服务器和安全跟踪服务器。 配置Web SDK扩展时，您可以设置所需的[!UICONTROL Edge域]值。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 选择所需的标记属性。
1. 转到[!UICONTROL 扩展]选项卡，然后选择[!UICONTROL Adobe Experience Platform Web SDK]下的&#x200B;**[!UICONTROL 配置]**&#x200B;按钮。
1. 设置所需的&#x200B;**[!UICONTROL Edge域]**&#x200B;文本字段。

有关详细信息，请参阅Web SDK文档中的[配置Adobe Experience Platform Web SDK扩展](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=zh-Hans)。

>[!TIP]
>
>如果您的组织从AppMeasurement或Analytics扩展实施移至Web SDK，则此字段可以使用`trackingServerSecure`（或`trackingServer`）中包含的相同值。

## Edge域手动实施Web SDK

使用[`edgeDomain`](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/web-sdk/commands/configure/edgedomain)配置SDK。 字段是一个字符串，可确定要将数据发送到的域。

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
// Example value when using a first-party domain
s.trackingServerSecure = "data.example.com";

// Example value when using a third-party domain
s.trackingServerSecure = "example.data.adobedc.net";
```

## 确定`trackingServerSecure`值的注意事项

您为`trackingServerSecure`（或`edgeDomain`）使用的值取决于您的组织如何向Adobe发送数据：

* **如果贵组织使用第一方域**，例如通过[Adobe管理的证书计划](https://experienceleague.adobe.com/zh-hans/docs/core-services/interface/data-collection/adobe-managed-cert)、[客户管理的证书](https://experienceleague.adobe.com/zh-hans/docs/core-services/interface/data-collection/customer-managed-cert)或[内容交付网络(CDN)](https://experienceleague.adobe.com/zh-hans/docs/core-services/interface/data-collection/cdn)，请将该值设置为该域。 例如：`data.example.com`。
* **如果您的组织使用第三方域**，请将该值设置为您的租户ID子域`data.adobedc.net`。 例如：`example.data.adobedc.net`。

有关每个选项的详细信息，包括如何查找租户ID，请参阅CX Enterprise界面和管理指南中的[选择数据收集域](https://experienceleague.adobe.com/zh-hans/docs/core-services/interface/data-collection/collection-domain)。

Adobe强烈建议在[解决方案设计文档](../../prepare/solution-design.md)中维护此信息，以保持整个组织的一致性。

## 不使用访客ID服务或Experience Platform Identity服务所产生的影响

Adobe强烈建议在所有实施中使用ECID作为访客身份的主要形式。 可以通过多种不同的方式收集ECID，具体取决于实施类型：

* 手动AppMeasurement实施使用`VisitorAPI.js`并调用`getInstance`方法。 有关详细信息，请参阅[为Analytics实施访客ID服务](https://experienceleague.adobe.com/zh-hans/docs/id-service/using/implementation/setup-analytics)。
* 使用Adobe Analytics标记扩展的实施使用[[!UICONTROL Experience Cloud ID服务]标记扩展](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/extensions/client/id-service/overview)，该扩展实现了访客ID服务。 添加后，无需其他配置。
* 使用任何形式的Web SDK（`alloy.js`或Web SDK标记扩展）的实施会自动包含Experience Platform Identity服务。 设置`edgeDomain`值后无需进行配置。

**如果您的实施不使用ECID**，请考虑对您的实施产生以下影响：

* 如果未使用访客ID服务或Experience Platform Identity服务，`trackingServerSecure`将确定Cookie位置。 将此变量设置为第三方域会强制AppMeasurement使用回退Cookie，因为大多数现代浏览器会拒绝第三方Cookie。
* 内部链接跟踪和Activity Map可能不太可靠。
