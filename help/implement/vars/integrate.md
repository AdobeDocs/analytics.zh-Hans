---
title: 集成模块
description: 借助集成模块，Adobe 合作伙伴可以将其数据收集工作与您的组织集成在一起。
feature: Variables
exl-id: 378ba77b-be81-49af-8f36-81c65bd01a53
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '883'
ht-degree: 98%

---

# 集成模块

借助集成模块，Adobe 合作伙伴可以将其数据收集工作与您的组织集成在一起。这种集成为双向数据连接提供了机会。通常情况下，集成模块的使用是由 Adobe 合作伙伴来驱动的。

>[!NOTE]
>
>在实施中请求合作伙伴数据可能会增加页面加载和发送到 Adobe 数据收集服务器的数据之间的延迟。如果访客在发送数据之前加载了新页面，则不会记录该页面。

## 集成模块工作流程

1. 站点的访客将加载一个页面，该页面会向合作伙伴发起 `get` 请求。
2. Adobe 合作伙伴接收 `get` 请求，并将相应的变量打包到 JSON 对象中。返回 JSON 对象。
3. 站点将接收 JSON 对象，并调用 `setVars` 以将 JSON 对象中包含的信息分配给 Adobe Analytics 变量。
4. 图像请求被发送到 Adobe 数据收集服务器。

## 集成模块实施

通过使用以下这些步骤，与 Adobe 合作伙伴合作的组织可以成功地开始使用集成模块。

### 获取集成模块代码

获取模块代码要求用户具有产品管理员访问权限或属于某个具有代码管理器访问权限的产品配置文件。对于包括 Adobe Experience Platform 中的标记在内的所有实施方法，获取模块代码的方法都是相同的。

1. 使用您的 Adobe ID 凭据登录 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。
1. 单击右上角的 9 个正方形图标，然后单击彩色的 Analytics 徽标。
1. 在顶部导航栏中，单击&#x200B;**[!UICONTROL 管理员]** > **[!UICONTROL 所有管理员]** > **[!UICONTROL 代码管理器]**。
1. 下载最新的 JavaScript AppMeasurement 库。
1. 下载后，解压缩文件并找到 `AppMeasurement_Module_Integrate.js`。

### 将集成模块放入实施中

在网站上实施集成模块需要访问Adobe Experience Platform数据收集。 如果使用旧版 JavaScript 实施，则需要具有访问贵组织网站源代码的权限。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 单击要编辑的标记属性。
1. 单击“扩展”选项卡，然后单击 Adobe Analytics 下的“配置”。
1. 打开“使用自定义代码配置跟踪器”折叠面板，然后单击“&lt;/> 打开编辑器”。
1. 将“集成模块”代码粘贴到代码模态窗口中。完成后，单击“保存”。

## 集成模块方法

实施集成模块后，请使用以下方法将其配置为从所需的 Adobe 合作伙伴发送和接收数据。

### add

`add` 方法可实例化某个合作伙伴对象，在合作伙伴系统和您的实施之间共享数据时，该对象将充当变量数据的中间存储。所有集成都需要使用此方法。如果在单个实施中使用多个合作伙伴，则必须为每个唯一的合作伙伴使用单独的合作伙伴对象。

```JavaScript
s.Integrate.add("<partner_name>");
```

贵组织通常会与 Adobe 合作伙伴一起确定合作伙伴名称的值。

### beacon

`beacon` 方法将创建一个图像请求，并将其指向指定的 URL。这些图像请求与标准图像请求不同。beacon 方法通常会将数据发送至 Adobe 合作伙伴，而不是 Adobe 数据收集服务器。

```JavaScript
p.beacon("<partner_url>/track?qs1=value1&qs2=value2");
```

贵组织通常会与 Adobe 合作伙伴一起确定合作伙伴名称的值。URL 中包含的查询字符串是可选的，具体取决于合作伙伴。集成模块自动包含一个查询字符串，其中包含一个可防止浏览器缓存的随机数。

### delay

Adobe 正在与团队开展内部合作，以将此方法记录在案。

### get

`get` 方法允许客户导入合作伙伴变量，并将这些变量存储在合作伙伴对象中。将数据存储在合作伙伴对象后，便可以将其分配到 Analytics 变量，并以图像请求的形式发送。此方法将调用指向包含所需数据的 JSON 对象的 URL。

```JavaScript
s.Integrate.<partner_name>.get("<url_to_json_object>?pid=value1&pid2=value2");
```

* **合作伙伴名称：**&#x200B;贵组织通常会与 Adobe 合作伙伴一起确定合作伙伴名称的值。
* **指向 JSON 对象的 URL：**&#x200B;指向 JSON 对象的 URL，该对象包含要合并到图像请求中的合作伙伴变量。
* **查询字符串参数：**&#x200B;可以在合作伙伴系统中标识贵组织的合作伙伴帐户信息。Adobe 合作伙伴将使用此信息来标识您的数据集。

集成模块会自动向 URL 添加更多的查询字符串。var 查询字符串可指定模块期望从合作伙伴返回的 JSON 对象的名称。其还会添加一个随机数以防止浏览器缓存。

### ready

Adobe 正在与团队开展内部合作，以将此方法记录在案。

### useVars

`useVars` 方法允许客户与 Adobe 合作伙伴共享变量值。

```JavaScript
s.Integrate.<partner_name>.useVars = function (s,p) {
    p.<partner_var1> = s.eVar1;
    p.<partner_var2> = s.eVar2;
}
```

贵组织通常会与 Adobe 合作伙伴一起确定合作伙伴名称的值以及合作伙伴使用的变量。

### setVars

`setVars` 方法允许客户使用检索到的合作伙伴数据填充 Analytics 变量。合作伙伴数据可以是 `get` 方法、静态分配或使用数据填充合作伙伴对象的任何其他机制的结果。

```JavaScript
s.Integrate.<partner_name>.setVars = function (s,p) {
    s.eVar1 = p.<partner_var1>;
    s.eVar2 = p.<partner_var2>;
}
```

贵组织通常会与 Adobe 合作伙伴一起确定合作伙伴名称的值以及合作伙伴使用的变量。

### script

`script` 方法允许 Adobe 合作伙伴在满足某些条件（例如，如果设置了促销活动变量）的情况下从合作伙伴网站调用其他 JavaScript。

```JavaScript
p.script("<partner_url>/script?qs1=value1&qs2=value2");
```

贵组织通常会与 Adobe 合作伙伴一起确定合作伙伴名称的值。URL 中包含的查询字符串是可选的，具体取决于合作伙伴。集成模块自动包含一个查询字符串，其中包含一个可防止浏览器缓存的随机数。
