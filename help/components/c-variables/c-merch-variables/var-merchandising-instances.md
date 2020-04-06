---
description: 描述实例如何在促销变量上进行计数。
keywords: Analytics Implementation
title: 有关促销变量的实例
topic: Developer and implementation
uuid: 4cdfd53e-88aa-48cf-a135-98f7fc8dcece
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 有关促销变量的实例

描述实例如何在促销变量上进行计数。

销售变量当前不支持实例。 如果您注意到报表中包含销售变量的实例，则表明eVar正在产品字符串外的某些位置设置，不应将其视为所选销售变量的实际实例计数。

如果您使用“转换变量语法”，则每次设置变量时都会计算一个实例。 但是，该实例归因于“无”，除非每次设置变量时都发生以下情况：

* 设置绑定事件。
* products变量已设置。
* 销售eVar有值。

例如，以下eVar1实例被分配到“Outdoors:Ski Goggles”:

```js
s.eVar1="Outdoors:Ski Goggles" 
s.events="prodView" 
s.products=";Fernie Snow Goggles"
```

但是，在下一个示例中，eVar1的实例将分配到“无”，因为当设置eVar时，不满足所有条件(没有绑定事件，并且未设置products变量):

访问的第1页：

```js
s.eVar1="Outdoors:Ski Goggles"
```

访问的第2页：

```js
s.events="prodView" 
s.products=";Fernie Snow Goggles"
```

如果在未发生绑定事件的页面上为eVar设置了值，或者在产品字符串中设置了eVar值而没有绑定事件，则将分配到“无”。

>[!NOTE] 当前用于计数有关促销变量的实例的功能正在审核中，并计划在下一个发行版本中进行更改。

