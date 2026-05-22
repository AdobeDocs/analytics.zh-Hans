---
title: 实施 Adobe Analytics
description: 在您的网站、属性或应用程序上实施 Adobe Analytics。
feature: Implementation Basics
exl-id: 2b629369-2d69-4dc6-861a-ff21a46d39e0
role: Admin, Developer, Leader, User
TQID: https://experienceleague.adobe.com/c1TZC9k-mu1n95Oq3jhQOvcBXFwx8oK28plhoNcJDK4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: c77ba355-6681-41fe-b719-563d3f507fdb
  - id: c8add8f2-4250-4fd9-9cde-9707036c567d
  - id: df312454-73c4-43f6-a90e-18f5043f074c
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 29d1585ad3d00922a7e39bf1b4da64089d9168c7
workflow-type: tm+mt
source-wordcount: 814
ht-degree: 83%

---

# 实施 Adobe Analytics

![横幅](../../assets/doc_banner_implement.png)

Adobe Analytics 需要在您的网站、移动应用程序或其他应用程序中实施相应代码，才能将数据发送到数据收集服务器。 根据平台和贵组织的需求，可以通过多种方法来实施相应代码。

## 网站实施方法

对于您的&#x200B;**网站**，可以使用以下实现方法：

### 客户端

* **Web SDK 扩展**：这是一种在为新客户实施 Adobe Analytics 时推荐使用的标准化方法。 在 Adobe Experience Platform Data Collection **标记**&#x200B;中添加 **Adobe Experience Platform Web SDK 扩展**，然后在每个页面上放置一个加载器标记。 该标记将数据发送到 Adobe Experience Platform **Edge Network**，而后者将这些数据转发到 Adobe Analytics。
  ![Web SDK扩展](./assets/websdk-extension-implementation.png)
请参阅[如何使用Adobe Analytics Web SDK扩展实施Adobe Experience Platform。](./aep-edge/overview.md) 了解更多信息。

* **Web SDK**：如果您不想使用 Adobe Experience Platform 数据收集，可以在您的站点上手动加载 Web SDK 库。 在每个页面上引用 Web SDK 库 (`alloy.js`)，并将所需的跟踪调用以您组织方便的格式发送到 Adobe Experience Platform **Edge Network**。 Edge Network 将这些数据转发到 Adobe Analytics。
  ![Web SDK](./assets/websdk-implementation.png)
有关详细信息，请参阅[如何使用Adobe Experience Platform Web SDK实施Adobe Analytics](./aep-edge/overview.md)。

* **Analytics 扩展**：在 Adobe Experience Platform 数据收集&#x200B;**标签**&#x200B;中添加 **Adobe Analytics 扩展**，然后在每个页面上放置一个加载器标记。 该标记将数据直接发送到 Adobe Analytics。 如果要利用标记的便利，但不想使用 Edge Network 基础设施，请使用此实施。
  ![Adobe Analytics扩展](./assets/analytics-extension-implementation.png)
有关更多信息，请参阅[如何使用Adobe Analytics扩展实施Analytics](launch/overview.md)。

* **旧版 JavaScript**：历史上用于实施 Adobe Analytics 的手动方法。 在每个页面上引用 AppMeasurement 库 (`AppMeasurement.js`)，然后在 JavaScript 中设置变量和各种设置。
  ![如何使用旧版JavaScript实施Adobe Analytics](./assets/appmeasurement-implementation.png)
此实施方法对于使用自定义代码的实施非常有用，非常适合于其他地方未提供的实施类型，例如[AMP页面](other/amp.md)。

以下决策流程可帮助您选择客户端实施方法：

![用于选择实施方法的决策树，如本节所述。](./assets/decision-tree.png)


>[!TIP]
>
>有关根据您的当前状况要选择何种实施的建议和最佳实践，请联系您的 Adobe 客户团队。

### 服务器端

要实施 Adobe Analytics 服务器端，您有以下选项：

* **Edge Network API**：您在使用 Adobe Experience Platform Edge Network API 通过数据流与 Adobe Analytics 进行通信的服务器上实施代码。
  ![服务器端实施](assets/edge-network-server-api.png)
有关详细信息，请参阅[使用Adobe Experience Platform Edge Network API实施Adobe Analytics](/help/implement/aep-edge/api/overview.md)。

* **（批量）数据插入 API**：您可以使用 Adobe Analytics（批量）数据插入 API 将服务器端数据直接收集到 Adobe Analytics 中。
  ![数据插入API](assets/analytics-apis.png)
有关详细信息，请参阅[数据插入API](../import/c-data-insertion-api/c-data-insertion-api.md)。

## 移动应用程序实施方法

对于您的&#x200B;**移动应用程序**，可以使用以下实现方法：

* **Mobile SDK 扩展**：这是一种在您的移动设备应用程序中实施 Adobe Analytics 时推荐使用的标准化方法。 使用专用库，可轻松将数据从您的移动应用程序中发送到 Adobe。 在 Adobe Experience Platform 数据收集&#x200B;**标记**&#x200B;中添加 **Adobe Experience Platform Mobile SDK 扩展**，然后在您的应用程序中实施 Mobile SDK 库。 可使用该 SDK 导入库、注册扩展和加载标记配置。 将数据发送到 Adobe Experience Platform **Edge Network**，然后 Edge 将这些数据转发到 Adobe Analytics。
  ![Mobile SDK 扩展](./assets/mobilesdk-extension.png)

  有关详细信息，请参阅[使用 Adobe Experience Platform Mobile SDK 实施 Adobe Analytics](../implement/aep-edge/mobile-sdk/overview.md)。

* **Analytics 扩展**：在 Adobe Experience Platform 数据收集&#x200B;**标记**&#x200B;中添加 **Adobe Analytics 扩展**，并在您的应用程序中实施 Mobile SDK 库。 可使用该 SDK 导入库、注册扩展和加载标记配置。 此实施方法直接将数据发送到 Adobe Analytics。 如果要利用 Adobe Experience Platform 数据收集的便利，但不想使用 Adobe 的 Experience Platform Edge 网络基础设施，则建议使用此实施。
  ![Analytics 扩展](./assets/mobilesdk-analytics-extension.png)

  有关详细信息，请参阅[使用 Analytics 扩展实施 Adobe Analytics](../implement/aep-edge/mobile-sdk/overview.md)。


>[!CAUTION]
>
>有关对 Adobe 移动 SDK 旧版本的支持，请参阅 [SDK 终止支持公告](https://developer.adobe.com/client-sdks/resources/sdks-end-of-support/)。

## 重要 Analytics 实施文章

* [负责现有的 Adobe Analytics 实施](/help/implement/prepare/existing-implementation.md)
* [Adobe Debugger](validate/debugger.md)
* [在 Experience Platform 中创建标记属性](launch/create-analytics-property.md)
* [AppMeasurement 更新](appmeasurement-updates.md)
* [使用Platform Web SDK设置Adobe Analytics教程](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/applications-setup/setup-analytics.html?lang=zh-Hans)
* [在移动应用程序中实施Adobe CX Enterprise教程](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/overview.html?lang=zh-Hans)


## 重要 Analytics 资源

* [联系客户关怀团队](https://experienceleague.adobe.com/zh-hans?support-solution=Analytics#support)
* [Experience League上的Adobe Analytics社区](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community?profile.language=zh-Hans)
* [Adobe Analytics资源](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/adobe-analytics-resources/m-p/276666?profile.language=zh-Hans)
* [最新发行说明](../release-notes/latest.md)
