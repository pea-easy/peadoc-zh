---
title: 业务层
type: guide
order: 6
---

如果团队中有个约定俗成的合理的开发规则，那整个项目将节省大量沟通成本和交接成本以及开发成本，同时这个规则又是大家普遍认可的规则,这样就更灵活了,下面是peajs的层次的介绍。
其中**服务认证层**是peajs里面特别新增的一个层次，在团队项目实践过程中发现这个层次非常有用，避免了很多参数漏传的问题。

## 路由层
路由层的位置在**app/routes** 下面,主要是管理理由的模块，管理路由主要按模块分比如用户模块，订单模块，图表模块。

## 控制层
路由层的位置在**app/controllers** 
服务层提供功能完整性的模块，控制层对功能完整性模块进行组装。

## 服务层
路由层的位置在**app/service** 
服务层主要为控制层服务，完成一个个功能性模块，然后控制层在对服务层进行调用。

### 服务认证层
路由层的位置在**app/validate** 
* 每个服务层的function需要一些简单的校验，比如查询用户需要检测用户id是否存在，更新订单需要校验订单id是否存在，主要是为了避免一些常规的错误。
* 每个服务层对应一个服务认证层，可以通过[yo pea:module](migration.html)
统一生成。


## 数据库操作层
这一层主要是为了和数据库进行交互

> 业务层可以通过[yo pea:module](migration.html)一键生成，同时涵盖example
> 因为peajs只是koa的扩展,所有支持koa所有通用的语法.