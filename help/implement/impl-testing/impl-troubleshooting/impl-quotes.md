---
description: 当您在变量中输入值时，可遵循一些最佳实践。
keywords: Analytics 实施
seo-description: 当您在变量中输入值时，可遵循一些最佳实践。
seo-title: 使用引号
solution: Analytics
subtopic: 故障诊断
title: 使用引号
topic: 开发人员和实施
uuid: 9f09c48b-7ae5-441e-8635-fd6 bdc2 e94 c7
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 使用引号

当您在变量中输入值时，可遵循一些最佳实践。

您可以使用单引号或双引号，但是要保证其一致性。如果您使用单引号，就要始终使用单引号。如果您使用双引号，就要始终使用双引号。以下两个示例都是正确的。

```js
s.prop2='test' (single quotes)
```

```js
s.prop2="test" (double quotes)
```

确保已关闭智能引号。如果您使用单引号，并且在变量值中还有一个撇号，则 JavaScript 会将此撇号解释为一个单引号。它表示字符串的末尾。请仔细研究下面的示例：

```js
s.pageName='John's Home Page'
```

在这种情况下，JavaScript 会将 "John's" 中的撇号（它同时也是一个单引号）解释为字符串的末尾。由于 ''s Home Page" 在 JavaScript 中没有任何意义，因此它将导致错误，该错误会阻止图像请求产生。以下两个示例都非常有用：

```js
s.pageName='John\'s Home Page'
```

```js
s.pageName="John's Home Page"
```

在第一个示例中，您可以在撇号前面插入一个反斜线 (\) ，即可对该撇号进行转义。它会告诉 JavaScript 这个撇号并不是字符串的末尾，而是字符串本身所包含的部分。该字符串随后会在结尾的单引号处正常终止。第二个示例使用双引号包住整个字符串。在这一情况下，单引号不能表示字符串的末尾。如果字符串本身就包含双引号，也会遇到和前面一样的情况。s.pageName="Team Says "We Win!""是一个不正确的值，因为在字符串内使用了双引号，而且字符串前后也用双引号包住。如果输入 s.pageName="Team Says \"We Win!\""，才是正确的值。
