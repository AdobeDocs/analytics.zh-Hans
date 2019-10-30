---
title: 内部流量
description: “内部流量”插件可动态识别源自内部网络的访客。
seo-description: “内部流量”插件
seo-title: “内部流量”插件
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# 内部流量

“内部流量”插件可动态识别源自内部网络的访客。

通过提供一种可以对所收集数据进行过滤和细分的机制来识别内部和外部流量，可提高所有类型报告的准确性。正确实施后，其将不再需要使用 VISTA 规则或处理规则，这些规则是用于识别此类流量的典型方法。

## “内部流量”插件工作原理

该插件会尝试加载仅在内部网络/内联网中可用的文件，即 1x1 透明像素。如果成功加载，则该访客的流量将被标识为内部流量。任何其他流量均被标识为外部流量。

## 注意事项

* 此方法的唯一缺点是，在外部访客访问第一个页面上时浏览器控制台中将显示 404 错误。但这不会影响用户体验。
* 我们强烈建议您在尝试加载内部托管的像素之前，先获得网络或信息安全团队的批准。
* 虽然该插件不会将流量移动到其他报表包，也不会将其从报表中排除（与 VISTA 规则一样），但其实施中可以包含自定义逻辑，以便此功能可以在客户端执行。

## 实施

1. 添加内联网像素：您可以在内联网上添加该插件将尝试访问的任何类型的文件。建议添加 1x1 透明像素。该文件应被放置在内联网上从内部网络广泛访问的某个位置。
1. 配置 eVar：需要在目标报表包中添加 eVar。“访问”和“原始值（第一个）”的分配应到期。
1. 定义内部 URL：在 AppMeasurement 配置变量中，并且在实例化 doPlugins 之前，为可用于流量检查的像素或其他文件定义内部 URL 变量 (s.intURL)。例如：`s.intURL = "https://www.yourdomainhere.com/trafficCheck.gif"`
1. Modify doPlugins and set the eVar: The plugin can then be initialized by including this line of code within the doPlugins section of your AppMeasurement library code, using the eVar defined in step one: `s.eVarXX = s.intCheck();`
The variable value will be set to "internal" or "external".
1. 添加插件源代码：将插件代码包含到 AppMeasurement 文件的 doPlugins 区域下方。

## 插件源代码

将此代码添加到 AppMeasurement 文件的 doPlugins 区域下方。

```JavaScript
s.intCheck=new Function("",""
+"var s=this;if(document.cookie.indexOf('intChk=')==-1){try{document."
+"cookie='intChk=1';var x=new XMLHttpRequest(),y;x.open('GET',s.intUr"
+"l,false);x.send();if(x.status===200&&x.statusText==='OK'){y='intern"
+"al';}}catch(e){y='external'}finally{return y}}");
```

## 其他注释

* 在生产环境中进行部署之前，请务必对插件安装进行测试，以确保可按预期进行数据收集。
* 您的实施可以使用与默认 Adobe Analytics“s”对象不同的对象名称。如果是这样，请相应地更新对象名称。
* 如果您使用标签管理系统，请按照其步骤更新 doPlugins 和其他自定义插件。
