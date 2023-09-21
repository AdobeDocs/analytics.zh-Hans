---
title: 浏览器
description: 使用的浏览器的名称和版本。
feature: Dimensions
exl-id: 2bdf2a5a-3482-43fa-b2e1-fbea892918fb
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 38%

---

# 浏览器

“[!UICONTROL 浏览器]’ [维度](overview.md) 报告发送点击的浏览器的名称和版本。 此维度有助于了解访客最常使用的浏览器。 测试网站的新版本时，您可以在此维度中的热门浏览器上运行这些测试，以便最大限度地做好质量控制工作。

## 使用数据填充此维度

此维度引用 Adobe 内部的一个查找表。查找值基于图像请求中的 `User-Agent` HTTP 标头。如果您使用 AppMeasurement 库（例如，通过 Adobe Experience Platform 中的标记），则此维度可开箱即用。

## 维度项目

维度项目包括使用的浏览器名称和版本。同一浏览器的不同版本是不同的维度项目。

某些维度项目包含 `"(unknown version)"`，而不是版本号。此维度项目会引用 Adobe 尚未添加到其查找表的最新浏览器版本。由于浏览器经常更新，因此给定浏览器的 `"(unknown version)"` 很常见，而且是临时的。Adobe 通常在月度维护版本发布期间更新查找表。

## 标签和定义的更改

以下是有关浏览器在报表中的呈现方式所发生的更改列表。 这些更改可能会影响您的报表或依赖这些值的任何逻辑，例如区段。

### 从浏览器中删除公司

从Chrome、Edge和Firefox浏览器版本100开始，公司名称将不再显示在浏览器之前。 如果用户具有基于浏览器名称的区段定义，这可能会影响用户。 例如，从110版开始，包含“浏览器包含‘Google’”定义的区段将不再识别Chrome浏览器。

示例：

Chrome版本109将显示为“Google Chrome 109”。
Chrome版本110将显示为“Chrome 109”。

### 消除Chrome中移动和非移动之间的区别

从Chrome 110开始，移动设备版本和非移动设备版本的Chrome将被标记为相同。 当前，移动设备版本和非移动设备版本会单独进行标记。 重要的是，这将更改名称的含义，而非“mobile”。 “Chrome 109”为非移动设备（即桌面）“Chrome 110”为移动设备且非移动设备。 同样，如果浏览器名称中有引用“mobile”的区段定义，这些定义可能不再按预期工作。 您可以使用移动设备分段和划分来比较移动设备流量与非移动设备流量。

示例：

Mobile Chrome 109将显示为“Chrome Mobile 109”。
非移动设备Chrome 109将显示为“Chrome 109”。

Mobile Chrome 110将显示为“Chrome 110”。
非移动设备Chrome 110将显示为“Chrome 110”。
