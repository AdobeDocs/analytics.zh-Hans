---
title: Adobe Analytics 中的行为报表
description: 了解如何在 Adobe Analytics 中创建行为报表
feature: Third-party Integration
exl-id: ea441afa-e595-4ffa-b446-d67e87f8a7c9
source-git-commit: 34ba0e09cd909951a777b0ad3da080958633f97e
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 98%

---

# 行为报表

行为报表显示有关用户如何与您的网站交互的信息。

本页面假定用户具有使用 Analysis Workspace 的基本知识。如果您还不熟悉 Adobe Analytics 中的工具，请参阅[在 Analysis Workspace 中为 Google Analytics 用户创建基本报表](create-report.md)。

## 行为流量

可以使用“流量”可视化重新创建行为流量报表。

1. 单击左侧的“可视化”图标，然后将“流量”可视化拖到自由格式表上方的工作区
2. 找到&#x200B;**页面**&#x200B;维度，然后单击箭头图标以显示页面值。维度项为黄色。
3. 找到要开始使用的所需页面值，并将其拖动到中心标有“维度或项目”的位置
4. 此流量报告是交互式的。单击任意值可将流量展开到后续或之前的页面。使用右键单击菜单可展开或折叠列。此外，还可以在同一流量报告中使用不同的维度。

![流量报表](/help/technotes/ga-to-aa/assets/flow.png)

## 网站内容 - 所有页面

页面报表显示网站上各个页面的性能。

1. 在“组件”菜单中，找到&#x200B;**页面**&#x200B;维度，并将其拖动到标有“将维度放置在此处”的大型自由格式表区域。
2. 将所需的量度拖动到工作区上自动创建的&#x200B;**发生次数**&#x200B;量度旁边。有关如何获取各个量度的详细信息，请参阅[量度翻译指南](common-metrics.md)。

作为替代方法，Adobe 提供了若干个名为模板的预创建工作区。“内容使用情况 (Web)”模板可向所有页面报表提供类似的值。

1. 单击&#x200B;*[!UICONTROL 项目] > [!UICONTROL 新建]*，此时将打开一个包含项目选项的模式窗口。
2. 单击“内容使用情况 (Web)”模板，然后单击“创建”。

## 网站内容 - 内容明细

内容明细报表允许您按 URL 结构查看页面流量。需要进一步实施才能在 Analysis Workspace 中使用。Adobe 建议与实施顾问合作，以确保准确收集这些数据。

## 网站内容 - 登陆页面

登陆页面报表显示您网站上排名最前的登陆页面。登陆页面可在 Analysis Workspace 中作为&#x200B;**登入页面**&#x200B;维度使用。

1. 在“组件”菜单中，找到&#x200B;**登入页面**&#x200B;维度，并将其拖动到标有“在此处放置维度”的大型自由格式表区域。
2. 将所需的量度拖动到工作区上自动创建的&#x200B;**发生次数**&#x200B;量度旁边。有关如何获取各个量度的详细信息，请参阅[量度翻译指南](common-metrics.md)。

Adobe 建议对此维度使用&#x200B;**访问次数**&#x200B;量度。

## 网站内容 - 退出页面

退出页面报表显示成为个人访问最后一页的排名最前的页面。该报表可在 Analysis Workspace 中以相同的名称使用。

1. 在“组件”菜单中，找到&#x200B;**退出页面**&#x200B;维度，并将其拖动到标有“在此处放置维度”的大型自由格式表区域。
2. 将所需的量度拖动到工作区上自动创建的&#x200B;**发生次数**&#x200B;量度旁边。有关如何获取各个量度的详细信息，请参阅[量度翻译指南](common-metrics.md)。

Adobe 建议对此维度使用&#x200B;**访问次数**&#x200B;量度。

## 网站速度报表

网站速度报表显示页面加载速度，显示增加页面加载时间的机会。

此功能需要在两个平台上进行额外实施；Adobe 建议与实施顾问合作，以确保为 Analysis Workspace 正确配置此数据。通常将 [getPageLoadTime 插件](/help/implement/vars/plugins/getpageloadtime.md)分配给 eVar，以在 Adobe Analytics 中获取性能数据。

## 网站搜索报表

网站搜索报表提供访客如何使用网站内部搜索功能的分析。

此功能需要在两个平台上进行额外实施；Adobe 建议与实施顾问合作，以确保为 Analysis Workspace 正确配置此数据。通常，从查询字符串参数中提取内部搜索词并将其置于 eVar 中进行报告。

## 事件报表

Google 和 Adobe Analytics 中的事件存在一些主要结构性差异。这两种报表都需要进行额外实施更改才能在各自的平台上正常工作。

* 在 Google Analytics 的实施中，事件被定义为文本。事件具有类别、操作和标签。
* 在 Adobe Analytics 中，首先在 Admin Console 中设置事件，为其分配一个标识符。该标识符在实施代码中使用。例如：
   1. 您可以在 Admin Console 中将 event1 设置为“注册”。
   2. 在您的实施中，您应在注册确认页面上将 event1 包含到事件变量中。每次显示注册确认页面时，event1 都会增加。
   3. 在 Analysis Workspace 中，“注册”显示为用于任何报表的量度。

由于此功能需要实施更改，因此 Adobe 建议与实施顾问合作，以确保为 Analysis Workspace 正确配置数据。

## 发行者报表

与 Google 需要通过 Google Ad Manager 建立连接类似，Adobe 提供了一种专门的产品来提供分析，称为 Adobe Advertising Cloud。如果您的组织有兴趣使用此产品，请联系您的Adobe客户团队。
