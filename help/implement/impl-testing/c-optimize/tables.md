---
description: 许多 Web 浏览器直到编译了整个表格之后，才会显示表格中的内容。
keywords: Analytics Implementation
solution: Analytics
subtopic: Troubleshooting
title: 表格
topic: Developer and implementation
uuid: f72d7894-38bd-4926-bce4-0c6af7278c63
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 表格

许多 Web 浏览器直到编译了整个表格之后，才会显示表格中的内容。

如果页面的全部内容都包含在一个大表中，则浏览器在显示内容之前，必须编译页面的所有内容。

将对 JavaScript 库文件的调用置于表格标记之外，可以确保对 Analytics 服务器的调用不会影响页面内容的显示。

> [!NOTE] 该文件应放置在图像的合法位置，并且必须显示在开始 <body> 标记和结束 </body> 标记之间。

