---
description: 列出了 Adobe Analytics 和 DFA 报表之间为何存在数据差异的一些原因。
keywords: DFA
seo-description: 列出了 Adobe Analytics 和 DFA 报表之间为何存在数据差异的一些原因。
seo-title: 产生差异的可能原因
solution: Analytics
title: 产生差异的可能原因
topic: Data connectors
uuid: fd414cc6-d568-491e-9b1 c-5d493 dcfbobe45
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# 产生差异的可能原因{#possible-reasons-for-discrepancies}

列出了 Adobe Analytics 和 DFA 报表之间为何存在数据差异的一些原因。

## Safari 浏览器和其他阻止第三方 Cookie 的浏览器的用户 {#section-4b0dc429a54a4744a33976b0bb2d1b2a}

是否接受第三方 Cookie 通常是导致 Adobe Analytics 和 DFA 之间出现差异的最大因素。Safari 和某些其他默认阻止第三方 Cookie 的浏览器。这意味着在默认情况下，Safari 接受大部分 Analytics 实施使用的第一方 Cookie，但拒绝 DFA 使用的第三方 Cookie。

我们的Analytics15测试版客户的数据范例显示，少于0.5%的用户通常拒绝第一方cookie，而5-12%拒绝第三方cookie(其中很多集成可能由于默认浏览器设置而异)。

这种差异可导致 Analytics 和 DFA 收集的数据间出现较大差别。

## 为何 DFA 中报告的展示次数可能高于 Adobe Analytics 中报告的展示次数？ {#section-db0ad070a65a4985bcc589b2d0d30b90}

* DFA 将数据在夜间批量发送到 Adobe 数据收集服务器，因此 Analytics 中的展示数据最长可能滞后于 DFA 报表 2 天。
* Adobe 使用 SAINT 分类将导入的 DFA 跟踪代码分类为不同级别的汇总（促销活动名称、版面名称、广告名称等）。如果在运行分类报表时出现差异，请执行一个简单的测试以了解分类是否还未赶上导入的量度：

   * 在分类报表中，找到名为“无”的行项目。
   * 使用原始 DFA ID 报表，以按相同的变量划分此行项目（如促销活动 ID）。
   * 在此报表中，请注意任何格式为 DFA:XXXXX:XXXXX 的未分类 DFA 跟踪代码...
   * 如果这其中的许多跟踪代码确实存在，请调查夜间 SAINT 分类过程。

## 为何 DFA 点击量可能高于 Adobe Analytics 点进次数？ {#section-2fce4608ed044bdc9cf812cb719d5d35}

* DFA 在访客登陆客户网站之前即记录一次点击。Analytics 在登陆页面加载后记录点进次数，并执行 Adobe JavaScript 信标。通常，差异的出现是因为访客在 DFA 跟踪到一次点击后没有到达登陆页面，或是&#x200B;*`s.maxDelay`*&#x200B;计时器被点击。
* 请确保 Floodlight 配置中的所有版面和创作均在登陆页面 URL 中加入了 clickThroughParam（例如“?CID=1”）。未能设置此参数将导致 Adobe Analytics JavaScript 丢失在访问的首次点击后发生的任何点进。
* 请确保所有版面和创作的登陆页面均使用 JavaScript 标记并具有 DFA 集成模块，而且此登陆页面中的 Floodlight 配置 ID 匹配服务广告的 Floodlight 配置 ID。通常，差异的出现是因为广告的登陆页面被设置为第三方网站或服务的广告。
* 如果您使用富媒体广告或 Flash (swf) 广告，请确保每当 DFA 点击跟踪器被点击时，访客的浏览器都会被重定向到查询字符串中包含 `clickThroughParam` 的登陆页面。未能重定向浏览器将不会导致记录一次点进。
* 超时表示虽然可能已有可用的 DFA 数据，但 JavaScript 却没有及时收到响应的情况。当访客到达登陆页面时，Adobe JavaScript 从 DFA 的 fls.doubleclick.net 服务请求访客的信息。The *`s.maxDelay`*&#x200B;参数决定 JavaScript 将等待 Floodlight 服务 (FLS) 数据多长时间。If *`s.maxDelay`* is too high, visitors can leave the site before Adobe collects the hit data; meaning that no click data is recorded. *`s.maxDelay`* 如果设置过低，访客的Internet连接无法及时检索FLS数据；意味着点击被发送给Adobe，而没有DFA单击信息。See [Tuning s.maxDelay](../../dfa-data-connector-analytics/dfa-integration/dfa-tuning-s-maxlelay.md#concept-6deb28eee18e414db220d6009d449f0d) for a further discussion on this subject.

* 机器人流量可能夸大 DFA 点击数。机器人或许能够点击广告，但其复杂性可能不足以执行 Analytics 信标或触发同步脚本标记以加载 Floodlight 服务器请求数据。如果这些机器人未从点击量数据中删除，则可能成为造成差异的一个因素。
* 在&#x200B;*`s.maxDelay`*&#x200B;过期及 DFA 数据返回之前离开页面的访客将会丢失；且不会为他们收集任何 DFA 或访客数据。
* Analytics 尝试标识并删除重复的点进，这样这些点进将对应每个促销活动每次访问只计数一次。DFA 将单击“返回”和经历多次广告重定向的访客数计为额外的 ACM 点击量，而 Analytics 不会将它们计为多次点进。
* DFA Floodlight 标记不依赖启用的 JavaScript，而 Analytics 却依赖它们。因此，在某些情况下可能会出现 DFA 记录了一次点击，而 Analytics 没有记录。要辨明这是否是个问题，请使用“访客配置文件”菜单中的 Analytics JavaScript 报表。

## 为何 DFA 后展示活动数可能高于 Adobe Analytics 显示到达次数？ {#section-5daa91039c404df48b6a3447c20406f7}

* Analytics 尝试标识并删除重复的点进，这样这些点进将对应每个促销活动每次访问只计数一次。DFA 将单击“返回”和经历多次广告重定向的访客数计为额外的 ACM 点击量，而 Analytics 不会将它们计为多次点进。
* DFA Floodlight 标记不依赖禁用的 JavaScript，而 Analytics 却依赖它们。因此，可能会出现以下这类情况，即 DFA 记录了一次点击，而 Analytics 没有记录。
* DFA 在使用 Floodlight 标记时（它们可能置于客户端网站上）可对后展示活动进行计数。Analytics 在 JavaScript 信标（图像请求）执行后对显示到达进行计数。网页上的代码布局可决定将一个终止的页面加载计为一次后展示活动还是一次显示到达。

## 如果差异远远超过可接受的范围并且以上可能的原因都不适用，该怎么办？ {#section-ca50eb75dd5d4d0396f4668b44d7547c}

请咨询您的集成顾问或 Adobe 客户关怀，以记录差异并将它们报告给 Data connectors 工程团队。为加快请求速度，请使用 2 到 3 天的数据对涉及的量度进行比较（在促销活动代码级别）。在您的请求中，请标识您为协调差异所执行的所有操作。
