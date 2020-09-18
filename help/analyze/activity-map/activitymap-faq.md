---
description: 有关在 Activity Map 中设置、配置和部署功能的常见问题解答。
title: Activity Map 常见问题解答
topic: Activity map
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
translation-type: tm+mt
source-git-commit: ec93137d0b5334e312fe0ec42953457243117d4a
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 24%

---


# Activity Map 常见问题解答

有关在 Activity Map 中设置、配置和部署功能的常见问题解答。

## 是否所有Analytics客户都有权访问“管理工具ActivityMap启用”页？

拥有Adobe Analytics Standard、Premium和Ultimate合同的组织可以访问Activity Map。

## Activity Map是否提供“视图”数据？

否，Adobe不会跟踪已查看的链接。

## Activity Map支持哪些浏览器和版本？

Activity Map支持最新版本的最新浏览器。

## Activity Map会增加服务器调用吗？

Activity Map本身不发送服务器调用。 相反，Activity Map上下文数据变量会包含在后续页面上的分析页面视图调用中。

## 为什么缺少某些排名项叠加？**

某些排名链接（如子菜单链接）在页面中处于隐藏状态。 因此，不显示其相应的链接叠加。 会为页面上的所有链接（包括隐藏的链接）计算排名。

## 链接等级如何在“所有链接”报告中确定？**

* **在渐变和气泡模式下**:排名由度量列确定。 对于量度值相同的链接而言，其排名由链接 ID 的字母顺序进一步确定。
* **在“Gainer &amp; Loser”模式下**:排名主要由%增益列确定。 对于增益相同的链接，其排名会进一步基于链接ID的字母顺序。

## Activity Map如何处理使用多个报表包的页面？

默认情况下，Activity Map使用与页面发送的第一个标记关联的报表包。 您可以通过&#x200B;**[!UICONTROL Activity Map 设置]** > **[!UICONTROL 其他]**&#x200B;选项卡，选择带有标签的其他报表包。

## Activity Map在页面上扫描多长时间？

活动图在完成页面事件后扫描Adobe Analytics是否存在最多20秒。

## Activity Map如何处理动态内容？

Activity Map每2秒检查一次，以查看它是否在网页状态中发现了更改，例如：

* HTML 内容变为可见
* 隐藏了 HTML 内容
* 插入了新的 HTML 内容

如果隐藏或显示了内容，该应用程序则会自动将受影响的链接状态（以及因此形成的叠加图）从“隐藏”改为“显示”或从“显示”改为“隐藏”。如果插入了新内容，应用程序将检索关联的链接，为它们提取分析数据，并为这些链接添加叠加。

## 页面流报告所基于的指标是什么？

显示的所有数据均基于页面视图。

## 能否通过数据服务导出Activity Map上下文数据变量？

活动映射上下文数据变量在数据服务中不可用。

## 区段是否在实时模式下工作？

否，区段在“实时”模式下无效。 该功能与Reports &amp; Analytics中的实时报告功能相当，后者不支持细分。

## Activity Map是否与虚拟报告套件兼容？

是的。但是，由于虚拟报表包的限制，Activity Map 的实时模式与虚拟报表包不兼容。
