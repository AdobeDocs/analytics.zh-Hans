---
description: 验证您的网站是否正确加载了动态标签管理库。
keywords: Analytics 实施;实施方法;dynamic tag management;DTM;代码;页面代码;页眉代码;页脚代码;嵌入代码;验证代码;验证页眉代码;验证页脚代码;嵌入选项卡;嵌入
seo-description: 验证您的网站是否正确加载了动态标签管理库。
seo-title: 验证页眉和页脚代码
solution: Analytics
title: 验证页眉和页脚代码
topic: 开发人员和实施
uuid: d395a417-0c61-41a6-a124-d2f400f4626f
translation-type: ht
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

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

