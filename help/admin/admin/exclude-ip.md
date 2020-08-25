---
title: 按 IP 地址排除
description: 防止某些IP地址生成的数据显示在报告中。
translation-type: tm+mt
source-git-commit: 47b14bde1bb1217bcb172c6d4f01d68f917d44db
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 85%

---


# 按 IP 地址排除

您可以从报表中排除特定 IP 地址的数据，例如，内部网站活动、站点测试和员工使用情况。数据排除能够通过排除 IP 地址数据来提高报表的准确性。此外，还可以删除来自拒绝服务攻击或其他可能影响报表数据准确性的恶意事件的数据。您可以对排除进行配置，也可以使用您的防火墙进行排除。

**[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 按 IP 排除]**

>[!NOTE]
>
>按 IP 地址排除的点击将作为[服务器调用](https://docs.adobe.com/content/help/zh-Hans/analytics/technotes/terms.html)计费。

您可使用通配符标记 (*) 排除某个地址范围。例如，`[!DNL 0.0.*.0]` 将排除 `[!DNL 0.0.0.0]` 和 `[!DNL 0.0.255.0]` 之间的所有 IP 地址。最多可以排除 50 个不同的 IP 地址。

>[!TIP]
>
>私有IP地址无需排除。 只有外部IP地址可以到达Adobe数据收集服务器。 私有地址 `10.*.*.*`包括 `192.168.*.*`、 `172.[16-31].*.*`、和 `169.254.*.*`。

## IP 模糊处理的影响 {#section_51B7529FFF16449CA016FDC51D87E2CA}

如果启用了 IP 模糊处理，则在 IP 地址被模糊处理之前会进行 IP 排除，这样客户就无需在启用 IP 模糊处理时更改任何内容。

如果删除了最后八位字节，则该操作是在 IP 过滤之前完成的。这样，最后八位字节将被替换为 0，并且应当更新 IP 排除规则以匹配末尾为 0 的 IP 地址。匹配 * 应当匹配 0。
