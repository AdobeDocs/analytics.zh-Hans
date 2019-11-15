---
description: 使用动态标签管理可添加页眉和页脚代码，以便确定 JavaScript 和页面内容在网站上的加载情况。无论使用何种托管选项，您都必须在网站的每个页面上同时安装页眉和页脚代码。
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;code;page code;header code;footer code;embed code;embed tab;embed
solution: Analytics
title: 添加页眉和页脚代码
topic: Developer and implementation
uuid: 23d89ae0-340a-4b12-91d1-953b4613c98e
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 添加页眉和页脚代码

使用动态标签管理可添加页眉和页脚代码，以便确定 JavaScript 和页面内容在网站上的加载情况。无论使用何种托管选项，您都必须在网站的每个页面上同时安装页眉和页脚代码。

由于动态标签管理在您的页眉和页脚中均包含一个代码片段，因此您可以在页面的开头或结尾运行规则。此功能允许您实施测试工具和其他技术，同时保留对页面跟踪的控制。

动态标签管理会创建暂存和生产两种嵌入代码，在将所做更改推送到生产环境之前，您可以在暂存环境中使用已创建的暂存和生产嵌入代码对所做更改进行测试。

>[!IMPORTANT]
>
>对于成功的实施，关键是要按照 Adobe 帮助中显示的说明进行操作。具体而言，必须在文档模板的 `<head>` 部分中放置页眉代码。同时，还必须在结束 `</body>` 标记之前放置页脚代码。将任一嵌入代码放置在标记中的其他位置、使用异步方法附加嵌入代码，或者通过任何方式使嵌入代码换行，都“不”是受支持的动态标签管理实施。**&#x200B;必须完全按照提供的样式实施嵌入代码。
>
>不受支持的实施会产生意外结果，从而使得客户关怀团队和工程人员无法针对您的实施提供帮助。

1. 在“动态标签管理”界面中，打开“[!UICONTROL 嵌入]”选项卡，选择托管选项（例如 Akamai），然后将开关切换到“启用”。

   步骤结果 1. 复制动态标签管理“嵌入”选项卡中提供的生产页眉代码，然后将其置于您网站 HTML 的 [!DNL HEAD] 部分。

   ![](assets/dtm-embed.png)

   将代码放在靠近 [!DNL  的位置<head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">] 标记的位置包含了完整的页眉代码。应当将此代码片段放在实时生产网站的每个页面中。

   >[!NOTE]
   >
   >生产嵌入代码仅反映该[属性](/help/implement/c-implement-with-dtm/t-create-web-property.md)中发布的项。但是，用于暂存的嵌入代码将反映关联属性中的所有项，而不考虑它们是处于已发布状态还是未发布状态。要在您的生产网站上测试未发布项，请按照[测试 Akamai 托管的未发布规则](/help/implement/c-implement-with-dtm/c-rules/t-test-rules-akamai.md)中的说明进行操作，以便从本地在控制台中启用暂存。

1. 复制生产页脚代码，并将其置于网站 HTML 的 [!DNL BODY] 部分中。

   将代码放在靠近 [!DNL  的位置</body>] 标记的位置包含了完整的页眉代码。
1. 复制暂存页眉和页脚代码，然后在您的暂存网站中重复以上步骤。

   >[!NOTE]
   >
   >生产和暂存代码片段的区别在于，暂存版本的文件名后面附加有 [!DNL -staging]。页脚代码在暂存和生产中保持相同。

