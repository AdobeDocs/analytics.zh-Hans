---
title: 在Adobe Analytics中排除数据
description: 了解有关如何排除数据收集前后的数据的各种方法。
exl-id: dee5bf3b-8bb3-48eb-908d-b4a981f17bfb
source-git-commit: a17297af84e1f5e7fe61f886eb3906c462229087
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 0%

---

# 在Adobe Analytics中排除数据

排除数据通常用于阻止贵组织的测试工作填充生产数据，或防止不需要的数据虚增报表。 根据您的用例，使用以下任一方法从Adobe Analytics中排除数据。

## 排除数据收集后的数据

以下方法是在Adobe数据收集服务器收到图像请求后，在Analytics报表中排除数据的方法。 使用这些方法排除的数据仍会计入可计费服务器调用。

* **按IP排除**:Adobe Analytics提供了在报表包中排除IP地址或范围数据的基本功能。 请参阅 [按IP排除](/help/admin/admin/exclude-ip.md) 管理用户指南中的。
* **机器人规则**:机器人规则从已知机器人用户代理字符串中获取流量，并从Analytics报表中排除这些流量。 通过机器人规则排除的数据会放置在机器人报表中。 可以创建自定义机器人规则以排除其他数据。 请参阅 [机器人规则](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md) 管理用户指南中的。
* **VISTA规则**:根据贵组织的需求，将符合您要求的点击发送到另一个专门用于接收排除数据的报表包。 VISTA规则通常用于IP地址，但不限于这些规则。 您可以使用任何维度在报表包中包含或排除数据。 VISTA规则需要支付额外费用；有关详细信息，请联系贵组织的客户经理。
* **禁用Cookie**:您网站的所有访客都可以通过访问特定于跟踪服务器的页面，自愿选择退出在Adobe Analytics中进行跟踪。 请参阅 [实施选择退出链接](/help/implement/js/opt-out.md) 中的。

>[!TIP]
>
>处理规则无法排除数据或将数据发送到其他报表包。 但是，某些变量可以有条件地设置，并且可以使用区段从报表中排除该数据。

## 排除数据预数据收集

如果要阻止某些点击到达Analytics数据收集服务器，请使用 [`abort`](/help/implement/vars/config-vars/abort.md) 变量。 此标记可阻止发送图像请求。 对于中止的图像请求，计费服务器调用不会递增，因为它们未到达Adobe数据收集服务器。
