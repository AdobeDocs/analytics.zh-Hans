---
title: 营销渠道的处理规则
description: 使用规则确定点击所属的营销渠道。
feature: Marketing Channels
exl-id: 825f70a5-cce3-4b1c-bb42-828388348216
role: Admin
source-git-commit: e934de3938f013067d6bbd6b516b0444b0c9f782
workflow-type: tm+mt
source-wordcount: '819'
ht-degree: 3%

---

# 营销渠道处理规则

_此页面指的是将营销渠道分配给点击的处理规则。 请参阅[处理规则](../general/processing-rules/pr-overview.md)以了解允许您调整数据收集方式的功能。_

营销渠道处理规则允许您创建逻辑以确定[营销渠道](/help/components/dimensions/marketing-channel.md)和[营销渠道详细信息](/help/components/dimensions/marketing-detail.md)维度的值。 使用[营销渠道管理器](c-channels.md)确定您使用的营销渠道，然后使用处理规则确定每个渠道的设置方式。

![营销渠道桶](assets/buckets_2.png)

**[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 报表包]** > **[!UICONTROL 编辑设置]** > **[!UICONTROL 营销渠道]** > **[!UICONTROL 营销渠道处理规则]**

运行[自动设置](/help/components/c-marketing-channels/c-getting-started-mchannel.md)后，它将为设置期间生成的每个渠道创建一个规则。

![默认规则](assets/marketing_channel_rules.png)

您可以使用多个规则来定义单个营销渠道。 如果要根据规则条件以不同方式设置渠道详细信息，为单个渠道使用多个规则可能会有帮助。 您还可以使用多个条件来定义单个规则。

## 规则定义

每个规则都包含一个条件和分配：

* **[!UICONTROL 如果以下任意或全部为true]**：如果向单个规则添加多个条件，则可以确定是否必须满足所有条件或满足任意一个条件才能设置渠道和相关值。
* **规则条件**：指定必须满足的一个或多个规则条件。 通常，您会指定点击必须匹配才能符合营销渠道条件的维度。
* **[!UICONTROL 然后执行以下操作]**：当规则条件匹配时，设置[营销渠道](/help/components/dimensions/marketing-channel.md) （[!UICONTROL 将该渠道标识为]）和[营销渠道详细信息](/help/components/dimensions/marketing-detail.md) （[!UICONTROL 设置该渠道的值]）。

## 规则条件

设置规则条件时，可以使用以下选项。

>[!NOTE]
>
>所有文本字段均评估为&#x200B;**不区分大小写**。 例如，如果您使用查询字符串参数`cmp`等于`abc123`的规则条件，则查询字符串参数和值都可以使用大写和小写的任意组合。

**Adobe检测到的条件**&#x200B;不包含任何用于输入文本的选项或字段。

| Adobe检测到的条件 | 描述 |
|---|---|
| **[!UICONTROL 匹配付费搜索检测规则]** | 点击来自可识别的搜索引擎，并且与[付费搜索检测规则](../general/paid-search-detection/paid-search-detection.md)匹配。 |
| **[!UICONTROL 匹配免费搜索检测规则]** | 点击源自可识别的搜索引擎，与付费搜索检测规则不匹配。 |
| **[!UICONTROL 引用网站与内部URL筛选器匹配]** | 点击包含与[内部URL过滤器](/help/components/dimensions/referrer.md)匹配的[反向链接](../general/internal-url-filter-admin.md)。 |
| **[!UICONTROL 引用网站与内部URL筛选器不匹配]** | 点击包含与内部URL过滤器不匹配的反向链接。 |
| **[!UICONTROL 为访问的首次点击]** | 点击是访问中的第一次。 |
| **[!UICONTROL 反向链接为社交网络]** | [反向链接类型](/help/components/dimensions/referrer-type.md)为“社交网络”。 |
| **[!UICONTROL 反向链接不是社交网络]** | 反向链接类型不是“社交网络”。 |
| **[!UICONTROL 反向链接是对话式人工智能]** | 反向链接类型是“对话人工智能”。 |
| **[!UICONTROL 反向链接不是对话式AI]** | 反向链接类型不是“对话式人工智能”。 |

**点击属性**&#x200B;允许您指定要查找的维度、匹配运算符和值。

| 点击属性条件 | 描述 |
|---|---|
| **[!UICONTROL 页面]** | [页面](/help/components/dimensions/page.md)维度。 |
| **[!UICONTROL 页面域]** | URL的域。 例如，`products.example.com`。 |
| **[!UICONTROL 页面域和路径]** | URL的域和路径。 例如，`products.example.com/mens/pants/overview.html`。 |
| **[!UICONTROL 页面根域]** | URL的根域。 例如，`example.co.uk`。 |
| **[!UICONTROL 页面 URL]** | 整页URL。 |
| **[!UICONTROL 查询字符串参数]** | 页面URL中的单个查询字符串参数。 为每个规则条件使用一个查询字符串参数。 如果要在规则中包含多个查询字符串参数，请使用多个规则条件。 |
| **[!UICONTROL 反向链接]** | [推荐人](/help/components/dimensions/referrer.md)维度。 |
| **[!UICONTROL 反向链接域]** | [反向链接域](/help/components/dimensions/referring-domain.md)维度。 |
| **[!UICONTROL 反向链接域和路径]** | 反向链接域和反向链接的URL路径的连接。 例如，`www.example.com/products/id/12345`或`ad.example.com/foo`。 |
| **[!UICONTROL 引用参数]** | 反向链接中的查询字符串参数。 |
| **[!UICONTROL 反向链接根域]** | 反向链接根域。 |
| **[!UICONTROL 搜索引擎]** | [搜索引擎](/help/components/dimensions/search-engine.md)维度。 |
| **[!UICONTROL 搜索关键词]** | [搜索关键字](/help/components/dimensions/search-keyword.md)维度。 |
| **[!UICONTROL 搜索引擎+搜索关键词]** | 搜索引擎和搜索关键词的串联。 |
| **[!UICONTROL AMO ID]** | Adobe Advertising和Advertising Analytics集成使用的主要跟踪代码。 如果启用其中一个集成，则可以使用跟踪代码前缀来标识特定于Advertising的渠道。 以“AL”开头的值适用于Search和Social。 以“AC”开头的值用于显示。 在营销渠道中使用AMO ID时，点击/成本/展示次数量度可归因于正确的渠道。 |
| **[!UICONTROL AMO EF ID]** | Adobe Advertising使用的辅助跟踪代码。 用作将数据发送回Advertising的密钥。 它可用于标识显示点进次数，并将视图点进次数显示为两个单独的营销渠道。 为此，请为以`:d`结尾的“AMO EF ID”设置营销渠道逻辑，为显示点进设置营销渠道逻辑，或者为显示视图点进设置以`:i`结尾的“AMO EF ID”营销渠道逻辑。 如果您不希望将显示拆分为两个渠道，请改用AMO ID维度。 |

**转化变量**&#x200B;允许您指定自定义eVar、匹配运算符和要查找的值。

| 转化变量条件 | 描述 |
|---|---|
| **eVar 1-250** | 关联的[eVar](/help/components/dimensions/evar.md)维度。 |
