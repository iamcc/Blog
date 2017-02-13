---
title: 磁盘占满导致redis错误
date: 2016-06-20 17:08:39
tags: [redis, error, exp]
categories: tech
---

今天莫名其妙的开发服务器登录成功却马上又跳到401错误，第一反应当然是session出问题。
排查代码没有修改，配置文件没有修改，但是session始终无法正确保存。
最后再排查日志，由于redis开了aof，磁盘占满后无法写入磁盘导致redis无法写入。
又踩到一个大坑。
