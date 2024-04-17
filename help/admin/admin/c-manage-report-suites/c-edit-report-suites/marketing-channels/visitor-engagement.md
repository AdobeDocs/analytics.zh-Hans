---
description: 了解如何在营销渠道中指定访客参与到期。
subtopic: Marketing channels
title: 营销渠道到期
feature: Marketing Channels
exl-id: a9df659b-3b6a-4bdb-bd77-f4490d2b7c79
role: Admin
source-git-commit: def7d071de1765acf524a638a8f8d13ae69e1a1f
workflow-type: ht
source-wordcount: '389'
ht-degree: 100%

---

# 营销渠道到期

>[!NOTE]
>
> 有关营销渠道的一般信息，请参阅[营销渠道快速入门](/help/components/c-marketing-channels/c-getting-started-mchannel.md)。
>
> 为了最大限度地提高归因和 Customer Journey Analytics 的营销渠道效率，我们发布了一些[修订后的最佳实践](/help/components/c-marketing-channels/mchannel-best-practices.md)。

**[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 报表包]** > **[!UICONTROL 编辑设置]** > **[!UICONTROL 营销渠道]** > **[!UICONTROL 营销渠道到期]**。

了解如何为营销渠道指定到期时间或访客参与期限。

访客参与是指您希望多长时间使访客在网站上的先前活动归于首次联系渠道。默认到期设置为 30 天。

如果访客频繁使用网站，则参与窗口将随着这些访问渠道一起滚动。渠道必须处于非活动状态 30 天后，该期限才会到期，并且渠道才会重置。如果访客的首次接触和最后接触渠道在该浏览器上处于非活动状态持续 30 天，则会进行重置。

示例：

* 第 1 天：用户通过“显示”访问网站。首次联系和最近联系渠道将设置为“显示”。
* 第 2 天：用户通过“免费搜索”访问网站。首次联系仍为“显示”，最近联系将设置为“免费搜索”。
* 第 35 天：用户已经 33 天没有访问过该网站，现在使用他们在浏览器中打开的选项卡重新访问该网站。假设参与期为 30 天，此时，该窗口将关闭，并且营销渠道 Cookie 将过期。由于用户来自内部 URL，因此首次联系和最近联系渠道将被重置，并且都将设置为“会话刷新”。

## 营销渠道到期时间设置

到期设置包括：

| 字段 | 定义 |
|--- |--- |
| 不活动天数 | 访客首次联系参与到期前必须经过的天数。默认值为 30。 |
| 从不 | 访客的参与期限不会到期。 |
| 渠道重置 | 将所有访客的参与期限设置为过期。如果您需要重置所有营销渠道数据，可以将所有访客的参与期限设置为过期。如果您的处理规则先前配置错误，则可能需要重置数据。当访客回访时，所有首次联系和最近联系渠道值都将立即过期并被重置。 |

## 定义营销渠道到期 {#define-expiration}

指定访客参与期限。

1. 单击 **[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 报表包]**。
2. 在[!UICONTROL 报表包管理器]中，单击&#x200B;**[!UICONTROL 编辑设置]** > **[!UICONTROL 营销渠道]** > **[!UICONTROL 营销渠道到期]**。

   ![](assets/mchannel_expiration.png)

3. 配置访客参与期限字段。
4. 单击&#x200B;**[!UICONTROL 保存]**。
