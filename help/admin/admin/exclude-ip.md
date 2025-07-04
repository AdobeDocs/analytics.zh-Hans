---
title: 按 IP 地址排除
description: 防止在报表中出现由某些 IP 地址生成的数据。
exl-id: 315a3000-f043-434b-a677-d111aeed7971
feature: Admin Tools
role: Admin
source-git-commit: d642bf8703d7c4c1545bfd9763c70ed8b1237eac
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 62%

---

# 按 IP 地址排除

您可以从报表中排除特定 IP 地址的数据，例如，内部网站活动、站点测试和员工使用情况。数据排除能够通过排除 IP 地址数据来提高报表的准确性。此外，还可以删除来自拒绝服务攻击或其他可能影响报表数据准确性的恶意事件的数据。

要按IP地址排除数据，您可以按如下所述配置排除项，也可以[配置防火墙](/help/technotes/ip-addresses.md)。

## 按IP地址配置排除项

>[!NOTE]
>
>在按IP地址配置排除项时，请考虑以下事项：
>
>* 按 IP 地址排除的点击按[服务器调用](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=zh-Hans)计费。
>* 无需排除私有 IP 地址。只有外部 IP 地址可抵达 Adobe 数据收集服务器。私有地址包括 `10.*.*.*`、`192.168.*.*`、`172.[16-31].*.*` 和 `169.254.*.*`。
>* 您可以使用通配指示符(&#42;)排除某个范围的地址。 例如，`[!DNL 0.0.*.0]` 将排除 `[!DNL 0.0.0.0]` 和 `[!DNL 0.0.255.0]` 之间的所有 IP 地址。最多可以排除 50 个不同的 IP 地址。
>* 对于在设置排除后的5分钟内进入系统的任何新点击，会排除排除排除的IP地址中的数据。
>* 在对IP地址进行更改之前捕获的点击数据不会受到影响。
>

要按IP地址配置排除项，请执行以下操作：

1. 在Adobe Analytics中，选择&#x200B;**[!UICONTROL 管理员]** > **[!UICONTROL 所有管理员]**。

1. 在“管理”页面上，选择&#x200B;**[!UICONTROL 按IP排除]**。




## IP模糊处理的影响 {#section_51B7529FFF16449CA016FDC51D87E2CA}

如果启用了 IP 模糊处理，则在 IP 地址被模糊处理之前会进行 IP 排除，这样客户就无需在启用 IP 模糊处理时更改任何内容。

如果删除了最后八位字节，则该操作是在 IP 过滤之前完成的。这样，最后八位字节将被替换为 0，并且应当更新 IP 排除规则以匹配末尾为 0 的 IP 地址。匹配 &#42; 应匹配 0。
