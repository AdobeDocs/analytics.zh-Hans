---
description: 许多 Web 浏览器直到编译了整个表格之后，才会显示表格中的内容。
keywords: Analytics 实施
seo-description: 许多 Web 浏览器直到编译了整个表格之后，才会显示表格中的内容。
seo-title: 表格
solution: Analytics
subtopic: 故障诊断
title: 表格
topic: 开发人员和实施
uuid: f72d7894-38bd-4926-bce4-0c6 af7278 c63
translation-type: tm+mt
source-git-commit: 6250335d05c8e7799802fce26192896a7a6598fe

---


# 表格

许多 Web 浏览器直到编译了整个表格之后，才会显示表格中的内容。

如果页面的全部内容都包含在一个大表中，则浏览器在显示内容之前，必须编译页面的所有内容。

将对 JavaScript 库文件的调用置于表格标记之外，可以确保对 Analytics 服务器的调用不会影响页面内容的显示。

>[!NOTE]
>
>应将文件放在图像的合法位置，并且必须在打开之间显示 <body> 标签和结束 </body> 标签。

