---
description: AppMeasurement 3.x for Android
seo-description: 适用于Android的AppMeasurement 3.x的传统文档
seo-title: AppMeasurement 3.x for Android
solution: Analytics
subtopic: 书签
title: AppMeasurement 3.x for Android
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 595efd52fe3b8edae32d8b3c2216ea066ec642be

---


# AppMeasurement 3.x for Android

*注意：本文档包含AppMeasurement早期版本的旧版信息，特别是针对Android版本3.x的旧版信息。
有关当前AppMeasurement实施的信息，请参[阅关于AppMeasurement for Javascript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html)。*

*上次更新：2018年3月15日适用于Android的AppMeasurement 3.x*

Adobe appMeasurement for android允许您在Adobe Experience cloud中测量原生Android应用程序。

本指南分为两部分：其中一个面向具有Adobe Analytics经验的分析师，另一个面向具有移动应用程序开发经验的Android开发人员。

**支持的版本**:Android 2.0或更高版本。

**下载库下载说**&#x200B;明和所有AppMeasurement移动平台的链接，可在开发人员连接上的“测量和优化移动应用程序”页获取。 您必须具有免费的 Developer Connection 帐户或登录 SiteCatalyst 以后才能下载库。在您登录后下载链接才会出现。

## 分析师快速入门

此部分指导您实施 Android 库和添加标准实施所需的代码。并提供了具体步骤，向您展示如何发送自定义事件和其他数据。

作为分析师，您需要对您的报表包启用移动设备应用程序报表。如果您有其他量度要捕获，则应向您的开发人员提供应用程序应发送的上下文数据变量的描述。例如，要在登录后收集用户名，可以让您的开发人员将用户名设置到名为 `myco.username` 的上下文数据变量中。

### 在 SiteCatalyst 中启动移动设备应用程序报表

SiteCatalyst 提供了用于启用移动设备应用程序生命周期跟踪的接口。此映射可让 SiteCatalyst 自动生成移动设备应用程序报表。

1. 打开管理控制台&gt;报表包&gt;编辑设置&gt;移动设备管理&gt;移动设备应用程序报表。
1. 单击“启用移动应用程序生命周期跟踪”。

现在已经捕获了生命周期量度，“移动设备应用程序报表”会出现在 SiteCatalyst“报表”菜单中。

### 使用处理规则捕获其他量度

如果实施使用上下文数据发送其他事件和维度，您必须配置处理规则以捕获该数据。

创建处理规则前，组织中必须有人获得认证。有关详细信息，请参阅处理规则帮助。

启用处理规则后，复制上下文数据变量示例展示映射上下文数据所需的过程。

### （可选）启用离线跟踪

若计划在设备离线时存储点击，则报表包必须启用时间戳。

启用离线跟踪后，所有点击都必须盖上时间戳，否则将无法收集这些点击。如果您目前在向某个报表包报告 AppMeasurement 数据，而该报表包也从 JavaScript 收集数据，那么您应该为移动数据单独建立一个报表包，以避免数据丢失，或使用 s.timestamp 变量在 JavaScript 点击上添加自定义时间戳。

如果不确定您的报表包是否启用了时间戳，请与客户服务联系。

## 开发人员快速入门

此部分指导您完成选择和配置用于收集 Android 数据的事件、eVar 和 prop。还提供创建处理规则的步骤，以将 Android 库发送的上下文数据复制到这些变量。

实施Android库和开始发送测量数据的步骤如下：

* 获取库
* 将库添加到项目
* 添加应用程序权限
* TrackingHelper 的简介
* 实施

### 获取库

访问 Developer Connection 上的测量和优化移动设备应用程序以下载 Android 库。解压缩下载文件，其中会包含以下软件组件：

* admsAppLibrary.jar：专门与 Android 设备及模拟器搭配使用的库。需要 Android 2.0 或更高版本。
* Examples\TrackingHelper.java：旨在将跟踪代码与应用程序逻辑分离的可选类。

### 将库添加到项目

1. 在 Eclipse IDE 中，右键单击项目名称。
1. 选择生成路径 &gt; 添加外部存档。
1. 选择 `admsAppLibrary.jar`.
1. 单击打开。
1. 再次右键单击项目，然后选择生成路径&gt;配置生成路径。
1. 单击订购和导出选项卡。
1. Ensure that `admsAppLibrary.jar` is selected.

您的应用程序可以使用导入com.adobe.ADMS从admsAppLibrary.jar库导入类／接口。*;

### 添加应用程序权限

AppMeasurement 库需要以下权限来发送数据和记录离线跟踪调用：

* INTERNET
* ACCESS_NETWORK_STATE

To add these permissions, add the following lines to your AndroidManifest.xml file (in the application project directory):
`<uses-permission android:name="android.permission.INTERNET" />`
`<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />`

### TrackingHelper 的简介

SDK 包括一个额外的可选类，名为 TrackingHelper。TrackingHelper 提供了一种方法可以将测量代码与应用程序逻辑分离。

请考虑以下示例：在应用程序中，您想要发送跟踪每次登录的事件。您可以直接在登录代码后面添加以下代码来发送此事件（不用担心代码详细信息，我们稍后再了解）：

```
Hashtable<String, Object> contextData = new Hashtable<String, Object>();
contextData.put("username", "username_value");
measure.trackEvents("event1", contextData);
```

此直接的方法虽然可行，但是您应该会希望将此代码放在其他某个地方，以便它不会妨碍应用程序开发。TrackingHelper 就是一个合适的位置。在 TrackingHelper 中，可以将此代码放置到方法 trackLogonEvent：

```
public static void trackLogonEvent (String username_value) {
Hashtable<String, Object> contextData = new Hashtable<String, Object>();
contextData.put("username", username_value);
measure.trackEvents("event1", contextData);
}
```

现在，在您的应用程序代码中，可以通过对 trackLogonEvent 的简单调用跟踪登录事件：

TrackingHelper.trackLogonEvent("username");

应用程序代码中的测量调用缩减为只有一行。另外，如果基本测量逻辑需要更改，只需要更新 TrackingHelper 即可。如果其他开发人员对您的代码进行添加，他（或她）可以使用您定义的简化方法，而无需参加 AppMeasurement 库的速成课。

我们认为您会喜欢使用 TrackingHelper 进行新的实施，尽管这项实施的设置需要多花费一两分钟。本指南中剩余的步骤将指导您完成设置 TrackingHelper 并开始发送测量数据。

确保将 TrackingHelper.java 复制到您应用中包含类文件的目录中，并替换此文件顶部的数据包名称，以与您的数据包结构 (com.company.application) 匹配。如果您希望在不使用 TrackingHelper 的情况下实施，可以在 TrackingHelper 中找到可复制到您应用程序的多个示例。

### 实施

1. 打开 TrackingHelper.java 并使用您的报表包 ID 和跟踪服务器更新 TRACKING_RSID 和 TRACKING_SERVER。例如：

   ```
   private static final String TRACKING_RSID = "rsid";
   private static final String TRACKING_SERVER = "server";
   ```

   这些值是必需的，并且必须进行更正，否则测量不起作用。如果不确定这些值，请咨询您的 SiteCatalyst 专家。

2. 找到 configureAppMeasurement 方法。这是启用 SSL、启用离线跟踪和对配置进行其他全局更改的位置。现在，取消行的注释以启用 debugLogging，直到事情按照您预期的方式运行。

3. 从应用程序的根活动添加对 configureAppMeasurement 的调用。

```
@Override
public void onCreate(Bundle savedInstanceState) {
super.onCreate(savedInstanceState);
setContentView(R.layout.main);
TrackingHelper.configureAppMeasurement(this);
}
```

这就是开始跟踪自定义量度所需的全部代码。但是，使用额外几行代码，您便可启用生命周期跟踪以自动发送生命周期量度，包括启动、升级、崩溃以及每日用户和每月用户。

AppMeasurement 库会执行所有繁琐的工作，您只需要向应用程序的每个活动类添加两个方法调用即可。

### （推荐）跟踪生命周期事件

启用生命周期跟踪后，每次启动应用程序时，都会发送一次点击以跟踪安装、升级、参与天数和其他生命周期指标。

要开始跟踪生命周期事件，请在您的应用程序中，将对 onResume() 和 onPause() 方法的调用添加到应用程序的每个活动中，如下例所示。我们还建议将 Activity 或 Service 作为上下文对象（而非全局应用程序上下文）传递。

```
@Override
protected void onResume() {
super.onResume();
TrackingHelper.startActivity(this);
}
@Override
protected void onPause() {
super.onPause();
TrackingHelper.stopActivity();
}
```

就这么简单！现在，您已经在 Android 应用程序中实施了基本的生命周期跟踪。网页分析师配置 SiteCatalyst 以处理报告的 AppMeasurement 量度后，SiteCatalyst 报表包将包含默认的生命周期量度。

下一步：

* （可选）跟踪自定义事件。将自定义方法添加到 TrackingHelper 以跟踪要在应用程序中测量的所有事件。您可以添加方法来跟踪登录、应用程序内购买等。
* （可选）跟踪应用程序状态。应用程序状态与页面查看类似。此部分向您展示如何将自定义方法添加到 TrackingHelper 以跟踪应用程序状态。
* 视频测量快速入门. 添加代码以跟踪视频量度，包括视频查看次数、总播放时间和最受欢迎的视频。

### （可选）跟踪自定义事件

自定义事件是您的应用程序所独有的成功量度。您可以在用户登录、启动应用程序内购买或点击 Facebook 页面链接时发送自定义事件。跟踪帮助程序类包含显示如何跟踪自定义事件的示例。您可以将此方法用作模板来添加其他事件跟踪方法。

在 TrackingHelper.java 中，定义一个自定义事件跟踪方法：

```
public static void trackCustomEvents () {
Hashtable<String, Object> contextData = new Hashtable<String, Object>();
contextData.put("contextKey", "value");
measure.trackEvents("event1, event2", contextData);
}
```

在您的整个代码中，您可以调用此方法以跟踪自定义事件：

`TrackingHelper.trackCustomEvents();`

使用此步骤您可以根据需要添加各种事件跟踪方法。TrackingHelper 的简介包含跟踪登录事件的示例方法。

### （可选）跟踪应用程序状态

跟踪帮助程序类还包含显示如何跟踪应用程序状态的示例。跟踪自定义状态与跟踪事件非常相似，唯一的区别在于使用的是 trackAppState 方法，而不是 trackEvents 方法。

```
measure.trackAppState("name", contextData);
```

从报表方面来看，trackAppState 会增加页面查看的次数，而 trackEvents 则不会。

## 视频测量快速入门

有关视频测量的介绍，可以参阅在 SiteCatalyst 中测量视频指南。在所有 AppMeasurement 平台中，测量视频的大概过程都非常相似。此快速入门部分提供开发人员任务的基本概述以及代码示例。

应用程序和视频跟踪使用的是相同的库 admsAppLibrary.jar。文档中将这些方法统称为媒体模块，以保持平台之间的一致性。

您需要配置一个测量实例，才能使用媒体模块。

要在 Android 上实施视频跟踪，请完成以下任务：

* 将播放器事件映射到 SiteCatalyst 变量
* 配置里程碑、区段和调用频率
* 跟踪播放器事件

### 将播放器事件映射到 SiteCatalyst 变量

要配置视频测量，需要将为视频跟踪选择的 SiteCatalyst 事件和 eVar 映射到上下文数据变量。有关更多信息，请参阅 SiteCatalyst 视频配置。

网页分析师应向您提供视频实施工作表，其中包含他们为接收视频数据而配置的 SiteCatalyst 变量列表：

* 视频名称(eVar):eVar2
* 视频名称(Prop):prop2
* 区段(eVar):eVar3
* 内容类型(eVar):eVar1
* 视频时间（事件）:event3
* 视频查看（事件）:event1
* 视频完成（事件）:event7
* 视频区段查看（事件）:event2

1. 将下面的代码添加到您在实施中添加的代码之后，将您选择的 SiteCatalyst 变量替换为代码中的示例：

   ```
   ADMS_MediaMeasurement mediaMeasure = ADMS_MediaMeasurement.sharedInstance();
   Hashtable<String, Object> contextDataMapping = new Hashtable<String, Object>();
   contextDataMapping.put("a.media.name", "eVar2,prop2");
   contextDataMapping.put("a.media.segment", "eVar3");
   contextDataMapping.put("a.contentType", "eVar1"); //note that this is not in the .media
   namespace
   contextDataMapping.put("a.media.timePlayed", "event3");
   contextDataMapping.put("a.media.view", "event1");
   contextDataMapping.put("a.media.segmentView", "event2");
   contextDataMapping.put("a.media.complete", "event7");
   mediaMeasure.ContextDataMapping = contextDataMapping;
   ```

2. 配置里程碑、区段和调用频率.

3. 跟踪播放器事件.


### 配置里程碑、区段和调用频率

里程碑允许您在视频达到特定点时发送一个事件。区段允许您将视频划分为多个部分，以用于更精细的跟踪。调用频率允许您发送以特定时间间隔查看的测量调用。有关更多信息，请参阅视频量度。

### 映射里程碑

您可以根据总长度的百分比或根据经过的秒数定义里程碑。此示例将里程碑定义为总长度的百分比。对于一个 2 分钟的视频，下面的代码在 30 秒、60 秒和 90 秒时发送里程碑事件。

```
Hashtable<String, Object> milestoneMapping = new Hashtable<String, Object>();
milestoneMapping.put("25", "event4");
milestoneMapping.put("50", "event5");
milestoneMapping.put("75", "event6");
contextDataMapping.put("a.media.milestones", milestoneMapping);
```


### 映射时间差里程碑

此示例以视频开始后所经过的秒数定义里程碑。对于一个 2 分钟的视频，下面的代码在 20 秒、40 秒和 60 秒时发送里程碑事件，而不管视频的总长度是多少。

```
Hashtable<String, Object> offsetMilestoneMapping = new Hashtable<String, Object>();
offsetMilestoneMapping.put("20", "event8");
offsetMilestoneMapping.put("40", "event9");
offsetMilestoneMapping.put("60", "event10");

contextDataMapping.put("a.media.offsetMilestones", offsetMilestoneMapping);
```

### 示例

```
//get sharedInstance
ADMS_MediaMeasurement mediaMeasure = ADMS_MediaMeasurement.sharedInstance();

//Track By Milestones:
mediaMeasure.trackMilestones = "25,50,75";

// track Milestones & segmentByMilestones:
mediaMeasure.trackMilestones = "25,50,75";
mediaMeasure.segmentByMilestones = true;

// track by seconds:
mediaMeasure.trackSeconds = 15;

// track Milestones & segmentByMilestones & seconds:
mediaMeasure.trackMilestones = "25,50,75";
mediaMeasure.segmentByMilestones = true;
mediaMeasure.trackSeconds = 15;

// track offsetMilestones & segmentByOffsetMilestones:
mediaMeasure.trackOffsetMilestones = "15,30,45,60,75,90";
mediaMeasure.segmentByOffsetMilestones = true;

// track offsetMilestones:
mediaMeasure.trackOffsetMilestones = "5,15,45";
```

### 跟踪播放器事件

要测量视频，需要添加代码，在播放器中发生事件时告知媒体模块（使用 open、play、stop 和 close 方法）。当用户开始播放视频时，您需要调用 play 方法，以便媒体模块开始计算查看的秒数。

如果用户暂停视频，则需要调用 stop，以便暂停计数。这通常使用播放器提供的事件处理程序执行。

例如：

加载：调用 open 和 play。

暂停：调用 stop。例如，如果用户在 15 秒后暂停视频，会调用 stop("Video1",15)。

缓冲：视频缓冲时调用 stop。恢复播放时调用 play。

继续：调用 play。例如，当用户继续之前播放了 15 秒的视频时，会调用 s.play("Video1",15)。

移动（滑块）：用户拖动视频滑块时，调用 stop。用户释放视频滑块时，调用 play。

结束：调用 stop，然后调用 close。例如，在 100 秒视频结束时，调用 stop("Video1",100)，然后调用 close("Video1")。

要完成此过程，您可以定义四个自定义函数，以从媒体播放器事件处理程序调用。传递到 open、play、stop 和 close 的各项参数均来自播放器。以下伪代码显示此过程：

```
function startMovie(){
mediaMeasure.open(mediaName,mediaLength,mediaPlayerName);
playMovie();
}
/*Call on video resume from pause and slider release*/
function playMovie(){
mediaMeasure.play(mediaName,mediaOffset);
}
/*Call on video pause and slider grab*/
function stopMovie(){
mediaMeasure.stop(mediaName,mediaOffset);
}
/*Call on video end*/
function endMovie(){
stopMovie();
mediaMeasure.close(mediaName);
Video Measurement Quick Start 12
```

## 生命周期量度

此工作表列出了启用自动生命周期跟踪时测量的量度和维度。

### 生命周期量度和维度

配置后，生命周期量度会在上下文数据参数中发送到 Analytics，随每个 mbox 调用在参数中发送到 Target，以及作为信号发送到受众管理。Analytics 和 Target 使用相同的格式，而受众管理则对每个量度使用不同的前缀。

对于 Analytics，将会使用在第一列中列出的量度或维度自动捕获并报告通过每个生命周期跟踪调用发送的上下文数据，“描述”列中另有说明的情况除外。

| 量度 | Analytics Context | Analytics Context Audience Manager信号说明 | 数据／目标参数 |
|--- |--- |--- |--- |
| 首次启动 | a.InstallEvent | c_a_InstallEvent | 安装（或重新安装）后首次运行时触发。 |
| 升级 | a.UpgradeEvent | c_a_UpgradeEvent | 在升级后（随时更改版本号）首次运行时触发。 |
| 每日参与的用户 | a.DailyEngUserEvent | c_a_DailyEngUserEvent | 当特定的某天使用应用程序时触发。 |
| 每月参与的用户 | 每月参与的用户 | a.MonthlyEngUserEvent | 当特定的某月使用应用程序时触发。 |
| 启动 | a.LaunchEvent | c_a_LaunchEvent | 在每次运行时触发，包括崩溃次数和安装次数。 | 启动项当超出生命周期会话超时时，从后台恢复时也会触发启动项。 |
| 崩溃 | a.CrashEvent | c_a_CrashEvent | 当应用程序未能正常退出时触发。应用程序在崩溃后启动时发送事件（如果未调用 quit，则将应用程序视为崩溃）。 |
| 上一会话时长 | a.PreviousSessionLength | Cc_a_PreviousSessionLength | 上一会话的累计总时长，以秒为单位。 |

*注意：“每&#x200B;**日参与的用户**”和“每&#x200B;**月参与的用户**”不会自动存储在Analytics量度中。 您必须创建一个处理规则，以设置一个自定义事件来捕获这些量度。*

### 维度

| 量度 | Analytics 上下文数据/Target 参数 | Analytics Context Audience Manager信号 | 描述 |
|--- |--- |--- |--- |
| 安装日期 | a.InstallDate | c_a_InstallDate | 安装后首次启动的日期。YYYY/MM/DD |
| 升级 | a.UpgradeEvent | c_a_UpgradeEvent | 在升级后（随时更改版本号）首次运行时触发。 |
| 应用程序 ID | a.AppID | c_a_AppID | 采用以下格式存储应用程序名称和版本：`[AppName] [BundleVersion]`。例如，myapp 1.1. |
| 首次使用后的天数 | a.DaysSinceFirstUse | c_a_DaysSinceFirstUse | 自首次运行以来经过的天数。 |
| 每月参与的用户 | 每月参与的用户 | a.MonthlyEngUserEvent | 当特定的某月使用应用程序时触发。 |
| 启动 | a.LaunchEvent | c_a_LaunchEvent | 在每次运行时触发，包括崩溃次数和安装次数。 | 启动项当超出生命周期会话超时时，从后台恢复时也会触发启动项。 |
| 崩溃 | a.CrashEvent | c_a_CrashEvent | 当应用程序未能正常退出时触发。应用程序在崩溃后启动时发送事件（如果未调用 quit，则将应用程序视为崩溃）。 |
| 上一会话时长 | a.PreviousSessionLength | Cc_a_PreviousSessionLength | 上一会话的累计总时长，以秒为单位。 |
| 上次使用后的天数 | a.DaysSinceLastUse | c_a_DaysSinceLastUse | 上次使用后间隔的天数。 |
| 星期 | a.DayOfWeek | c_a_DayOfWeek | 应用程序启动的星期数。 |
| 小时 | a.HourOfDay | c_a_HourOfDay | 测量应用程序启动的小时。24 小时数字格式。用于时间分片以确定峰值使用时间。 |
| 操作系统版本 | a.OSVersion | c_a_OSVersion | 操作系统版本。 |
| 自上次升级后的天数 | a.DaysSinceLastUpgrade | c_a_DaysSinceLastUpgrade | 自应用程序版本号发生更改后间隔的天数。 |
| 自上次升级后的启动次数 | a.LaunchesSinceUpgrade | c_a_LaunchesSinceUpgrade | 自应用程序版本号发生更改后的启动次数。 |
| 设备名称 | a.DeviceName | c_a_DeviceName | 存储设备名称。 | iOS：以逗号分隔的 2 位数字字符串，用于识别 iOS 设备。第一个数字通常代表第几代设备，第二个数字通常表示设备系列的不同成员。有关常用设备名称的列表，请参阅 iOS 设备版本。 |
| 运营商名称 | a.CarrierName | c_a_CarrierName | 存储由设备提供的移动设备服务提供商的名称。 |
| 分辨率 | a.Resolution | c_a_Resolution | 宽 x 高（实际像素） |

*注意：自上&#x200B;**次升级起**，自上&#x200B;**次升级起的启动次数和运营**商名称&#x200B;****，不会自动存储在Analytics变量中。 You must create a processing rule to copy these values to an Analytics variable for reporting.*

## 上下文数据

上下文数据是将应用程序数据发送到收集服务器的首选方法。

您可以使用上下文数据变量发送 SiteCatalyst 中映射的名称值对，而无需明确将值分配给 prop 和 eVar。根据这些键值对，您可以设置事件、将值复制到eVar和prop并执行其他条件语句。 这有助于避免代码更新后支持不同的报表包配置。

有两种方式可以使用跟踪方法发送上下文数据。所有直接在 PersistentContextData 对象上设置的上下文数据都随每次调用进行发送。您还可以将上下文数据作为一个参数传递到单次跟踪调用，并仅随该调用进行发送。

### Persistent Context Data

永久性上下文数据中放置的值会随每次服务器调用进行发送。在下面的示例中，"key" 和 "value" 随所有 trackAppState 调用进行发送：

```
Hashtable<String, Object> contextData = new HashTable<String,Object>();
contextData.put("key", "value");
measure.setPersistentContextData(contextData);
measure.trackAppState("state1");
measure.trackAppState("state2");
measure.trackAppState("state3");
```

### 单次调用上下文数据

要对单次调用发送上下文数据，请将 contextData 作为一个参数发送到跟踪调用（trackAppState、trackEvents 等）。

在下面的示例中，"key" 和 "value" 随全部的三次 trackAppState 调用进行发送。但是，"key2" 和 "value2" 则仅随第二次 trackAppState 调用发送：

```
Hashtable<String, Object> contextData = new HashTable<String,Object>();
contextData.put("key", "value");
measure.setPersistentContextData = contextData;
Hashtable<String, Object> contextDataState = new HashTable<String,Object>();
contextDataState.put("key2", "value2");
measure.trackAppState("state1");
measure.trackAppState("state2", contextDataState);
measure.trackAppState("state3");
```

## 配置变量

应用程序启动时可设置下列变量:

*注意：除ReportSuiteID和trackingServer外，所有配置变量都是可选的。*

**共享实例**

在进行测量调用之前，必须在测量库中为您调用的每种方法检索库的实例：

```
ADMS_Measurement measure = ADMS_Measurement.sharedInstance(((Activity)
context).getApplication());
```

*注意：配置变量是专用变量。使用 get 和 set 方法可更改这些值。*

### 配置变量

**reportSuiteID**:（必需）要跟踪的报表包或报表包（多报表包标记）。 要跟踪多个报表包，请传递各个报表包以逗号分隔的名称列表。

您无法针对单次调用覆盖此变量，必须更改永久值。

语法：

```
String getReportSuiteIDs()
void setReportSuiteIDs(String reportSuiteIDs)
```

示例:

`measure.setReportSuiteIDs("rsid");`

多包标记:
`measure.setReportSuiteIDs("rsid1, rsid2");`

**trackingServer**:（必需）标识集合服务器。

应当使用您的跟踪服务器域（不含“http://”或“https://”协议前缀）填充此变量。协议前缀将由库根据 ssl 变量自动处理。

如果 ssl 为 true，则对此服务器进行安全连接。如果 ssl 为 false，则对此服务器进行非安全连接。

您无法针对单次调用覆盖此变量，必须更改永久值。

语法：

```
String getTrackingServer()
void setTrackingServer(String trackingServer)
```

示例:

`measure.setTrackingServer("metrics.corp1.com");`

**visitorID**:默认：uuid每个访客的唯一标识符。 如果您不设置自定义 visitorID，则会生成唯一的 visitorID。

我们推荐您使用默认设置，除非您需要在特定的情况下设置 visitorID。设置自定义 visitorID 可能在使用生命周期跟踪时造成重复的访问。为避免出现这种情况，请在配置 App Measurement 前设置访客 ID。

**characterSet**:默认为UTF-8

语法：

```
String getCharSet()
void setCharSet(String charSet)
```

示例:
`[measure.setCharacterSet("UTF-8");`

**currencyCode**：默认值为none（使用为报表包定义的值）

用于 Android 应用程序中所跟踪的购买或货币事件的货币代码。

语法：

```
String getCurrencyCode()
void setCurrencyCode(String currencyCode)
```

示例:
`measure.setCurrencyCode("USD");`

**lifecycleSessionTimeout**:默认为5分钟

指定应用程序在后一次启动时，必须与前一次启动间隔多长时间，才能被视为新会话（以秒为单位）。此超时也适用于应用程序被发送到后台后又重新启用的情况。会话时间长度不包括应用程序在后台中运行的时间。

语法：

```
int getLifecycleSessionTimeout()
void setLifecycleSessionTimeout(int sessionLength)
```

示例:

`measure.setLifecycleSessionTimeout(600); //10 minute session`

**ssl**:默认值为false

启用 (true) 或禁用 (false) 通过 SSL (HTTPS) 发送测量数据的功能。您无法针对单次调用覆盖此变量，必须更改永久值。

语法：

`void setSSL(boolean ssl)`

示例:

`measure.setSSL(true);`

**debugLogging** Default为false

启用 (true) 或禁用 (false) 查看输出控制台中调试信息和库版本的功能。默认情况下，此变量为 false。您无法针对单次调用覆盖此变量，必须更改永久值。

语法：

`void setDebugLogging(boolean debugLogging)`

示例:

`measure.setDebugLogging(true);`

## 跟踪变量

**共享实例**

在进行测量调用之前，必须在测量库中为您调用的每种方法检索库的实例：

```
ADMS_Measurement measure = ADMS_Measurement.sharedInstance(((Activity)
context).getApplication());
```

*注意：配置变量是专用变量。使用 get 和 set 方法可更改这些值。*

### 永久跟踪变量

**Evar**:将指定的eVar设置为提供的值。 eVar 随所有跟踪调用发送，直到将其设置为空字符串或通过调用 ClearVars 清除。

语法：

`void setEvar(int evarNum, String evarValue)`

示例:
`measure.setEvar(1, "value");`

**Prop**:将指定的prop设置为提供的值。 prop 随所有跟踪调用发送，直到将其设置为空字符串或通过调用 clearVars 清除。

语法：

`void setProp(int propNum, String propValue)`

示例：

`measure.setProp(1, "value");`

**Hier**:将指定的heir变量设置为提供的值。 heir 变量随所有跟踪调用发送，直到将其设置为空字符串或通过调用 clearVars 清除。

语法：

`void setHier(int hierNum, String hierValue)`

示例：

`measure.setHier(1, "value");`


**ListVar**:将指定的listVar设置为提供的值。 listVar 随所有跟踪调用发送，直到将其设置为空字符串或通过调用 clearVars 清除。

语法：

`void setListVar(int listNum, String listValue)`

示例：

`measure.setListVar(1, "value");`

**purchaseID**:purchaseID用于防止SiteCatalyst对订单进行多次计数。

每次在网站上使用购买事件时，都应使用 purchaseID 变量为此购买分配一个唯一 ID。

`measure.setPurchaseID("unique_id");`

**transactionID**:集成数据源使用交易ID将离线数据绑定到在线交易（如在线生成的潜在客户或购买）。

每个发送到 Adobe 的唯一 transactionID 均会被记录，以备该交易离线信息的数据源上载。

`measure.setTransactionID("unique_id");`

**appState**:（页面名称）为应用程序状态提供的值存储在页面名称变量中。

`measure.setAppState("state");`

**channel**:measure.setChannel("mobile");

**appSection**:为应用程序部分提供的值存储在服务器变量中。

语法：

`void setAppSection(String Section)`

示例:
`measure.setAppSection("news");`

**campaign**

语法：

`void setCampaign(String Campaign)`

示例：

`measure.setCampaign("112233");`

**产品**

语法：

```
void setProducts(String Products)
// example Products string: Category;Product[,Category;Product]
```

示例：

`measure.setProducts("Running;Shoe");`

**events**

语法：

`void setEvents(String Event) //comma-delimited list`

示例：

`measure.setEvents("event1, event2");`

**geoState**

语法：

`void setGeoState(String GeoState)`

示例：

`measure.setGeoState("UT");`

**geoZip**

语法：

`void setGeoZip(String GeoZip)`

示例：

`measure.setGeoZip("12345");`

**永久上下文数据**:放置在永久上下文数据中的值会随每次服务器调用发送。 要发送单次调用的上下文数据，请将 contextData hashtable 作为一个参数发送到跟踪调用（trackAppState、trackEvents 等）。

示例：

```
Hashtable contextData = new Hashtable<String, Object>();
contextData.put("key", "value");
measure.setPersistentContextData(contextData);
```

请参阅上下文数据。

**linkTrackVars**:以逗号分隔的变量名称列表，可限制用于链接跟踪的当前变量集。 如果未定义 linkTrackVars，AppMeasurement for Android 通过 trackLink 调用发送所有定义的变量。

语法：

`void setLinkTrackVars(String Vars) //comma-delimited list`

示例：

`measure.setLinkTrackVars("eVar1, prop1");`

**linkTrackEvents**:限制用于链接跟踪的当前事件集的事件列表（以逗号分隔）。 如果未定义 linkTrackEvents，AppMeasurement for Android 通过 trackLink 调用发送所有事件。

语法：

`void setLinkTrackEvents(String Events) //comma-delimited list`

示例：

`measure.setLinkTrackEvents("event1, event2");`

## 方法

此部分列出了 Android 库提供的一些方法。

**共享实例**

在进行测量调用之前，必须在测量库中为您调用的每种方法检索库的实例：

```
ADMS_Measurement measure = ADMS_Measurement.sharedInstance(((Activity)
context).getApplication());
```

### 初始配置

此方法配置必要的变量，并且必须在其他方法之前调用。

**configureMeasurement**:该方法用于配置启动应用程序测量所需的两个参数。 您必须在发送任何服务器调用之前，使用此方法设置测量对象上的 reportSuiteIDs 和 trackingServer 值。

语法：

`void configureMeasurement(String reportSuiteIDs, String trackingServer)`

示例:

`measure.configureMeasurement("my_rsid", "my_tracking_server");`

### 事件和状态跟踪

这些是用于跟踪自定义事件和应用程序状态的主要方法。

**trackAppState**:这是跟踪应用程序中应用程序状态的推荐方法。 appState 中提供的值显示为服务器调用的页面名称变量。必须针对每次调用提供 appState 字符串，因为它不会传递到下一次调用。

随此调用发送的上下文数据会附加到 persistentContextData 中的任何值，并随调用发送。仅 persistentContextData 中设置的值保留用于下一次调用。

语法：

`void trackAppState(string AppStateName)`

示例:

`measure.trackAppState("state");`

```
Hashtable contextData = new Hashtable<String, Object>();
contextData.put("key", "value");
measure.trackAppState("state", contextData);
```

**trackEvents**:这是跟踪应用程序中事件的推荐方法。 trackEvents与trackAppState类似，但会发送事件而不是页面名称。 事件以逗号分隔字符串的形式提供。必须针对每次调用提供 events 字符串，因为它不会传递到下一次调用。

此方法对trackLinkURL进行基础调用，其中linkURL设置为nil,linkType设置为“o”，并使用应用程序ID填充linkName。

这意味着 linkTrackVars 和 linkTrackEvents 将应用于对 trackEvents 的调用。

随此调用发送的上下文数据会附加到 persistentContextData 中的任何值，并随调用发送。仅 persistentContextData 中设置的值保留用于下一次调用。

语法：

`void trackEvents(string Events)`

示例:

`measure.trackEvents("event1");`

```
Hashtable<String, Object> contextData = new HashTable<String,Object>();
contextData.put("key", "value");
measure.trackEvents("event1", contextData);
```

**如果使用 trackLink 方法，请导入注释**

trackEvents 对 trackLink 进行基本调用，其中 linkURL 设置为 null，linkType 设置为 "o"，而 linkName 使用应用程序 ID 进行填充。这样做是为了防止每次发送事件时，页面查看（状态查看）计数都会递增一次。

如果您直接调用 trackLink 并设置 linkTrackVars 和 linkTrackEvents 的值，这些变量和事件限制将应用于 TrackEvents。这意味着仅这些列表上定义的变量和事件随 TrackEvents 发送。除非您想将那些限制应用于 trackEvents，否则您应该将 linkTrackVars 和 linkTrackEvents 设置为 null。

### 高级跟踪（Track 和 TrackLink）

这两种方法提供其他跟踪选项，允许您直接填充 prop、eVar 和其他 SiteCatalyst 变量。这两种方法应该由具有现有实施的客户或非常熟悉其他 SiteCatalyst 实施的客户使用。

`track` 和 `trackLink` 是跨多个平台在所有版本的 Adobe 测量库中实施的核心测量方法。在大多数情况下，当跟踪移动应用程序时，使用 trackAppState 和 trackEvents 方法比直接调用 track 和 trackLink 更为简单。

页面查看跟踪 (track) 和链接跟踪 (trackLink) 会发送所有赋值（非 null 值、非空值、非零值）的永久变量。在调用 track 或 trackLink 之前，应根据需要重置或清空所有变量。

*注意：由于现代应用程序的多线程性质，不建议设置永久变量值以随将来的跟踪调用一起发送（使用setEvar、setProp、setHier、SetListVar和setPersistentContextData）。 例如，如果在多线程中设置了变量值，则执行跟踪调用时，该值可能处于不一致的状态。 为避免出现这种情况，我们建议您在每次跟踪调用时传递上下文数据，并在处理规则中设置变量值。

**方法描述**

**track**:将标准页面视图以及在测量对象上设置的任何其他变量一起发送到集合服务器。

对 track 的每次调用都会发送测量对象上定义的所有永久数据（这些数据都在 clearVars 的描述中列出），以及任何 contextData 或仅为该调用提供的变量。如果您发送一个定义的变量，则会覆盖相应永久变量中的任何值。

语法：

```
void track()
void track(Hashtable<String, Object> contextData)
void track(Hashtable<String, Object> contextData, Hashtable<String, Object>
variables)
```

示例:

`measure.track();`

```
measure.setEvar(1, "evar1value");
Hashtable contextData = new Hashtable<String, Object>();
contextData.put("key", "value");
measure.track(contextData);
```

```
//set an eVar
measure.setEvar(1, "evar1value");
//contextData
Hashtable contextData = new Hashtable<String, Object>();
contextData.put("key", "value");
//variable overrides
Hashtable variableOverrides = new Hashtable<String, Object>();
variableOverrides.put("evar2", "evar2value");
//sends eVar1, eVar2 (set in overrides), and context data
measure.track(contextData, variableOverrides);
```

**trackLink**:将自定义、下载或退出链接数据连同任何具有值的trackconfig变量一起发送到Adobe数据收集服务器。

使用 trackLink 跟踪不应捕获页面查看的所有活动。

语法：

```
void trackLink(String linkURL, String linkType, String linkName,
Hashtable<String, Object> contextData, Hashtable<String, Object> variables)
```

**linkURL**：识别已点击的 URL。若未指定任何 URL，则会使用名称。仅在从 Android 应用程序内链接至网页时，才使用该参数。否则，请为该参数传递 null 值。

**linkType**：识别将显示 URL 或名称的链接报表。支持的值包括：
* “o”（自定义链接）
* “d”（文件下载）
* “e”（退出链接）

**linkName**：显示在链接报表中的名称。若未指定任何名称，则报表会使用 URL。

要收集数据，必须指定 linkURL 或 linkName 参数。当不使用这些参数、上下文数据或其他变量之一时，请传递null作为值。

示例:

`measure.trackLink("url", "o", "name", contextData, null);`

**setEvar**:将指定的eVar设置为提供的值。 eVar 随所有跟踪调用发送，直到将其设置为空字符串或通过调用 ClearVars 清除。

语法：

`void setEvar(int evarNum, String evarValue)`

**setProp**:将指定的prop设置为提供的值。 prop 随所有跟踪调用发送，直到通过将其设置为空字符串或通过调用 ClearVars 将其清除。

语法：

`void setProp(int propNum, String propValue)`

**setHier**:将指定的heir变量设置为提供的值。 heir 变量随所有跟踪调用发送，直到通过将其设置为空字符串或通过调用 ClearVars 将其清除。

语法：

`void setHier(int hierNum, String hierValue)`

**setListVar**:将指定的listVar设置为提供的值。 listVar 随所有跟踪调用发送，直到通过将其设置为空字符串或通过调用 ClearVars 将其清除。

语法：

`void setListVar(int listNum, String listValue)`

**setPersistentContextData**:放置在永久上下文数据中的值会随每次服务器调用发送。 要发送单次调用的上下文数据，请将 contextData hashtable 作为一个参数发送到跟踪调用（trackAppState、trackEvents 等）。

```
Hashtable<String, Object> contextData = new HashTable<String,Object>();
contextData.put("key", "value");
measure.setPersistentContextData(contextData);
```

请参阅上下文数据。

**clearVars**:从对象的以下变量中删除值：

```
props
eVars
heirs
listVars
events
PersistentContextData
purchaseID
transactionID
appState
channel
appSection
campaign
products
geoZip
geoState
linkTrackVars
linkTrackEvents
```

语法：

`void clearVars()`

示例:
`measure.clearVars();`

**离线跟踪**

*注意：要启用离线 AppMeasurement，报表包必须启用时间戳。*

下面的变量允许您在应用程序离线时存储测量调用。要启用离线 AppMeasurement，报表包必须启用时间戳。进行此更改后，所有点击都必须盖上时间戳，否则将被丢弃。如果当前将 AppMeasurement 数据报告给还收集 JavaScript 数据的报表包，那么可能需要为离线 AppMeasurement 设置单独的报表包以避免数据丢失。

启用后，离线 AppMeasurement 按照下面的方式运行：
* 应用程序发送服务器调用，但是数据传输失败。
* AppMeasurement 生成当前点击时间戳。
* AppMeasurement 缓冲点击数据，并将缓冲的点击数据备份为永久存储以避免数据丢失。

AppMeasurement 在每次后续点击时或经过 offlineThrottleDelay 定义的间隔后，尝试发送缓冲的点击数据，并保持原始点击顺序。如果数据传输失败，它会继续缓冲点击数据（这在设备离线时仍继续）。

### 配置方法

**setOfflineTrackingEnabled**:默认值为false。 启用或禁用对测量库的离线跟踪。

语法：

`void setOfflineTrackingEnabled(boolean Enabled);`

示例：“measure.setOfflineTrackingEnabled(true);

**setOfflineHitLimit**:默认为1000。 队列中存储的离线点击的最大数量。如果点击限制设置为超过 5000 的值，性能可能会受到影响。

语法：

`void setOfflineHitLimit(int offlineHitLimit)`

示例:

`measure.setOfflineHitLimit(2000);`

**getTrackingQueueSize**:返回脱机队列中存储的跟踪调用数。

语法：

`int getTrackingQueueSize()`

示例:

`int size = measure.getTrackingQueueSize();`

**clearTrackingQueue**:从脱机队列中删除所有存储的跟踪调用。

语法：

`void clearTrackingQueue()`

示例:

`measure.clearTrackingQueue();`

**警告：手动清除队列时请务必谨慎，因为此操作无法还原。**


**setOnline和setOffline**:手动设置测量对象的联机或脱机状态。 库会自动检测设备离线或在线，因此仅在希望强制离线测量时才需要使用这两种方法。SetOnline 仅用于在手动离线后恢复到在线状态。

离线测量时：

* 如果 offlineTrackingEnabled 为 true：会存储点击量，直到测量在线。
* 如果 offlineTrackingEnabled 为 false：会放弃点击量。

语法：

```
void setOnline()
void setOffline()
```

示例:

```
measure.setOffline();
measure.setOnline();
```

## 离线跟踪

您可以使用 AppMeasurement 来测量应用程序的使用情况，在 Android 设备离线时同样可以工作。

*注意：要启用离线 AppMeasurement，报表包必须启用时间戳。*

请参阅离线跟踪。

## Target

Adobe 提供了在 Android 应用程序内传输目标内容的功能。

从 Test&amp;Target 返回的内容可以为任何基于文本的内容，例如 HTML、XML 或纯文本。加载内容后，则由 Android 应用程序开发人员决定如何在应用程序内使用内容。内容可以显示为 HTML，或用于更改应用程序的行为。本指南提供 Test&amp;Target 类的简单使用示例。

要求

* JDK 5/6/7
* Android SDK for Platform 1.5 或更新版本。

此部分中的示例以 Eclipse 为基础。

**获取库**

访问 Developer Connection 上的测量和优化移动设备应用程序以下载 Android 库。

解压缩下载文件，其中会包含以下软件组件：

* admsAppLibrary.jar：专门与 Android 设备及模拟器搭配使用的库。需要 Android 2.0 或更高版本。
* Examples\TrackingHelper.java：旨在将跟踪代码与应用程序逻辑分离的可选类。

**将库添加到项目**

1. 在 Eclipse IDE 中，右键单击项目名称。
1. 选择生成路径 &gt; 添加外部存档。
1. 选择 admsAppLibrary.jar。
1. 单击打开。
1. 再次右键单击项目，然后选择生成路径&gt;配置生成路径。
1. 单击订购和导出选项卡。
1. 确保选择 admsAppLibrary.jar。

您的应用程序可以使用 .*; 从 `importcom.adobe.ADMS.*;`admsAppLibrary.jar 库导入类/界面

**添加应用程序权限**

AppMeasurement 库需要以下权限来发送数据和记录离线跟踪调用：

* INTERNET
* ACCESS_NETWORK_STATE

要添加这些权限，请将以下行添加到 AndroidManifest.xml 文件（位于应用程序项目目录中）：

```
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

示例

在将库添加到项目并添加应用程序权限后，您可以使用两个 Test&amp;Target 类：MboxFactory 和 Mbox。

下面的示例展示如何在一个简单的 Android 应用程序内从 Test&amp;Target 将 HTML 内容加载到 WebView。此示例假定 Test&amp;Target 管理工具中已创建了关联的 HTML 产品和促销活动，并且促销活动已获得批准。

1. 完成实施中的步骤，然后在应用程序或活动子类的顶部导入 testandtarget 数据包：

   `com.adobe.adms.testandtarget.*;`

2. 遵循下列已编号代码以创建 mbox（有关每行代码的解释，请参阅注释）。要完成此步骤，您需要知道您的客户端代码和 Test&amp;Target 管理工具中促销活动设置使用的 mbox 名称。

   ```
   public class AndroidDemoApplication extends Activity {
   private WebView _webView;
   public void onCreate(Bundle savedInstanceState) {
   super.onCreate(savedInstanceState);
   _webView = new WebView(this);
   setContentView(_webView);
   // 1. Create an instance of the MboxFactory class with your client code.
   MboxFactory factory = new MboxFactory("androiddemo16");
   // 2. Use the MboxFactory instance to create an Mbox.
   Mbox mbox = factory.create("DemoApp");
   // 3. Set the default content for the Mbox.
   mbox.setDefaultContent("<h1>DEFAULT CONTENT</h1>");
   /**
   * 4. Create a custom MboxContentConsumer to consume the content returned. The
   * CustomMboxContentConsumer class defined below simply displays the content
   * returned in a BrowserField as HTML.
   */
   CustomConsumer consumer = new CustomConsumer(_webView);
   mbox.addOnLoadConsumer(consumer);
   // 5. Load the Mbox.
   mbox.load();
   ...
   ```

3. 定义实施 MboxContentConsumer 界面的自定义类。此抽象界面仅需要您定义名为“consume”的方法以向其传递内容。下面定义的 CustomConsumer 类仅显示 WebView 中的内容。

   ```
   class CustomConsumer implements MboxContentConsumer {
   private WebView _view;
   public CustomConsumer(WebView webview) {
   _view = webview;
   }
   public void consume(String content) {
   _view.loadData(content, "text/html", "utf-8");
   }
   }
   ```

4. 右键单击您的项目，然后选择运行为&gt; Android 应用程序，以生成和测试您的应用程序。如果正确设置并批准了 Test&amp;Target 活动，则应该看到您的产品显示在 Android 设备模拟器中。

**生命周期量度**

如果已启用生命周期量度，则会将生命周期量度作为参数发送到每个 mbox 加载。

* （推荐）跟踪生命周期事件
* 生命周期量度

## 受众管理

Adobe 提供了从受众管理中发送信号和检索访客区段的功能。

### 要求

* JDK 5/6/7
* Android SDK for Platform 1.5 或更新版本。

此部分中的示例以 Eclipse 为基础。

### 获取库

访问 Developer Connection 上的测量和优化移动设备应用程序以下载 Android 库。

解压缩下载文件，其中会包含以下软件组件：

* admsAppLibrary.jar：专门与 Android 设备及模拟器搭配使用的库。需要 Android 2.0 或更高版本。
* Examples\TrackingHelper.java：旨在将跟踪代码与应用程序逻辑分离的可选类。

### 将库添加到项目

1. 在 Eclipse IDE 中，右键单击项目名称。
1. 选择生成路径 &gt; 添加外部存档。
1. 选择 admsAppLibrary.jar。
1. 单击打开。
1. 再次右键单击项目，然后选择生成路径&gt;配置生成路径。
1. 单击订购和导出选项卡。
1. 确保选择 admsAppLibrary.jar。

您的应用程序可以使用 .*; 从 `importcom.adobe.ADMS.*;`admsAppLibrary.jar 库导入类/界面

### 添加应用程序权限

AppMeasurement 库需要以下权限来发送数据和记录离线跟踪调用：
* INTERNET
* ACCESS_NETWORK_STATE

要添加这些权限，请将以下行添加到 AndroidManifest.xml 文件（位于应用程序项目目录中）：

```
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

### 代码示例

在将库添加到项目后，您可以使用 ADMS_AudienceManager 类。To import the audience manager package add: `import com.adobe.adms.audiencemanager;`

1. 配置受众管理：

   `ADMS_AudienceManager.ConfigureAudienceManager("mycompany.demdex.net", this);`

   将 mycompany.demdex.net 替换为您的端点。受众管理可在您应用程序中的任何端点进行配置。


2. （可选）设置 dpid 和 dpuuid。

   `ADMS_AudienceManager.SetDpidAndDpuuid("284", "abc123");`

3. 创建一个特质字典，并在信号中提交该字典。

```
HashMap<String, Object> data = new HashMap<String, Object>();
data.put("trait", "b");
ADMS_AudienceManager.SubmitSignal(data, new
ADMS_AudienceManager.AudienceManagerCallback<HashMap>() {
@Override
public void call(HashMap visitorProfile) {
// do things with visitorProfile
}
});
```

访客资料字典将在回调中作为 content 参数返回。

### 生命周期量度

如果启用了生命周期量度并在 application:didFinishLaunchingWithOptions: 中配置了受众管理，则在配置完成后将发送一个包含生命周期量度的信号。

* （推荐）跟踪生命周期事件
* 生命周期量度

### ADMS_AudienceManager 引用

**方法**

**配置AudienceManager**:设置受众管理端点。

语法：

`public static void ConfigureAudienceManager(String server, Context context);`

示例：

`ADMS_AudienceManager.ConfigureAudienceManager("mycompany.demdex.net", this);`

**GetDebugLogging**:返回布尔值，指示Audience manager方法是否将在控制台中提供调试日志记录。

语法：

`public static boolean GetDebugLogging();`

**GetDpid**:返回dpid。

语法：

`public static String GetDpid();`

**GetDpuuid**:返回dpuuid。

语法：

`public static String GetDpuuid();`

**GetVisitorProfile**:在您提交信号以检索最近的访客资料后，可以随时调用此方法。

访客资料包含在 stuff 对象中返回的所有键值对。

语法：

`public static HashMap GetVisitorProfile();`

**SetDebugLogging**:在控制台中启用或禁用调试日志记录。

语法：

`public static void SetDebugLogging(boolean logging);`

**SetDpidAndDpuuid**:如果设置了newDpid和newDpuuid，则将随每个信号一起发送它们。

语法：

`public static void SetDpidAndDpuuid(String newDpid, String newDpuuid);`

**SubmitSignal**:发送到特征词典中，并在回调中接收更新的访客配置文件。

来自 JSON 响应的 uuid 存储在内部并用于所有后续信号。此外，还会向 dests 对象中找到的每个 URL 发送一个像素请求。

语法：

```
public static void SubmitSignal(HashMap<String, Object> data,
AudienceManagerCallback<HashMap> callback);
```

### 接口

**方法**


**AudienceManagerCallback**

语法：

```
public interface AudienceManagerCallback<T> {
AudienceManagerCallback
public void call(T item);
}
```

在从 SubmitSignal 调用进行的回调中使用的对象接口。


## PhoneGap 插件

使用该插件，您可以从 PhoneGap 项目发送 Android AppMeasurement 调用。

有关创建 PhoneGap 项目的帮助，请参阅 PhoneGap Android 入门指南。

要下载插件，请参阅适用于 SiteCatalyst 的 PhoneGap iOS 和 Android 插件。

### 包含插件

1. 将 ADMS_plugin.java 复制到 src 文件夹的数据包中。
2. 将 ADMS_Helper.js 复制到 PhoneGap 项目的 assets/www/js 文件夹中。
3. In the res/xml folder, open config.xml file and register an new plugin by creating a new child node under plugins: `<plugin name="ADMS_Plugin" value="[YOUR_PACKAGE_NAME].ADMS_plugin" />`

For example, if you package is named com.example.phonegaptest, then your plugin node would be the following: `<plugin name="ADMS_Plugin" value="com.example.phonegaptest.ADMS_plugin" />`

### 包含 AppMeasurement 库

要下载 AppMeasurement 库，请参阅获取库。

1. 将 admsAppLibrary.jar 复制到 PhoneGap 项目的 libs 文件夹中。
2. 通过右键单击 libs &gt;生成路径&gt;配置生成路径验证 admsAppLibrary.jar 是否位于您的生成路径中。
3. 在“库”选项卡中，如果列表中尚未包含库，请单击“添加JAR”，然后从库文件夹中选择admsAppLibrary.jar。


### 生命周期量度自动跟踪

跟踪生命周期量度需要在 PhoneGap 外部进行配置。要启用生命周期自动跟踪，请完成“开发人员快速入门”中的实施步骤。

### 使用插件

在要使用跟踪的 html 文件中，包括：

`<script type="text/javascript" src="js/ADMS_Helper.js"></script>`

完成，您现在已准备好进行测量调用。请参阅 PhoneGap 插件方法。

### 故障诊断

**我的语法正确，但是为什么无法获取插件中的代码？**

Check your output console for the following error: `java.lang.ClassNotFoundException: ADMS_plugin`

如果出现此错误，请确保在“包括插件”部分执行了步骤3。

## PhoneGap 插件方法

在要使用这些方法的 html 文件中，包括：

`<script type="text/javascript" src="js/ADMS_Helper.js"></script>`

**配置方法**


**configureMeasurementWithReportSuiteIDsTrackingServer**:该方法用于配置启动应用程序测量所需的两个参数。 您必须在发送任何服务器调用之前，使用此方法设置测量对象上的 reportSuiteIDs 和 trackingServer 值。

语法：

`void configureMeasurementWithReportSuiteIDsTrackingServer(stringreportSuiteIDs, string trackingServer);`

示例：

`ADMS.configureMeasurementWithReportSuiteIDsTrackingServer("testRSID","10.20.40.199:5050");`

**setOnline和setOffline**:手动设置测量对象的联机或脱机状态。 库会自动检测设备离线或在线，因此仅在希望强制离线测量时才需要使用这两种方法。SetOnline 仅用于在手动离线后恢复到在线状态。

离线测量时：

* 如果 offlineTrackingEnabled 为 true：会存储点击量，直到测量在线。
* 如果 offlineTrackingEnabled 为 false：会放弃点击量。

语法：

```
void setOnline();
void setOffline();
```

示例：

```
ADMS.setOnline();
ADMS.setOffline();
```

**setDebugLogging**:启用(true)或禁用(false)查看调试信息。 默认情况下，此变量为 false。

无法使用变量覆盖功能来覆盖此变量。

语法：

`void setDebugLogging(bool debugLogging);`

示例：

`ADMS.setDebugLogging(true);`

### 事件和状态跟踪方法


**trackAppState**:这是跟踪应用程序中的应用程序状态（例如，页面）的推荐方法。 appState 中提供的值显示为服务器调用的页面名称变量。必须针对每次调用提供 appState 字符串，因为它不会传递到下一次调用。

语法：

`void trackAppState(string stateName);`

示例：

`ADMS.trackAppState("login page");`

**trackAppStateWithContextData**:这是跟踪应用程序中的应用程序状态（例如，页面）的推荐方法。 appState 中提供的值显示为服务器调用的页面名称变量。必须针对每次调用提供 appState 字符串，因为它不会传递到下一次调用。

随此调用发送的上下文数据会附加到 persistentContextData 中的任何值，并随调用发送。仅 persistentContextData 中设置的值保留用于下一次调用。

语法：

`void trackAppStateWithContextData(string stateName, JSON cData);`

cData：在上下文数据中发送的具有键值对的 JSON 对象。

示例：

```
trackAppStateWithContextData("login page",
{"user":"john","remember":"true"});
```

**trackEvents**:这是跟踪应用程序中事件的推荐方法。 trackEvents与trackAppState类似，但会发送事件而不是页面名称。 事件以逗号trackEvents分隔的字符串形式提供。 必须针对每次调用提供 events 字符串，因为它不会传递到下一次调用。

此方法对trackLinkURL进行基础调用，其中linkURL设置为null,linkType设置为“o”，并使用应用程序ID填充linkName。

这意味着 linkTrackVars 和 linkTrackEvents 将应用于对 `trackEvents` 的调用。

语法：

`void trackEvents(string eventNames);`

示例：

`ADMS.trackEvents("login,event2");`

**如果使用 trackLink 方法，请导入注释**

`trackEvents` 对 trackLinkURL 执行基本调用，其中 linkURL 设置为 null，linkType 设置为 "o"，linkName 使用应用程序 ID 进行填充。这样做是为了防止每次跟踪事件时，页面查看（状态查看）计数都会递增一次。

如果您直接调用 trackLinkURL 并设置 linkTrackVars 和 linkTrackEvents 的值，这些变量和事件限制将应用于 TrackEvents。这意味着仅这些列表上定义的变量和事件随 TrackEvents 发送。除非您想将那些限制应用于 trackEvents，否则您应该将 linkTrackVars 和 linkTrackEvents 设置为 null。

**trackEventsWithContextData**:这是跟踪应用程序中事件的推荐方法。 trackEvents与trackAppState类似，但会发送事件而不是页面名称。 事件以逗号分隔字符串的形式提供。必须针对每次调用提供 events 字符串，因为它不会传递到下一次调用。

此方法对 trackLinkURL 执行基本调用，其中 linkURL 设置为 null，linkType 设置为 "o"，而 linkName 使用应用程序 ID 进行填充。

这意味着 linkTrackVars 和 linkTrackEvents 将应用于对 trackEvents 的调用。

随此调用发送的上下文数据会附加到 persistentContextData 中的任何值，并随调用发送。仅 persistentContextData 中设置的值保留用于下一次调用。

语法：

`void trackEventsWithContextData(string eventNames, JSON cData);`

cData：在上下文数据中发送的具有键值对的 JSON 对象。

示例：

`ADMS.trackEventsWithContextData("login,event2",
{"user":"john","remember":"true"});`

**如果使用 trackLink 方法，请导入注释**

trackEvents 对 trackLinkURL 执行基本调用，其中 linkURL 设置为 null，linkType 设置为 "o"，linkName 使用应用程序 ID 进行填充。这样做是为了防止每次跟踪事件时，页面查看（状态查看）计数都会递增一次。

如果您直接调用 trackLinkURL 并设置 linkTrackVars 和 linkTrackEvents 的值，这些变量和事件限制将应用于 TrackEvents。这意味着仅这些列表上定义的变量和事件随 TrackEvents 发送。除非您想将那些限制应用于 trackEvents，否则您应该将 linkTrackVars 和 linkTrackEvents 设置为 null。

**高级跟踪方法（Track 和 TrackLink）)**

这两种方法提供其他跟踪选项，允许您直接填充 prop、eVar 和其他 SiteCatalyst 变量。这两种方法应该由具有现有实施的客户或非常熟悉其他 SiteCatalyst 实施的客户使用。

`track` 和 `trackLink` 是跨多个平台在所有版本的 Adobe 测量库中实施的核心测量方法。在大多数情况下，当跟踪移动应用程序时，使用 trackAppState 和 trackEvents 方法比直接调用 track 和 trackLink 更为简单。

页面查看跟踪 (track) 和链接跟踪 (trackLink) 会发送所有赋值（非 null 值、非空值、非零值）的永久变量。在调用 track 或 trackLink 之前，应根据需要重置或清空所有变量。

**方法**

**track**:将标准页面视图以及在测量对象上设置的任何其他变量一起发送到集合服务器。

语法：

`void track();`

示例：

`ADMS.track();`

**trackWithContextData**:将标准页面视图以及在测量对象上设置的任何其他变量一起发送到集合服务器。

对 trackWithContextData 的每次调用都会发送测量对象上定义的所有永久数据（这些数据都在 clearVars 描述中列出），并发送您仅为该调用提供的任何 contextData。

语法：

`void trackWithContextData(JSON cData);`

cData：在上下文数据中发送的具有键值对的 JSON 对象。

示例：

`ADMS.trackWithContextData({"key1":"value1","key2":"value2"});`


**trackWith ContextDataAndVariables**:将标准页面视图以及在测量对象上设置的任何其他变量一起发送到集合服务器。

对 trackWithContextDataAndVariables 的每次调用都会发送测量对象上定义的所有永久数据（这些数据都在 clearVars 描述中列出），并发送您仅为该调用提供的任何 contextData 和变量。如果您发送一个定义的变量，则会覆盖相应永久变量中的任何值。

语法：

`void trackWithContextDataAndVariables(JSON cData, JSON vars);`

cData：在上下文数据中发送的具有键值对的 JSON 对象。

示例：

```
ADMS.trackWithContextDataAndVariables({"key1":"value1","key2":"value2"},
{"eVar1":"newValue","prop3":"newValue"});
```

**trackLinkURLWithLinkTypeName**:将自定义、下载或退出链接数据连同任何具有值的跟踪配置变量一起发送到Adobe数据收集服务器。

使用 trackLink 跟踪不应捕获页面查看的所有活动。

对 trackLinkURLWithLinkTypeNameContextDataVariables 的每次调用都会发送测量对象上定义的所有永久数据（这些数据都在 clearVars 描述中列出），并发送您仅为该调用提供的任何 contextData。

语法：

```
void trackLinkURLWithLinkTypeNameContextDataVariables(string`
linkUrl, string linkType, string linkName, JSON cData, JSON vars);
```

cData：在上下文数据中发送的具有键值对的 JSON 对象。

示例：

```
ADMS.trackLinkURLWithLinkTypeNameContextDataVariables("theLink",
"o", "logout", {"key1":"value1"}, {"eVar1":"newValue"});
```

### 设置和获取 AppMeasurement 变量

**方法**

**setEvarToValue**:将指定的eVar设置为提供的值。 eVar 随下一次跟踪调用发送。

语法：

`void setEvarToValue(int evar, string value);`

示例：

`ADMS.setEvarToValue(1, "newValue");`

**setPropToValue**:将指定的prop设置为提供的值。 prop 随下一次跟踪调用发送。

语法：

void setPropToValue(int prop, string value);

示例：

`ADMS.setPropToValue(1, "newValue");`

**setHierToValue**:将指定的hier变量设置为提供的值。 该变量随下一次跟踪调用发送。

语法：

`void setHierToValue(int hier, string value);`

示例：

`ADMS.setHierToValue(1, "newValue");`

**setListVarToValue**:将指定的listvar设置为提供的值。 listvar 随下一次跟踪调用发送。

语法：

`void setListVarToValue(int list, string value);`

示例：

`ADMS.setListVarToValue(1, "newValue");`

**getEvar**:获取指定的变量。

语法：

`void getEvar(int evar, function success, function fail);`

示例：

```
ADMS.getEvar(1, function (value) { myTempEvar1 = value; }, function ()
{ myTempEvar1 = null; });
```

**getProp**:获取指定的变量。

语法：

`void getProp(int prop, function success, function fail);`

示例：

```
ADMS.getProp(1, function (value) { myTempProp1 = value; }, function ()
{ myTempProp1 = null; });
```

**getHier**:获取指定的变量。

语法：

`void getHier(int hier, function success, function fail);`

示例：

```
ADMS.getHier(1, function (value) { myTempHier1 = value; }, function ()
{ myTempHier1 = null; });
```

**getListVar**:获取指定的变量。

语法：

`void getListVar(int list, function success, function fail);`

示例：

```
ADMS.getListVar(1, function (value) { myTempListVar1 = value; }, function
() { myTempListVar1 = null; });
```

**clearVars**:从对象的以下变量中删除值：

```
props
eVars
heirs
listVars
events
PersistentContextData
purchaseID
transactionID
appState
channel
appSection
campaign
products
geoZip
geoState
linkTrackVars
linkTrackEvents
```

语法：

`void clearVars();`

示例：

`ADMS.clearVars();`

**trackingQueueSize**:获取或设置脱机队列中存储的跟踪调用数。

语法：

`void trackingQueueSize(function success, function fail);`

示例：

`ADMS.trackingQueueSize(function (value) { myQueueSize = value; }, function () { myQueueSize = 0; });`

**clearTrackingQueue**:从脱机队列中删除所有存储的跟踪调用。 警告：手动清除队列时请务必谨慎，因为此操作无法还原。

语法：

`void clearTrackingQueue();`

示例：

`ADMS.clearTrackingQueue();`

### 设置和获取配置变量

**方法**

**getVersion**:获取库版本。

语法：

`void getVersion(function success, function fail);`

示例：

```
ADMS.getVersion(function (value) { versionNum = value; }, function ()
{ versionNum = 1.0; });
```

**setReportSuiteIDs**:（必需）要跟踪的报表包或报表包（多报表包标记）。 要跟踪多个报表包，请传递各个报表包以逗号分隔的名称列表。

您无法针对单次调用覆盖此变量，必须更改永久值。

语法：`void setReportSuiteIDs(string reportSuiteIDs);`

示例：

`ADMS.setReportSuiteIDs("rsid1, rsid2");`

**setTrackingServer**:（必需）标识集合服务器。

此变量应使用代码管理器中为您生成的值进行填充。

如果启用了 SSL，会将相同的值用于安全跟踪。

您无法针对单次调用覆盖此变量，必须更改永久值。

语法：

`void setTrackingServer(string trackingServer);`

示例：

`ADMS.setTrackingServer("10.23.52.191:5923");`

**setDataCenter**:

语法：

`void setDataCenter(string dataCenter);`

示例：

`ADMS.setDataCenter("myDataCenter");`

**setVisitorID**:默认值为CFUUID。

每位访客的唯一标识符。如果未设置自定义 visitorID，则会在初次启动时生成唯一的 visitorID（使用 Apple 的 CFUUID），然后将其存储在用户的默认密钥中。自此开始，AppMeasurement 和 PhoneGap 将使用该密钥。该密钥还会在标准应用程序备份过程中保存和还原。

语法：

`void setVisitorID(string visitorId);`

示例：

`ADMS.setVisitorID("myVisitorId");`

**setCharSet**:默认为UTF-8。

语法：

`void setCharSet(string charSet);`

示例：

`ADMS.setCharSet("UTF-8");`

**setCurrencyCode**:默认值为none（使用为报表包定义的值）。

用于 iOS 应用程序中所跟踪的购买或货币事件的货币代码。

语法：

`void setCurrencyCode(string currencyCode);`

示例：

`ADMS.setCurrencyCode("USD");`


**setSSLEnabled**:默认为false。

启用 (true) 或禁用 (false) 通过 SSL (HTTPS) 发送测量数据的功能。您无法针对单次调用覆盖此变量，必须更改永久值。

语法：

`void setSSLEnabled(bool sslEnabled);`

示例：

`ADMS.setSSLEnabled(false);`

### 设置和获取永久跟踪变量

**方法**

**setPurchaseID**:

语法：

`void setPurchaseID(string purchaseId);`

示例：

`ADMS.setPurchaseID("purchase1");`

**setTransactionID**:

语法：

`void setTransactionID(string transactionId);`

示例：

`ADMS.setTransactionID("transaction1");`

**setAppState**:

语法：

`void setAppState(string stateName);`

示例：

`ADMS.setAppState("myAppState");`

**setChannel**:

语法：

`void setChannel(string channel);`

示例：

`ADMS.setChannel("myChannel");`

**setAppSection**:

语法：

`void setAppSection(string appSection);`

示例：

`DMS.setAppSection("myAppSection");`

**setCampaign**:

语法：

`void setCampaign(string campaign);`

示例：

`ADMS.setCampaign("myCampaign");`

**setProducts**:

语法：

`void setProducts(string products);`

示例：

`ADMS.setProducts("myProduct1,myProduct2");`

**setEvents**:

语法：

`void setEvents(string events);`

示例：

`ADMS.setEvents("event1, event2");`

**setGeoState**

语法：

`void setGeoState(string state);`

示例：

`ADMS.setGeoState("FL");`

**setGeoZip**:

语法：

`void setGeoZip(string zip);`

示例：

`ADMS.setGeoZip("39984");`

**setPersistentContextData**:上下文数据是收集数据的推荐方式。 要发送上下文数据，请创建 JSON 对象并为要发送的值分配键值对。

语法：

`void setPersistentContextData(JSON cData);`

示例：

`ADMS.setPersistentContextData({"key1":"value1"});`

**persistentContextData**:

语法：

`void persistentContextData(function success, function fail);`

示例：

```
ADMS.persistentContextData(function(value) { alert(value); },
function(error) { alert(error); });
```

**setLinkTrackVars**:以逗号分隔的变量名称列表，可限制用于链接跟踪的当前变量集。

如果未定义 linkTrackVars，则 PhoneGap 插件通过 trackLink 调用发送所有定义的变量。

语法：

`void setLinkTrackVars(string linkTrackVars);`

示例：

`ADMS.setLinkTrackVars("eVar1,eVar2");`


**setLinkTrackEvents**:限制用于链接跟踪的当前事件集的事件列表（以逗号分隔）。 如果未定义 linkTrackEvents，则 PhoneGap 插件通过 trackLink 调用发送所有事件。

语法：

`void setLinkTrackEvents(string linkTrackEvents);`

示例：

`ADMS.setLinkTrackEvents("event1,loginEvent");`


**setLightTrackVars**:以逗号分隔的变量列表，可限制光跟踪调用的当前变量集。 通过简易服务器调用发送的此变量由 ClientCare 进行配置。

语法：

`void setLightTrackVars(string lightTrackVars);`

示例：

`ADMS.setLightTrackVars("prop1,hier3");`

### 离线跟踪

**方法**

**setOfflineTrackingEnabled**:

语法：

`void setOfflineTrackingEnabled(bool offlineTrackingEnabled);`

示例：

`ADMS.setOfflineTrackingEnabled(true);`

**setOfflineHitLimit**:

语法：

`void setOfflineHitLimit(int offlineHitLimit);`

示例：

`ADMS.setOfflineHitLimit(3000);`

## Android 2.x 到 3.x 版迁移指南

* AppMeasurement 现在为 ADMS_Measurement。找到引用此类的位置，并将名称更新为 ADMS_Measurement。
* getInstance 现在为 sharedInstance。找到调用 getInstance 的位置，并将其替换为 sharedInstance。
* 删除所有对流失量度 (getChurnInstance) 的调用。这些调用由自动跟踪处理，而变量现在使用上下文数据插入。
* 删除 Timestamp。库会自动处理时间戳。

以下方法的语法已发生更改。所有属性和方法的更新示例在 配置变量和方法。


### 报表包

**早期版本 (2.1.x)**

`account`

**新版本 (3.x)**

`reportSuiteIDs`

### Track

**早期版本 (2.1.x)**


`String track()`

`String track(Hashtable variableOverrides)`

**新版本 (3.x)**

为未使用的值传递 null。

```
void track()
void track(Hashtable<String, Object>
contextData)
void track(Hashtable<String, Object>
contextData, Hashtable<String, Object>
variables)
```

### 跟踪链接

**早期版本 (2.1.x)**

```
String trackLink(String linkURL, String
linkType, String linkName)
```

```
String trackLink(String linkURL, String
linkType, String linkName,
Hashtable variableOverrides)
```

**新版本 (3.x)**

这两个调用已替换为一个调用。为未使用的值传递 null。

```
void trackLink(String linkURL, String linkType,
String linkName,
Hashtable<String, Object> contextData,
Hashtable<String, Object> variables)
```

### 脱机跟踪方法

**早期版本 (2.1.x)**

`void forceOffline();`


`void forceOnline();`

**新版本 (3.x)**

`void setOnline();`

`void setOffline();`


### 重命名的变量

下表显示了版本 2.x 变量及其在版本 3.x 中的对应值。我们从版本 3.x 中删除了多个变量，以更注重库的移动性并简化实施。


*注意：3.x 版本使用 getter 和 setter，而不是公共变量。您需要在您的代码中更新直接设置变量的位置以使用 get 和 set 方法。*

```
timestamp; //Removed
trackOffline; //void setOfflineTrackingEnabled(boolean Enabled)
offlineLimit; //void setOfflineHitLimit(int offlineHitLimit)
account; //reportSuiteIDs
linkURL; //Removed (sent with linkTrackURL)
linkName; //Removed (sent with linkTrackURL)
linkType; //Removed (sent with linkTrackURL)
linkTrackVars; //void setLinkTrackVars(String Vars) //comma-delimited list
linkTrackEvents; //void setLinkTrackEvents(String Events) //comma-delimited list
dc; //Removed
trackingServer; //void setTrackingServer(String trackingServer)
trackingServerSecure; //Removed, trackingServer value is used for secure server if ssl=YES
userAgent; //Removed
dynamicVariablePrefix; //Removed
visitorID; //void setVisitorID(String ID)
charSet; //void setCharSet(String charSet)
visitorNamespace; //Removed
pageName; //void setAppState(String State)
pageURL; //Removed
referrer; //Removed
currencyCode; //void setCurrencyCode(String currencyCode)
purchaseID; //void setPurchaseID(String ID)
channel; //void setChannel(String Channel)
server; //void setAppSection(String Section)
pageType; //Removed
transactionID; //void setTransactionID(String ID)
campaign; //void setCampaign(String Campaign)
state; //void setGeoState(String GeoState)
zip; //void setGeoZip(String GeoZip)
events; //void setEvents(String Event) //comma-delimited list
products; //void setProducts(String Products)
list1-list3; //setListVar(int listNum, String listValue);
hier1-heir5; //setHier(int hierNum, String hierValue);
prop1-prop75; //setProp(int propNum, String propValue);
eVar1-eVar75; //setEvar(int evarNum, String evarValue);
ssl; //void setSSL(boolean ssl)
linkLeaveQueryString; //Removed
debugTracking; //debugLogging
usePlugins; //Removed
useBestPractices; //Removed - handled by Lifecycle AutoTracking
contextData; //persistentContextData
```

## 使用 Bloodhound 测试移动应用程序

使用 Bloodhound 工具，您可以向本地计算机发送服务器调用以测试移动应用程序。

*重要信息：自 2017 年 4 月 30 日起，已弃用 Adobe Bloodhound。从 2017 年 5 月 1 日开始，将不再提供其他增强功能以及额外的工程部或 Adobe Expert Care 团队支持。*

在应用程序开发期间，使用 Bloodhound 可以在本机上查看服务器调用，并可以选择将数据转发到 Adobe 收集服务器中。

Bloodhound 可用于 Mac 和 Windows。

### 要求

* 运行 Snow Leopard (10.6) 或更高版本的基于 Intel 的 Mac 计算机，或 Windows PC。
* 到您移动设备或模拟器的网络连接。

### 下载

请参阅 Developer Connection 上的 Bloodhound - App Measurement QA Tool（Bloodhound - App Measurement QA 工具）。

### 安装

* Mac：打开下载的 dmg 并将 Bloodhound 拖动到 Applications 文件夹。
* Windows：运行所下载的安装文件。

### 使用 Bloodhound

启动此工具后，服务器将处于禁用状态，直到您点击“开始”按钮。在您准备好从应用程序捕获服务器调用时，点击“开始”按钮。

或者，您可以在启动服务器之前指定一个自定义端口号（必须是 1024 以上）。如果您未提供端口号，则服务器将自动选择一个开放端口。

在服务器运行后，您需要配置应用程序或设备，以便将数据发送到对应工具，具体步骤会在下节中讨论。

### 配置设备以发送点击到 Bloodhound

您可以更改设备的代理设置以向此工具发送 http 请求。可以选择将发送到此工具的请求转发到 Adobe 数据收集服务器。

如果您的设备不支持代理，则可以将点击直接发送到 Bloodhound 进行测试。

*注意：Bloodhound 不支持 SSL 跟踪。使用 Bloodhound 进行测试时，您必须在 AppMeasurement 库中禁用 SSL。*

#### iOS 设备

iOS 设备必须与托管 Bloodhound 的计算机位于同一网络上。

1. 导航到设置&gt; Wi-Fi。
1. 单击当前 Wi-Fi 网络右侧的蓝色箭头。
1. 滚动到 HTTP 代理设置。
1. 选择自动。
1. 在 URL 字段中输入代理 URL 和端口（从 Bloodhound UI）。

#### 其他设备

如果设备支持代理自动配置，则只需将代理 URL（从 Bloodhound UI）用作代理自动配置 (PAC) URL。不同 Android 版本的代理支持有所不同，可通过一些适用于 Android 的代理配置工具进行简单配置。

### 直接发送点击

对于不支持代理的设备（iOS 模拟器、Android 早期版本等），可以将 Bloodhound 指定为跟踪服务器以捕获它生成的点击。为此，请将跟踪服务器设置为<Bloodhound IP>:<BloodhoundPort>".

例如：

```
//iOS
[measure configureMeasurementWithReportSuiteIDs:@"my_rsid" trackingServer:@"10.10.2.2:5000"];
measure.ssl = NO;
```

```
//Android
measure.configureMeasurement("my_rsid", "10.10.2.2:5000");
measure.ssl = false;
```

```
//WinRT for Windows 8, Windows Phone 8
measure.ConfigureMeasurement("my_rsid", "10.10.2.2:5000");
measure.ssl = false;
```

### 疑难解答/常见问题

* 仅在使用非 SSL 跟踪时 Bloodhound 才有效。通过 SSL 发送的任何跟踪点击均不会被捕获，无论使用以上哪种方法。

## Android 小组件

可以使用与应用程序相同的方法来跟踪 Android 小组件。小组件会与您的应用程序共享应用程序上下文，从而保留点击顺序和访客标识。

以下准则将帮助您跟踪 Android 小组件：

* 不要在小组件本身中实施生命周期量度 (startActivity/stopActivity)。
* 要在将小组件添加到主屏幕时进行跟踪，请向小组件的 onEnabled 方法添加 trackState 或 trackEvent 调用。
* 要在从小组件启动应用程序时进行跟踪，请在产生启动应用程序的意图之前，添加 trackState 或 trackEvent 调用。
* 如果您希望跟踪某个操作的上下文，则可以定义一个 ContextData 变量，通过此变量可以选择单独划分各个上下文（例如，AppExperienceType="widget" vs. "app"）。
