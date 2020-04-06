---
title: linkLeaveQueryString
description: 允许在链接跟踪维度中保留查询字符串。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkLeaveQueryString

默认情况下，AppMeasurement 会从链接跟踪 URL 中剥离查询字符串。Use the `linkLeaveQueryString` variable to preserve query strings in link tracking dimensions.

对于某些退出链接和下载链接，URL 的重要部分可以包含在查询字符串中。例如，下载链接（如 `https://example.com/download.asp?filename=myfile.exe`）在查询字符串中包含重要链接信息。

如果链接跟踪信息不在网站的 URL 中，则不必使用此变量。从链接跟踪 URL 中剥离查询字符串有助于限制维度包含的唯一值的数量。

启用 `linkLeaveQueryString` 适用于所有链接跟踪维度（包括自定义链接、退出链接和下载链接）。

>[!TIP] 此变量不影响链接跟踪外部的维度。它仅影响自定义链接、退出链接和下载链接。

## Adobe Experience Platform Launch 中的“保留 URL 参数”

[!UICONTROL Keep URL Parameters] 是配置Adobe Analytics扩展 [!UICONTROL Link Tracking] 时accordion下的复选框。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. 展开折叠 [!UICONTROL Link Tracking] 面板，该面板会显示该 [!UICONTROL Keep URL Parameters] 复选框。

如果要在链接跟踪维度中包含查询字符串，请选中此框。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.linkLeaveQueryString

`s.linkLeaveQueryString` 变量是一个布尔值。其默认值为 `false`。

* 如果将此变量设置为 `true`，则查询字符串将保留在链接跟踪 URL 中。
* 如果将此变量设置为 `false` 或未定义此变量，则将从链接跟踪 URL 中剥离查询字符串。

```js
s.linkLeaveQueryString = true;
```

## 示例

将此变量设置为 true 时要小心，因为它会影响链接跟踪过滤器，如 [`linkInternalFilters`](linkinternalfilters.md)、[`linkExternalFilters`](linkexternalfilters.md) 和 [`linkDownloadFiletypes`](linkdownloadfiletypes.md)。

假定 `adobe.com` 上有以下示例：

```html
<script>
  s.linkInternalFilters = "adobe.com";
  s.linkLeaveQueryString = true;
</script>

<!--This link is not an exit link because the internal filter matches part of the query string -->
<a href = "example.com?r=adobe.com">Example link</a>
```
