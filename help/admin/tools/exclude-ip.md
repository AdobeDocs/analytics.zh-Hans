---
title: 按 IP 地址排除
description: 防止在报表中出现由某些 IP 地址生成的数据。
exl-id: 315a3000-f043-434b-a677-d111aeed7971
feature: Admin Tools
role: Admin
source-git-commit: 4b4febd839682d88164b2f505245441d18ef2543
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 28%

---

# 按 IP 地址排除

您可以从报表中排除特定 IP 地址的数据，例如，内部网站活动、站点测试和员工使用情况。排除数据可通过排除IP地址数据来提高报表准确性。 此外，您可以从拒绝服务或其他可能扭曲报表数据的恶意事件中删除数据。

要按IP地址排除数据，您可以按如下所述配置排除项，也可以[配置防火墙](/help/technotes/ip-addresses.md)。

## 按IP地址配置排除项

>[!NOTE]
>
>在按IP地址配置排除项时，请考虑以下事项：
>
>* 按 IP 地址排除的点击按[服务器调用](/help/technotes/terms.md)计费。
>* 无需排除私有 IP 地址。只有外部 IP 地址可抵达 Adobe 数据收集服务器。私有地址包括 `10.*.*.*`、`192.168.*.*`、`172.[16-31].*.*` 和 `169.254.*.*`。
>* 您可以使用通配指示符(&#42;)排除某个范围的地址。 例如，`[!DNL 0.0.*.0]` 将排除 `[!DNL 0.0.0.0]` 和 `[!DNL 0.0.255.0]` 之间的所有 IP 地址。最多可以排除 50 个不同的 IP 地址。
>* 对于在设置排除后的5分钟内进入系统的任何新点击，会排除排除排除的IP地址中的数据。
>* 在对IP地址进行更改之前捕获的点击数据不会受到影响。 IP排除仅适用于未来的数据。
>* 排除的点击在[数据馈送](/help/export/analytics-data-feed/data-feed-overview.md)（标记为`exclude_hit = 4`）中仍可见。

要按IP地址配置排除项，请执行以下操作：

1. 在Adobe Analytics中，选择&#x200B;**[!UICONTROL 管理员]** > **[!UICONTROL 所有管理员]**。

1. 在“管理”页面上，选择&#x200B;**[!UICONTROL 按IP排除]**。

## 将IP模糊处理与IP排除结合使用的影响

使用[IP模糊处理](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)以及IP排除的影响取决于每个报表包的IP模糊处理设置：

* **IP模糊处理（最后一个八位字节）**：运行IP排除之前，IP被部分模糊处理。 确保IP排除规则始终将`0`作为最后一个八位字节（通配符有效，因为它们包含`0`）。
* **IP模糊处理（删除IP）**：运行IP排除后，IP被完全模糊处理。 无需调整IP排除规则。
