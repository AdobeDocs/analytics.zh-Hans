---
description: 您可以实施自定义方法，通过设置 s.visitorID 变量来识别访客。
keywords: Analytics Implementation
solution: Analytics
title: 自定义访客 ID
topic: Developer and implementation
uuid: 49881e27-0418-4ecf-a092-dcc3db923f40
translation-type: tm+mt
source-git-commit: edf88e40cae8b6886b04257f266666c13a37f88d

---


# 自定义访客 ID

您可以实施自定义方法，通过设置 s.visitorID 变量来识别访客。

自定义访客 ID 可以在通过唯一方式识别访客的网站上使用。例如，当用户使用用户名和密码登录网站时，就会生成一个 ID。

如果能够获得和管理用户的[!UICONTROL 访客 ID]，则可以使用以下方法设置 ID：

| 方法 | 描述 |
|---|---|
| [s.visitorID](/help/implement/js-implementation/page-variables/page-variables.md) 变量 | 如果在浏览器中使用 JavaScript，或者如果使用任何其他 AppMeasurement 库，则可以在数据收集变量中设置访客 ID。 |
| 图像请求中的查询字符串参数 | 此功能允许您通过硬编码图像请求中的 [!UICONTROL vid 查询字符串]参数将[!UICONTROL 访客 ID] 传递到 Adobe。 |
| 数据插入 API | 如果设备使用的无线协议不接受 JavaScript，则可以将包含 `<visitorid/>` XML 元素的 XML post 从您的服务器发送到 Adobe 收集服务器。 |
| URL 重写和 VISTA | 部分部署架构支持使用 URL 重写，以便在无法设置 Cookie 的情况下保持会话状态。在此类情况下，Adobe 工程技术服务可以实施 [!DNL VISTA] 规则来查找页面 URL 中的会话值，然后设置其格式并置入 [!UICONTROL visid] 值。 |
>[!CAUTION]
>**自定义访客 ID 必须足够具体/独特**：如果自定义访客 ID 的实施无效，则可能会导致数据错误和报表性能不佳。如果自定义访客ID不够唯一或细度，或者被错误地设置为通用默认值（如字符串“NULL”或“0”）,Adobe Analytics将将多个不同访客的点击视为单个访客。 这种情况会导致数据不正确，访客计数过低，且该访客的区段无法正常工作。如果自定义访客 ID 不够具体，还会导致数据无法在 Analytics 报表集群中的各个节点之间正确分布。在这种情况下，一个节点会变得过载，无法及时处理报表请求。最终，报表包的所有报表都将失败。<br>实施不当的自定义访客ID可能不会立即影响报告性能，因为Analytics通常可以处理几个月的不平衡数据；但是，随着时间的推移，实施不当的自定义访客ID值可能会出现问题，以致于要求Analytics禁用对受影响报表包的处理。</br><br>实施人员应遵循以下准则：绝不应将单个自定义访客ID值计入超过报表包流量的1%。 尽管对于大多数报表包来说，1% 的标准已经足够，但是对于大型报表包而言，可能存在一些实际限制，导致报表性能受到影响，致使其值低于 1%。</br>
