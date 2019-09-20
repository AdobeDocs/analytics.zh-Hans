---
description: Flash 的发行说明汇总。使用 ActionScript 的 Flash 应用程序可在桌面和 Web 上进行测量。
seo-description: Flash 的发行说明汇总。使用 ActionScript 的 Flash 应用程序可在桌面和 Web 上进行测量。
seo-title: Flash-Flex
solution: Analytics
subtopic: 发行说明
title: Flash-Flex
topic: 开发人员和实施
uuid: 2ee7fb92-9b62-44d4-bd93-6dff26764b7f
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Flash-Flex{#flash-flex}

Flash 的发行说明汇总。使用 ActionScript 的 Flash 应用程序可在桌面和 Web 上进行测量。

>[!NOTE]
>
>要查找当前库版本，请打开调试日志记录。

<!-- 

https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=omtrcache&title=AppMeasurement+Change+Log

 -->

## April 20, 2017 {#section_8521EC2B68E24203A0F1B14A9D2652D2}

**版本 4.0.3 **

* 包括 Visitor API 1.6.1.

## 2016 年 8 月 18 日 {#section_D72EF20672174249B864997905D7552A}

** 4.0.2 —— 更新**

包括 Visitor API 1.6.0。

## May 19, 2016 {#section_061305CFC1E040E69E3CDF4078C17AE4}

** 4.0.1 —— 更新**

包括 Visitor API 1.5.6

## April 21, 2016 {#section_6EFC6DBEB9E1460DB344A8278F9FC696}

Adobe 已为 [ for Flash 库发布了](https://helpx.adobe.com/security/products/analytics/apsb16-13.html)安全更新 APSB16-13[!DNL AppMeasurement]。此更新消除了该库的重要漏洞（仅当启用了 `debugTracking` 时才会出现），别有用心的人可能会利用该漏洞发起[基于 DOM 的 XSS 攻击](https://www.owasp.org/index.php/DOM_Based_XSS)。

>[!IMPORTANT]
>
>This issue affects [!DNL AppMeasurement] for Flash only when `debugTracking` has been enabled ( `debugTracking` is disabled in the default configuration). **如果受此问题影响，我们强烈建议您立即禁用`debugTracking`。**&#x200B;下面是一些示例代码：

```
public var s:AppMeasurement; 
s = new AppMeasurement(); 
s.debugTracking = false; // set to false or remove line 
                         // for default "disabled” behavior 
```

受影响的版本包括在所有平台上运行的 适用于 [!DNL AppMeasurement] 所有平台上的Flash版本4.0及更早版本。

>[!NOTE]
>
>Due to security reasons, we will no longer be distributing an AS2 version of [!DNL AppMeasurement] for Flash. 我们将继续支持从现有 AS2 项目中收集的数据。但是，我们强烈建议客户将其实施项目升级为 AS3 版本，并融入 [!DNL AppMeasurement] for Flash 的最新安全功能。

[!DNL AppMeasurement] 对于受此问题影响的Flash客户，必须使用更新的库重新构建项目，该库可从 [!DNL Analytics] Console [More...](https://help.adobe.com/en_US/Flex/4.0/UsingFlashBuilder/WS6f97d7caa66ef6eb1e63e3d11b6c4d0d21-7feb.html#WS6f97d7caa66ef6eb1e63e3d11b6c4d0d21-7f88) (AN-121780)下载

## November 5, 2015 {#section_18C1A1C82EA844E78A1D563E66DE3FCF}

4.0版——更新：

* 包括 Visitor API 1.5.3。

## September 17, 2015 {#section_319911C0F080452981F8C8BEA2880463}

4.0版——更新：

* 包括 Visitor API 1.5.2。

## 2015 年 8 月 20 日 {#section_1BEA10285E9F4863B89B4B713DBB20DB}

4.0版——更新：

* 包括 Visitor API 1.5.1.

## 2015 年 6 月 18 日 {#section_2ACB18A1693244D6A49B53F4E17F0C30}

4.0版——更新

* 包括 Visitor API 1.5。
* 使用 Visitor API 1.5+ getCustomerIDs 方法收集客户 ID 和身份验证状态，并通过数据收集请求发送它们 (AN-102131)

## 2015 年 5 月 21 日 {#section_F5EFCC451F13499F9AA53326AE5926F1}

版本3.9.2 —— 更新：

* 包括 Visitor API 1.4

## 2015 年 2 月 19 日 {#section_95ADF1725CE7415D956944A28182E69B}

版本 3.9.2:

* 包括 Visitor API 1.3.5。
* 首次跟踪调用后更改为不执行自动反向链接跟踪，以便第 2 次、第 3 次（依此类推）跟踪调用在&#x200B;*`s.referrer`*&#x200B;于首次跟踪调用之前被手动设置时，不会将反向链接计算两次。(AN-92647)
* Removal of deprecated [!UICONTROL Heartbeat] video tracking embedded in the Media module. The supported [!UICONTROL Heartbeat] video tracking has been moved to a separate Video [!DNL Analytics] library.

## September 18, 2014 {#section_80939868A2284961BF620851B000294F}

版本 3.9.1:

* Added cookie support testing to Flash (k = Y/N query-string variable) and pf=1 to query-string when cookie support test is possible (browser with [!DNL JavaScript] access).
* 支持访客 ID 服务 1.3.2 中的新增功能。

## 2014 年 8 月 21 日 {#section_F7CA56E42B6548D3BE5A0D020BCEE97A}

版本 3.9:

* 添加了纬度和经度变量。
* 支持访客 ID 服务 1.3.1 中的新增功能。

## 版本 3.8.1 {#section_29A2A0A20D9B43A1B57E5ED299C6EAF3}

发行日期：**2014 年 6 月 19 日**

* Fixed handling of done and waiting flags for Visitor API fields such as the legacy [!DNL Analytics] Visitor ID, that was causing errors.
* 支持访客 ID 服务 1.3 中的新增功能。

## 版本 3.8 {#section_3F75C4D0C9BE470B95838DDB2CDCA79F}

发行日期：**2014 年 4 月 17 日**

* 支持 [Experience Cloud访客ID服务](https://marketing.adobe.com/resources/help/en_US/mcvid/)。

## 版本 3.7.3 {#section_1159B2AB56F54903A6FBFB7047AEC1C5}

发行日期：**2014 年 3 月 13 日**

* Multiple bug fixes to [!UICONTROL Heartbeat] video tracking.

## 版本 3.7.2 {#section_D6DCE5FE846A45F1A2CED237E8AAEFE9}

发行日期：**2014 年 2 月 6 日**

* Multiple bug fixes to [!UICONTROL Heartbeat] video tracking.

## 版本 3.7.1 {#section_DC79F108AB5E42189A8EC7D87697AE0B}

发行日期：**2013 年 11 月 14 日**

* Multiple bug fixes to [!UICONTROL Heartbeat] video tracking.

## 版本 3.7 {#section_7239878DCD724FD0B9BC900821A4DA96}

发行日期：**2013 年 10 月 17 日**

* 对[心率视频跟踪](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/)的支持。
* 已包含 VisitorAPI.swc，以便支持[访客 ID 服务](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_service#)。
* 停止了对适用于 ActionScript 3 的 Flash Player 9 的支持。适用于 ActionScript 3 的最低 Flash Player 版本为 10。

## 版本 3.6.2 {#section_57FB21568BDD48F7882F00AD630E6CE8}

发行日期：**2013 年 9 月 18 日**

* 执行了某些内部更改以支持即将推出的测试版功能。

## 版本 3.5.5 {#section_149CAF8AF39741C2B9F6A015F7FB8C61}

发行日期：**2013 年 8 月 15 日**

* 在离线跟踪被禁用的情况下，禁用了失败请求的重新排队。

## 版本 3.5.4 {#section_3429BD7DE2B64110BEE3A3850E58A0F7}

发行日期：**2013 年 2 月 21 日**

* 已修复 ActionScript 2 中的 URL 编码/解码问题。

## 版本 3.5.3 {#section_5192BC1C8BF547D1A5A92863686601DD}

发行日期：**2013 年 1 月 31 日**

* 为了支持 Adobe 数据收集服务器中扩展的“页面 URL”字段，已添加对发送大于 255 字节 URL 的支持。Page URLs longer than 255 bytes are split, with the first 255 bytes appearing in the `g=` parameter, with the remaining bytes appearing later in the query sting in the `-g=` query parameter. 这有助于在浏览器截断的情况下防止长 URL 优先于其他数据，但仍然启用对长 URL 的捕获功能。

* 添加了新的备用访客识别方法。请参阅[识别独特访客](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_identifying_unique_visitors)。
* Added a new `abort` flag that can be set inside `doPlugins`. 将此标记设置为 true 会导致 [!DNL AppMeasurement] 库不继续进行跟踪呼叫。中止标记已通过每个跟踪呼叫进行重置，因此，如果还需要中止后续跟踪呼叫，则需要在 `doPlugins` 内重新设置标记。

   ```js
   s.doPlugins = function(s) { 
        s.campaign = s.getQueryParam("cid"); 
        if ((!s.campaign) && (!s.events)) { 
             s.abort = true; 
        } 
   };
   ```

   这可让您将用于确认您不希望跟踪的活动的逻辑集中在一起，如一些自定义链接或显示广告中的外部链接。

## 版本 3.5.2 {#section_77727E343EC14B869020358183DAB2DB}

发行日期：**2012 年 11 月 8 日**

* Internal updates for [!DNL Audience Manager] integration.

## 版本 3.5.1 {#section_F6345AC9F4994D6F97BBCF399B02BB21}

发行日期：**2012 年 10 月 22 日**

* 更改了 ActionScript 3 生成，以忽略任何 `s.charSet` 设置，因为我们将始终使用 UTF-8。

## 版本 3.5 {#section_7DC183DD46CF42FE85F42E7AB8915D99}

Release Date: **September 13, 2012**
**Important change to variable binding**: In version 3.5, an option to disable variable binding was added for customers who need to start and end literal string values with curly braces. 使用大括号的变量绑定主要用于使用 XML 标记配置 OSMF 视频播放器的情况：

```
<autoTrackMediaName>{media.player.metadata(https://www.corp1.com/,episodeID)}</autoTrackMediaName>
```

提供称为 `autoBind` 的新属性，以覆盖 XML 标记中的默认行为：

```
<autoTrackMediaName autoBind=false>{123}</autoTrackMediaName>
```

将 `autoBind` 设置为 `false` 会导致将值视为文字字符串，且不使用变量绑定。当此属性未设置为 `false` 时，XML 标记中的行为保持不变。

**对 ActionScript 代码的影响**

Though not commonly used, this syntax is also available to bind [!DNL AppMeasurement] variables in your ActionScript code. If you are unsure whether or not you are using variable binding, search your code for [!DNL AppMeasurement] variable values that start and end with curly braces. 例如：

```
s.eVar1 = "{source}";
```

如果您要使用变量绑定。您应该更改此代码以使用新的 `bindVariable` 方法：

```
s.bindVariable("eVar1","source");
```

除了更改每个位置以外，您还可以选择将 `autoBindVariablesByValue` 设置为 true，恢复 3.5 版本之前的行为：

```
s.autoBindVariablesByValue = true;
```

**其他修复：**

* 修复了可能导致在使用自定义 `media.monitor` 方法（跟踪媒体关闭事件）时未发送视频完成事件的问题。

   ```
   If(media.event==”CLOSE”) { 
   … 
   } 
   ```

## 版本 3.4.9 {#section_5F2566CF954242D0A7205DA0B257DABA}

发行日期：**2012 年 7 月 19 日**

* Added a master-only meta policy, see [https://www.adobe.com/devnet/flashplayer/articles/fplayer9_security.html](https://www.adobe.com/devnet/flashplayer/articles/fplayer9_security.html).

## 版本 3.4.8 {#section_7501E04F6A854D50BFF0F287607A796F}

发行日期：**2012 年 6 月 21 日**

* 更改为在 AS3 生成中总是使用 UTF-8。这样做会避免某些多字节语言中的字符串出现问题。

## 版本 3.4.7 {#section_B26A014D13B14878816472E394FBAAA6}

发行日期：**2012 年 4 月 26 日**

视频测量：修复了 Brightcove 播放器 API 报告的完成情况偏移值不一致的问题。现在如果偏移量报告为零，则当报告完成时，我们会将长度用作偏移量。这提供了一个使用偏移值跟踪完成情况的新方法来解决问题。

## 版本 3.4.6 {#section_273B76A58745486E9715D9F5C2AEC433}

发行日期：**2012 年 1 月 19 日**

* 使用新方法更新了视频跟踪功能，以便跟踪完成的视频查看。

## 版本 3.4.5 {#section_DEDF0BEF6BF4458CA00896799E5BA67C}

发行日期：**2011 年 9 月 8 日**

* 已启用 prop 来包含文字零值 "0"。以前具有文字零值的 prop 不会发送出去。

## 版本 3.4.3 {#section_6C930AA0E95045BCA9AD4096B63657C9}

发行日期：**2011 年 5 月**

* 在 OSMF 中，已修复跟踪 OSMF 视频播放器时使用代理插件的问题。此次修复使得当代理的元素未被跟踪时，会跟踪 OSMF 代理元素。
* 修复了导致在 Flash Player 9.0.16 上测量视频时出错的问题。

