---
title: ActivityMap.linkExclusions
description: 按链接名称筛选Activity Map数据。
role: Admin, Developer
feature: Appmeasurement Implementation
exl-id: 9fc95016-362d-4c21-806e-e23adce9b6f7
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 12%

---

# ActivityMap.linkExclusions

`ActivityMap.linkExclusions`变量允许您根据[Activity Map链接](/help/components/dimensions/activity-map-link.md)维度中的文本，有选择地筛选或排除Activity Map数据。

## Web SDK扩展中的链接排除项

启用&#x200B;**[!UICONTROL 启用“点击数据收集”]**&#x200B;后，请使用&#x200B;**[!UICONTROL 筛选条件“点击属性”]**&#x200B;回调代码块。 在此代码块中，您可以检查`content.linkName`的值，然后更改该值或放弃链接跟踪数据的集合。

## Web SDK JavaScript库中的链接排除项

启用[`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled)后，在`clickCollection`对象中使用`filterClickDetails`回调。 在此回调中，您可以检查`linkName`的值，然后更改该值或放弃链接跟踪数据的集合。

```js
alloy("configure", {
  clickCollectionEnabled: true,
  clickCollection: {
    filterClickDetails: function(content) {
      // If the link is a clickable telephone number, anonymize it
      if(content.linkUrl.includes("tel:")) {
        content.linkName = content.linkUrl = "Phone number";
      }
      // If the link is an email address, anonymize it
      if(content.linkUrl.includes("mailto:")) {
        content.linkName = content.linkUrl = "Email address";
      }
    }
  }
});
```

## 使用Adobe Analytics扩展链接排除项

Adobe Analytics 扩展程序中没有专门的字段来使用此变量。 按照 AppMeasurement 语法使用自定义代码编辑器。

## 使用AppMeasurement的s.ActivityMap.linkExclusions

`s.ActivityMap.linkExclusions`变量是一个字符串，其中包含要从Activity Map跟踪中排除的以逗号分隔的短语值。 如果有任何短语与在[Activity Map链接](/help/components/dimensions/activity-map-link.md)维度中收集的值匹配，则会从点击中删除所有Activity Map数据。 请注意，此变量查看`linkName`，而不是`linkUrl`。

```html
<script>
  var s = s_gi("examplersid");
  s.ActivityMap.linkExclusions = "Contact";
</script>

<!-- Clicking this link tracks normally -->
<a href="products.html">View our products</a>

<!-- Activity Map data is not tracked for this link -->
<a href="mailto:user@example.com">Contact this user</a>
```
