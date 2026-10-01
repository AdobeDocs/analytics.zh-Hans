---
title: eVar（促销变量）
description: 与单个产品关联的自定义变量。
feature: Appmeasurement Implementation
exl-id: 26e0c4cd-3831-4572-afe2-6cda46704ff3
mini-toc-levels: 3
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/BdChWcR9AJqLZ0KjOxSvFAjB8-58JmmGahrpvTyFeFI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: ca917b867cd84b09b899ce7b72586f0b15003106
workflow-type: tm+mt
source-wordcount: '787'
ht-degree: 29%
---
# eVar (Merchandising)

>[!BEGINSHADEBOX]

*此帮助页面介绍了如何实施推销 eVar。 有关推销eVar如何用作维度的信息，请参阅《组件用户指南》中的[eVar （促销维度）](/help/components/dimensions/evar-merchandising.md)。*

>[!ENDSHADEBOX]

促销eVar将值捆绑到单个产品，以便涉及每个产品的成功事件将点数计入捆绑到该产品的值。 您可以通过以下两种方式之一设置值：

* **[!UICONTROL 产品语法]**：在[`products`](products.md)变量中设置每个产品的值。
* **[!UICONTROL 转化变量语法]**：在eVar本身中设置值。 值将绑定到包含捆绑事件的点击上的产品。

有关绑定、分配和到期的工作方式，请参阅[eVar （促销维度）](/help/components/dimensions/evar-merchandising.md)。

## 在报告包设置中设置 eVar

在实施中使用 eVar 之前，请确保在报告包设置中将 eVar 配置为所需的语法。 请参阅《管理员指南》中的[转化变量](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md)。

>[!WARNING]
>
>未能正确配置促销 eVar 会导致变量出现意外值或数据丢失。 确保针对您的实施正确配置它。

## 选择语法

当设置`products`变量时促销值可用，或者同一点击中的产品需要不同的值时，请使用[!UICONTROL 产品语法]。 当在产品之前知道该值（例如搜索词或导致访客访问产品的内部促销活动）时，请使用[!UICONTROL 转化变量语法]。 有关完整比较，请参阅[绑定和分配的工作方式](/help/components/dimensions/evar-merchandising.md#how-binding-and-allocation-work)。

## 使用产品语法实施

启用[!UICONTROL 产品语法]后，将直接在`products`变量中设置推销值，因此不使用捆绑事件。 促销eVar进入每个产品的最后一个区段：

```js
s.products = "[category];[name];[quantity];[revenue];[events];[eVars]";
```

使用管道字符(`|`)在同一个产品上分隔多个推销eVar。 即使您未使用数量、收入和事件的空占位符，这些占位符也是必需的。 如果没有这些参数，eVar值将被忽略。

该值将捆绑到该点击上的产品。 以后的值是否替换现有绑定取决于[!UICONTROL 分配]设置。 请参阅[绑定和分配的工作方式](/help/components/dimensions/evar-merchandising.md#how-binding-and-allocation-work)。

```js
// The bare minimum to set a merchandising eVar with product syntax
s.products = ";Example product;;;;eVar1=Example merchandising value";

// An example single product with product syntax
s.products = "Example category;Example product;1;5.99;event1=1;eVar1=Turtles";

// Tie a merchandising eVar to different values on two different products
s.products = "Birds;Scarlet Macaw;1;4200;;eVar1=talking bird,Birds;Turtle dove;2;550;;eVar1=love birds";
```

### 使用 Web SDK 的产品语法

如果使用&#x200B;[**XDM对象**](/help/implement/aep-edge/xdm-var-mapping.md)，则产品语法促销变量使用以下XDM字段：

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

如果使用&#x200B;[**数据对象**](/help/implement/aep-edge/data-var-mapping.md)，则在`data.__adobe.analytics.products`中设置产品语法推销eVar，使用的语法与AppMeasurement `products`变量相同。 上述XDM示例的数据对象等效项：

```json
"data": {
  "__adobe": {
    "analytics": {
      "products": ";Bahama Shirt;3;12.99;event4|event10=2:abcd;eVar10=green|eVar33=large"
    }
  }
}
```

## 使用转化变量语法实施

在`products`变量中无法设置eVar值时，请使用[!UICONTROL 转化变量语法]。 这种情况通常意味着您的产品页面没有促销渠道的上下文或查找方法。 在这些情况下，请将推销eVar设置在捆绑事件发生页面的上面或之前。 该值会一直保留到它过期或被新值覆盖为止。

当点击包含`products`变量和选定的[!UICONTROL 促销捆绑事件]时，eVar的当前值将捆绑到该点击上的每个产品。 在没有捆绑事件的产品旁设置eVar不会捆绑该值。 后续绑定是否替换现有绑定取决于[!UICONTROL 分配]设置。 请参阅[绑定和分配的工作方式](/help/components/dimensions/evar-merchandising.md#how-binding-and-allocation-work)。

有关同时设置多个产品查找方法eVar的示例，请参阅[最佳实践：产品查找方法](/help/components/dimensions/evar-merchandising.md#best-practice-product-finding-methods)。

以下示例在捆绑事件之前设置推销eVar：

```js
// Place on the same or previous page before the binding event:
s.eVar1 = "Aviary";

// Place on the page where the binding event occurs:
s.events = "prodView";
s.products = ";Canary";
```

如果[!UICONTROL 产品视图事件]是捆绑事件，则`eVar1`的值`"Aviary"`将捆绑到产品`"Canary"`。 与此产品相关的后续成功事件将计入`"Aviary"`。 值`"Aviary"`还会绑定到以后包含捆绑事件的点击上的产品，直到满足以下任一条件为止：

* eVar过期（根据[!UICONTROL 过期时间]设置）。
* 促销 eVar 被新值覆盖。

### 使用 Web SDK 的转化变量语法

如果使用&#x200B;[**XDM对象**](/help/implement/aep-edge/xdm-var-mapping.md)，则语法的操作方式与实现其他[eVars](evar.md)和[events](events/events-overview.md)类似。 如果使用&#x200B;[**数据对象**](/help/implement/aep-edge/data-var-mapping.md)，则语法遵循AppMeasurement。

镜像上述AppMeasurement示例的XDM如下所示。

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

镜像上述AppMeasurement示例的数据对象如下所示。

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

