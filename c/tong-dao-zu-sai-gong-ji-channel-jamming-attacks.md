# 通道阻塞攻击 - Channel Jamming Attacks

**通道阻塞攻击**是一种拒绝服务（DoS）攻击，攻击者可以阻止高达 20 跳远的一系列通道在较长时间内无法使用部分或全部资金。

闪电网络（LN）节点可以通过 20 个或更多跳的路径将支付路由到自己。这为通道阻塞攻击创造了两种可能的途径：

* _流动性阻塞攻击_（最初在 2015 年称为[循环攻击](https://lists.linuxfoundation.org/pipermail/lightning-dev/2015-August/000135.html)）是指攻击者用 `x` 数量的资金（例如 1 BTC）通过其他 20 个通道发送给自己，但延迟解决或拒绝支付，暂时锁定属于其他用户的总计 `20x` 资金（例如 20 BTC）。在锁定其他用户的资金几小时后，攻击者可以取消支付并完全退还费用，使得攻击基本上免费。
* _HTLC 阻塞攻击_是指攻击者通过 20 个通道发送 483 个小额支付（[HTLCs](https://bitcoinops.org/en/topics/htlc/)），其中 483 是通道可包含的最大待处理支付数量。在这种情况下，拥有两个通道、每个通道有 483 个槽位的攻击者可以阻塞超过 10,000 个诚实的 HTLC 槽位——同样不需要支付任何费用。

![](https://bitcoinops.org/img/posts/2020-12-ln-jamming-attacks.png)

已经讨论了各种可能的解决方案，包括支付方向每个沿途节点支付的_前向预付费用_、[反向预付费用](https://bitcoinops.org/en/newsletters/2020/02/26/#reverse-up-front-payments)（从每个支付跳点支付给前一个跳点）、前向和反向费用的 [结合](https://bitcoinops.org/en/newsletters/2020/11/04/#bi-directional-upfront-fees-for-ln)、[嵌套递增路由](https://bitcoinops.org/en/newsletters/2020/10/14/#incremental-routing) 以及[保证金](https://bitcoinops.org/en/newsletters/2020/12/02/#fidelity-bonds-for-ln-routing)。截至 2021 年 4 月，还没有解决方案获得广泛支持，开发人员继续讨论这个问题。

## 主要代码和文档

* [循环攻击（原始描述）](https://lists.linuxfoundation.org/pipermail/lightning-dev/2015-August/000135.html)
* [LN 垃圾邮件预防](https://github.com/t-bast/lightning-docs/blob/master/spam-prevention.md)
* [解除闪电网络阻塞：系统方法](https://raw.githubusercontent.com/s-tikhomirov/ln-jamming-simulator/master/unjamming-lightning.pdf)
* [断路器：保护节点不受 htlcs 洪水的软件](https://github.com/lightningequipment/circuitbreaker)

## Optech 新闻简报和网站提及

**2023**

* [DoS 保护设计哲学和前向承诺费用与反向保持费用的示例](https://bitcoinops.org/en/newsletters/2023/08/09/#denial-of-service-dos-protection-design-philosophy)
* [闪电网络开发者关于通道阻塞攻击的讨论](https://bitcoinops.org/en/newsletters/2023/07/26/#channel-jamming-mitigation-proposals)
* [LND #7710 允许检索有关 HTLC 的额外数据以支持阻塞对策](https://bitcoinops.org/en/newsletters/2023/06/28/#lnd-7710)
* [Eclair #2701 现在记录 HTLC 接收和结算时间以帮助缓解通道阻塞](https://bitcoinops.org/en/newsletters/2023/06/28/#eclair-2701)
* [测试 HTLC 认可以防止通道阻塞攻击](https://bitcoinops.org/en/newsletters/2023/05/17/#testing-htlc-endorsement)
* [关于 LN 好邻居评分以减轻阻塞的反馈请求](https://bitcoinops.org/en/newsletters/2023/02/22/#feedback-requested-on-ln-good-neighbor-scoring)
* [关于缓解 LN 阻塞的电话会议摘要](https://bitcoinops.org/en/newsletters/2023/02/08/#summary-of-call-about-mitigating-ln-jamming)

**2022**

* [2022 年度回顾：通道阻塞](https://bitcoinops.org/en/newsletters/2022/12/21/#jamming)
* [CircuitBreaker 附加软件部分缓解阻塞攻击而无需协议更改](https://bitcoinops.org/en/newsletters/2022/12/14/#local-jamming-to-prevent-remote-jamming)
* [声誉凭证提案以减轻 LN 阻塞攻击](https://bitcoinops.org/en/newsletters/2022/11/30/#reputation-credentials-proposal-to-mitigate-ln-jamming-attacks)
* [根据当地声誉和预付费用提出解决阻塞攻击的论文](https://bitcoinops.org/en/newsletters/2022/11/16/#paper-about-channel-jamming-attacks)
* [关于通道阻塞攻击及其解决方案的指南](https://bitcoinops.org/en/newsletters/2022/08/24/#overview-of-channel-jamming-attacks-and-mitigations)

**2021**

* [2021 年度回顾：通道阻塞](https://bitcoinops.org/en/newsletters/2021/12/22/#jamming)
* [LN 开发者大会总结，包括通道阻塞攻击讨论](https://bitcoinops.org/en/newsletters/2021/11/10/#ln-summit-2021-notes)
* [通过降低探测成本使阻塞攻击更昂贵](https://bitcoinops.org/en/newsletters/2021/10/20/#lowering-the-cost-of-probing-to-make-attacks-more-expensive)
* [关于双向预付 LN 费用的重新讨论](https://bitcoinops.org/en/newsletters/2021/02/17/#renewed-discussion-about-bidirectional-upfront-ln-fees)

**2020**

* [2020 年度回顾：LN 通道阻塞攻击](https://bitcoinops.org/en/newsletters/2020/12/23/#jamming)
* [保证金以防止通道阻塞攻击](https://bitcoinops.org/en/newsletters/2020/12/02/#fidelity-bonds-for-ln-routing)
* [双向预付费用以减轻阻塞攻击](https://bitcoinops.org/en/newsletters/2020/11/04/#bi-directional-upfront-fees-for-ln)
* [更多前向费用讨论](https://bitcoinops.org/en/newsletters/2020/10/21/#more-ln-upfront-fees-discussion)
* [可信前向支付以减轻阻塞攻击](https://bitcoinops.org/en/newsletters/2020/10/14/#trusted-upfront-payment)
* [增量路由作为前向费用的替代方案](https://bitcoinops.org/en/newsletters/2020/10/14/#incremental-routing)
* [Eclair #1539 实施了简单措施以减少通道阻塞攻击](https://bitcoinops.org/en/newsletters/2020/10/07/#eclair-1539)
* [反向前向费用以减轻阻塞](https://bitcoinops.org/en/newsletters/2020/02/26/#reverse-up-front-payments)

**2019**

* [Hashcash 和基于退款的前向费用以减轻阻塞](https://bitcoinops.org/en/newsletters/2019/11/13/#ln-up-front-payments)

## 参见

* [HTLCs（哈希时间锁定合约）](https://bitcoinops.org/en/topics/htlc/)
* [HTLC 认可（HTLC Endorsement）](https://bitcoinops.org/en/topics/htlc-endorsement/)
