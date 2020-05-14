---
title: 手动将XDM数据映射到分析
description: '手动将XDM数据从Experience Platform映射到Adobe Analytics '
translation-type: tm+mt
source-git-commit: 717c3e23eb2c3fb2477bd77ea92a1dce744f02df
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 1%

---


# 手动将XDM数据映射到分析

Adobe Experience Platform(AEP)Web SDK包括帮助您在平台和分析之间手动映射数据的帮助。

对于未自动映射到Analytics的XDM数据，您可以添加上 [下文数据](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/contextdata.html) ，以匹配 [模式](https://docs.adobe.com/content/help/en/experience-platform/xdm/schema/composition.html)。 然后，Analytics处理规则可使用 [它填充](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/t-processing-rules.html) Analytics变量。

此外，您可以使用一组默认的操作和产品列表来使用AEP Web SDK发送或检索数据。 为此，请参阅产 [品](https://docs.adobe.com/content/help/en/experience-platform/edge/implement/commerce.html)。

## 上下文数据

要供Analytics使用，XDM数据使用点表示法进行拼合并提供 `contextData`。 以下值对的列表显示了以下示例 `context data`:

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

边缘网络收集的所有数据都可以通过处理 [规则访问](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/t-processing-rules.html)。 在Analytics中，您可以使用处理规则将上下文数据合并到Analytics变量中。

例如，在以下规则中，Analytics设置为 **用与a.x_atag.search.term(Context Data)关联的数** 据填充内部搜索词(eVar2) ****。

![](assets/examplerule.png)


## XDM模式

Experience Platform使用模式以一致、可重用的方式描述数据结构。 通过跨系统一致地定义数据，更容易保留含义并从数据中获得价值。 Analytics上下文数据与由模式定义的结构配合使用。

以下示例显示如 [`event` 何与](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/tracking-events.html) “AEP Web SDK `xdm` ”选项一起使用命令以发送和检索数据。 在此示例中，该命 `event` 令与ExperienceEvent Commerce [Details模式匹配](https://github.com/adobe/xdm/blob/1c22180490558e3c13352fe3e0540cb7e93c69ca/docs/reference/context/experienceevent-commerce.schema.md) ，以便跟踪productListItems `name` 和 `SKU` 值：


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

有关使用AEP Web SDK跟踪事件的更多信息，请参阅 [跟踪事件](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/tracking-events.html)。