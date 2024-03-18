---
title: eVar（促销变量）
description: 与单个产品关联的自定义变量。
feature: Variables
exl-id: 26e0c4cd-3831-4572-afe2-6cda46704ff3
mini-toc-levels: 3
role: Admin, Developer
source-git-commit: 12347957a7a51dc1f8dfb46d489b59a450c2745a
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 90%

---

# eVar（推销）

*此帮助页面介绍了如何实施推销 eVar。有关促销 eVar 如何用作维度的信息，请参阅组件用户指南中的 [eVar（促销维度）](/help/components/dimensions/evar-merchandising.md)。*

有关促销 eVar 如何工作的详细讨论，请参阅[促销 eVar 和产品查找方法](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/merchandising-evars.html?lang=zh-Hans)。

## 在报告包设置中设置 eVar

在实施中使用 eVar 之前，请确保在报告包设置中将 eVar 配置为所需的语法。 请参阅《管理员指南》中的[转化变量](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md)。

>[!WARNING]
>
>未能正确配置推销 eVar 会导致变量出现意外值或数据丢失。确保为您的实施正确配置推销 eVar。

## 使用产品语法实施

启用“产品语法”后，将直接在 `products` 变量内填充推销类别，因此无需选择和设置捆绑事件。推荐使用此方法，除非当发生成功事件时无法在 `products` 中设置此值。

```js
// The bare minimum to set a merchandising eVar with product syntax
s.products = ";Example product;;;;eVar1=Example merchandising value";

// An example single product with product syntax
s.products = "Example category;Example product;1;5.99;event1=1;eVar1=Turtles";

// Tie a merchandising eVar to a different values on two different products
s.products = "Birds;Scarlet Macaw;1;4200;;eVar1=talking bird,Birds;Turtle dove;2;550;;eVar1=love birds";
```

`eVar1` 的值已分配给产品。所有与本产品相关的后续成功事件将计入 eVar 值。

### 使用 Web SDK 的产品语法

如果使用 [**XDM对象**](/help/implement/aep-edge/xdm-var-mapping.md)，产品语法促销变量使用以下XDM字段：

* 产品语法促销 eVar 在 `xdm.productListItems[]._experience.analytics.customDimensions.eVars.eVar1` 下映射到 `xdm.productListItems[]._experience.analytics.customDimensions.eVars.eVar250`。
* 产品语法促销事件在 `xdm.productListItems[]._experience.analytics.event1to100.event1.value` 下映射到 `xdm.productListItems[]._experience.analytics.event901to1000.event1000.value`。 [事件序列化](events/event-serialization.md)XDM 字段在 `xdm.productListItems[]._experience.analytics.event1to100.event1.id` 下映射到 `xdm.productListItems[]._experience.analytics.event901to1000.event1000.id`。

>[!NOTE]
>
>当您在 `productListItems` 下设置事件时，您不需要在事件字符串中设置事件。 如果在两个地方都设置了事件，则事件字符串中的值优先。

以下示例展示了使用多个推销 eVar 和事件的单一[产品](products.md)：

```json
"productListItems": [
  {
    "name": "Bahama Shirt",
    "priceTotal": "12.99",
    "quantity": 3,
    "_experience": {
      "analytics": {
        "customDimensions" : {
          "eVars" : {
            "eVar10" : "green",
            "eVar33" : "large"
          }
        },
        "event1to100" : {
          "event4" : {
            "value" : 1
          },
          "event10" : {
            "value" : 2,
            "id" : "abcd"
          }
        }
      }
    }
  }
]
```

上述示例对象将作为 `";Bahama Shirt;3;12.99;event4|event10=2:abcd;eVar10=green|eVar33=large"` 发送到 Adobe Analytics。

如果使用 [**数据对象**](/help/implement/aep-edge/data-var-mapping.md)，eVar促销用途 `data.__adobe.analytics.eVar1` - `data.__adobe.analytics.eVar250` 遵循AppMeasurement语法。

## 使用转化变量语法实施

如果在 `products` 变量中无法设置 eVar 值，应使用转化变量语法。这种情况通常意味着您的页面没有推销渠道的任何上下文或查找方法。在这类情况下，请先设置推销变量，然后再进入产品页，该值会持续到捆绑事件发生为止。

当在配置期间选择捆绑事件时，eVar 的这个持久值将与该产品关联。例如，如果 `prodView` 指定为捆绑事件，那么只有当该事件发生时，推销类别才会与当前产品列表绑定。只有后续捆绑事件才能更新已分配给产品的推销 eVar。

```js
// Place on the same or previous page before the binding event:
s.eVar1 = "Aviary";

// Place on the page where the binding event occurs:
s.events = "prodView";
s.products = ";Canary";
```

`eVar1` 的值 `"Aviary"` 已分配给产品 `"Canary"`。所有与本产品相关的后续成功事件将计入 `"Canary"`。另外，推销变量的当前值将被绑定到所有后续产品，直到满足以下其中一个条件为止：

* eVar 过期（根据“过期时间”设置）
* 推销 eVar 被新值覆盖。

### 使用 Web SDK 的转化变量语法

如果使用 [**XDM对象**](/help/implement/aep-edge/xdm-var-mapping.md)，语法的操作方式与实现其他语法类似 [eVar](evar.md) 和 [事件](events/events-overview.md). 镜像上述示例的 XDM 如下所示：

在同一或上个事件调用中设置 eVar：

```json
"_experience": {
  "analytics": {
    "customDimensions": {
      "eVars": {
        "eVar1" : "Aviary"
      }
    }
  }
}
```

设置产品字符串的捆绑事件和值：

```json
"commerce": {
  "productViews" : {
    "value" : 1
  }
},
"productListItems": [
  {
    "name": "Canary"
  }
]
```

如果使用 [**数据对象**](/help/implement/aep-edge/data-var-mapping.md)，则镜像上述示例的数据对象将如下所示：

在同一或上个事件调用中设置 eVar：

```json
"data": {
  "__adobe": {
    "analytics": {
      "eVar1": "Aviary"
    }
  }
}
```

设置产品字符串的捆绑事件和值：

```json
"data": {
  "__adobe": {
    "analytics": {
      "events": "prodView",
      "products": ";Canary"
    }
  }
}
```
