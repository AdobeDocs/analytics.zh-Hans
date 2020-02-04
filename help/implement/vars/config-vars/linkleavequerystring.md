---
title: linkLeaveQueryString
description: 允许保留链接跟踪维中的查询字符串。
translation-type: tm+mt
source-git-commit: e500332fe16887fa004858b07b59644837e183aa

---


# linkLeaveQueryString

默认情况下，AppMeasurement会从链接跟踪URL中去除查询字符串。 使用linkLeaveQueryString变量可保留链接跟踪维中的查询字符串。

对于某些退出链接和下载链接，URL的重要部分可以位于查询字符串中。 例如，下载链接（如）在查 `https://example.com/download.asp?filename=myfile.exe` 询字符串中包含重要链接信息。

如果链接跟踪信息不在站点的URL中，则不必使用此变量。 从链接跟踪URL中剥离查询字符串有助于限制维包含的唯一值的数量。

启用 `linkLeaveQueryString` 功能适用于所有链接跟踪维度（包括自定义链接、退出链接和下载链接）。

> [!TIP] 此变量不影响链接跟踪之外的维。 它仅影响自定义链接、退出链接和下载链接。

## 在Adobe Experience Platform Launch中保留URL参数

[!UICONTROL 配置Adobe Analytics扩展时] ，保留URL参数是“链接跟 [!UICONTROL 踪] ”折叠面板下的复选框。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到“扩 [!UICONTROL 展] ”选项卡，然后单击Adobe Analytics [!UICONTROL 下的] “配置”按钮。
4. 展开“链 [!UICONTROL 接跟踪] ”折叠面板，该面板会显示“ [!UICONTROL 保留URL参数”复选框] 。

如果要在链接跟踪维中包含查询字符串，请选中此框。

## AppMeasurement和Launch自定义代码编辑器中的s.linkLeaveQueryString

该 `s.linkLeaveQueryString` 变量是布尔值。 Its default value is `false`.

* 如果此变量设置为， `true`则查询字符串将保留在链接跟踪URL中。
* 如果此变量设置为或未定 `false` 义，则从链接跟踪URL中去除查询字符串。

```js
s.linkLeaveQueryString = true;
```

## 示例

将此变量设置为true时要小心，因为这会影响链接跟踪过滤器( `linkInternalFilters`如 `linkExternalFilters`、和) `linkDownloadFiletypes`。

请考虑以下示例，就像它在上一样 `adobe.com`:

```html
<script>
  s.linkInternalFilters = "adobe.com";
  s.linkLeaveQueryString = true;
</script>

<!--This link is not an exit link because the internal filter matches part of the query string -->
<a href = "example.com?r=adobe.com">Example link</a>
```
