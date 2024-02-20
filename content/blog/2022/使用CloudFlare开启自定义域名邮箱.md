---
title: "使用CloudFlare开启免费自定义域名邮箱"
date: 2022-07-08T14:48:56+08:00
draft: false
categories: ["tips"]


---



偶然发现cloudflare提供了`Beta`版本的电子邮件功能，目前还是免费的。简单来说就是只要你把域名交给了cloudflare解析，那么就可以生成自己域名为后缀的邮箱了，如域名：`myname.com`，那么邮箱就可以为`DIY@myname.com`，DIY处任意填写。

<!--more-->

当然，事实上cloudflare并没有提供邮箱服务，这个邮箱只是中转名称而已，你还是需要一个实际的收件邮箱。实用性不能算聊胜于无，起码逼格够了，不过安全与隐私性目前不得而知。

### 1.将域名DNS解析到cloudflare

​	这个操作应该不用说了吧，到购买域名的服务商那把域名DNS服务器更改成cloudflare就好了。

| 类型 |           值           |
| :--: | :--------------------: |
|  NS  | brad.ns.cloudflare.com |
|  NS  | tori.ns.cloudflare.com |

### 2.创建自定义邮箱地址与目标地址

自定义地址就是想要生成的逼格地址，后缀为你的域名。

目标地址就是收件地址了，填写自己最常用的邮箱就好。

填写完毕后，你的目标邮箱会收到验证邮件，需要点击验证链接完整验证。

![image-20220325165447063](https://raw.githubusercontent.com/DolgenLyu/imgcloud/master/image-20220325165447063.png)

### 3.解析邮件DNS记录

给域名添加MX解析，这些都是给邮箱用的，后台有一键填写，填写完成后会出现绿色的`路由已启用`提示。

![image-20220325165823232](https://raw.githubusercontent.com/DolgenLyu/imgcloud/master/image-20220325165823232.png)

### 4.测试并开始使用吧。

查看后台可以发现，`自定义地址`和`目标地址`都不唯一，可以添加多个，意味着自定义邮箱也可以创建很多的，并且指向不同收件邮箱，实用性拉满，再加上目前该功能免费，其实还是不错的。

![Snipaste_2022-03-25_16-53-50](https://raw.githubusercontent.com/DolgenLyu/imgcloud/master/Snipaste_2022-03-25_16-53-50.png)