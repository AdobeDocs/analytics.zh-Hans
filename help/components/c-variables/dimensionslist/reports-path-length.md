---
description: 按百分比和总次数显示每次访问网站的深度。换言之，此报表指示访客退出网站前平均查看的页面数。
title: 路径长度
topic: Reports
uuid: f1c29e78-279a-46a5-b758-d4f0da629239
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 路径长度

按百分比和总次数显示每次访问网站的深度。换言之，此报表指示访客退出网站前平均查看的页面数。

自定义链接（s.tl 调用）不会加入到页面的路径长度中。但是，它们会将 prop（流量变量）的路径长度计算在内。

同一个值的多个实例（重新载入）不会增加路径长度。示例：

**[!UICONTROL 页面 A]** > **[!UICONTROL 页面 B]** > **[!UICONTROL 自定义链接]** > **[!UICONTROL 页面 B]** = 两者的路径长度。（请注意，自定义链接和页面 B 的重新载入不计算到路径长度中。）

**[!UICONTROL Prop A]** > **[!UICONTROL 传递 Prop B 的自定义链接]** > **[!UICONTROL Prop C]** = 三者的路径长度。（请注意，Prop B 的自定义链接不计算到路径长度中。）
