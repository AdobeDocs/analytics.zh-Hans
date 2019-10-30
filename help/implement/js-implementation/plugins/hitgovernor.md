---
description: s.hitGovernor 插件可跟踪在预定义的连续时间范围内发送的 Analytics 图像请求的总数量，如果总数超过了某个阈值，则此插件还可以根据需要执行其他逻辑。
seo-description: s.hitGovernor 插件可跟踪在预定义的连续时间范围内发送的 Analytics 图像请求的总数量，如果总数超过了某个阈值，则此插件还可以根据需要执行其他逻辑。
seo-title: hitGovernor
title: hitGovernor
uuid: d9091eae-005a-43c2-b419-980b795bc2a9
translation-type: ht
source-git-commit: 4d3fdf9d90afab9d899a93561105a589742d838e

---


# hitGovernor

s.hitGovernor 插件可跟踪在预定义的连续时间范围内发送的 Analytics 图像请求的总数量，如果总数超过了某个阈值，则此插件还可以根据需要执行其他逻辑。

虽然来自机器人、蜘蛛程序、特定用户代理或特定 IP 地址列表的流量都可以被识别为机器人流量（否则将不被计入报表），但是您的报告包中仍有可能会捕获不应计算的流量。例如，在不合理的一段时间（如大约每秒一个请求）内的大量点击或页面查看次数可能是重复的流量。

使用此插件可以在访客生命周期的剩余时间内自动阻止此类流量，并且还可以在报表中动态识别此类流量。

## hitGovernor 插件原理 {#section_541BC639E31442D09B1C85A2FFCDC02C}

每次将图像请求发送到跟踪服务器时，此插件即会增加 Cookie 值，并在连续时间范围内跟踪该值。默认时间范围为 1 分钟，但该时间范围可以被覆盖。（请参阅下面的[实施](../../../implement/js-implementation/plugins/hitgovernor.md#task_D4BDB524AA294C139AFCAE2B61FEA3F2)）。如果该时间范围内的点击总量超过了默认的点击量阈值 (60)，则会发送最终的自定义链接图像请求，以设置 *`exceptionFlag`* 上下文数据变量。默认的点击量阈值也可以被覆盖。

如有需要，从此刻起，可以在默认期限（60 天）内阻止系统收集该特定访客的流量。如果要阻止流量，需要在 doPlugins 函数中额外添加一行代码，如下所述。同样地，此时间期限也可以调整。对于此时间期限逻辑，可以将该访客的 IP 地址、用户代理或 [!DNL Experience Cloud] 访客 ID 包含在适当的永久异常逻辑中，或在 60 天过后重置此时间期限。如此一来，如果此流量在 60 天后被插件识别为欺诈，则该流量会再次被标记为异常，那么在接下来的 60 天内系统同样不会收集该流量。

## 报表 {#section_E742F19B528041808454744DB2C7007C}

无需设置任何默认变量或事件。但是，我们强烈建议您设置处理规则逻辑以相应地设置变量和事件。这些自定义变量和事件可能包括：

* [!DNL Experience Cloud] 访客 ID
* IP 地址
* 用户代理
* 已标记的异常事件

然后通过为这些变量创建区段，可以创建区段和虚拟报表包，以查看这些不明确的点击对站点所造成的整体影响。

我们建议您使用在报表中捕获到的值来更新机器人规则、DB VISTA 规则，或公司 IP 排除规则。

## 实施 {#task_D4BDB524AA294C139AFCAE2B61FEA3F2}

要实施 hitGovernor 插件，请执行以下操作：

1. 修改 AppMeasurement 库。

   要初始化此插件，请在 AppMeasurement 库代码的 `registerPostTrackCallback` 函数中插入此行代码（粗体部分）。

   >[!NOTE]
   >
   >虽然 `registerPostTrackCallback` 函数包含在 1.8.0 及以上版本的 AppMeasurement 库中，但默认情况下，此函数未包含在任何自定义代码配置中。将此函数插入在 doPlugins 函数的后面。**

   ```
    s.registerPostTrackCallback(function(){ 
    s.governor();
   }); 
   ```

   在 AppMeasurement 文件的 doPlugins 部分下方，插入[插件源代码](../../../implement/js-implementation/plugins/hitgovernor.md#reference_76423C81A7A342B2AC4BE41490B27DE0)中的插件代码。

   您可以通过在插件自身以外的位置设置点击量上限阈值、点击时间范围阈值和流量排除时间期限等变量来覆盖这三个变量，不过您最好使用其他配置变量来进行覆盖：

<table id="table_9959A40F5F0B40B39DB86E21D03E25FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 变量 </th> 
   <th colname="col2" class="entry"> 语法 </th> 
   <th colname="col3" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>点击量上限阈值 </p> </td> 
   <td colname="col2"> <p> <code> s.hl = 60; </code> </p> </td> 
   <td colname="col3"> <p>在给定的时间范围内不应超过的总点击量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>点击时间阈值 </p> </td> 
   <td colname="col2"> <p> <code> s.ht = 10; </code> </p> </td> 
   <td colname="col3"> <p>记录点击量的时间范围（以秒为单位）。此数值除以 6 可确定连续的时间段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>排除时间期限阈值 </p> </td> 
   <td colname="col2"> <p> <code> s.he = 60; </code> </p> </td> 
   <td colname="col3"> <p>为该访客设置排除 Cookie 的天数。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>您的实施可以使用与默认分析“s”对象不同的对象名称。如果是这样，请相应地更新对象名称。

1. 配置处理规则。

   此插件会将已标记的异常项作为上下文数据记录在链接跟踪图像请求中。因此，必须将处理规则配置为将已标记的异常分配到相应变量并进行跟踪（如下所示）。

   ![](assets/hitgov-config.png)

1. （可选）将流量阻止代码包含到 doPlugins 中。

   在流量被识别为异常后，通过在 `doPlugins` 函数中插入此代码，可以完全阻止该访客随后发起的任何点击。

   ```
   //Check for hit governor flag 
         if(s.Util.cookieRead('s_hg')==9)s.abort=true;
   ```

   如果不包含此代码，来自该访客的流量将只会被标记，而不会被阻止。

## 插件源代码 {#reference_76423C81A7A342B2AC4BE41490B27DE0}

此代码应该添加在 AppMeasurement 库 doPlugins 部分的下方。

```
//Hit Governor (Version 0.1 BETA, 11-13-17) 
s.governor=new Function("","" 
+"var s=this;if(typeof s.hl=='undefined'){s.hl=60;}if(typeof s.ht=='u" 
+"ndefined'){s.ht=60;}if(typeof s.he=='undefined'){s.he=60;}if(s.Util" 
+".cookieRead('s_hg')==8){var i=new Date(),y=i.getFullYear(),m=i.getM" 
+"onth(),d=i.getDate(),i=new Date(y,m,d+s.he);s.Util.cookieWrite('s_h" 
+"g',9,i);return;}var f=s.Util.cookieRead('s_hc'),g=Number(s.Util.coo" 
+"kieRead('s_ht')),h=Math.floor((new Date()).getTime()),ha=f!=''?f.sp" 
+"lit('|').map(Number):[0,0,0,0,0],i=ha.reduce(function(ha,b){return " 
+"ha+b;},0),j=g==0?0:Math.floor(((h-g)/(s.ht/6))/1000);if(g==0)s.Util" 
+".cookieWrite('s_ht',h);if(i<s.hl){if(j>=1){if(j>=6){ha=[0,0,0,0,0];" 
+"}else{for(var k=0;k<j;k++){ha.unshift(0);ha.pop();}}s.Util.cookieWr" 
+"ite('s_ht',h);}}else{s.Util.cookieWrite('s_hg',8);s.linkTrackVars+=" 
+"',contextData.exceptionFlag';s.contextData['exceptionFlag']='true';" 
+"s.tl(this,'o','exceptionFlag');}ha[0]++;s.Util.cookieWrite('s_hc',h" 
+"a.join('|'));"); 
```

