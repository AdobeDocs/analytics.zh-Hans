---
description: 有关 Activity Map 中链接跟踪的常见问题解答。
title: 链接跟踪常见问题解答
uuid: 10172073-b98b-4950-8397-67a18b37b3b4
feature: Activity Map
role: Business Practitioner, Administrator
exl-id: b6ccdf91-98ce-413f-842d-c5423598ed49
translation-type: tm+mt
source-git-commit: 7ba73d75dde80571125c83efb3265441b8d3278a
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 44%

---

# 链接跟踪常见问题解答

有关 Activity Map 中链接跟踪的常见问题解答。

>[!CAUTION]
>
>启用 Activity Map 跟踪后，**您可能会收集个人身份识别信息 (PII) 数据。**&#x200B;此类数据可用于（单独或与其他信息配合使用）识别、联系或查找个人，或者在上下文中识别个人。

以下是使用 Activity Map 跟踪收集 PII 数据的一些已知案例：

* `Mailto` 链接。Mailto 链接是一种 HTML 链接，它可以激活计算机上的默认邮件客户端来发送电子邮件。
* 用户登录后可能出现在网站页眉/页脚的 `User ID` 链接。
* 在金融机构的网站中，账号可能会显示为链接。单击该链接将收集链接的文本。
* 在医疗保健网站中，PII 数据也可能会显示为链接。单击这些链接将收集链接的文本，进而收集 PII 数据。

## 何时进行链接跟踪？

Activity Map链接和区域标识在用户单击页面时发生。

## 默认情况下跟踪哪些内容？

如果某个元素出现单击事件，该元素必须通过一些检查来确定AppMeasurement是否将其视为链接。 检查内容如下：

* 这是带有`href`属性的`A`或`AREA`标签吗？
* 是否存在设置`s_objectID`变量的`onclick`属性？
* 这是带有值或子文本的`INPUT`标记还是`SUBMIT`按钮？
* 这是`INPUT`标记，类型为`IMAGE`和`src`属性吗？
* 这是`BUTTON`吗？

如果以上任一问题的回答为是，则该元素将被视为链接，需要对其进行跟踪。

>[!IMPORTANT]
>
>AppMeasurement不将属性为type=&quot;button&quot;的Button标签视为链接。 请考虑在按钮标签上删除type=&quot;button&quot;，并改为添加role=&quot;button&quot;或submit=&quot;button&quot;。

>[!IMPORTANT]
>
>带有“href”的锚点标签，其中带有“#”的开始被AppMeasurement视为内部目标位置，而不是链接（因为您不要离开页面）。 默认情况下，Activity Map 不跟踪这些内部目标位置，而是仅跟踪将用户导航到新页面的链接。

## Activity Map如何跟踪其他可视HTML元素？

a.通过`s.tl()`函数。

如果通过`s.tl()`调用进行了单击，则Activity Map还将收到此单击事件，并确定是否找到`linkName`字符串变量。 在执行`s.tl()`期间，该linkName将设置为Activity Map链接ID。 发起`s.tl()`调用的已点击元素将用于确定区域。 示例：

```
<img onclick="s.tl(true,'o','abc')" src="someimageurl.png"/>
```

b.通过`s_objectID`变量。 示例：

    &quot;&#39;
    
    &lt;a>&lt;img>&lt;/a>
    
    &lt;a>在此处链接文&lt;/a>
    
    
    本&quot;&#39;

>[!IMPORTANT]
>
>在Activity Map中使用`s_objectID`时，需要尾随分号(;)。

## 能否提供一些将被跟踪的链接示例？

### 示例 1

```
  <a hef="/home?lang=en>Home</a>
```

### 示例 2

```
 <input type="submit" value="Submit"/>
```

### 示例 3

```
  <input type="image" src="submit-button.png"/>
```

### 示例4

```
    <p onclick="var s_objectID='custom link id';">
      <span class="title">Current Market Rates</span>
      <span class="subtitle">1.45USD</span>
    </p>
```

### 示例5

```
    <div onclick="s.tl(true,'o','custom link id')">
      <span class="title">Current Market Rates</span>
      <span class="subtitle">1.45USD</span>
    </div>
```

## 能否提供一些不会跟踪的链接示例？

1. 原因：锚标记不具备有效的 `href`:
   `<a name="innerAnchor">Section header</a>`

1. 原因：`s_ObjectID`和`s.tl()`均不存在：

   ```
   <p onclick="showPanel('market rates')">
     <span class="title">Current Market Rates</span>
     <span class="subtitle">1.45USD</span>
   </p>
   ```

1. 原因：`s_ObjectID`和`s.tl()`均不存在：

   ``` 
   <input type="radio" onclick="changeState(this)" name="group1" value="A"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="B"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="C"/>
   
   ```  
   
1. 原因：&quot;src&quot;属性缺少表单输入元素：

   `<input type="image"/>`
