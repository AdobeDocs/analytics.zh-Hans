---
description: 了解如何实施多包标记以将图像请求发送到多个报表包。
title: 实施多包标记
exl-id: null
source-git-commit: 3986084eaab81842b6ea0dbabc7bdb78e39f887a
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 91%

---


# 实施多包标记

利用[多包标记](/help/admin/c-manage-report-suites/rollup-report-suite.md)，您不仅可以将图像请求发送到全局报表包，还可以发送到各个子报表包，以便您可以向不同的最终用户提供公司全局报表包数据的子集。

要实施多包标记，您必须在网页和应用程序的跟踪代码中包含全局报表包的报表包 ID (RSID)，还要包括适用子报表包的 RSID。

* 对于Adobe Experience Platform标记实施，请为[[!DNL Analytics] 扩展](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html)指定每个报表包。

* 对于旧版 JavaScript 和移动 SDK 实施，请用逗号分隔 RSID，并且不要使用空格（`rsid1,rsid2,rsid3` 等）。

* 对于其他实施类型，请使用所需的语法列出多个 RSID。

>[!TIP]
>
> 最佳实践是首先列出全局报表包或报表包 ID。

多包标记会导致对每个图像请求进行多个服务器调用：对全局报表包进行主调用，对每个子报表包进行次调用。

>[!NOTE]
>
> [虚拟报表包](/help/components/vrs/vrs-about.md)也允许您向不同的最终用户提供公司全局报表包数据的子集，但不会引起次服务器调用。

## 我是应该实施多包标记还是虚拟报表包？

使用虚拟报表包代替多包标记通常是最佳实践，但您的业务需求决定了适合您组织的最佳报表包方法。

要了解虚拟报表包是否是您的最佳方法，请参阅“[虚拟报表包和多包标记注意事项](/help/components/vrs/vrs-considerations.md)”。另请参阅“[虚拟报表包与多包标记](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78)”，以比较多包标记和虚拟报表包功能。
