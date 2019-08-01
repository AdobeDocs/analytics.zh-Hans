---
description: DFA 的 Genesis 集成可利用 DFA Floodlight 配置 ID (dfa_SPOTID)，以提高 DFA 和 Adobe 数据收集系统之间的报表一致性。
keywords: DFA
seo-description: DFA 的 Genesis 集成可利用 DFA Floodlight 配置 ID (dfa_SPOTID)，以提高 DFA 和 Adobe 数据收集系统之间的报表一致性。
seo-title: 更新网站的数据收集代码
solution: Analytics
title: 更新网站的数据收集代码
topic: Data connectors
uuid: a97d1b62-f883-48b1-9516-4f889 e701901
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# 更新网站的数据收集代码{#update-your-web-site-s-data-collection-code}

DFA 的 Genesis 集成可利用 DFA Floodlight 配置 ID (dfa_SPOTID)，以提高 DFA 和 Adobe 数据收集系统之间的报表一致性。

>[!NOTE]
>
>在最近发布的Google DFA中，术语Spotlight已更改为Floodlight。JavaScript 参数 `dfa_SPOTID` 基于 Spotlight 术语而命名，但它可同时用于两个版本。

要在您的网站上启用 DFA 集成，您必须通过添加以下内容来更新 JavaScript 数据收集代码：

* DFA 的集成模块
* 添加到收集代码的内容

## DFA 的集成模块 {#section-fa00e42a732a4e27a4ab3dfcfeae1a5b}

DFA 集成可利用 Adobe Marketing Cloud 集成模块，以向您的核心 JavaScript 数据收集代码 (`s_code.js`) 添加功能。The Integrate Module comes as part of the .zip file when you download the AppMeasurement for Javascript code from the [Code Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html). 仅当您需要查找其他帮助时，请与Adobe顾问联系。

Insert the Integrate Module code in the `Modules` section of your website's `s_code.js` file.

## 添加到收集代码的内容 {#section-8f98c727f1ba414fb8b4f02d696b8791}

基于您在集成向导中激活 DFA 集成时所做的选择，Data connectors 会为您的 JavaScript 数据收集代码生成自定义的添加内容，并通过电子邮件发送给您。将此代码插入 `s_code.js` 文件的主部分（不在 `doPlugins` 函数或任何其他函数中）。

以下显示的示例代码仅适用于插图；请使用您在完成 Data connectors 集成向导之后通过电子邮件收到的代码。

收集代码由以下组件组成：

* DFA 集成设置
* 需要集成的插件

**DFA 集成设置**

```
/************************** DFA VARIABLES **************************/ 
var dfaConfig = { 
   CSID:              "1234567", 
   SPOTID:            "29876543", 
   tEvar:             "eVar17", 
   errorEvar:         "eVar59", 
   timeoutEvent:      "event76", 
   requestURL:         "http://fls.doubleclick.net/ 
json?spot=[SPOTID]&src=[CSID]&var=[VAR]&host=integrate.112.2o7.net%2 
Fdfa_echo%3Fvar%3D[VAR]%26AQE%3D1%26A2S%3D1&ord=[RAND]", 
 
   maxDelay:          "1500", 
   visitCookie:       "s_dfa", 
   clickThroughParam: "CID", 
   searchCenterParam: "s_kwcid", 
   newRsidsProp:      undefined 
}; 
/************************ END DFA Variables ************************/ 
```

DFA 集成设置块可设置 DFA 集成所需要的变量。这其中每个变量的值来自以下来源：

**CSID**：客户端 ID。在您完成集成向导之后即由 DFA 生成。Data connectors 在此变量中预填充您的 DFA CS ID，并且在您完成集成向导后通过设置电子邮件向您发送此值。如果您的帐户中启用了高级广告服务，则不需要此变量。

**SPOTID**：Floodlight 配置（以前称为 Spotlight ID）。根据您在集成向导中指定的 DFA 帐户信息，Data connectors 在此变量中预填充您的 DFA Floodlight 配置 ID。

**tEvar**：转移变量。Data connectors 在此变量中预填充您在集成向导中为显示到达变量指定的 Analytics 变量名称。在没有与 Adobe 工程或工程服务部门密切协调的情况下，请不要更改此值。

**errorEvar**：错误变量。Data connectors 在此变量中预填充您在集成向导中为 DFA 查询失败变量指定的 Analytics 变量名称。

**timeoutEvent**：超时事件。Data connectors 在此变量中预填充您在集成向导中为超时事件变量指定的 Analytics 变量名称。

**requestURL**：用于查询广告信息的远程 DFA 主机。请不要更改此值，除非 Adobe 指示您这么做。

**maxDelay**：指定 JavaScript 数据收集代码等待来自 DFA Floodlight 服务器响应的时间量（以毫秒为单位）。Adobe 建议对此值进行试验，以找出基于您网站流量的最佳值。例如，提高此值通常会收集更多的 DFA 数据，但也会增加损失基本访客数据的风险（如果访客在延迟期间离开网站的话）。降低此值可减少损失点击数据的风险，但也会减少随 Adobe 点击数据一起发送的 DFA 数据量。

**visitCookie**：用于将 DFA 调用限制为每次访问调用一次的 Cookie 的名称。

**clickThroughParam**：一个查询字符串，通常包含在所有广告内，可通知集成模块刚刚发生了一次点击。如果查询字符串中存在此参数，则无论最近 30 分钟内是否已查询该访客，都可导致向 DFA Floodlight 服务器发出请求。

**newRsidsProp**：（可选）映射到未使用的流量属性变量。DFA 集成可在访问 Cookie 中收集并存储此值，以标识收集特定访客数据的报表包。此属性仅在通过 Adobe 工程服务进行自定义实施时需要用到。

**需要集成的插件**

所添加的收集代码加入了可改善 DFA 集成运行的额外插件：

* 将 DFA 查询限制为每次访问查询一次
* 使 Cookie 名称具有灵活性。尽管大部分组织都使用 s_dfa，但您可以对 DFA 集成使用任何有效的 Cookie 名称。
* 消除了不必要的重定向。由于显示到达数据是实时收集的，Adobe 收集服务器和 DFA 有可能交换每次页面查看的数据。在信息并非必要的情况下，插件可阻止这些数据交换。

>[!CAUTION]
>
>插件用于消除不必要的DFA查询的机制之一是基于域的访问cookie。当访客在一次受 DFA 影响的显示到达或点进后跨了多个域时，跨越多个域的集成报表包会夸大点进和显示到达数据。

