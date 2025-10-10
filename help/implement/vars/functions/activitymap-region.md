---
title: ActivityMap.region
description: 自定义Activity Map收集所点击区域的方式。
feature: Appmeasurement Implementation
role: Admin, Developer
exl-id: 9bbdb124-b865-4431-8a98-9814c3f2e65c
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 13%

---

# ActivityMap.region

`ActivityMap.region`变量允许您覆盖Activity Map用于设置区域值的逻辑。 此变量适用于您希望拥有比[`ActivityMap.regionExclusions`](../config-vars/activitymap-regionexclusions.md)提供的更多控制权的区域。

>[!CAUTION]
>此变量将完全覆盖Activity Map逻辑。 在此处设置一个返回错误值的覆盖函数可能会导致Activity Map维度和Activity Map覆盖出现数据收集问题。

## 使用Web SDK覆盖区域值

您可以使用[`OnBeforeLinkClickSend`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/onbeforelinkclicksend)回调来更改Web SDK有效负载或中止发送数据。

## 使用Adobe Analytics扩展的区域覆盖

Adobe Analytics 扩展程序中没有专门的字段来使用此变量。 按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement中的ActivityMap.region和Analytics扩展自定义代码编辑器

为此变量分配一个函数，该函数：

* 接收所单击的HTML元素；并且
* 返回字符串值。 此字符串值是[Activity Map Region](/help/components/dimensions/activity-map-region.md)维度使用的最终值。

如果返回值为[假](https://developer.mozilla.org/zh-CN/docs/Glossary/Falsy)，则清除所有Activity Map上下文数据变量，并且不跟踪任何链接数据。

## 示例

使用小写标记名称作为区域：

```js
s.ActivityMap.region = function(clickedElement) {
  while (clickedElement && (clickedElement = clickedElement.parentNode)) {
    var regionId = clickedElement.tagName;
    if (regionId) {
      return regionId.toLowerCase();
    }
  }
}
```

使用特定的所需类名作为区域：

```js
s.ActivityMap.region = function(ele) {
  var className,
  classNames = {
    'header': 1,
    'navbar': 1,
    'left-content': 1,
    'main-content': 1,
    'footer': 1,
  };
  while ((ele && (ele = ele.parentNode))) {
    if ((className = ele.className)) {
      let classes = className.split(' ');
      for (let i = 0; i < classes.length; i++) {
        if (classNames[classes[i]]) {
          return classes[i];
        }
      }
    }
  }
  return "BODY";
}
```
