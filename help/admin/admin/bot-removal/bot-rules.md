---
description: 使用机器人规则，您可以从报表包中删除已知蜘蛛程序和机器人程序生成的流量。删除机器人程序流量可为您网站上的用户活动提供更准确的测量。
seo-description: 使用机器人规则，您可以从报表包中删除已知蜘蛛程序和机器人程序生成的流量。删除机器人程序流量可为您网站上的用户活动提供更准确的测量。
seo-title: 机器人规则
solution: Analytics
subtopic: 机器人规则
title: 机器人规则
topic: 管理工具
uuid: cb9e29d-1c37-43de-b7 ac-34441093a60 e
translation-type: tm+mt
source-git-commit: 4a627e268994d0152a19fb44e9bc06ea7ebc64c6

---


# 机器人规则

机器人规则允许您从由已知蜘蛛程序和机器人生成的报表套件中删除流量。删除机器人程序流量可为您网站上的用户活动提供更准确的测量。

定义了机器人规则之后，将按照定义的规则对所有传入流量进行比较。报表包中将不会收集与任何这些规则匹配的流量，并且流量量度中也不会包含这些流量。

To update or upload bot rules, navigate to **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**. Select the correct Report Suite, and then go to **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL General]** &gt; **[!UICONTROL Bot Rules]**.

删除机器人程序流量通常会减少流量和转化量度。许多客户发现删除机器人程序流量会导致转化比率增加以及其他可用性量度值增加。在删除机器人程序流量之前，请与利益关系人进行交流以确保做出此更改后他们会对关键性能指标做出必要的调整。如有可能，建议首先从小型报表包中删除机器人程序流量以评估潜在的影响。

>[!NOTE]我们建议每个报表包定义不超过 500 个机器人规则。用户界面允许手动定义 500 个规则。在达到此限制后，必须通过“[导入文件](../../../admin/admin/bot-removal/t-upload-bot-rules.md#task_95868D8564564E6A996163335C119806)”和“导出机器人规则”选项对规则进行批量管理。

机器人程序流量数据存储在单独的库中，以便在[!UICONTROL 机器人]和[!UICONTROL 机器人页面]报表中显示。

| 规则类型 | 描述 |
|--- |--- |
| IAB | Selecting [!UICONTROL Include IAB] uses the IAB's (International Advertising Bureau's) International Spiders &amp; Bots List to remove bot traffic. 此列表由 IAB 每月更新。<br>要将机器人提交到IAB列表，请访问 [IAB](https://www.iab.net/sites/spiders/form.php)。<br>Adobe 无法向客户提供详细的 IAB 机器人程序列表，但是您可以使用“机器人报表”来查看访问您网站的机器人程序的列表。 |
| 自定义机器人规则 | 请参阅 [创建自定义机器人规则](../../../admin/admin/bot-removal/t-create-bot-rules.md). |

## 机器人规则对数据收集的影响 {#section_F01A3130E7A04A9993371CF26F6586F2}

机器人规则可应用到所有分析数据。机器人规则删除的数据仅在“机器人”和“机器人页面”报表中可见。

VISTA rules are applied after Bot Rules (see [Processing Order](../../../admin/admin/c-processing-rules/c-processing-rules-configuration/processing-rule-order.md#concept_8A6BBEA7F50C40C8A8D8755D4F579B1E)).

**高点击访问处理：**&#x200B;如果一次访问中出现 100 次以上的点击，则报表会确定访问时间（以秒为单位）是否小于或等于访问的点击次数。在这种情况下，由于长时间集中访问的处理成本原因，报表会重新开始一个新访问。高点击访问通常是由机器人攻击造成的，因此不视为正常的访客浏览。

>[!NOTE]
>
>标记为 *`bots`*[服务器调用](https://docs.adobe.com/content/help/en/analytics/admin/server-call-usage/overage-overview.html)的点击。

## IP 模糊处理对机器人过滤的影响 {#section_92E60B95BE8940D983F28C79E0CD6B12}

IAB 机器人列表完全基于用户代理，因此基于该列表的过滤不受 IP 模糊设置影响。对于非 IAB 机器人过滤（自定义规则），IP 可能为过滤标准的一部分。如果过滤机器人使用 IP，则在启用该设置的情况下，机器人过滤发生于最后八位字节已被删除之后，但又在其他 IP 模糊处理选项之前，例如删除整个 IP 或将它替换为某些唯一 ID。

如果启用了 IP 模糊处理，则在 IP 地址被模糊处理之前会发生 IP 排除，这样客户就无需在启用 IP 模糊处理时更改任何内容。

如果删除了最后八位字节，则该操作是在 IP 过滤之前完成的。这样，最后八位字节将被替换为 0，并且应当更新 IP 排除规则以匹配末尾为 0 的 IP 地址。匹配 * 应当匹配 0。
