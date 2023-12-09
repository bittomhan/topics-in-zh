# 集群内存池 - Cluster mempool

**集群内存池**是一种提议，旨在将内存池中的每个未确认交易与相关交易关联起来，从而创建一个集群。无论是单个交易还是多个交易，每个交易集群都可以从最值得挖掘到最不值得挖掘进行排序，这样就可以快速完成添加或移除新集群的操作，以便在 P2P 网络代码中使用。

如果 P2P 网络代码可以确定一个新的未确认交易（或交易集群）是否会在短期内提高内存池对矿工的盈利能力，那么这个标准可以代替其他启发式方法来确定何时接受交易 [打包（package）](https://bitcoinops.org/en/topics/package-relay/) 或[替换（replacement）](https://bitcoinops.org/en/topics/replace-by-fee/)。希望这将允许交易中继提供更灵活的策略，而不会使中继节点面临新的资源浪费攻击。

## 主要代码和文档

* [Bitcoin Core #27677: 新内存池设计](https://github.com/bitcoin/bitcoin/issues/27677)

## Optech 新闻通讯和网站提及

**2023**

* [关于多种中继策略主题的 LN 开发者讨论，包括集群内存池](https://bitcoinops.org/en/newsletters/2023/07/26/#reliable-transaction-confirmation)
* [包括集群内存池在内的内存池提议](https://bitcoinops.org/en/blog/waiting-for-confirmation/#policy-proposals)
* [关于内存池重设计的比特币核心会议记录](https://bitcoinops.org/en/newsletters/2023/05/17/#mempool-clustering)

## 参见

* [打包中继（Package relay）](https://bitcoinops.org/en/topics/package-relay/)
* [费用替换（Replace-by-Fee）](https://bitcoinops.org/en/topics/replace-by-fee/)
