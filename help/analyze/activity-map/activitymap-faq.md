---
description: 有关在 Activity Map 中设置、配置和部署功能的常见问题解答。
title: Activity Map 常见问题解答
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
feature: Activity Map
role: User, Admin
exl-id: 6b2767cb-6c2c-4bf3-b9a9-a23418624650
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 98%

---

# Activity Map 常见问题解答

有关在 Activity Map 中设置、配置和部署功能的常见问题解答。

+++是否所有 Analytics 客户都可以访问管理工具的“Activity Map 启用”页面？具有 Adobe Analytics Standard、Premium 和 Ultimate 合同的组织可以访问 Activity Map。
+++

+++Activity Map 如何支持单页面应用程序 (SPA)？每隔几秒，Activity Map 扫描网页，查看对页面的更改。ActivityMap 查找页面上的新内容而无需加载新页面，但此新内容始终归因于在加载页面时找到的第一个 pageName。

* Activity Map 检查以确定它知道的链接的可见性是否发生了更改。如果发现了可见性的更改，则“页面上的链接”表上该链接的“现在”列将使用[!UICONTROL 已显示]或[!UICONTROL 已隐藏]更新。

* 当用户的交互创建新内容时，AppMeasurement 发现的任何作为链接的新元素将添加到[!UICONTROL 页面上的链接]表中。Activity Map 发送包括这些新链接的新数据请求。当 UI 处理数据请求时，新链接应显示在[!UICONTROL 页面上的链接]表中。
+++

+++Activity Map 是否提供有关“查看数”的数据？否，Adobe 不跟踪所查看的链接。
+++

+++Activity Map 支持什么浏览器和版本？Activity Map 支持大多数现代浏览器的最新版本。
+++

+++Activity Map 是否会增加服务器调用数？Activity Map 本身不会发送服务器调用。相反，Activity Map 上下文数据变量包括在后续页面上的 Analytics 页面查看调用中。
+++

+++为什么有些已排名项叠加会缺失？页面中会隐藏一些排名链接，例如子菜单链接。因此，其对应的链接叠加也不显示。排名的计算针对页面上的所有链接，包括隐藏链接。
+++

+++在“所有链接”报告中如何确定链接排名？**
* **在梯度和气泡模式中**：排名由量度列决定。对于量度值相同的链接而言，其排名由链接 ID 的字母顺序进一步确定。
* **在获胜方和失败方模式中**：排名主要由“增益百分比”列决定。对于具有相同增益的链接而言，其排名由链接 ID 的字母顺序进一步确定。
+++

+++Activity Map 如何与使用多个报告包的页面配合使用？默认情况下，Activity Map 使用与页面发送的第一个标记关联的报告包。您可以通过 **[!UICONTROL Activity Map 设置]** > **[!UICONTROL 其他]**选项卡，选择带有标记的其他报告包。
+++

+++Activity Map 多长时间在页面上扫描一次 Adobe Analytics？Activity map 在页面完成事件后最多 20 秒扫描是否存在 Adobe Analytics。
+++

+++Activity Map 如何处理动态内容？Activity Map 每两秒检查一次是否发现网页的状态有更改，例如：

* HTML 内容变为可见
* 隐藏了 HTML 内容
* 插入了新的 HTML 内容

如果隐藏或显示了内容，该应用程序则会自动将受影响的链接状态（以及因此形成的叠加图）从“隐藏”改为“显示”或从“显示”改为“隐藏”。如果注入了新内容，应用程序会检索关联的链接、从中提取分析数据并为这些链接添加叠加图。
+++

+++页面流量报告基于什么量度？显示的所有数据基于页面查看量。
+++

+++能否通过数据馈送导出 Activity Map 上下文数据变量？是的。Activity Map 使用的[数据列](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md)是 `clickmaplink`、`clickmaplinkbyregion`、`clickmappage` 和 `clickmapregion`。
+++

+++区段在实时模式下是否可以使用？否，区段不适用于实时模式。
+++

+++Activity Map 是否与虚拟报告包兼容？是。但是，由于虚拟报告包的限制，Activity Map 的实时模式与虚拟报告包不兼容。
+++

+++如何禁用 Activity Map？您有三个选项：

* 从 JS 文件中删除 `AppMeasurement_Module_ActivityMap` 函数
* 添加使用空正文重写上述函数的自定义代码，例如：

  ```js
  function AppMeasurement_Module_ActivityMap() {}
  ```

* 通过将 `s.trackClickMap` 和 `s.trackInlineStats` 设置为 `false` 来配置 AppMeasurement
+++
