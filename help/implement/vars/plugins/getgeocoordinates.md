---
title: getGeoCoordinates
description: 跟踪访客的geoLocation。
translation-type: tm+mt
source-git-commit: e08f3e168a779f9678a109d7f533761629cd38f3

---


# Adobe插件：getGeoCoordinates

> [!IMPORTANT] 此插件由Adobe Consulting提供，旨在帮助您从Adobe Analytics的使用中获得更多价值。 Adobe客户关怀部门不提供此插件的支持，包括安装或疑难解答。 如果您需要此插件的帮助，请与贵组织的客户经理联系。 他们可以安排与顾问的会议寻求帮助。

该 `getGeoCoordinates` 插件允许您捕获访客设备的经度和纬度。 如果您希望在Analytics变量中捕获地理位置数据，Adobe建议使用此插件。

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
/* Adobe Consulting Plugin: getGeoCoordinates v1.0 */
s.getGeoCoordinates=function(){var d=this,b="",a=d.c_r("s_ggc").split("|"),e={timeout:5E3,maximumAge:0},f=function(c){c=c.coords;var a=new Date;a.setTime(a.getTime()+18E5);d.c_w("s_ggc",parseFloat(c.latitude.toFixed(4))+"|"+parseFloat(c.longitude.toFixed(4)),a); b="latitude="+parseFloat(c.latitude.toFixed(4))+" | longitude="+parseFloat(c.longitude.toFixed(4))},g=function(a){b="error retrieving geo coordinates"};1<a.length&&(b="latitude="+a[0]+" | longitude="+a[1]);navigator.geolocation&& navigator.geolocation.getCurrentPosition(f,g,e);""===b&&(b="geo coordinates not available");return b};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用插件

该方 `getGeoCoordinates` 法不使用任何参数。 它返回以下值之一：

* `"geo coordinates not available"`:对于在插件运行时没有可用地理位置数据的设备。 此值在首次访问点击时很常见，尤其是当访客首次需要同意跟踪其位置时。
* `"error retrieving geo coordinates"`:当插件尝试检索设备位置时遇到任何错误
* `"latitude=[LATITUDE] | longtitude=[LONGITUDE]"`:其中 [LATITUDE]/[LONGITUDE] （经纬度）分别是经纬度

> [!NOTE] 坐标值四舍五入到最接近的四进制。 例如，舍入值 `"40.438635333"` 以限制要 `"40.4386"` 捕获的唯一值的数量。 这些值足够接近，能够准确定位设备在约20英尺内的准确位置。

该插件使用名为cookie的Cookie，以在必 `"s_ggc"` 要时存储点击之间的坐标。

## 示例调用

### 示例#1

以下代码……

```js
s.eVar1 = s.getGeoCoordinates();
```

...根据访客的设备状态，将eVar1设置为等于上述返回值之一

### 示例#2

以下代码将纬度和经度提取到它们自己的变量（称为finalLatitude和finalLongitude）中，以用于其他代码／应用程序

```js
var coordinates = s.getGeoCoordinates();
if(coordinates.indexOf("latitude") > -1)
{
  var finalLatitude = Number(coordinates.split("|")[0].trim().split("=")[1]),
  finalLongitude = Number(coordinates.split("|")[1].trim().split("=")[1]);
}
```

从那里，您可以确定访客是否在自由女神像处：

```js
if(finalLatitude >= 40.6891 && finalLatitude <= 40.6893 && finalLongtude >= -74.0446 && finalLongitude <= -74.0444)
  var visitorAtStatueOfLiberty = true;
else
  var visitorAtStatueOfLiberty = false;
```

## 版本历史

### 1.0（2015年5月25日）

* 第一版。
