---
description: 列出在部署集成之前从您的Seligent帐户提供的必要信息。
seo-description: 列出在部署集成之前从您的Seligent帐户提供的必要信息。
seo-title: Seligent的先决条件
solution: Analytics
title: Seligent的先决条件
uuid: a43a1c0-5f51-4bc8-b6 b9 b9-0c46 a00 ba9 f
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Seligent的先决条件{#prerequisites-for-selligent}

列出在部署集成之前从您的Seligent帐户提供的必要信息。

**有效的自助帐户**

要使用此数据连接器集成，您必须具有有效的Seligent帐户。

**帐户信息**

在此集成设置期间，您将需要有关您的Seligent帐户的以下信息：

* **Adobe服务URL**：

   URL可从用于登录到Serient Marketing解决方案的URL派生。将url的“/simweb/login. aspx”部分替换为“/automation/omniture. asmx”

   例如：http://<client-specific install url>/automation/omniture.asmx

* **查询字符串参数：** 这些内容附加到消息ID和收件人ID(访问者ID)的登录页面URL中。对于消息ID和收件人ID，这些总是MID和RID。

* **集成令牌** 从Simweb中启动管理器工具并转到 **[!UICONTROL 配置]** &gt; **[!UICONTROL 系统设置]** &gt; **[!UICONTROL 常规]** 选项卡&gt; **[!UICONTROL 系统]**。**[!UICONTROL 在安全性]**&#x200B;下，您可以找到集成令牌。

   ![](assets/selligent-integration_token.png)

