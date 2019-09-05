---
title: 内部流量
description: 内部流量插件动态识别源自内部网络的访客。
seo-description: 内部流量插件
seo-title: 内部流量插件
translation-type: tm+mt
source-git-commit: 8c2b28ee1ca2e9448b9dec99a0505d0fae525e94

---


# 内部流量

内部流量插件动态识别源自内部网络的访客。

识别内部和外部流量可提供过滤和细分数据所需的机制，从而提高所有类型报告中的准确性。它还能正确实现，它还可以消除VISTA规则或处理规则的需求，这些方法是识别此类流量的典型方法。

## Internal Traffic插件是如何工作的？

插件尝试加载仅在内部网络/内部网中可用的文件，即1x透明像素。如果成功加载，则该访客的流量将被标识为内部。其他任何东西都将是外部流量。

## 注意事项

* 这种方法的唯一缺点是，在浏览器控制台中，在其访问的第一页上显示404错误。这不会影响用户体验。
* 在试图加载内部托管的像素之前，我们强烈建议您从网络或Infosec团队获得批准。
* 尽管插件不会将流量移动到另一个报表包或将其从报表中排除(像使用VISTA规则一样)，但可以将自定义逻辑包含在其实施中，以便此功能能够进行客户端。

## 实施

1. 添加Intranet像素：您可以在Intranet上添加任何类型的文件，插件将尝试访问该文件。建议使用1x透明像素。它应该放在Intranet上的某个位置，可从内部网络中广泛访问。
1. 配置eVar：需要在目标报告套件中添加eVar。它应已过期“访问”和分配“原始值(第一个)”。
1. 定义内部URL：在AppMeasurement配置变量内，在实例化doPlugins之前，为像素或其他文件定义内部URL变量(s. inTurl)。例如：`s.intURL = "https://www.yourdomainhere.com/trafficCheck.gif"`
1. 修改doPlugins并设置eVar：然后，可使用第步中定义的eVar在AppMeasurement库代码的doPlugins部分中包含此行代码来初始化插件： `s.eVarXX = s.intCheck();`
变量值将设置为“internal”或“external”。
1. 添加插件源代码：在AppMeasurement文件的doPlugins部分下包含插件代码。

## 插件源代码

将此代码添加到AppMeasurement库的doPlugins部分下。

```JavaScript
s.intCheck=new Function("",""
+"var s=this;if(document.cookie.indexOf('intChk=')==-1){try{document."
+"cookie='intChk=1';var x=new XMLHttpRequest(),y;x.open('GET',s.intUr"
+"l,false);x.send();if(x.status===200&&x.statusText==='OK'){y='intern"
+"al';}}catch(e){y='external'}finally{return y}}");
```

## 其他备注

* 始终测试插件安装，以确保数据收集按预期方式进行，然后再在生产环境中部署。
* 您的实施可能使用不同于默认Adobe Analytics的对象的对象名称。如果是这样，请相应地更新对象名称。
* 如果您使用标签管理系统，请按照其步骤更新doPlugins和其他自定义插件。
