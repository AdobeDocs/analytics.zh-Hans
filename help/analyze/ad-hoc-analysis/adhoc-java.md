---
description: 有关如何使用Java11运行Ad Hoc Analysis的说明。
seo-description: 有关如何使用Java11运行Ad Hoc Analysis的说明。
seo-title: Ad Hoc Analysis和Java11
title: 使用Java11运行临时分析
translation-type: tm+mt
source-git-commit: 23bdb0c24416c376ec1df7b609a5794dbf8886f2

---


# 使用Java11运行临时分析

与在 Java 8 上运行 Ad Hoc Analysis 相比，在 Java 11 上运行 Ad Hoc Analysis 时需要遵循一些额外的步骤。

## 先决条件

与您的 IT 团队合作，确保满足以下条件：

* Java 11 must be installed, with *JAVA_HOME* environment variable set
* 必须已安装 JavaFX，并将 *PATH_TO_FX_SDK* 环境变量指向 JavaFX SDK 目录。例如，在 Mac 中，*PATH_TO_FX_SDK=/homedir/javafx-sdk-11.0.2*，或者在 PC 中，*PATH_TO_FX_SDK=C:\Users\username\javafx-sdk-11.0.2*。

## 安装适用于 Java 11 的 Ad Hoc Analysis

1. Go to **[!UICONTROL Analytics &gt; Tools &gt; Ad Hoc Analysis]**.
1. Click **[!UICONTROL Ad Hoc Analysis (Java 11)]**. 此时会下载一个 zip 文件。
1. 解压缩已下载的文件。
1. **选择 .bat (PC) 或 .sh (Mac) 文件**。通过查看 Adobe Analytics URL 中“sc”后面的数字，选择相应的数据中心文件。(3= LON，== SIN，5= PNG)如果您使用PC，请通过转到“关于您的PC”验证您运行的是32位还是64位Windows操作系统。然后，选择适当的 .bat 文件。
1. **运行所选文件**。对于 PC：双击 .bat 文件。对于 Mac：右键单击 .sh 文件，然后选择&#x200B;**[!UICONTROL 打开方式 &gt; 其他... &gt; 实用工具 &gt;（启用所有应用程序）&gt; 选择“终端”&gt; 打开]**。
1. 登录到 Ad Hoc Analysis。

>[!Nte]
>
> Federated和Enterprise ID身份验证方法与临时分析的Java11版本不兼容。

## Ad Hoc Analysis (Java 11) 中不支持的功能

Java11版本中存在与临时分析兼容的一些已知限制：

* 不支持 Federated ID 和 Enterprise ID 身份验证方法。
* 不支持 Linux 操作系统。
* When using a Mac, do not use the Mac application menu (including *cmd + Q*). 因为这可能会导致 Ad Hoc Analysis 在没有警告的情况下关闭。请改用 Ad Hoc Analysis 中的菜单。
* 在 MacOS 上运行 Ad Hoc Analysis 时，不支持“网站分析”可视化图表。

## 常见问题解答

**问：我收到“无法找到\ bin\ javaw”错误(以下示例)-我应该做什么？**

![](/help/analyze/ad-hoc-analysis/assets/error-java.png)

答：如果您收到此错误，请与您的 IT 团队一起设置 *JAVA_HOME* 环境变量，该变量是在 Java 11 中运行 Ad Hoc Analysis 所必需的。