---
title: linkInternalFilters
description: 使用 linkInternalFilters 变量有助于进行自动退出链接跟踪。
translation-type: tm+mt
source-git-commit: ec93137d0b5334e312fe0ec42953457243117d4a
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 92%

---


# linkInternalFilters

AppMeasurement 提供自动跟踪指向网站外部的链接的功能。如果启用了 [`trackExternalLinks`](trackexternallinks.md)，则当访客单击链接以离开您的网站时，图像请求会发送到 Adobe。[`linkExternalFilters`](linkexternalfilters.md) 和 `linkInternalFilters` 变量可确定哪些链接被视为内部/外部链接。

如果此变量包含值，则自动退出链接跟踪将以阻止列表的方式执行。如果链接点击与任何 `linkInternalFilters` 值都不匹配，则会将其视为退出链接。系统将针对此变量检查整个 URL。如果启用了 [`linkLeaveQueryString`](linkleavequerystring.md)，则还会检查查询字符串。

如果同时使用 `linkInternalFilters` 和 `linkExternalFilters`，则点击的链接必须与 `linkExternalFilters` 匹配&#x200B;**且**&#x200B;与 `linkInternalFilters` 不匹配时才能被视为退出链接。如果点击的链接与退出链接和下载链接标准均匹配，则将优先使用下载链接类型。

活动图使用此变量来帮助确定网站内部的链接。 Adobe建议为使用活动映射的实现设置此变量。

>[!NOTE]
>
>`linkInternalFilters` 和[内部 URL 过滤器](/help/admin/admin/internal-url-filter-admin.md)是两个不同功能，可以实现不同的目的。`linkInternalFilters` 变量专门用于退出链接跟踪。内部 URL 过滤器是一个管理员设置，可帮助处理流量源维度，如反向链接域名。

## Adobe Experience Platform Launch 中的“出站链接 - 从不跟踪”

“从不跟踪”字段是配置 Adobe Analytics 扩展时[!UICONTROL 链接跟踪]折叠面板下以逗号分隔的过滤器（通常是域）列表。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的]配置[!UICONTROL 按钮。
4. 展开[!UICONTROL 链接跟踪]折叠面板，这会显示[!UICONTROL 出站链接 - 从不跟踪]字段。

在此字段中放置您永远不希望作为退出链接进行跟踪的过滤器。用逗号分隔多个域，不带空格。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.linkInternalFilters

`s.linkInternalFilters` 变量是包含您视为网站内部链接的过滤器（如域）的字符串。用逗号分隔多个过滤器，不带空格。

```js
s.linkInternalFilters = "example.com,example.net";
```

假定 `adobe.com` 上有以下实施示例：

```html
<script>
  s.trackExternalLinks = true;
  s.linkInternalFilters = "adobe.com";
</script>

<!-- The following link is an exit link because it does not match the anything under linkInternalFilters -->
<a href = "example.org">Example link 2</a>
```
