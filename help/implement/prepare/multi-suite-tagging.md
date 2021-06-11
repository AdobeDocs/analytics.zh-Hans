---
description: 了解如何实施多包标记以将图像请求发送到多个报表包。
title: 实施多包标记
exl-id: null
source-git-commit: 81da9ff9b00a69c49c028fc7f006c161d8ff21d4
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 3%

---


# 实施多包标记

[通过多包](/help/admin/c-manage-report-suites/rollup-report-suite.md) 标记，您不仅可以将图像请求发送到全局报表包，还可以发送到各个子报表包，这样您就可以向不同的最终用户提供公司全局报表包数据的子集。

要实施多包标记，您必须在网页和应用程序的跟踪代码中包含全局报表包的报表包ID(RSID)，以及适用子报表包的RSID。

* 对于Adobe Experience Platform Launch实施，请为[[!DNL Analytics] 扩展](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html?lang=zh-Hans)指定每个报表包。

* 对于旧版JavaScript和Mobile SDK实施，请使用逗号分隔RSID，不留空格（`rsid1,rsid2,rsid3`等）。

* 对于其他实施类型，请使用所需的语法列出多个RSID。

>[!TIP]
>
> 最佳实践是先列出全局报表包或报表包ID。

多包标记会为每个图像请求发出多个服务器调用：对全局报表包的主调用和每个子报表包的次级调用。

>[!NOTE]
>
> [虚拟报表包](/help/components/vrs/vrs-about.md)（还允许您向不同的最终用户提供公司全局报表包数据的子集）不会发起次级服务器调用。

## 我应该实施多包标记还是虚拟报表包？

使用虚拟报表包而不是多包标记通常是最佳做法，但业务需求决定了适用于贵组织的最佳报表包方法。

要了解虚拟报表包是否是您的最佳方法，请参阅“[虚拟报表包和多包标记注意事项](/help/components/vrs/vrs-considerations.md)”。 另请参阅“[虚拟报表包与多包标记](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78)”，以了解多包标记和虚拟报表包功能的比较。
