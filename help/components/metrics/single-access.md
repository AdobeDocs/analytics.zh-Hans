---
title: 单次存取
description: 维度项目在访问中未更改的次数。
feature: Metrics
exl-id: 973ce835-9d6f-4ead-90c9-0b80aac82cc0
source-git-commit: 6d2c278c5525c89b73c39bbfcedbe644806bf989
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 15%

---

# 单次存取

**[!UICONTROL 单次存取]** [量度](overview.md)显示适用的报告维度在整个访问期间仅包含单个值的访问次数。 它是更广泛的、特定于维度的[[!UICONTROL 单页面访问次数]](single-page-visits.md)版本。 当您想要查看某个维度在访问期间仅设置一次时的值时，此量度非常有用。

## 如何计算此指标

此量度的定义依赖于[[!UICONTROL 计数重复实例]](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md#project-info-settings)的项目设置：

* **计算启用的重复实例数**：计算维度在一次访问中恰好包含一个值的访问次数。 如果维度仍然存在，则它不再计为单次存取。
* **计数已禁用的重复实例**：计数维度包含单个唯一值的访问次数。 您可以多次将维度项设置为相同的值，或者让维度项保持不变并仍将其计为单次访问。

无论“[!UICONTROL 计算重复实例]”为何，如果维度更改为第二个唯一值，则访问不再计为单次存取。 如果在其中设置了维度，则此计算中将包含链接跟踪调用。

## “[!UICONTROL 单次存取]”与“[!UICONTROL 单页访问]”之间的差异

在[[!UICONTROL 页面]](../dimensions/page.md)维度的上下文中，“[!UICONTROL 单次存取]”和“[!UICONTROL 单页访问次数]”始终完全相同，无论“[!UICONTROL 计数重复实例]”项目设置如何。 当您使用其他维度时，二者的差异就会显现。

* **[!UICONTROL 单次存取]**：显示单次点击存在给定维度项目的访问次数。 它与您在项目中使用的维度息息相关。
* **[!UICONTROL 单页面访问次数]**：显示单次点击中存在“[!UICONTROL 页面]”维度的访问次数。 即使您在报表中使用其他维度，它仍会计算包含单个唯一“[!UICONTROL 页面]”维度项目的访问量。

如果[[!UICONTROL 计数重复实例]](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md#project-info-settings)被禁用，则量度定义会稍有变化：

* **单次存取**：显示给定维度项目在整个访问期间未更改的访问次数。
* **单页面访问次数**：显示“[!UICONTROL 页面]”维度在整个访问期间未更改的访问次数。

例如，请考虑以下两次点击访问示例。 报表中的维度是[[!UICONTROL 网站部分]](../dimensions/site-section.md)，并且已禁用“[!UICONTROL 计数重复实例]”。

* 访客点击了两个页面，但它们都位于同一网站部分。由于网站部分在访问期间保持不变，因此它被计为“单次存取”。 它不计为单个页面访问次数，因为该访问包含多个唯一的[!UICONTROL 页面]维度项目。
* 访客点击不同网站区域中的两个页面，但两个页面的名称恰好相同。访问不计为单次存取，因为存在两个唯一的网站区域值。 它计为单个页面访问次数，因为有一个唯一的[!UICONTROL 页面]维度项目。
