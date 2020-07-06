---
title: 选择退出链接
description: 了解如何为网站的访客创建实施选择退出链接。
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 100%

---


# 实施选择退出链接

>[!IMPORTANT]
>
> Adobe 建议使用选择加入服务，尤其是需要遵从 GDPR 法规的组织。请参阅 Experience Cloud Identity Service 用户指南中的[选择加入服务概述](https://docs.adobe.com/content/help/zh-Hans/id-service/using/implementation/opt-in-service/optin-overview.html)。

某些访问您网站的访客不愿意将他们的浏览信息包含在您的数据集中。Adobe 让您能够向网站访客提供一种方案，禁止收集他们的信息。所有实施类型均适用；贵组织有责任遵守自己的隐私政策，同时也应遵守已签署的条款。

当访客访问选择退出 URL 时，系统会提示他们安装选择退出 Cookie。如果用户选择不被跟踪，并设置了选择退出 Cookie，则您的 JavaScript 文件将继续向 Adobe 服务器发送数据。但是，该数据不会进行处理或包含在报表中。

>[!TIP]
>
> Adobe 还根据每个报表包提供了相应的隐私设置。请参阅管理员用户指南中的[隐私设置](../../admin/admin/privacy-settings.md)。

## 选择退出 URL

贵组织的选择退出页面取决于实施中的 [`trackingServer`](../vars/config-vars/trackingserver.md) 变量值。

* 在 Adobe Experience Platform Launch 中：
   1. 登录到 [launch.adobe.com](https://launch.adobe.com)，然后单击所需的属性。
   2. 单击[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的[!UICONTROL 配置]。
   3. 单击[!UICONTROL 常规]折叠面板，并记下[!UICONTROL 跟踪服务器]值。

* 在 JavaScript 实施中：
   1. 在 Web 服务器上，在代码编辑器或文本编辑器中打开您网站上使用的 AppMeasurement.js 文件。
   2. 记下 `trackingServer` 变量值。

* 使用 [Adobe Experience Cloud 调试器](https://docs.adobe.com/content/help/zh-Hans/debugger/using/experience-cloud-debugger.html)：
   1. 使用 Chrome 浏览器导航到您的网站。
   2. 打开 Experience Cloud 调试器，然后转到[!UICONTROL 网络]选项卡。
   3. 记下[!UICONTROL 请求 URL - 主机名]值。

找到实施的 `trackingServer` 域后，将路径 `/optout.html` 附加到结尾处。例如：

* 第三方 Cookie：`https://example.sc.omtrdc.net/optout.html`
* 第一方 Cookie: `https://stats.example.com/optout.html`

## 选择退出查询字符串参数

有些设置您可以使用查询字符串自动加载到此页面上。

### 区域设置

通过包含 `locale` 查询字符串参数自动切换选择退出页面的语言。为此查询字符串参数分配以下任一值：

* en_US（英语，默认）
* bg_BG（保加利亚语）
* zh_CN（简体中文）
* zh_TW（繁体中文）
* cs_CZ（捷克语）
* da_NK（丹麦语）
* nl_NL（荷兰语）
* et_EE（爱沙尼亚语）
* fi_FI（芬兰语）
* fr_FR（法语）
* de_DE（德语）
* el_GR（希腊语）
* it_IT（意大利语）
* jp_JP（日语）
* ko_KR（韩语）
* lv_LV（拉脱维亚语）
* lt_LT（立陶宛语）
* nb_NO（挪威语）
* pl_PL（波兰语）
* pt_BR（葡萄牙语）
* sk_SK（斯洛伐克语）
* es_ES（西班牙语）

例如，`https://example.sc.omtrdc.net/optout.html?locale=ko_KR` 以韩语加载选择退出页面。

>[!TIP]
>
> `en_US` 查询字符串值不是必需的，因为默认情况下页面以英语加载。

### 弹出窗口

向页面添加“关闭窗口”按钮，从而使选择退出页面成为弹出窗口。使用 `popup` 查询字符串参数，并将其值设置为 `1`。

例如，`https://example.sc.omtrdc.net/optout.html?popup=1` 会加载具有“关闭窗口”按钮的选择退出页面。

>[!NOTE]
>
> 以前，此查询字符串参数会强制作为弹出窗口。但是，大多数现代浏览器都会控制向最终用户显示弹出窗口。

### 单击选择退出

允许用户立即选择退出跟踪。添加两个查询字符串参数 `opt_out` 和 `confirm_change`，为每个参数赋值 `1`。

例如，`https://example.sc.omtrdc.net/optout.html?opt_out=1&confirm_change=1` 会立即在访客页面上安装选择退出 Cookie。

### 单击选择加入

允许用户通过删除选择退出 Cookie 立即选择加入跟踪。添加两个查询字符串参数 `opt_in` 和 `confirm_change`，为每个参数赋值 `1`。

例如，`https://example.sc.omtrdc.net/optout.html?opt_in=1&confirm_change=1` 会立即删除访客的选择退出 Cookie。
