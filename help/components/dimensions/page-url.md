---
title: 页面 URL
description: 页面的URL。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 2%

---


# 页面 URL

“页面URL”维度列表您站点上的URL。

>[!IMPORTANT]
>
>此维仅在Data warehouse中可用。 如果要在其他Analytics解决方案中使用URL维，请使 [用eVar](evar.md)。

## 用数据填充此维

此维从图像请求中的 [`g` 查询字符串](/help/implement/validate/query-parameters.md) 检索数据。 AppMeasurement使用变量收集此 [`pageURL`](/help/implement/vars/page-vars/pageurl.md) 数据。

## 用URL填充eVar

Adobe建议将eVar设置为连接的字符串 `window.location.hostname + window.location.pathname`。 此字符串的工作效果通常比 `window.location.href` 它更好，因为它忽略了协议、查询字符串和锚点标签。

如果希望eVar与Data warehouse中的“页面URL”维完全匹配，则可以使 [用动态变量](/help/implement/vars/page-vars/dynamic-variables.md) ，并在每次点 `D=g` 击时将eVar设置为。 请注意，此方法不适用于自定义链接点击，因为所有调用都会删除页面 [`tl()`](/help/implement/vars/functions/tl-method.md) URL。

## 维项

维项目包括站点上页面的URL。
