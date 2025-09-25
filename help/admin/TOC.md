---
product: analytics
audience: admin
user-guide-title: Analytics 管理员指南
breadcrumb-title: 管理指南
user-guide-description: 了解 Analytics administration 任务，如在 Experience Cloud Admin Console 中管理用户和产品、配置报告包等等。
source-git-commit: 35675c2e65456a175d1516dd421b80d2af809286
workflow-type: ht
source-wordcount: '496'
ht-degree: 100%

---


# Adobe Analytics 管理员指南 {#admin}

+ [Analytics 管理员指南](home.md)
+ [Analytics 发行说明](https://experienceleague.adobe.com/zh-hans/docs/analytics/release-notes/latest)
+ Adobe Admin Console {#admin-console}
   + [概述](admin-console/home.md)
   + [Adobe Analytics 管理入门指南](admin-console/first-admin-guide.md)
   + [Adobe Analytics 中的管理员角色](admin-console/admin-roles-in-analytics.md)
   + Analytics 工具权限摘要 {#permissions}
      + [Adobe Analytics 的产品配置文件](admin-console/permissions/product-profile.md)
      + [“报告包工具”的产品配置文件权限](admin-console/permissions/report-suite-tools.md)
      + [Analytics 工具的产品配置文件权限](admin-console/permissions/analytics-tools.md)
+ Analytics 管理员工具 {#admin-tools}
   + [管理员工具概述](tools/c-admin-tools.md)
   + [代码管理器](tools/code-manager-admin.md)
   + [分析库存](tools/analytics-inventory.md)
   + [数据源](tools/data-sources.md)
   + [按 IP 地址排除](tools/exclude-ip.md)
   + [日志](tools/logs.md)
   + 报告活动管理器 {#reporting-activity-manager}
      + [概述](tools/reporting-activity-manager/reporting-activity-overview.md)
      + [查看报告活动](tools//reporting-activity-manager/reporting-activity.md)
      + [取消报告请求](tools/reporting-activity-manager/reporting-activity-cancel-requests.md)
   + 组件迁移 {#component-migration}
      + [准备迁移](tools/component-migration/prepare-component-migration.md)
      + [迁移工作流](tools/component-migration/component-migration.md)
   + 报告包管理器 {#manage-report-suites}
      + 编辑报告包设置 {#edit-report-suite}
         + 常规 {#report-suite-general}
            + [一般帐户设置](tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)
            + [内部 URL 过滤器](tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)
            + [自定义日程表](tools/manage-rs/edit-settings/general/custom-calendar.md)
            + 付费搜索检测 {#paid-search-detection}
               + [付费搜索检测概述](tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md)
               + [配置付费搜索检测](tools/manage-rs/edit-settings/general/paid-search-detection/t-paid-search-detection.md)
            + 处理规则 {#processing-rules}
               + [概述](tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)
               + [界面](tools/manage-rs/edit-settings/general/processing-rules/pr-interface.md)
               + [查看历史记录](tools/manage-rs/edit-settings/general/processing-rules/pr-view-history.md)
               + [复制规则](tools/manage-rs/edit-settings/general/processing-rules/pr-copy.md)
               + [可用量度和维度](tools/manage-rs/edit-settings/general/processing-rules/pr-variables.md)
               + [用例](tools/manage-rs/edit-settings/general/processing-rules/pr-use-cases.md)
            + 机器人规则 {#bot-removal}
               + [删除机器人](tools/manage-rs/edit-settings/general/bot-removal/bot-removal.md)
               + [了解和配置机器人规则](tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md)
               + [常见的机器人签名](tools/manage-rs/edit-settings/general/bot-removal/bot-signatures.md)
               + [机器人排除法](tools/manage-rs/edit-settings/general/bot-removal/bot-exclusion-methods.md)
            + [隐私设置](tools/manage-rs/edit-settings/general/privacy-settings.md)
            + [时间戳配置](tools/manage-rs/edit-settings/general/timestamp-configuration.md)
            + 服务器端转发 {#server-side-forwarding}
               + [服务器端转发概述](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md)
               + [GDPR/ePrivacy 合规和服务器端转发](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-gdpr.md)
               + [服务器端转发要求](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-requirements.md)
               + [服务器端转发数据和代码引用](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-reference.md)
               + [如何验证服务器端转发的实施情况](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-verify.md)
               + [服务器端转发常见问题解答](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-faq.md)
         + 流量 {#traffic-variables}
            + [流量变量](tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md)
            + [流量分类](tools/manage-rs/edit-settings/c-traffic-variables/traffic-classifications.md)
            + [自定义报告描述](tools/manage-rs/edit-settings/c-traffic-variables/custom-desc-admin.md)
         + 转化 {#conversion-variables}
            + [转化变量](tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md)
            + [查找方法](tools/manage-rs/edit-settings/conversion-var-admin/finding-methods.md)
            + [转化分类](tools/manage-rs/edit-settings/conversion-var-admin/conversion-classifications.md)
            + 独特访客变量 {#unique-visitor-variable}
               + [指定独特访客变量](tools/manage-rs/edit-settings/conversion-var-admin/unique-visitor-variable-admin/t-unique-visitor-variable.md)
               + [用例 — 提取访客 ID](tools/manage-rs/edit-settings/conversion-var-admin/unique-visitor-variable-admin/extract-visitorids-usecase.md)
            + [成功事件](tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/success-event.md)
            + [分类层次结构](tools/manage-rs/edit-settings/conversion-var-admin/classification-hierarchies.md)
            + [列表变量](tools/manage-rs/edit-settings/conversion-var-admin/list-var-admin.md)
            + [促销 eVar](tools/manage-rs/edit-settings/conversion-var-admin/merchandising-evars.md)
         + 营销渠道 {#marketing-channels}
            + [营销渠道管理器](tools/manage-rs/edit-settings/marketing-channels/c-channels.md)
            + [营销渠道处理规则](tools/manage-rs/edit-settings/marketing-channels/c-rules.md)
            + [营销渠道分类](tools/manage-rs/edit-settings/marketing-channels/classifications-mchannel.md)
            + [营销渠道有效期限](tools/manage-rs/edit-settings/marketing-channels/visitor-engagement.md)
         + 流量管理 {#traffic-management}
            + [概述](tools/manage-rs/edit-settings/c-traffic-management/traffic-management.md)
            + [计划尖峰](tools/manage-rs/edit-settings/c-traffic-management/t-traffic-schedule-spike.md)
            + [永久性流量](tools/manage-rs/edit-settings/c-traffic-management/t-traffic-permanent.md)
         + [默认量度](tools/manage-rs/edit-settings/default-metrics.md)
         + 应用程序管理 {#app-management}
            + [应用程序报告](tools/manage-rs/edit-settings/app-reporting.md)
            + [应用程序分类](tools/manage-rs/edit-settings/app-classifications.md)
         + [媒体管理](tools/manage-rs/edit-settings/media-management.md)
         + [Activity Map](tools/manage-rs/edit-settings/activity-map.md)
         + [AEM](tools/manage-rs/edit-settings/adobe-experience-manager.md)
         + [Adobe Campaign](tools/manage-rs/edit-settings/adobe-campaign.md)
         + [隐私报告](tools/manage-rs/edit-settings/privacy-reporting.md)
         + Document Cloud 管理 {#doc-cloud-mgt}
            + [使用 Adobe Analytics 配置 Document Cloud](tools/manage-rs/edit-settings/document-cloud-mgt.md)
            + [配置 Document Cloud 报告](tools/manage-rs/edit-settings/document-cloud-config.md)
         + [Advertising Analytics 配置](tools/manage-rs/edit-settings/advertising-analytics-config.md)
         + 实时 {#real-time-reports}
            + [实时报告概述](tools/manage-rs/edit-settings/realtime/realtime.md)
            + [实时报告配置](tools/manage-rs/edit-settings/realtime/t-realtime-admin.md)
            + [受支持的实时量度和维度](tools/manage-rs/edit-settings/realtime/realtime-metrics.md)
      + [管理报告包](tools/manage-rs/report-suites-admin.md)
      + [全局报告包](tools/manage-rs/rollup-report-suite.md)
      + [保存报告包搜索](tools/manage-rs/t-report-suite-saved-search.md)
      + [下载报告包设置](tools/manage-rs/t-download-rs-settings.md)
      + 新的报告包 {#c-new-report-suite}
         + [创建报告包](tools/manage-rs/new-rs/t-create-a-report-suite.md)
         + [创建报告包群组](tools/manage-rs/new-rs/t-create-rs-group.md)
         + [新报告包 — 设置](tools/manage-rs/new-rs/new-report-suite.md)
         + [未从源报告包复制的设置](tools/manage-rs/new-rs/settings-not-copied-from-rs.md)
      + 报告包模板 {#report-suite-templates}
         + [报告包模板概述](tools/manage-rs/rs-templates/report-suite-templates.md)
         + [内容聚合门户](tools/manage-rs/rs-templates/aggregator-portal.md)
         + [商务](tools/manage-rs/rs-templates/commerce-admin.md)
         + [内容和媒体](tools/manage-rs/rs-templates/content-media.md)
         + [默认模板](tools/manage-rs/rs-templates/default-rs-template.md)
         + [金融服务](tools/manage-rs/rs-templates/financial-services.md)
         + [求职门户](tools/manage-rs/rs-templates/job-portal.md)
         + [商机开发](tools/manage-rs/rs-templates/lead-generation.md)
         + [支持媒体](tools/manage-rs/rs-templates/support-media.md)
   + 公司设置 {#company-settings}
      + [公司设置概述](tools/company/c-company-settings.md)
      + [安全管理器](tools/company/security-manager.md)
      + [Web 服务](tools/company/web-services-admin.md)
      + [Report Builder 报告](tools/company/report-builder-reports-admin.md)
      + [单点登录](tools/company/single-signon-admin.md)
      + [隐藏报告包](tools/company/c-hide-report-suites.md)
      + [首选项管理器](tools/company/preferences-manager.md)
      + [待定操作](tools/company/pending-actions-admin.md)
      + [功能访问级别](tools/company/feature-access-levels.md)
   + 隐私标签 {#privacy-labeling}
      + [概述](tools/privacy-labeling/labeling-overview.md)
      + [Analytics 组件的数据隐私标签](tools/privacy-labeling/labels.md)
      + [查看/管理报告包的隐私标签](tools/privacy-labeling/view-settings.md)
      + [标签设置最佳实践](tools/privacy-labeling/best-practices.md)
      + [标签设置示例](tools/privacy-labeling/examples.md)
      + [命名空间](tools/privacy-labeling/namespaces.md)
   + 服务器调用使用情况 {#server-call-usage}
      + [服务器调用使用情况概述](tools/server-call-usage/overage-overview.md)
      + [查看当前的服务器调用使用情况](tools/server-call-usage/server-call-usage-dashboard.md)
      + [查看报告包使用情况](tools/server-call-usage/report-suite-usage.md)
      + [服务器调用使用情况警报](tools/server-call-usage/scu-alerts.md)
      + [服务器调用使用情况常见问题解答](tools/server-call-usage/overage-faq.md)
   + 用户和产品管理（旧版） {#user-product-management}
      + [用户和产品管理（旧版）](tools/user-management/user-management.md)
      + [管理旧版用户帐户、资源和有效期限](tools/user-management/users-assets.md)
      + 将用户迁移到 Adobe Admin Console {#migrate-users}
         + [将 Analytics 用户迁移到 Admin Console](tools/user-management/user-migration/c-migration-tool.md)
         + [为 Adobe ID 迁移 Analytics 用户帐户](tools/user-management/user-migration/t-migrate-users.md)
         + [迁移 Analytics 用户帐户以使用 Enterprise ID 和 Federated ID](tools/user-management/user-migration/migrate-enterprise.md)
         + [禁用旧版登录](tools/user-management/user-migration/t-disable-legacy-login.md)
         + [受迁移影响的 API](tools/user-management/user-migration/developer.md)
+ [管理员 API](c-admin-api/c-admin-api.md)
+ [Adobe Analytics 1.4 API EOL FAQ](c-admin-api/c-admin-14-api-eol.md)

