---
title: addProductEvent
description: 将自定义事件添加到产品变量和事件变量。
translation-type: tm+mt
source-git-commit: 3359ed8e7ef7979be57ca5ec9ca1803fc52afe88
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 98%

---


# Adobe 插件：addProductEvent

>[!IMPORTANT]
>
>此插件由 Adobe Consulting 团队提供，旨在帮助您从 Adobe Analytics 中获取更多的价值。Adobe 客户关怀团队不提供对此插件的支持，包括安装或疑难解答。如果您需要关于此插件的帮助，请与贵组织的帐户管理员联系。他们可以为您安排与顾问的答疑会，以便您向顾问寻求帮助。

`addProductEvent` 插件会向 [`products`](../page-vars/products.md) 变量添加数值或货币事件。如果您希望向 `products` 变量添加数值或货币事件而无需担心产品字符串格式，Adobe 建议使用此插件。如果不在 `products` 变量中使用数值或货币事件，则无需使用此插件。

## 使用 Adobe Experience Platform Launch 扩展安装此插件

Adobe 提供了一个扩展，通过该扩展，您可以使用一些最常用的插件。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
1. 单击所需的属性。
1. 转到[!UICONTROL 扩展]选项卡，然后单击[!UICONTROL 目录]按钮
1. 安装并发布[!UICONTROL 常用 Analytics 插件]扩展
1. 如果还没有任何扩展，请使用以下配置创建一个标签为“初始化插件”的规则：
   * 条件：无
   * 事件：核心 - 已加载的库（页面顶部）
1. 使用以下配置向上述规则添加操作：
   * 扩展：常用 Analytics 插件
   * 操作类型：初始化 addProductEvent
1. 保存并发布对上述规则所做的更改。

## 使用 Launch 自定义代码编辑器安装此插件

如果您不想使用插件扩展，则可以使用自定义代码编辑器。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
1. 单击所需的属性。
1. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 扩展下的[!UICONTROL 配置]按钮。
1. 展开[!UICONTROL 使用自定义代码配置跟踪]折叠面板，这会显示[!UICONTROL 打开编辑器]按钮。
1. 打开自定义代码编辑器，并将下面提供的插件代码粘贴到编辑窗口中。
1. 保存并发布对此 Analytics 扩展所做的更改。

## 使用 AppMeasurement 安装此插件

在实例化（使用 [`s_gi`](../functions/s-gi.md)）Analytics 跟踪对象后，将以下代码复制并粘贴到 AppMeasurement 文件中的任意位置。在您的实施中保留代码的注释和版本号可帮助 Adobe 对任何潜在问题进行疑难解答。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: addProductEvent v2.0 */
function addProductEvent(en,ev,ap){var f=en,g=ev,c=ap;if("-v"===f)return{plugin:"addProductEvent",version:"2.0"};var d=function(){if("undefined"!==typeof window.s_c_il)for(var b=0,e;b<window.s_c_il.length;b++)if(e=window.s_c_il[b],e._c&&"s_c"===e._c)return e}();if("undefined"!==typeof d&&(d.contextData.addProductEvent="2.0",window.apl=window.apl||function(b,e,c,d,f){function g(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(!b||"string"===typeof b){if("string"!==typeof e||""===e)return b;c=c||",";d=d||c;1==d&&(d=c,f||(f=1));2==d&&1!=f&&(d=c);e=e.split(",");k=e.length;for(var h=0;h<k;h++)g(b,e[h],c,f)||(b=b?b+d+e[h]:e[h])}return b},"string"===typeof f))if(g=isNaN(g)?"1":String(g),c=c||!1,d.events=window.apl(d.events,f),d.products){var l=d.products.split(","),m=l.length;c=c?0:m-1;for(var b;c<m;c++)b=l[c].split(";"),b[4]&&-1<b[4].indexOf("event")?b[4]=b[4]+"|"+f+"="+g:b[5]?b[4]=f+"="+g:b[4]||(b[3]||(b[3]=""),b[2]||(b[2]=""),b[1]||(b[1]=""),b[4]=f+"="+g),l[c]=b.join(";");d.products=l.join(",")}else d.products=";;;;"+f+"="+g};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用此插件

`addProductEvent` 方法使用以下参数：

* **`en`**（必需，字符串）：要添加到 `products` 变量中最后一个条目的事件。如果 `products` 变量为空，则会创建一个“空白”产品条目，并附加事件（及其值）。
* **`ev`**（必需，字符串）：分配给 `en` 参数中的数值或货币事件的值。如果未设置，则默认为 `1`。
* **`ap`**（可选，布尔值）：如果产品变量当前包含多个产品条目，则值为 `true`（或 `1`）会将事件添加到所有产品条目。如果未设置，则默认为 `false`。

`addProductEvent` 不会返回任何结果。而是将事件及其值添加到 `products` 变量。该插件还会自动将事件添加到 [`events`](../page-vars/events/events-overview.md) 变量中，因为此变量也需要该事件。

## Cookie

addProductEvent 插件不会创建或使用任何 Cookie

## 示例调用

### 示例 1

以下代码会将 `s.products` 变量设置为 `";product1;3;300,;product2;2;122,;product3;1;25;event35=25"`。

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25"
s.events="purchase";
s.addProductEvent("event35", "25");
```

上述代码还会将 `s.events` 变量设置为 `"purchase,event35"`

### 示例 2

以下代码会将 `s.products` 变量设置为 `";product1;3;300;event35=25,;product2;2;122;event35=25,;product3;1;25;event35=25"`

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25";
s.addProductEvent("event35", 25, 1);
```

如果 `addProductEvent` 调用中的第三个参数是 `true`（或 `1`），则每个产品条目会将调用中指定的事件添加到其值中。

### 示例 3

以下代码会将 `s.products` 变量设置为 `";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25;event33= 12|event34=10|event35=15"`

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25";
s.events="purchase,event2";
s.addProductEvent("event33", "12");
s.addProductEvent("event34", "10");
s.addProductEvent("event35", "15");
```

上述代码还会将 `s.events` 变量设置为 `"purchase,event2,event33,event34,event35"`

### 示例 4

以下代码会将 `s.products` 变量设置为 `";product1;3;300;event2=10|event33=12|event34=10|event35=15;eVar33=large|eVar34=men|eVar35=blue, ;product2;2;122;event33=12|event34=10|event35=15,;product3;1;25;event33=12|event34=10|event35=15"`

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25"
s.events="purchase,event2"
s.addProductEvent("event33", "12", 1);
s.addProductEvent("event34", 10, 1);
s.addProductEvent("event35", "15", 1);
```

上述代码还会将 `s.events` 变量设置为 `"purchase,event2,event33,event34,event35"`。

>[!NOTE]
>
>调用中的第二个参数可以是整数&#x200B;**或者**&#x200B;表示整数/数字的字符串

### 示例 5

如果尚未设置 `s.products`，以下代码会将其设置为 `";;;;event35=25"`

```js
s.addProductEvent("event35", "25");
```

上述代码还会将 `"event35"` 附加到 `s.events` 末尾，**或者**，如果尚未设置 `s.events`，上述代码会将 `s.events` 设置为 `"event35"`

## 版本历史记录

### 2.0（2021年3月19日）

* 已添加版本号作为上下文数据。

### 1.0（2019 年 10 月 7 日）

* 第一版。
