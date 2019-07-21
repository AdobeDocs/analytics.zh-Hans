---
description: 下表包含迁移实施所需执行的任务列表。
keywords: Analytics实施；appasurement；迁移；迁移；javascript
seo-description: 下表包含迁移实施所需执行的任务列表。
seo-title: 迁移到 AppMeasurement for JavaScript
solution: Analytics
subtopic: JavaScript AppMeasurement
title: 迁移到 AppMeasurement for JavaScript
topic: 开发人员和实施
uuid: 5s345a85-4175-a2 e6-97139b9 b46 ce
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# 迁移到 AppMeasurement for JavaScript

下表包含迁移实施所需执行的任务列表。

>[!NOTE]
>
>We recommend migrating to the [Identity Service](../../../implement/js-implementation/c-unique-visitors/visid-service.md#concept_230F8759826E47789EA8DEE08FA09B07) when you migrate to [!DNL AppMeasurement] for JavaScript.

![](assets/step1_icon.png) 检查插件兼容性

在何处：s\_ code. js

不再支持某些插件。See [AppMeasurement Plug-in Support](../../../implement/js-implementation/c-appmeasurement-js/plugins-support.md#concept_E31A189BC8A547738666EB5E00D2252A) .

![](assets/step2_icon.png) 下载新的 AppMeasurement

在何处：管理员&gt;代码管理器

下载的 zip 文件中包含一个压缩的 AppMeasurement.js 文件，以及用于媒体和集成模块的 Javascript 文件。

![](assets/step3_icon.png) 将s\_ code. js自定义复制 `AppMeasurement.js`到。

在何处：s\_ code. js和AppMeasurement. js

Move all code that appears before the `DO NOT ALTER ANYTHING BELOW THIS LINE` section in s\_code.js to the beginning of AppMeasurement.js.

![](assets/step4_icon.png) (可选)更新插件

在何处：AppMeasurement. js

If you are using the getQueryParam plug-in, update these calls to use the new utility, [Util.getQueryParam](../../../implement/js-implementation/util-getqueryparam.md#concept_763AD2621BB44A3990204BE72D3C9FA5).

![](assets/step5_icon.png) (可选)更新媒体和集成模块

在何处：AppMeasurement. js

If you are using either of these modules, copy and paste the code from AppMeasurement\_Module\_Media.js and/or AppMeasurement\_Module\_Integrate.js and paste it just before the `DO NOT ALTER ANYTHING BELOW THIS LINE` in AppMeasurement.js.

![](assets/step6_icon.png) 部署新的 JavaScript

在何处：您的网站

您可以根据您的标准过程部署新的 JavaScript 文件。现有页面代码与此版本兼容。