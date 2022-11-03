---
product: analytics
audience: admin
user-guide-title: Analytics 管理员指南
breadcrumb-title: 管理指南
user-guide-description: 了解 Analytics administration 任务，如在 Experience Cloud Admin Console 中管理用户和产品、配置报表包等等。
source-git-commit: bc8f87c42ca481382b603413088faa9a71ab01f1
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 100%

---


# Adobe Analytics 管理员指南 {#admin}

+ [Analytics 管理员指南](home.md)
+ [Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hans)
+ Analytics 管理概述{#admin-overview}
   + [我应该使用哪种 Adobe Analytics 工具？](c-analytics-product-comparison/which-analytics-tool.md)
   + [Analytics 产品比较和要求](c-analytics-product-comparison/analytics-product-comparison.md)
+ [系统要求](sys-reqs.md)
+ 管理工具{#admin-tools}
   + [管理工具](admin/c-admin-tools.md)
   + [计费](admin/billing-admin.md)
   + 机器人移除{#bot-removal}
      + [机器人移除](admin/bot-removal/bot-removal.md)
      + [机器人规则概述](admin/bot-removal/bot-rules.md)
      + [常见的机器人签名](admin/bot-removal/bot-signatures.md)
      + [机器人排除法](admin/bot-removal/bot-exclusion-methods.md)
   + [代码管理器](admin/code-manager-admin.md)
   + 转化变量{#conversion-variables}
      + [转化变量 (eVar)](admin/conversion-var-admin/conversion-var-admin.md)
      + [编辑转化变量](admin/conversion-var-admin/t-conversion-variables-admin.md)
      + [转化分类](admin/conversion-var-admin/conversion-classifications.md)
      + [分类层次结构](admin/conversion-var-admin/classification-hierarchies.md)
      + [列表变量](admin/conversion-var-admin/list-var-admin.md)
      + [促销 eVar](admin/conversion-var-admin/merchandising-evars.md)
   + [货币代码](admin/currency.md)
   + [自定义报表描述](admin/custom-desc-admin.md)
   + [自定义日历](admin/custom-calendar.md)
   + [数据源](admin/data-sources.md)
   + [默认指标](admin/default-metrics.md)
   + [按 IP 地址排除](admin/exclude-ip.md)
   + [查找方法](admin/finding-methods.md)
   + [一般帐户设置](admin/general-acct-settings-admin.md)
   + [内部 URL 过滤器](admin/internal-url-filter-admin.md)
   + [日志](admin/logs.md)
   + [营销渠道](admin/marketing-channels-admin.md)
   + [菜单自定义](admin/customize-menus.md)
   + [指标可见性](admin/metric-visibility.md)
   + [应用程序管理](admin/mobile-management.md)
   + 付费搜索检测{#paid-search-detection}
      + [付费搜索检测概述](admin/paid-search-detection/paid-search-detection.md)
      + [配置付费搜索检测](admin/paid-search-detection/t-paid-search-detection.md)
   + [发布列表](admin/publishing-list.md)
   + [发布构件](admin/publishing-widgets-admin.md)
   + [首选项管理器](admin/preferences-manager.md)
   + [隐私设置](admin/privacy-settings.md)
   + [隐私报表](admin/privacy-reporting.md)
   + 处理规则{#processing-rules}
      + [处理规则概述](admin/c-processing-rules/processing-rules.md)
      + 处理规则配置{#processing-rules-configuration}
         + [处理规则的工作原理](admin/c-processing-rules/c-processing-rules-configuration/processing-rules-about.md)
         + [创建处理规则](admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md)
         + [查看活动处理规则](admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules-view.md)
         + [查看处理规则历史记录](admin/c-processing-rules/c-processing-rules-configuration/t-processing-rule-view-history.md)
         + [还原处理规则](admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules-restore.md)
         + [将处理规则复制到其他报表包](admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules-copy-to-rs.md)
      + [可用于处理规则的维度](admin/c-processing-rules/processing-rule-dimensions.md)
      + 处理规则示例{#processing-rules-examples}
         + [处理规则的示例](admin/c-processing-rules/processing-rules-examples/processing-rules-examples.md)
         + [通过查询字符串参数填充促销活动 ID](admin/c-processing-rules/processing-rules-examples/processing-rules-populate-campaign-id.md)
         + [在产品概述页面中设置产品视图事件](admin/c-processing-rules/processing-rules-examples/setting-the-product-view-event.md)
         + [通过连接类别和页面名称添加子类别](admin/c-processing-rules/processing-rules-examples/subcategory-concatenating.md)
         + [通过将 eVar 值复制到 prop 来确定路径](admin/c-processing-rules/processing-rules-examples/processing-rules-determining-path.md)
         + [清理报告中的值](admin/c-processing-rules/processing-rules-examples/clean-up-values-in-a-report.md)
         + [使用查询字符串参数填充内部搜索词](admin/c-processing-rules/processing-rules-examples/processing-rules-populating-internal-search.md)
         + [将上下文数据变量复制到 eVar](admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md)
         + [使用上下文数据变量设置事件](admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md)
         + [通过点击删除事件](admin/c-processing-rules/processing-rules-examples/processing-rules-remove-event.md)
      + [处理规则的提示和技巧](admin/c-processing-rules/processing-rules-tips.md)
   + 实时报表 {#real-time-reports}
      + [实时报表概述](admin/realtime/realtime.md)
      + [实时报表配置](admin/realtime/t-realtime-admin.md)
      + [受支持的实时指标和维度](admin/realtime/realtime-metrics.md)
   + [报表活动管理器](admin/reporting-activity.md)
   + [已安排的报表队列](admin/scheduled-reports-admin.md)
   + 服务器端转发 {#server-side-forwarding}
      + [服务器端转发概述](admin/c-server-side-forwarding/ssf.md)
      + [GDPR/ePrivacy 合规和服务器端转发](admin/c-server-side-forwarding/ssf-gdpr.md)
      + [服务器端转发要求](admin/c-server-side-forwarding/ssf-requirements.md)
      + [服务器端转发数据和代码引用](admin/c-server-side-forwarding/ssf-reference.md)
      + [如何验证服务器端转发的实施情况](admin/c-server-side-forwarding/ssf-verify.md)
      + [服务器端转发常见问题解答](admin/c-server-side-forwarding/ssf-faq.md)
   + [简化的报表菜单](admin/t-simplified-menu.md)
   + [社交管理](admin/social-management.md)
   + 成功事件 {#success-events}
      + [成功事件概述](admin/c-success-events/success-event.md)
      + [配置成功事件](admin/c-success-events/t-success-events.md)
      + [关于更改事件类型](admin/c-success-events/event-type.md)
   + [可选时间戳](admin/timestamp-optional.md)
   + 流量变量 {#traffic-variables}
      + [流量变量 (prop) 概述](admin/c-traffic-variables/traffic-var.md)
      + [启用流量变量报表](admin/c-traffic-variables/t-traffic-variable.md)
      + [流量分类](admin/c-traffic-variables/traffic-classifications.md)
   + 独特访客变量 {#unique-visitor-variable}
      + [指定独特访客变量](admin/unique-visitor-variable-admin/t-unique-visitor-variable.md)
      + [用例 — 提取访客 ID](admin/unique-visitor-variable-admin/extract-visitorids-usecase.md)
   + [视频管理](admin/video-management.md)
+ Adobe Admin Console 中的 Analytics {#admin-console}
   + [Adobe Admin Console 中的 Analytics](admin-console/home.md)
   + 权限 {#permissions}
      + [Admin Console 中的 Analytics Permissions](admin-console/permissions/summary-tables.md)
      + [Adobe Analytics 的产品配置文件](admin-console/permissions/product-profile.md)
      + [“报表包工具”的产品配置文件权限](admin-console/permissions/report-suite-tools.md)
      + [Analytics 工具的产品配置文件权限](admin-console/permissions/analytics-tools.md)
   + [Adobe Analytics 管理入门指南](admin-console/first-admin-guide.md)
+ 公司设置 {#company-settings}
   + [公司设置概述](company/c-company-settings.md)
   + [功能访问级别](company/feature-access-levels.md)
   + [Web 服务](company/web-services-admin.md)
   + [Report Builder 报表](company/report-builder-reports-admin.md)
   + [单点登录](company/single-signon-admin.md)
   + [待定操作](company/pending-actions-admin.md)
   + [品牌联合](company/co-branding-admin.md)
   + [隐藏报表包](company/c-hide-report-suites.md)
   + [安全管理器](company/security-manager.md)
+ 管理报表包 {#manage-report-suites}
   + [报表包管理器](c-manage-report-suites/report-suites-admin.md)
   + [汇总报表包和全局报表包](c-manage-report-suites/rollup-report-suite.md)
   + [创建汇总报表包](c-manage-report-suites/t-rollups.md)
   + 报表包模板 {#report-suite-templates}
      + [报表包模板概述](c-manage-report-suites/c-report-suite-templates/report-suite-templates.md)
      + [内容聚合门户](c-manage-report-suites/c-report-suite-templates/aggregator-portal.md)
      + [商务](c-manage-report-suites/c-report-suite-templates/commerce-admin.md)
      + [内容和媒体](c-manage-report-suites/c-report-suite-templates/content-media.md)
      + [默认模板](c-manage-report-suites/c-report-suite-templates/default-rs-template.md)
      + [金融服务](c-manage-report-suites/c-report-suite-templates/financial-services.md)
      + [求职门户](c-manage-report-suites/c-report-suite-templates/job-portal.md)
      + [商机开发](c-manage-report-suites/c-report-suite-templates/lead-generation.md)
      + [支持媒体](c-manage-report-suites/c-report-suite-templates/support-media.md)
   + [保存报表包搜索](c-manage-report-suites/t-report-suite-saved-search.md)
   + [单个报表包设置](c-manage-report-suites/individual-rs-settings.md)
   + [下载报表包设置](c-manage-report-suites/t-download-rs-settings.md)
   + 新的报表包 {#new-report-suite}
      + [创建报表包](c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md)
      + [新报表包 — 设置](c-manage-report-suites/c-new-report-suite/new-report-suite.md)
      + [未从源报表包复制的设置](c-manage-report-suites/c-new-report-suite/settings-not-copied-from-rs.md)
   + [创建报表包群组](c-manage-report-suites/t-create-rs-group.md)
+ 用户和产品管理（旧版）{#user-product-management}
   + [用户和产品管理](user-management2/user-management.md)
   + 将用户迁移到 Adobe Admin Console {#migrate-users}
      + [将 Analytics 用户迁移到 Admin Console](user-management2/user-migration/c-migration-tool.md)
      + [为 Adobe ID 迁移 Analytics 用户帐户](user-management2/user-migration/t-migrate-users.md)
      + [迁移 Analytics 用户帐户以使用 Enterprise ID 和 Federated ID](user-management2/user-migration/migrate-enterprise.md)
      + [禁用旧版登录](user-management2/user-migration/t-disable-legacy-login.md)
      + [受迁移影响的 API](user-management2/user-migration/developer.md)
+ 数据管理 {#data-governance}
   + [Adobe Analytics 和 GDPR](c-data-governance/an-gdpr-overview.md)
   + [Adobe Analytics 和 CCPA](c-data-governance/an-ccpa-overview.md)
   + [CNIL 准许豁免](c-data-governance/cnil-consent-exemption.md)
   + [常见问题解答](c-data-governance/gdpr-faq.md)
   + [Adobe Analytics 数据隐私工作流程](c-data-governance/an-gdpr-workflow.md)
   + [查看/管理报表包的数据管理设置](c-data-governance/gdpr-view-settings.md)
   + [为报表包数据设置标签](c-data-governance/gdpr-setup-reportsuite.md)
   + [提交访问和删除请求](c-data-governance/gdpr-submit-access-delete.md)
   + [Analytics 变量的数据隐私标签](c-data-governance/gdpr-labels.md)
   + [命名空间](c-data-governance/gdpr-namespaces.md)
   + [ID 扩展](c-data-governance/gdpr-id-expansion.md)
   + [标签设置最佳实践](c-data-governance/gdpr-analytics-ids.md)
   + [标签设置示例](c-data-governance/gdpr-labeling-example.md)
   + [数据隐私和数据连接器 (Genesis)](c-data-governance/data-connectors-gdpr.md)
   + [数据隐私术语](c-data-governance/gdpr-terminology.md)
+ 服务器调用使用情况 {#server-call-usage}
   + [服务器调用使用情况概述](c-server-call-usage/overage-overview.md)
   + [查看当前的服务器调用使用情况](c-server-call-usage/server-call-usage-dashboard.md)
   + [查看报表包使用情况](c-server-call-usage/report-suite-usage.md)
   + [服务器调用使用情况警报](c-server-call-usage/scu-alerts.md)
   + [服务器调用使用情况常见问题解答](c-server-call-usage/overage-faq.md)
+ 流量管理{#traffic-management}
   + [管理流量](c-traffic-management/traffic-management.md)
   + [安排流量尖峰](c-traffic-management/t-traffic-schedule-spike.md)
   + [评估过去的服务器调用并安排流量尖峰](c-traffic-management/traffic-spike-estimate-past-server-calls.md)
   + [指定永久性流量增长](c-traffic-management/t-traffic-permanent.md)
   + [流量增长必需的前置时间](c-traffic-management/traffic-lead-time.md)
+ [管理员 API](c-admin-api/c-admin-api.md)
