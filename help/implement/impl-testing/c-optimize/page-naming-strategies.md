---
description: pageName 变量应使用简明而直观的页面标识符填充。
keywords: Analytics 实施
seo-description: pageName 变量应使用简明而直观的页面标识符填充。
seo-title: 页面命名策略
solution: Analytics
title: 页面命名策略
topic: 开发人员和实施
uuid: a829d0c7-6ebf-459a-b403-5e9 c05161 e5 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 页面命名策略

pageName 变量应使用简明而直观的页面标识符填充。

You can determine the best way of populating the *`pageName`* variable by looking at the structure of your website. The methods listed below outline various ways of populating the *`pageName`* variable.

*`pageName`* 虽然变量是识别用户行为的核心，但Adobe建议使用多个变量来指示页面信息。最佳页面命名策略对网站层级的各级别使用不同的变量，如下所示：

* The *`channel`*&#x200B;变量可用于表示网站区域。
* *`pageName`* 该变量可用于显示内容类型。
* [!UICONTROL 自定义分析]变量 (prop1) 可用于表示详细内容。

详细程度因属性而有所不同，如下所示：

| 变量 | 详细程度 | 示例 |
|---|---|---|
| Channel | 一般区域 | 电子产品 |
| Prop1 | 子区域 | 体育：地方体育 |
| PageName | 一般内容描述 | 贷款：房屋贷款：利率比较 |
| Prop2 | 详细内容描述 | 电子产品：笔记本：详细规格：IBM Thinkpad T20 |

网站层级越多，用于识别页面内容的变量也应越多。若允许变量重叠，对公司也非常有用。例如，一个较为详细的变量不仅可以包含所查看产品的信息，还可包含有关网站区域和子区域的信息。当某产品或文章在网站的多个区域中出现时，这会非常有用。

以下页面命名策略描述如何填充&#x200B;*`pageName`* 变量。虽然大家倾向于选择最容易实施的页面命名策略，但是页面命名策略在相当大的程度上决定了所有[!UICONTROL 路径]及[!UICONTROL 页面]报表的可用性。在决定页面的命名方法时需仔细进行判断。

## 每个页面的唯一名称 {#section_24704CA39E2F4C00ACEAFF39CA0A921B}

最佳的页面命名方法是为每个页面指定组织内所有 [!DNL Analytics] 用户都容易理解的唯一标识符。页面名称的示例包括“主页”、“电子产品部门主页”和“体育：地方体育：高中”。

大多数 [!DNL Analytics] 用户发现，层级页面名称在识别页面在网站中的发现位置及其目的时都十分有用。下表显示不同行业的页面名称示例。

| 转化 | 媒体 | 金融 |
|---|---|---|
| 主页 | 主页 | 主页 |
| 电子产品 | 技术 | 房屋贷款 |
| 电子产品：笔记本 | 技术：新配件 | 房屋贷款：利率比较 |
| 电子产品：笔记本：产品页面 | 技术：新配件：文章页面 | 房屋贷款：利率比较：10 年定期 |

## 文件路径（非完整 URL） {#section_37FDCDA00DA84B3D9B8AB4290555FF34}

一些网站的文件路径清晰，因而易于读取。任何企业用户都可读取 URL 并确定文件路径指向的页面。如果您的网站属于此类情况，则可使用服务器端变量向&#x200B;*`pageName`*&#x200B;变量填充文件路径，如下所示：

```js
s.pageName="<%= file_path %>"
```

Adobe does not recommend leaving the *`pageName`* blank, (which results in using the full URL of the page) even though you may be tempted to do so. The following side-effects are caused by leaving the *`pageName`* variable blank and using the *`pageURL`* as the page identifier.

* 页面的域与路径不会始终显示一致。例如，下面四个 URL 返回的是同一个页面：

   * `https://www.mysite.com/index.jsp`
   * `https://www.mysite.com`
   * `https://mysite.com/index.jsp`
   * `https://mysite.com/`
   If the *`pageName`* is left blank, each of these page names would occupy a separate entry in reports.

* 一些页面（例如表单）是自行发布的，这样会消除原始表单和输出结果之间的区别。
* 使用搜索引擎或其他在线工具将页面翻译成另一种语言时，该页面的 URL 将变成搜索引擎的 URL（而非您网站的 URL）。

## HTML (document.title) {#section_B99B8F66B0E2410FA7BFE44E6851EB3F}

If you have invested time into making your HTML titles readable and intuitive, you might consider using the same title as the value in the *`pageName`* variable. Adobe recommends using a server-side variable to populate the *`pageName`* rather than using JavaScript's [!DNL document.title]. 不同浏览器对 HTML 标题的解释有所不同，这可能会导致 [!DNL Analytics] 从不同的浏览器接收到不同的页面名称。

使用 HTML 标题的最佳方法是，将每个页面的现有标题复制到单独的变量或内容管理元素中。如果决定更改 HTML 标题以实现搜索引擎优化或其他目的，[!DNL Analytics] 页面名称将不会受到影响。如果 [!DNL Analytics] 中的页面名称发生更改，则该页面会变成新的页面，即使 URL 关联，也与旧的页面名称无关。
