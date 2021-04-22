---
title: linkLeaveQueryString
description: 允许在链接跟踪维度中保留查询字符串。
exl-id: 266f7d9c-803d-4dbe-95a1-282230012878
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '289'
ht-degree: 100%

---

# linkLeaveQueryString

默认情况下，AppMeasurement 会从链接跟踪 URL 中剥离查询字符串。使用 `linkLeaveQueryString` 变量可在链接跟踪维度中保留查询字符串。

对于某些退出链接和下载链接，URL 的重要部分可以包含在查询字符串中。例如，下载链接（如 `https://example.com/download.asp?filename=myfile.exe`）在查询字符串中包含重要链接信息。

如果链接跟踪信息不在网站的 URL 中，则不必使用此变量。从链接跟踪 URL 中剥离查询字符串有助于限制维度包含的唯一值的数量。

启用 `linkLeaveQueryString` 适用于所有链接跟踪维度（包括自定义链接、退出链接和下载链接）。

>[!TIP]
>
>此变量不影响链接跟踪外部的维度。它仅影响自定义链接、退出链接和下载链接。

## Adobe Experience Platform Launch 中的“保留 URL 参数”

[!UICONTROL 保留 URL 参数]是配置 Adobe Analytics 扩展时位于[!UICONTROL 链接跟踪]折叠面板下方的复选框。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的]配置[!UICONTROL 按钮。
4. 展开[!UICONTROL 链接跟踪]折叠面板，这会显示[!UICONTROL 保留 URL 参数]复选框。

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
