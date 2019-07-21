---
description: 预定义事件列表。
keywords: Analytics实施；event
seo-description: 预定义事件列表。
seo-title: 什么是预定义活动？
solution: Analytics
title: 什么是预定义活动？
topic: 开发人员和实施
uuid: 4d0799ba-0f97-42c3-a620-36c03 f9995 da
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 什么是预定义活动？

预定义事件列表。

| prodView | 在任何时候，访客查看产品，即发生成功事件。 |
|---|---|
| scView | 在任何时候，访客查看购物车，即发生成功事件。 |
| scOpen | 在任何时候，访客第一次打开购物车，即发生成功事件。 |
| scAdd | 在任何时候，产品添加到购物车，即发生成功事件。 |
| scRemove | 在任何时候，项目从购物车中取出，即发生成功事件。 |
| scCheckout | 进入结账的第一个页面时，即发生成功事件。 |
| purchase | 进入结账的最后一个页面（包括收入、订购和件数）时，即发生成功事件。 |

在发生上述任一预定义事件时，即会增加一个该事件的实例。您可以在多个不同报表中查看与该事件相关的量度。请参阅下文以了解用于配置预定义事件的代码示例。

```js
s.events="scAdd"
```

```js
s.events="scOpen,scAdd"
```

* 在上述第一个示例中，*`scAdd`是事件的值。*&#x200B;在任何时候，项目添加到购物车，即会增加该事件。
* 在第二个示例中，同时捕获了两个值。在同一页面上发生多个成功事件时，每个事件都会增加。

