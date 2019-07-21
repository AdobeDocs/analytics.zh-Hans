---
description: 在新版 JavaScript AppMeasurement 中，插件支持发生了更改。
keywords: Analytics实施；appasurement；javascript；插件；插件
seo-description: 在新版 JavaScript AppMeasurement 中，插件支持发生了更改。
seo-title: AppMeasurement插件支持
solution: Analytics
subtopic: JavaScript AppMeasurement
title: AppMeasurement插件支持
topic: 开发人员和实施
uuid: e048e16b-994a-4079-bde3 fa3 c96 d
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# AppMeasurement插件支持

JavaScript AppMeasurement当前版本中的插件支持。

## 已经过测试的插件 {#section_48415FB895E6455FAC34B0B96DE6EBE7}

以下插件已经过测试和验证，确认兼容：

* [s.abort 标记](/help/implement/js-implementation/plugins/abort.md)
* [appendList](/help/implement/js-implementation/plugins/appendlist.md)
* [doPlugins函数](/help/implement/js-implementation/plugins/function-doplugins.md)
* [getAndPersistValue](/help/implement/js-implementation/plugins/getandpersistvalue.md)
* [getDaysSinceLastVisit](../../../implement/js-implementation/plugins/getdayssincelastvisit.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF)
* [getLoadTime](/help/implement/js-implementation/plugins/getloadtime.md)
* [getNewRepeat](../../../implement/js-implementation/plugins/getnewrepeat.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF)
* [getPageVisibility](/help/implement/js-implementation/plugins/pagevisibility.md)
* [getPercentPageViewed](/help/implement/js-implementation/plugins/getpercentpageviewed.md)
* [getPreviousValue](/help/implement/js-implementation/plugins/getpreviousvalue.md)
* [getQueryParam](/help/implement/js-implementation/plugins/getqueryparam.md)
* [getTimeParting](../../../implement/js-implementation/plugins/gettimeparting.md#concept_3746EA1D1EF746049AE84105B911F44A)
* [getValOnce](/help/implement/js-implementation/plugins/getvalonce.md)
* [getVisitNum](/help/implement/js-implementation/plugins/getvisitnum.md)
* [getVisitStart](/help/implement/js-implementation/plugins/getvisitstart.md)
* [hitGovernor](/help/implement/js-implementation/plugins/hitgovernor.md)
* [内部流量](/help/implement/js-implementation/plugins/internal-traffic.md)
* [performanceTiming](/help/implement/js-implementation/plugins/performancetiming.md)
* [trackTNT](/help/implement/js-implementation/plugins/tracktnt.md)

## 未经过测试的插件 {#section_32BA7CAB37554A278170A728F1D65CE9}

由于其基本功能仍受支持，以下插件仍然有效，但是它们没有经过测试和验证，无法确认其兼容性。您应当在迁移之前先在自己的开发环境中测试这些插件。

* getActionDepth
* getCookiesAccepted
