---
description: 完成数据连接器界面中的集成向导的步骤。
seo-description: 完成数据连接器界面中的集成向导的步骤。
seo-title: 完成Adobe集成向导
solution: Analytics
title: 完成Adobe集成向导
uuid: fb106251-78cf-4a2a-8ba2-2a39188ba910
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Completing the Adobe Integration Wizard{#completing-the-adobe-integration-wizard}

完成数据连接器界面中的集成向导的步骤。

1. 导航到Adobe Marketing Cloud中的数据连接器(以前称为Genesis)区域。
1. 启动Responsys集成向导。
1. 选择所需的报表包，并提供集成的名称。
1. 配置以下项目：

   | 项目 | 描述 |
   |---|---|
   | 电子邮件地址 | 主要联系人的电子邮件地址 |
   | 描述 | (可选)此集成设置的说明 |
   | 帐户ID | 通过联系Responsys支持团队获取support@responsys.com |

1. Configure the following **[!UICONTROL Variable Mappings]** items:

   | 项目 | 描述 |
   |---|---|
   | 消息ID | 选择一个eVar以实时收集消息ID。 |
   | Recipient ID | 选择一个eVar以实时收集收件人ID。 |
   | 退回总次数 | 选择数字事件可从Responsys收到每日弹回次数。 |
   | 发送电子邮件 | 选择数字事件可从Responsys接收每日发送。 |
   | Clicked | 选择数字事件以接收Responsys中的每日点击量。 |
   | 已打开 | 从Responsys中选择要接收每日总打开次数的数字事件。 |
   | 取消订阅 | 选择数字事件以每天接收Responsys的取消订阅。 |
   | 已交付 | 选择数字事件以从Responsys接收每日发送。 |

1. 启用数据访问和配置数据收集。
   1. 根据需要重命名分类。
   1. **[!UICONTROL 合作伙伴细分]** 是包含在集成中的标准再营销细分。
   1. Under **[!UICONTROL Access Requests]**, check the box to allow product information to be exported to Responsys in daily remarketing segments.
   1. 通过手动更新Analytics收集代码或使用自动化解决方案，配置您是否将收集ID。If you select **[!UICONTROL Automated Solution]**, you must include the parameters that are used in email links to pass ID’s.
1. Review all configuration items and click **[!UICONTROL Activate Now]**.
