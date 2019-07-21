---
description: “自定义分析转化变量”（或 eVar）置于您网站所选网页的 Adobe 代码中。其主要目的是在自定义市场营销报告中划分转化成功量度区段。
keywords: Analytics实施；eVar；转换变量；eVar值；转换；success事件
seo-description: “自定义分析转化变量”（或 eVar）置于您网站所选网页的 Adobe 代码中。其主要目的是在自定义市场营销报告中划分转化成功量度区段。
seo-title: 转换变量(eVar)
solution: Analytics
title: 转换变量(eVar)
topic: 开发人员和实施
uuid: 50071c1c-be00-4b3 a-a7 ee-5d129 acf498 b
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 转换变量(eVar)

“自定义分析转化变量”（或 eVar）置于您网站所选网页的 Adobe 代码中。其主要目的是在自定义市场营销报告中划分转化成功量度区段。

eVar 最适合用于度量原因和影响，例如：

* 哪些内部促销活动会影响收入
* 哪些横幅广告最终会导致用户注册
* 在下订单前所用的内部搜索次数

>[!IMPORTANT]
>
>实施Analytics时，务必了解您将使用哪些eVar以及多少。此外，您还应了解如何在 Admin Console 中配置这些 eVar。有关 eVar 的详细信息，请参阅“Analytics 帮助和参考”文档中的[转化变量 (eVar)](https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html)。

eVar 可以是基于访问的，其功能与 Cookie 类似。在预先设定的一段时间内，传递到 eVar 变量的值将始终“跟随”着用户。

为访客设置 eVar 值之后，Adobe 会自动记住该值，直到它过期。eVar 值处于活动状态时，访客遇到的成功事件将计入该 eVar 值。

>[!NOTE]
>
>只有一个值可存储在图像请求中的eVar中。如果一个 eVar 值中需要多个值，我们建议您实施[](/help/implement/js-implementation/c-variables/page-variables.md)列表变量 (list vars)。

有关变量的更多信息，请参阅：

* [适用于 Analytics 实施和报告的变量](../../implement/js-implementation/c-variables/sc-variables.md#concept_E10E43221A2740FAAF900B79CE1EC5FB)（位于本帮助文档中）
* [变量 - 如何在报表中使用变量](https://marketing.adobe.com/resources/help/en_US/reference/variable_definitions.html)
* [页面变量](/help/implement/js-implementation/c-variables/page-variables.md)
* [营销活动变量](/help/implement/js-implementation/c-variables/page-variables.md)
* [产品变量](/help/implement/js-implementation/c-variables/page-variables.md)
* [产品变量](https://marketing.adobe.com/resources/help/en_US/mobile/android/products.html)（位于 Mobile SDK 文档中）

