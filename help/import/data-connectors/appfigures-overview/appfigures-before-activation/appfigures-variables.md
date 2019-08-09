---
description: AppDigiges的数据连接器集成使用Analytics变量跟踪各种AppDigiges指标。
seo-description: AppDigiges的数据连接器集成使用Analytics变量跟踪各种AppDigiges指标。
seo-title: 分析集成变量
title: 分析集成变量
uuid: 08d5b714-1c97-4be6-ae8-1f819253425
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Analytics Integration Variables{#analytics-integration-variables}

AppDigiges的数据连接器集成使用Analytics变量跟踪各种AppDigiges指标。

下表描述了自动激活用于appDigiges集成的Analytics变量。

## 必需变量 {#section-3ca8dc46bab0436cba0c9ef827c8356a}

>[!NOTE]
>
>此集成将专用变量用于应用商店数据，因此您无需指定自定义商务变量和事件。

| 变量类型 | 名称 | 填充方法 | 描述 |
|---|---|---|---|
| eVar | 应用商店对象 ID | 从AppDigiges导入。 | 将此eVar配置为访问到期、最近分配和基本子关系。 |
| event(数字) | 应用商店下载 | 从AppDigiges导入。 | 移动应用程序下载次数。 |
| event(数字) | App Store购买(在应用程序中) | 从AppDigiges导入。 | 应用程序内购买和订阅的数量。 |
| event(数字) | 应用商店排名 | 从AppDigiges导入。 | 用于定义平均AppDigit计算量度。不直接使用。 |
| event(数字) | 应用商店排名因素 | 从AppDigiges导入。 | 用于定义平均AppDigit计算量度。不直接使用。 |
| event(数字) | App Store 排行榜 | 从AppDigiges导入。 | 用于定义平均AppDigit计算量度。不直接使用。 |
| event(数字) | App Store 排名因素 | 从AppDigiges导入。 | 用于定义平均AppDigit计算量度。不直接使用。 |
| event(货币) | App Store收入(应用程序) | 从AppDigiges导入。 | 应用程序内收入减去商店费用。 |
| event(货币) | App Store Revenue(一次关闭) | 从AppDigiges导入。 | 应用程序购买的总收入减去商店费用。 |
| event(货币) | App Store Preralies(应用程序) | 从AppDigiges导入。 | 未使用 |
| event(货币) | App Store版税(一次性) | 从AppDigiges导入。 | 未使用 |

