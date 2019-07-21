---
description: 下表显示用于填充 Analytics 报表的报表映射变量。
keywords: Analytics 实施
seo-description: 下表显示用于填充 Analytics 报表的报表映射变量。
seo-title: 变量到报告映射
solution: Analytics
title: 变量到报告映射
topic: 开发人员和实施
uuid: fd81f97d-dd1 a-47d5-9157-b7932 fe13490
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 变量到报告映射

下表显示用于填充 Analytics 报表的报表映射变量。

在列出的每一个变量旁边，都伴有使用所列变量的报表。

<table id="table_16443E46AC0E46509F8533D26EDE1BCC"> 
 <thead> 
  <tr> 
   <th class="entry"> 变量 </th> 
   <th class="entry"> 填充报表 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> s.pageName </td> 
   <td> <p>转化报表 &gt; 路径报表 &gt; 页面值 </p> <p>转化报表 &gt; 路径报表 &gt; 登录页面 </p> <p>转化报表 &gt; 路径报表 &gt; 原始登录页面 </p> <p>流量报表 &gt; 网站流量 &gt; 页面查看 </p> <p>流量报表 &gt; 网站流量 &gt; 每小时独特访客 </p> <p>流量报表 &gt; 网站流量 &gt; 每日独特访客 </p> <p>流量报表 &gt; 网站流量 &gt; 每月独特访客 </p> <p>流量报表 &gt; 网站流量 &gt; 每年独特访客 </p> <p>流量报表 &gt; 访客资料 &gt; 关键访客查看的页面 </p> <p>流量报表 &gt; 区段 &gt; 最受欢迎页面 </p> <p>路径报表 &gt; 页面 &gt; 页面概要 </p> <p>路径报表 &gt; 页面 &gt; 页面值 </p> <p>路径报表 &gt; 页面 &gt; 最受欢迎页面 </p> <p>路径报表 &gt; 页面 &gt; 重新加载 </p> <p>路径报表 &gt; 页面 &gt; 页面点击 </p> <p>路径报表 &gt; 页面 &gt; 页面逗留时间 </p> <p>路径报表 &gt; 登录和退出 &gt; 登录页面 </p> <p>路径报表 &gt; 登录和退出 &gt; 退出页面 </p> <p>路径报表 &gt; 登录和退出 &gt; 退出链接 </p> <p>路径报表 &gt; 完整路径 &gt; 完整路径 </p> <p>路径报表 &gt; 完整路径 &gt; 最长路径 </p> <p>路径报表 &gt; 完整路径 &gt; 路径长度 </p> <p>路径报表 &gt; 完整路径 &gt; 每次访问逗留时间 </p> <p>路径报表 &gt; 完整路径 &gt; 单页访问 </p> <p>路径报表 &gt; 高级分析 &gt; 上一页 </p> <p>路径报表 &gt; 高级分析 &gt; 下一页 </p> <p>路径报表 &gt; 高级分析 &gt; 上一页面流量 </p> <p>路径报表 &gt; 高级分析 &gt; 下一页面流量 </p> <p>路径报表 &gt; 高级分析 &gt; PathFinder </p> <p>路径报表 &gt; 高级分析 &gt; 流失 </p> <p> <b>注意：</b>在以上列出的所有<span class="wintitle">流量</span>报表中（除<span class="wintitle">最受欢迎页面</span>报表之外），只要未设置 <span class="wintitle">s.pageName</span> 变量，则使用 URL。 </p> </td> 
  </tr> 
  <tr> 
   <td> s.server </td> 
   <td> 流量报表 &gt; 区段 &gt; 最受欢迎服务器 </td> 
  </tr> 
  <tr> 
   <td> s.pageType </td> 
   <td> 路径报表 &gt; 页面 &gt; 页面未找到 </td> 
  </tr> 
  <tr> 
   <td> s.channel </td> 
   <td> <p>转化报表 &gt; 网站路径报表 &gt; 网站区域 </p> <p>流量报表 &gt; 区段 &gt; 最受欢迎网站区域 </p> </td> 
  </tr> 
  <tr> 
   <td> s.prop1 - s.prop20 </td> 
   <td> 流量报表 &gt; 自定义分析 &gt; 自定义分析 1-20 </td> 
  </tr> 
  <tr> 
   <td> s.campaign </td> 
   <td> <p>转化报表 &gt; 促销活动 &gt; 转化和平均值 </p> <p>转化报表 &gt; 促销活动 &gt; 跟踪代码 </p> </td> 
  </tr> 
  <tr> 
   <td> s.state </td> 
   <td> 转化报表 &gt; 访客资料 &gt; 州 </td> 
  </tr> 
  <tr> 
   <td> s.zip </td> 
   <td> 转化报表 &gt; 访客资料 &gt; 邮政编码 </td> 
  </tr> 
  <tr> 
   <td> s.events </td> 
   <td> <p>转化报表 &gt; 购买 &gt; 转化和平均值 </p> <p>转化报表 &gt; 购买 &gt; 收入 </p> <p>转化报表 &gt; 购买 &gt; 订购 </p> <p>转化报表 &gt; 购买 &gt; 件数 </p> <p>转化报表 &gt; 购物车 &gt; 转化和平均值 </p> <p>转化报表 &gt; 购物车 &gt; 购物车 </p> <p>转化报表 &gt; 购物车 &gt; 购物车查看 </p> <p>转化报表 &gt; 购物车 &gt; 购物车加货 </p> <p>转化报表 &gt; 购物车 &gt; 购物车减货 </p> <p>转化报表 &gt; 购物车 &gt; 结帐 </p> <p>转化报表 &gt; 自定义事件 &gt; 自定义事件 1-20 </p> <p>转化报表 &gt; 产品 &gt; 转化和平均值 </p> <p>转化报表 &gt; 产品 &gt; 交叉销售 </p> <p>转化报表 &gt; 产品 &gt; 类别 </p> <p>转化报表 &gt; 促销活动 &gt; 转化和平均值 </p> <p>转化报表 &gt; 客户忠诚度 &gt; 客户忠诚度 </p> <p>转化报表 &gt; 销售周期 &gt; 首次购买间隔天数 </p> <p>转化报表 &gt; 销售周期 &gt; 上次购买间隔天数 </p> <p>转化报表 &gt; 销售周期 &gt; 访问量 </p> <p>转化报表 &gt; 销售周期 &gt; 每日独特访客 </p> <p>转化报表 &gt; 销售周期 &gt; 每月独特访客 </p> <p>转化报表 &gt; 销售周期 &gt; 每年独特访客 </p> <p>转化报表 &gt; 网站路径 &gt; 页面值 </p> </td> 
  </tr> 
  <tr> 
   <td> s.products </td> 
   <td> <p>转化报表 &gt; 购买 &gt; 转化和平均值 </p> <p>转化报表 &gt; 购买 &gt; 收入 </p> <p>转化报表 &gt; 购买 &gt; 订购 </p> <p>转化报表 &gt; 购买 &gt; 件数 </p> <p>转化报表 &gt; 购物车 &gt; 转化和平均值 </p> <p>转化报表 &gt; 产品 &gt; 转化和平均值 </p> <p>转化报表 &gt; 产品 &gt; 交叉销售 </p> <p>转化报表 &gt; 产品 &gt; 类别 </p> <p>转化报表 &gt; 促销活动 &gt; 转化和平均值 </p> <p>转化报表 &gt; 客户忠诚度 &gt; 客户忠诚度 </p> <p>转化报表 &gt; 销售周期 &gt; 首次购买间隔天数 </p> <p>转化报表 &gt; 销售周期 &gt; 上次购买间隔天数 </p> <p>转化报表 &gt; 销售周期 &gt; 访问量 </p> <p>转化报表 &gt; 销售周期 &gt; 每日独特访客 </p> <p>转化报表 &gt; 销售周期 &gt; 每月独特访客 </p> <p>转化报表 &gt; 销售周期 &gt; 每年独特访客 </p> <p>转化报表 &gt; 网站路径 &gt; 页面值 </p> </td> 
  </tr> 
  <tr> 
   <td> s.purchaseID </td> 
   <td> <p>转化报表 &gt; 购买 &gt; 转化和平均值 </p> <p>转化报表 &gt; 购买 &gt; 收入 </p> <p>转化报表 &gt; 购买 &gt; 订购 </p> <p>转化报表 &gt; 购买 &gt; 件数 </p> <p>转化报表 &gt; 购物车 &gt; 转化和平均值 </p> <p>转化报表 &gt; 产品 &gt; 转化和平均值 </p> <p>转化报表 &gt; 产品 &gt; 交叉销售 </p> <p>转化报表 &gt; 客户忠诚度 &gt; 客户忠诚度 </p> <p>转化报表 &gt; 销售周期 &gt; 首次购买间隔天数 </p> <p>转化报表 &gt; 销售周期 &gt; 上次购买间隔天数 </p> <p>转化报表 &gt; 销售周期 &gt; 访问量 </p> <p>转化报表 &gt; 销售周期 &gt; 每日独特访客 </p> <p>转化报表 &gt; 销售周期 &gt; 每月独特访客 </p> <p>转化报表 &gt; 销售周期 &gt; 每年独特访客 </p> <p>转化报表 &gt; 网站路径 &gt; 页面值 </p> </td> 
  </tr> 
  <tr> 
   <td> s.eVar1-s.eVar20 </td> 
   <td> 转化报表 &gt; 自定义变量 &gt; 客户 eVar 1-20 </td> 
  </tr> 
  <tr> 
   <td> s.linkName </td> 
   <td> 流量报表 &gt; 自定义分析 &gt; 自定义链接 </td> 
  </tr> 
  <tr> 
   <td> s.hier1 - s.hier5 </td> 
   <td> 流量报表 &gt; 层级 &gt; 层级 1-5 </td> 
  </tr> 
 </tbody> 
</table>

