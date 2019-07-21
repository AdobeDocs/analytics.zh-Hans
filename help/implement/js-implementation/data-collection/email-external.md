---
description: 公司使用 Analytics 来确定电子邮件促销活动的成功与否。
keywords: Analytics 实施
seo-description: 公司使用 Analytics 来确定电子邮件促销活动的成功与否。
seo-title: 外部电子邮件跟踪
solution: Analytics
title: 外部电子邮件跟踪
topic: 开发人员和实施
uuid: fa450f45-14cf-4d0d-a87 c-14a946512 a9 b
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 外部电子邮件跟踪

公司使用 Analytics 来确定电子邮件促销活动的成功与否。

[!DNL Analytics] 可报告以下几个关键量度的电子邮件促销活动分析数据：

| 量度 | 描述 |
|---|---|
| 点进次数 | 显示跟踪到的从电子邮件访问登陆页面的点进次数。 |
| 购买和/或成功 | 显示由电子邮件带来的购买数。 |
| 订购 | 显示由电子邮件带来的订购数。 |
| 收益 | 显示由电子邮件产生的每次访问的美元金额。 |
| 转化 | 显示由电子邮件产生的商机、注册或任何其他成功事件的数量。 |

需要对 HTML 电子邮件正文和 JavaScript 库进行修改，才能捕获上述关键量度。

## 实施 {#section_8A42A8F4A6CD4A1BAF4B9F99F709AF7A}

若要成功显示电子邮件促销活动分析数据，需要遵循几个步骤。步骤如下：

1. 创建唯一的跟踪代码。

   通常，用户会寻求每个唯一促销活动的跟踪建议。其实这完全取决于客户自己，主要看哪些代码使用效果最佳。每个用户的情况都不尽相同。Adobe 建议每个用户生成易记的跟踪代码，如以下示例所示：

   * sc_cid=A1123A321 &gt;“A”用于标记合作促销活动
   * sc_cid=EM033007 &gt;“EM”用于标记电子邮件促销活动
   * sc_cid=GG987123 &gt;“GG”表示 Google，是付费搜索促销活动
   请联系 Adobe [!DNL Customer Care]，以获取有关设置和使用跟踪代码的详细信息。

1. 向 HTML 电子邮件链接添加查询字符串参数。

   若要跟踪用户点进和后续成功事件，需要向 HTML 电子邮件中的每个链接添加查询字符串参数。您可选择分别跟踪每个链接，或同时跟踪所有链接。每个链接会有一个唯一的跟踪代码，或者所有链接使用相同的跟踪代码。请仔细研究以下从电子邮件中指向某网站的假设链接：

   ```js
   <a href="https://www.mycompany.com/index.asp">Visit our home page</a>
   ```

   应将以下查询字符串参数 ?sc_cid=112233B 添加到上面的链接：

   ```js
   <a href= "https://www.mycompany.com/index.asp?sc_cid=112233B">Visit our home page</a>
   ```

1. 更新 JavaScript 库。

   更改 JavaScript 文件 [!DNL s_code.js] 中的代码，可允许您捕获有多少用户（以及哪些用户）从电子邮件点进并参与后续成功事件。更新 JavaScript 库需分两步执行。

   1. Customize [!DNL s_code.js] by calling [!UICONTROL getQueryParam].

      [!DNL s_code.js] 文件应置于 Web 服务器上每个网页都可以访问的位置。The *`doPlugins`* function within this file should be altered so it captures the query string parameters on the email links. 例如：

      ```js
      /* Plugin Config */ 
      s.usePlugins=true 
      function s_doPlugins(s) { 
       /* Add calls to plugins here */ 
       // External Campaigns 
      s.campaign=s.getQueryParam('source') 
      } 
      s.doPlugins=s_doPlugins 
      ```

      每个需要复制到变量的查询字符串参数应调用一次 [!UICONTROL getQueryParam]。在以上示例中，查询字符串参数 [!UICONTROL sc_cid] 被复制到 *`campaign`*。

      仅需要第一次调用 [!UICONTROL getQueryParam] 来捕获点进次数。请联系 Adobe [!DNL Customer Care] 来实施此函数，并确保您的 JavaScript 文件版本包含 [!UICONTROL getQueryParam] 插件。

   1. 请确保“待粘贴代码”JavaScript 标签出现在所有登陆页面上。此待粘贴代码必须引用 A 部分中更改的 [!DNL s_code.js] 版本。

      在更新 JavaScript 库时，请记住以下要点。这些要点如下所示。

      * 查询字符串参数 [!UICONTROL sc_cid] 必须显示在最终登陆页面的 URL 中，否则不会记录任何点进转化。
      * [!UICONTROL sc_cid] 参数是一个示例查询字符串参数。[!UICONTROL getQueryParam] 插件可使用和捕获任何查询字符串参数。请确保查询字符串参数仅用于促销活动跟踪。任何时候，只要查询字符串中显示有参数，它们的值就会复制到 *`campaign`*。

1. 使用 [!UICONTROL SAINT] 划分促销活动跟踪代码。

   [!UICONTROL SAINT 促销活动管理工具]可用于将跟踪代码转换为用户易记的名称。它还可用于总结每个电子邮件促销活动的成功情况。以下步骤 5 概述了开展电子邮件促销活动所必需的过程。

1. 按电子邮件促销活动查看路径（可选）。

   电子邮件促销活动的路径分析与其他促销活动的路径分析类似。您可使用变量以按促销活动显示路径，如以下步骤所示：

   1. 请联系 Adobe [!DNL Customer Care]，以了解如何启用[!UICONTROL 自定义分析]变量 (prop) 的路径功能。

   1. 在所有页面上，将页面名称复制到指定的 [!DNL s.prop]。
   1. 在电子邮件登陆页面上，将电子邮件促销活动的名称附加到 prop 上。结果显示如下：

      ```js
      s.prop1="Home Page : 123456"
      ```

      在启用了[!UICONTROL 自定义分析]变量的路径功能之后，您可以使用[!UICONTROL 路径]报表（如[!UICONTROL 下一页面流量]或[!UICONTROL 流失]）来查看访客从登陆页面开始的导航情况。

