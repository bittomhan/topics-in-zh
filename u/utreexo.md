# Utreexo

**Utreexo** 是一种提出的替代 UTXO 集合的方法，它允许全节点获取和验证交易中所花费 UTXO 的信息。

在每个区块之后更新的默克尔树累积了对每个未花费交易输出的引用，使节点能够跳过存储这些输出本身。新交易可以与它们所花费的 UTXO 一起分发，并提供一个默克尔分支证明它们是 utreexo 默克尔树的一部分。总的来说，这可以减少全节点所需的存储量，代价是适度增加带宽。Utreexo 不会改变比特币的安全模型。

## 主要代码和文档

* [Utreexo: 针对比特币 UTXO 集合优化的动态基于哈希的累加器](https://eprint.iacr.org/2019/611.pdf)

## Optech 新闻简报和网站提及

**2023**

* [宣布 Libflorestra 库用于在应用程序中使用 utreexo](https://bitcoinops.org/en/newsletters/2023/08/23/#libfloresta-library-announced)
* [使用 utreexo 变体的 ZeroSync 协议](https://bitcoinops.org/en/newsletters/2023/05/24/#state-compression-with-zero-knowledge-validity-proofs)
* [Utreexo 的服务位](https://bitcoinops.org/en/newsletters/2023/03/15/#service-bit-for-utreexo)

**2022**

* [使用 Utreexo 的 ZeroSync 项目启动](https://bitcoinops.org/en/newsletters/2022/10/19/#zerosync-project-launches)

**2019**

* [在 CoreDev.Tech 上关于 Utreexo 的问答环节](https://bitcoinops.org/en/newsletters/2019/06/12/#utreexo)
* [探索累加器](https://bitcoinops.org/en/newsletters/2019/02/05/#accumulators-for-blockchains)

**2018**

* [CoreDev.Tech 总结：Utreexo](https://bitcoinops.org/en/newsletters/2018/10/16/#using-utxo-accumulators-to-reduce-data-storage-requirements-utreexo)

## 参见

* [非经济性输出](https://bitcoinops.org/en/topics/uneconomical-outputs/)
