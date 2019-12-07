---
description: 验证您的网站是否正确加载了动态标签管理库。
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;code;page code;header code;footer code;embed code;verify code;verify header code;verify footer code;embed tab;embed
title: 验证页眉和页脚代码
topic: Developer and implementation
uuid: d395a417-0c61-41a6-a124-d2f400f4626f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 验证页眉和页脚代码

验证您的网站是否正确加载了动态标签管理库。

1. 在浏览器中打开您的网站。
1. 右键单击并选择&#x200B;**[!UICONTROL 检查元素]** &gt; **[!UICONTROL 控制台]**，打开[!UICONTROL 开发人员控制台]。
1. 按 **[!UICONTROL Enter]**。

   如果代码安装正确，控制台中将会显示 *`true`*。

   如果代码安装不正确，则将会显示引用错误：

   `_satellite is not defined`

   如果收到此错误，请确保：

* 您在每个网站页面 [!DNL HEAD] 部分中尽可能靠近 [!DNL  <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">] 标记的位置包含了完整的页眉代码。
* 您的代码片段中没有出现意外字符，当从某个格式化的文档中进行复制和粘贴时，可能会导致出现意外字符。

