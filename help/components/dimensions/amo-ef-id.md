---
title: AMO EF ID
description: Adobe Media Optimizer EF ID，用于Adobe Advertising集成。
feature: Dimensions
source-git-commit: 408d8db0d1e3c8301a066fe54d611ec7b8e3418a
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 4%

---

# AMO EF ID

**[!UICONTROL AMO EF ID]**&#x200B;是Adobe Advertising集成中使用的广告点击标识符。 它是Adobe Advertising用于将活动与访客级别的在线点击或广告曝光度关联的唯一令牌。 启用[Analytics for Advertising](https://experienceleague.adobe.com/en/docs/advertising/integrations/analytics/overview)集成时，将自动创建维度。

## 使用数据填充此维度

此维度通过多种方式收集其值：

* 对于点进流量，数据是从`ef_id`页面URL[中的](page-url.md)查询字符串参数收集的，通常是在广告驱动流量进入网站的页面上。
* 当URL不包含跟踪代码，但Adobe Advertising JavaScript在前两分钟内检测到点击时，也可以捕获点进流量。
* 对于受支持的显示到达流量，Adobe Advertising使用补充ID (`SDID`)补充后端上的值。

>[!NOTE]
>
>EF ID区分大小写。 如果您的实施强制将URL跟踪转换为小写，则Adobe Advertising不会识别EF ID。

## 维度项目

Dimension项目包括由支持的广告网络生成的广告点击标识符。 字符串格式取决于生成该字符串的网络和渠道。

### Google Ads搜索广告

```text
{gclid}:G:{s}
```

* **`gclid`**： Google点击ID (GCLID)。
* **`s`**：网络类型（`"s"`用于搜索）。

### Microsoft Advertising搜索广告

```text
{msclkid}:G:{s}
```

* **`msclkid`**： Microsoft点击ID (MSCLKID)。
* **`s`**：网络类型（`"s"`用于搜索）。

### 在其他搜索引擎上显示广告和搜索广告

```text
{amovid}:{ts}:{channel}
```

* **`amovid`**： Adobe Advertising访客ID，也称为冲浪者ID。
* **`ts`**： Adobe Advertising生成的时间戳。
* **`channel`**：负责点击或曝光的渠道类型：
   * **`d`**：点击DSP显示广告（显示点进）。
   * **`i`**： DSP显示广告（显示显示显示到达）的展示。
   * **`s`**：点击搜索广告（搜索点进）。

### 示例

```text
CjwKCAiAkbbMBhB2EiwANbxtbb9L573Dys0rjTDqcMo3x7tv2yEfh1RGb8exG9N892NoMqAzMBEGmhoCWxwQAvD_BwE:G:s
06207ca63ae6f4fa832197585547393c:20260301111101:i
WcmibgAAAHJK1RyY:1551968087687:d
```
