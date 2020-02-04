---
title: linkExternalFilters
description: 使用linkExternalFilters变量帮助自动退出链接跟踪。
translation-type: tm+mt
source-git-commit: 8f7baa770f800ffe800e760f1eca59911d3db348

---


# linkExternalFilters

AppMeasurement提供自动跟踪站点外的链接的功能。 如果 `trackExternalLinks` 是 `true`这样，则当访客单击链接离开您的站点时，图像请求会直接发送到Adobe。 这些 `linkTrackExternalFilters` 和变 `linkTrackInternalFilters` 量决定哪些链接被视为内部／外部链接。

如果此变量包含值，则自动退出链接跟踪的行为类似于白名单。 如果链接单击与任何值不 `linkExternalFilters` 匹配，则不会将其视为退出链接。 将针对此变量检查整个URL。 如果 `linkLeaveQueryString` 是 `true`，则查询字符串也会被检查。

> [!TIP] 仅当您确切知道要将哪些域视为退出链接时，才使用此变量。 许多组织发现使用 `linkInternalFilters` 足以满足其退出链接跟踪需求，而且不使用 `linkExternalFilters`。

如果同时使用和 `linkInternalFilters` 同时使 `linkExternalFilters` 用，则单击的链接必须匹配 `linkExternalFilters` 且不匹配 **，才**`linkInternalFilters` 能被视为退出链接。 如果单击的链接与退出链接和下载链接条件均匹配，则下载链接类型将优先。

## 出站链接——在Adobe Experience Platform Launch中跟踪

“跟踪”字段是配置Adobe Analytics扩展时链接跟踪折叠面板下以逗号分隔的筛选器(通常是 [!UICONTROL 域] )列表。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到“扩 [!UICONTROL 展] ”选项卡，然后单击Adobe Analytics [!UICONTROL 下的] “配置”按钮。
4. 展开“链 [!UICONTROL 接跟踪] ”折叠面板，该面板显示“ [!UICONTROL 出站链接——跟踪”字段] 。

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

<!-- The following link is not considered an exit link, even though the link is outside adobe.com -->
<a href = "example.org">Example link 1</a>

<!-- The following link is an exit link because it matches the linkExternalFilters whitelist -->
<a href = "example.com">Example link 2</a>
```
