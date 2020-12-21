---
title: getTimeParting
description: 测量特定操作发生的时间。
translation-type: tm+mt
source-git-commit: 01dce7813d60801f5c7826a903bb97d0db5d2617
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 84%

---


# Adobe 插件：getTimeParting

>[!IMPORTANT]
>
>此插件由 Adobe Consulting 团队提供，旨在帮助您从 Adobe Analytics 中获取更多的价值。Adobe 客户关怀团队不提供对此插件的支持，包括安装或疑难解答。如果您需要关于此插件的帮助，请与贵组织的帐户管理员联系。他们可以为您安排与顾问的答疑会，以便您向顾问寻求帮助。

`getTimeParting` 插件允许您捕获网站上发生任何可衡量活动的详细时间。如果您希望按任一可重复分时段对指定日期范围内的量度进行细分，此插件将非常有帮助。例如，您可以比较一周内某两天的转化率，如所有星期日的转化率与所有星期四的转化率。您还可以比较一天内的不同时段，如比较所有上午与所有晚上。

Analysis Workspace 提供了与此插件类似的开箱即用维度，只是维度的格式略有不同。有关更多信息，请参阅 Analytics 用户指南中的[时间划分维度](/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md)。有些组织发现 Analysis Workspace 提供的开箱即用维度足以满足其需求。

>[!IMPORTANT]
>
>此插件的4.0+版与先前版本有显着不同。 Adobe 强烈建议您“从头开始”实施此插件。引用了版本 4.0 之前插件的代码与此插件的当前版本不兼容。

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
   * 操作类型：初始化 getTimeParting
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
/* Adobe Consulting Plugin: getTimeParting v6.2 */
var getTimeParting=function(a){a=document.documentMode?void 0:a||"Etc/GMT";a=(new Date).toLocaleDateString("en-US",{timeZone:a, minute:"numeric",hour:"numeric",weekday:"long",day:"numeric",year:"numeric",month:"long"});a=/([a-zA-Z]+).*?([a-zA-Z]+).*?([0-9]+).*?([0-9]+)(.*?)([0-9])(.*)/.exec(a);return"year="+a[4]+" | month="+a[2]+" | date="+a[3]+" | day="+a[1]+" | time="+(a[6]+a[7])};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用此插件

`getTimeParting` 方法会使用以下参数：

**`t`**（可选但建议使用的字符串）：要将访客的本地时间转换到的时区的名称。默认为 UTC/GMT 时间。请参阅维基百科上的 [TZ 时区数据库所含时区列表](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)，以获取有效值的完整列表。

常见有效值包括：

* `"America/New_York"`（表示东部时间）
* `"America/Chicago"`（表示中部时间）
* `"America/Denver"`（表示山地时间）
* `"America/Los_Angeles"`（表示太平洋时间）

调用此方法将返回一个字符串，其中包含以管道 (`|`) 分隔的以下项：

* 当前年份
* 当前月份
* 当前日期
* 星期几
* 当前时间（上午/下午）

## 示例调用

### 特定时区示例

如果客户位于法国巴黎，请使用以下示例代码：

```js
s.eVarX = getTimeParting("Europe/Paris");
```

如果客户位于加利福尼亚州圣何塞，请使用以下示例代码：

```js
s.eVarX = getTimeParting("America/Los_Angeles");
```

如果客户位于非洲加纳，请使用以下示例代码：

```js
s.eVarX = getTimeParting();
```

加纳处于 UTC/GMT 时区内。此示例说明UTC/GMT不需要插件参数。

### 考虑 Internet Explorer 浏览器

如果要从Internet Explorer访客中排除分时段数据，请使用以下示例。 从IE浏览器返回的值仅在访客的本地时间。

```js
if(!document.documentMode) s.eVarX = getTimeParting("America/New_York");
else s.eVarX = "Internet Explorer Visitors";
```

### 调用结果

假设2020年8月31日美国丹佛科罗拉多州访客在上午9:15访问某网站。

```js
s.eVar10 = getTimeParting("Europe/Athens");
// Returns the string value "year=2020 | month=August | date=31 | day=Friday | time=6:15 PM"

s.eVar11 = getTimeParting("America/Nome");
// Returns the string value "year=2020 | month=August | date=31 | day=Friday | time=6:15 AM"

s.eVar12 = getTimeParting("Asia/Calcutta");
// Returns the string value "year=2020 | month=August | date=31 | day=Friday | time=8:45 PM"

s.eVar13 = getTimeParting("Australia/Sydney");
// Returns the string value "year=2020 | month=September | date=1 | day=Saturday | time=1:15 AM"
```

## 版本历史记录

### 6.2（2019 年 11 月 5 日）

* 修复了若干小错误
* 从整体上缩小了代码大小

### 6.1（2018 年 11 月 26 日）

* 对 Internet Explorer 浏览器问题进行了修复。此类浏览器可以返回时间，但只能返回访客所在地区的本地时间。

### 6.0（2018 年 8 月 14 日）

* 为符合国际标准，进行了彻底重写。现在可正确转换夏令时和所有时区。

### 5.0（2018 年 4 月 17 日）

* 修正版本（重新编译，代码更小）
* 由于现在可自动检测到夏令时开始/结束日期，因此无需再使用 `tpDST` 参数。

>[!CAUTION]
>
>此插件的先前版本未能适应未来所有时间。 如果使用此插件的先前版本，Adobe强烈建议升级到最新版本，以避免JavaScript错误和数据丢失。 如果升级此插件不可行，请确保插件代码中的`s._tpdst`变量将来包含相应的年份。

### 4.0（2016 年 8 月 22 日）

* 提供了全新的解决方案，现在可包含年份、月份和日期信息。
