# 点时间锁定合约 - Point Time Locked Contracts, PTLCs

**点时间锁定合约**是可以替代 LN 支付通道、同链币交换、某些跨链原子交换以及其他合约协议中使用的 HTLCs 的条件支付。与 HTLCs 相比，它们可以更加私密并使用更少的区块空间。

PTLCs 与 [HTLCs](https://bitcoinops.org/en/topics/htlc/) 在主要的锁定和解锁方法上有所不同：

*   **HTLC 哈希锁：**使用哈希摘要进行锁定，并通过提供相应的原像来解锁。最常用的哈希函数是 SHA256，它产生 256 位（32 字节）的摘要，通常由 32 字节的原像生成。

    当用于保护多个支付时（例如路由的 LN 支付或原子交换），所有支付都使用相同的原像和哈希锁。如果这些支付在链上发布或通过监视节点在链下路由，这会在这些支付之间创建链接。
*   **PTLC 点锁：**使用公钥（比特币椭圆曲线上的_点_）进行锁定，并通过提供满足条件的[签名适配器](https://bitcoinops.org/en/topics/adaptor-signatures/)的相应签名来解锁。对于提议的[椭圆曲线数字签名算法（Schnorr 签名）](https://bitcoinops.org/en/topics/schnorr-signatures/) 构造，该密钥将是 32 字节，签名为 64 字节。然而，使用多方 ECDSA 或 Schnorr 密钥聚合和签名，可以将密钥和签名与授权任何支出所需的其他密钥和签名结合起来，使得点锁不使用任何独特的区块空间。

    每个点锁可以使用不同的密钥和签名，因此点锁本身不会在链上或通过监视节点在链下路由时关联不同的支付。

在比特币中实现 PTLCs 需要创建[签名适配器](https://bitcoinops.org/en/topics/adaptor-signatures/)，当比特币上实施了[椭圆曲线数字签名算法（Schnorr 签名）](https://bitcoinops.org/en/topics/schnorr-signatures/) 后，将这些适配器与数字签名结合起来会更容易。因此，比特币中 PTLCs 的开发大多是一个讨论主题，而不是积极进行的工作。在其他加密货币中不可用的 Schnorr 签名也可能阻止在某些跨链合约中使用 PTLCs，尽管仅使用 ECDSA 公钥和签名技术上仍然可以使用 PTLCs。

## 主要代码和文档

* [无脚本的多跳锁](https://github.com/ElementsProject/scriptless-scripts/blob/master/md/multi-hop-locks.md)

## Optech 新闻简报和网站提及

**2023**

* [提议的 LN 消息更改摘要，用于 PTLCs](https://bitcoinops.org/en/newsletters/2023/09/13/#ln-messaging-changes-for-ptlcs)
* [使用 PTLCs 和签名适配器证明 LN 异步支付的接受](https://bitcoinops.org/en/newsletters/2023/02/01/#ln-async-proof-of-payment)

**2021**

* [2021 年回顾：LN 的 PTLCs](https://bitcoinops.org/en/newsletters/2021/12/22/#ptlcsx)
* [关于支持 PTLCs 的 LN 协议变更的讨论](https://bitcoinops.org/en/newsletters/2021/12/15/#preparing-ln-for-ptlcs)- [LN 开发者会议总结，包括 PTLCs 的讨论](https://bitcoinops.org/en/newsletters/2021/11/10/#ln-summit-2021-notes)
* [使用 PTLCs 进行非托管离线接收](https://bitcoinops.org/en/newsletters/2021/10/20/#paying-offline-ln-nodes)
* [提议升级 LN 以使用 PTLCs](https://bitcoinops.org/en/newsletters/2021/10/13/#multiple-proposed-ln-improvements)
* [为 Taproot 升级 LN：从 HTLCs 到 PTLCs](https://bitcoinops.org/en/newsletters/2021/09/01/#preparing-for-taproot-11-ln-with-taproot)
* [为 Taproot 准备：PTLCs](https://bitcoinops.org/en/newsletters/2021/08/25/#preparing-for-taproot-10-ptlcs)
* [使用 PTLCs 在 LN 上实现逻辑或的技术](https://bitcoinops.org/en/newsletters/2021/02/17/#escrow-over-ln)

**2020**

* [2020 年回顾：将 LN 从 HTLCs 切换到 PTLCs](https://bitcoinops.org/en/newsletters/2020/12/23/#ptlcs)
* [针对从 HTLCs 到 PTLCs 的更新见证非对称通道提议](https://bitcoinops.org/en/newsletters/2020/10/14/#updated-witness-asymmetric-payment-channel-proposal)
* [使用见证非对称支付通道从 HTLCs 转移到 PTLCs](https://bitcoinops.org/en/newsletters/2020/09/02/#witness-asymmetric-payment-channels)
* [PTLCs 在 LN 通道中使用简化 ECDSA 适配器签名](https://bitcoinops.org/en/newsletters/2020/04/08/#work-on-ptlcs-for-ln-using-simplified-ecdsa-adaptor-signatures)

**2018**

* [关于实现 2p-ECDSA 以用于 LN 资金和 PTLCs 的讨论](https://bitcoinops.org/en/newsletters/2018/10/09/#multiparty-ecdsa-for-scriptless-lightning-network-payment-channels)

## 参见

* [哈希时间锁定合约（HTLC）](https://bitcoinops.org/en/topics/htlc/)
* [适配器签名](https://bitcoinops.org/en/topics/adaptor-signatures/)
