---
description: 根据设备是启用、禁用 JavaScript 还是当作“未识别”Javascript 来显示量度。
title: JavaScript 支持
topic: Reports
uuid: 7b95001a-cd35-478a-8b24-54d30666110d
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# JavaScript 支持

根据设备是启用、禁用 JavaScript 还是当作“未识别”Javascript 来显示量度。

>[!NOTE] 2016 年 11 月初，我们计划删除在移动设备中始终将 JavaScript 列为 *`disabled / unidentified`* 的限制。

JavaScript报告与原始数据中的列javascript相对应。

javascript是访问级别字段，因此它会保留访问中首次点击的值。 列javascript基于j_jscript列中存在的第一个值(如visit_推荐人将仅保留访问的第一个推荐人)。

j_jscript是从Adobe Analytics图像请求中的参数j填充的。

示例如下：

| 点击 | j_jscript | javascript |
|---|---|---|
| 1 |  | 0 |
| 2 | 1.6 | 0 |
| 3 | 1.6 | 0 |

因此，在访问中某个时点指定了javascript版本并不重要——它将始终显示为非Javascript，因为第一次点击不包含j_jscript的任何值。
