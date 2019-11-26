---
title: 强制IP登录限制 [!UICONTROL 的终止]
description: 了解生命周期结束的时间安排及其对实施IP登录限 [!UICONTROL 制的影响]
translation-type: tm+mt
source-git-commit: 490a856effac7ec3ff2430dff0ffdcee587bf933

---


# 强制IP登录限制 [!UICONTROL 的终止]

通过 **[Adobe Analytics中的强制IP登录限制](/help/admin/company/security-manager.md)** ，您可以将特定IP地址（被视为安全的）列入白名单，以允许成功登录并访问您的Adobe Analytics环境。 在许多情况下，此功能用于将企业IP地址设置为用户可从中登录的唯一安全IP地址。 因此，要使用Adobe Analytics，这要求用户在公司办公室或通过VPN登录网络。

我们计划在2020年10月终止此功能。

## 为什么我们要终止此功能？

在某些情况下，Experience cloud登录迁移和／或Experience cloud登录会破坏此功能。 众所周知，使用客户属性或受众库 **[!UICONTROL 的客户]** ，会 **[!UICONTROL 中断]**。

此外，如果您拥有多个Experience cloud解决方案，则可以使用其他解决方案之一登录Experience Cloud来绕过此要求，因为Analytics本身之外不存在或不支持此功能。 用户还可以通过IP欺骗来绕过此问题。

最后，Adobe通过单点登录和联合ID提供了功能强大且出众的替代解决方案。 此功能可让您更好地控制用户的登录体验并提高安全性。 请参阅下文以了解更多信息。

## 删除此功能对您有何影响？

对于设置了“强 **[!UICONTROL 制IP登录限制]** ”的任何客户，此功能将于2020年10月删除。 此时，任何仍然有效的IP登录限制将不再得到实施。 如果您仍需要按IP地址限制登录，则应查看并实施推荐的单点登录和联合ID解决方案（下面的更多信息和资源）。

此外，将 **[!UICONTROL 从Analytics UI中的]** dmin &gt;公司设置&gt;安全管理器 **[!UICONTROLA]** （如下所示）中删除强制IP登录限制设置。

![](assets/sec-manager2.png)

## 您还有哪些选择？

如上所述，此Analytics功能将停止运行。 为了给您时间实施SSO和Federated ID，我们已将EOL日期延迟至2020年10月。

SSO和Federated ID都是我们目前所具备的IP登录限制功能的出众解决方案，将为您提供更多控制、安全和功能。 有关如何设置SSO/Federated ID的信息，我们提供以下帮助文档。 我们建议您仔细阅读并与您的IT部门合作，以实现这些功能：

* [单点登录和Experience Cloud](https://spark.adobe.com/page/JeSB8EPEQIvjD/)
* [Admin Console —— 身份设置文档](https://helpx.adobe.com/enterprise/using/set-up-identity.html)
* [Admin Console —— 身份设置教程（视频）](https://helpx.adobe.com/enterprise/how-to/identity-directories-domains.html?playlist=/ccx/v1/collection/product/enterprise/topics/enterprise-identity/collection.ccx.js&ref=helpx.adobe.com)
* [配置Federated ID教程（视频）](https://helpx.adobe.com/enterprise/how-to/identity-configure-ids.html?playlist=/ccx/v1/collection/product/enterprise/topics/enterprise-identity/collection.ccx.js&ref=helpx.adobe.com)
* [单点登录——常见问题](https://helpx.adobe.com/enterprise/using/sso-faq.html)
* [Adobe支持的身份类型](https://helpx.adobe.com/enterprise/using/identity.html)

如果您希望继续表达对IP登录限制的支持并请求IP登录限制由Experience cloud提供，您可以在“论坛”页面上投票支持此 [功能](https://forums.adobe.com/ideas/11648)。