---
title: 维度概述
description: 了解什么是维度，以及它们在 Adobe Analytics 中如何使用。
feature: Dimensions
exl-id: dc00e06a-fdb5-40e3-82e2-269bad3b3677
TQID: https://experienceleague.adobe.com/WypIneraYlrSyIpXv3UQWIFn42A-Dxi0SxeJ2VbeubQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 436
ht-degree: 37%

---

# 维度概述

维度是 Adobe Analytics 中的变量，它通常包含字符串值。 常见维度包括[页面](page.md)、[反向链接域](referring-domain.md)或 [eVar](evar.md)。 相反，[量度](../metrics/overview.md)包含与维度相关的数字值。 基本报告根据数值列（量度）显示字符串值的行（维度）。

例如，如果将&#x200B;**[!UICONTROL 页面]**&#x200B;维度与&#x200B;**[!UICONTROL 访问量]**&#x200B;量度相结合，您将获得一个显示最常访问的页面的排名报告：

| 页面 | 访问次数 |
| --- | ---: |
| 主页 | 800 |
| 产品页面 | 500 |
| 购买页面 | 100 |

{style="table-layout:fixed"}

每个维度表示网站的不同部分或方面。 您可以将其中一个或多个维度与一个或多个量度组合在一起，创建所需的报告。

## 添加维度描述

Analytics 管理员可以在“报告包”中或直接在 Analysis Workspace 中添加维度和其他组件的描述。 有关如何向维度添加描述的信息，请参阅[添加组件描述](/help/analyze/analysis-workspace/components/add-component-descriptions.md)。

## 已弃用的维度

以下维度已停用。 大部分报表都是Analysis Workspace中不可用的Reports &amp; Analytics报表。 如果您在旧版报表或历史数据中遇到这些问题，可在此处记录这些问题以供参考。

* **层次结构**：自定义维度(`hier1`-`hier5`)，用于捕获报表的网站层次结构。 该功能已停用，在Analysis Workspace中不可用。 请改用[eVar](evar.md)和分类。
* **主页**：指示当前页面是否为访客浏览器主页的标志。 它是一个旧版维度，由于现代浏览器隐私惯例，没有现代等效项。
* **JavaScript支持**：指示访客的浏览器是否支持JavaScript。 对于现代测量不再有意义的旧版维度。
* **JavaScript版本**：报告访客浏览器支持的JavaScript版本。 不再收集的旧版维度。
* **下一页**：一个路径维度，显示访客查看的下一页。 对Analysis Workspace中的当前路径维度使用[流量可视化图表](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)。
* **上一页**：一个路径维度，显示访客查看的上一页。 对Analysis Workspace中的当前路径维度使用[流量可视化图表](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)。
* **时区**：访客的时区，派生自AppMeasurement图像请求中的时间戳偏移。 Web SDK使用[`placeContext`](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/commands/configure/context)收集时区。
* **顶级域**：访客访问点的顶级域。 旧版Reports &amp; Analytics报表；请改用[域](domain.md)维度。
* **访问页码**：访问中的页码。 旧版Reports &amp; Analytics报表；请改用[点击深度](hit-depth.md)维度。
* **访客状态**：从`s.state`变量报告了美国的状态。 已弃用，改用使用地域划分的[美国州](us-states.md)维度。
