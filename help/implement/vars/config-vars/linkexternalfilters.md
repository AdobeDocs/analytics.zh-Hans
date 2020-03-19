---
title: linkExternalFilters
description: 使用linkExternalFilters变量帮助自动退出链接跟踪。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkExternalFilters

AppMeasurement提供自动跟踪站点外的链接的功能。 如果 [`trackExternalLinks`](trackexternallinks.md) 启用此功能，则当访客单击链接离开您的站点时，图像请求会直接发送到Adobe。 这些 `linkExternalFilters` 和变 [`linkInternalFilters`](linkinternalfilters.md) 量决定哪些链接被视为内部／外部链接。

如果此变量包含值，则自动退出链接跟踪的行为类似于白名单。 如果链接单击与任何值不 `linkExternalFilters` 匹配，则不会将其视为退出链接。 将针对此变量检查整个URL。 如果 [`linkLeaveQueryString`](linkleavequerystring.md) 启用，则还会检查查询字符串。

> [!TIP] 仅当您确切知道要将哪些域视为退出链接时，才使用此变量。 许多组织发现使用 `linkInternalFilters` 足以满足其退出链接跟踪需求，而且不使用 `linkExternalFilters`。

如果同时使用和 `linkInternalFilters` 同时使 `linkExternalFilters` 用，则单击的链接必须匹配 `linkExternalFilters` 且不匹配 **，才**`linkInternalFilters` 能被视为退出链接。 如果单击的链接与退出链接和下载链接条件均匹配，则下载链接类型将优先。

## 出站链接——在Adobe Experience Platform Launch中跟踪

“跟踪”字段是配置Adobe Analytics扩展时accordion下以逗号分隔的筛 [!UICONTROL Link Tracking] 选器（通常是域）列表。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到选项卡， [!UICONTROL Extensions] 然后单击“Adobe Analytics” [!UICONTROL Configure] 下的按钮。
4. 展开可 [!UICONTROL Link Tracking] 折叠面板，以显示 [!UICONTROL Outbound Links - Track] 字段。

在此字段中放置您希望始终考虑外部的过滤器。 用逗号分隔多个域，不带空格。

## AppMeasurement和Launch自定义代码编辑器中的s.linkExternalFilters

该 `s.linkExternalFilters` 变量是包含您考虑退出链接的过滤器（如域）的字符串。 使用不带空格的逗号分隔多个域。

```js
s.linkExternalFilters = "example.com,example.net,example.org";
```

请考虑以下实施示例，就像它在上一样 `adobe.com`:

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
