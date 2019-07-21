---
description: Adobe 提供了一些更新 Analytics 代码的最佳实践。
keywords: Analytics 实施
seo-description: Adobe 提供了一些更新 Analytics 代码的最佳实践。
seo-title: 替换Analytics代码
solution: Analytics
subtopic: 故障诊断
title: 替换Analytics代码
topic: 开发人员和实施
uuid: d3ea6585-199f-4dobe-9ee8-15b204689f2f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 替换Analytics代码

Adobe 提供了一些更新 Analytics 代码的最佳实践。

客户经常使用 Adobe [!UICONTROL 代码管理器]将其代码替换为最新版本。只要记住一些特定的规则，这还是一项颇值得遵循的做法。

## 使用错误的数据收集服务器 ID {#section_1726CEB1ABEC408492569B06664410C8}

有时，客户会将通用的 [!DNL s_code.js] 文件（尚未从 Adobe 代码管理器中生成）发送给网站的代码实施方。因此，会对该帐户使用错误的数据收集服务器 ID（如 [!UICONTROL s.dc] 变量中所示）。Adobe 建议客户直接从[!UICONTROL 代码管理器]为特定的报表包生成新的代码，而不是重复使用其他报表包的代码。这是确保正确填充 [!UICONTROL s.dc] 变量的最佳方式。

## 插件 {#section_53650E52D6A54A4795F95E491E7548D1}

有些客户通过实施插件来增强其 Adobe 体验。在替换代码时，请不要忘记插件也是该代码的一部分。[!UICONTROL 代码管理器]中创建的代码不会包含任何插件代码，因此需要将所有插件手动迁移到更新后的代码库中。制作一份现有代码的副本，以防发生意外，需要还原为以前的代码。
