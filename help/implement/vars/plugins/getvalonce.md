---
title: getValOnce
description: 防止将Analytics变量设置为一行中的相同值两次。
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Adobe插件：getValOnce

> [!IMPORTANT] 此插件由Adobe Consulting提供，旨在帮助您从Adobe Analytics中获得更多价值。 Adobe客户关怀部门不提供此插件的支持，包括安装或疑难解答。 如果您需要此插件的帮助，请与贵组织的客户经理联系。 他们可以安排与顾问的会议寻求帮助。

插 `getValOnce` 件可防止将变量设置为等于同一值多次。 当您希望删除访客刷新页面或以其他方式多次访问给定页面的重复出现时，Adobe建议使用此插件。 如果您不担心Analysis Workspace中的“发生次数”量度，则不必使用此插件。

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
/* Adobe Consulting Plugin: getValOnce v2.0 */
s.getValOnce=function(vtc,cn,et,ep){if(vtc&&(cn=cn||"s_gvo",et=et||0,ep="m"===ep?6E4:864E5,vtc!==this.c_r(cn))){var e=new Date;e.setTime(e.getTime()+et*ep);this.c_w(cn,vtc,0===et?0:ep);return vtc}return""};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用插件

该方 `getValOnce` 法使用以下参数：

* **`vtc`**（必需，字符串）:要检查并查看它之前是否设置为相同值的变量
* **`cn`**（可选，字符串）:包含要检查的值的Cookie的名称。 默认值为`"s_gvo"`
* **`et`**（可选，整数）:cookie的到期时间(以天为单位，或以分钟为单位，具体取决于`ep`参数)。 默认为`0`，浏览器会话结束时过期
* **`ep`**（可选，字符串）:仅当参数也被设置时`et`才设置此参数。 如果希望该参`"m"`数在数分钟(而`et`不是数天)后过期，请将此参数设置为。 默认为`"d"`，以天为单位`et`设置参数。

如果参 `vtc` 数与cookie值匹配，则此方法返回空字符串。 如果参 `vtc` 数与cookie值不匹配，则该方法将参数作为 `vtc` 字符串返回。

## 示例调用

### 示例#1

使用此调用可防止在接下来30天内连续多次将相同值传入s.campaign:

```js
s.campaign=s.getValOnce(s.campaign,"s_campaign",30);
```

在上述调用中，插件将首先比较s_campaign cookie中已包含的值与当前s.campaign变量中的值。   如果未匹配，插件会将s_campaign cookie设置为与s.campaign中的新值相等，然后返回新值。   这种比较将在接下来的30天内进行

### 示例#2

使用此调用可防止在整个会话中设置相同的值：

```js
s.eVar2=s.getValOnce(s.eVar2,"s_ev2",0,"m");
```

此代码可防止同一值在用户整个会话中连续多次传入s.eVar2。  由于到期时间设置为等于0，因此它还会忽略参数中的“m”值（在呼叫结束时）。   该代码还将比较值存储在s_ev2 cookie中。

## 版本历史

### 2.0

* 点发行版（重新编译后，代码尺寸更小）。

### 1.1

* 添加了通过参数选择到期时间的分钟数或天 `t` 数。
* 更正了用于 `k` 仅限插件的变量的范围。 此更改可防止页面上其他代码的可能干扰。
