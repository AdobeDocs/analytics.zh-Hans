---
description: 您可以实施自定义方法，通过设置 s.visitorID 变量来识别访客。
keywords: Analytics 实施
seo-description: 您可以实施自定义方法，通过设置 s.visitorID 变量来识别访客。
seo-title: 自定义访客 ID
solution: Analytics
title: 自定义访客 ID
topic: 开发人员和实施
uuid: 49881e27-0418-4ecf-a092-dcc3db923f40
translation-type: ht
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 自定义访客 ID

您可以实施自定义方法，通过设置 s.visitorID 变量来识别访客。

自定义访客 ID 可以在通过唯一方式识别访客的网站上使用。例如，当用户使用用户名和密码登录网站时，就会生成一个 ID。

如果能够获得和管理用户的[!UICONTROL 访客 ID]，则可以使用以下方法设置 ID：

| 方法 | 描述 |
|---|---|
| [s.visitorID](/help/implement/js-implementation/c-variables/page-variables.md) 变量 | 如果在浏览器中使用 JavaScript，或者如果使用任何其他 AppMeasurement 库，则可以在数据收集变量中设置访客 ID。 |
| 图像请求中的查询字符串参数 | 此功能允许您通过硬编码图像请求中的 [!UICONTROL vid 查询字符串]参数将[!UICONTROL 访客 ID] 传递到 Adobe。 |
| 数据插入 API | 如果设备使用的无线协议不接受 JavaScript，则可以将包含 `<visitorid/>` XML 元素的 XML post 从您的服务器发送到 Adobe 收集服务器。 |
| URL 重写和 VISTA | 部分部署架构支持使用 URL 重写，以便在无法设置 Cookie 的情况下保持会话状态。在此类情况下，Adobe 工程技术服务可以实施 [!DNL VISTA] 规则来查找页面 URL 中的会话值，然后设置其格式并置入 [!UICONTROL visid] 值。 |
>[!CAUTION]
>**自定义访客 ID 必须足够具体/独特**：如果自定义访客 ID 的实施无效，则可能会导致数据错误和报表性能不佳。如果自定义访客 ID 不够独特或具体，或者未正确设置为通用默认值（例如字符串“NULL”或“0”），则 Adobe Analytics 会将多个不同访客的点击视为单个访客的点击。这种情况会导致数据不正确，访客计数过低，且该访客的区段无法正常工作。如果自定义访客 ID 不够具体，还会导致数据无法在 Analytics 报表集群中的各个节点之间正确分布。在这种情况下，一个节点会变得过载，无法及时处理报表请求。最终，报表包的所有报表都将失败。<br>自定义访客 ID 实施不当可能不会立即影响报表的性能，因为 Analytics 处理不平衡数据通常需要几个月。但是，随着时间的流逝，如果自定义访客 ID 值实施不当，则可能会导致问题，要求 Analytics 禁用对受影响报表包的处理。</br><br>实施人员应遵循以下准则：单个自定义访客 ID 的点击值绝不能超过报表包流量的 1%。尽管对于大多数报表包来说，1% 的标准已经足够，但是对于大型报表包而言，可能存在一些实际限制，导致报表性能受到影响，致使其值低于 1%。</br>
