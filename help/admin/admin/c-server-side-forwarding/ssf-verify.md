---
description: 要验证是否已正确启用服务器端转发，您将需要检查来自 Analytics 跟踪请求的 HTTP 响应。此操作可以使用浏览器的开发人员工具或使用 Charles Web Debugger 之类的代理工具来完成。以下说明介绍了必须存在哪些指示器才能确保已正确启用服务器端转发。
solution: Audience Manager
title: 如何验证服务器端转发的实施情况
uuid: e37296cc-0120-486a-a4ca-78d648cf6a11
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

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
>如果响应包含键值对 `"status":"SUCCESS"` 或一个 2 x 2 图像，则表示服务器端转发的配置 *不* 正确。请确保已正确部署标识服务，已部署 App Measurement 模块，已将适用的报表包映射到正确的 IMS 组织，并且已在 Analytics Admin Console 中启用服务器端转发。

>[!MORELIKETHIS]
>
>* [Charles Web Debugger](https://www.charlesproxy.com/)

