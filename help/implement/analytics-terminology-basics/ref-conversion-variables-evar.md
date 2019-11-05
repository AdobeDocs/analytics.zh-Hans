---
description: “自定义分析转化变量”（或 eVar）置于您网站所选网页的 Adobe 代码中。其主要目的是在自定义市场营销报告中划分转化成功量度区段。
keywords: Analytics 实施;eVar;转化变量;eVar 值;转化;成功事件
seo-description: “自定义分析转化变量”（或 eVar）置于您网站所选网页的 Adobe 代码中。其主要目的是在自定义市场营销报告中划分转化成功量度区段。
seo-title: 转化变量 (eVar)
solution: Analytics
title: 转化变量 (eVar)
topic: 开发人员和实施
uuid: 50071c1c-be00-4b3a-a7ee-5d129acf498b
translation-type: tm+mt
source-git-commit: 57fe1f6d613b9f54a5191ac8684d36bccfebf4e5

---


# 转化变量 (eVar)

“自定义分析转化变量”（或 eVar）置于您网站所选网页的 Adobe 代码中。其主要目的是在自定义市场营销报告中划分转化成功量度区段。

eVar 最适合用于度量原因和影响，例如：

* 哪些内部促销活动会影响收入
* 哪些横幅广告最终会导致用户注册
* 在下订单前所用的内部搜索次数

>[!IMPORTANT]
>
>在实施 Analytics 时，务必要知道要使用哪些 eVar 以及数量。此外，您还应了解如何在 Admin Console 中配置这些 eVar。有关 eVar 的详细信息，请参阅“Analytics 帮助和参考”文档中的[转化变量 (eVar)](https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html)。

eVar 可以是基于访问的，其功能与 Cookie 类似。在预先设定的一段时间内，传递到 eVar 变量的值将始终“跟随”着用户。

为访客设置 eVar 值之后，Adobe 会自动记住该值，直到它过期。eVar 值有效期间，访客遇到的任何成功事件将计入该 eVar 值。

> [!NOTE]在图像请求中，一个 eVar 中只能存储一个值。如果一个 eVar 值中需要多个值，我们建议您实施[](/help/implement/js-implementation/c-variables/page-variables.md)列表变量 (list vars)。

有关变量的更多信息，请参阅：

* [适用于 Analytics 实施和报告的变量](/help/implement/js-implementation/c-variables/sc-variables.md)（位于本帮助文档中）
* [变量 - 如何在报表中使用变量](https://marketing.adobe.com/resources/help/en_US/reference/variable_definitions.html)
* [页面变量](/help/implement/js-implementation/c-variables/page-variables.md)
* [促销活动变量](/help/implement/js-implementation/c-variables/page-variables.md)
* [产品变量](/help/implement/js-implementation/c-variables/page-variables.md)
* [产品变量](https://marketing.adobe.com/resources/help/en_US/mobile/android/products.html)（位于 Mobile SDK 文档中）

