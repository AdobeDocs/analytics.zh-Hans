---
description: s.sa() 函数允许您在触发图像请求的前后，随时在页面上动态更改报表包。
keywords: Analytics Implementation
solution: Analytics
subtopic: Functions
title: s.sa() 函数
topic: Developer and implementation
uuid: a6aacd10-2a5b-448b-b3b7-bed5590b71d4
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.sa() 函数

s.sa() 函数允许您在触发图像请求的前后，随时在页面上动态更改报表包。

如果您的组织希望将数据发送至不同的报表包，且不进行页面重载，则强烈建议使用此函数。

此信息适用于熟悉报表和实施的高级用户。在没有完全了解后果之前请勿尝试对您的实施进行任何编辑。如果您要对实施进行更改，请联系贵组织的客户经理。

## 函数的属性 {#section_E10CB41A0CF749F4A24C8377958E3671}

设置这个函数时，会涉及到所有以前定义的变量，该函数允许这些变量在其他报表包中使用。

## 实施示例 {#section_14B0B8C853244D5F82B08B995773640C}

在向一个报表包发送视频数据的同时，将其他数据发送给另一个报表包：

```js
// Set in the core JS file by default 
var s=s_gi('prodrsid'); 
 
// Define this when a user interacts with a video 
s.sa('videorsid'); 
s.t(); // Sends an image request
```

使用 s.sa() 和多包标记：

```js
// Set in the core JS file by default 
var s=s_gi('rsid1'); 
 
// Call the function when you wish to change report suites 
s.sa('rsid1,rsid2'); 
s.t();
```

