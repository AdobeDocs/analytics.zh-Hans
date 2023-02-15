---
product: analytics
audience: admin
user-guide-title: Analytics 管理员指南
breadcrumb-title: 管理指南
user-guide-description: 了解 Analytics administration 任务，如在 Experience Cloud Admin Console 中管理用户和产品、配置报告包等等。
source-git-commit: 1ca7040156f7f2105a9625f921de3d90b4175056
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 99%

---


# Adobe Analytics 管理员指南 {#admin}

+ [Analytics 管理员指南](home.md)
+ [Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hans)
+ Adobe Admin Console {#admin-console}
   + [概述](admin-console/home.md)
   + [Adobe Analytics 管理入门指南](admin-console/first-admin-guide.md)
   + [Adobe Analytics 中的管理员角色](admin-console/admin-roles-in-analytics.md)
   + Analytics 工具权限摘要 {#permissions}
      + [Admin Console 中的 Analytics Permissions](admin-console/permissions/summary-tables.md)
      + [Adobe Analytics 的产品配置文件](admin-console/permissions/product-profile.md)
      + [“报告包工具”的产品配置文件权限](admin-console/permissions/report-suite-tools.md)
      + [Analytics 工具的产品配置文件权限](admin-console/permissions/analytics-tools.md)
+ Analytics 管理员工具 {#admin-tools}
   + [管理员工具概述](admin/c-admin-tools.md)
   + [计费](admin/billing-admin.md)
   + [代码管理器](admin/code-manager-admin.md)
   + [数据源](admin/data-sources.md)
   + [按 IP 地址排除](admin/exclude-ip.md)
   + [日志](admin/logs.md)
   + [报告活动管理器](admin/reporting-activity.md)
   + 报告包管理器 {#manage-report-suites}
      + 编辑报告包设置 {#edit-report-suite}
         + 常规 {#report-suite-general}
            + [一般帐户设置](admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)
            + [内部 URL 过滤器](admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md)
            + [自定义日历](admin/c-manage-report-suites/c-edit-report-suites/general/custom-calendar.md)
            + 付费搜索检测{#paid-search-detection}
               + [付费搜索检测概述](admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/paid-search-detection.md)
               + [配置付费搜索检测](admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/t-paid-search-detection.md)
            + [自定义菜单](admin/c-manage-report-suites/c-edit-report-suites/general/customize-menus.md)
            + 处理规则{#c-processing-rules}
               + [处理规则概述](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md)
               + 处理规则 {#c-processing-rules-configuration}
                  + [处理规则的工作原理](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/processing-rules-about.md)
                  + [创建处理规则](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md)
                  + [查看活动处理规则](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules-view.md)
                  + [查看处理规则历史记录](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rule-view-history.md)
                  + [还原处理规则](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules-restore.md)
                  + [将处理规则复制到其他报告包](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules-copy-to-rs.md)
                  + [可用于处理规则的维度](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rule-dimensions.md)
               + 处理规则示例{#processing-rules-examples}
                  + [处理规则的示例](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-examples.md)
                  + [通过查询字符串参数填充促销活动 ID](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-populate-campaign-id.md)
                  + [在产品概述页面中设置产品视图事件](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/setting-the-product-view-event.md)
                  + [通过连接类别和页面名称添加子类别](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/subcategory-concatenating.md)
                  + [通过将 eVar 值复制到 prop 来确定路径](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-determining-path.md)
                  + [清理报告中的值](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/clean-up-values-in-a-report.md)
                  + [使用查询字符串参数填充内部搜索词](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-populating-internal-search.md)
                  + [将上下文数据变量复制到 eVar](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md)
                  + [使用上下文数据变量设置事件](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md)
                  + [通过点击删除事件](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-remove-event.md)
               + [处理规则的提示和技巧](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-tips.md)
            + 机器人规则 {#bot-removal}
               + [机器人移除](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-removal.md)
               + [机器人规则概述](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md)
               + [常见的机器人签名](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-signatures.md)
               + [机器人排除法](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-exclusion-methods.md)
            + [隐私设置](admin/c-manage-report-suites/c-edit-report-suites/general/privacy-settings.md)
            + [可选时间戳](admin/c-manage-report-suites/c-edit-report-suites/general/timestamp-optional.md)
            + 服务器端转发 {#server-side-forwarding}
               + [服务器端转发概述](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf.md)
               + [GDPR/ePrivacy 合规和服务器端转发](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-gdpr.md)
               + [服务器端转发要求](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-requirements.md)
               + [服务器端转发数据和代码引用](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-reference.md)
               + [如何验证服务器端转发的实施情况](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-verify.md)
               + [服务器端转发常见问题解答](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-faq.md)
         + 流量 {#traffic-variables}
            + [流量变量](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md)
            + [启用流量变量报告](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/t-traffic-variable.md)
            + [流量分类](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-classifications.md)
            + [自定义报告描述](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/custom-desc-admin.md)
         + 转化 {#conversion-variables}
            + [转化变量](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md)
            + [查找方法](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/finding-methods.md)
            + [转化分类](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-classifications.md)
            + 独特访客变量 {#unique-visitor-variable}
               + [指定独特访客变量](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/unique-visitor-variable-admin/t-unique-visitor-variable.md)
               + [用例 — 提取访客 ID](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/unique-visitor-variable-admin/extract-visitorids-usecase.md)
            + 成功事件 {#success-events}
               + [成功事件概述](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md)
               + [配置成功事件](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/t-success-events.md)
               + [关于更改事件类型](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/event-type.md)
            + [分类层次结构](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/classification-hierarchies.md)
            + [列表变量](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md)
            + [促销 eVar](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/merchandising-evars.md)
         + 营销渠道 {#marketing-channels}
            + [管理营销渠道](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-channels.md)
            + [营销渠道的处理规则](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md)
            + [营销渠道中的分类](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/classifications-mchannel.md)
            + [营销渠道到期](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/visitor-engagement.md)
         + 流量管理 {#traffic-management}
            + [概述](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/traffic-management.md)
            + [计划尖峰](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-schedule-spike.md)
            + [永久性流量](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-permanent.md)
         + [默认指标](admin/c-manage-report-suites/c-edit-report-suites/default-metrics.md)
         + [应用程序管理](admin/c-manage-report-suites/c-edit-report-suites/mobile-management.md)
         + [媒体管理](admin/c-manage-report-suites/c-edit-report-suites/media-management.md)
         + [Activity Map](admin/c-manage-report-suites/c-edit-report-suites/activity-map.md)
         + [AEM](admin/c-manage-report-suites/c-edit-report-suites/adobe-experience-manager.md)
         + [Adobe Campaign](admin/c-manage-report-suites/c-edit-report-suites/adobe-campaign.md)
         + [隐私报告](admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md)
         + 实时 {#real-time-reports}
            + [实时报告概述](admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md)
            + [实时报告配置](admin/c-manage-report-suites/c-edit-report-suites/realtime/t-realtime-admin.md)
            + [受支持的实时指标和维度](admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime-metrics.md)
      + [管理报告包](admin/c-manage-report-suites/report-suites-admin.md)
      + [汇总报告包和全局报告包](admin/c-manage-report-suites/rollup-report-suite.md)
      + [保存报告包搜索](admin/c-manage-report-suites/t-report-suite-saved-search.md)
      + [下载报告包设置](admin/c-manage-report-suites/t-download-rs-settings.md)
      + 新的报告包 {#c-new-report-suite}
         + [创建报告包](admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md)
         + [创建汇总报告包](admin/c-manage-report-suites/c-new-report-suite/t-rollups.md)
         + [创建报告包群组](admin/c-manage-report-suites/c-new-report-suite/t-create-rs-group.md)
         + [新报告包 — 设置](admin/c-manage-report-suites/c-new-report-suite/new-report-suite.md)
         + [未从源报告包复制的设置](admin/c-manage-report-suites/c-new-report-suite/settings-not-copied-from-rs.md)
      + 报告包模板 {#report-suite-templates}
         + [报告包模板概述](admin/c-manage-report-suites/c-report-suite-templates/report-suite-templates.md)
         + [内容聚合门户](admin/c-manage-report-suites/c-report-suite-templates/aggregator-portal.md)
         + [商务](admin/c-manage-report-suites/c-report-suite-templates/commerce-admin.md)
         + [内容和媒体](admin/c-manage-report-suites/c-report-suite-templates/content-media.md)
         + [默认模板](admin/c-manage-report-suites/c-report-suite-templates/default-rs-template.md)
         + [金融服务](admin/c-manage-report-suites/c-report-suite-templates/financial-services.md)
         + [求职门户](admin/c-manage-report-suites/c-report-suite-templates/job-portal.md)
         + [商机开发](admin/c-manage-report-suites/c-report-suite-templates/lead-generation.md)
         + [支持媒体](admin/c-manage-report-suites/c-report-suite-templates/support-media.md)
   + 公司设置 {#company-settings}
      + [公司设置概述](admin/company/c-company-settings.md)
      + [安全管理器](admin/company/security-manager.md)
      + [Web 服务](admin/company/web-services-admin.md)
      + [Report Builder 报告](admin/company/report-builder-reports-admin.md)
      + [单点登录](admin/company/single-signon-admin.md)
      + [品牌联合](admin/company/co-branding-admin.md)
      + [隐藏报告包](admin/company/c-hide-report-suites.md)
      + [首选项管理器](admin/company/preferences-manager.md)
      + [待定操作](admin/company/pending-actions-admin.md)
      + [功能访问级别](admin/company/feature-access-levels.md)
   + 服务器调用使用情况 {#server-call-usage}
      + [服务器调用使用情况概述](admin/c-server-call-usage/overage-overview.md)
      + [查看当前的服务器调用使用情况](admin/c-server-call-usage/server-call-usage-dashboard.md)
      + [查看报告包使用情况](admin/c-server-call-usage/report-suite-usage.md)
      + [服务器调用使用情况警报](admin/c-server-call-usage/scu-alerts.md)
      + [服务器调用使用情况常见问题解答](admin/c-server-call-usage/overage-faq.md)
   + 用户和产品管理（旧版）{#user-product-management}
      + [用户和产品管理（旧版）](admin/user-management2/user-management.md)
      + 将用户迁移到 Adobe Admin Console {#migrate-users}
         + [将 Analytics 用户迁移到 Admin Console](admin/user-management2/user-migration/c-migration-tool.md)
         + [为 Adobe ID 迁移 Analytics 用户帐户](admin/user-management2/user-migration/t-migrate-users.md)
         + [迁移 Analytics 用户帐户以使用 Enterprise ID 和 Federated ID](admin/user-management2/user-migration/migrate-enterprise.md)
         + [禁用旧版登录](admin/user-management2/user-migration/t-disable-legacy-login.md)
         + [受迁移影响的 API](admin/user-management2/user-migration/developer.md)
+ [管理员 API](c-admin-api/c-admin-api.md)

