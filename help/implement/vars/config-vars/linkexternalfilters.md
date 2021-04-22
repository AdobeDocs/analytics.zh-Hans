---
title: linkExternalFilters
description: 使用 linkExternalFilters 变量有助于进行自动退出链接跟踪。
exl-id: 7d4e8d96-17ee-4a04-9a57-37d2056ee9a7
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '306'
ht-degree: 100%

---

# linkExternalFilters

AppMeasurement 提供自动跟踪指向网站外部的链接的功能。如果启用了 [`trackExternalLinks`](trackexternallinks.md)，则当访客单击链接以离开您的网站时，图像请求会发送到 Adobe。`linkExternalFilters` 和 [`linkInternalFilters`](linkinternalfilters.md) 变量可确定哪些链接被视为内部/外部链接。

如果此变量包含值，则自动退出链接跟踪的行为类似于允许列表。如果链接点击与任何 `linkExternalFilters` 值都不匹配，则不会将其视为退出链接。系统将针对此变量检查整个 URL。如果启用了 [`linkLeaveQueryString`](linkleavequerystring.md)，则还会检查查询字符串。

>[!TIP]
>
>仅当您确切知道要将哪些域视为退出链接时，才使用此变量。许多组织发现使用 `linkInternalFilters` 足以满足其退出链接跟踪需求，因此没有使用 `linkExternalFilters`。

如果同时使用 `linkInternalFilters` 和 `linkExternalFilters`，则点击的链接必须与 `linkExternalFilters` 匹配&#x200B;**且**&#x200B;与 `linkInternalFilters` 不匹配时才能被视为退出链接。如果点击的链接与退出链接和下载链接标准均匹配，则将优先使用下载链接类型。

## Adobe Experience Platform Launch 中的“出站链接 - 跟踪”

“跟踪”字段是在配置 Adobe Analytics 扩展时[!UICONTROL 链接跟踪]折叠面板下以逗号分隔的过滤器（通常是域）列表。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的]配置[!UICONTROL 按钮。
4. 展开[!UICONTROL 链接跟踪]折叠面板，这会显示[!UICONTROL 出站链接 - 跟踪]字段。

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

<!-- The following link is an exit link because it matches the linkExternalFilters allowlist -->
<a href = "example.com">Example link 2</a>
```
