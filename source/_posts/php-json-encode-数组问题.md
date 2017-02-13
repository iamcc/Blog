---
title: php json_encode 数组问题
date: 2016-06-23 10:57:47
tags: [tech, php, javascript, json, array]
categories: tech
---

项目里一个正常跑的项目前端突然报了一个 `xxx.map is not a function`。
纳闷的我又开始了填坑的路，chrome debug 一下，发现原本应该是 `array` 的地方变成 `object` 了。
也就是 [0: xxx] 变成 {"0": xxx} 这样了，导致前端 `js` 报错。
最后用了一个偷懒的方法解决这个问题，就是输出之前 `array_values` 一下就好了。
