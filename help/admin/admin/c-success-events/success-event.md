---
description: 成功事件是指可跟踪的活动。什么是成功事件完全由您来决定。例如，如果访客购买一件产品，则该购买事件可视为成功事件。.
keywords: event
title: 成功事件概述
topic: Admin tools
uuid: 410eee44-8960-462c-a9c3-07b44d0b1df0
translation-type: tm+mt
source-git-commit: 7a1c3c7ed0e509969e281e865e8ff2c969a18bcb

---


# 成功事件概述

成功事件是指可跟踪的活动。什么是成功事件完全由您来决定。例如，如果访客购买一件产品，则该购买事件可视为成功事件。.

访问报表包设置中的“成功事件”页面：

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your AdobeID credentials.
2. Click the 9-grid button at the top, then click [!UICONTROL Analytics].
3. Navigate to [!UICONTROL Admin] > [!UICONTROL Report Suites]
4. 选择所需的报表包，然后导航到 [!UICONTROL 编辑设置] >转 [!UICONTROL 换] > [!UICONTROL 成功事件]。
5. 找到所需的事件，并将“唯一事件录制 [!UICONTROL ”下拉列] 表修改为“每次访问录制一次 [!UICONTROL ”或“使] 用事件ID” 。

成功事件的种类有多种，具体取决于网站类型。下面是一些示例：

* **零售**：产品查看、结账、购买
* **媒体**：订阅、竞赛注册、页面查看、视频查看
* **金融**：提交申请、登录、使用自助服务工具
* **旅行**：预订（购买）、内部促销活动（点进）、搜索（行程定价）
* **电信**：购买、商机、使用自助服务工具
* **高科技**：下载白皮书、RFP、填写表单、请求支持
* **汽车**：提交商机、申请报价、下载手册

成功事件是由 [s.events](https://marketing.adobe.com/resources/help/zh_CN/sc/implement/events.html) 变量来定义。

## 成功事件页面 - 描述 {#section_681ECEC981694CABBDBF00E18165B447}

**[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 报表包]** > **[!UICONTROL 编辑设置]** > **[!UICONTROL 转化]** > **[!UICONTROL 成功事件]**

使用“成功事件”页面可配置您网站上使用的事件变量。您可以添加多达 1,000 个成功事件。事件 81-1,000 仅在 H22 代码或更高版本的代码中才可用。

| 元素 | 描述 |
|--- |--- |
| Event | 事件的原始名称。 |
| 名称 | 为您的网站上使用的成功事件取一个有意义的名称。例如，如果 event1 用于跟踪注册，则在此处更改名称，使 event1 在所有转化报表中都表示为“注册”量度。 |
| 类型 | 所选类型确定事件是计数器（标准）、量度还是货币事件。数值和货币事件允许您以大于 1 的增量增加量度。计数器事件用于及时记录事件，而货币事件则记录小数，例如税款或运输费用。传递给货币事件的值在收到后将从页面货币换算为报表包的基本货币。有关使用货币事件的详细信息，请与 Adobe 代表联系。数值事件用于报告非货币数字，例如订单中使用的优惠券数量。货币事件用于跟踪税款和运输费用。在“标准”类型的“数据源”中使用的事件必须是数值事件或货币事件。 |
| 极性 | 量度极性允许您指示 Adobe Analytics 将给定自定义事件（量度）上升的情况视为好还是坏。它允许 Adobe Analytics 显示各种量度的方向指示器（箭头）以添加上下文（例如，逐周比较）。示例：如果“提交的错误数”呈逐周上升趋势，Adobe Analytics 应将这种情况视为好还是坏？“电子邮件注册数”的上升可能是好的。但“表单提交错误数”的上升可能是坏的。在 Analysis Workspace 中，极性可应用于以下对象：自由格式表的条件格式、“概要变化”可视化图表，及地图可视化的“反差”颜色方案。 |
| 描述 | 有关事件目的和用法的简要描述。 |
| 独特事件记录 | **每次访问录制一次**:将特定事件与访客会议联系起来。 忽略同一访问中给定事件的后续计数。 此类事件序列化不需要任何实施更改。<br>**使用事件ID **:将给定事件绑定到自定义ID。 忽略对具有相同事件ID的给定事件的后续计数。 此类事件序列化要求点击中的自定义ID来消除重复值。 See[Event ID serialization](../../../implement/vars/page-vars/events/event-serialization.md)in the Implement user guide. |
| 参与率 | 请参阅[参与率量度](/help/components/c-variables/c-metrics/metrics-participation.md)。 |
| 警告（货币事件） | 将事件类型更改为货币事件，或将货币事件更改为其他事件类型时，将显示一则消息，声明历史数据在报表中不可用。不同事件类型使用单独的数据表格，并且无法同时使用。如果用户还原事件类型，则可以恢复一些历史数据。但是，初始更改后收集的任何数据都将不可用。更改事件类型时，请务必要小心谨慎。 |

