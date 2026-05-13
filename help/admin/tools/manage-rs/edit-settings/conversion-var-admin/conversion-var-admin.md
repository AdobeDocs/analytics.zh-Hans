---
description: Custom Insight转化变量（或eVar）会放置在网站所选网页的Adobe代码中。 其主要目的是在自定义市场营销报告中划分转化成功量度区段。 eVar可以基于访问，其功能与Cookie类似。 在预先设定的一段时间内，传递到 eVar 变量的值将始终“跟随”着用户。
keywords: eVar
title: 转化变量 (eVar)
feature: Admin Tools
role: Admin
exl-id: 822ecaff-a06c-42e1-aee8-ef4a43df4230
TQID: https://experienceleague.adobe.com/rYLxVYB1oDyfEk8gQyesTSRRPHid-6zJ8QaqFG2b0Kc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 1740
ht-degree: 53%

---

# 转化变量 (eVar)

Custom Insight转化变量（或eVar）会放置在网站所选网页的Adobe代码中。 其主要目的是在自定义市场营销报告中划分转化成功量度区段。 eVar可以基于访问，其功能与Cookie类似。 在预先设定的一段时间内，传递到 eVar 变量的值将始终“跟随”着用户。

**[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 报表包]** > **[!UICONTROL 编辑设置]** > **[!UICONTROL 转化]** > **[!UICONTROL 转化变量]**

## 转化变量 (eVar) 概述

有关转化变量的视频概述，请参阅Analytics教程指南中的[转化变量简介](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/dimensions/introduction-to-conversion-variables-evars)。

当eVar设置为访客的值时，Adobe会自动记住该值，直到它过期为止。 eVar 值有效期间，访客遇到的任何成功事件将计入该 eVar 值。

eVar最适合用于衡量原因和结果，例如：

* 哪些内部活动影响了收入
* 最终导致注册的横幅广告
* 订单前使用内部搜索的次数

如果需要流量测量或路径，则建议使用流量变量。

>[!NOTE]
>
>在图像请求中，一个 eVar 中只能存储一个值。 如果一个 eVar 值中需要多个值，我们建议您实施[列表变量 (list vars)](/help/implement/vars/page-vars/page-variables.md)。

### 转化变量 - 描述 {#section_7C317BB0287A4B8EB0A1A4ECC40627BF}

[编辑转化变量](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md)时所用字段的描述。

| 元素 | 描述 |
| --- | --- |
| [!UICONTROL 名称] | 转化变量的易记名称。 此名称是常规报告引用 eVar 时所用的名称，并且该名称将是左侧菜单中报告/维度的名称。 |
| [!UICONTROL 类型]（仅限 eVar） | 变量值类型：<ul><li>**[!UICONTROL 文本字符串]**：捕获您网站上使用的文本值。 这是eVar最常见的类型，也是默认设置。 它的作用与其他变量类似，其中的值是静态文本字符串。 如果要跟踪内部营销活动或内部搜索关键词等内容，则建议使用此设置。</li><li>**[!UICONTROL 计数器]**：计算在成功事件之前某个动作的发生次数。 例如，如果使用 eVar 跟踪网站上的内部搜索，则将此值设置为[!UICONTROL 文本字符串]以跟踪搜索词的使用。 将此值设置为[!UICONTROL 计数器]可累计搜索的次数，与使用的搜索词无关。 例如，您可以使用计数器eVar来跟踪某人在购买前使用您的内部搜索的次数。</li></ul> |
| [!UICONTROL 分配] | 确定变量在事件之前收到多个值时，Analytics 如何分配成功事件的点数。 支持的值包括：<ul><li>**[!UICONTROL 最近]**：始终由最后一个 eVar 值接收成功事件的信用，直至该 eVar 过期。</li><li>**[!UICONTROL 原始值]**：始终由第一个 eVar 接收成功事件的信用，直至该 eVar 过期。</li><li>**[!UICONTROL 线性]**：对所有 eVar 值平均分配成功事件。 由于线性分配实际仅能在一次访问内分配值，所以应将线性分配与 eVar 访问过期结合使用。</li></ul> **注意**：将分配切换至线性或从线性切换分配可防止显示历史数据。 在报告界面中混合多种分配类型可导致在报告中错报数据。 例如，线性分配可能会将收入分配给多个不同的eVar值。 在改回最近分配后，该收入的100%将与最近的单个值相关联。 这种关联可能会导致用户做出错误的结论。<br><br>为避免在报告中可能产生混淆，Adobe Analytics 在界面中不显示历史数据。 如果您决定将给定的eVar更改回初始分配设置，则可以查看此项，但您不应仅为了访问历史数据而更改eVar分配设置。 Adobe建议在需要为已记录的数据设置新的分配设置时使用新的eVar，而不是在已积累大量历史数据的eVar上更改分配设置。 |
| [!UICONTROL 过期时间] | 指定一个时段或事件，eVar值将在此时段或事件之后过期（即，不再接收成功事件的信用）。 如果在 eVar 过期之后发生成功事件，则由“无”值接收该事件的信用（不激活任何 eVar）。  如果选择某个事件作为过期值，则变量仅在该事件发生时过期。 如果未发生该事件，则变量从不过期。  可用的过期选项可分为四个主要类别：<ul><li>**在页面查看或访问级别。** 页面查看或访问以外的转化事件与eVar无关联。</li><li>**基于时段，如日、周、月或年。** 指定时间段以外的转化事件与eVar无关联。 设置变量后，有效期即会开始。 eVar的过期期限从设置的时间调整到秒（分钟、小时、天、月等）： <ul><li>MINUTE=60秒</li><li>HOUR=3600秒（60分钟）</li><li>DAY=86400秒（24小时）</li><li>WEEK=604800秒（7天）</li><li>MONTH=2678400秒（31天）</li><li>QUARTER=8035200秒（93天 — 31天中的3个月）</li><li>YEAR=31536000秒（365天）</li><br>如果访问从星期一上午7:00开始，并在该访问期间于上午7:15设置了eVar，则过期时间如下所示：<li>天过期： eVar将于星期二上午7:15过期。</li><li>周过期：eVar将于下周一早上7:15过期。</li><li>月份过期：eVar将于星期一后第31天早上7:15过期。</li></ul><li>**特定转化事件。** 在指定与eVar关联的特定事件之后触发的任何其他转化事件。</li><li>**从不。** 只要访客使用相同的标识符，eVar与事件之间可以经过任意长的时间。</li></ul> |
| [!UICONTROL 状态]（仅限 eVar） | 定义 [!UICONTROL eVar] 状态：<ul><li>**禁用**：禁用 [!UICONTROL eVar]。 从转化变量列表中删除 [!UICONTROL eVar]。</li><li>**无子关系**：阻止您根据维度划分 [!UICONTROL eVar]。</li><li>**基本子关系**：可让您根据任何完整维度（例如“产品”或“营销活动”）来划分 eVar。</li></ul> |
| [!UICONTROL 重置] | 在 eVar 中重置任何现有值。 在重新利用eVar时，请使用此设置，这样您就不会将旧值混合到新报表中。 重置不会擦除历史数据。 |
| [!UICONTROL 促销]（仅限 eVar） | 促销变量可遵循以下两种语法之一：<ul><li>**[!UICONTROL 产品语法]**：将 eVar 值与产品关联。 **注意**：如果选择“[!UICONTROL 产品语法]”，则“[!UICONTROL 促销捆绑事件]”部分会处于禁用状态，且无法选择该部分来进行编辑。 对于此语法，“[!UICONTROL 捆绑事件]”不适用。</li><li>**[!UICONTROL 转化变量语法]**：仅在发生捆绑事件时才将 eVar 与产品关联。 在此情况下，您可以选择充当“[!UICONTROL 捆绑事件]”的事件。  更改此设置时，如果不相应更新 JavaScript 代码，则会导致数据丢失。 请参阅[促销变量](/help/components/dimensions/evar-merchandising.md)。</li></ul> |
| [!UICONTROL 促销捆绑事件]（仅限 eVar） | 如果将“促销”设置为[!UICONTROL 转化变量语法]，则所选事件会将当前 eVar 值与产品进行捆绑。 要使用“[!UICONTROL 捆绑事件]”，请将“[!UICONTROL 分配]”设置为“[!UICONTROL 最近]”。 如果将“[!UICONTROL 分配]”设置为“[!UICONTROL 原始值]”，则第一个 eVar 产品捆绑将在 eVar 过期之前一直有效。 通过按住 ctrl (Windows) 或 cmd (Mac) 并单击列表中的多个项目，可选择多个事件。 只有在选择了“[!UICONTROL 转化变量语法]”后才能选择事件。 |

### 有效期限

`eVars` 会在指定的时间段后过期。 eVar过期后，将不再接收成功事件的信用。 eVar也可以配置为在成功事件时过期。 例如，如果您的内部促销在访问结束时过期，则内部促销将仅接收在激活其访问期间发生的购买或注册的点数。

有两种方式可使eVar过期：

* 您可以将eVar设置为在指定的时间段或事件后过期。
* 您可以通过重置 eVar 强制使其过期，在重新利用变量时这非常有用。

例如，如果将 eVar 的过期时间从 30 天更改为 90 天，则收集的 eVar 值将在设置的新过期期间（在此例中为 90 天）内继续保留。 系统只查看所收集 eVar 值的当前过期设置以及最后设置时间戳来确定过期时间。 只有&#x200B;**[!UICONTROL 重置]**&#x200B;选项可以使值立即过期。

另一示例：如果 eVar 在 5 月用于反映内部促销活动，并且在 21 天后过期，而在 6 月，又要使用它来捕获内部搜索关键词。在这种情况下，您应当在 6 月 1 日强制该变量过期，或重置该变量。 这样做有助于从 6 月的报告中排除内部促销值。

### 区分大小写

eVar 不区分大小写。 报告中使用的大写或小写基于后端系统注册的第一个值。 此值可能是第一次出现，也可能在某个时段（例如每月）发生变化，具体取决于与报表包关联的数据的种类和数量。

### 计数器

虽然eVar最常用于保存字符串值，但也可以将其配置为充当计数器。 当您尝试在事件之前计算用户执行的操作数时，eVar可用作计数器。 例如，您可以使用eVar捕获购买前的内部搜索次数。 每次有访客进行搜索时，eVar应包含一个值“+1”。 如果访客在购买之前进行了四次搜索，您将看到每个总数的实例：1.00、2.00、3.00和4.00。 但是，只有4.00版会获得购买事件（订单和收入量度）的点数。 仅允许正数作为eVar计数器的值。

## 添加或编辑转化变量

1. 单击 **[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 报表包]**。
1. 选择报表包。
1. 单击&#x200B;**[!UICONTROL 编辑设置]** > **[!UICONTROL 转化]** > **[!UICONTROL 转化变量]**。
1. 在[!UICONTROL 转化变量]页面上，单击您想要修改的转化变量旁的&#x200B;**[!UICONTROL 展开]**&#x200B;图标 [+]。

   或

   单击&#x200B;**[!UICONTROL 新增]**，将未使用的 eVar 添加至报表包。
1. 选择想要修改的转化变量字段。

   请参阅[转化变量 — 描述](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md#section_7C317BB0287A4B8EB0A1A4ECC40627BF)。 某些字段允许您直接在字段中键入。 而其他参数则允许您从支持的值的下拉列表中选择。
1. 单击&#x200B;**[!UICONTROL 保存]**。
