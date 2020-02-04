---
title: getTimeParting
description: 测量特定操作发生的时间。
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Adobe插件：getTimeParting

> [!IMPORTANT] 此插件由Adobe Consulting提供，旨在帮助您从Adobe Analytics中获得更多价值。 Adobe客户关怀部门不提供此插件的支持，包括安装或疑难解答。 如果您需要此插件的帮助，请与贵组织的客户经理联系。 他们可以安排与顾问的会议寻求帮助。

该插 `getTimeParting` 件允许您捕获网站上发生任何可衡量活动的详细时间。 当您希望按给定日期范围内的任何可重复时间划分指标时，此插件很有价值。 例如，您可以比较一周中两个不同天的转化率，如所有星期日与所有星期四。 您还可以比较一天中的时段，如所有早晨与所有晚上。

Analysis Workspace提供的开箱即用尺寸与此插件格式略有不同。 有关详 [细信息，请参阅](/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md) “分析用户指南”中的分时维度。 一些组织发现，Analysis Workspace的现成维度已足够。

> [重要] ：此插件的4.0+版与先前版本有显着不同。 Adobe强烈建议“从头开始”实施此插件。 引用4.0版之前的插件的代码与此插件的当前版本不兼容。

## 使用Adobe Experience Platform Launch扩展安装插件

Adobe提供了一个扩展，允许您使用最常用的插件。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 单击所需的属性。
1. 转到“扩 [!UICONTROL 展] ”选项卡，然后单击“目 [!UICONTROL 录] ”按钮
1. 安装和发布 [!UICONTROL Common Analytics插件扩展]
1. 对于要使用插件的任何启动规则，请添加一个具有以下配置的操作：
   * 扩展：常见分析插件
   * 操作类型：初始化addProductEvar
1. 保存更改并发布到规则

## 使用Launch自定义代码编辑器安装插件

如果您不想使用插件扩展，则可以使用自定义代码编辑器。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 单击所需的属性。
1. 转到“扩 [!UICONTROL 展] ”选项卡，然后单击Adobe Analytics扩 [!UICONTROL 展下的] “配置”按钮。
1. 使用自定 [!UICONTROL 义代码accordion展开“配置跟踪] ”，该面板显示“打 [!UICONTROL 开编辑器] ”按钮。
1. 打开自定义代码编辑器，并将下面提供的插件代码粘贴到编辑窗口中。
1. 保存更改并将其发布到Analytics扩展。

## 使用AppMeasurement安装插件

在实例化（使用）Analytics跟踪对象后，复制并粘贴AppMeasurement文件中的任意位置的以下代 `s_gi`码。 在您的实施中保留代码的注释和版本号可帮助Adobe解决任何潜在问题。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getTimeParting v6.2 */
var getTimeParting=function(a){a=document.documentMode?void 0:a||"Etc/GMT";a=(new Date).toLocaleDateString("en-US",{timeZone:a, minute:"numeric",hour:"numeric",weekday:"long",day:"numeric",year:"numeric",month:"long"});a=/([a-zA-Z]+).*?([a-zA-Z]+).*?([0-9]+).*?([0-9]+)(.*?)([0-9])(.*)/.exec(a);return"year="+a[4]+" | month="+a[2]+" | date="+a[3]+" | day="+a[1]+" | time="+(a[6]+a[7])};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用插件

该方 `getTimeParting` 法使用以下参数：

**`t`**（可选，但建议，字符串）:将访客的本地时间转换为的时区名称。  默认为UTC/GMT时间。 请参[阅维基百科上的TZ数据库时区列表](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)，以获取有效值的完整列表。

常见有效值包括：

* `"America/New_York"` for Eastern Time
* `"America/Chicago"` 对于Central Time
* `"America/Denver"` for Mountain Time
* `"America/Los_Angeles"` 对于太平洋时间

调用此方法将返回一个字符串，该字符串包含以管道(`|`)分隔的以下内容：

* 本年度
* 当月
* 当月的某天
* 一周中的某天
* 当前时间（上午／下午）

## 示例调用

### 特定时区示例

如果客户端位于法国巴黎，请使用以下示例代码：

```js
s.eVarX = getTimeParting("Europe/Paris");
```

如果客户端位于加利福尼亚州圣何塞：

```js
s.eVarX = getTimeParting("America/Los_Angeles");
```

如果客户在非洲国家加纳：

```js
s.eVarX = getTimeParting();
```

加纳在UTC/GMT时区内。  此示例说明，在这种情况下，不必使用插件参数。

### Internet explorer浏览器计费

如果要从Internet explorer访客中排除分时段数据，请使用以下示例（因为从IE浏览器返回的值只能在访客的本地时间内）

```js
if(!document.documentMode) s.eVarX = getTimeParting("America/New_York");
else s.eVarX = "Internet Explorer Visitors";
```

### 调用结果

如果科罗拉多州丹佛的访客在2020年8月31日上午9:15访问某网站，

正在运行以下代码……

```js
s.eVar10 = getTimeParting("Europe/Athens");
```

...将s.eVar10设置为等于“year=2020”|月=八月| date=31| day=星期五|时间=下午6:15&quot;

当以下代码……

```js
s.eVar10 = getTimeParting("America/Nome");
```

...将s.eVar10设置为等于“year=2020”|月=八月| date=31| day=星期五| time=6:15 AM&quot;

以下代码……

```js
s.eVar10 = getTimeParting("Asia/Calcutta");
```

...将s.eVar10设置为等于“year=2020”|月=八月| date=31| day=星期五|时间=晚上8:45”

下面的代码……

```js
s.eVar10 = getTimeParting("Australia/Sydney");
```

...将s.eVar10设置为等于“year=2020”|月=九月| date=1| day=星期六| time=1:15 AM&quot;

## 版本历史

### 6.2（2019年11月5日）

* 小错误修复
* 缩小了总体代码大小

### 6.1（2018年11月26日）

* 针对Internet explorer浏览器的修复。 他们可以返回时间，但只返回访客的当地时间。

### 6.0（2018年8月14日）

* 完全重写以符合国际标准。 现在可正确转换夏令时和所有时区。

### 5.0（2018年4月17日）

* 点发行（重新编译后，代码更小）
* 删除了对该参数的 `tpDST` 需求，因为现在自动检测夏令时开始／结束日期

### 4.0（2016年8月22日）

* 提供全新的解决方案，现在包括年份、月份和日期信息。
