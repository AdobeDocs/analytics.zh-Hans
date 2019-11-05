---
description: 下表包含迁移实施所需执行的任务列表。
keywords: Analytics 实施;appmeasurement;迁移;迁移;javascript
seo-description: 下表包含迁移实施所需执行的任务列表。
seo-title: 迁移到 AppMeasurement for JavaScript
solution: Analytics
subtopic: JavaScript AppMeasurement
title: 迁移到 AppMeasurement for JavaScript
topic: 开发人员和实施
uuid: 5be345a8-5a95-4176-a2e6-97139b9b46ce
translation-type: tm+mt
source-git-commit: 2fc1a01aced4cf2b165b46353418fbee9b83bee5

---


# 迁移到 AppMeasurement for JavaScript

下表包含迁移实施所需执行的任务列表。

>[!NOTE]
>
>当您迁移到 [!DNL AppMeasurement] for JavaScript 时，我们建议您迁移到 [Identity Service](/help/implement/js-implementation/c-unique-visitors/visid-service.md)。

![](assets/step1_icon.png) 检查插件兼容性

其中：s\_code.js

不再支持某些插件。请参阅 [AppMeasurement 插件支持](/help/implement/js-implementation/c-appmeasurement-js/plugins-support.md)。

![](assets/step2_icon.png) 下载新的 AppMeasurement

其中：“管理员”&gt;“代码管理器”

下载的 zip 文件中包含一个压缩的 AppMeasurement.js 文件，以及用于媒体和集成模块的 Javascript 文件。

![](assets/step3_icon.png) 将 s_code.js 自定义设置复制到 `AppMeasurement.js`。

其中：s_code.js 和 AppMeasurement.js

将 s_code.js 中显示在 `DO NOT ALTER ANYTHING BELOW THIS LINE` 部分之前的所有代码移动到 AppMeasurement.js 的起始位置。

![](assets/step4_icon.png)（可选）更新插件

其中：AppMeasurement.js

如果您要使用 getQueryParam 插件，请更新这些调用以使用新工具 [Util.getQueryParam](/help/implement/js-implementation/util-getqueryparam.md)。

![](assets/step5_icon.png)（可选）更新媒体和集成模块

其中：AppMeasurement.js

如果您要使用这两个模块的任何一个，请复制 AppMeasurement\_Module\_Media.js 和/或 AppMeasurement\_Module\_Integrate.js 中的代码，并将其粘贴到 AppMeasurement.js 中的 `DO NOT ALTER ANYTHING BELOW THIS LINE` 之前。

![](assets/step6_icon.png) 部署新的 JavaScript

其中：您的网站

您可以根据您的标准过程部署新的 JavaScript 文件。现有页面代码与此版本兼容。
