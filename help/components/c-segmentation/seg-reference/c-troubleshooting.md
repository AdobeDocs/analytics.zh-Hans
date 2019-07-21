---
description: 'null'
seo-description: 'null'
seo-title: 分段疑难解答
title: 分段疑难解答
uuid: 8476d617-4b44-4ff2-9b3a-02685f666afc
translation-type: tm+mt
source-git-commit: 50069fe860d58f04df7ffe63714afeef9d3d7a28

---


# 分段疑难解答

## Error: "Incompatible elements in this segment" {#section_B167EE10A0844E649DD7E14D0BAEDA17}

当您尝试在“Data Warehouse”文件夹中保存的区段含有与 Data Warehouse 不兼容的元素时，会出现此问题。要解决此错误，请执行以下操作之一：

* 将该区段保存在其他文件夹
* 删除或更改该区段中的不兼容部分。

## 为何我的区段根本不返回任何数据？ {#section_999749CBBE984142AEA49A6E68E6730A}

可能的原因：

* 反向嵌套 - 例如，在访问容器下嵌套访客容器。
* 报表不支持分段。
* 没有与此分段标准匹配的数据。

## 为何我看不到在“区段管理器”中创建的区段？ {#section_BE0A0930A2694A23BB32DA71696D52CE}

可能的原因：

* 有些维度只能在“Data Warehouse”中使用，不能在“区段管理器”中使用。
* 区段和 Reports &amp; Analytics 不兼容。
* 已指定该区段专门用于特定的报表包。
* 其他用户可能删除了共享的区段。
* 区段由于数据中心或浏览器缓存问题而无法加载。
* 未保存区段。
* 用户端可能阻止了 IP 地址。

## 为何在应用了区段后显示的“页面数据”看似不正确？ {#section_B226AF69FE06463A8BC5337FDA8D4949}

可能的原因：

* 规则/运算符不正确，无法获得所需结果
* 对区段应用了不正确的容器。
* 区段使用的流量变量未经过正确设置或者已过期。

