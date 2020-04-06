---
description: 您可以从报表中排除特定 IP 地址的数据，例如，内部网站活动、站点测试和员工使用情况。排除数据可通过排除IP地址数据提高报表准确性。 此外，您还可以从拒绝服务或其他可能歪斜报告数据的恶意事件中删除数据。 您可以配置排除，也可以使用防火墙。
title: 按 IP 地址排除
topic: Admin tools
uuid: 1ed6105f-e7c5-4c4f-b8f4-e5f66d0824bb
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 按 IP 地址排除

您可以从报表中排除特定 IP 地址的数据，例如，内部网站活动、站点测试和员工使用情况。排除数据可通过排除IP地址数据提高报表准确性。 此外，您还可以从拒绝服务或其他可能歪斜报告数据的恶意事件中删除数据。 您可以配置排除，也可以使用防火墙。

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Exclude by IP]**

>[!NOTE] 按 IP 地址排除的点击将作为[服务器调用](https://marketing.adobe.com/resources/help/zh_CN/reference/primary_server_calls.html)计费。

## 按 Cookie 排除 {#section_FB5A20AB5E514DA6BC596CC67F6A3A4C}

允许您排除在帐户中跟踪此计算机。 如果选择排除计算机，则不会计算从计算机生成的任何数据。

此功能可让您和您的同事在访问您的网站时不影响流量数据。如果您没有静态IP地址(如通过服务提供商进行拨号Internet连接)，并且希望从帐户数据中排除自己，则可能希望使用此功能。

| 元素 | 描述 |
|--- |--- |
| [!UICONTROL Add CNAME] | 生成可用于排除域的退出链接。 如需帮助，请与您公司的受支持用户联系。<br>只需访问您公司的禁用页面并选择将您的浏览器排除在测量范围之外，就不会在报表包中报告您的流量。<br>如果您的实施使用的是第三方 Cookie，请从[此处](https://democorp.112.2o7.net/optout.html?locale=en_US&amp;popup=true)获取您的禁用页面。 |

>[!NOTE] 只有符合以下条件时，按计算机排除数据才适适用：
>
> * 从同一工作站进入网站。
> * 您所使用的浏览器启用了 cookie。
> * 您的 cookie 未删除。如果 cookie 已删除，您必须再次排除本人的帐户。


## 按 IP 地址排除 {#section_609FB6461529409D840111A32FEF5C3D}

IP地址是Internet地址。 所有Internet用户都被分配有数字IP地址(通常通过Internet服务提供商)，这些地址有效地充当电子标识符。

页面视图计数，并通过IP地址识别唯一的页面访客。 排除IP地址后，您就无法跟踪频繁的访客。 此功能允许您和您的同事访问您的站点，而不会影响流量数据的准确性。 最多可以排除 50 个不同的 IP 地址。

可以使用通配符指示符(*)来排除一系列地址。 例如，`[!DNL 0.0.*.0]` 将排除 `[!DNL 0.0.0.0]` 和 `[!DNL 0.0.255.0]` 之间的所有 IP 地址。最多可以排除 50 个不同的 IP 地址。

## 通过防火墙排除 {#section_3E7BFB71ADD941D39F923DB9557AD9CD}

您还可以通过防火墙阻止从特定 IP 地址收集数据。

请参阅 [Experience Cloud中使用的IP地址](https://marketing.adobe.com/resources/help/zh_CN/home/index.html#kb-adobe-ip-addresses) 。

## IP模糊化的影响 {#section_51B7529FFF16449CA016FDC51D87E2CA}

如果启用了 IP 模糊处理，则在 IP 地址被模糊处理之前会进行 IP 排除，这样客户就无需在启用 IP 模糊处理时更改任何内容。

如果删除最后八位字节，则在IP过滤之前完成。 因此，最后八位字节将替换为0，并且应更新IP排除规则以使IP地址与末尾的零相匹配。 匹配 * 应当匹配 0。
