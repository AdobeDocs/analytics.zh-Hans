---
title: 设置Report Builder
description: 了解安装和配置Adobe Analytics Report Builder for Excel的完整指南。 用于无缝集成的分步设置说明。
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 9d0161a9-ee7b-43a9-92ad-4079cf4b9c6c
source-git-commit: 1e893ce94ee3da46bbf22d7a90573681950d1135
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 39%

---

# 设置Report Builder

本文概述在[!DNL Microsoft] [!DNL Excel]中为Adobe Analytics使用Report Builder的要求。 以及如何安装和设置加载项。

## 要求

以下操作系统和Web浏览器支持适用于Adobe Analytics的Report Builder。

### macOS

- macOS 版本 10.x 或更高版本
- 所有[!DNL Microsoft] [!DNL Excel]版本

### Windows

- Windows 10，版本 1904 或更高版本
- [!DNL Excel]版本2106或更高版本

  所有Windows桌面[!DNL Excel]用户都必须安装Microsoft Edge Webview2才能使用此加载项。 安装控制器：

   1. 转到 <https://aka.ms/webview2installer>。
   1. 选择并下载 Evergreen 独立安装程序。
   1. 按照安装提示操作。

### Web Office

- 支持所有浏览器和版本


## Report Builder Excel 插件

您必须安装Report Builder [!DNL Excel]加载项才能将[!DNL Report Builder]用于Adobe Analytics。 安装Report Builder [!DNL Excel]加载项后，您可以从打开的[!DNL Excel]工作簿中访问Report Builder。

### 下载并安装 Report Builder 插件

下载并安装 Report Builder 插件

1. 启动[!DNL Excel]并打开新工作簿。

1. 选择&#x200B;**[!UICONTROL 插入]** > **[!UICONTROL 获取加载项]**。

1. 在“Office 插件”对话框中，选择“Store”选项卡。

1. 搜索“Report Builder”并单击&#x200B;**[!UICONTROL 添加]**。

1. 在“许可条款和隐私策略”对话框中，单击&#x200B;**[!UICONTROL 继续]**。

**如果“Store”选项卡未显示**

1. 在[!DNL Excel]中，选择“文件”>“帐户”>“管理设置”。

1. 选中“启用可选连接体验”旁边的框。

1. 重新启动[!DNL Excel]。

**如果组织阻止了对 Microsoft Store 的访问**

- 联系 IT 或安全团队，请求批准使用 Report Builder 插件。获得批准后，在“Office加载项”对话框中，选择&#x200B;**[!UICONTROL 管理员托管]**&#x200B;选项卡。

  ![Office加载项对话框中的管理员管理选项卡。](./assets/image1.png)

- 或者，您可以手动检索[清单文件](https://reportbuilder.an.adobe.com/manifest.xml)，并将该文件托管在您自己的IT基础架构上。 <br/>有关如何安装未从Microsoft应用商店提供的Microsoft清单文件的说明，请参阅Office [联机文档](https://learn.microsoft.com/en-us/office/dev/add-ins/publish/publish)。

安装Report Builder插件后，“主页”选项卡下的[!DNL Excel]功能区中会显示Report Builder图标。

![Excel中的Report Builder图标](/help/analyze/report-builder/assets/rb_app_icon.png)

## 登录 Report Builder

为操作平台或浏览器安装了Report Builder for Excel插件后，请按照以下步骤登录Report Builder。

1. 打开 Excel 工作簿。

1. 单击 Report Builder 图标以启动 Report Builder。

1. 在Adobe Report Builder工具栏中，单击&#x200B;**[!UICONTROL 登录]**。

   ![单击“Report Builder登录”按钮。](/help/analyze/report-builder/assets/rb_login.png)

1. 输入您的 Adobe Experience ID 帐户信息。您的帐户信息应该与您的Adobe Analytics凭据匹配。

   ![您的登录图标和组织。](/help/analyze/report-builder/assets/image4.png)

登录后，您的登录图标和组织将显示在面板顶部

## 切换组织

首次登录时，您会登录到分配给您的轮廓的默认组织。

1. 单击在您登录时显示的组织的名称。

1. 从可用组织列表中选择组织。只列出您有访问权限的组织。

   ![您可以访问的组织列表。](/help/analyze/report-builder/assets/image5.png)

## 注销

您可从 Report Builder 的用户轮廓中注销。

1. 保存对任何打开工作簿的更改。

1. 单击头像图标以显示您的用户轮廓。

   ![您的用户个人资料头像和“注销”按钮。](/help/analyze/report-builder/assets/image6.png)

1. 单击&#x200B;**注销**。
