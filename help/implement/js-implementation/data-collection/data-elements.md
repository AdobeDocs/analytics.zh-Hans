---
description: 您可以将表单元素（例如单选按钮和复选框项目）的值捕获到报表中。这可帮助您分析在线表单中最受欢迎的选项。
keywords: Analytics 实施
seo-description: 您可以将表单元素（例如单选按钮和复选框项目）的值捕获到报表中。这可帮助您分析在线表单中最受欢迎的选项。
seo-title: 收集表单元素中的数据
solution: Analytics
title: 收集表单元素中的数据
topic: 开发人员和实施
uuid: e0c13b96-e1 ca-4744-a912-60ca2 f25 c3
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 收集表单元素中的数据

您可以将表单元素（例如单选按钮和复选框项目）的值捕获到报表中。这可帮助您分析在线表单中最受欢迎的选项。

例如，如果有一个单选按钮允许用户指定他/她喜爱的音乐风格（例如摇滚、说唱、古典或爵士），则可以在变量中捕获此响应以确定用户群的总体音乐偏好。

捕获此数据的最佳方法取决于表单的处理方式。还取决于表单提交后进入的页面上的查询字符串中是否提供有您要捕获的表单选项。本文中的示例采用 PHP 语言。但是，您可以根据您的服务器环境将这些概念调整为其他语言。

此信息适用于熟悉报表和实施的高级用户。在没有完全了解后果之前请勿尝试对您的实施进行任何编辑。如果您要对实施进行更改，请联系贵组织的客户经理。

## GET 方法 {#section_7A2B35822BFF4F6EB57940B31AE6303A}

如果您的表单使用 [!UICONTROL GET] 方法提交数据，则可以从表单提交后所进入页面上的 URL 查询字符串中获取所需的数据。您可以使用[!UICONTROL getQueryParam] 插件从查询字符串自动捕获此数据，并将该数据置于您所选的变量中。

## POST 方法 {#section_56715C30EF374BA7AA12B946B50E4A9A}

如果您的表单使用 [!UICONTROL POST] 方法提交数据（此情况更为常见），则可在 [!UICONTROL $_POST superglobal] 中找到每个特定表单元素的结果。若要在变量中捕获此数据，请先确定当前表单元素的名称。如果使用上述音乐风格作为示例，则当前部分表单元素类似于：

```
<input type="radio" name="music_genre" value="rock">
```

该单选按钮属于 "music_genre" 表单元素。You then have access to the user's selected value by using $_POST['music_genre']. 可将该值写入表单提交后进入的页面上的变量中：

```js
s.eVar1="<?=$_POST['music_genre'];?>"
```

[!UICONTROL eVar1] 变量可根据 value= 属性中指定的值接收通过表单提交到服务器的任意值的副本。

如果您需要了解有关此自定义实施方法的其他信息，请联系贵组织的客户经理。他们会安排 Adobe 实施顾问与您进行会谈，以便为您提供帮助。
