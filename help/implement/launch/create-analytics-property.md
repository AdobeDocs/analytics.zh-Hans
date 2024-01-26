---
title: 在标记中创建 Analytics 属性
description: 使用标记创建一个空间，以自定义数据的收集方式。
feature: Tags
exl-id: ffcd8e97-4d29-489e-bc2b-88805400dad5
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 100%

---

# 创建 Adobe Analytics 标记属性

使用 Adobe Experience Platform 中的标记，您可以在网站上集成 Experience Cloud 解决方案（包括 Analytics）。此页面专门概述了标记管理员如何正确配置基本的 Adobe Analytics 实施。

## 先决条件

[创建报表包](/help/admin/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md)：为要收集的 Analytics 数据创建一个容器。

## 创建标记属性并安装重要扩展

属性是用于管理标记的主要容器。通过扩展，您可以安装和配置特定于产品的标记。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection?lang=zh-Hans)。
1. 单击&#x200B;**[!UICONTROL 新建属性]**。
1. 为您的属性指定名称（如网站的标题），然后输入要在其中实施 Analytics 的域。单击&#x200B;**[!UICONTROL 保存]**。
1. 单击新创建的标记属性以输入其设置。
1. 单击&#x200B;**[!UICONTROL 扩展]**&#x200B;选项卡，然后单击&#x200B;**[!UICONTROL 目录]**。
1. 找到 &#39;Experience Cloud ID 服务&#39;，然后点击 **[!UICONTROL 安装]**.
1. 所有设置（包括 Experience Cloud 组织 ID）都应当已经填充。单击&#x200B;**[!UICONTROL 保存]**。
1. 返回扩展目录，找到 Adobe Analytics 并单击&#x200B;**[!UICONTROL 安装]**。

有关更多详细信息，请参阅 [Adobe Analytics 扩展](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=zh-Hans)完整文档。

## 为 Adobe Analytics 创建数据元素

数据元素是对网站特定部分的引用，以便收集变量值。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 单击要在网站上实施的标记属性。
1. 单击&#x200B;**[!UICONTROL 数据元素]**&#x200B;选项卡，然后单击&#x200B;**[!UICONTROL 添加新数据元素]**。
1. 为数据元素指定以下设置：

   * 名称：页面名称
   * 扩展：核心
   * 数据元素类型：JavaScript 变量
   * JavaScript 变量名称`window.document.title`

     >[!NOTE]
     >
     >此值可作为帮助入门的示例。如果您的组织为页面名称定义了更好的值（例如数据层值），则可以在此处输入该值。
   * 清理选中的文本
   * 存储持续时间：无
1. 单击&#x200B;**[!UICONTROL 保存]**。

## 为 Adobe Analytics 创建规则

规则会将数据元素映射到 Analytics 变量值，并确定何时将这些值发送到 Adobe 的服务器。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 单击要在网站上实施的标记属性。
1. 单击 **[!UICONTROL 规则]** 选项卡，然后单击 **[!UICONTROL 添加规则]**。将其命名为 `Global Rule`。
1. 单击事件旁边的&#x200B;**[!UICONTROL 添加]**，然后输入以下设置：
   * 扩展：核心
   * 事件类型：已加载的库（页面顶部）
   * 名称：核心 - 已加载的库（页面顶部）
1. 单击&#x200B;**[!UICONTROL 保留更改]**。
1. 在&#x200B;**[!UICONTROL 操作]**&#x200B;下，单击&#x200B;**[!UICONTROL 添加]**，然后输入以下设置：
   * 扩展：Adobe Analytics
   * 操作类型：设置变量
   * 页面名称：单击容器图标，然后选择 `Page Name` 数据元素。
   * 促销活动：值为 `cid` 的查询参数
1. 单击&#x200B;**[!UICONTROL 保留更改]**。
1. 单击操作旁边的加号以添加其他操作，然后输入以下设置：
   * 扩展：Adobe Analytics
   * 操作类型：发送信标
   * 名称：Adobe Analytics - 发送信标
   * 跟踪：s.t()
1. 单击&#x200B;**[!UICONTROL 保留更改]**。
1. 验证是否已设置事件和两个操作，然后单击&#x200B;**[!UICONTROL 保存]**。

## 后续步骤

[将 Analytics 实施部署到开发环境](deploy-dev.md)：获取可在测试环境中运作的 Analytics 代码。
