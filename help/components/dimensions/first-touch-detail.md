---
title: 首个联系渠道详细信息
description: 访客参与有效期限内的第一个营销渠道的详细信息。
feature: Dimensions
exl-id: a155182d-7bc0-4c7d-9de7-680bfe2d6432
TQID: https://experienceleague.adobe.com/duNfZhq3nb1kAjVkbUEUkuFPixk-FaTZX3-TA25AifQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 362
ht-degree: 82%

---

# 首个联系渠道详细信息

“首个联系渠道详细信息”[维度](overview.md)报告访客在该访客的参与期（默认为30天）内与之匹配的第一个营销渠道的详细信息。 此维度对于了解哪些因素促成匹配营销渠道的点击量非常有价值。 例如，如果访客到达您的网站且与“付费搜索”营销渠道匹配，则您可以使用渠道详细信息来查看使用了哪个搜索引擎或搜索了哪个关键词。

## 使用数据填充此维度

此维度复制其他变量中的值。 使用的变量引用每个[营销渠道处理规则](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md)内的渠道值。 当点击与营销渠道处理规则匹配时，[最近联系渠道](last-touch-channel.md)维度将设置为渠道名称，并且此维度将会设置为规则中设置的渠道值。

如果要将此维度设置为特定值，必须执行以下步骤：

* 确保所需的维度项目位于点击属性或自定义变量中。
* 设置包含点击所需条件的营销渠道处理规则。
* 在营销渠道处理规则中的[!UICONTROL 设置渠道值]下选择所需的下拉值。
* 访客对网站的点击必须符合营销渠道处理规则中所述的条件，_并且_&#x200B;必须是访客参与期内第一个符合条件的营销渠道值。

如果后续点击与其他营销渠道下的条件相匹配，则此维度不会被新的营销渠道覆盖。

## 维度项目

Dimension项目取决于适用营销渠道处理规则的下拉列表中列出的渠道值。 例如，如果将渠道值设置为“页面 URL”，则维度项目包括您网站上的页面 URL。 如果将渠道值设置为“反向链接域”，则维度项目包括访客通过点击进入您网站的域。 此维度汇总所有详细维度项目，而不管这些维度项目位于哪个渠道。

Adobe 建议设置与营销渠道相关的渠道值，以便洞察渠道详细信息。
