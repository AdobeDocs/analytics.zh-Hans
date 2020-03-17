---
description: 根据设备是启用、禁用 JavaScript 还是当作“未识别”Javascript 来显示量度。
title: JavaScript 支持
topic: Reports
uuid: 7b95001a-cd35-478a-8b24-54d30666110d
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# JavaScript 支持

根据设备是启用、禁用 JavaScript 还是当作“未识别”Javascript 来显示量度。

> [!NOTE] 2016 年 11 月初，我们计划删除在移动设备中始终将 JavaScript 列为 *`disabled / unidentified`* 的限制。

JavaScript 报表对应于原始数据中的 javascript 列。

javascript 是一个访问级别的字段，因此它会保留访问中首次点击的值。javascript 列基于 j_jscript 列中出现的第一个值（例如，visit_referrer 将仅保留访问的第一个反向链接）。

j_jscript 通过 Adobe Analytics 图像请求中的参数 j 进行填充。

示例如下：

| 点击 | j_jscript | javascript |
|---|---|---|
| 1 |  | 0 |
| 2 | 1.6 | 0 |
| 3 | 1.6 | 0 |

因此，如果您在访问中的某个时间点指定了 javascript 版本，这无关紧要 - 由于首次点击不包含任何 j_jscript 值，因此它会始终显示为非 Javascript。
