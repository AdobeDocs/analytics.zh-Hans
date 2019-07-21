---
description: 验证您的网站是否正确加载了动态标签管理库。
keywords: Analytics实施；实施方法；动态标签管理；dm；代码；页面代码；标题代码；页脚代码；嵌入代码；验证代码；验证标题代码；验证页脚代码；嵌入选项卡；嵌入
seo-description: 验证您的网站是否正确加载了动态标签管理库。
seo-title: 验证页眉和页脚代码
solution: Analytics
title: 验证页眉和页脚代码
topic: 开发人员和实施
uuid: d395a417-0c61-41a6-a124-d2 f400 f4626 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 验证页眉和页脚代码

验证您的网站是否正确加载了动态标签管理库。

1. 在浏览器中打开您的网站。
1. Open the [!UICONTROL Developer Console] by right-clicking and choosing **[!UICONTROL Inspect Element]** &gt; **[!UICONTROL Console]**.
1. Press **[!UICONTROL Enter]**.

   If the code was properly installed, you will see *`true`* display in the console.

   如果代码安装不正确，则将会显示引用错误：

   `_satellite is not defined`

   如果收到此错误，请确保：

* You have included the full header code on every page of the site in the [!DNL HEAD] section, as close to the [!DNL <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">]开始标记的位置。
* 您的代码片段中没有出现意外字符，当从某个格式化的文档中进行复制和粘贴时，可能会导致出现意外字符。

