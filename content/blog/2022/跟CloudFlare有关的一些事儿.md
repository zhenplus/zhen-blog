---
title: "CloudFlare与https的一些注意事项"
date: 2022-07-08T14:48:56+08:00
draft: false
categories: ["tips"]


---

# 

### 一、宝塔面板

宝塔面板的web服务是python搭建的，不支持cloudflare的CDN，代理域名需要`点掉云盾`，不使用cf的CDN，等待缓存完成就可以了正常访问了。

<!--more-->

又或者，在宝塔版本7.9.0的设置中，发现了面板云端请求方式可以修改为PHP，但是否可以解决CF CDN访问的问题尚未测试。

![image-20220323173247024](https://blog-1251414445.cos.ap-guangzhou.myqcloud.com/typora-img/image-20220323173247024.png)

### 二、Github Pages

Github Pages目前已经支持自定义域名的https了，但在套用cloudflare的情况下仍需注意应按照以下方案操作：

1. 域名绑定到cloudflare的DNS解析后，点掉`云盾`图标。
2. Github Pages页面绑定域名，然后会`自动申请并绑定ssl证书`，等待操作完全即可 。
3. 打开cloudflare的DNS解析后的云盾即可使用CDN服务。
4. cloudflare的SSL/TSL设置中需要选择`完全`模式。

![image-20220323173819711](https://blog-1251414445.cos.ap-guangzhou.myqcloud.com/typora-img/image-20220323173819711-16480283321991.png)