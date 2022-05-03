---
description: 要验证是否已正确启用服务器端转发，您将需要检查来自 Analytics 跟踪请求的 HTTP 响应。此操作可以使用浏览器的开发人员工具或使用 Charles Web Debugger 之类的代理工具来完成。以下说明介绍了必须存在哪些指示器才能确保已正确启用服务器端转发。
solution: Analytics
title: 如何验证服务器端转发的实施情况
feature: Server-Side Forwarding
exl-id: 21db4572-da3c-43aa-a774-86a089656695
source-git-commit: aa4550d7012f76571f7623428d3d4ee08f728f64
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 84%

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
>如果响应包含键值对 `"status":"SUCCESS"` 或一个 2 x 2 图像，则表示服务器端转发的配置 *不* 正确。请确保已正确部署Identity Service，已部署App Measurement模块，已将适用的报表包映射到正确的组织ID，并且已在Analytics管理控制台中启用服务器端转发。

>[!MORELIKETHIS]
>
>* [Charles Web Debugger](https://www.charlesproxy.com/)

