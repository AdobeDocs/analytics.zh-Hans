---
title: 退出链接
description: 了解如何为网站的访客创建实施退出链接。
translation-type: tm+mt
source-git-commit: 664d0cde8b8b17c86b47858611d459026aab0bef

---


# 实施退出链接

> [!IMPORTANT] Adobe建议使用选择加入服务，尤其是针对符合GDPR规定的组织。 See [Opt-in service overview](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html) in the Experience Cloud Identity Service user guide.

某些访问您网站的访客不愿意将他们的浏览信息包含在您的数据集中。 Adobe能够为网站的访客提供一种选择退出所收集信息的方式。 满足所有实施类型；贵组织有责任遵守您自己的隐私政策并遵守您的已签署条款。

当访客到达退出URL时，系统会提示他们安装退出Cookie。 如果用户选择不跟踪，并设置了退出Cookie，则您的JavaScript文件将继续向Adobe服务器发送数据。 但是，该数据不会被处理或包含在报告中。

> [!TIP] Adobe还针对每个报告包提供隐私设置。 请参 [阅管理员用户指南](../../admin/admin/privacy-settings.md) 中的隐私设置。

## 退出URL

贵组织的退出页面取决于实施中 [`trackingServer`](../vars/config-vars/trackingserver.md) 的变量值。

* 在Adobe Experience Platform Launch中：
   1. 登录到 [launch.adobe.com](https://launch.adobe.com) ，然后单击所需的属性。
   2. Click the [!UICONTROL Extensions] tab, then click [!UICONTROL Configure] under Adobe Analytics.
   3. 单击“ [!UICONTROL 常规] ”折叠面板，并记下“跟 [!UICONTROL 踪服务器] ”值。

* 在JavaScript实现中：
   1. 在Web服务器上，在代码或文本编辑器中打开您站点上使用的AppMeasurement.js文件。
   2. 请注意 `trackingServer` 变量值。

* Using the [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html):
   1. 使用Chrome浏览器导航到您的站点。
   2. 打开Experience Cloud调试器，然后转到“网络” [!UICONTROL 选项卡]。
   3. 请注意 [!UICONTROL 请求URL —— 主机名] 值。

找到实施的域后， `trackingServer` 将路径追加到 `/optout.html` 结束处。 例如：

* 第三方Cookie: `https://example.sc.omtrdc.net/optout.html`
* 第一方 Cookie: `https://stats.example.com/optout.html`

## 退出查询字符串参数

您可以使用查询字符串自动加载到此页面上的设置。

### 区域设置

通过包括查询字符串参数自动切换退出页面 `locale` 的语言。 将此查询字符串参数指定为以下值之一：

* zh_CN（英语，默认）
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

例如， `https://example.sc.omtrdc.net/optout.html?locale=ko_KR` 以韩语加载退出页面。

> [!TIP] 查询 `en_US` 字符串值不是必需的，因为默认情况下页面以英语加载。

### 弹出窗口

向页面添加“关闭窗口”按钮，允许潜在用户将退出页面作为弹出窗口。 使用查 `popup` 询字符串参数，并为其赋值 `1`。

例如，加 `https://example.sc.omtrdc.net/optout.html?popup=1` 载带“关闭窗口”按钮的退出页面。

> [!NOTE] 历史上，此查询字符串参数强制弹出窗口。 但是，大多数现代浏览器都可以控制最终用户的弹出窗口。

### 单击退出

允许用户立即退出跟踪。 添加两个查询字符串参 `opt_out` 数和 `confirm_change`，为每个参数赋值 `1`。

例如， `https://example.sc.omtrdc.net/optout.html?opt_out=1&confirm_change=1` 会立即在访客页面上安装退出Cookie。

### 单击选择加入

允许用户通过删除退出Cookie立即选择退回跟踪。 添加两个查询字符串参 `opt_in` 数和 `confirm_change`，为每个参数赋值 `1`。

例如， `https://example.sc.omtrdc.net/optout.html?opt_in=1&confirm_change=1` 立即删除访客的退出Cookie。
