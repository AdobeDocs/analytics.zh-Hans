---
description: 如果使用 Akamai 托管，则从控制台测试未发布的规则。
keywords: Dynamic Tag Management;rule;switcher plugin;akamai;test akamai;unpublished rules;test unpublished rules;debug rule
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: 测试用于 Akamai 托管的尚未发布的规则
uuid: 979e3d74-8d96-47d0-b581-cf5371248434
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 测试用于 Akamai 托管的尚未发布的规则

如果使用 Akamai 托管，则从控制台测试未发布的规则。

Switcher 插件通常是最简单的测试方法。有关更多信息，请参阅动态标签管理产品文档中的 [Search Discovery 插件](https://marketing.adobe.com/resources/help/en_US/dtm/search_discovery_plugins.html)。

下列步骤说明了如何在不使用 Switcher 插件的情况下进行测试：

1. 访问您网站中的 Web 控制台，并键入 `localStorage.setItem('sdsat_stagingLibrary', true)`.
1. 按 **[!UICONTROL Enter]**。
1. 键入 `_satellite.setDebug(true)`，然后按 **[!UICONTROL Enter]**。
1. 刷新页面。

   此操作会加载您的暂存库并设置调试器，以便您能够看到页面中触发的所有可用（已发布或未发布）规则的详细信息。
1. 完成后，运行 `localStorage.setItem('sdsat_stagingLibrary', false)`，然后按 **[!UICONTROL Enter]**。

   步骤结果
