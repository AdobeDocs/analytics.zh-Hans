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
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
    internal-label: Admin Tools
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: ca917b867cd84b09b899ce7b72586f0b15003106
workflow-type: tm+mt
source-wordcount: '1726'
ht-degree: 25%
---
# 转化变量 (eVar)

Custom Insight转化变量（或eVar）会放置在网站所选网页的Adobe代码中。 其主要目的是在自定义市场营销报告中划分转化成功量度区段。 eVar可以基于访问，其功能与Cookie类似。 在预先设定的一段时间内，传递到 eVar 变量的值将始终“跟随”着用户。

**[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 报表包]** > **[!UICONTROL 编辑设置]** > **[!UICONTROL 转化]** > **[!UICONTROL 转化变量]**

## 转化变量 (eVar) 概述

有关转化变量的视频概述，请参阅Analytics教程指南中的[转化变量简介](https://experienceleague.adobe.com/zh-hans/docs/analytics-learn/tutorials/analysis-workspace/dimensions/introduction-to-conversion-variables-evars)。

当eVar设置为访客的值时，Adobe会自动记住该值，直到它过期为止。 eVar 值有效期间，访客遇到的任何成功事件将计入该 eVar 值。

eVar最适合用于衡量原因和结果，例如：

* 哪些内部活动影响了收入
* 最终导致注册的横幅广告
* 订单前使用内部搜索的次数

如果需要流量测量或路径，则建议使用流量变量。

>[!NOTE]
>
>在图像请求中，一个 eVar 中只能存储一个值。 如果eVar值中需要多个值，请使用[列表变量](/help/implement/vars/page-vars/page-variables.md)。

### 转化变量 - 描述 {#section_7C317BB0287A4B8EB0A1A4ECC40627BF}

| 元素 | 描述 |
| --- | --- |
| [!UICONTROL 状态] | 确定eVar是否处于活动状态：<ul><li>**[!UICONTROL 已启用]**： eVar处于活动状态。</li><li>**[!UICONTROL 已禁用]**：禁用eVar并将其从转化变量列表中删除。</li></ul> |
| [!UICONTROL 描述] | eVar的可选描述。 使用它来记录eVar捕获的内容及其实施方式。 |
| [!UICONTROL 名称] | 转化变量的友好维度名称。 这是常规报表中引用eVar的方式。 |
| [!UICONTROL 分配] | 确定变量在事件之前收到多个值时，Analytics 如何分配成功事件的点数。 支持的值包括：<ul><li>**[!UICONTROL 最近（最后一个）]**：始终由最后一个eVar值接收成功事件的信用，直至该eVar过期。</li><li>**[!UICONTROL 原始值（第一个）]**：始终由第一个eVar接收成功事件的信用，直至该eVar过期。</li><li>**[!UICONTROL 线性]**：对所有 eVar 值平均分配成功事件。 由于线性分配仅在访问内分配值，因此请将eVar到期时间设置为访问或更短时间的线性分配。 此选项不适用于推销eVar。</li></ul>**重要信息**： Adobe建议不要切换到[!UICONTROL 线性]分配，或从中切换到，因为它会在报表中隐藏历史数据，直到您切换回为止。 要更改具有大量历史记录的eVar上的分配，Adobe建议改用新的eVar。 |
| [!UICONTROL 过期时间] | 指定eVar值何时过期（不再接收成功事件的信用）。 如果在 eVar 过期之后发生成功事件，则由“无”值接收该事件的信用（不激活任何 eVar）。 支持的值包括：<ul><li>**[!UICONTROL 访问]**：该值将在访问结束时过期。</li><li>**[!UICONTROL 点击]**：该值仅适用于设置它的点击。</li><li>**[!UICONTROL Minute]**、**[!UICONTROL Hour]**、**[!UICONTROL Day]**、**[!UICONTROL Week]**、**[!UICONTROL Month]**、**[!UICONTROL Quarter]**&#x200B;或&#x200B;**[!UICONTROL Year]**：该值在设置后的一定时间内过期，截止时间为秒：<ul><li>分钟= 60秒</li><li>小时= 3600秒（60分钟）</li><li>日= 86400秒（24小时）</li><li>周= 604800秒（7天）</li><li>月= 2678400秒（31天）</li><li>季度= 8035200秒（93天 — 31天中的3个月）</li><li>年份= 31536000秒（365天）</li></ul>例如，如果eVar设置为星期一上午7:15，[!UICONTROL 天]的过期时间于星期二上午7:15结束，[!UICONTROL 周]的过期时间于下星期一上午7:15结束，[!UICONTROL 月]的过期时间于31天后上午7:15结束。</li><li>**[!UICONTROL 自定义]**：该值将在您输入的天数（每天86400秒）后过期。</li><li>**事件** （[!UICONTROL 购买]、[!UICONTROL 产品查看]、[!UICONTROL 购物车打开]、[!UICONTROL 购物车结帐]、[!UICONTROL 购物车添加]、[!UICONTROL 购物车删除]、[!UICONTROL 购物车查看]或自定义事件）：值将在所选事件发生时过期。 如果事件从未发生，则值永不过期。</li><li>**[!UICONTROL 从不]**：只要访客使用相同的标识符，eVar和事件之间就可以经过任意长的时间。</li></ul> |
| [!UICONTROL Type] | 变量值类型：<ul><li>**[!UICONTROL 文本字符串]**：捕获文本值。 它是eVar最常见的类型，也是默认设置。 它的作用与其他变量类似，其中的值是静态文本字符串。 如果跟踪内部营销活动或内部搜索关键词等，则建议使用此设置。</li><li>**[!UICONTROL 计数器]**：计算在成功事件之前某个动作的发生次数。 例如，您可以计算在成功事件之前执行的搜索次数，而不管使用的搜索词如何。</li></ul> |
| [!UICONTROL 重置] | 保存后，将立即过期所有访客中此变量的所有服务器端保留值，包括促销产品捆绑。 重新利用eVar时使用[!UICONTROL 重置]，这样您就不会在新报表中混合使用旧值。 **重置不会擦除历史数据。** |
| [!UICONTROL 启用促销] | 支持的值包括：<ul><li>**[!UICONTROL 已禁用]**： eVar将成功事件归因于访客仍然存在的值。</li><li>**[!UICONTROL 已启用]**： eVar将成为一个将值捆绑到单个产品的推销eVar。 每个产品的成功事件将计入捆绑到该产品的值。 启用促销会显示[!UICONTROL 促销]和[!UICONTROL 促销捆绑事件]设置，并删除[!UICONTROL 线性]分配。</li></ul>仅对描述如何发现或购买产品的eVar启用推销。 推销eVar不再归功于未与产品关联的成功事件。 请参阅[eVar（推销）](/help/components/dimensions/evar-merchandising.md)。 |
| [!UICONTROL 促销] | 确定捆绑到产品的值来自何处：<ul><li>**[!UICONTROL 产品语法]**：该值在`products`变量中的每个产品上设置，并在该点击上绑定到该产品。 每个产品可以具有不同的值。 未使用捆绑事件，因此[!UICONTROL 促销捆绑事件]已禁用。</li><li>**[!UICONTROL 转化变量语法]**：该值在eVar本身中设置，并作为暂存值保留，始终反映发送的最新值，而不考虑[!UICONTROL 分配]。 仅当点击包含选定的[!UICONTROL 促销捆绑事件]时，该值才会捆绑到该点击上的产品。 该点击上的每个产品都会收到相同的值。</li></ul>更改此设置而不相应地更新实施会导致数据丢失。 有关实现详细信息，请参阅[eVar （促销变量）](/help/implement/vars/page-vars/evar-merchandising.md)。 |
| [!UICONTROL 促销捆绑事件] | 仅当[!UICONTROL 促销]设置为[!UICONTROL 转化变量语法]时可用。 确定哪些事件或eVar会将eVar的暂存值捆绑到同一点击中的产品。 如果不选择捆绑事件，则使用[!UICONTROL 所有]。 支持的值包括：<ul><li>**[!UICONTROL All]**：点击触发器绑定上的任何其他事件或eVar。 此设置是默认设置。</li><li>**[!UICONTROL 购买事件]**、**[!UICONTROL 产品查看事件]**、**[!UICONTROL 购物车打开事件]**、**[!UICONTROL 购物车结账事件]**、**[!UICONTROL 购物车添加事件]**、**[!UICONTROL 购物车删除事件]**&#x200B;或&#x200B;**[!UICONTROL 购物车查看事件]**：包含所选事件的点击发生绑定。</li><li>**[!UICONTROL 促销活动事件]**：绑定发生在包含[跟踪代码](/help/components/dimensions/tracking-code.md)维度（[`campaign`](/help/implement/vars/page-vars/campaign.md)变量）的实例的点击上。</li><li>**自定义事件**：绑定发生在包含所选自定义事件的点击上。</li><li>**自定义eVar**：在设置所选eVar的点击上发生绑定。</li></ul>Prop无法触发绑定。 通过按住ctrl (Windows)或cmd (Mac)并单击列表中的多个项目来选择多个值。 当已绑定到eVar的特定产品收到与同一eVar的另一个绑定时，[!UICONTROL 分配]将确定保留哪个值。 |

### 有效期限

`eVars` 会在指定的时间段后过期。 eVar过期后，将不再接收成功事件的信用。 eVar也可以配置为在成功事件时过期。 例如，如果您的内部促销在访问结束时过期，则内部促销将仅接收在激活其访问期间发生的购买或注册的点数。

有两种方式可使eVar过期：

* 您可以将eVar设置为在指定的时间段或事件后过期。
* 您可以通过重置eVar来强制使其过期，在重新利用变量时这非常有用。

例如，如果将 eVar 的过期时间从 30 天更改为 90 天，则收集的 eVar 值将在设置的新过期期间（在此例中为 90 天）内继续保留。 系统只查看所收集 eVar 值的当前过期设置以及最后设置时间戳来确定过期时间。 只有&#x200B;**[!UICONTROL 重置]**&#x200B;选项可以使值立即过期。

另一示例：如果 eVar 在 5 月用于反映内部促销活动，并且在 21 天后过期，而在 6 月，又要使用它来捕获内部搜索关键词。在这种情况下，您应当在 6 月 1 日强制该变量过期，或重置该变量。 这样做有助于从 6 月的报告中排除内部促销值。

### 区分大小写

eVar 不区分大小写。 报告中使用的大写或小写取决于后端系统记录的第一个值。 此值可能是第一次出现，也可能在某个时段（例如每月）发生变化，具体取决于与报告包关联的数据的种类和数量。

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
