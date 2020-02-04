---
title: JavaScript实施疑难解答
description: 了解JavaScript实施疑难解答的常见问题和最佳做法。
translation-type: tm+mt
source-git-commit: 8aa6932dcbb6dad88c27ba1cd4f5aad3bafcfc52

---


# JavaScript实施疑难解答

以下是贵组织在将数据正确导入Adobe Analytics时可能遇到问题的几个原因。

## 使用引号

发送到Adobe的大多数变量都是字符串。 在JavaScript中，可以使用单引号或双引号。

### 混合引号以定义变量

作为最佳实践，请确保您的报价类型与您使用的报价类型一致。 如果单引号指定了字符串的开头，则必须使用单引号将其关闭。

例如，和 `s.eVar1 = 'Value'` 都 `s.eVar1 = "Value"` 有效。 `s.eVar1 = 'Value"` 无效.

### 在字符串中包括单引号或双引号

有时，需要在字符串中包含单引号或双引号。 例如，您希望将值包含在报 `Alex's sale` 表 `John the "Hunter"` 中或中。 有两种方法可包含这些值：

* **使用其他报价类型**:例如， `s.eVar1 = "Alex's sale"` 和 `s.eVar1 = 'John the "Hunter"'` 均有效。
* **转义引号**:使用反斜杠转义引号。 例如， `s.eVar1 = 'Alex\'s sale'` 和 `s.eVar1 = "John the \"Hunter\""` 均有效。

### 避免使用弯引号

某些程序会自动将中性引号(`"..."` 和 `'...'`)转换为弯引号(`“...”` 和 `‘...’`)。 避免使用文档编辑器（如Microsoft Word），或通过电子邮件发送代码片段。 JavaScript中不能使用弯引号。

## 引用Analytics对象

发送到Adobe的所有变量都使用Analytics对象。 大多数实现都使用 `s` 对象。 在引用引用引用中包含Analytics对象的变量时，请确保。

例如， `s.eVar1 = 'Value'` is valid, while `eVar1 = 'Value'` is not.

## 定义每个变量一次

运行跟踪函数(`s.t()`)时，AppMeasurement会获取所有定义的变量并将其编译为图像请求。 如果在实施中多次定义变量，则只使用最新值。 确保运行跟踪函数时所有变量值都包含正确的值。

## 正确的变量大写

某些变量使用大写字母。 JavaScript变量区分大小写。 确保在定义变量时使用正确的大小写。 例如， `s.eVar1 = 'Value'` is valid, while `s.evar1 = 'Value'` is not.

## 插件

一些组织使用插件来改进Adobe Analytics的实施。 升级AppMeasurement版本时，请不要忘记重新包含任何已安装的插件。 在“代码管理器 [!UICONTROL ”中创建的代码] ，没有任何插件代码。 复制现有代码，以备您需要还原到AppMeasurement的先前版本。

## 变量值中的空白

在 HTML 中，有多个字符会产生空格。这些字符包括空格、Tab 和回车（或换行）。请仔细研究下面的示例：

```html
<head>
  <title>
    Home Page
  </title>
</head>
<body>
<script language="javascript">
  s.pageName = document.title;
</script>
</body>
```

In this case, `document.title` populates `s.pageName`, which receives a value of &quot;Home Page&quot;. 但是，某些浏览器可以以不同方式解释空白。 结果可以是以下两个示例之一：

```js
s.pageName = "Home Page";
```

```js
s.pageName = "        Home Page";
```

在Adobe Analytics中，这两个变量值被视为单独的。 但是，出于显示目的，会自动删除空白。 结果是显示两个看似相同的“主页”行项目的报表。 确保变量值在所需值之前或之后不包含空格。
