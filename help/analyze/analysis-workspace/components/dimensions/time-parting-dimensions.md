---
description: 了解时间划分维度如何采用所收集事件的时间戳，并将这些事件划分为更有意义的维度，例如每天时间或每周时间。
title: 时间划分维度
feature: Dimensions
role: User, Admin
exl-id: 92fbcc1e-1f7f-405a-8ad1-199fb7ba505e
source-git-commit: bf8bc40e3ec325e8e70081955fb533eee66a1734
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 74%

---

# 时间划分维度

时间划分会采用所收集的点击量的时间戳，并将其划分为更有意义的维度，例如&#x200B;**小时**&#x200B;或&#x200B;**星期**。


>[!BEGINSHADEBOX]

观看演示视频的![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [时间划分维度](https://video.tv.adobe.com/v/41460?quality=12&learn=on&captions=chi_hans){target="_blank"}。

>[!ENDSHADEBOX]


时间划分维度基于报表包或虚拟报表包的时区。这些维度可以在 Analysis Workspace 中使用，并且可以帮助您回答以下问题：

* 在某个较长的日期范围内，哪些时段内访问网站或应用程序的访客最多？
* 在我的网站或应用程序上，是否每周有几天或每天有几个小时的转化率较高？
* 周末的销售额与工作日的销售额相比如何？
* 特定营销活动是在上午还是在下午产生更高的转化？

>[!NOTE]
>
>时间划分维度仅在 Analysis Workspace 中可用。要在其他 Analytics 解决方案中使用时间划分维度，您可以实施 [getTimeParting 插件](https://experienceleague.adobe.com/docs/analytics/implementation/vars/plugins/gettimeparting.html?lang=zh-Hans)。

Analysis Workspace 中的时间划分维度包括：

| 维度 | 示例值 |
| --- | --- |
| 每天时间 | 0 时至 23 时 |
| 上午/下午 | 上午、下午 |
| 每周时间 | 星期一、星期二、星期三、星期四、星期五、星期六、星期日 |
| 周末/工作日 | 周末、工作日 |
| 日期 | 1 日至 31 日 |
| 月份 | 一月至十二月 |
| 每年的某一天 | 第 1 天至第 366 天 |
| 季度 | 第一季度、第二季度、第三季度和第四季度 |
