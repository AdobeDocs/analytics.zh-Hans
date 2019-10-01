---
description: 'null'
seo-description: 'null'
seo-title: 部署集成
solution: Analytics
title: 部署集成
uuid: 5abf6d49-b05b-4e0f-8d9b-bb02d8f1c84a
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

---


# 部署集成{#deploying-the-integration}

部署此集成是一个简单的过程，它需要执行以下操作：

## 完成Adobe集成向导{#completing-the-adobe-integration-wizard}

完成数据连接器界面中集成向导的步骤。

1. 导航到Adobe Experience cloud中的数据连接器（以前称为Genesis）区域。
1. 启动Responsys集成向导。
1. 选择所需的报表包并提供集成的名称。
1. 配置以下项目：

   | 项目 | 描述 |
   |---|---|
   | 电子邮件地址 | 主要联系人的电子邮件地址 |
   | 描述 | （可选）此集成设置的说明 |
   | 帐户ID | 联系Responsys支持团队support@responsys.com获得 |

1. 配置以下 **[!UICONTROL 变量映射]** :

   | 项目 | 描述 |
   |---|---|
   | 消息ID | 选择一个eVar以实时收集消息ID。 |
   | Recipient ID | 选择一个eVar以实时收集收件人ID。 |
   | 总弹回次数 | 选择一个数字事件以从Responsys接收每日弹回。 |
   | 电子邮件已发送 | 选择一个数字事件，以从Responsys接收每日发送。 |
   | 已单击 | 选择一个数字事件，从Responsys接收每日总点击量。 |
   | 已打开 | 从Responsys中选择一个数字事件以接收每日打开总数。 |
   | 取消订阅 | 选择一个数字事件，以从Responsys接收每日取消订阅。 |
   | 交付 | 选择一个数字事件，以从Responsys接收每日发送。 |

1. 启用数据访问和配置数据收集。
   1. 根据需要重命名分类。
   1. **[!UICONTROL 合作伙伴细分]** ，是包含在您的集成中的标准再营销细分。
   1. 在“ **[!UICONTROL 访问请求]**”下，选中该框可允许将产品信息导出到每日再营销区段中的Responsys。
   1. 配置您是通过手动更新Analytics收集代码还是使用自动化解决方案来收集ID。 如果选择“ **[!UICONTROL 自动解决方案]**”，则必须包含电子邮件链接中使用的参数才能传递ID。
1. 查看所有配置项，然后单击“ **[!UICONTROL 立即激活]**”。

## 在Responsys系统内配置{#configuring-within-the-responsys-system}

激活集成需要联系Responsys支持。

完成集成向导后，必须激活Responsys内的集成。

为此，请通过support@responsys.com与Responsys支持团队联系。