---
title: ActivityMap.regionIDAttribute
description: 更改Activity Map查找的属性以确定区域。
feature: Variables
role: Admin, Developer
exl-id: 4aec045e-1a86-412f-bd37-777ac49ccc7d
source-git-commit: bcab98e453247c74b7d96497d34e6aea9ca32bc7
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 11%

---

# ActivityMap.regionIDAttribute

`ActivityMap.regionIDAttribute`变量允许您更改Activity Map在确定[Activity Map区域](/help/components/dimensions/activity-map-region.md)维度时查找的属性。 如果网站的结构方式使`id`属性对Activity Map区域不那么有用，则可以设置此变量来查看其他属性。

## Web SDK扩展中的“区域ID”属性

启用&#x200B;**[!UICONTROL 启用“点击数据收集”]**&#x200B;后，请使用&#x200B;**[!UICONTROL 筛选条件“点击属性”]**&#x200B;回调代码块。 在此代码块中，您可以检查`content.clickedElement`的值，然后更改该值或放弃链接跟踪数据的集合。

## Web SDK JavaScript库中的“区域ID”属性

启用[`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled)后，在`clickCollection`对象中使用`filterClickDetails`回调。 在此回调中，您可以检查`clickedElement`的值，并自定义所收集区域的逻辑。

```js
alloy("configure", {
  clickCollectionEnabled: true,
  clickCollection: {
    filterClickDetails: function(content) {
      // If the clicked element was in a table, set the region to the contents of the data-custom attribute
      // If the clicked element was not in a table, or if the data-custom attribute doesn't exist, leave region as-is
      content.region = content.clickedElement.closest('table')?.getAttribute('data-custom') || content.region;
    }
  }
});
```

## 使用Adobe Analytics扩展的“区域ID”属性

Adobe Analytics 扩展程序中没有专门的字段来使用此变量。 按照 AppMeasurement 语法使用自定义代码编辑器。

## s.ActivityMap.regionIDAttribute使用AppMeasurement

`s.ActivityMap.regionIDAttribute`变量是一个字符串，它表示用于确定[Activity Map区域](/help/components/dimensions/activity-map-region.md)维度的属性。 默认情况下，此变量设置为`id`。 如果更改此变量，则Activity Map不再查找`id`属性，但仍会查找其他条件以确定区域（如语义元素）。

```html
<script>
  var s = s_gi("examplersid");
  s.ActivityMap.regionIDAttribute = "data-custom";
</script>

<!-- Clicking any of these links populates the region dimension with 'left-nav' -->
<div id="676967617A656C6C65" data-custom="left-nav">
  <a href="index.html">Home</a>
  <a href="products.html">View our products</a>
  <a href="contact.html">Contact us</a>
</div>
```
