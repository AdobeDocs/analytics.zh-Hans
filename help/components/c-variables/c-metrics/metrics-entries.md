---
description: 条目表示将给定值捕获为访问中第一个值的次数。 每次访问只能出现一次条目。 但是，如果未定义变量，它不一定是第一次点击。
title: 登录
topic: Metrics
uuid: c4608b66-b70c-4e98-b7c6-9be5fbe4ec9c
translation-type: tm+mt
source-git-commit: e6aaf2754c6a5c33fbe3e093b4d7ca5a375c41e7

---


# 登录

“条目”表示将给定值捕获为访问中第一个值的次数。 每次访问只能出现一次条目。 但是，如果未定义变量，它不一定是第一次点击。

在分析工作区中，自2020年3月起，我们更改了“无”值与“登入／退出”的交互方式。  由于您现在可以在分析工作区中打开和关闭“无”，因此在进入或退出后，我们会应用“无”，而（对于evar）以前会应用它。  例如，假设访问的第一次点击对eVar21没有任何值，但第二次点击对eVar21没有。 在Reports &amp; Analytics中，它将对条目显示为“未指定”，但在分析工作区中，它将在第二次点击时显示为值。

条目页面具有访问细分范围，这意味着它们会在访问的所有点击中持续存在。 有关更 [多信息，请参阅细分和细分容器](https://marketing.adobe.com/resources/help/en_US/sc/user/c_Breakdown_and_segmentation_containers.html) 。
