---
title: 独特访客
description: 唯一个人（或设备）的数量。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 10%

---


# 独特访客

“唯一访客”度量显示维度项的访客ID数。 它是确定流量时使用的最常见的指标之一，因为它提供了维度项目受欢迎程度的高级概述。 例如，访客可以在一个月内每天访问您的网站，但仍将其计为单个唯一访客。

如果您使 [用跨设备分析](../cda/overview.md)，则此指标将重命名为“唯一设备”。

## 每日、每周、每月、每季度和每年唯一访客

报告和Analytics为每日、每周、每月、每季和每年唯一访客提供选项。 唯一访客不会计入整个时间段的单个唯一访客，而是根据所选的度量计数。 例如，您希望查看网站的每日独特访客。 如果访客在早晨和晚上来到您的网站，他们将计为每天唯一的访客。 如果访客在周一和周二再次访问您的网站，他们将计为每天两个独特的访客。

Analysis Workspace根据报表的粒度处理唯一访客。 例如，如果您使用 [Day](../dimensions/day.md) dimension，您将看到每个维项目的每日唯一访客。 但是，对于报表合计，它会消除自由形式表日期范围的重复唯一访客。

## 如何计算此度量

此度量计算给定维度项的唯一访客ID的数量。 它使用多种高级机制来识别独特的访客，因为有多种方法可以识别它们。 下表列表了访客的识别方式及其优先级。 一些点击可以有多种访客识别方法； 在这些情况下，使用较高优先级的方法。

| 使用顺序 | 查询参数（收集方法） | 前提条件 |
| --- | --- | --- |
| 1 | `vid` | 变量 [`visitorID`](/help/implement/vars/config-vars/visitorid.md) 已设置。 |
| 2 | `aid` | 访客有现有 [`s_vi`](https://docs.adobe.com/content/help/zh-Hans/core-services/interface/ec-cookies/cookies-analytics.html) cookie。 在不实施访客ID服务或在实施该服务之前进行设置。 |
| 3 | `mid` | 访客有现有 [`s_ecid`](https://docs.adobe.com/content/help/zh-Hans/core-services/interface/ec-cookies/cookies-analytics.html) cookie。 在使用Adobe Experience Cloud Identity服 [务的实施中设置](https://docs.adobe.com/content/help/zh-Hans/id-service/using/home.html)。 |
| 4 | `fid` | 访客有现 [`s_fid`](https://docs.adobe.com/content/help/zh-Hans/core-services/interface/ec-cookies/cookies-analytics.html) 有的cookie，或者 `aid` 由于 `mid` 任何原因无法设置和。 |
| 5 | IP 地址、用户代理、网关 IP 地址 | 如果访客的浏览器不接受cookie，最后确定唯一访客。 |

>[!NOTE]
>
>每个Analytics访客ID都与Adobe服务器上的用户档案关联。 这些访客用户档案在至少13个月不活动后被删除，而不管任何访客ID cookie过期。

## 影响唯一访客计数的行为

唯一访客标识符通常存储在浏览器cookie中。 如果新的唯一访客执行以下任一操作，则计数这些唯一数据：

* 随时清除其缓存
* 在同一台计算机上打开其他浏览器。 每个浏览器计数一个唯一访客。
* 在不同设备上浏览网站的同一人。 每台设备计算一个单独的唯一访客。 您可以使用 [跨设备分析](../cda/overview.md) ，使用“人员”指标将访客 [组合到一](people.md) 起。
* 打开隐私浏览会话（如Chrome的Incognito选项卡）。

只要保留Cookie标 *识符* ，就不会计算新的唯一访客:

* 在较长的时间内关闭浏览器
* 将他们的浏览器升级到最新版本
