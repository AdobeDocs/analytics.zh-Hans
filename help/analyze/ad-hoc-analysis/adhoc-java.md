---
description: 关于如何使用 Java 11 运行 Ad Hoc Analysis 的说明。
title: 使用 Java 11 运行 Ad Hoc Analysis
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 使用 Java 11 运行 Ad Hoc Analysis

与使用Java 8运行临时分析相比，在运行Java 11时，您需要执行其他步骤。

## 先决条件

与您的IT团队合作，确保以下各项到位：

* 必须已安装 Java 11，并设置了 *JAVA_HOME* 环境变量
* 必须安装JavaFX，并且 *PATH_TO_FX_SDK* 环境变量指向JavaFX SDK目录。 例如， *PATH_TO_FX_SDK=/homedir/javafx-sdk-11.0.2* ，或 *PATH_TO_FX_SDK=C:\Users\username\javafx-sdk-11.0.2* 。

## 安装适用于Java 11的临时分析

1. 转到 **[!UICONTROL Analytics > Tools > Ad Hoc Analysis]** 。
1. 单击 **[!UICONTROL Ad Hoc Analysis (Java 11)]**. 这会下载一个zip文件。
1. 解压缩下载的文件。
1. **选择。bat(PC)或。sh(Mac)文件**。 通过查看 Adobe Analytics URL 中“sc”后面的数字，选择相应的数据中心文件。（3 = LON，4 = SIN，5 = PNW）如果您使用的是 PC，请转至“电脑信息”，确认您运行的是 32 位还是 64 位 Windows 操作系统。然后选择相应的。bat文件。
1. **运行所选文件**。 对于PC:双击。bat文件。 对于Mac:右键单击。sh文件，然后选择 **[!UICONTROL Open With > Other... > Utilities > (Enable all applications) > select Terminal > Open]**。
1. 登录到 Ad Hoc Analysis。

>[!NOTE]Java 11 版本的 Ad Hoc Analysis 不兼容 Federated ID 和 Enterprise ID 身份验证方法。

## Ad Hoc Analysis (Java 11) 中不支持的功能

在与 Ad Hoc Analysis 兼容的 Java 11 版本中，存在着一些已知的限制：

* 不支持Federated和Enterprise ID身份验证方法。
* 不支持Linux操作系统。
* 使用 Mac 时，请勿使用 Mac 应用程序菜单（包括 *cmd + Q*）。这可能导致临时分析关闭而不发出警告。 请改用临时分析中的菜单。
* 在MacOS上运行临时分析时，不支持站点分析可视化。

## 常见问题解答

**问：我收到“无法找到 \bin\javaw”错误（参见下面的示例）- 我该怎么办？**

![](/help/analyze/ad-hoc-analysis/assets/error-java.png)

答：如果您收到此错误，请与您的 IT 团队一起设置 *JAVA_HOME* 环境变量，该变量是在 Java 11 中运行 Ad Hoc Analysis 所必需的。
