---
title: 使用Adobe Analytics标记扩展进行访客识别
description: 在实施Adobe Analytics标记扩展时正确识别访客。
source-git-commit: 5bd1914dc52c664348f30793761f0fc347343156
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 0%

---

# 使用Adobe Analytics标记扩展进行访客识别

Adobe Analytics标记扩展允许您使用标记管理界面实施AppMeasurement。 由于此标记扩展本质上是隐藏的AppMeasurement，因此它提供了类似的方法来识别访客，并且要求为访客ID服务使用单独的标记扩展。

## 使用访客ID服务识别访客（推荐）

要使用Adobe Analytics标记扩展使用访客ID服务，请在标记属性中包含Experience Cloud ID服务标记扩展。

1. 使用您的Adobe ID凭据登录[experience.adobe.com](https://experience.adobe.com)。
1. 导航到&#x200B;**[!UICONTROL 数据收集]** > **[!UICONTROL 标记]**。
1. 找到所需的标记属性。
1. 导航到&#x200B;**[!UICONTROL 扩展]**，然后选择&#x200B;**[!UICONTROL 目录]**&#x200B;选项卡。
1. 找到&#x200B;**[!UICONTROL Experience Cloud ID服务]**&#x200B;扩展，然后选择&#x200B;**[!UICONTROL 安装]**。

标记扩展会自动获取您的IMS组织ID，因此无需额外配置。

## 使用`s_vi` Cookie识别访客（不推荐）

>[!IMPORTANT]
>
>Adobe建议不要使用此方法来识别访客。

如果您的组织不使用访客ID服务标签扩展，则Adobe Analytics标签扩展将使用其自身的访客识别形式。 当访客首次访问您的网站时，扩展会检查[`s_vi`](https://experienceleague.adobe.com/zh-hans/docs/core-services/interface/data-collection/cookies/analytics) Cookie。 当&#x200B;**[!UICONTROL 配置标记扩展]**&#x200B;时，在匹配&#x200B;**[!UICONTROL SSL跟踪服务器]**（对于HTTPS）或[跟踪服务器](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/extensions/client/analytics/overview)（对于HTTP）的域中设置此Cookie。

* 如果您参与[托管证书计划](https://experienceleague.adobe.com/zh-hans/docs/core-services/interface/data-collection/adobe-managed-cert)，您的跟踪服务器通常是第一方域，使`s_vi` Cookie成为第一方。
* 如果您未参与托管证书计划，则跟踪服务器通常是`adobedc.net`、`omtrdc.net`或`2o7.net`的子域，从而使`s_vi` Cookie成为第三方Cookie。 由于现代浏览器隐私惯例，第三方Cookie被大多数浏览器拒绝。 被拒绝后，AppMeasurement会尝试改为设置第一方回退Cookie (`fid`)。

如果您正确设置了[!UICONTROL SSL跟踪服务器]，则无需进一步的访客识别措施。

## 使用`visitorID`识别访客（不推荐）

>[!IMPORTANT]
>
>Adobe建议不要使用此方法来识别访客。

使用&#x200B;**[!UICONTROL 访客ID]**&#x200B;变量可让您的组织完全独立地控制访客的识别。 如果使用数据元素设置[!UICONTROL 访客ID]，请注意以下限制：

* 每次点击必须包含相同的[!UICONTROL 访客ID]值才能计为单个访客。
   * 任何忽略[!UICONTROL 访客ID]数据元素的点击都会自动尝试使用其他访客识别方法，将它们视为单独的访客。
   * 任何包含与上一次点击不同的[!UICONTROL 访客ID]值的点击都将被视为单独的访客。
   * Adobe不提供将使用不同访客ID的点击拼合在一起的任何方式。
* 使用[!UICONTROL 访客ID]标识的访客不支持共享受众、Analytics for Target和客户属性。

有关使用此变量的实施说明，请参阅[`visitorID`](/help/implement/vars/config-vars/visitorid.md)。
