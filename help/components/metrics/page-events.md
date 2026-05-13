---
title: 页面事件
description: 触发的链接跟踪操作数量。
feature: Metrics
exl-id: 1afe86e3-65b3-4e4e-b436-ed7cb5da9641
TQID: https://experienceleague.adobe.com/tOEidVQjv4ynokjH53SEdKeOHiqwZn02WZDalUESsAs
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 210
ht-degree: 33%

---

# 页面事件

“页面事件”[量度](overview.md)显示执行任何链接跟踪调用的次数。 当您想要了解哪些页面具有最吸引人的内容时，此量度很有用。 当访客无需导航到新页面即可对页面执行操作时，此量度的度量最有价值。

例如，在电子商务网站的典型历程中，访客可以在单个页面上进行多次交互。 典型的Analytics实施将这些交互配置为链接跟踪([`tl()`](/help/implement/vars/functions/tl-method.md))调用，而页面查看([`t()`](/help/implement/vars/functions/t-method.md))调用保留用于初始页面加载。 此实施方法提供了丰富的事件跟踪功能，可为insight提供访客在继续其旅程之前发生交互的情况。

## 如何计算此指标

此量度计数报表包中所有链接跟踪调用 ([`tl()`](/help/implement/vars/functions/tl-method.md))。 此量度中包含所有链接类型，特别是[自定义链接](../dimensions/custom-link.md)、[下载链接](../dimensions/download-link.md)和[退出链接](../dimensions/exit-link.md)。 它不包括页面查看调用([`t()`](/help/implement/vars/functions/t-method.md))。

## 与类似量度比较

* **页面事件与[页面查看次数](page-views.md)**：页面事件计算链接跟踪调用([`tl()`](/help/implement/vars/functions/tl-method.md))的数量，并排除页面查看跟踪调用([`t()`](/help/implement/vars/functions/t-method.md))。 页面查看次数则相反；它计算页面查看跟踪调用的数量，不包括链接。
