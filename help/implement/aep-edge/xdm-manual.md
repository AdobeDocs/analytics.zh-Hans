---
title: 手动将 XDM 数据映射到 Analytics
description: '手动将 XDM 数据从 Experience Platform 映射到 Adobe Analytics '
translation-type: ht
source-git-commit: 717c3e23eb2c3fb2477bd77ea92a1dce744f02df
workflow-type: ht
source-wordcount: '371'
ht-degree: 100%

---


# 手动将 XDM 数据映射到 Analytics

Adobe Experience Platform (AEP) Web SDK 包括有助于您在 Platform 与 Analytics 之间手动映射数据的辅助工具。

对于未自动映射到 Analytics 的 XDM 数据，您可以添加[上下文数据](https://docs.adobe.com/content/help/zh-Hans/analytics/implementation/vars/page-vars/contextdata.html)以匹配您的[架构](https://docs.adobe.com/content/help/zh-Hans/experience-platform/xdm/schema/composition.html)。然后，Analytics [处理规则](https://docs.adobe.com/content/help/zh-Hans/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/t-processing-rules.html)会使用这些数据来填充 Analytics 变量。

此外，您还可以使用一组默认的操作和产品列表，通过 AEP Web SDK 来发送或检索数据。为此，请参阅[产品](https://docs.adobe.com/content/help/zh-Hans/experience-platform/edge/implement/commerce.html)。

## 上下文数据

为了供 Analytics 使用，应采用点标记对 XDM 数据进行扁平化处理，并作为 `contextData` 提供。以下值对列表显示了 `context data` 示例：

```javascript
{
          "bh": "900",
          "bw": "1680",
          "c": "24",
          "c.a.d.key.[0]": "value1",
          "c.a.d.key.[1]": "value2",
          "c.a.d.object.key1": "value1",
          "c.a.d.object.key2.[0]": "value2",
          "c.a.x.environment.browserdetails.javascriptenabled": "true",
          "c.a.x.environment.type": "browser",
          "cust_hit_time_gmt": "1579781427",
          "g": "http://example.com/home",
          "gn": "home",
          "j": "1.8.5",
          "k": "Y",
          "s": "1680x1050",
          "tnta": "218287:1:0|0,218287:1:0|2,218287:1:0|1,218287:1:0|32767,218287:1:0|1,218287:1:0|0,218287:1:0|1,218287:1:0|0,218287:1:0|1",
          "user_agent": "Mozilla/5.0 AppleWebKit/537.36 Safari/537.36",
          "v": "Y"
        }
```

## 处理规则

可以通过[处理规则](https://docs.adobe.com/content/help/zh-Hans/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/t-processing-rules.html)访问边缘网络收集的所有数据。在 Analytics 中，您可以使用处理规则将上下文数据纳入 Analytics 变量。

例如，在以下规则中，Analytics 设置为使用与 **a.x_atag.search.term（上下文数据）**&#x200B;相关联的数据来填充&#x200B;**内部搜索词 (eVar2)**。

![](assets/examplerule.png)


## XDM 架构

Experience Platform 会使用架构，以便以可重用的一致方式描述数据结构。通过在整个系统中以一致的方式定义数据，更容易保留含义并因此从数据中获取价值。Analytics 上下文数据与架构定义的结构可搭配使用。

以下示例显示如何将 [`event` 命令](https://docs.adobe.com/content/help/zh-Hans/experience-platform/edge/fundamentals/tracking-events.html)与 `xdm` 选项一起使用，以通过 AEP Web SDK 来发送和检索数据。在此示例中，`event` 命令与 [ExperienceEvent 商务详细信息架构](https://github.com/adobe/xdm/blob/1c22180490558e3c13352fe3e0540cb7e93c69ca/docs/reference/context/experienceevent-commerce.schema.md)匹配，因此可以跟踪 productListItems `name` 和 `SKU` 值：


```
alloy("event",{
  "xdm":{
    "commerce":{
      "productViews":{
        "value":1
      }
    },
    "productListItems":[
      {
        "SKU":"HT105",
        "name":"Large Field Hat",
      },
      {
        "SKU":"HT104",
        "name":"Small Field Hat",
      }
    ]
  }
});
```

有关使用 AEP Web SDK 跟踪事件的更多信息，请参阅[跟踪事件](https://docs.adobe.com/content/help/zh-Hans/experience-platform/edge/fundamentals/tracking-events.html)。