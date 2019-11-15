---
description: 按百分比和总次数显示每次访问网站的深度。换言之，此报表指示访客退出网站前平均查看的页面数。
solution: Analytics
title: 路径长度
topic: Reports
uuid: f1c29e78-279a-46a5-b758-d4f0da629239
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 路径长度

按百分比和总次数显示每次访问网站的深度。换言之，此报表指示访客退出网站前平均查看的页面数。

自定义链接（s.tl 调用）不会加入到页面的路径长度中。但是，它们会将 prop（流量变量）的路径长度计算在内。

同一个值的多个实例（重新载入）不会增加路径长度。示例:

**[!UICONTROL 页面A]** &gt;页 **[!UICONTROL 面B]** &gt;自定 **[!UICONTROL 义链接]** &gt;页 **[!UICONTROL 面B]** =路径长度为2。 （请注意，自定义链接和页面 B 的重新载入不计算到路径长度中。）

**[!UICONTROL Prop A]** &gt;自定 **[!UICONTROL 义链接传递Prop B]** &gt; **[!UICONTROL Prop C]** =路径长度为3。 （请注意，Prop B 的自定义链接不计算到路径长度中。）
