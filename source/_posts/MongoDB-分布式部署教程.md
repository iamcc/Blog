---
title: MongoDB 分布式部署教程
date: 2016-02-24 15:23:23
tags: [database, mongodb, cluster, sharding]
categories: tech
---

[MongoDB 分布式部署教程](http://mr-dai.github.io/mongodb/2015/11/23/MongoDB-Distribution-Tutorial.html)

<!-- more -->

另外记一次数据库恢复过程。

### 前因
服务器因为受到用户抢红包而超负荷Down机，在没有意识的情况下直接重启了服务，结果出现了所有服务都出现了问题，最终定位为数据库连接失败。立即上服务器查询，第一感觉是一切良好，没有什么问题，唯一一个奇怪的地方就是，每个分片的Replset 的数据都正常，但是mongoos的collections却少了好多。Google一番还是没结果，😂，正欲哭无泪的时候想起了阿里的同学，经过一番帮助，终于恢复正常。

### 原因
出现collection数量不同步的原因原来是主shard出现了问题，重启服务的时候，不知什么情况下，shard1的Replset找不到master，然后shard1启动失败了，然后主shard变成了shard2，查来查去都查不到问题，因为一切看起来都那么正常。而少了的那部份collections就是shard1里面的未sharding的collection，未sharding的collection是不会同步到其他shard，所以当主shard是shard2的时候自然就少了那部份collections

### 总结
😂，真是吓出一身冷汗，查不出问题也是因为经验不足和不够细心，也是对整套架构的了解不够，所以再次就一笔。
