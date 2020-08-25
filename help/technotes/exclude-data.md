---
title: 排除Adobe Analytics的数据
description: 了解如何排除数据收集前后的数据的各种方法。
translation-type: tm+mt
source-git-commit: 47b14bde1bb1217bcb172c6d4f01d68f917d44db
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 0%

---


# 排除Adobe Analytics的数据

排除数据通常用于防止组织的测试工作填充生产数据，或防止不需要的数据虚报报告。 根据您的用例，使用以下任意方法从Adobe Analytics排除数据。

## 排除数据后期数据收集

以下方法是在Adobe数据收集服务器收到图像请求后，在Analytics报告中排除数据的方法。 使用这些方法排除的数据仍计入可计费服务器调用。

* **按IP排除**:Adobe Analytics提供基本功能，用于排除报表包中IP地址或范围的数据。 请参 [阅《管理员](/help/admin/admin/exclude-ip.md) 》用户指南中的“按IP排除”。
* **机器人规则**:机器人规则从已知的机器人用户代理字符串获取流量，并从Analytics报告中排除它们。 通过机器人规则排除的数据将放置在“机器人”报告中。 可以创建自定义机器人规则以排除其他数据。 See [Bot Rules](/help/admin/admin/bot-removal/bot-rules.md) in the Admin user guide.
* **VISTA规则**:根据您组织的需求，与您的要求相符的点击量会发送到另一个专门用于接收被排除数据的报表包。 VISTA规则通常用于IP地址，但不限于这些规则。 您可以使用任何维在报表包中包含或排除数据。 VISTA规则需要支付额外费用；有关详细信息，请与贵组织的客户经理联系。
* **选择退出Cookie**:访问您的跟踪服务器选择退出特定的页面，即可自愿在Adobe Analytics跟踪您网站的所有访客。 请参 [阅实施用户指南](/help/implement/js/opt-out.md) 中的实施退出链接。

>[!TIP]
>
>处理规则不能排除数据或将数据发送到另一个报表包。 但是，可以有条件地设置某些变量，并且可以使用区段从报告中排除该数据。

## 排除数据预数据收集

如果要阻止某些点击到达Analytics数据收集服务器，请使用该 [`abort`](/help/implement/vars/config-vars/abort.md) 变量。 此标志阻止发送图像请求。 对于中止的图像请求，收费服务器调用不会增加，因为它们无法到达Adobe数据收集服务器。
