---
description: 显示如何生成简单的“每次访问页面查看次数”量度。
title: 构建简单的“每次访问的页面查看次数”量度
feature: Calculated Metrics
exl-id: 2d1c4677-b07c-4eca-97b7-e5e4594daee1
source-git-commit: 7722a2f01ff77dfec8ce110fd04fe977f6c627c6
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 56%

---

# 生成“每次访问的页面查看次数”量度

以下信息介绍了如何创建简单的“每次访问的页面查看次数”量度。

要构建简单的“每次访问的页面查看次数”量度，请执行以下操作：

1. 开始生成量度，如[生成量度](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md)中所述。
1. 为量度指定“每次访问页面查看次数”或类似的名称。
1. 为量度提供用户友好的&#x200B;**[!UICONTROL 描述]**，以显示其用途。
1. 选择正确的&#x200B;**[!UICONTROL 格式]**。 对于此示例，请选择&#x200B;[!UICONTROL **十进制**]。
1. 确定您希望报表显示多少个小数位。
1. 在&#x200B;[!UICONTROL **将上升趋势显示为**]&#x200B;下拉菜单中，选择&#x200B;[!UICONTROL **良好（绿色）**]。
1. 添加&#x200B;**[!UICONTROL 标记]**&#x200B;以组织您的量度。
1. 对于此量度，首先将“页面查看次数”拖到画布的&#x200B;[!UICONTROL **定义**]&#x200B;部分中，然后将“访问次数”拖动到其下方（等到蓝线出现后再放置）。
1. 选择“除以”运算符。（“除以”是默认的运算符。）
1. 现在，当您生成量度时，即可在右上角看到该量度的&#x200B;**[!UICONTROL 预览]**。
1. 产品兼容性显示该量度是与“[当前数据](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/current-data.html?lang=zh-Hans)”兼容，还是仅与“完全处理数据”兼容。
1. 选择&#x200B;**[!UICONTROL 保存]**。

   请注意，无论您何时对量度定义进行更改，**[!UICONTROL 概要]**&#x200B;公式都会随之发生更新。

1. （可选）要共享、批准、（重新）标记、重命名或删除指标，可转到[计算量度页面](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md)。
