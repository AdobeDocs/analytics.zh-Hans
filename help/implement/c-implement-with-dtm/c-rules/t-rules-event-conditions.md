---
description: 这些条件决定了何时触发基于事件的规则。
keywords: 动态标签管理；规则；创建规则；新规则；基于事件的规则；延迟链接激活；将事件处理函数直接应用于元素；冒泡；事件冒泡
seo-description: 这些条件决定了何时触发基于事件的规则。
seo-title: 为基于事件的规则创建条件
solution: Experience Cloud，分析，目标，动态标签管理
title: 为基于事件的规则创建条件
uuid: a847391c-5aec-4d64-8a35-388587731598
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# 为基于事件的规则创建条件

这些条件决定了何时触发基于事件的规则。

1. 选择您要跟踪的交互类型，例如鼠标点击或表单提交。

   ![](assets/condition-event-based.png)

   有关更多信息，请参阅“Adobe 标签管理产品文档”中的[事件类型](https://marketing.adobe.com/resources/help/en_US/dtm/event_types.html)。

1. 根据需要启用以下选项：

   | 元素 | 描述 |
   |--- |--- |
   | 延迟链接激活 | 在事件激活链接且希望链接延迟至事件有时间触发时启用。 |
   | 将事件处理程序直接应用于元素 | 将事件处理程序应用于特定目标元素。此设置绑定到浏览器中的事件冒泡和分层概念。 |

   For example, when you click an image inside an anchor tag like `<a href="abc.html"><img src="xyz.png"/></a>`, you might expect the click to be associated with the anchor tag, because the tag is in the bubble stream. However, when you inspect the click in the developer tools, the click may actually affect only the `<img>` tag. To ensure that the event is handled correctly, associate the click with the `<img>` tag and do not depend on the browser to bubble up the click to a parent element. An event like a click can potentially bubble up to `<body>`. 请务必了解事件绑定的实际位置，并专门将其确定为目标，以确保规则正确触发。

   *事件冒泡*&#x200B;是指事件首先由最内部的元素捕获和处理，然后被传播到外部元素。

1. 指示您希望跟踪的标记的名称，以及您希望匹配的其他标记属性。

   ![](assets/condition-event-based2.png)

   有关如何找到正确的元素标记的信息，请参阅“动态标签管理产品文档”中的[使用 CSS 选择器](https://marketing.adobe.com/resources/help/en_US/dtm/css-selector.html)。

1. 选择并设置您希望绑定到规则的任何其他标准或条件类型。

   ![](assets/condition-event-based3.png)

1. 指示与事件冒泡相关的首选项。

   事件冒泡是 HTML DOM 中的一种事件传播方式。

   | 如果您... | 选中此选项 |
   |--- |--- |
   | 希望已识别的规则选择器子元素中的相关交互触发规则。 | 允许子元素中的事件冒泡。。 |
   | 希望在子元素已触发其自身的事件时阻止事件冒泡。 | 在子元素已触发事件时不允许这么做。 |
   | 不希望已识别的规则选择器事件超出事件层级中的元素本身。 | 不允许事件向上冒泡至父元素。 |
