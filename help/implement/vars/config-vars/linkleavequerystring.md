---
title: linkLeaveQueryString
description: 允许在链接跟踪维度中保留查询字符串。
feature: Appmeasurement Implementation
exl-id: 266f7d9c-803d-4dbe-95a1-282230012878
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 84%

---

# linkLeaveQueryString

默认情况下，AppMeasurement 会从链接跟踪 URL 中剥离查询字符串。使用 `linkLeaveQueryString` 变量可在链接跟踪维度中保留查询字符串。

对于某些退出链接和下载链接，URL 的重要部分可以包含在查询字符串中。例如，下载链接（如 `https://example.com/download.asp?filename=myfile.exe`）在查询字符串中包含重要链接信息。

如果链接跟踪信息不在网站的 URL 中，则不必使用此变量。从链接跟踪 URL 中剥离查询字符串有助于限制维度包含的唯一值的数量。

启用 `linkLeaveQueryString` 适用于所有链接跟踪维度（包括自定义链接、退出链接和下载链接）。

>[!TIP]
>
>此变量不影响链接跟踪外部的维度。它仅影响自定义链接、退出链接和下载链接。

## 使用Web SDK处理链接查询字符串

未从XDM字段`web.webInteraction.URL`中剥离查询字符串。 如果要从此XDM字段中去除查询字符串，可以使用`onBeforeEventSend`编辑它。

## 使用Adobe Analytics扩展保留URL参数

[!UICONTROL 保留 URL 参数]是配置 Adobe Analytics 扩展时位于[!UICONTROL 链接跟踪]折叠面板下方的复选框。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
2. 单击所需的标记属性。
3. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的&#x200B;]**配置**[!UICONTROL &#x200B;按钮。
4. 展开[!UICONTROL 链接跟踪]折叠面板，这会显示[!UICONTROL 保留 URL 参数]复选框。

如果要在链接跟踪维度中包含查询字符串，请选中此框。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.linkLeaveQueryString

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
