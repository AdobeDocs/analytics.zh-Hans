---
description: 使用动态标签管理可添加页眉和页脚代码，以便确定 JavaScript 和页面内容在网站上的加载情况。无论使用何种托管选项，您都必须在网站的每个页面上同时安装页眉和页脚代码。
keywords: Analytics实施；实施方法；动态标签管理；dm；代码；页面代码；标题代码；页脚代码；嵌入代码；嵌入选项卡；嵌入
seo-description: 使用动态标签管理可添加页眉和页脚代码，以便确定 JavaScript 和页面内容在网站上的加载情况。无论使用何种托管选项，您都必须在网站的每个页面上同时安装页眉和页脚代码。
seo-title: 添加页眉和页脚代码
solution: Analytics
title: 添加页眉和页脚代码
topic: 开发人员和实施
uuid: 23d89ae0-340a-4b12-91d1-953b4613c98e
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 添加页眉和页脚代码

使用动态标签管理可添加页眉和页脚代码，以便确定 JavaScript 和页面内容在网站上的加载情况。无论使用何种托管选项，您都必须在网站的每个页面上同时安装页眉和页脚代码。

由于动态标签管理在您的页眉和页脚中均包含一个代码片段，因此您可以在页面的开头或结尾运行规则。此功能允许您实施测试工具和其他技术，同时保留对页面跟踪的控制。

动态标签管理会创建暂存和生产两种嵌入代码，在将所做更改推送到生产环境之前，您可以在暂存环境中使用已创建的暂存和生产嵌入代码对所做更改进行测试。

>[!IMPORTANT]
>
>为了成功实施，您必须按照这些说明操作，就像在Adobe帮助中一样。Specifically, you must place the header code in the `<head>` section of your document templates. Also, you must place the footer code just before the closing `</body>` tag. 将任一嵌入代码放置在标记中的其他位置、使用异步方法附加嵌入代码，或者通过任何方式使嵌入代码换行，都“不”是受支持的动态标签管理实施。**&#x200B;必须完全按照提供的样式实施嵌入代码。
>
>不受支持的实施会产生意外结果，从而使得客户关怀团队和工程人员无法针对您的实施提供帮助。

1. 在“动态标签管理”界面中，打开“[!UICONTROL 嵌入]”选项卡，选择托管选项（例如 Akamai），然后将开关切换到“启用”。

   Step Result1.复制动态标签管理“嵌入”选项卡中提供的生产页眉代码，然后将其置于您网站 HTML 的 [!DNL HEAD] 部分。

   ![](assets/dtm-embed.png)

   Place the code as close to the [!DNL <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">]开始标记的位置。应当将此代码片段放在实时生产网站的每个页面中。

   >[!NOTE]
   >
   >Production embed code reflects only the published items in that [property](../../../implement/c-implement-with-dtm/t-create-web-property.md#task_960467FBB7A54499AC228CB3AA3C4123). 但是，用于暂存的嵌入代码将反映关联属性中的所有项，而不考虑它们是处于已发布状态还是未发布状态。要在您的生产网站上测试未发布项，请按照[测试 Akamai 托管的未发布规则](../../../implement/c-implement-with-dtm/c-rules/t-test-rules-akamai.md#task_B397167F9E9B4487957AD6CE2AD47259)中的说明进行操作，以便从本地在控制台中启用暂存。

1. 复制生产页脚代码，并将其置于网站 HTML 的 [!DNL BODY] 部分中。

   Place the code as close to the [!DNL </body>]开始标记的位置。
1. 复制暂存页眉和页脚代码，然后在您的暂存网站中重复以上步骤。

   >[!NOTE]
   >
   >The difference between production and staging code snippets is the addition of [!DNL -staging] to the filename in the staging version. 页脚代码在暂存和生产中保持相同。

