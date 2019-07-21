---
description: 客户有责任测试 .JS 文件或 HTML 代码的任何修改。这一测试应当在修改被发布到制作的网站之前完成。
keywords: Analytics 实施
seo-description: 客户有责任测试 .JS 文件或 HTML 代码的任何修改。这一测试应当在修改被发布到制作的网站之前完成。
seo-title: 代码修改
solution: Analytics
title: 代码修改
topic: 开发人员和实施
uuid: efax045e-15f5-45f6-a21 a-de6 c4 b0 a8185
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 代码修改

客户有责任测试 .JS 文件或 HTML 代码的任何修改。这一测试应当在修改被发布到制作的网站之前完成。

Ensure that the linefeeds/return characters are not stripped or altered from the code that is placed within the HTML, or from within the [!DNL .JS] file. 请确保 JavaScript 在所有页面和页面模板中执行时不会出错（在 Internet Explorer 的“Internet 选项”中，选择“高级”选项卡，然后单击“显示每个脚本错误的通知”）。

在测试错误时，请将代码粘贴到默认的 HTML 页面中，以确定错误是否是因为其他页面元素/对象而产生的。

```js
<html><head></head><body>
...paste code here to debug...
</body></html>
```

