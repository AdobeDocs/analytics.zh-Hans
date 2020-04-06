---
title: linkExternalFilters
description: 使用 linkExternalFilters 变量有助于进行自动退出链接跟踪。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkExternalFilters

AppMeasurement 提供自动跟踪指向网站外部的链接的功能。If [`trackExternalLinks`](trackexternallinks.md) is enabled, an image request is sent to Adobe right as a visitor clicks a link to leave your site. `linkExternalFilters` 和 [`linkInternalFilters`](linkinternalfilters.md) 变量可确定哪些链接被视为内部/外部链接。

如果此变量包含值，则自动退出链接跟踪将以白名单的方式执行。如果链接点击与任何 `linkExternalFilters` 值都不匹配，则不会将其视为退出链接。系统将针对此变量检查整个 URL。If [`linkLeaveQueryString`](linkleavequerystring.md) is enabled, the query string is also examined.

>[!TIP] 仅当您确切知道要将哪些域视为退出链接时，才使用此变量。许多组织发现使用 `linkInternalFilters` 足以满足其退出链接跟踪需求，因此没有使用 `linkExternalFilters`。

如果同时使用 `linkInternalFilters` 和 `linkExternalFilters`，则点击的链接必须与 `linkExternalFilters` 匹配&#x200B;**且**&#x200B;与 `linkInternalFilters` 不匹配时才能被视为退出链接。如果点击的链接与退出链接和下载链接标准均匹配，则将优先使用下载链接类型。

## Adobe Experience Platform Launch 中的“出站链接 - 跟踪”

The Track field is a comma-separated list of filters (usually domains) under the [!UICONTROL Link Tracking] accordion when configuring the Adobe Analytics extension.

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. 展开可 [!UICONTROL Link Tracking] 折叠面板，以显示 [!UICONTROL Outbound Links - Track] 字段。

在此字段中放置要始终视为外部链接的过滤器。用逗号分隔多个域，不带空格。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.linkExternalFilters

`s.linkExternalFilters` 变量是包含被视为退出链接的过滤器（如域）的字符串。用逗号分隔多个域，不带空格。

```js
s.linkExternalFilters = "example.com,example.net,example.org";
```

假定 `adobe.com` 上有以下实施示例：

```html
<script>
  s.trackExternalLinks = true;
  s.linkExternalFilters = "example.com,example.net";
</script>

<!-- The following link is NOT considered an exit link, even though the link is outside adobe.com -->
<a href = "example.org">Example link 1</a>

<!-- The following link is an exit link because it matches the linkExternalFilters whitelist -->
<a href = "example.com">Example link 2</a>
```
