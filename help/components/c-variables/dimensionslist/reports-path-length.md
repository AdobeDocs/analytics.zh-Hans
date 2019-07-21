---
description: 按百分比和总次数显示每次访问网站的深度。换言之，此报表指示访客退出网站前平均查看的页面数。
seo-description: 按百分比和总次数显示每次访问网站的深度。换言之，此报表指示访客退出网站前平均查看的页面数。
seo-title: 路径长度
solution: Analytics
title: 路径长度
topic: 报表
uuid: f1c29e78-279a-46a5-b758-d4 f0 da629239
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 路径长度

按百分比和总次数显示每次访问网站的深度。换言之，此报表指示访客退出网站前平均查看的页面数。

自定义链接（s.tl 调用）不会加入到页面的路径长度中。但是，它们会将 prop（流量变量）的路径长度计算在内。

同一个值的多个实例（重新载入）不会增加路径长度。示例：

**[!UICONTROL 页面A]** &gt; **[!UICONTROL 页面B]** &gt; **[!UICONTROL 自定义链接]** &gt; **[!UICONTROL 页面B]** =路径长度2。（请注意，自定义链接和页面 B 的重新载入不计算到路径长度中。）

**[!UICONTROL Prop A]** &gt; **[!UICONTROL Custom Link传递Prop B]** &gt; **[!UICONTROL Prop C]** = Path长度3。（请注意，Prop B 的自定义链接不计算到路径长度中。）
