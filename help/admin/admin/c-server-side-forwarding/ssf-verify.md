---
description: 要验证是否已正确启用服务器端转发，您将需要检查来自 Analytics 跟踪请求的 HTTP 响应。此操作可以使用浏览器的开发人员工具或使用 Charles Web Debugger 之类的代理工具来完成。以下说明介绍了必须存在哪些指示器才能确保已正确启用服务器端转发。
seo-description: 要验证是否已正确启用服务器端转发，您将需要检查来自 Analytics 跟踪请求的 HTTP 响应。此操作可以使用浏览器的开发人员工具或使用 Charles Web Debugger 之类的代理工具来完成。以下说明介绍了必须存在哪些指示器才能确保已正确启用服务器端转发。
seo-title: 如何验证服务器端转发的实施情况
solution: Audience Manager
title: 如何验证服务器端转发的实施情况
uuid: e37296cc-0120-486a-a4ca-78d648cf6a11
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# 如何验证服务器端转发的实施情况

要验证是否已正确启用服务器端转发，您将需要检查来自 Analytics 跟踪请求的 HTTP 响应。此操作可以使用浏览器的开发人员工具或使用 Charles Web Debugger 之类的代理工具来完成。以下说明介绍了必须存在哪些指示器才能确保已正确启用服务器端转发。

要检查服务器端转发的状态，请执行以下操作：

1. 加载包含更新的 AppMeasurement 代码的测试页面。
1. 在浏览器的调试工具中或使用您的代理软件，检查来自 Analytics 跟踪请求的 HTTP 响应（您可以通过选择任何包含“b/ss”的路径来轻松对其过滤）。
1. 检查 HTTP 响应。如果响应包含 Audience Manager 数据（如下所示），则表示服务器端转发工作正常。

![](assets/ssf-succeed.png)

>[!CAUTION]
>
>If the response contains the key value pair `"status":"SUCCESS"` or a 2 x 2 image, then server-side forwarding * is not* configured correctly. 请确保正确部署了标识服务，您已部署了App Measurement模块，相应的报表包已映射到正确的IMS组织，并且已在Analytics管理控制台中启用了服务器端转发。

>[!MORE_LIKE_THIS]
>
>* [Charles Web Debugger](https://www.charlesproxy.com/)

