---
layout: post
title: "开启Raspberry Pi的root用户"
description: ""
category: 树莓派
tags: [树莓派, RaspberryPi]
---
{% include JB/setup %}

debian中root用户默认锁定，且没有密码。

用pi用户登陆后，执行命令

`sudo passwd root`

输入两遍新密码。

再执行：

`sodu passwd --unlock root`




