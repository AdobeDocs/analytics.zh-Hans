---
description: 'null'
title: GDPR/ePrivacy 合规和服务器端转发
uuid: 1b90c567-3321-4dbd-a699-38c04e809fa4
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# GDPR/ePrivacy 合规和服务器端转发

本部分介绍了根据 2017 年 9 月 30 日生效的[欧盟 Cookie 合规条例](https://ec.europa.eu/ipg/basics/legal/cookies/index_en.htm)的规定，最近对服务器端转发所做的功能增强。

服务器端转发用于实时将数据从 Adobe Analytics 共享到其他 [!DNL Experience Cloud Solutions]，例如 Audience Manager。启用服务器端转发后，在数据收集过程中该功能还允许 Analytics 将数据推送到其他 Experience Cloud 解决方案，而对于这些解决方案，则将数据推送到 Analytics。

直到最近，服务器端转发还无法划定同意事件/点击和预先同意的事件/点击。从 2018 年 11 月 1 日起，数据控制方（Adobe Analytics 客户）可以选择将预先同意的数据限制在 Adobe Analytics 中，并阻止将其转发到 AAM。新的实施环境变量可以让您标记出在未获得同意的情况下的点击量。设置了该变量后，它可以阻止将这些点击量发送到 AAM，直至获得同意为止。

当点击存在新上下文变量 `cm.ssf=1` 时，此点击会进行标记，因此不会被服务器端转发到 AAM。相反，如果未对点击设置此字符串，则点击会被转发到 AAM。

服务器端转发是双向的，这意味着当它应用于点击并且该点击被转发到 AAM 时，Audience Analytics 会从 AAM 接收该点击的区段信息并将其发送回 Analytics。因此，对于不是由服务器端从 Analytics 转发到 AAM 的任何点击，将不会使用 AAM 的区段 ID 列表加以丰富。这样，便会有部分流量/点击不会从 AAM 中获取区段 ID 信息。

## 实施详细信息 {#section_FFA8B66085BF469FAB5365C944FE38F7}

根据您的实施方法，请按照下列步骤操作。

| 实施方法 | 步骤 |
|--- |--- |
| Adobe Experience Platform Launch | 如果您已安装 Adobe Analytics 扩展，请在规则的“操作”配置中将以下上下文数据变量定义添加到自定义代码编辑器：<br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' `<br/>注意：如果客户不同意进行目标营销，请定义上下文数据变量并将其设置为 1。如果客户同意进行目标营销，则将 `contextdata` 变量设置为 *0*。 |
| DTM | 将上下文数据变量定义添加到自定义页面代码编辑器：<br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' `<br/>注意：定义 contextdata 变量时，如果客户不同意进行目标营销，则将其设置为 1。如果客户同意进行目标营销，则将 contextdata 变量设置为 0。 |
| AppMeasurement | 将上下文数据变量定义添加到 AppMeasurement.js 文件：<br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' `<br/>注意：定义 contextdata 变量时，如果客户不同意进行目标营销，则将其设置为 1。如果客户同意进行目标营销，则将 contextdata 变量设置为 0。 |

## 报表（可选）{#section_6AD4028EC11C4DABA2A34469DDC99E89}

您可以使用 Adobe Analytics 报告有多少流量基于同意并经由服务器端转发，以及有多少流量非基于同意且尚未转发到 AAM。

要配置此类型的报表，请通过处理规则将新上下文变量映射到自定义流量变量 (prop)。为此，请执行以下步骤：

1. 实施“cm.ssf”变量（如上所示。）
1. [启用 prop。](/help/admin/admin/c-traffic-variables/traffic-var.md)
1. 使用处理规则将上下文变量映射到 prop。

   1. 转至 **[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 报表包]**，然后选择一个报表包。
   1. 单击&#x200B;**[!UICONTROL 编辑报表包]** > **[!UICONTROL 常规]** > **[!UICONTROL 处理规则]**。
   1. 单击&#x200B;**[!UICONTROL 添加规则。]**
   1. 在&#x200B;**[!UICONTROL 始终执行]**&#x200B;下，使用上下文变量“cm.ssf(Context Data)”覆盖您已启用的 prop 的值。
   1. 单击&#x200B;**[!UICONTROL 保存]**。

