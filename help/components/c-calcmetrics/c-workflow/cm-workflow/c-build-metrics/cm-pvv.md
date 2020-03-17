---
description: 显示如何生成简单的“每次访问页面查看次数”量度。
title: 构建简单的“每次访问的页面查看次数”量度
uuid: 0730e51c-1f8f-473b-8825-d72911f2944c
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 构建简单的“每次访问的页面查看次数”量度

显示如何生成简单的“每次访问页面查看次数”量度。

有关 UI 组件的详细描述，请参阅[生成量度](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md)。

下面说明了如何生成简单的“每次访问页面查看次数”量度。

1. 导航至计算量度生成器。
1. 为量度指定“每次访问页面查看次数”或类似的名称。
1. 为量度提供用户友好的&#x200B;**[!UICONTROL 描述]**，以显示其用途。
1. 选择正确的&#x200B;**[!UICONTROL 格式]**，在此例中，选择“小数”。
1. 确定您希望报表显示多少个小数位。
1. 设置量度极性。对于此量度，上升趋势是有利的（绿色）。
1. 添加&#x200B;**[!UICONTROL 标记]**&#x200B;以组织您的量度。
1. 对于此量度，首先将“页面查看次数”拖到画布中，然后再将“访问次数”拖到下方（等到出现蓝线时再放下它）。
1. 选择“除以”运算符。（“除以”是默认的运算符。）
1. 现在，当您生成量度时，即可在右上角看到该量度的&#x200B;**[!UICONTROL 预览]**。
1. 产品兼容性显示该量度是与“[当前数据](https://marketing.adobe.com/resources/help/zh_CN/reference/data_latency.html)”兼容，还是仅与“完全处理数据”兼容。
1. 单击&#x200B;**[!UICONTROL 保存]**。
1. 请注意，无论您何时对量度定义进行更改，**[!UICONTROL 概要]**&#x200B;公式都会随之发生更新。
1. 此时您会自动转到[计算量度管理器](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md)，它类似于区段管理器。它允许您共享、批准、（重新）标记、重命名或删除量度。

