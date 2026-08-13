---
description: 要验证服务器端转发是否已正确启用，您需要检查来自Analytics跟踪请求的HTTP响应。 这些说明说明了必须显示哪些指示符以确保正确启用服务器端转发。
solution: Analytics
title: 如何验证服务器端转发的实施情况
feature: Report Suite Settings
exl-id: 21db4572-da3c-43aa-a774-86a089656695
role: Admin
TQID: 'https://experienceleague.adobe.com/FpB4dk9D87gc24t5KG6WRJ-r8GFOvOEUlRTTjc6XFYI'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: ff9b434a-2221-4df7-81d1-5bcbf5f80bceid: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2: id: c354699e-6555-4397-8706-1a9a89984069
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 246
ht-degree: 33%

---

# 如何验证服务器端转发的实施情况

要验证服务器端转发是否已正确启用，您需要检查来自Analytics跟踪请求的HTTP响应。 可以使用浏览器的开发人员工具或代理工具（如Charles Web调试器）完成此操作。 以下说明说明了必须显示哪些指示符以确保正确启用服务器端转发。

检查服务器端转发的状态：

1. 加载包含已更新AppMeasurement代码的测试页面。
1. 在浏览器的调试工具或使用代理软件，检查来自Analytics跟踪请求的HTTP响应（通过选择包含“b/ss”的任意路径可轻松过滤此响应）。
1. 检查HTTP响应。 如果响应包含Audience Manager数据（如下图所示），则表示服务器端转发运行正常。

![](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/assets/ssf-succeed.png)

>[!CAUTION]
>
>如果响应包含键值对 `"status":"SUCCESS"` 或一个 2 x 2 图像，则表示服务器端转发的配置 *不* 正确。 请确保已正确部署身份标识服务，已部署 App Measurement 模块，已将适用的报表包映射到正确的组织 ID，并且已在 Analytics 管理工具中启用服务器端转发。

>[!MORELIKETHIS]
>
>* [Charles Web Debugger](https://www.charlesproxy.com/)
