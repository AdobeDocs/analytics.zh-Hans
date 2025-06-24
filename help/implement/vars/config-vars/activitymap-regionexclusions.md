---
title: ActivityMap.regionExclusions
description: 按地区筛选Activity Map数据。
role: Admin, Developer
feature: Appmeasurement Implementation
exl-id: 353282aa-860c-45dc-a6b0-8d9f1fa09f13
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 13%

---

# ActivityMap.regionExclusions

`ActivityMap.regionExclusions`变量允许您根据[Activity Map区域](/help/components/dimensions/activity-map-region.md)维度中收集的维度项，有选择地筛选或排除Activity Map数据。

## Web SDK扩展中的区域排除项

启用&#x200B;**[!UICONTROL 启用“点击数据收集”]**&#x200B;后，请使用&#x200B;**[!UICONTROL 筛选条件“点击属性”]**&#x200B;回调代码块。 在此代码块中，您可以检查`content.linkRegion`的值，然后更改该值或放弃链接跟踪数据的集合。

## Web SDK JavaScript库中的区域排除项

启用[`clickCollectionEnabled`](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled)后，在`clickCollection`对象中使用`filterClickDetails`回调。 在此回调中，您可以检查`linkRegion`的值，然后更改该值或放弃链接跟踪数据的集合。

```js
alloy("configure", {
  clickCollectionEnabled: true,
  clickCollection: {
    filterClickDetails: function(content) {
      // If the clicked region has personal links in it, don't send click data
      if(content.linkRegion.includes("personal")) {
        return false;
      }
    }
  }
});
```

## 使用Adobe Analytics扩展的区域排除项

Adobe Analytics 扩展程序中没有专门的字段来使用此变量。 按照 AppMeasurement 语法使用自定义代码编辑器。

## 使用AppMeasurement的s.ActivityMap.regionExclusions

`s.ActivityMap.regionExclusions`变量是一个字符串，其中包含要从Activity Map跟踪中排除的逗号分隔短语。 如果有任何短语与在[Activity Map区域](/help/components/dimensions/activity-map-region.md)维度中收集的值匹配，则将从点击中删除所有Activity Map数据。

```html
<script>
  var s = s_gi("examplersid");
  s.ActivityMap.regionExclusions = "contact";
</script>

<!-- Clicking any of these links tracks normally. -->
<!-- While "contact" is present, it is not tracked in region. The region is "nav" -->
<nav>
  <a href="index.html">Home</a>
  <a href="products.html">View our products</a>
  <a href="contact.html">Contact us</a>
</nav>

<!-- Activity Map data is not tracked for any of these links. -->
<!-- All these links belong to the region "Personal contact information" -->
<div id="personal-contact-information">
 <a href="mailto:user@example.com">Example user</a>
 <a href="mailto:user2@example.com">Example user 2</a>
 <a href="mailto:user3@example.com">Example user 3</a>
</div>
```
