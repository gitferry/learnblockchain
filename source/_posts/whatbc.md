---
title: 区块链技术原理
date: 2017-10-25 23:26:04
categories: BlockChain
tags:
    - 区块链
    - 原理
author: Tiny熊
---

 > 区块链是一个基于密码学安全的分布式账本，是一个方便验证，不可篡改的账本。
 > 比特币其实是一个区块链应用，也是目前最成功的一个。

<!-- more -->

## 区块链技术
相信上一篇文章的介绍，已经知道比特币是什么，但还是有很多疑问
* 比特币系统如何解决保密问题
每人都有一份账本，那是不是每个人都知道其他人有多少钱？
* 如何快速验证账本有效性
账本数据随时间推移越来越大，如果每次都交易的时候都验证一下账本，是不是验证的时间越来越长？



### 哈希函数
在讲区块链技术之前，先说明一下哈希函数。
哈希函数：Hash(原始信息) = 摘要信息
原始信息可以是任意的信息,hash之后会得到一个简短的摘要信息

哈希函数有几个特点:
* 同样的原始信息用同一个哈希函数总能得到相同的摘要信息
* 原始信息任何微小的变化都会哈希出面目全非的摘要信息
* 从摘要信息无法逆向推算出原始信息

举例说明：
Hash(张三借给李四100万，利息1%，1年后还本息 .....) = AC4635D34DEF
账本上记录了AC4635D34DEF这样一条记录。

可以看出哈希函数有4个作用：
* 简化信息
很好理解，哈希后的信息变短了。
* 标识信息
可以使用AC4635D34DEF来标识原始信息，摘要信息也称为原始信息的id。
* 隐匿信息
账本是AC4635D34DEF这样一条记录，原始信息被隐匿。
* 验证信息
假如李四在还款时欺骗说，张三只借给李四10万，双方可以用AC4635D34DEF来验证原始信息

哈希函数的这4个作用在区块链技术里有广泛的运用。
（哈希函数是一组函数或算法，以后会发文章专门介绍哈希）

### 区块链技术

假设有如下一个账页:

| 账号 | 入账 | 出账 | 余额 |  备注说明 | 
| - | - | - | - | - | 
| 王二 | 100 |  | 190 | 收到xxx货款 | 
| 张三 |  | 100 | 30 |  xxxx | 
| 李四 | 120 | 90 | 170 | xxxx | 





