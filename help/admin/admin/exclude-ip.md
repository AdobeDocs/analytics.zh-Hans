---
description: 您可以从报表中排除特定 IP 地址的数据，例如，内部网站活动、站点测试和员工使用情况。数据排除能够通过排除 IP 地址数据来提高报表的准确性。此外，还可以删除来自拒绝服务攻击或其他可能影响报表数据准确性的恶意事件的数据。您可以对排除进行配置，也可以使用您的防火墙进行排除。
seo-description: 您可以从报表中排除特定 IP 地址的数据，例如，内部网站活动、站点测试和员工使用情况。数据排除能够通过排除 IP 地址数据来提高报表的准确性。此外，还可以删除来自拒绝服务攻击或其他可能影响报表数据准确性的恶意事件的数据。您可以对排除进行配置，也可以使用您的防火墙进行排除。
seo-title: 按 IP 地址排除
solution: Analytics
title: 按 IP 地址排除
topic: 管理工具
uuid: 1ed6105f-e7c5-4c4f-b8f4-e5f66d0824bb
translation-type: tm+mt
source-git-commit: a26902b3f513f896fc8ba08a8464d7abce9418ca

---


# 按 IP 地址排除

您可以从报表中排除特定 IP 地址的数据，例如，内部网站活动、站点测试和员工使用情况。数据排除能够通过排除 IP 地址数据来提高报表的准确性。此外，还可以删除来自拒绝服务攻击或其他可能影响报表数据准确性的恶意事件的数据。您可以对排除进行配置，也可以使用您的防火墙进行排除。

**[!UICONTROL Analytics]** &gt;管 **[!UICONTROL 理员]** &gt;按 **[!UICONTROL IP排除]**

>[!NOTE]
>
>IP地址排除的点击将计为服 [务器调用](https://marketing.adobe.com/resources/help/en_US/reference/primary_server_calls.html)。

## 按 Cookie 排除 {#section_FB5A20AB5E514DA6BC596CC67F6A3A4C}

可以在帐户中排除对您的计算机的跟踪。如果选择排除您的计算机，则生成的任何来自您的计算机的数据都不会记入。

此功能可让您和您的同事在访问您的网站时不影响流量数据。如果您没有静态 IP 地址（例如您使用服务供应商提供的拨号互联网连接），但希望从您的帐户数据中排除自己，则建议使用此功能。

| 元素 | 描述 |
|--- |--- |
| [!UICONTROL 添加 CNAME] | 生成一个禁用链接，可用于排除您的域。如需帮助，请与您公司的受支持用户联系。<br>只需访问您公司的禁用页面并选择将您的浏览器排除在测量范围之外，就不会在报表包中报告您的流量。<br>如果您的实施使用的是第三方 Cookie，请从[此处](https://democorp.112.2o7.net/optout.html?locale=en_US&popup=true)获取您的禁用页面。 |

>[!NOTE]
>
>由计算机排除仅在以下情况下有效：
>
>* 您从同一工作站进入网站。
>* 您所使用的浏览器启用了 cookie。
>* 您的 cookie 未删除。如果 cookie 已删除，您必须再次排除本人的帐户。


## 按 IP 地址排除 {#section_609FB6461529409D840111A32FEF5C3D}

IP 地址就是互联网地址。所有互联网用户都拥有数字 IP 地址（通常由互联网服务供应商提供），作为有效的电子标识。

系统会记录页面查看次数并通过 IP 地址识别独特页面访客数。通过排除 IP 地址计数，可以防止 Adobe 跟踪频繁访客。此功能可让您和您的同事在访问您的网站时不影响流量数据。最多可以排除 50 个不同的 IP 地址。

您可使用通配符标记 (*) 排除某个地址范围。For example, `[!DNL 0.0.*.0]` would exclude all IP addresses between `[!DNL 0.0.0.0]` and `[!DNL 0.0.255.0]`. 最多可以排除 50 个不同的 IP 地址。

## 通过防火墙排除 {#section_3E7BFB71ADD941D39F923DB9557AD9CD}

您还可以通过防火墙阻止从特定 IP 地址收集数据。

请参阅 [Experience Cloud 中使用的 IP 地址](https://marketing.adobe.com/resources/help/en_US/home/index.html#kb-adobe-ip-addresses)一文。

## IP 模糊处理的影响 {#section_51B7529FFF16449CA016FDC51D87E2CA}

如果启用了 IP 模糊处理，则在 IP 地址被模糊处理之前会发生 IP 排除，这样客户就无需在启用 IP 模糊处理时更改任何内容。

如果删除了最后八位字节，则该操作是在 IP 过滤之前完成的。这样，最后八位字节将被替换为 0，并且应当更新 IP 排除规则以匹配末尾为 0 的 IP 地址。匹配 * 应当匹配 0。
