---
title: "Hugo部署后css失效的问题"
date: 2022-07-13T00:47:22+08:00
draft: false
categories: ["blog"]
tags: ["tip"]
---

使用hugo有几天了，从最开始的一团糟到现在算是能够完整部署到服务器端而不出现问题了。结果虽然是好的，但这个过程其实挺折腾，毕竟好几个睡不着的晚上都在跟自己并不懂的事情做斗争，一遍又一遍尝试。唉，不能系统学习前端知识就是这样的。

<!--more-->

这次遇见的问题就是我使用的主题[PaperMod](https://github.com/adityatelange/hugo-PaperMod/)有些样式我不是很满意，需要自己修改。于是我相当然地认为直接修改各个part的css文件就可以。然后这样的结果是只要你修改了主题里的那些css文件，重新生成静态资源并部署到githubpage等地方，就会出现css样式无法加载的问题。

之前根据我从网上寻找的答案，很多人都说css样式丢失是部署出的问题，重新按照手动git方式部署就可以解决。我尝试了几次，都没有解决。而其中有两次我是把站点删除重新建立的，误打误撞就没问题，以为真的可以解决。然而再一次修改css文件后，部署后访问起来css又丢失了。

这个问题还没那么好发现，因为我电脑端的chrome浏览器缓存了之前的css，所以当我修改了css文件并部署到远程以后，按理来说应该网站应该没有样式了。但缓存这个时候生效，导致我前几天一直没发现这个问题。反而是手机上访问一直没有样式，我还以为是hugo部署的问题，没能兼容移动端的css。

刚刚又在搜索，然后意外发现有人在谈custom styles——自定义样式的问题，我才觉得恍然大悟。一定是我不应该直接修改主题的css文件。而这个主题也果然有预留的blank.css文件，就是专门留给用户的。

于是将我的自定义样式迁移到这里，然后重新push一下静态资源，再次访问网站，果然一切都正常了。

尽管其中的原理我还不是很明白，因为js和css框架我都没学。但其实早就该想到这个点，因为主题这个东西作者在docs上一开始就写了升级方式。显然我这种直接修改主题文件的方式，一旦升级就GG了。

少走弯路的唯一捷径，还是系统学习。
