---
description: 您可以实施自定义方法，通过设置 s.visitorID 变量来识别访客。
keywords: Analytics 实施
seo-description: 您可以实施自定义方法，通过设置 s.visitorID 变量来识别访客。
seo-title: 自定义访客 ID
solution: Analytics
title: 自定义访客 ID
topic: 开发人员和实施
uuid: 49881e27-0418-4ecf-a092-dcc3 db923 f40
translation-type: tm+mt
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
| 数据插入 API | On devices using wireless protocols that don't accept JavaScript, you can send an XML post containing the `<visitorid/>` XML element to Adobe collection servers from your servers. |
| URL 重写和 VISTA | 部分部署架构支持使用 URL 重写，以便在无法设置 Cookie 的情况下保持会话状态。在此类情况下，Adobe 工程技术服务可以实施 [!DNL VISTA] 规则来查找页面 URL 中的会话值，然后设置其格式并置入 [!UICONTROL visid] 值。 |
>[!CAUTION]
>**自定义访客ID必须足够精细/唯一**：自定义访客ID的无效实施可能导致数据错误且报表性能不佳。如果自定义访客ID的唯一性或粒度不够，或者错误地设置为常用默认值(如字符串“NULL”)或“0”，则Adobe Analytics将以单个访客的身份将多个访客的点击次数视为一个访客。这种情况导致数据不正确，访客计数过低，区段无法正确工作。粒度不足的自定义访问者ID还可防止数据在Analytics报告群集中的节点之间正确分布。在这种情况下，一个节点会过载，并且无法及时处理报告请求。最后，报告包的所有报告都将失败。<br>未实施的自定义访客ID可能不会立即影响报告性能，因为Analytics通常可以处理数个月的不对称数据；但是，随着时间的推移，未实施的自定义访客ID值可能会因要求Analytics禁用对受影响报表包的处理而产生问题。</br><br>实施人员应遵循以下准则：不应为超过1%的报表包流量将单个自定义访客ID值计入其中。Although the 1% guideline is sufficient for most report suites, the actual limit that might cause reporting performance to be impacted may be lower than 1% for very large report suites.</br>
