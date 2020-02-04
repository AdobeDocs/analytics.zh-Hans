---
title: getNewRepeat
description: 跟踪新访客与重复访客的活动。
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Adobe插件：getNewRepeat

> [!IMPORTANT] 此插件由Adobe Consulting提供，旨在帮助您从Adobe Analytics中获得更多价值。 Adobe客户关怀部门不提供此插件的支持，包括安装或疑难解答。 如果您需要此插件的帮助，请与贵组织的客户经理联系。 他们可以安排与顾问的会议寻求帮助。

该插 `getNewRepeat` 件允许您确定网站访客是新访客还是在所需天数内的重复访客。 如果您希望使用自定义天数将访客识别为“新”访客，Adobe建议使用此插件。 如果Analysis Workspace中的新访客／重复访客维度满足您组织的需求，则无需使用此插件。

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
/* Adobe Consulting Plugin: getNewRepeat v2.1 */
s.getNewRepeat=function(d){d=d?d:30;var s=this,p="s_nr"+d,b=new Date,e=s.c_r(p),f=e.split("-"),c=b.getTime();b.setTime(c+864E5*d); if(""===e||18E4>c-f[0]&&"New"===f[1])return s.c_w(p,c+"-New",b),"New";s.c_w(p,c+"-Repeat",b);return"Repeat"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用插件

该方 `getNewRepeat` 法使用以下参数：

* **`d`**（integer，可选）:将访客重置回访的访问之间所需的最少天数`"New"`。 如果未设置此参数，则默认为30天。

如果插件设置的 `"New"` Cookie不存在或已过期，则此方法返回的值。 如果插件设置的 `"Repeat"` cookie存在，则返回的值，且自当前点击和cookie中设置的时间大于30分钟以来的时间。 此方法为整个访问返回相同的值。

此插件使用名为where的cookie, `"s_nr[LENGTH]"` 该 `[LENGTH]` cookie等于参 `d` 数。 Cookie包含表示访客（或）的当前时间和当前状态的Unix`"New"` 时间 `"Repeat"`戳。

## 示例调用

### 示例#1

以下代码将新访客的s.eVar1设置为“New”值，并在访客访问网站的剩余时间内继续将s.eVar1设置为“New”值（每次新调用）。

```js
s.eVar1=s.getNewRepeat();
```

### 示例#2

如果访客自上次调用s.getNewRepeat()以来在31分钟到30天内随时返回网站，则以下代码将s.eVar1设置为“Repeat”值，并在访客访问网站的剩余时间中继续将s.eVar1设置为“Repeat”值（每次新调用）。

```js
s.eVar1=s.getNewRepeat();
```

### 示例#3

如果访客自上次调用s.getNewRepeat()起至少30天未访问过网站，则以下代码将s.eVar1设置为“New”值，并在访客访问网站的剩余时间内继续将s.eVar1设置为“New”值（每次新调用）。

```js
s.eVar1=s.getNewRepeat();
```

### 示例#4

如果访客自上次调用s.getNewRepeat()以来在31分钟到365天（即1年）内回访网站，则以下代码将s.eVar1设置为“Repeat”的值，并将s.eVar1设置为“Repeat”的值（每次新调用），并在剩余时间内继续将s.eVar1设置为“Repeat”的值访客对网站的访问。

```js
s.eVar1=s.getNewRepeat(365);
```

### 示例#5

如果访客自上次调用s.getNewRepeat()以来至少365天（即1年）未访问过网站，则以下代码将s.eVar1设置为“New”值，并将s.eVar1设置为“New”值（每次新调用），在剩余时间内，始终将s.eVar1设置为“New”值访问网站。

```js
s.eVar1=s.getNewRepeat(365);
```

## 版本历史

### 2.1（2019年9月30日）

* 重排JavaScript逻辑以减小插件大小

### 2.0（2018年4月16日）

* 使用较小的代码大小重新编译
* 删除了命名cookie以存储访问信息的功能。 该插件现在根据传递到参数的值动态命名 `d` cookie。
