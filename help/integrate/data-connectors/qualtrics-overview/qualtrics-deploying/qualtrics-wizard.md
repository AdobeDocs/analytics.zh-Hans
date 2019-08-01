---
description: 要激活集成，您必须完成数据连接器界面中的Qualtrics集成向导
seo-description: 要激活集成，您必须完成数据连接器界面中的Qualtrics集成向导
seo-title: 完成Adobe集成向导
solution: Analytics
subtopic: Qualtrics
title: 完成Adobe集成向导
topic: Data connectors
uuid: e065fba4-1fe1-4e25-9c55-6c52dc20f81e
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Completing the Adobe Integration Wizard{#completing-the-adobe-integration-wizard}

要激活集成，您必须完成数据连接器界面中的Qualtrics集成向导

1. 导航到数据连接器并启动Qualtrics集成向导。([Data Connectors 帮助](http://microsite.omniture.com/t2/help/en_US/genesis/)).
1. 选择要用于此集成的报表包并提供一个名称。

   完成集成向导，提供以下步骤所述的信息。1. **Wizard Step 1**

   | Email Address | 主要联系人电子邮件地址。 |
   |---|---|
   | 描述 | (可选)此集成设置的说明。 |
   | Qualtrics组织ID | [查找Qualttrics组织ID](../../qualtrics-overview/qualtrics-org-id.md#task-47ea30d6dcd24893986a5e5b8dcf5e96) |
   | Adobe SiteCatalyst令牌 | [生成Qualtrics Adobe Analytics令牌](../../qualtrics-overview/qualtrics-token.md#task-e32eacbc91614008b84e6b2f0b92d372) |

1. **向导步骤-变量映射**

   | Qualtrics响应列表 | 从报表包中选择可用的列表变量。(您可能需要在报表包管理器中启用新的ListVar。) |
   |---|---|
   | Qualtrics响应ID | 从您的报表套件中选择可用的eVar或prop。(您可能需要在报表包管理器中启用新的ListVar。) |
   | 跟踪服务器 | 提供用于跟踪Adobe Analytics数据的跟踪服务器(域)设置。Use the `trackingServerSecure` tracking server if it differs from your standard tracking server setting. |
   | Qualtrics Survey提交 | 从报表包中选择可用活动(您可能需要从报表包管理器中启用新活动)。 |

1. **向导步骤3**：不需要任何信息。

   Step Result1.**向导步骤-导出设置**

   | eVar | 选择最多五个eVar以导出到Qualtrics |
   |---|---|
   | 事件 | 选择最多五个自定义事件以导出到Qualtrics |
   | Prop | 选择最多五个Prop以显示导出到Qualtrics |
   | 访问请求 | 检查您希望导出到Qualtrics的任何标准指标和维度的框。The `visitor_id` is required to allow the export to function properly. |

1. **向导步骤5**：查看配置，然后单击 **[!UICONTROL 立即激活]**。
