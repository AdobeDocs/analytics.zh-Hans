---
description: 报告时间处理是一个虚拟报告套件设置，它允许以非破损的、可追溯的方式处理数据。
seo-description: 报告时间处理是一个虚拟报告套件设置，它允许以非破损的、可追溯的方式处理数据。
seo-title: 报表时间处理
title: 报表时间处理
uuid: 1d82ea-8c93-43cc-8689-cdf59 c309 b1
translation-type: tm+mt
source-git-commit: 1e8d5af54ab22311e1c3967979c8bdc982a66d5b

---


# 报表时间处理

报告时间处理是一个虚拟报告套件设置，它允许以非破损的、可追溯的方式处理数据。

>[!NOTE]
>
>报告时间处理仅适用于Analysis Workspace。

报表时间处理仅影响虚拟报表包中的数据，而不会影响基础报表包中的任何数据或数据收集。通过下图可以最好地理解报表时间处理与传统 Analytics 处理之间的区别：

![](assets/google1.jpg)

在 Analytics 数据处理过程中，数据会通过数据收集通道传输到预处理步骤，进而为报告准备数据。在收集数据时，此预处理步骤会将访问过期逻辑和 eVar 持久性逻辑（以及其他内容）应用于数据。这种预处理模式的主要缺点在于，它需要在收集数据之前预先完成所有配置。这意味着对预处理设置的任何更改仅适用于在此更改后收集的新数据。如果数据未按顺序到达或设置的配置错误，这种模式就会出现问题。

报表时间处理是一种截然不同的 Analytics 报表数据处理方式。在收集数据之前，Analytics 不会预先确定处理逻辑，它而是会在预处理步骤中忽略数据集，并在每次运行报表时应用此逻辑：

![](assets/google2.jpg)

这种处理架构提供了更为灵活的报表选项。例如，您可以将访问超时时段以非破坏性的方式更改为任何所需时长，这些更改将以追溯方式反映在您的 eVar 持久性和区段容器中，就如同您在收集数据之前应用了这些设置一样。此外，您还可以创建任意数量的虚拟报表包，每个虚拟报表包均具有不同的报表时间处理选项，这些选项基于相同的基础报表包，而无需更改基础报表包中的任何数据。

通过报表时间处理，Analytics 还可以避免将后台点击计算为新的访问，并且[移动 SDK](https://marketing.adobe.com/developer/get-started/mobile/c-measuring-mobile-applications) 也可以让报表在每次触发应用程序启动事件时才开始一次新访问。

以下配置选项当前可用于启用了报表时间处理的虚拟报表包：

<table id="table_C086C5FD10A84A1ABC081F5DE28F802D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 设置 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 访问超时 </p> </td> 
   <td colname="col2"> <p> 访问超时设置定义独特访客在新访问自动开始之前必须处于非活动状态的时间。默认为 30 分钟。例如，如果将访问超时设置为 15 分钟，则会以 15 分钟的非活动状态进行分隔，为每个收集的点击序列创建一个新访问组。此设置不仅会影响您的访问计数，还会影响访问区段容器的评估方式，以及任何在访问时过期的 eVar 的访问过期逻辑。缩短访问超时时间可能会增加报表中的总访问次数，而延长访问超时时间可能会减少报表中的总访问次数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 移动设备应用程序访问设置 </p> </td> 
   <td colname="col2"> <p> 对于包含由移动设备应用程序通过 <a href="https://www.adobe.io/apis/cloudplatform/mobile.html" format="html" scope="external">Adobe Mobile SDK</a> 生成的数据的报表包，可以使用其他访问设置。这些设置不具有破坏性，只会影响通过移动 SDK 收集的点击量。这些设置对通过移动 SDK 之外的程序收集的数据没有影响。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 避免将后台点击计算为一次新的访问 </p> </td> 
   <td colname="col2"> <p> 当应用程序处于后台状态时，移动 SDK 会收集后台点击量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 在每次应用程序启动后即开始一个新访问 </p> </td> 
   <td colname="col2"> <p> 除了访问超时之外，您还可以不考虑非活动状态时限，只要移动 SDK 中记录了应用程序启动事件，就可以强制开始一次访问。此设置会影响访问量度和访问区段容器，以及 eVar 中的访问过期逻辑。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>通过事件开始新访问 </p> </td> 
   <td colname="col2"> <p>无论会话是否超时，均会在事件被触发时启动新会话。新创建的会话包含启动该会话的事件。此外，您可以使用多个事件启动会话，如果在数据中观察到这些事件中的任何一个，便会触发新会话。此设置将影响您的访问计数、访问分段容器以及 eVar 上的访问过期逻辑。 </p> </td> 
  </tr> 
 </tbody> 
</table>

报表时间处理不支持传统 Analytics 报表中提供的所有量度和维度。Virtual report suites utilizing Report Time Processing are only accessible in Analysis Workspace and will not be accessible in [!UICONTROL Reports &amp; Analytics], Ad Hoc Analysis, Data Warehouse, Report Builder, Data Feeds, or the reporting API.

另外，报表时间处理仅可处理报告日期范围（以下称为“日期时限”）内的数据。这意味着在报告日期范围之前为访客设置的“永不过期”的 eVar 值不会在报告时限内持续保留，并且也不会显示在报表中。这还意味着客户忠诚度测量完全基于报告日期范围内的数据，而不是报告日期范围之前的整个历史记录。

以下是使用报表时间处理时，当前不支持的量度和维度列表：

<table id="table_127AFE8FA1BE4F2BAB3975CA12A2FA47"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度/维度名称 </th> 
   <th colname="col2" class="entry"> 报表时间处理注释 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 目标分析 </p> </td> 
   <td colname="col2"> <p> 当前不支持。计划将来支持。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 针对Advertising Cloud保留指标/维度的分析 </p> </td> 
   <td colname="col2"> <p> 当前不支持。计划将来支持。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> “单次存取”量度 </p> </td> 
   <td colname="col2"> <p> 现在和将来均不支持。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 列表变量 </p> </td> 
   <td colname="col2"> <p> 当前不支持。计划将来支持。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 计数器 eVar </p> </td> 
   <td colname="col2"> <p> 现在和将来均不支持。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 营销渠道变量 </p> </td> 
   <td colname="col2"> <p> 当前不支持。计划将来支持。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> “上次购买间隔天数”维度 </p> </td> 
   <td colname="col2"> <p> 由于报表时间处理存在日期时限性，因此不支持此维度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> “首次购买间隔天数”维度 </p> </td> 
   <td colname="col2"> <p> 由于报表时间处理存在日期时限性，因此不支持此维度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> “回访频度”维度 </p> </td> 
   <td colname="col2"> <p> 由于报表时间处理存在日期时限性，因此不支持此维度。 </p> <p> 可以使用一种替代方法，即在区段中使用访问计数量度，或者在直方图报表中使用访问量度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> “上次访问间隔天数”维度 </p> </td> 
   <td colname="col2"> <p> 由于报表时间处理存在日期时限性，因此不支持此维度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> “原始登录页面”维度 </p> </td> 
   <td colname="col2"> <p> 由于报表时间处理存在日期时限性，因此不支持此维度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 线性分配 eVar </p> </td> 
   <td colname="col2"> <p> 当前不支持。计划将来支持。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> “原始反向链接域名”维度 </p> </td> 
   <td colname="col2"> <p> 当前不支持。计划将来支持。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 访问量 </p> </td> 
   <td colname="col2"> <p> 由于报表时间处理存在日期时限性，因此不支持此量度。 </p> <p> 要报告移动设备应用程序中的新访客数与重复访客数，您可以使用计算量度（包括访客数/访问次数）以及应用程序安装量度来识别新访客数或访问次数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 交易 ID 数据源 </p> </td> 
   <td colname="col2"> <p> 当前不支持。计划将来支持。 </p> </td> 
  </tr> 
 </tbody> 
</table>

以下是受影响的维度和量度列表，具体取决于所选的报表时间处理设置：

<table id="table_491E48C55BC84917B4A8EACBF04C939F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度/维度名称 </th> 
   <th colname="col2" class="entry"> 报表时间处理注释 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> “独特访客数”量度 </p> </td> 
   <td colname="col2"> <p> 如果启用“避免将后台点击计算为一次新的访问”，则独特访客数不包括在报告日期范围内只有后台点击量的访客。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 访问 </p> </td> 
   <td colname="col2"> <p> 访问次数反映了虚拟报表包配置的任何设置，这些设置可能与基础报表包不同。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 包含事件 ID 的序列化事件 </p> </td> 
   <td colname="col2"> <p> 由于报表时间处理存在日期时限，使用事件序列化且包含事件 ID 的事件仅会对一个访客在报告日期范围内发生的事件进行重复数据删除，而不会在全局范围内对所有日期或访客发生的事件进行重复数据删除。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 购买/收入/订购/件数 </p> </td> 
   <td colname="col2"> <p> 当使用购买 ID 时，由于报表时间处理存在日期时限，这些量度仅会对一个访客在报告日期范围内出现的重复购买 ID 进行重复数据删除，而不会在全局范围内对所有日期或访客出现的重复购买 ID 进行重复数据删除。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 跳出次数/跳出率 </p> </td> 
   <td colname="col2"> <p> 如果启用“避免将后台点击计算为一次新的访问”，则当后台点击之后未跟有前台点击时，该后台点击将不被视为一次跳出，并且不计入跳出率。有关更多详细信息，请参阅 <a href="../../components/vrs/vrs-mobile-visit-processing.md#concept_EC51308E4FD14E149F1B5D63C0AB34BD" format="dita" scope="local"> 上下文感知型Sightization</a> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 每次访问逗留秒数 </p> </td> 
   <td colname="col2"> <p> 如果启用“避免将后台点击计算为一次新的访问”，则只有包含前台点击的访问才会计入此量度。有关更多详细信息，请参阅 <a href="../../components/vrs/vrs-mobile-visit-processing.md#concept_EC51308E4FD14E149F1B5D63C0AB34BD" format="dita" scope="local"> 上下文感知型Sightization</a> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 每次访问逗留时间 </p> </td> 
   <td colname="col2"> <p> 如果启用“避免将后台点击计算为一次新的访问”，则只有包含前台点击的访问才会计入此量度。有关更多详细信息，请参阅 <a href="../../components/vrs/vrs-mobile-visit-processing.md#concept_EC51308E4FD14E149F1B5D63C0AB34BD" format="dita" scope="local"> 上下文感知型Sightization</a> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 登录 </p> </td> 
   <td colname="col2"> <p> 如果启用“避免将后台点击计算为一次新的访问”，则只会考虑包含前台点击的访问中的登入次数。有关更多详细信息，请参阅 <a href="../../components/vrs/vrs-mobile-visit-processing.md#concept_EC51308E4FD14E149F1B5D63C0AB34BD" format="dita" scope="local"> 上下文感知型Sightization</a> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 非促销 eVar/保留的 eVar </p> </td> 
   <td colname="col2"> <p> 由于报表时间处理存在日期时限，仅当 eVar 中的值是在报告日期范围内设置的时，才会持久保留该值。 </p> <p> 此外，如果持久保留时间跨越夏令时变更，则基于时间的过期可能会提前一小时或延迟一小时。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 促销 eVar/保留的 eVar </p> </td> 
   <td colname="col2"> <p> 请参阅上面的内容。 </p> <p> 此外，对于将绑定设置为“任何事件”的转化语法，将改用“任何点击”。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 登入和退出维度 </p> </td> 
   <td colname="col2"> <p> 如果启用“避免将后台点击计算为一次新的访问”，则只有包含前台点击的访问中的登入和退出次数才会显示在此维度中。有关更多详细信息，请参阅 <a href="../../components/vrs/vrs-mobile-visit-processing.md#concept_EC51308E4FD14E149F1B5D63C0AB34BD" format="dita" scope="local"> 上下文感知型Sightization</a> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 点击类型 </p> </td> 
   <td colname="col2"> <p> 此维度指定点击是前台点击还是后台点击。 </p> </td> 
  </tr> 
 </tbody> 
</table>

