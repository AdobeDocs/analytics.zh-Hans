---
description: 帮助您回答以下问题“用户点击某一促销活动进入我的网站后，都浏览了哪些位置？”
keywords: Analytics 实施
seo-description: 帮助您回答以下问题“用户点击某一促销活动进入我的网站后，都浏览了哪些位置？”
seo-title: 营销活动或跟踪代码的路径
solution: Analytics
title: 营销活动或跟踪代码的路径
topic: 开发人员和实施
uuid: eb6e3444-1b40-4ec6-8017-ac1003 cdf636
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 营销活动或跟踪代码的路径

帮助您回答以下问题“用户点击某一促销活动进入我的网站后，都浏览了哪些位置？”

要解答此问题，需要留出一个 [!UICONTROL sprop] 变量，用于此报表。然后，您需要以一种有效的方式搭建数据结构，填充 prop，这样在启用路径分析后才能得到有意义的报表。

在此示例中，您将使用 [!UICONTROL prop1] 作为促销活动路径 prop。现在，您要填充此 [!UICONTROL sprop] 变量，使用的值与 [!UICONTROL page name] 变量所使用的值相同。请参阅以下代码：

```js
s.prop1=s.pageName;
```

您应当对所有页面采取此操作，但当用户从促销活动点击进入时除外。如果用户从促销活动点击进入促销活动的登陆页面，则需要将促销活动和 [!UICONTROL pagename] 串联起来填充 prop。请参阅以下代码：

```js
 s.prop1=s.campaign + ‘ : ’ + s.pageName;
```

如果用户点击的促销活动名为“banner1234”，而登陆页面的名称为“Home Page”，则为此 prop 填充的值即为“banner1234 : Home Page”。如上所示，再将每一个后续页面的 [!UICONTROL pagename] 放入 prop。

如果用户点击促销活动进入网站并陆续浏览四个页面后退出，则 sprop 会按此顺序排列值：

```js
“banner1234 : Home Page” > “Page 2” > “Page 3” > “Page 4”
```

借助以此方式捕获的 [!UICONTROL prop1] 数据，并对此 prop 启用路径分析，便可查看不同的路径报表，了解用户从促销活动点击进入网站后的浏览路径。

您可以指定路径报表的起始页面。在此例中，您选择了“banner1234 : Home Page”作为起始页，因为您想知道用户在点击促销活动“banner 1234”后都浏览了哪些位置。此报表只是众多路径报表中的一个示例。
