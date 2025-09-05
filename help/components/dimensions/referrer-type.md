---
title: 反向链接类型
description: 反向链接类型，取决于访客的来源。
feature: Dimensions
exl-id: a6cfcbf4-cd08-4e7f-8e86-47488ceb0ea3
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 96%

---

# 反向链接类型

“反向链接类型”[维度](overview.md)报告访客点击了哪些通用渠道进入您的网站。 Adobe 将维护每个维度项目的规则，它与[营销渠道](marketing-channel.md)不同，营销渠道是贵组织负责维护每个渠道的规则。

## 使用数据填充此维度

此维度引用 Adobe 内部的多个查找表。每个值都基于点击的[反向链接](referrer.md)，具体取决于[内部 URL 过滤器](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)。确保正确配置反向链接维度和内部 URL 过滤器。

## 维度项目

维度项目包括点击的反向链接类型。具体值包括：

* **已输入/添加书签**：点击不存在反向链接数据。
* **搜索引擎**：反向链接来自于包括关键词查询字符串的可识别搜索引擎。
* **社交网络**：反向链接数据属于 Adobe 可识别的社交网络。
* **其他网站**：反向链接数据既不属于搜索引擎，也不属于 Adobe 可识别的社交网络。
* **硬盘**：反向链接源于访客硬盘上网页的本地副本。
* **电子邮件**：反向链接源于使用 `imap://` 或 `mail://` 协议的 URL。不包括在线电子邮件服务，因为这些服务通常使用 `https://` 协议。

### 社交网站

以下列表引用了 Adobe 使用的“社交网络”查找表。Adobe 将以下列表免费提供给 Adobe Analytics 客户。如果您希望向 Adobe 提出建议将某个域添加到此列表，请让贵组织的支持代表联系客户服务部门。

>[!NOTE]
>
>此列表不同于[营销渠道处理规则](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-rules.md)中的社交网络默认列表。

* `12seconds.tv`
* `4travel.jp`
* `advogato.org`
* `ameba.jp`
* `anobii.com`
* `answers.yahoo.com`
* `asmallworld.net`
* `avforums.com`
* `backtype.com`
* `badoo.com`
* `bebo.com`
* `bigadda.com`
* `bigtent.com`
* `biip.no`
* `blackplanet.com`
* `blog.seesaa.jp`
* `blogspot.com`
* `blogster.com`
* `blomotion.jp`
* `bolt.com`
* `brightkite.com`
* `bsky.app`
* `buzznet.com`
* `cafemom.com`
* `care2.com`
* `classmates.com`
* `cloob.com`
* `collegeblender.com`
* `cyworld.co.kr`
* `cyworld.com.cn`
* `dailymotion.com`
* `delicious.com`
* `deviantart.com`
* `digg.com`
* `diigo.com`
* `disqus.com`
* `draugiem.lv`
* `facebook.com`
* `faceparty.com`
* `fc2.com`
* `flickr.com`
* `flixster.com`
* `fotolog.com`
* `foursquare.com`
* `friendfeed.com`
* `friendsreunited.com`
* `friendsreunited.co.uk`
* `friendster.com`
* `fubar.com`
* `gaiaonline.com`
* `geni.com`
* `go.bsky.app`
* `goodreads.com`
* `plus.google.com`
* `plus.url.google.com`
* `grono.net`
* `habbo.com`
* `hatena.ne.jp`
* `hi5.com`
* `hotnews.infoseek.co.jp`
* `hyves.nl`
* `ibibo.com`
* `identi.ca`
* `t.ifeng.com`
* `imeem.com`
* `instagram.com`
* `intensedebate.com`
* `irc-galleria.net`
* `iwiw.hu`
* `jaiku.com`
* `jp.myspace.com`
* `kaixin001.com`
* `kakaku.com`
* `kanshin.com`
* `kozocom.com`
* `last.fm`
* `likeshop.me`
* `linkedin.com`
* `linkin.bio`
* `livejournal.com`
* `lnkd.in`
* `meetup.com`
* `me2day.net`
* `mister-wong.com`
* `mixi.jp`
* `mixx.com`
* `mouthshut.com`
* `mp.weixin.qq.com`
* `multiply.com`
* `mumsnet.com`
* `myheritage.com`
* `mylife.com`
* `myspace.com`
* `myyearbook.com`
* `nasza-klasa.pl`
* `matome.naver.jp`
* `netlog.com`
* `nettby.no`
* `netvibes.com`
* `nextdoor.com`
* `nicovideo.jp`
* `ning.com`
* `odnoklassniki.ru`
* `ok.ru`
* `orkut.com`
* `pakila.jp`
* `photobucket.com`
* `pinterest.com`
* `pinterest.co.uk`
* `plaxo.com`
* `plurk.com`
* `po.st`
* `reddit.com`
* `renren.com`
* `skyrock.com`
* `slideshare.net`
* `smcb.jp`
* `smugmug.com`
* `snapchat.com`
* `sonico.com`
* `studivz.net`
* `stumbleupon.com`
* `t.163.com`
* `t.co`
* `t.hexun.com`
* `t.people.com.cn`
* `t.qq.com`
* `t.sina.com.cn`
* `t.sohu.com`
* `tabelog.com`
* `tagged.com`
* `taringa.net`
* `thefancy.com`
* `threads.com`
* `threads.net`
* `tiktok.com`
* `toutiao.com`
* `tripit.com`
* `trombi.com`
* `trytrend.jp`
* `tuenti.com`
* `tumblr.com`
* `twine.com`
* `twitter.com`
* `uhuru.jp`
* `viadeo.com`
* `vimeo.com`
* `vk.com`
* `wayn.com`
* `web-cdn.bsky.app`
* `weibo.com`
* `weourfamily.com`
* `wer-kennt-wen.de`
* `wordpress.com`
* `x.com`
* `xanga.com`
* `xing.com`
* `yammer.com`
* `yaplog.jp`
* `yelp.com`
* `yelp.co.uk`
* `youku.com`
* `youtube.com`
* `yozm.daum.net`
* `yuku.com`
* `zooomr.com`
* `zhihu.com`

### “其他网站”维度项目中的搜索引擎

在查看“反向链接类型”维度中的特定域时，您可能会发现自己预计会列在“搜索引擎”下的域，实际上列在“其他网站”下。例如，您可能会看到 `'google.com'` 列在“其他网站”下。

* **“搜索引擎”维度项目中的搜索引擎域**：反向链接符合 Adobe 分类为搜索引擎的所有条件。反向链接域是有效的搜索引擎，*并且*&#x200B;反向链接 URL 包含关键词查询字符串参数。
* **“其他网站”维度项目中的搜索引擎域**：反向链接 URL 不符合分类为搜索引擎的所有条件。常见示例包括专用于搜索之外的其他功能的子域。例如，`mail.google.com` 或 `autos.yahoo.com` 不是搜索引擎，但驻留在通常与搜索相关联的顶级域上。这些子域不包含关键词查询字符串，这正是它们被归入“其他网站”而不是“搜索引擎”下的原因。
