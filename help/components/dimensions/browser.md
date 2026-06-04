---
title: 浏览器
description: 使用的浏览器的名称和版本。
feature: Dimensions
exl-id: 2bdf2a5a-3482-43fa-b2e1-fbea892918fb
TQID: https://experienceleague.adobe.com/J6rDfVwmRZpRLrultdurQkRih2HcPygjcjwO0bkms5E
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: d2311670-43bd-4c2e-bc98-1da2aaba9cefid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: bdd7a704c94394d6f6cedfbc07988bde69993691
workflow-type: tm+mt
source-wordcount: 280
ht-degree: 43%

---

# 浏览器

“[!UICONTROL 浏览器]”[维度](overview.md)报告发送点击的浏览器的名称和版本。 当您想要测量访客最常使用的浏览器时，此维度很有用。 测试网站的新版本时，您可以在此维度中的热门浏览器上运行这些测试，以便最大限度地做好质量控制工作。

## 使用数据填充此维度

此维度引用 Adobe 内部的一个查找表。 查找值基于图像请求中的 `User-Agent` HTTP 标头。 Adobe与[DeviceAtlas](https://deviceatlas.com/)合作，共同在用户代理和浏览器之间维护查找。

* 对于AppMeasurement实施，此维度可开箱即用。
* 对于Web SDK实施，请在[配置数据流](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html)时启用[!UICONTROL 设备查找]。

## 维度项目

维度项目包括使用的浏览器名称和版本。 同一浏览器的不同版本是不同的维度项目。

某些维度项目包含 `"(unknown version)"`，而不是版本号。 此维度项目引用Adobe尚未添加到其查找表的最新浏览器版本。 由于浏览器经常更新，因此给定浏览器的 `"(unknown version)"` 很常见，而且是临时的。 Adobe 通常在月度维护版本发布期间更新查找表。

某些维度项包含`.999`作为次要版本号，如`"Chrome 148.999"`。 此值表示Adobe无法可靠地确定浏览器的次要版本。 当Chrome或Edge浏览器发送不带[客户端提示](/help/technotes/client-hints.md)的请求时，用户代理字符串中的次要版本被视为不可信。 Adobe不会用可能不准确的次要版本夸大维度项，而是将这些次要版本替换为`.999`。 同样，如果任何浏览器报告的版本号异常高（高于99999），Adobe会将其标准化为`999.999`。
