---
title: ActivityMap.link
description: 自定义Activity Map收集链接点击量的方式。
feature: Appmeasurement Implementation
role: Admin, Developer
exl-id: 3a31f80b-dbee-4a45-ac3c-0b8ca198c95a
TQID: 'https://experienceleague.adobe.com/5NCARDGth07l5vixudVzLrE7FVrh82PS4xNrJ61gnow'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 308
ht-degree: 10%

---

# ActivityMap.link

`ActivityMap.link`变量允许您覆盖Activity Map用于设置链接值的逻辑。 此变量适用于您希望拥有比[`ActivityMap.linkExclusions`](../config-vars/activitymap-linkexclusions.md)提供的更多控制权的区域。

>[!CAUTION]
>此变量将完全覆盖Activity Map逻辑。 在此处设置一个返回错误值的覆盖函数可能会导致Activity Map维度和Activity Map覆盖出现数据收集问题。

## 使用Web SDK覆盖链接值

您可以使用[`OnBeforeLinkClickSend`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/onbeforelinkclicksend)回调来更改Web SDK有效负载或中止发送数据。

## 使用Adobe Analytics扩展进行链接覆盖

Adobe Analytics 扩展程序中没有专门的字段来使用此变量。 按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement中的ActivityMap.link和Analytics扩展自定义代码编辑器

为此变量分配一个函数，该函数：

* 接收所单击的HTML元素；并且
* 返回字符串值。 此字符串值是[Activity Map链接](/help/components/dimensions/activity-map-link.md)维度使用的最终值。

如果返回值为[假](https://developer.mozilla.org/zh-CN/docs/Glossary/Falsy)，则清除所有Activity Map上下文数据变量，并且不跟踪任何链接数据。

## 示例

仅使用`<a>`标记中的title属性。 如果标题属性不存在，则不会跟踪任何链接。

```js
s.ActivityMap.link = function(clickedElement) {
  var linkId;
  if (clickedElement && clickedElement.tagName.toUpperCase() === 'A') {
    linkId = clickedElement.getAttribute('title');
  }
  return linkId;
}
```

如果存在，则返回`s.tl`中的手动设置链接名称，否则返回链接URL。

```js
s.ActivityMap.link = function(ele, linkName) {
  if (linkName) {
    return linkName;
  }
  if (ele && ele.tagName == 'A' && ele.href) {
    return ele.href;
  }
}
```

您可以有条件地更改默认链接逻辑，而不是完全替换默认链接逻辑。

```html
<script>
  // Copy the original link function
  var originalLinkFunction = s.ActivityMap.link;
  // Return the link name from s.tl, a modified activity map value, or the original activity map value
  s.ActivityMap.link = function(element,linkName)
  {
    return linkName || customFunction(element) || originalLinkFunction(element,linkName);
  };
</script>

<button type="button" onclick="s.tl(this,'o',customFunction(this)">Add To Cart</button>
```

1. 如果传递了`linkName`，则`tl()`调用了该方法。 返回作为`linkName`传入的`tl()`。
2. 当由Activity Map调用时，永远不会传递`linkName`，因此使用链接元素调用`customFunction()`。 您可以使用任何想要返回值的自定义函数。
3. 如果以上两个值都不返回，则使用通常收集为回退的链接名称。
