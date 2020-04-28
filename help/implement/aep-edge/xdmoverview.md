---
title: 将XDM数据与Analytics结合使用
description: '在Adobe Analytics中使用Experience Platform中的XDM数据概述 '
translation-type: tm+mt
source-git-commit: 31efa43043120b68de90e817a7980addbe2ded39

---




# 将Adobe Experience Platform Edge数据与Analytics结合使用

>[!IMPORTANT]
>
>Adobe Experience Edge Web SDK不发布，仅适用于受邀客户的测试版测试。 本文档仅面向测试版用户，并不代表完整的功能。如果您有兴趣成为此功能的测试版用户，请联系 Adobe
[客户关怀团队](https://helpx.adobe.com/cn/contact/enterprise-support.ec.html)。


您可以使用 [Adobe Experience Platform(AEP)Web SDK](https://docs.adobe.com/content/help/zh-Hans/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html) ，将数据发送到Adobe Analytics。 这通过将体验数 [据模型(XDM)转换为Analytics使用的格式](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html) 来实现。

Analytics通过两种方法收集XDM数据：

* 从XDM模式自动映射

* 手动映射到上下文数据

## 自动映射

自动映射依赖于XDM中的默 [认模式](https://docs.adobe.com/content/help/en/experience-platform/xdm/schema/composition.html) ，该可自动填充典型Analytics数据收集中包含的JSON对象。 从XDM [](https://git.corp.adobe.com/analytics-data-collection/anedge/blob/master/XDM_Translator.md) 自动映射到您配置的报表包的Analytics变量不需要任何开发人员支持。

## 手动映射

将XDM数据手动映射到Analytics取决于 [Analytics上下文数据变量](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/contextdata.html) 。 这些变量将放入与适用模式对应的JSON对象中。 通常，开发团队在实施时添加上下文数据，然后管理员设置处 [理规则](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/t-processing-rules.html) ，以将该数据应用到指定的报表包。


## 设置

要设置Analytics以接收XDM数据，请执行以下操作：

1. 安装 [和配](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/configuring-the-sdk.html)[置Adobe Experience Platform Web SDK](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/installing-the-sdk.html)。

2. 确保将适用的报表包映射到所需数据。 XDM数据自动从Adobe Experience Platform流向报表包。

