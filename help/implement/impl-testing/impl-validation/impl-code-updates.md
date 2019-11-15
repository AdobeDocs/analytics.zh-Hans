---
description: 客户有责任测试 .JS 文件或 HTML 代码的任何修改。这一测试应当在修改被发布到制作的网站之前完成。
keywords: Analytics Implementation
solution: Analytics
title: 代码修改
topic: Developer and implementation
uuid: efac045e-15f5-45f6-a21a-de6c4b0a8185
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 代码修改

客户有责任测试 .JS 文件或 HTML 代码的任何修改。这一测试应当在修改被发布到制作的网站之前完成。

请确保未从置于 HTML 内或 [!DNL .JS] 文件内的代码中清除或修改任何换行/回车符。请确保 JavaScript 在所有页面和页面模板中执行时不会出错（在 Internet Explorer 的“Internet 选项”中，选择“高级”选项卡，然后单击“显示每个脚本错误的通知”）。

在测试错误时，请将代码粘贴到默认的 HTML 页面中，以确定错误是否是因为其他页面元素/对象而产生的。

```js
<html><head></head><body>
...paste code here to debug...
</body></html>
```

