---
description: 路径信息可能不被记录，没有显示在报表中的原因列表。
keywords: Analytics 实施
seo-description: 路径信息可能不被记录，没有显示在报表中的原因列表。
seo-title: 可能无法记录路径
solution: Analytics
title: 可能无法记录路径
topic: 开发人员和实施
uuid: 9985b7f7-75ea-4c94-97a3-520f92630989
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# 可能无法记录路径

路径信息可能不被记录，没有显示在报表中的原因列表。

* 没有在相应报表包中为该 prop 启用路径分析。此启用操作是报表包特定的。
* 没有将数据传递给正确的 prop。
* 已启用路径分析，并且数据已放入 prop 中，但没有在报表中显示。[!UICONTROL sprop] 数据会在 10 分钟内显示，但路径数据直到访客的会话结束时才会显示。会话停留在非活动状态达 30 分钟后结束。Analytics 然后再用 10 分钟完成对路径数据的处理，以在报表中最终演示。

如果您检查了上述所有内容，但仍不显示数据，请与客户关怀部门联系，以便进一步调试。
