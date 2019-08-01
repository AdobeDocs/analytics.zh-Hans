---
description: 完成数据连接器界面中的集成向导的步骤。
seo-description: 完成数据连接器界面中的集成向导的步骤。
seo-title: 完成Adobe集成向导
solution: Analytics
title: 完成Adobe集成向导
uuid: a8135be3-fba3-436d-8959-faed40 b15088
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Completing the Adobe Integration Wizard{#completing-the-adobe-integration-wizard}

完成数据连接器界面中的集成向导的步骤。

1. 导航到Adobe Marketing Cloud中的数据连接器(以前称为Genesis)区域。
1. 启动ContactLab集成向导。
1. 选择所需的报表包，并提供集成的名称。
1. 配置以下项目：

   | 项目 | 描述 |
   |---|---|
   | 电子邮件地址 | 主要联系人的电子邮件地址 |
   | 描述 | (可选)此集成设置的说明 |

1. Configure the following **[!UICONTROL Variable Mappings]** items:

   | 项目 | 描述 |
   |---|---|
   | 链接 ID | 选择一个eVar以实时收集链接ID。 |
   | 消息ID | 选择一个eVar以实时收集消息ID。 |
   | Recipient ID | 选择一个eVar以实时收集收件人ID。 |
   | 跳出次数 | 选择数字事件可从ContactLab收到每日弹回。 |
   | 已发送 | 选择数字事件可从ContactLab接收每日发送。 |
   | Clicked | 选择数字事件以接收ContactLab的每日点击量。 |
   | 已打开 | 选择一个数字事件以从ContactLab收到每日总打开次数。 |
   | 取消订阅 | 选择数字事件以每天接收ContactLab的取消订阅。 |

1. 启用数据访问和配置数据收集。
   1. 根据需要重命名分类。
   1. **[!UICONTROL 合作伙伴细分]** 是包含在集成中的标准再营销细分。
   1. Under **[!UICONTROL Your Segments]**, select any custom segments that you would like to include in this integration. 您可以在管理面板下创建其他自定义区段。
   1. Under **[!UICONTROL Access Requests]**, check the box to allow product information to be exported to ContactLab in daily remarketing segments.
   1. 根据需要重命名计算量度。
   1. 通过手动更新Analytics收集代码或使用自动化解决方案，配置您是否将收集ID。If you select **[!UICONTROL Automated Solution]**, you must include the parameters that are used in email links to pass ID’s.
1. Review all configuration items and click **[!UICONTROL Activate Now]**.
