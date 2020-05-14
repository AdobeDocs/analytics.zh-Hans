---
title: 将XDM数据与Analytics结合使用
description: '在Adobe Analytics中使用Experience Platform中的XDM数据概述 '
translation-type: tm+mt
source-git-commit: 3526d9f98b545e5f720a0cb127857e7fd5d5388e
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 4%

---


# 将Adobe Experience Platform Edge数据与Analytics结合使用

您可以使用 [Adobe Experience Platform(AEP)Web SDK](https://docs.adobe.com/content/help/zh-Hans/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html) ，将数据发送到Adobe Analytics。 这通过将体验数 [据模型(XDM)转换为](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html) Analytics使用的格式来实现。

Analytics通过两种方法收集XDM数据：

* 从XDM模式自动映射

* 手动映射到上下文数据

## 自动映射

[自动映射](https://git.corp.adobe.com/AdobeDocs/analytics.en/blob/master/help/implement/aep-edge/xdm-manual.md) 依赖于XDM中 [的默认](https://docs.adobe.com/content/help/en/experience-platform/xdm/schema/composition.html) 模式，该可自动填充典型Analytics数据收集中包含的JSON对象。 从 [XDM自动映射到您配置的报表包的](https://git.corp.adobe.com/analytics-data-collection/anedge/blob/master/XDM_Translator.md) Analytics变量不需要任何开发人员支持。

## 手动映射

将XDM数据手动映射到Analytics需要依 [赖Analytics上下文数据](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/contextdata.html) 变量。 这些变量将放入与适用模式对应的JSON对象中。 通常，开发团队在实施时添加上下文数据，然后管理员设 [置处理规则](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/t-processing-rules.html) ，将该数据应用到指定的报表包。


## 设置

要设置Analytics以接收XDM数据，请执行以下操作：

1. 安装 [和配](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/configuring-the-sdk.html)[置Adobe Experience Platform Web SDK](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/installing-the-sdk.html)。

2. 确保将适用的报表包映射到您需要的数据。 XDM数据自动从Adobe Experience Platform流向报表包。

