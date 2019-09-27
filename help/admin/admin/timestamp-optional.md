---
description: 可以将加盖时间戳和未加盖时间戳的数据合并到单个报表包中。
seo-description: 可以将加盖时间戳和未加盖时间戳的数据合并到单个报表包中。
seo-title: 可选时间戳
solution: Analytics
title: 可选时间戳
topic: 管理工具
uuid: 0fa63658-1cc2-4adc-8d51-a0662d0a941
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# 可选时间戳

可以将加盖时间戳和未加盖时间戳的数据合并到单个报表包中。

使用可选时间戳，您可以：

* 在同一全局报表包中混合加盖时间戳和未加盖时间戳的数据。
* 将加盖时间戳的数据从移动设备应用程序发送至全局报表包。
* 升级应用程序以使用离线跟踪功能，而不必创建新的报表包。

请参阅[使用可选时间戳](/help/implement/js-implementation/timestamps-overview.md)，以了解在报表包中使用时间戳的最佳做法。

>[!IMPORTANT]
>
>If you are using Timestamps Optional, then do not set [s.visitorID](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_custom.html) on data that is already timestamped. 这可能会导致数据混乱，并且会对时间计算操作（例如，逗留时间值）、属性（eVar 持久性）、访问量/访问计数以及路径报表产生负面影响。

>[!NOTE]
>
>启用了时间戳的会话数据会保存长达 92 天。这意味着访问／会话将“保持打开状态”92天，而任何额外点击（在上次点击后30分钟内）仍可包含在同一访问／会话中。 收到的任何“旧”点击如不订购，将产生“未知”的结果，因为有许多因素（分段、分配、过期等）影响是否将这些点击包含在报告中。

## 新建报表包 {#section_095A7CFBD280494593B9BEC1592B73A6}

* 如果通过模板创建，则新报表包将默认使用“可选时间戳”。

   （您可在以下位置通过模板新建报表包：**管理员 &gt; 报表包 &gt; 新建 &gt; 报表包**。）
* 如果从现有的报表包进行复制，则新报表包将继承原始报表包的时间戳设置，其中包括：

   * **禁用时间戳**（支持设置 s.visitorID）
   * **必须提供时间戳**（不支持设置 s.visitorID）
   * **可选时间戳**（支持设置 s.visitorID，但不适用于带有时间戳的点击）

## 将现有报表包更改为“可选时间戳” {#section_40BCD3B4639241DEA716F7640ED33E72}

1. 转到&#x200B;**管理员 &gt; 报表包 &gt; 编辑设置 &gt; 常规 &gt; 时间戳配置**。
1. 选中&#x200B;**将选定的报表包转换为可选时间戳**&#x200B;框。

   这会将您的报表包更改为“可选时间戳”。

>[!NOTE]
>
>If a report suite was set to **Timestamps Optional**, to change this to any other setting, please contact Adobe Client Care.

