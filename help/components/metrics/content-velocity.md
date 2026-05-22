---
title: 内容周转率
description: 内容周转率会测量内容对下游内容的影响。
feature: Metrics
exl-id: 8ba54990-ff7d-4693-92de-7f9d9f916b55
TQID: https://experienceleague.adobe.com/KEcYF9OWDaxwZX798AETiAIxcffBAwj29Go-oHLOnaU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 299
ht-degree: 12%

---

# 内容周转率

“内容周转率”计算量度可帮助您衡量维度（通常为[[!UICONTROL 页面]](/help/components/dimensions/page.md)）对用户在您的网站或应用程序上花费时间的贡献情况。

此量度使用[页面查看次数](page-views.md)量度上的[参与率归因](/help/analyze/analysis-workspace/attribution/models.md)作为其计算的一部分。 利用访问参与率，每次点击页面时，之前在同一次访问期间点击的所有页面都会获得页面查看的点数。 此公式通常意味着在访问期间越早点击页面，它获得的点数越多。 (请参阅[页面查看次数（参与率） |访问)或“访问参与率”](#page-views-participation--visit-or-visit-participation)以了解更多信息。)

## 计算

“内容周转率”是默认的计算结果[量度](overview.md)，它使用公式`Page views (Visit participation)`除以`Visits`。

![](assets/cont-velo-1.png)

## 常见用法

[!UICONTROL 内容周转率]通常与其他关键量度一起用于内容分析，例如[!UICONTROL 页面查看次数]、[!UICONTROL 访问次数]和[!UICONTROL 跳出率]。

![](assets/cont-velo-3.png)

## 示例

以下示例划分了Content Velocity的2个部分：“页面查看次数（参与率）” | Visit)”和“Visits”。

### 页面查看次数（参与率） |访问)或“访问参与率”

请思考以下访问参与率如何影响归因的示例：

在网站上，用户按以下顺序访问以下页面：

* 页面A
* 页面B
* 页面C
* 页面D

在上例中，页面A将接收4次点击的点数，页面B接收3次点击，页面C接收2次点击，页面D接收1次点击。

以下示例说明了相同的原则，但一些页面被多次访问。

* 页面A
* 页面B
* 页面C
* 页面B
* 页面D
* 页面A

在上例中，页面A将接收7次点击的点数，页面B接收8次点击，页面C接收4次点击，页面D接收2次点击。

### 访问次数

计算访问参与率后，结果除以访问次数。
