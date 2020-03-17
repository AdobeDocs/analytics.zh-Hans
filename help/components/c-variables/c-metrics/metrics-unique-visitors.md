---
description: 在版本 14 中，独特访客是指在指定时段内首次访问网站的访客。例如，独特访客可能在一周内访问了网站 10 次，但如果指定的时段为“周”，则在该周内，每一位独特访客将只被计入一次。该周结束之后，才可为另一个时段再次计入该独特访客。
title: 独特访客
topic: Metrics
uuid: ae210698-99f9-485e-a640-c7520807adc7
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 独特访客

在版本 14 中，独特访客是指在指定时段内首次访问网站的访客。例如，独特访客可能在一周内访问了网站 10 次，但如果指定的时段为“周”，则在该周内，每一位独特访客将只被计入一次。该周结束之后，才可为另一个时段再次计入该独特访客。

## 版本 14 和 15 之间的差异

版本 14 未从基于分类的报表中删除重复的[!UICONTROL 访问]和[!UICONTROL 独特访客]量度。例如，如果两个视频剪辑共享同一分类，查看了这两个视频剪辑的单一访客在基于分类的报表中会生成两次[!UICONTROL 访问]并且会被计为两个[!UICONTROL 独特访客]。

版本 15 从基于分类的报表中删除了重复的[!UICONTROL 访问]和[!UICONTROL 独特访客]。此方法计算[!UICONTROL 访问]和[!UICONTROL 访客]更为准确，但是在基于分类的报表中，如果与升级前收集的数据相比，您的[!UICONTROL 访问]和[!UICONTROL 独特访客]量度通常会减少。

| 使用 | 描述 |
|---|---|
| 流量 | 访客是指访问您网站的人。不需要使用永久性 Cookie。 |
| 转化 | 访客是指访问您网站的人。当发生转化相关的事件或操作时会被计为一次。 |
| Ad Hoc Analysis | 访客是指访问您网站的人。不需要使用永久性 Cookie。 |

请参阅[独特访客报表 - 版本 15 和 Ad Hoc Analysis](/help/components/c-variables/dimensionslist/reports-unique-visitors-v15-dsc.md)。

>[!MORELIKETHIS]
>
>* [每日独特访客](/help/components/c-variables/c-metrics/metrics-daily-unique-visitors.md)

