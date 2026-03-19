---
title: AMO ID
description: Adobe Media Optimizer ID，用于Adobe Advertising集成。
feature: Dimensions
source-git-commit: 408d8db0d1e3c8301a066fe54d611ec7b8e3418a
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 3%

---

# AMO ID

**[!UICONTROL AMO ID]**&#x200B;是Adobe Advertising集成中使用的连接标识符的集合。 此维度中存储的值会自动组织为更加易于用户识别的单独分类维度，以用于Analytics报表。 启用[Analytics for Advertising](https://experienceleague.adobe.com/en/docs/advertising/integrations/analytics/overview)集成时，将自动创建维度。

## 使用数据填充此维度

此维度通过多种方式收集其值：

* 对于点进流量，数据是从`s_kwcid`页面URL[中的](page-url.md)查询字符串参数收集的，通常是在广告驱动流量进入网站的页面上。
* 当URL不包含跟踪代码，但Adobe Advertising JavaScript在前两分钟内检测到点击时，也可以捕获点进流量。
* 对于受支持的显示到达流量，Adobe Advertising使用补充ID (`SDID`)补充后端上的值。

## 维度项目

Dimension项目包括AMO ID，也称为`s_kwcid`值。 确切的格式取决于流量是源自DSP还是源自Search、Social和Commerce。 AMO ID比EF ID粒度更小，主要用于在Analytics中分类和摄取Adobe Advertising指标。

### DSP

```text
AC!{ad key}!{placement key}
```

* **`AC`**：指示显示渠道。
* **`ad key`**： Adobe Advertising生成的广告字母数字标识符。
* **`placement key`**：投放的Adobe Advertising生成的字母数字标识符。

示例值

```text
AC!iIMvXqlOa6Nia2lDvtgw!GrVv6o2oV2qQLjQiXLC7
```

### 搜索、社交和Commerce广告

搜索、社交和Commerce AMO ID以`AL`开头，依次是广告商用户ID、广告网络帐户ID，然后是特定于网络的标识符。 共享广告网络帐户ID包括：

* **`3`**： Google广告
* **`10`**： Microsoft Advertising
* **`45`**： Meta
* **`86`**： Yahoo！ 显示网络
* **`87`**：导航
* **`88`**：百度
* **`90`**： Yandex
* **`94`**： Yahoo！ 日本广告
* **`105`**： Yahoo Native（已弃用）
* **`106`**： Pinterest（已弃用）

#### Google Ads

Google Ads使用两种相关的格式。 较新的帐户可以包括营销活动ID和广告组ID，它们支持Performance Max和草稿/实验营销活动的营销活动级和广告组级报表。

```text
AL!{user}!3!{creative}!{matchtype}!{placement}!{network}!{product partition}!{keyword}[!{campaign id}!{ad group id}]
```

* **`creative`**： Google Ads创作ID。
* **`matchtype`**：关键字匹配类型（`e`表示完全匹配，`p`表示短语，`b`表示广泛）。
* **`placement`**：广告被点击的域。
* **`network`**：发生点击的网络（`g`用于Google搜索，`s`用于搜索合作伙伴，`d`用于显示）。
* **`product partition`**：产品广告的产品组ID。
* **`keyword`**：在搜索站点上触发关键字，或在内容站点上触发最佳匹配关键字。
* **`campaign id`**：Google广告促销活动ID（如果存在）。
* **`ad group id`**：Google Ads广告组ID（如果存在）。

对于动态搜索广告，使用自动定位填充keyword字段。

示例：

```text
AL!1234!3!569345525675!e!!g!!adobe express!15557590691!136734402131
```

#### Microsoft Advertising

```text
AL!{user}!10!{ad id}!!!!{keyword/order item id}!!{campaign id}!{ad group id}
```

* **`ad id`**： Microsoft Advertising创作ID。
* **`keyword/order item id`**： Microsoft Advertising关键字ID。
* **`campaign id`**： Microsoft Advertising促销活动ID。
* **`ad group id`**： Microsoft Advertising广告组ID。

某些未迁移的帐户仍可以存在旧版Microsoft格式。

示例：

```text
AL!1234!10!79577297926903!!!!79577437127536!!291647087!1273234845019564
```

#### 百度

```text
AL!{user}!88!{creative}!{placement}!{keyword id}
```

* **`creative`**：百度创意ID。
* **`placement`**：广告被点击的网站。
* **`keyword id`**：百度关键字ID。

#### Yahoo!日本广告

```text
AL!{user}!94!{creative}!{matchtype}!{network}!{keyword}
```

* **`creative`**： Yahoo！ 日本广告创意ID。
* **`matchtype`**：关键字匹配类型（`be`个精确，`bp`个短语，`bb`广泛）。
* **`network`**：发生点击的网络（`n`本机，`s`搜索）。
* **`keyword`**：正在触发关键字。

#### 扬代克斯

```text
AL!{user}!90!{ad id}!{source type}!!!{phrase id}
```

* **`ad id`**： Yandex创作ID。
* **`source type`**：显示广告的网站类型（`b`搜索、`c`上下文/内容、`ct`类别）。
* **`phrase id`**： Yandex关键字ID。

## 分类

启用[Analytics for Advertising](https://experienceleague.adobe.com/en/docs/advertising/integrations/analytics/overview)集成时，会自动创建以下分类。 分类值由集成自动维护。

| 分类 | 描述 | DSP | 搜索、<br>Social和<br>Commerce |
| --- | --- | :---: | :---: |
| **[!UICONTROL 帐户]** | 帐户名称。 | &amp;amp；检查； | &amp;amp；检查； |
| **[!UICONTROL 广告显示URL]** | 广告中显示的URL。 | | &amp;amp；检查； |
| **[!UICONTROL 广告描述]** | 广告描述(DSP)或广告正文（搜索、社交和Commerce）。 | &amp;amp；检查； | &amp;amp；检查； |
| **[!UICONTROL 广告目标URL]** | 广告的目标URL。 | | &amp;amp；检查； |
| **[!UICONTROL 广告组]** | 广告组名称。 | | &amp;amp；检查； |
| **[!UICONTROL 广告平台]** | 广告DSP或搜索引擎名称。 | &amp;amp；检查； | &amp;amp；检查； |
| **[!UICONTROL 广告标题]** | 广告类型(DSP)或广告标题（搜索、社交和Commerce）。 | &amp;amp；检查； | &amp;amp；检查； |
| **[!UICONTROL 广告类型]** | 广告类型，如`text`、`video`、`display`或`native`。 | &amp;amp；检查； | &amp;amp；检查； |
| **[!UICONTROL AdCloud属性1]** -<br>**[!UICONTROL AdCloud属性5 ]** | 预留给未来自定义属性的占位符分类。 当前未使用。 | | |
| **[!UICONTROL Campaign]** | 营销活动名称。 | &amp;amp；检查； | &amp;amp；检查； |
| **[!UICONTROL Creative体验名称]** | 与广告交互关联的创意体验的名称，表示在测试或个性化中使用的一组创意变体。 | &amp;amp；检查； | |
| **[!UICONTROL Creative分支名称]** | 创意体验中表示创意体验中特定变体或路径的分支名称。 | &amp;amp；检查； | |
| **[!UICONTROL Creative分支ID]** | 在创意体验中分配给创意分支的唯一标识符。 | &amp;amp；检查； | |
| **[!UICONTROL Creative名称]** | 提供给用户的特定广告创意资源的名称。 | &amp;amp；检查； | |
| **[!UICONTROL Creative变体名称]** | 在创意体验或分支中使用的创意的特定变体的名称。 | &amp;amp；检查； | |
| **[!UICONTROL 关键字]** | 关键字。 | | &amp;amp；检查； |
| **[!UICONTROL 关键字匹配类型]** | 关键字和匹配类型。 | | &amp;amp；检查； |
| **[!UICONTROL 登陆类型]** | 登陆页面条目是浏览还是点进。 | &amp;amp；检查； | &amp;amp；检查； |
| **[!UICONTROL 匹配类型]** | 搜索匹配类型。 | | &amp;amp；检查； |
| **[!UICONTROL 网络]** | RTB (DSP)或广告网络名称（搜索、社交和Commerce）。 | &amp;amp；检查； | &amp;amp；检查； |
| **[!UICONTROL 优化]** | 包名称(DSP)或项目组合名称（搜索、社交和Commerce）。 | &amp;amp；检查； | &amp;amp；检查； |
| **[!UICONTROL 投放位置]** | 投放位置名称。 | &amp;amp；检查； | |
| **[!UICONTROL 产品目标]** | 产品列表广告的产品目标。 | | &amp;amp；检查； |
