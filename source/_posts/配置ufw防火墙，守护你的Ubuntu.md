---
title: 配置ufw防火墙，守护你的Ubuntu
date: 2018-01-15 05:21:10
toc: true
tags:
- UFW
- ubuntu
- 安全
---

很久以来许许多多人催促着我赶快配置好防火墙规则以保护vps，但是。。。配置繁琐的iptables使我望而却步~~（其实就是懒~~

直到我发现了ufw这个神器

> UFW 全称为 UncomplicatedFirewall[1]，是 Ubuntu 系统上默认的防火墙组件, 为了轻量化配置 iptables 而开发的一款工具。UFW 提供一个非常友好的界面用于创建基于IPV4，IPV6的防火墙规则。

废话不多说，上教程

# 环境
Ubuntu 16.04

# 安装
```
apt install ufw
```
# 配置
首先先打开ssh端口
```
ufw allow ssh
```
如果你的ssh端口不是默认的22，就
```
ufw allow 你的ssh端口
```
打开53端口，使dns功能不受影响
```
ufw allow 53/tcp
ufw allow 53/udp
```
可选：打开80，443端口
```
ufw allow http/tcp
ufw allow https/tcp
```
然后
```
ufw default deny
```
阻断除上述规则外的外部连接（本机外发流量无影响）
```
ufw enable
```
启动防火墙，done！

# 操作指令
```
启动防火墙 ufw enable
关闭防火墙 ufw disable
更新配置 ufw reload
查看防火墙状态 ufw status
```
----
这篇文章的 PRESS.one 签名:
https://press.one/file/v?s=6e068c89b3f6ca86a239a577b327fa4e04ba0ef6e5c8ba275be3394b5cce914379193543997d8568165fbeedcddf34686d9f59ae94aedb870eaf6e01eb4602cb00&h=6338fd3a0605eafd20fe98c9c32c8f686d17ed03d9c4f244123fc49df19c55d0&a=79a3a060a7faa9dfc9b8b4e0a59bf3ebac305f78&f=P1&v=3