---
title: linkInternalFilters
description: 使用linkInternalFilters变量帮助自动退出链接跟踪。
translation-type: tm+mt
source-git-commit: 8f7baa770f800ffe800e760f1eca59911d3db348

---


# linkInternalFilters

AppMeasurement提供自动跟踪站点外的链接的功能。 如果 `trackExternalLinks` 是 `true`这样，则当访客单击链接离开您的站点时，图像请求会直接发送到Adobe。 这些 `linkTrackExternalFilters` 和变 `linkTrackInternalFilters` 量决定哪些链接被视为内部／外部链接。

如果此变量包含值，则自动退出链接跟踪的行为类似于黑名单。 如果链接单击与任何值不匹 `linkInternalFilters` 配，则该链接被视为退出链接。 将针对此变量检查整个URL。 如果 `linkLeaveQueryString` 是 `true`，则查询字符串也会被检查。

如果同时使用和 `linkInternalFilters` 同时使 `linkExternalFilters` 用，则单击的链接必须匹配 `linkExternalFilters` 且不匹配 **，才**`linkInternalFilters` 能被视为退出链接。 如果单击的链接与退出链接和下载链接条件均匹配，则下载链接类型将优先。

> [!NOTE] 内 `linkInternalFilters` 部URL过滤器是单独的功能，可用于不同用途。 该变 `linkInternalFilters` 量专门用于退出链接跟踪。 内部URL过滤器是管理员设置，可帮助处理流量源维度，如引用域。 See [Internal URL filters](/help/admin/admin/internal-url-filter-admin.md) in the Admin user guide.

## 出站链接——在Adobe Experience Platform Launch中从不跟踪

“从不跟踪”字段是配置Adobe Analytics扩展时“链接跟踪”折叠面板下以逗号分隔的筛选器(通常是 [!UICONTROL 域] )列表。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到“扩 [!UICONTROL 展] ”选项卡，然后单击Adobe Analytics [!UICONTROL 下的] “配置”按钮。
4. 展开“链 [!UICONTROL 接跟踪] ”折叠面板，该面板显示“出站链 [!UICONTROL 接——从不跟踪] ”字段。

在此字段中放置您永远不希望作为退出链接跟踪的过滤器。 用逗号分隔多个域，不带空格。

## AppMeasurement中的s.linkInternalFilters和启动自定义代码编辑器

该 `s.linkInternalFilters` 变量是一个包含过滤器（如域）的字符串，您认为这些过滤器是站点内部的。 使用不带空格的逗号分隔多个过滤器。

```js
s.linkInternalFilters = "example.com,example.net,example.org";
```

请考虑以下实施示例，就像它在上一样 `adobe.com`:

```html
<script>
  s.trackExternalLinks = true;
  s.linkInternalFilters = "adobe.com";
</script>

<!-- The following link is an exit link because it does not match the anything under linkInternalFilters -->
<a href = "example.com">Example link 2</a>
```
