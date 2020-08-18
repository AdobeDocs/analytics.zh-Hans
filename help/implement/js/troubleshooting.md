---
title: JavaScript 实施疑难解答
description: 了解 JavaScript 实施存在的常见问题以及疑难解答最佳实践。
translation-type: tm+mt
source-git-commit: b569f87dde3b9a8b323e0664d6c4d1578d410bb7
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 73%

---


# JavaScript 实施疑难解答

下面列出了贵组织无法将数据正确导入到 Adobe Analytics 的若干原因。

## 使用引号

发送到 Adobe 的大多数变量都是字符串。在 JavaScript 中，既可以使用单引号，也可以使用双引号。

### 混合使用不同引号定义变量

为符合最佳实践，请确保您使用的引号类型始终保持一致。如果使用单引号指定字符串的开头，则必须使用单引号结束字符串。

例如，`s.eVar1 = 'Value'` 和 `s.eVar1 = "Value"` 均有效。但 `s.eVar1 = 'Value"` 无效。

### 在一个字符串中包含单引号或双引号

有时，需要在一个字符串中包含单引号或双引号。例如，您希望在报表中包含值 `Alex's sale` 或 `John the "Hunter"`。包含这些值时可使用两种方法：

* **使用另一种引号**：例如，`s.eVar1 = "Alex's sale"` 和 `s.eVar1 = 'John the "Hunter"'` 均有效。
* **对引号进行转义**：使用反斜杠对引号进行转义。例如，`s.eVar1 = 'Alex\'s sale'` 和 `s.eVar1 = "John the \"Hunter\""` 均有效。

### 避免使用弯引号

有些程序会自动将直引号（`"..."` 和 `'...'`）转换为弯引号（`“...”` 和 `‘...’`）。避免使用文档编辑器（如 Microsoft Word），或通过电子邮件发送代码段。不能在 JavaScript 中使用弯引号。

## 引用 Analytics 对象

发送到 Adobe 的所有变量都会使用 Analytics 对象。大多数实施都使用 `s` 对象。确在引用变量时将 Analytics 对象包含在引用中。

例如，`s.eVar1 = 'Value'` 有效，但 `eVar1 = 'Value'` 无效。

## 每个变量定义一次

运行跟踪函数 (`s.t()`) 时，AppMeasurement 会获取定义的所有变量并将它们编译到一个图像请求中。如果在实施中将变量定义多次，则只会使用最新值。确保在运行跟踪函数时所有变量值都包含正确的值。

## 更正变量大小写

有些变量使用大写字母。JavaScript 变量需区分大小写。确保在定义变量时使用正确的大小写。例如，`s.eVar1 = 'Value'` 有效，但 `s.evar1 = 'Value'` 无效。

## 插件

一些组织使用插件来改进 Adobe Analytics 实施。升级 AppMeasurement 版本时，切记重新包含任何已安装的插件。在[!UICONTROL 代码管理器]中创建的代码不含任何插件代码。为现有代码创建一个副本，以防您需要将 AppMeasurement 还原到之前的版本。

## 变量值中的空格

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

在本例中，`document.title` 中填充了 `s.pageName` 变量，该变量将收到值“Home Page”。但是，有些浏览器可能会按不同方式解读空格。因此，可能会产生如以下两个示例所示的不同结果：

```js
s.pageName = "Home Page";
```

```js
s.pageName = "        Home Page";
```

在 Adobe Analytics 中，这两个变量值会被视为不同的值。但是，出于显示目的，系统会自动删除空格。因此，生成的报表中会显示两个看似相同的“Home Page”行项。确保变量值中所需值的前后都不包含空格。

## 截断的图像请求

用长值填充许多变量的实现有时会遇到截断的图像请求。 某些较旧的浏览器（如Internet Explorer）对图像请求URL施加2083个字符的限制。 如果您的组织面临很长的图像请求，请尝试以下操作：

* **使用Experience CloudID服务**:AppMeasurement库1.4.1及更高版本会在图像请求过长时使用HTTPPOST自动发送这些请求。 使用此方法发送的数据不会被截断，而不管长度如何。 See [Adobe Experience Cloud ID service](https://docs.adobe.com/content/help/zh-Hans/id-service/using/home.html) for more information.
* **使用处理规则**: [处理规则](/help/admin/admin/c-processing-rules/processing-rules.md) 可以将值从一个变量复制到另一个变量。 此方法可避免在多个变量中设置相同的值。 例如：

   始终执行：<br>用eVar1覆盖prop1的值<br>用eVar1覆盖eVar2的值<br>用eVar1覆盖prop2的值<br>

   然后在您的实施中设置eVar1:

   ```js
   s.eVar1 = "The quick brown fox jumps over the lazy dog";
   ```

* **使用动态变量**:如果实现使用相同的值填充许多变量，则可 [以使用动态变](/help/implement/vars/page-vars/dynamic-variables.md) 量来缩短请求URL:

   ```js
   s.eVar1 = "The quick brown fox jumps over the lazy dog";
   s.eVar2 = "D=v1";
   s.prop1 = "D=v1";
   s.prop2 = "D=v1";
   ```

* **使用分类**:如果产品或页面名称异常长，您可以使用标识值或代码，然后使用 [分类](/help/components/classifications/c-classifications.md) ，以显示更友好的名称。
