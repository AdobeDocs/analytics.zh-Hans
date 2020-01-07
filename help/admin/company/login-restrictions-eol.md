---
title: “[!UICONTROL 强制 IP 登录限制]”终止使用
description: 了解“[!UICONTROL 强制 IP 登录限制]”的终止使用时间和含义
translation-type: ht
source-git-commit: 490a856effac7ec3ff2430dff0ffdcee587bf933

---


# “[!UICONTROL 强制 IP 登录限制]”终止使用

通过 Adobe Analytics 中的&#x200B;**[强制 IP 登录限制](/help/admin/company/security-manager.md)**&#x200B;功能，您可以将特定的 IP 地址（被认为是安全的）列入白名单，以便成功登录并访问 Adobe Analytics 环境。在许多情况下，此功能用于将公司 IP 地址设置为用户可以从中登录的唯一安全 IP 地址。因此，要使用 Adobe Analytics，这要求用户位于公司办公室或通过 VPN 登录网络。

我们计划于 2020 年 10 月终止使用此功能。

## 为什么我们要终止使用此功能？

在某些情况下，Experience Cloud 登录迁移和/或 Experience Cloud 登录会破坏此功能。对于使用&#x200B;**[!UICONTROL 客户属性]**&#x200B;或&#x200B;**[!UICONTROL 受众库]**&#x200B;的客户，此功能已知会受到破坏。

此外，如果您拥有多个 Experience Cloud 解决方案，则可以通过使用其他某个解决方案登录 Experience Cloud 来绕过此要求，因为该功能本身在 Analytics 外部不存在或不受支持。用户还可以通过 IP 欺骗来绕过此要求。

最后，Adobe 通过单点登录和 Federated ID 提供了功能强大且出众的替代解决方案。这些功能可让您更好地控制用户的登录体验并确保安全。有关详细信息，请参阅下文。

## 删除此功能对您有何影响？

对于已设置&#x200B;**[!UICONTROL 强制 IP 登录限制]**&#x200B;的任何客户，此功能将于 2020 年 10 月被删除。届时，将不再强制执行任何已设置的 IP 登录限制。如果仍需要通过 IP 地址限制登录，则应查看并实施推荐的单点登录和 Federated ID 解决方案（下面提供了更多信息和资源）。

此外，还将从 Analytics UI 的&#x200B;**[!UICONTROLA管理员 &gt; 公司设置 &gt; 安全管理器]**&#x200B;中删除&#x200B;**[!UICONTROL 强制 IP 登录限制]**&#x200B;设置（如下所示）。

![](assets/sec-manager2.png)

## 您有哪些其他选项？

如上所述，此 Analytics 功能将终止使用。为了让您有时间实施 SSO 和 Federated ID，我们将终止使用日期推迟到了 2020 年 10 月。

SSO 和 Federated ID 都是我们当前使用的 IP 登录限制功能的高级解决方案，它们将为您提供更好的控制、安全性和功能。有关如何设置 SSO/Federated ID 的信息，我们提供了以下帮助文档。我们建议您仔细阅读这些文档并与您的 IT 部门合作，以实施这些功能：

* [单点登录和 Experience Cloud](https://spark.adobe.com/page/JeSB8EPEQIvjD/)
* [Admin Console - 身份设置文档](https://helpx.adobe.com/cn/enterprise/using/set-up-identity.html)
* [Admin Console - 身份设置教程（视频）](https://helpx.adobe.com/cn/enterprise/how-to/identity-directories-domains.html?playlist=/ccx/v1/collection/product/enterprise/topics/enterprise-identity/collection.ccx.js&amp;ref=helpx.adobe.com)
* [配置 Federated ID 教程（视频）](https://helpx.adobe.com/cn/enterprise/how-to/identity-configure-ids.html?playlist=/ccx/v1/collection/product/enterprise/topics/enterprise-identity/collection.ccx.js&amp;ref=helpx.adobe.com)
* [单点登录 - 常见问题](https://helpx.adobe.com/cn/enterprise/using/sso-faq.html)
* [Adobe 支持的身份类型](https://helpx.adobe.com/cn/enterprise/using/identity.html)

如果您想继续表达对 IP 登录限制的支持并请求 Experience Cloud 提供该功能，则可以在我们的[论坛页面](https://forums.adobe.com/ideas/11648)上对该功能进行投票来表示支持。