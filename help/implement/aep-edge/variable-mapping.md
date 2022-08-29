---
title: Adobe Experience Edge 中的 Analytics 变量映射
description: 查看 Edge 自动映射到 Analytics 变量的 XDM 字段。
exl-id: fbff5c38-0f04-4780-b976-023e207023c6
source-git-commit: 4fedc1d27a03d4376103e4648e1e66cbd62346af
workflow-type: ht
source-wordcount: '1381'
ht-degree: 100%

---

# Adobe Experience Edge 中的 Analytics 变量映射

下表显示了 Adobe Experience Platform Edge Network 自动映射到 Adobe Analytics 的变量。 如果使用这些 XDM 字段路径，则无需额外配置即可将数据发送到 Adobe Analytics。

| XDM 字段路径 | Analytics 维度和描述 |
| --- | --- |
| `application.isClose` | 帮助定义移动量度[崩溃](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=zh-Hans#metrics)。 |
| `application.isInstall` | 帮助确定何时增加[首次发布](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=zh-Hans#metrics)移动量度。 |
| `application.isLaunch` | 帮助确定何时增加[首次发布](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=zh-Hans#metrics)移动量度。 |
| `application.closeType` | 确定关闭事件是否为崩溃。 有效值包括 `close`（生命周期会话结束，前一个会话收到暂停事件）和 `unknown`（生命周期会话结束，没有暂停事件）。 帮助设定[崩溃](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=zh-Hans#metrics)量度。 |
| `application.isInstall` | 移动量度[安装](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=zh-Hans#metrics)。 |
| `application.isLaunch` | 移动量度[发布](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=zh-Hans#metrics)。 |
| `application.name` | 帮助设置移动维度 [App ID](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=zh-Hans#dimensions)。 |
| `application.isUpgrade` | 移动量度[升级](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=zh-Hans#metrics)。 |
| `application.version` | 帮助设置移动维度 [App ID](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=zh-Hans#dimensions)。 |
| `application.sessionLength` | 移动量度[上一个会话长度](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=zh-Hans#metrics)。 |
| `commerce.checkouts.id` | 将[事件序列化](../vars/page-vars/events/event-serialization.md)应用于[“结账”](../../components/metrics/checkouts.md)量度。 |
| `commerce.checkouts.value` | 按所需的量增加[“结账”](../../components/metrics/checkouts.md) 量度。 |
| `commerce.order.currencyCode` | 设置 [currencyCode](../vars/config-vars/currencycode.md) 配置变量。 |
| `commerce.order.purchaseID` | 设置 [purchaseID](../vars/page-vars/purchaseid.md) 页面变量。 |
| `commerce.productListAdds.id` | 将[事件序列化](../vars/page-vars/events/event-serialization.md)应用于[“购物车添加”](../../components/metrics/cart-additions.md)量度。 |
| `commerce.productListAdds.value` | 增加[购物车添加](../../components/metrics/cart-additions.md) 量度。 |
| `commerce.productListOpens.id` | 将[事件序列化](../vars/page-vars/events/event-serialization.md)应用于[“购物车”](../../components/metrics/carts.md)量度。 |
| `commerce.productListOpens.value` | 增加[购物车](../../components/metrics/carts.md) 量度。 |
| `commerce.productListRemovals.id` | 将[事件序列化](../vars/page-vars/events/event-serialization.md)应用于[“购物车移除”](../../components/metrics/cart-removals.md)量度。 |
| `commerce.productListRemovals.value` | 增加[购物车减货](../../components/metrics/cart-removals.md) 量度。 |
| `commerce.productListViews.id` | 将[事件序列化](../vars/page-vars/events/event-serialization.md)应用于[“购物车查看”](../../components/metrics/cart-views.md)量度。 |
| `commerce.productListViews.value` | 增加[购物车查看次数](../../components/metrics/cart-views.md) 量度。 |
| `commerce.productViews.id` | 将[事件序列化](../vars/page-vars/events/event-serialization.md)应用于[“产品查看”](../../components/metrics/product-views.md)量度。 |
| `commerce.productViews.value` | 增加[“产品查看次数”](../../components/metrics/product-views.md) 量度。 |
| `commerce.purchases.value` | 增加[“订单”](../../components/metrics/orders.md) 量度。 |
| `device.model` | 移动维度 [设备名称](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=zh-Hans#dimensions)。 |
| `device.colorDepth` | 帮助设置 [“颜色深度”](../../components/dimensions/color-depth.md) 维度。 |
| `device.screenHeight` | 帮助设置移动维度 [“监测器分辨率”](../../components/dimensions/monitor-resolution.md) 维度。 |
| `device.screenWidth` | 帮助设置移动维度 [“监测器分辨率”](../../components/dimensions/monitor-resolution.md) 维度。 |
| `device.type` | 移动设备类型。 |
| `environment.browserDetails.acceptLanguage` | 帮助设置 [“语言”](../../components/dimensions/language.md) 维度。 |
| `environment.browserDetails.cookiesEnabled` | 设置 [“Cookie 支持”](../../components/dimensions/cookie-support.md) 维度。 有效值包括 `Y`（浏览器接受 Cookie）和 `N`（浏览器拒绝 Cookie）。 |
| `environment.browserDetails.javaEnabled` | 设置 [“启用 Java”](../../components/dimensions/java-enabled.md) 维度。 有效值包括 `Y`（Java 已启用）和 `N`（Java 已禁用）。 |
| `environment.browserDetails.userAgent` | 用作后备的[独特访客](../../components/metrics/unique-visitors.md)识别方法。 通常使用 `User-Agent` HTTP 请求头填充。 如果要在报告中使用此字段，可以将其映射到 eVar。 |
| `environment.browserDetails.viewportHeight` | 设置 [“浏览器高度”](../../components/dimensions/browser-height.md) 维度。 |
| `environment.browserDetails.viewportWidth` | 设置 [“浏览器宽度”](../../components/dimensions/browser-width.md) 维度。 |
| `environment.carrier` | 移动维度[“运营商名称”](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=zh-Hans#dimensions)。 |
| `environment.connectionType` | 帮助设置 [“连接类型”](../../components/dimensions/connection-type.md) 维度。 |
| `environment.ipV4` | 用作后备的[独特访客 ](../../components/metrics/unique-visitors.md) 识别方法。 通常使用 `X-Forwarded-For` HTTP 头填充。 |
| `environment.language` | 移动维度区域设置。 |
| `environment.operatingSystem` | 移动维度[操作系统](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=zh-Hans#dimensions)。 |
| `environment.operatingSystemVersion` | 帮助设置[操作系统版本](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=zh-Hans#dimensions)维度。 |
| `_experience.analytics.customDimensions.`<br/>`eVars.eVar1` -<br/>`_experience.analytics.customDimensions.`<br/>`eVars.eVar250` | 设置相应的 [eVar](../../components/dimensions/evar.md) 维度。 |
| `_experience.analytics.customDimensions.`<br/>`listProps.prop1.delimiter` -<br/>`_experience.analytics.customDimensions.`<br/>`listProps.prop75.delimiter` | 用于给定 [List Prop](../vars/page-vars/prop.md#list-props) 的分隔符。 |
| `_experience.analytics.customDimensions.`<br/>`listProps.prop1.values` -<br/>`_experience.analytics.customDimensions.`<br/>`listProps.prop75.values` | 一个字符串数组，包含相应的 [List Prop](../vars/page-vars/prop.md#list-props) 值。 |
| `_experience.analytics.customDimensions.`<br/>`lists.list1.list[].value` -<br/>`_experience.analytics.customDimensions.`<br/>`lists.list3.list[].value` | 使用逗号分隔符将每个 `list[]` 数组中的所有 `value` 字符串连接到其各自的[列表变量](../vars/page-vars/list.md)。 |
| `_experience.analytics.customDimensions.`<br/>`props.prop1` -<br/>`_experience.analytics.customDimensions.`<br/>`props.prop75` | 设置相应的 [Prop](../../components/dimensions/prop.md) 维度。 |
| `_experience.analytics.event1to100.`<br/>`event1.id` -<br/>`_experience.analytics.event901to1000.`<br/>`event1000.id` | 将[事件序列化](../vars/page-vars/events/event-serialization.md)应用于相应的[自定义事件](../../components/metrics/custom-events.md)量度。 |
| `_experience.analytics.event1to100.`<br/>`event1.value` -<br/>`_experience.analytics.event901to1000.`<br/>`event1000.value` | 按所需的量增加相应的[自定义事件](../../components/metrics/custom-events.md)量度。 |
| `identityMap.ECID[0].id` | [Adobe Experience Cloud 身份服务 ID](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hans)。 |
| `marketing.trackingCode` | 设置 [“跟踪代码”](../../components/dimensions/tracking-code.md) 维度。 |
| `media.mediaTimed.completes.value` | Media Analytics 量度[内容完成](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=zh-Hans#content-complete)。 |
| `media.mediaTimed.dropBeforeStart.value` | `c.a.media.view`, `c.a.media.timePlayed`, `c.a.media.play` |
| `media.mediaTimed.federated.value` | Media Analytics 量度[联邦数据](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=zh-Hans#federated-data)。 |
| `media.mediaTimed.firstQuartiles.value` | Media Analytics 量度 [25% 进度标记](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=zh-Hans#twenty-five-progress-marker)。 |
| `media.mediaTimed.mediaSegmentView.value` | Media Analytics 量度[内容区段视图](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=zh-Hans#content-segment-views)。 |
| `media.mediaTimed.midpoints.value` | Media Analytics 量度 [50% 进度标记](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=zh-Hans#fifty-progress-marker)。 |
| `media.mediaTimed.pauseTime.value` | Media Analytics 量度[总暂停时间](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=zh-Hans#total-pause-duration)。 |
| `media.mediaTimed.pauses.value` | Media Analytics 量度[暂停事件](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=zh-Hans#pause-events)。 |
| `media.mediaTimed.primaryAssetReference.`<br/>`@id` | Media Analytics 维度[资产 ID](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=zh-Hans#asset-id)。 |
| `media.mediaTimed.primaryAssetReference.`<br/>`dc:title` | Media Analytics 维度[视频名称](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=zh-Hans#video-name)。 |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Creator[N].iptc4xmpExt:Name` | Media Analytics 维度[发起人](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=zh-Hans#originator)。 |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Episode.iptc4xmpExt:Number` | Media Analytics 维度[集](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=zh-Hans#episode)。 |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Genre` | Media Analytics 维度[流派](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=zh-Hans#genre)。 |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Rating[N].iptc4xmpExt:RatingValue` | Media Analytics 维度[内容评级](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=zh-Hans#content-rating)。 |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Season.iptc4xmpExt:Number` | Media Analytics 维度[季](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=zh-Hans#season)。 |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Series.iptc4xmpExt:Identifier` | Media Analytics 维度[内容 ID](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=zh-Hans#content-id)。 |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Series.iptc4xmpExt:Name` | Media Analytics 维度[节目](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=zh-Hans#show)。 |
| `media.mediaTimed.primaryAssetReference.`<br/>`showType` | Media Analytics 维度[节目类型](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=zh-Hans#show-type)。 |
| `media.mediaTimed.primaryAssetReference.`<br/>`xmpDM:duration` | Media Analytics 维度[视频长度](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=zh-Hans#video-length)。 |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`@id` | Media Analytics 维度[媒体会话 ID](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=zh-Hans#media-session-id)。 |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastChannel` | Media Analytics 维度[内容频道](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=zh-Hans#content-channel)。 |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastContentType` | Media Analytics 维度[内容类型](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=zh-Hans#content-type)。 |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastNetwork` | Media Analytics 维度[网络](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=zh-Hans#network)。 |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`mediaSegmentView.value` | Media Analytics 维度[内容区段](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=zh-Hans#content-segment)。 |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`playerName` | Media Analytics 维度[内容播放器名称](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=zh-Hans#content-player-name)。 |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`playerSDKVersion.version` | Media Analytics 维度 [SDK 版本](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=zh-Hans#sdk-version)。 |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`sourceFeed` | Media Analytics 维度[媒体馈送类型](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=zh-Hans#media-feed-type)。 |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`streamFormat` | Media Analytics 维度[流格式](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=zh-Hans#stream-format)。 |
| `media.mediaTimed.progress10.value` | Media Analytics 量度 [10% 进度标记](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=zh-Hans#ten-progress-marker)。 |
| `media.mediaTimed.progress95.value` | Media Analytics 量度 [95% 进度标记](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=zh-Hans#ninety-five-progress-marker)。 |
| `media.mediaTimed.resumes.value` | Media Analytics 量度[内容恢复](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=zh-Hans#content-resumes)。 |
| `media.mediaTimed.starts.value` | Media Analytics 量度[媒体开始](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=zh-Hans#media-starts)。 |
| `media.mediaTimed.thirdQuartiles.value` | Media Analytics 量度 [75% 进度标记](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=zh-Hans#seventy-five-progress-marker)。 |
| `media.mediaTimed.timePlayed.value` | Media Analytics 量度[内容花费时间](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=zh-Hans#content-time-spent)。 |
| `media.mediaTimed.totalTimePlayed.value` | Media Analytics 量度[媒体花费时间](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=zh-Hans#media-time-spent)。 |
| `placeContext.geo.latitude` | 移动维度”纬度“。 |
| `placeContext.geo.longitude` | 移动维度”经度“。 |
| `placeContext.geo.postalCode` | [“邮政编码”](../../components/dimensions/zip-code.md) 维度。 |
| `placeContext.geo.stateProvince` | [“美国”](../../components/dimensions/us-states.md) 维度。 |
| `productListItems[]._experience.analytics.`<br/>`customDimensions.eVars.eVar1` -<br/>`productListItems[]._experience.analytics.`<br/>`customDimensions.eVars.eVar250` | 将[产品语法](../vars/page-vars/products.md)促销应用于 eVar。 |
| `productListItems[]._experience.analytics.`<br/>`event1to100.event1.value` -<br/>`productListItems[]._experience.analytics.`<br/>`event901-1000.event1000.value` | 将[产品语法](../vars/page-vars/products.md)促销应用于事件。 |
| `productListItems[].lineItemId` | [“类别”](../../components/dimensions/category.md) 维度。另请参阅[产品](../vars/page-vars/products.md)页面变量。 |
| `productListItems[].name` | [产品](../../components/dimensions/product.md)维度。另请参阅[产品](../vars/page-vars/products.md)页面变量。 如果 `productListItems[].SKU` 和 `productListItems[].name` 都包含数据，则使用 `productListItems[].SKU` 中的值。 |
| `productListItems[].priceTotal` | 帮助确定[收入](../../components/metrics/revenue.md)量度。另请参阅[产品](../vars/page-vars/products.md)页面变量。 |
| `productListItems[].quantity` | 帮助确定[单位](../../components/metrics/units.md)量度。另请参阅[产品](../vars/page-vars/products.md)页面变量。 |
| `productListItems[].SKU` | [产品](../../components/dimensions/product.md)维度。另请参阅[产品](../vars/page-vars/products.md)页面变量。如果 `productListItems[].SKU` 和 `productListItems[].name` 都包含数据，则使用 `productListItems[].SKU` 中的值。 |
| `web.webInteraction.URL` | [linkURL](../vars/config-vars/linkurl.md) 实施变量。 |
| `web.webInteraction.name` | [自定义链接](../../components/dimensions/custom-link.md)、[下载链接](../../components/dimensions/download-link.md) 或者[退出链接](../../components/dimensions/exit-link.md)维度取决于 `web.webInteraction.type` 中的值 |
| `web.webInteraction.type` | 确定链接点击的类型。 有效值包括 `other`（自定义链接）、`download`（下载链接）和 `exit`（退出链接）。 |
| `web.webPageDetails.URL` | [页面 URL](../../components/dimensions/page-url.md) 维度。 |
| `web.webPageDetails.errorPage` | 帮助确定“找不到页面”[维度](../../components/dimensions/pages-not-found.md)和[量度](../../components/metrics/pages-not-found.md)。 |
| `web.webPageDetails.name` | [页面](../../components/dimensions/page.md)维度。 |
| `web.webPageDetails.server` | [服务器](../../components/dimensions/server.md)维度。 |
| `web.webPageDetails.siteSection` | [网站分区](../../components/dimensions/site-section.md)维度。 |
| `web.webReferrer.URL` | [推荐人](../../components/dimensions/referrer.md)维度。 |

{style=&quot;table-layout:auto&quot;}

<!-- `environment.browserDetails.javaScriptVersion` and `web.webPageDetails.homePage` were included in the original table, but they no longer exist in Analytics. | -->

## 将其他 XDM 字段映射到 Analytics 变量

如果有任何维度或量度要添加到 Adobe Analytics 中，可以通过[上下文数据变量](../vars/page-vars/contextdata.md)进行添加。 任何未自动映射的 XDM 字段元素将作为前缀为 a.x 的上下文数据发送到 Adobe Analytics。然后，您可以利用[处理规则](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules.html?lang=zh-Hans)将此上下文数据变量映射到所需的 Analytics 变量中。 例如，如果发送以下事件：

```js
alloy("event",{
    "xdm":{
        "_atag":{
            "search":{
                "term":"Example search term"
            }
        }
    }
})
```

Web SDK 将该数据作为上下文数据变量发送给 Adobe Analytics `a.x._atag.search.term`。 然后，您可以使用处理规则将该上下文数据变量值分配给所需的 Analytics 变量，例如 eVar：

![搜索词处理规则](assets/examplerule.png)
