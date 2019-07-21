---
title: 集成模块
seo-title: Adobe Analytics集成模块
description: 集成模块允许Adobe合作伙伴将其数据收集工作与您的组织集成。
seo-description: 集成模块允许Adobe合作伙伴将其数据收集工作与您的组织集成。
translation-type: tm+mt
source-git-commit: dae73042ace20eded9d0caf690a14203827f903a

---


# 集成模块

集成模块允许Adobe合作伙伴将其数据收集工作与您的组织集成。这种集成为双向数据连接提供了机会。通常，集成模块的使用由Adobe合作伙伴驱动。

> [!NOTE] 在实施中请求合作伙伴数据可增加页面加载和发送到Adobe数据收集服务器之间的延迟。如果访客在发送数据前加载新页面，则不会记录该页面。

## 集成模块工作流程

1. A visitor to your site loads a page that initiates a `get` request for partner data.
2. The Adobe partner receives the `get` request and packages the appropriate variables in a JSON object. 返回JSON对象。
3. Your site receives the JSON object and calls `setVars` to assign the information contained in the JSON object to Adobe Analytics variables
4. 图像请求被发送到 Adobe 数据收集服务器。

## 集成模块实施

与Adobe合作伙伴合作的组织可以使用这些步骤成功开始使用集成模块。

### 获取集成模块代码

获取模块代码需要具有产品管理员访问权限的用户，或者属于具有对代码管理器访问权限的产品配置文件。获取模块代码的方法与所有实施方法(包括Adobe Experience Platform Launch)相同。

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.
1. 单击右上角的方形图标，然后单击彩色的Analytics徽标。
1. In the top navigation, click [!UICONTROL Admin] &gt; [!UICONTROL Code Manager].
1. 下载最新的JavaScript AppMeasurement库。
1. Once downloaded, unzip the file and locate `AppMeasurement_Module_Integrate.js`.

### 将集成模块放入实施中

在您的站点上实施集成模块需要访问Adobe Experience Platform Launch。如果您使用传统的JavaScript实施，则需要访问单位的网站源代码。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your Adobe ID credentials.
2. 单击要编辑的启动项属性。
3. 单击“扩展”选项卡，然后单击Adobe Analytics下的“配置”。
4. 打开“使用自定义代码配置跟踪器”，然后单击“&lt;/&gt;打开编辑器”。
5. 将集成模块代码粘贴到代码模态窗口中。完成后单击保存。

## 集成模块方法

实施集成模块后，使用这些方法将其配置为从所需的Adobe合作伙伴发送和接收数据。

### add

`add` 该方法实例化合作伙伴对象，它在合作伙伴系统与您的实施之间共享数据时充当变量数据的中间存储。所有集成都需要此方法。如果在单个实施中使用了多个合作伙伴，则必须为每个唯一合作伙伴使用一个单独的合作伙伴对象。

```JavaScript
s.Integrate.add("<partner_name>");
```

您的组织通常与Adobe合作伙伴合作来确定合作伙伴名称的值。

### 信标

`beacon` 该方法创建一个图像请求并将其指向指定的URL。这些图像请求与标准图像请求不同。信标方法通常将数据发送给Adobe合作伙伴而不是Adobe数据收集服务器。

```JavaScript
p.beacon("<partner_url>/track?qs1=value1&qs2=value2");
```

您的组织通常与Adobe合作伙伴合作来确定合作伙伴名称的值。URL中包含的查询字符串是可选的，并且依赖于合作伙伴。集成模块自动包含一个包含随机数的查询字符串，以防止浏览器缓存。

### delay

Adobe正在与内部团队合作，以便记录此方法。

### get

`get` 该方法允许客户端导入合作伙伴变量并将其存储在合作伙伴对象中。数据在合作伙伴对象中后，可以将其分配给Analytics变量并在图像请求中发送。此方法调用一个URL，该URL指向包含所需数据的JSON对象。

```JavaScript
s.Integrate.<partner_name>.get("<url_to_json_object>?pid=value1&pid2=value2");
```

* **合作伙伴名称：** 您的组织通常与Adobe合作伙伴合作来确定合作伙伴名称的值。
* **JSON对象URL：** 指向JSON对象的URL，该对象包含要纳入图像请求的合作伙伴变量。
* **查询字符串参数：** 用于在合作伙伴系统中识别您的组织的合作伙伴帐户信息。Adobe合作伙伴使用此信息识别您的数据集。

集成模块自动向URL添加更多查询字符串。var查询字符串指定模块期望从合作伙伴返回的JSON对象名称。还增加了随机号码以防止浏览器缓存。

### ready

Adobe正在与内部团队合作，以便记录此方法。

### UseVars

The `useVars` method lets the client share variable values with an Adobe partner.

```JavaScript
s.Integrate.<partner_name>.useVars = function (s,p) {
    p.<partner_var1> = s.eVar1;
    p.<partner_var2> = s.eVar2;
}
```

您的组织通常与Adobe合作伙伴合作，以确定合作伙伴名称和合作伙伴使用的变量的值。

### SetVars

The `setVars` method lets the client populate Analytics variables using partner data retrieved. Partner data can be the result of a `get` method, a static assignment, or any other mechanism that populates the partner object with data.

```JavaScript
s.Integrate.<partner_name>.setVars = function (s,p) {
    s.eVar1 = p.<partner_var1>;
    s.eVar2 = p.<partner_var2>;
}
```

您的组织通常与Adobe合作伙伴合作，以确定合作伙伴名称和合作伙伴使用的变量的值。

### 脚本

`script` 该方法允许Adobe合作伙伴在满足某些条件(例如，如果已设置营销活动变量)时从合作伙伴站点调用额外的JavaScript。

```JavaScript
p.script("<partner_url>/script?qs1=value1&qs2=value2");
```

您的组织通常与Adobe合作伙伴合作来确定合作伙伴名称的值。URL中包含的查询字符串是可选的，并且依赖于合作伙伴。集成模块自动包含一个包含随机数的查询字符串，以防止浏览器缓存。
