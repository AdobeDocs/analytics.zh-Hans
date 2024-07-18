---
title: 在Adobe Analytics中排除数据
description: 了解有关如何在数据收集之前和之后排除数据的各种方法。
exl-id: dee5bf3b-8bb3-48eb-908d-b4a981f17bfb
feature: Data Configuration and Collection
role: Admin
source-git-commit: d3d5b01fe17f88d07a748fac814d2161682837c2
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 0%

---

# 在Adobe Analytics中排除数据

排除数据通常用于防止组织的测试工作填充生产数据，或防止不需要的数据错误地使报表虚增。 使用以下任意方法，根据您的用例从Adobe Analytics中排除数据。

## 排除数据后收集

以下方法是在Adobe数据收集服务器接收图像请求后在Analytics报表中排除数据的方法。 使用这些方法排除的数据仍会计入计费服务器调用。

* **按IP排除**： Adobe Analytics提供了在报表包中排除IP地址或范围数据的基本功能。 请参阅管理员用户指南中的[按IP排除](/help/admin/admin/exclude-ip.md)。
* **机器人规则**：机器人规则从已知的机器人用户代理字符串中获取流量，并将其从Analytics报表中排除。 通过机器人规则排除的数据将放入机器人报表中。 可创建自定义机器人规则以排除其他数据。 请参阅管理员用户指南中的[机器人规则](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md)。
* **VISTA规则**：根据您组织的需求，会将符合您要求的点击发送到专用于接收排除数据的其他报表包。 VISTA规则通常针对IP地址使用，但不限于此IP地址。 您可以使用任何维度在报表包中包含或排除数据。 VISTA规则可能会产生额外成本；请联系您的Adobe客户团队以了解详情。
* **选择退出Cookie**：您网站的所有访客都可以通过访问特定于您的跟踪服务器的页面来自愿选择退出Adobe Analytics中的跟踪。 请参阅实施用户指南中的[实施选择退出链接](/help/implement/js/opt-out.md)。

>[!TIP]
>
>处理规则不能排除数据，也不能将数据发送到其他报表包。 但是，某些变量可以有条件地设置，并且区段可用于从报表中排除这些数据。

## 排除数据前收集

如果要阻止某些点击访问Analytics数据收集服务器，请使用[`abort`](/help/implement/vars/config-vars/abort.md)变量。 此标记可阻止发送图像请求。 对于已中止的图像请求，可计费服务器调用不会递增，因为它们不会到达Adobe数据收集服务器。
