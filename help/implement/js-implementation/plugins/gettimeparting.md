---
description: getTimeParting 插件可使用小时、星期、周末和工作日等值填充自定义变量。Analysis Workspace 提供了一些现成的“时间区分”维度。如果除 Analysis Workspace 之外，其他 Analytics 解决方案中也需要使用时间区分维度，则应该使用此插件。
keywords: Analytics Implementation
subtopic: Plug-ins
title: getTimeParting
topic: Developer and implementation
uuid: 74f696a3-7169-4560-89b2-478b3d8385e1
translation-type: tm+mt
source-git-commit: 73d20b23e38bc619c156c418c95096a94d2fdfce

---


# getTimeParting

getTimeParting插件提供了一个完整的分析解决方案，允许您捕获网站上发生任何可衡量活动的详细时间。

如果您希望按给定日期范围内任何可重复的时间划分来划分指标，则应使用getTimeParting插件。  例如，getTimeParting插件允许您比较一周中两个不同的日期（例如，所有周日与所有周四）、一天中两个不同的时段（例如，所有早晨与所有晚上），或甚至两个后续分钟（例如，所有上午10:00与所有上午10:01实例）的转换率您在报表中指定的日期范围。

[!DNL Analysis Workspace] 提供了类似的现成尺寸，其格式与此插件提供的格式略有不同(请参 [阅此处](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.html))。  Adobe Consulting建议您阅读本帮助部分的其余部分，以确定此插件是否以更适合您需求的方式提供数据。

如果您不需要按特定日期范围内的可重复时间划分指标，则无需使用getTimeParting插件。  此外，如果您发现“分 [!DNL Analysis Workspace] 时维”足够，则无需实施此插件。

>[!CAUTION] getTimeParting插件4.0+版提供的解决方案与插件的先前版本提供的解决方案截然不同。  如果您选择从4.0之前的版本升级，则应“从头开始”实施解决方案。  换句话说，您应该设置一个全新的eVar（一个eVar），以保存插件提供的数据并仔细阅读本文档，然后实施解决方案。

>[!CAUTION] 另外：此版本的插件与Microsoft Internet explorer浏 *览器不完全兼容* ，但该插件与Microsoft edge浏览器完全兼容。   使用Internet explorer的访客将能够提供时间，但只能在其本地时 *区* ，而不能转换为您指定的时区。  有关不包括Internet explorer浏览器数据但仍将考虑其存在的解决方案，请参阅以下示例。

> [!NOTE]下面的说明需要您更改网站上的数据收集代码。此操作会影响您网站上的数据收集，且只应由具有使用和实施 [!DNL Analytics] 经验的开发人员完成。

> [!WARNING] 在部署到生产之前，应始终测试所有插件实施，以确保数据收集按预期工作。

## 先决条件

无

## 如何实现

* 复制+将以下代码粘贴到AppMeasurement代码的“插件”部分中的任意位置：

```function getTimeParting(a){a=document.documentMode?void 0:a||"Etc/GMT";a=(new Date).toLocaleDateString("en-US",{timeZone:a, minute:"numeric",hour:"numeric",weekday:"long",day:"numeric",year:"numeric",month:"long"});a=/([a-zA-Z]+).*?([a-zA-Z]+).*?([0-9]+).*?([0-9]+)(.*?)([0-9])(.*)/.exec(a);return"year="+a[4]+" | month="+a[2]+" | date="+a[3]+" | day="+a[1]+" | time="+(a[6]+a[7])}```

> [!NOTE] 您还可以使用Adobe Launch等标签管理器来部署插件代码，而无需将其附加到AppMeasurement或任何其他分析解决方案

* 按照doPlugins函数中或您需要捕获时间分段数据的任何其他位置中的如下所述运行getTimeParting函数

**要传入的参数**

* t:(**可选**，但建议使用字符串)要将访客的本地时间转换为的时区名称。  未设置时，默认为“Etc/GMT”或UTC/GMT时间。  请访 [问] https://en.wikipedia.org/wiki/List_of_tz_database_time_zones，获取要输入的值的完整列表。

常见值包括：

* 《美国／纽约》(America/New_York)，东部时间
* 《美国／芝加哥》
* 《美国／丹佛》
* 太平洋时间的“美国／洛杉矶”

## 返回结果

getTimeParting插件返回包含以下内容的字符串：

* 本年度
* 当月
* 当前日期（即当月的某天）
* 当天（即一周中的某天）
* 当前时间（非军事时间）

上述每个项目都由管道(&quot;|&quot;)字符分隔。

## 示例调用

如果您位于法国巴黎，并且希望使用eVar10（在Adobe Analytics中）来捕获分时段数据，请使用以下代码：

```s.eVar10 = getTimeParting("Europe/Paris")```

如果您位于加利福尼亚州圣何塞，请使用以下代码：

```s.eVar10 = getTimeParting("America/Los_Angeles")```

如果您位于非洲国家（加纳），请使用以下代码：

```s.eVar10 = getTimeParting();```

加纳在UTC/GMT时区内。  因此，此示例说明在这种情况下不需要插件参数。

如果您位于纽约并且不希望包括Internet explorer访客的数据，请使用以下代码（因为从IE浏览器返回的值只能在访客的本地时间提供）

```if(!document.documentMode) s.eVar10 = getTimeParting("America/New_York");```
```else s.eVar10 = "Internet Explorer Visitors";```

**调用结果**

如果来自科罗拉多州丹佛的访客在2020年8月31日上午9:15访问某网站，则以下代码……

```s.eVar10 = getTimeParting("Europe/Athens");```

...会将s.eVar10设置为等于 **year=2020|月=八月| date=31| day=星期一|时间=下午6:15**

以下代码……

```s.eVar10 = getTimeParting("America/Nome");```

...将s.eVar10设置为等于 **year=2020|月=八月| date=31| day=星期一|时间=上午6:15**

以下代码……

```s.eVar10 = getTimeParting("Asia/Calcutta");```

...将s.eVar10设置为等于 **year=2020|月=八月| date=31| day=星期一|时间=晚上8:45**

以下代码……

```s.eVar10 = getTimeParting("Australia/Sydney");```

...将s.eVar10设置为等于 **year=2020|月=九月| date=1| day=星期二|时间=上午1:15**

## Adobe Analytics设置

如果要在Adobe Analytics中捕获分时段数据，请设置具有以下特征的新eVar:

* 名称：分时段
* 分配：最近（最后）
* 过期时间：访问
* 所有其他属性使用提供的默认值
