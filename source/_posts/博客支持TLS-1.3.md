---
title: 博客支持 TLS 1.3
author: johnpoint
date: 2019-04-11 09:36:00
tags:
- https
- TLS
- DNMP
- nginx
pressone: https://press.one/file/v?s=e770b366bbe0d251732e2eab2804233830e800c7cc49846e1fc1966117e01f334de16f0aead5d314aa9d24bfa7aec38927856dd2da1ef6e78f71c0d24a12274601&h=0bea6a1d0679e1f04d338e3386af6e8c161933b43da63f7a050d3a6b7330b14d&a=79a3a060a7faa9dfc9b8b4e0a59bf3ebac305f78&f=P1&v=3
---

博客终于在无数次的 想配置 TLS1.3 和 "啊好麻烦啊，不上了" 中一直没有上 TLS1.3
<!--more-->

借着更新 [DNMP-lvcshu](https://github.com/johnpoint/DNMP-lvcshu) 项目中的 NGINX 模块，顺便把 TLS1.3 的支持给加上了，其实也没有做啥改变，就把 NGINX 的版本升级到了 `1.15.11` 就好了 ~~其实是我太菜~~

然后项目里 NGINX 的本来基于 UBUNTU 的镜像换成了 alpine 版本的镜像，体积： 45MB --> 7MB，更加轻量化了呢。

最麻烦的还是修改配置文件，毕竟每一个网站都要手动加上 TLS1.3 的相关配置，看起来分发 NGINX 配置文件的小工具也要提上日程了呢（~~四面杵鸽.jpg~~