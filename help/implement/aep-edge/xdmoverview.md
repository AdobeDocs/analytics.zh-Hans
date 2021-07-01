---
title: 在 Analytics 中使用 XDM 数据
description: 在 Adobe Analytics 中使用源自 Experience Platform 的 XDM 数据概述
exl-id: 6f1282fb-8d4a-4d88-9be0-1c939c22cb92
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: ht
source-wordcount: '249'
ht-degree: 100%

---

# 在 Analytics 中使用 Adobe Experience Platform Edge 数据

您可以使用 [Adobe Experience Platform (AEP) Web SDK](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html?lang=zh-Hans) 将数据发送到 Adobe Analytics。实现方式是将[体验数据模型 (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-Hans) 转换为 Analytics 使用的某种格式。

Analytics 通过两种方法收集 XDM 数据：

* 从 XDM 架构自动映射
* 手动映射到上下文数据

## 自动映射

自动映射依赖于 XDM 中的一种默认[架构](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=zh-Hans)，该架构可自动填充典型 Analytics 数据收集中包含的 JSON 对象。从 XDM 自动映射到您配置的报表包的 Analytics 变量不需要任何开发人员支持就可以合并。

## 手动映射

[将 XDM 数据手动映射到 Analytics](xdm-manual.md) 依赖于 [Analytics 上下文数据](../vars/page-vars/contextdata.md)变量。这些变量将被放入与适用的架构相对应的 JSON 对象中。通常情况下，开发团队会在实施时添加上下文数据，然后管理员设置[处理规则](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md)，将上下文数据应用到指定的报表包。

## 设置

要设置 Analytics 以接收 XDM 数据，请执行以下操作：

1. 安装并[配置](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=zh-Hans) [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=zh-Hans)。

2. 确保将适用的报表包映射到您需要的数据。XDM 数据会自动从 Adobe Experience Platform 流向报表包。
