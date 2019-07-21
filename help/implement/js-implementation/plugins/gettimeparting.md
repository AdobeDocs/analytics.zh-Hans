---
description: getTimeParting 插件可使用小时、星期、周末和工作日等值填充自定义变量。Analysis Workspace 提供了一些现成的“时间区分”维度。如果除 Analysis Workspace 之外，其他 Analytics 解决方案中也需要使用时间区分维度，则应该使用此插件。
keywords: Analytics 实施
seo-description: getTimeParting 插件可使用小时、星期、周末和工作日等值填充自定义变量。Analysis Workspace 提供了一些现成的“时间区分”维度。如果除 Analysis Workspace 之外，其他 Analytics 解决方案中也需要使用时间区分维度，则应该使用此插件。
seo-title: getTimeParting
solution: Analytics
subtopic: 插件
title: getTimeParting
topic: 开发人员和实施
uuid: 74f696a3-7169-4560-89b2-478b3d8385e1
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getTimeParting

getTimeParting 插件可使用小时、星期、周末和工作日等值填充自定义变量。Analysis Workspace 提供了一些现成的“时间区分”维度。The plug-in should be used if time parting dimensions are needed in other Analytics solutions, outside of [!UICONTROL Analysis Workspace].

该插件可捕获用户 Web 浏览器中提供的日期和时间信息。它可从此信息中获取具体的小时和星期。然后将此数据转化为您所选的时区。该插件还支持夏令时。

>[!NOTE]
>
>以下说明要求您更改站点上的数据收集代码。此操作会影响您网站上的数据收集，且只应由具有使用和实施 [!DNL Analytics] 经验的开发人员完成。

## 插件代码 {#section_1390D6FA53BE4C40B748B0C0AE09C4FA}

**配置区域**

将以下代码置于标记为[!DNL s_code.js]配置区域[!UICONTROL 的 ] 文件区域中，并按照以下描述进行必要的更新。

`s._tpDST` - 一组DST值。The array is structured in the following format: `YYYY:'MM/DD,MM/DD'`

```js
//time parting configuration 
//Australia 
s._tpDST = { 
2012:'4/1,10/7', 
2013:'4/7,10/6', 
2014:'4/6,10/5', 
2015:'4/5,10/4', 
2016:'4/3,10/2', 
2017:'4/2,10/1', 
2018:'4/1,10/7', 
2019:'4/7,10/6'} 
  
//US 
s._tpDST = { 
2012:'3/11,11/4', 
2013:'3/10,11/3', 
2014:'3/9,11/2', 
2015:'3/8,11/1', 
2016:'3/13,11/6', 
2017:'3/12,11/5', 
2018:'3/11,11/4', 
2019:'3/10,11/3'} 
  
//Europe 
s._tpDST = { 
2012:'3/25,10/28', 
2013:'3/31,10/27', 
2014:'3/30,10/26', 
2015:'3/29,10/25', 
2016:'3/27,10/30', 
2017:'3/26,10/29', 
2018:'3/25,10/28', 
2019:'3/31,10/27'}
```

针对北半球客户的注意事项：在该数组中，DST 值为 DST 开始日期，DST 结束日期。

针对南半球客户的注意事项：在该数组中，DST 值为 DST 结束日期，DST 开始日期。

**参数**

```js
var tp = s.getTimeParting(h,z);
```

* h =（必需）半球 - 指定要将时间转换为哪个半球。值为“n”或“s”。该参数用于确定如何使用传递的 DST 数组。如果传递“n”，则该插件使用 DST 开始日期。如果传递“s”，则该插件使用 DST 结束日期。
* z =（可选）时区 - 如果您希望数据基于特定的时段，则需要在此处将该参数指定为与 GTM 相差的小时数。请注意，该参数在非 DST 期间应为 GMT。如果未指定任何值，则默认设置为 GMT（例如，对于美国东部时间，应指定“-5”）

**返回结果**

返回分钟级时间与星期的串联值，例如：

```
8:03 AM|Monday
```

然后，可以使用[分类](https://marketing.adobe.com/resources/help/en_US/reference/classifications.html)将访问分组到时段中。例如，可以在分类规则生成器中设置一个规则，将上午 9:00 到上午 9:59 之间的访问存储到“9:00 AM - 10:00 AM”中。作为分类的替代方案，您可以在 JavaScript 中提供其他客户端逻辑来存储访问。

**示例调用**

```js
var tp = s.getTimeParting('n','-7'); 
s.prop1 = tp;
```

**插件区域**

将以下代码添加到 [!UICONTROL  文件中的 ]PLUGINS SECTION[!DNL s_code.js]（插件区域）。

```js
/* 
 * Plugin: getTimeParting 3.4 
 */ 
s.getTimeParting=new Function("h","z","" 
+"var s=this,od;od=new Date('1/1/2000');if(od.getDay()!=6||od.getMont" 
+"h()!=0){return'Data Not Available';}else{var H,M,D,U,ds,de,tm,da=['" 
+"Sunday','Monday','Tuesday','Wednesday','Thursday','Friday','Saturda" 
+"y'],d=new Date();z=z?z:0;z=parseFloat(z);if(s._tpDST){var dso=s._tp" 
+"DST[d.getFullYear()].split(/,/);ds=new Date(dso[0]+'/'+d.getFullYea" 
+"r());de=new Date(dso[1]+'/'+d.getFullYear());if(h=='n'&&d>ds&&d<de)" 
+"{z=z+1;}else if(h=='s'&&(d>de||d<ds)){z=z+1;}}d=d.getTime()+(d.getT" 
+"imezoneOffset()*60000);d=new Date(d+(3600000*z));H=d.getHours();M=d" 
+".getMinutes();M=(M<10)?'0'+M:M;D=d.getDay();U=' AM';if(H>=12){U=' P" 
+"M';H=H-12;}if(H==0){H=12;}D=da[D];tm=H+':'+M+U;return(tm+'|'+D);}");
```

**注意**

* 在部署到生产之前，请务必对插件安装进行测试，以确保可按预期进行数据收集。
* 必须为插件设置配置变量，插件才能正常工作。

