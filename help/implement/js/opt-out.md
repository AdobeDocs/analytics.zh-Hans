---
title: 选择退出链接
description: 了解如何为网站的访客创建实施选择退出链接。
feature: Implementation Basics
exl-id: 08b8c7cc-28c6-45e3-ab44-77471eea8ef1
hide: true
hidefromtoc: true
role: Developer
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 67%

---

# 实施选择退出链接

>[!IMPORTANT]
>
> 本文为（计划）在其网站上实施Adobe Analytics **的** Adobe Analytics客户提供了有关如何为网站用户提供选择退出链接的说明。 <p><p>
<p>-ERR:REF-NOT-FOUND-<p>-ERR:REF-NOT-FOUND-> 如果您&#x200B;**正在访问已实施Adobe Analytics**&#x200B;的网站，并且希望选择退出，则&#x200B;**<span style="color:red">本文不适合您</span>**。 请参阅[Adobe隐私选择](https://www.adobe.com/cn/privacy/opt-out.html)以控制Adobe如何使用您的信息。

某些访问您网站的访客不愿意将他们的浏览信息包含在您的数据集中。Adobe让您能够向网站访客提供一种方法，禁止对其信息进行分析。

通过选择退出链接，您可以允许网站的访客在Analytics报表中忽略其数据。 这些链接仅限于AppMeasurement实施；Adobe建议改用[Adobe Experience Cloud选择加入服务](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=zh-Hans)。 选择加入服务更加稳健，可跨多个Adobe Experience Cloud产品(包括Adobe Analytics和AppMeasurement)使用。

当访客访问选择退出 URL 时，系统会提示他们安装选择退出 Cookie。如果用户选择不被跟踪，并设置了选择退出Cookie，则AppMeasurement将继续向Adobe发送数据。 但是，该数据不会进行处理或包含在报表中。

>[!TIP]
>
>Adobe 还根据每个报表包提供了相应的隐私设置。请参阅《管理员用户指南》中的[隐私设置](/help/admin/tools/manage-rs/edit-settings/general/privacy-settings.md)。

## 选择退出 URL

贵组织的选择退出页面取决于实施中的 [`trackingServer`](../vars/config-vars/trackingserver.md) 变量值。

* 在Analytics扩展中：
   1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
   1. 单击所需的标记属性。
   1. 单击[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的[!UICONTROL 配置]。
   1. 单击[!UICONTROL 常规]折叠面板，并记下[!UICONTROL 跟踪服务器]值。

* 在 JavaScript 实施中：
   1. 在 Web 服务器上，在代码编辑器或文本编辑器中打开您网站上使用的 AppMeasurement.js 文件。
   1. 记下 `trackingServer` 变量值。

* 使用 [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/experience-platform/debugger/home.html)：
   1. 使用 Chrome 浏览器导航到您的网站。
   1. 打开 Experience Cloud Debugger，然后转到[!UICONTROL 网络]选项卡。
   1. 记下[!UICONTROL 请求 URL - 主机名]值。

找到实施的 `trackingServer` 域后，将路径 `/optout.html` 附加到结尾处。例如：

* 第三方 Cookie：`https://example.data.adobedc.net/optout.html`
* 第一方 Cookie: `https://stats.example.com/optout.html`

## 选择退出查询字符串参数

有些设置您可以使用查询字符串自动加载到此页面上。

### 区域设置

通过包含 `locale` 查询字符串参数自动切换选择退出页面的语言。为此查询字符串参数分配以下任一值：

* `en_US` （英语，默认）
* `bg_BG` （保加利亚语）
* `zh_CN` （简体中文）
* `zh_TW` （繁体中文）
* `cs_CZ` （捷克语）
* `da_NK` （丹麦语）
* `nl_NL` （荷兰语）
* `et_EE` （爱沙尼亚语）
* `fi_FI` （芬兰语）
* `fr_FR` （法语）
* `de_DE` （德语）
* `el_GR` （希腊语）
* `it_IT` （意大利语）
* `jp_JP` （日语）
* `ko_KR` （韩语）
* `lv_LV` （拉脱维亚语）
* `lt_LT` （立陶宛语）
* `nb_NO` （挪威语）
* `pl_PL` （波兰语）
* `pt_BR` （葡萄牙语）
* `sk_SK` （斯洛伐克语）
* `es_ES` （西班牙语）

例如，`https://example.data.adobedc.net/optout.html?locale=ko_KR` 以韩语加载选择退出页面。

### 弹出窗口

向页面添加“关闭窗口”按钮，从而使选择退出页面成为弹出窗口。使用 `popup` 查询字符串参数，并将其值设置为 `1`。

例如，`https://example.data.adobedc.net/optout.html?popup=1` 会加载具有“关闭窗口”按钮的选择退出页面。

>[!NOTE]
>
>以前，此查询字符串参数会强制作为弹出窗口。但是，大多数现代浏览器都会控制向最终用户显示弹出窗口。

### 单击选择退出

允许用户立即选择退出跟踪。添加两个查询字符串参数 `opt_out` 和 `confirm_change`，为每个参数赋值 `1`。

例如，`https://example.data.adobedc.net/optout.html?opt_out=1&confirm_change=1` 会立即在访客页面上安装选择退出 Cookie。

### 单击选择加入

允许用户通过删除选择退出 Cookie 立即选择加入跟踪。添加两个查询字符串参数 `opt_in` 和 `confirm_change`，为每个参数赋值 `1`。

例如，`https://example.data.adobedc.net/optout.html?opt_in=1&confirm_change=1` 会立即删除访客的选择退出 Cookie。
