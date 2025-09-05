---
description: 阐述欧盟 Cookie 监管法规促成的服务器端转发改进。
title: GDPR/ePrivacy 合规和服务器端转发
feature: Report Suite Settings
exl-id: 54e43a16-8f15-4ee8-9aa2-579af30be2c9
role: Admin
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 55%

---

# GDPR/ePrivacy 合规和服务器端转发

此部分阐述（2017 年 9 月 30 日生效的）[欧盟 Cookie 监管法规](https://wikis.ec.europa.eu/display/WEBGUIDE/04.+Cookie 和类似技术)促成的服务器端转发改进。

服务器端转发用于实时将数据从 Adobe Analytics 共享到其他 [!DNL Experience Cloud Solutions]，例如 Audience Manager。启用服务器端转发后，Analytics 还可在数据收集过程中将数据推送到其他 Experience Cloud 解决方案，并且这些解决方案可将数据推送到 Analytics。

以前，服务器端转发无法区分同意和同意前的事件/点击。自2018年11月1日起，作为数据控制者(Adobe Analytics客户)，您可以选择将预先同意的数据限制在Adobe Analytics中，并阻止将这些数据转发到Adobe Audience Manager。 新的实施环境变量可以让您标记出在未获得同意的情况下的点击量。变量设置后，可在征得同意之前阻止将这些点击发送到Adobe Audience Manager。

当点击存在此新上下文变量`cm.ssf=1`时，此点击会进行标记，因此不会被服务器端转发到Adobe Audience Manager。 相反，如果点击中未显示此字符串，则点击将被转发到Adobe Audience Manager。

服务器端转发是双向的，这意味着当它将应用于点击，并且该点击被转发到Adobe Audience Manager时，Audience Analytics将从Adobe Audience Manager接收该点击的区段信息，并将其发送回Analytics。 因此，任何不是从Analytics服务器端转发到Adobe Audience Manager的点击都不会使用Adobe Audience Manager中的区段ID列表进行扩充。 因此，将存在一个流量/点击的子集，这些流量/点击不会从Adobe Audience Manager获取区段ID信息。

## 实施详细信息 {#section_FFA8B66085BF469FAB5365C944FE38F7}

根据您的实施方法，请按照下列步骤操作。

| 实施方法 | 步骤 |
|--- |--- |
| Adobe Experience Platform 中的标记 | 假设您已安装 Adobe Analytics 扩展，请将以下 contextData 变量定义添加到规则的“操作”配置内的自定义代码编辑器：<br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' `<br/>注意：如果客户不同意进行目标营销，请定义 contextData 变量，并将它设置为 1。对于同意进行目标营销的客户，请将 `contextdata` 变量设置为 *0*。 |
| AppMeasurement | 将上下文数据变量定义添加到AppMeasurement.js文件： <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>注意：如果客户不同意进行目标营销，请定义上下文数据变量并将其设置为1。 对于同意进行目标营销的客户，请将 contextData 变量设置为 0。 |

## 报表（可选） {#section_6AD4028EC11C4DABA2A34469DDC99E89}

您可以使用Adobe Analytics报告有多少流量基于同意并经由服务器端转发，以及有多少流量非基于同意且尚未转发到Adobe Audience Manager。

要配置此类型的报表，请通过处理规则将新上下文变量映射到自定义流量变量 (prop)。为此，请执行以下步骤：

1. 实施“cm.ssf”变量（如上所示。）
1. [启用 prop。](/help/admin/tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md)
1. 使用处理规则将上下文变量映射到 prop。

   1. 转至 **[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 报表包]**，然后选择一个报表包。
   1. 单击&#x200B;**[!UICONTROL 编辑报表包]** > **[!UICONTROL 常规]** > **[!UICONTROL 处理规则]**。
   1. 单击&#x200B;**[!UICONTROL 添加规则。]**
   1. 在&#x200B;**[!UICONTROL 始终执行]**&#x200B;下，使用上下文变量“cm.ssf(Context Data)”覆盖您已启用的 prop 的值。
   1. 单击&#x200B;**[!UICONTROL 保存]**。
