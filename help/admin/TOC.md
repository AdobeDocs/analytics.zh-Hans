---
product: analytics
audience: admin
user-guide-title: Analytics 管理员指南
breadcrumb-title: 管理指南
user-guide-description: 了解 Analytics administration 任务，如在 Experience Cloud Admin Console 中管理用户和产品、配置报告包等等。
source-git-commit: 0bed2622f54bf2f46aa57dbfad7bd55a61d6c7d0
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 98%

---


# Adobe Analytics 管理员指南 {#admin}

+ [Analytics 管理员指南](home.md)
+ [Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
+ Adobe Admin Console {#admin-console}
   + [概述](admin-console/home.md)
   + [Adobe Analytics 管理入门指南](admin-console/first-admin-guide.md)
   + [Adobe Analytics 中的管理员角色](admin-console/admin-roles-in-analytics.md)
   + Analytics 工具权限摘要 {#permissions}
      + [Adobe Analytics 的产品配置文件](admin-console/permissions/product-profile.md)
      + [“报告包工具”的产品配置文件权限](admin-console/permissions/report-suite-tools.md)
      + [Analytics 工具的产品配置文件权限](admin-console/permissions/analytics-tools.md)
+ Analytics 管理员工具 {#admin-tools}
   + [管理员工具概述](admin/c-admin-tools.md)
   + [代码管理器](admin/code-manager-admin.md)
   + [分析库存](admin/analytics-inventory.md)
   + [数据源](admin/data-sources.md)
   + [按 IP 地址排除](admin/exclude-ip.md)
   + [日志](admin/logs.md)
   + 报告活动管理器 {#reporting-activity-manager}
      + [概述](admin/reporting-activity-manager/reporting-activity-overview.md)
      + [查看报告活动](admin//reporting-activity-manager/reporting-activity.md)
      + [取消报告请求](admin/reporting-activity-manager/reporting-activity-cancel-requests.md)
   + 组件迁移 {#component-migration}
      + [准备迁移](admin/component-migration/prepare-component-migration.md)
      + [迁移工作流](admin/component-migration/component-migration.md)
   + 报告包管理器 {#manage-report-suites}
      + 编辑报告包设置 {#edit-report-suite}
         + 常规 {#report-suite-general}
            + [一般帐户设置](admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)
            + [内部 URL 过滤器](admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md)
            + [自定义日程表](admin/c-manage-report-suites/c-edit-report-suites/general/custom-calendar.md)
            + 付费搜索检测 {#paid-search-detection}
               + [付费搜索检测概述](admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/paid-search-detection.md)
               + [配置付费搜索检测](admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/t-paid-search-detection.md)
            + 处理规则 {#processing-rules}
               + [概述](admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-overview.md)
               + [界面](admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-interface.md)
               + [查看历史记录](admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-view-history.md)
               + [复制规则](admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-copy.md)
               + [可用的维度和量度](admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-variables.md)
               + [用例](admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-use-cases.md)
            + 机器人规则 {#bot-removal}
               + [删除机器人](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-removal.md)
               + [了解和配置机器人规则](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md)
               + [常见的机器人签名](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-signatures.md)
               + [机器人排除法](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-exclusion-methods.md)
            + [隐私设置](admin/c-manage-report-suites/c-edit-report-suites/general/privacy-settings.md)
            + [时间戳配置](admin/c-manage-report-suites/c-edit-report-suites/general/timestamp-optional.md)
            + 服务器端转发 {#server-side-forwarding}
               + [服务器端转发概述](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf.md)
               + [GDPR/ePrivacy 合规和服务器端转发](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-gdpr.md)
               + [服务器端转发要求](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-requirements.md)
               + [服务器端转发数据和代码引用](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-reference.md)
               + [如何验证服务器端转发的实施情况](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-verify.md)
               + [服务器端转发常见问题解答](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-faq.md)
         + 流量 {#traffic-variables}
            + [流量变量](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md)
            + [流量分类](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-classifications.md)
            + [自定义报告描述](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/custom-desc-admin.md)
         + 转化 {#conversion-variables}
            + [转化变量](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md)
            + [查找方法](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/finding-methods.md)
            + [转化分类](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-classifications.md)
            + 独特访客变量 {#unique-visitor-variable}
               + [指定独特访客变量](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/unique-visitor-variable-admin/t-unique-visitor-variable.md)
               + [用例 — 提取访客 ID](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/unique-visitor-variable-admin/extract-visitorids-usecase.md)
            + [成功事件](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md)
            + [分类层次结构](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/classification-hierarchies.md)
            + [列表变量](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md)
            + [促销 eVar](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/merchandising-evars.md)
         + 营销渠道 {#marketing-channels}
            + [营销渠道管理器](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-channels.md)
            + [营销渠道处理规则](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md)
            + [营销渠道分类](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/classifications-mchannel.md)
            + [营销渠道有效期限](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/visitor-engagement.md)
         + 流量管理 {#traffic-management}
            + [概述](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/traffic-management.md)
            + [计划尖峰](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-schedule-spike.md)
            + [永久性流量](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-permanent.md)
         + [默认量度](admin/c-manage-report-suites/c-edit-report-suites/default-metrics.md)
         + 应用程序管理 {#app-management}
            + [应用程序报告](admin/c-manage-report-suites/c-edit-report-suites/app-reporting.md)
            + [应用程序分类](admin/c-manage-report-suites/c-edit-report-suites/app-classifications.md)
         + [媒体管理](admin/c-manage-report-suites/c-edit-report-suites/media-management.md)
         + [Activity Map](admin/c-manage-report-suites/c-edit-report-suites/activity-map.md)
         + [AEM](admin/c-manage-report-suites/c-edit-report-suites/adobe-experience-manager.md)
         + [Adobe Campaign](admin/c-manage-report-suites/c-edit-report-suites/adobe-campaign.md)
         + [隐私报告](admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md)
         + Document Cloud 管理 {#doc-cloud-mgt}
            + [使用 Adobe Analytics 配置 Document Cloud](admin/c-manage-report-suites/c-edit-report-suites/document-cloud-mgt.md)
            + [配置 Document Cloud 报告](admin/c-manage-report-suites/c-edit-report-suites/document-cloud-config.md)
         + [Advertising Analytics 配置](admin/c-manage-report-suites/c-edit-report-suites/advertising-analytics-config.md)
         + 实时 {#real-time-reports}
            + [实时报告概述](admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md)
            + [实时报告配置](admin/c-manage-report-suites/c-edit-report-suites/realtime/t-realtime-admin.md)
            + [受支持的实时量度和维度](admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime-metrics.md)
      + [管理报告包](admin/c-manage-report-suites/report-suites-admin.md)
      + [全局报告包](admin/c-manage-report-suites/rollup-report-suite.md)
      + [保存报告包搜索](admin/c-manage-report-suites/t-report-suite-saved-search.md)
      + [下载报告包设置](admin/c-manage-report-suites/t-download-rs-settings.md)
      + 新的报告包 {#c-new-report-suite}
         + [创建报告包](admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md)
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
      + [隐藏报告包](admin/company/c-hide-report-suites.md)
      + [首选项管理器](admin/company/preferences-manager.md)
      + [待定操作](admin/company/pending-actions-admin.md)
      + [功能访问级别](admin/company/feature-access-levels.md)
   + 数据治理隐私标签 {#data-governance}
      + [Adobe Analytics 数据隐私工作流程](admin/c-data-governance/an-gdpr-workflow.md)
      + [常见问题解答](admin/c-data-governance/gdpr-faq.md)
      + 数据标签设置 {#data-labels}
         + [Analytics 组件的数据隐私标签](admin/c-data-governance/data-labeling/gdpr-labels.md)
         + [为报告包数据设置标签](admin/c-data-governance/data-labeling/gdpr-setup-reportsuite.md)
         + [查看/管理报告包的隐私标签](admin/c-data-governance/data-labeling/gdpr-view-settings.md)
         + [标签设置最佳实践](admin/c-data-governance/data-labeling/gdpr-analytics-ids.md)
         + [标签设置示例](admin/c-data-governance/data-labeling/gdpr-labeling-example.md)
         + [命名空间](admin/c-data-governance/data-labeling/gdpr-namespaces.md)
      + [CNIL 准许豁免](admin/c-data-governance/cnil-consent-exemption.md)
   + 服务器调用使用情况 {#server-call-usage}
      + [服务器调用使用情况概述](admin/c-server-call-usage/overage-overview.md)
      + [查看当前的服务器调用使用情况](admin/c-server-call-usage/server-call-usage-dashboard.md)
      + [查看报告包使用情况](admin/c-server-call-usage/report-suite-usage.md)
      + [服务器调用使用情况警报](admin/c-server-call-usage/scu-alerts.md)
      + [服务器调用使用情况常见问题解答](admin/c-server-call-usage/overage-faq.md)
   + 用户和产品管理（旧版） {#user-product-management}
      + [用户和产品管理（旧版）](admin/user-management2/user-management.md)
      + [管理旧版用户帐户、资源和有效期限](admin/user-management2/users-assets.md)
      + 将用户迁移到 Adobe Admin Console {#migrate-users}
         + [将 Analytics 用户迁移到 Admin Console](admin/user-management2/user-migration/c-migration-tool.md)
         + [为 Adobe ID 迁移 Analytics 用户帐户](admin/user-management2/user-migration/t-migrate-users.md)
         + [迁移 Analytics 用户帐户以使用 Enterprise ID 和 Federated ID](admin/user-management2/user-migration/migrate-enterprise.md)
         + [禁用旧版登录](admin/user-management2/user-migration/t-disable-legacy-login.md)
         + [受迁移影响的 API](admin/user-management2/user-migration/developer.md)
+ [管理员 API](c-admin-api/c-admin-api.md)
+ [Adobe Analytics 1.4 API EOL FAQ](c-admin-api/c-admin-14-api-eol.md)

