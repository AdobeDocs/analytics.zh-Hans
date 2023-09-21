---
title: 独特访客
description: 独特访客 ID 的数量。
feature: Metrics
exl-id: 56e7bad4-4802-49ac-a0f1-ae77441fc016
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 97%

---

# 独特访客

“独特访客” [量度](overview.md) 显示维度项目的访客ID数量。 它是确定流量时最常用的指标之一，因为它提供了对维度项目常用程度的简要概述。例如，访客可能在一个月内每天访问您的网站，但仍将其计为一个独特访客。

如果您使用[跨设备分析](../cda/overview.md)，则此指标会被替换为[独特设备](unique-devices.md)指标。

## 每日、每周、每月、每季度和每年独特访客

Reports &amp; Analytics 提供了每日、每周、每月、每季度和每年独特访客选项。独特访客不会计算整个时间段的单个独特访客，而是会根据所选的指标进行计数。例如，您希望查看网站的每日独特访客。如果访客早上访问您的网站，晚上再次访问，将计为一个每日独特访客。如果访客周一访问您的网站，周二再次访问，将计为两个每日独特访客。

Analysis Workspace 根据报表的粒度处理独特访客。例如，如果您使用[天](../dimensions/day.md)维度，您将看到每个维度项目的每日独特访客。但是，对于报表合计，它会消除自由形式表日期范围的重复独特访客。

## 如何计算此指标

此指标计算给定维度项目的独特访客 ID 数量。它使用多种高级机制来识别独特访客，因为有多种方法可以识别他们。下表列出了识别访客的方法及其优先级。某些点击可能有多种访客识别方法；在这种情况下，使用较高优先级的方法。

| 使用顺序 | 查询参数（收集方法） | 前提条件 |
| --- | --- | --- |
| 1 | `vid` | 已设置 [`visitorID`](/help/implement/vars/config-vars/visitorid.md) 变量。 |
| 2 | `aid` | 访客现有 [`s_vi`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=zh-Hans) Cookie。在不实施访客 ID 服务或在实施该服务之前进行设置。 |
| 3 | `mid` | 访客现有 [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=zh-Hans) Cookie。在使用 [Adobe Experience Cloud Identity 服务](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hans)实施时设置。 |
| 4 | `fid` | 访客现有 [`s_fid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=zh-Hans) Cookie，或者如果由于任何原因无法设置 `aid` 和 `mid`。 |
| 5 | IP 地址、用户代理、网关 IP 地址 | 如果访客的浏览器不接受 Cookie，最后诉诸于确定独特访客。 |

>[!NOTE]
>
>每个 Analytics 访客 ID 都与 Adobe 服务器上的个人资料相关联。无论任何访客 ID Cookie 是否过期，这些访客资料在处于至少 13 个月的非活动状态之后都会被删除。

## 影响独特访客计数的行为

独特访客标识符通常存储在浏览器 Cookie 中。如果新独特访客执行以下任一操作，则计算该独特访客：

* 随时清除其缓存
* 在同一台计算机上打开其他浏览器。每个浏览器计算一个独特访客。
* 同一人在不同设备上浏览您的网站。每台设备计算一个单独的独特访客。您可以使用[跨设备分析](../cda/overview.md)和[人员](people.md)指标将访客合并起来。
* 打开隐私浏览会话（例如，Chrome 的“隐身”选项卡）。

只要保留 Cookie 标识符，就&#x200B;*不会* 计算新的独特访客：

* 访客关闭他们的浏览器过长时间
* 访客将他们的浏览器升级到最新版本
