---
title: getNewRepeat
description: 跟踪新访客与回访访客的活动。
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '819'
ht-degree: 100%

---


# Adobe 插件：getNewRepeat

>[!IMPORTANT]
>
>此插件由 Adobe Consulting 团队提供，旨在帮助您从 Adobe Analytics 中获取更多的价值。Adobe 客户关怀团队不提供对此插件的支持，包括安装或疑难解答。如果您需要关于此插件的帮助，请与贵组织的帐户管理员联系。他们可以为您安排与顾问的答疑会，以便您向顾问寻求帮助。

`getNewRepeat` 插件允许您确定网站访客是新访客还是所需天数内的回访访客。如果您想要使用自定义天数将访客识别为“新”访客，Adobe 建议使用此插件。如果 Analysis Workspace 中的新访客/回访访客维度满足贵组织的需求，则无需使用此插件。

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
   * 操作类型：初始化 getNewRepeat
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
/* Adobe Consulting Plugin: getNewRepeat v2.1 */
s.getNewRepeat=function(d){d=d?d:30;var s=this,p="s_nr"+d,b=new Date,e=s.c_r(p),f=e.split("-"),c=b.getTime();b.setTime(c+864E5*d); if(""===e||18E4>c-f[0]&&"New"===f[1])return s.c_w(p,c+"-New",b),"New";s.c_w(p,c+"-Repeat",b);return"Repeat"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用此插件

`getNewRepeat` 方法使用以下参数：

* **`d`**（整数，可选）：将访客重置回 `"New"` 的两次访问之间所需的最小天数。如果未设置此参数，则默认为 30 天。

如果插件设置的 Cookie 不存在或已过期，则此方法将返回值 `"New"`。如果插件设置的 Cookie 存在，并且自当前点击以来的时间以及 Cookie 中设置的时间大于 30 分钟，则它将返回值 `"Repeat"`。在整个访问期间，此方法将返回相同的值。

该插件使用名为 `"s_nr[LENGTH]"` 的 Cookie，其中 `[LENGTH]` 等于 `d` 参数。Cookie 包含一个 Unix 时间戳，该时间戳表示访客的当前时间和当前状态（`"New"` 或 `"Repeat"`）。

## 示例调用

### 示例 1

以下代码会将新访客的 s.eVar1 的值设置为等于“New”，并在访客访问网站的剩余时间内继续将 s.eVar1 的值设置为等于“New”（通过每次新调用）。

```js
s.eVar1=s.getNewRepeat();
```

### 示例 2

如果访客自上次调用 s.getNewRepeat() 以来在 31 分钟到 30 天内的任何时间返回网站，则以下代码会将 s.eVar1 的值设置为等于“Repeat”，并在访客访问网站的剩余时间中继续将 s.eVar1 的值设置为等于“Repeat”（通过每次新调用）。

```js
s.eVar1=s.getNewRepeat();
```

### 示例 3

如果访客自上次调用 s.getNewRepeat() 以来至少有 30 天未返回网站，则以下代码会将 s.eVar1 的值设置为“New”，并在访客访问网站的剩余时间中继续将 s.eVar1 的值设置为等于“New”（通过每次新调用）。

```js
s.eVar1=s.getNewRepeat();
```

### 示例 4

如果访客自上次调用 s.getNewRepeat() 以来在 31 分钟到 365 天（即 1 年）内的任何时间返回网站，则以下代码将 s.eVar1 的值设置为等于“Repeat”，并在访客访问网站的剩余时间中继续将 s.eVar1 的值设置为等于“Repeat”（通过每次新调用）。

```js
s.eVar1=s.getNewRepeat(365);
```

### 示例 5

如果访客自上次调用 s.getNewRepeat() 以来至少有 365 天（即 1 年）未返回网站，则以下代码会将 s.eVar1 的值设置为等于“New”，并在访客访问网站的剩余时间中继续将 s.eVar1 的值设置为等于“New”（通过每次新调用）。

```js
s.eVar1=s.getNewRepeat(365);
```

## 版本历史记录

### 2.1（2019 年 9 月 30 日）

* 重新整理了 JavaScript 逻辑以减小插件大小

### 2.0（2018 年 4 月 16 日）

* 使用较小的代码大小重新编译
* 删除了命名 Cookie 以存储访问信息的功能。该插件现在会根据传递到 `d` 参数的值动态命名 Cookie。
