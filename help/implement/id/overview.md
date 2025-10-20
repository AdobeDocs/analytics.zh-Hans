---
title: Adobe Analytics中的访客识别
description: 了解如何使用最新最佳实践在Adobe Analytics中识别访客。
source-git-commit: 779ba5b0a1d71467aaaf3872fd707cc323ae8af2
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 12%

---

# Adobe Analytics中的访客识别

访客识别对于Adobe Analytics提供的用于了解在线用户行为的价值至关重要。 它涉及使用通用标识符将一段时间内的点击链接到同一个人。 准确的访客识别可确保可靠的量度，并支持健康的实施策略。 Adobe建议组织优先考虑现代身份服务，以实现跨平台的一致性和数据完整性。

Adobe Analytics中的访客识别包含以下组件：

* 客户端标识符：通常存储在第一方Cookie中。 由于现代浏览器隐私标准的缘故，依赖第三方Cookie的实施与访客识别不太一致。
* 服务器端标识符：每个Analytics访客ID都与Adobe服务器上的一个配置文件绑定。 这些访客配置文件允许在变量（如[eVars](/help/components/dimensions/evar.md)）上持久保留。 无论任何访客ID Cookie是否过期，用户档案在处于至少13个月的非活动状态之后都会被删除。

## Adobe Analytics标识操作顺序

当Adobe收到点击时，将按顺序进行以下检查。 如果给定属性存在，Adobe会使用该标识符进行点击。 如果点击中存在多个标识符，则仅使用第一个方法。

| 使用的顺序 | 查询参数 | 前提条件 |
|---|---|---|
| **1<sup>st</sup>** | `vid` | 已设置 [`visitorID`](/help/implement/vars/config-vars/visitorid.md) 变量。 |
| **2<sup>nd</sup>** | `aid` | 访客现有[`s_vi`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) Cookie。 在不实施访客 ID 服务或在实施该服务之前进行设置。 |
| **3<sup>rd</sup>** | `mid` | 访客现有[`s_ecid`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) Cookie。 在使用[Adobe Experience Cloud Identity服务](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hans)的实施上设置。 Adobe建议尽可能对所有实施使用ID服务。 |
| **4<sup>th</sup>** | `fid` | 访客现有[`s_fid`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) Cookie，或者由于任何原因无法设置`aid`和`mid`。 |
| **5<sup>th</sup>** | IP 地址、用户代理、网关 IP 地址 | 在访客的浏览器不接受Cookie时用作最后手段来识别独特访客。 |

## 影响独特访客计数的行为

独特访客标识符通常存储在浏览器 Cookie 中。如果访客执行以下任何操作，则会计为新的独特访客：

* 随时清除其Cookie。 每次清除缓存后，点击均会计为一位独特访客。
* 访客ID Cookie会因其浏览器的隐私设置而过期。 一些浏览器包括可限制Cookie生命周期的跟踪预防方法。
* 在同一台计算机上打开其他浏览器。每个浏览器计算一个独特访客。
* 打开专用浏览会话(例如，Chrome的“隐身”选项卡)。 关闭所有选项卡后，每个浏览会话计算一个独特访客。
* 在不同设备上访问您的网站。 每台设备计算一个独特访客。
* 在处于非活动状态超过13个月后访问您的网站。

考虑在Customer Journey Analytics中使用[拼接](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/stitching/overview)来识别使用多个浏览器或多个设备的同一个人。

## 不影响独特访客计数的行为

只要保留访客标识符，就&#x200B;*不计算新的独特访客*：

* 关闭浏览器（少于13个月）
* 访客将他们的浏览器升级到最新版本
* 重新启动计算机
