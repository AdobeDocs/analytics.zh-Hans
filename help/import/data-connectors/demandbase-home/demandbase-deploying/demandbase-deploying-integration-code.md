---
description: 完成集成向导后，您必须将集成代码部署到Adobe Analytics部署代码(s_ code)。
seo-description: 完成集成向导后，您必须将集成代码部署到Adobe Analytics部署代码(s_ code)。
seo-title: 部署集成代码
title: 部署集成代码
uuid: b3fbda0b-4ed3-4967-84ee-6c66564606e7
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# 部署集成代码{#deploying-the-integration-code}

完成集成向导后，您必须将集成代码部署到Adobe Analytics部署代码(s_ code)。

>[!NOTE]
>
>如果使用Adobe TagManager或Dynamic Tag Management部署Adobe Analytics，则可以使用其中一种工具轻松添加集成代码。

1. 转到 **[!UICONTROL “支持]** ”选项卡，并从集成的“资源”区域下载并保存 `integration code v2_0_1` 资源。

1. 如果适用，请对代码进行必要的修改，有关详细信息，请参阅 [修改集成代码](../../demandbase-home/demandbase-deploying/demandbase-deploying-integration-code.md#concept-2e9e56282c9940d78e879aa45f70d855)。
1. 如果您的Adobe Analytics部署代码中没有集成模块，请包含集成模块。有关更多信息，请参阅 [包含集成模块](../../demandbase-home/demandbase-deploying/demandbase-including-integrate-module.md#concept-2cc81dff010a4da89b097a59476f8b6e)。
1. 使用以下方法之一部署代码：

   * 使用Adobe TagManager或Dynamic Tag Management添加代码。
   * 或者，向负责更新Adobe Analytics部署代码的组织资源发送代码。

>[!IMPORTANT]
>
>在部署到生产环境之前，确保您在开发/阶段环境中测试了此集成的部署。

