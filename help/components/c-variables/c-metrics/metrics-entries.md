---
description: 登录次数表示作为访问中第一个值所捕获到的给定值的次数。登录在每次访问中只能发生一次。但是，如果未定义变量，则它不一定是首次点击。
title: 登录
topic: Metrics
uuid: c4608b66-b70c-4e98-b7c6-9be5fbe4ec9c
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# 登录

“条目”表示将给定值捕获为访问中第一个值的次数。 登录在每次访问中只能发生一次。但是，如果未定义变量，则它不一定是首次点击。

在 Analysis Workspace 中，从 2020 年 3 月起，我们更改了“无”值与“登入”/“退出”的交互方式。由于您现在可以在分析工作区中打开和关闭“无”，因此在进入或退出后，我们会应用“无”，而（对于evar）以前会应用它。  例如，假设访问的第一次点击对eVar21没有任何值，但第二次点击对eVar21没有。 在 Reports &amp; Analytics 中，它将对“登入”显示为“未指定”，但在 Analysis Workspace 中，它将在第二次点击时显示为值。

登录页面包含一个访问划分范围，表示这些页面在一次访问的所有点击中一直存留。请参阅[划分和分段容器](https://docs.adobe.com/content/help/en/analytics/components/segmentation/seg-overview.html)以了解详细信息。
