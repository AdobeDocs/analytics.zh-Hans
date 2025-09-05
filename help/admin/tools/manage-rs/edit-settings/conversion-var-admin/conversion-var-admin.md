---
description: “自定义分析转化变量”（或 eVar）置于您网站所选网页的 Adobe 代码中。其主要目的是在自定义市场营销报告中划分转化成功量度区段。eVar 可以是基于访问的，其功能与 Cookie 类似。在预先设定的一段时间内，传递到 eVar 变量的值将始终“跟随”着用户。
keywords: eVar
title: 转化变量 (eVar)
feature: Admin Tools
role: Admin
exl-id: 822ecaff-a06c-42e1-aee8-ef4a43df4230
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '1720'
ht-degree: 94%

---

# 转化变量 (eVar)

“自定义分析转化变量”（或 eVar）置于您网站所选网页的 Adobe 代码中。其主要目的是在自定义市场营销报告中划分转化成功量度区段。eVar 可以是基于访问的，其功能与 Cookie 类似。在预先设定的一段时间内，传递到 eVar 变量的值将始终“跟随”着用户。

**[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 报表包]** > **[!UICONTROL 编辑设置]** > **[!UICONTROL 转化]** > **[!UICONTROL 转化变量]**

## 转化变量 (eVar) 概述

有关转化变量的视频概述，请参阅Analytics教程指南中的[转化变量简介](https://experienceleague.adobe.com/zh-hans/docs/analytics-learn/tutorials/analysis-workspace/dimensions/introduction-to-conversion-variables-evars)。

为访客设置 eVar 值之后，Adobe 会自动记住该值，直到它过期。eVar 值有效期间，访客遇到的任何成功事件将计入该 eVar 值。

eVar 最适合用于度量原因和影响，例如：

* 哪些内部促销活动会影响收入
* 哪些横幅广告最终会导致用户注册
* 在下订单前所用的内部搜索次数

如果需要进行流量测量或路径分析，则建议您使用流量变量。

>[!NOTE]
>
>在图像请求中，一个 eVar 中只能存储一个值。如果一个 eVar 值中需要多个值，我们建议您实施[列表变量 (list vars)](/help/implement/vars/page-vars/page-variables.md)。

### 转化变量 - 描述 {#section_7C317BB0287A4B8EB0A1A4ECC40627BF}

[编辑转化变量](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md)时所用字段的描述。

| 元素 | 描述 |
| --- | --- |
| [!UICONTROL 名称] | 转化变量的易记名称。此名称是常规报告引用 eVar 时所用的名称，并且该名称将是左侧菜单中报告/维度的名称。 |
| [!UICONTROL 类型]（仅限 eVar） | 变量值类型：<ul><li>**[!UICONTROL 文本字符串]**：捕获您网站上使用的文本值。这是 eVar 最常见的类型，并且是默认设置。它与其他变量类似，其值是静态文本字符串。如果您要跟踪内部促销活动或内部搜索关键词等内容，则这是推荐的设置。</li><li>**[!UICONTROL 计数器]**：计算在成功事件之前某个动作的发生次数。例如，如果使用 eVar 跟踪网站上的内部搜索，则将此值设置为[!UICONTROL 文本字符串]以跟踪搜索词的使用。将此值设置为[!UICONTROL 计数器]可累计搜索的次数，与使用的搜索词无关。例如，您可以使用计数器 eVar 来跟踪某人在进行购买前所用内部搜索的次数。</li></ul> |
| [!UICONTROL 分配] | 确定变量在事件之前收到多个值时，Analytics 如何分配成功事件的点数。支持的值包括：<ul><li>**[!UICONTROL 最近]**：始终由最后一个 eVar 值接收成功事件的信用，直至该 eVar 过期。</li><li>**[!UICONTROL 原始值]**：始终由第一个 eVar 接收成功事件的信用，直至该 eVar 过期。</li><li>**[!UICONTROL 线性]**：对所有 eVar 值平均分配成功事件。由于线性分配实际仅能在一次访问内分配值，所以应将线性分配与 eVar 访问过期结合使用。</li></ul> **注意**：将分配切换至线性或从线性切换分配可防止显示历史数据。在报告界面中混合多种分配类型可导致在报告中错报数据。例如，线性分配可能会在大量不同的 eVar 值间划分收入。更改回最近分配后，100% 的收入都与最近单个值关联。这种关联可能会导致用户得出不正确的结论。<br><br>为避免在报告中可能产生混淆，Adobe Analytics 在界面中不显示历史数据。虽然您不该只是为了访问历史数据而更改 eVar 分配设置，但如果您确定要将给定的 eVar 更改回初始分配设置，则可以查看历史数据。已记录的数据需要新的分配设置时，Adobe 建议使用新的 eVar，而非更改已积累大量历史数据的 eVar 的分配设置。 |
| [!UICONTROL 过期时间] | 指定一个时段或事件，eVar 值将在此时段或事件之后过期（即，不再接收成功事件的信用）。如果在 eVar 过期之后发生成功事件，则由“无”值接收该事件的信用（不激活任何 eVar）。如果选择某个事件作为过期值，则变量仅在该事件发生时过期。如果未发生该事件，则变量从不过期。可用的过期选项可分为四个主要类别：<ul><li>**在页面查看或访问级别。**&#x200B;页面查看或访问以外的转化事件与 eVar 无关联。</li><li>**基于时段，例如日、周、月或年。**&#x200B;指定时段以外的转化事件与 eVar 无关联。过期时段从设置变量后开始。eVar 根据为其设置的时间而过期，该时间的单位为秒（分钟、小时、天、月，等等）： <ul><li>MINUTE=60 秒</li><li>HOUR=3600 秒（60 分钟）</li><li>DAY=86400 秒（24 小时）</li><li>WEEK=604800 秒（7 天）</li><li>MONTH=2678400 秒（31 天）</li><li>QUARTER=8035200 秒（93 天 - 3 个月，每个月 31 天）</li><li>YEAR=31536000 秒（365 天）</li><br>如果访问从星期一上午7:00开始，并在该访问期间于上午7:15设置了eVar，则过期时间如下所示：<li>天过期： eVar将于星期二上午7:15过期。</li><li>周过期：eVar将于下周一早上7:15过期。</li><li>月份过期：eVar将于星期一后第31天早上7:15过期。</li></ul><li>**特定转化事件。**&#x200B;在指定的特定事件之后触发的任何其他转化事件与 eVar 相关联。</li><li>**从不。**&#x200B;只要 visitorID Cookie 保持不变，eVar 与事件之间可以经过任意长的时间。</li></ul> |
| [!UICONTROL 状态]（仅限 eVar） | 定义 [!UICONTROL eVar] 状态：<ul><li>**禁用**：禁用 [!UICONTROL eVar]。从转化变量列表中删除 [!UICONTROL eVar]。</li><li>**无子关系**：阻止您根据维度划分 [!UICONTROL eVar]。</li><li>**基本子关系**：可让您根据任何完整维度（例如“产品”或“营销活动”）来划分 eVar。</li></ul> |
| [!UICONTROL 重置] | 在 eVar 中重置任何现有值。在重新利用eVar时，请使用此设置，这样您就不会将旧值混合到新报表中。 重置不会擦除历史数据。 |
| [!UICONTROL 促销]（仅限 eVar） | 促销变量可遵循以下两种语法之一：<ul><li>**[!UICONTROL 产品语法]**：将 eVar 值与产品关联。**注意**：如果选择“[!UICONTROL 产品语法]”，则“[!UICONTROL 促销捆绑事件]”部分会处于禁用状态，且无法选择该部分来进行编辑。对于此语法，“[!UICONTROL 捆绑事件]”不适用。</li><li>**[!UICONTROL 转化变量语法]**：仅在发生捆绑事件时才将 eVar 与产品关联。在此情况下，您可以选择充当“[!UICONTROL 捆绑事件]”的事件。更改此设置时，如果不相应更新 JavaScript 代码，则会导致数据丢失。请参阅[促销变量](/help/components/dimensions/evar-merchandising.md)。</li></ul> |
| [!UICONTROL 促销捆绑事件]（仅限 eVar） | 如果将“促销”设置为[!UICONTROL 转化变量语法]，则所选事件会将当前 eVar 值与产品进行捆绑。要使用“[!UICONTROL 捆绑事件]”，请将“[!UICONTROL 分配]”设置为“[!UICONTROL 最近]”。 如果将“[!UICONTROL 分配]”设置为“[!UICONTROL 原始值]”，则第一个 eVar 产品捆绑将在 eVar 过期之前一直有效。通过按住 ctrl (Windows) 或 cmd (Mac) 并单击列表中的多个项目，可选择多个事件。只有在选择了“[!UICONTROL 转化变量语法]”后才能选择事件。 |

### 有效期限

`eVars` 会在指定的时间段后过期。eVar 过期后，将不再对成功事件计数。eVar 还可配置为在发生成功事件时过期。例如，如果有一个内部促销在一次访问结束时即告过期，对于此促销，将仅对该访问期间（在此期间有效）发生的购买或注册计数。

使 eVar 过期的方法有两种：

* 您可以将 eVar 设置为在指定的时间段或事件后过期。
* 您可以通过重置 eVar 强制使其过期，在重新利用变量时这非常有用。

例如，如果将 eVar 的过期时间从 30 天更改为 90 天，则收集的 eVar 值将在设置的新过期期间（在此例中为 90 天）内继续保留。系统只查看所收集 eVar 值的当前过期设置以及最后设置时间戳来确定过期时间。只有&#x200B;**[!UICONTROL 重置]**&#x200B;选项可以使值立即过期。

另一示例：如果 eVar 在 5 月用于反映内部促销活动，并且在 21 天后过期，而在 6 月，又要使用它来捕获内部搜索关键词。在这种情况下，您应当在 6 月 1 日强制该变量过期，或重置该变量。这样做有助于从 6 月的报告中排除内部促销值。

### 区分大小写

eVar 不区分大小写。报告中使用的大写或小写基于后端系统注册的第一个值。 此值可能是第一次出现，也可能在某个时段（例如每月）发生变化，具体取决于与报表包关联的数据的种类和数量。

### 计数器

eVar 最常用于保存字符串值，但也可以配置为用作计数器。在您尝试计入用户在某个事件前所执行的操作数时，使用 eVar 与计数器一样有用。例如，可以使用 eVar 捕获购买前的内部搜索数。访客每搜索一次时，eVar 包含值“+1”。如果访客在购买前搜索了四次，则将看到每个总计数的实例：1.00、2.00、3.00 和 4.00。但只有 4.00 针对购买事件（订购和收入量度）计数。只允许正数作为 eVar 计数器的值。

## 添加或编辑转化变量

1. 单击 **[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 报表包]**。
1. 选择报表包。
1. 单击&#x200B;**[!UICONTROL 编辑设置]** > **[!UICONTROL 转化]** > **[!UICONTROL 转化变量]**。
1. 在[!UICONTROL 转化变量]页面上，单击您想要修改的转化变量旁的&#x200B;**[!UICONTROL 展开]**&#x200B;图标 [+]。

   或

   单击&#x200B;**[!UICONTROL 新增]**，将未使用的 eVar 添加至报表包。
1. 选择想要修改的转化变量字段。

   请参阅[转化变量 - 描述](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md#section_7C317BB0287A4B8EB0A1A4ECC40627BF)。某些字段可让您在字段中直接键入。其他字段可从包含支持的值的下拉列表中选择。
1. 单击&#x200B;**[!UICONTROL 保存]**。
