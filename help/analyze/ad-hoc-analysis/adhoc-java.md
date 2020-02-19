---
description: 关于如何使用 Java 11 运行 Ad Hoc Analysis 的说明。
title: 使用 Java 11 运行 Ad Hoc Analysis
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 使用 Java 11 运行 Ad Hoc Analysis

与在 Java 8 上运行 Ad Hoc Analysis 相比，在 Java 11 上运行 Ad Hoc Analysis 时需要遵循一些额外的步骤。

## 先决条件

与您的 IT 团队合作，确保满足以下条件：

* 必须已安装 Java 11，并设置了 *JAVA_HOME* 环境变量
* 必须已安装 JavaFX，并将 *PATH_TO_FX_SDK* 环境变量指向 JavaFX SDK 目录。例如，在 Mac 中，*PATH_TO_FX_SDK=/homedir/javafx-sdk-11.0.2*，或者在 PC 中，*PATH_TO_FX_SDK=C:\Users\username\javafx-sdk-11.0.2*。

## 安装适用于 Java 11 的 Ad Hoc Analysis

1. 转到 **[!UICONTROL Analytics > 工具 > Ad Hoc Analysis]**。
1. 单击 **[!UICONTROL Ad Hoc Analysis (Java 11)]**。此时会下载一个 zip 文件。
1. 解压缩已下载的文件。
1. **选择 .bat (PC) 或 .sh (Mac) 文件**。通过查看 Adobe Analytics URL 中“sc”后面的数字，选择相应的数据中心文件。（3 = LON，4 = SIN，5 = PNW）如果您使用的是 PC，请转至“电脑信息”，确认您运行的是 32 位还是 64 位 Windows 操作系统。然后，选择适当的 .bat 文件。
1. **运行所选文件**。对于 PC：双击 .bat 文件。对于 Mac：右键单击 .sh 文件，然后选择&#x200B;**[!UICONTROL 打开方式 > 其他... > 实用工具 >（启用所有应用程序）> 选择“终端”> 打开]**。
1. 登录到 Ad Hoc Analysis。

> [!NOTE]Java 11 版本的 Ad Hoc Analysis 不兼容 Federated ID 和 Enterprise ID 身份验证方法。

## Ad Hoc Analysis (Java 11) 中不支持的功能

在与 Ad Hoc Analysis 兼容的 Java 11 版本中，存在着一些已知的限制：

* 不支持 Federated ID 和 Enterprise ID 身份验证方法。
* 不支持 Linux 操作系统。
* 使用 Mac 时，请勿使用 Mac 应用程序菜单（包括 *cmd + Q*）。因为这可能会导致 Ad Hoc Analysis 在没有警告的情况下关闭。请改用 Ad Hoc Analysis 中的菜单。
* 在 MacOS 上运行 Ad Hoc Analysis 时，不支持“网站分析”可视化图表。

## 常见问题解答

**问：我收到“无法找到 \bin\javaw”错误（参见下面的示例）- 我该怎么办？**

![](/help/analyze/ad-hoc-analysis/assets/error-java.png)

答：如果您收到此错误，请与您的 IT 团队一起设置 *JAVA_HOME* 环境变量，该变量是在 Java 11 中运行 Ad Hoc Analysis 所必需的。
