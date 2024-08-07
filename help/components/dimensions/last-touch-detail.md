---
title: 最近联系渠道详细信息
description: 访客参与到期时间内最近的那个营销渠道的详细信息。
feature: Dimensions
exl-id: def03267-f3e5-4772-a707-5678c45eba6d
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 80%

---

# 最近联系渠道详细信息

“最近联系渠道详细信息”[维度](overview.md)报告访客在该访客的参与期（默认为30天）内与之匹配的最新营销渠道的详细信息。 此维度对于了解哪些因素促成匹配营销渠道的点击量非常有价值。例如，如果访客到达您的网站且与“付费搜索”营销渠道匹配，则您可以使用渠道详细信息来查看使用了哪个搜索引擎或搜索了哪个关键词。

## 使用数据填充此维度

此维度复制其他变量中的值。使用的变量引用每个[营销渠道处理规则](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md)内的渠道值。当点击与营销渠道处理规则匹配时，[最近联系渠道](last-touch-channel.md)维度将设置为渠道名称，并且此维度将会设置为规则中设置的渠道值。

如果要将此维度设置为特定值，必须执行以下步骤：

* 确保所需的维度项目位于点击属性或自定义变量中。
* 设置包含点击所需条件的营销渠道处理规则。
* 在营销渠道处理规则中的[!UICONTROL 设置渠道值]下选择所需的下拉值。
* 访客对网站的点击，必须符合营销渠道处理规则中所述的条件。

## 维度项目

Dimension项目取决于适用营销渠道处理规则的下拉列表中列出的渠道值。 例如，如果将渠道值设置为“页面 URL”，则维度项目包括您网站上的页面 URL。如果将渠道值设置为“反向链接域”，则维度项目包括访客通过点击进入您网站的域。此维度汇总所有详细维度项目，而不管这些维度项目位于哪个渠道。

Adobe 建议设置与营销渠道相关的渠道值，以便深入了解渠道详细信息。
