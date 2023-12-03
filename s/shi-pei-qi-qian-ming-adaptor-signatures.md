---
description: 同时涵盖签名适配器（Signature Adaptors）和适配器签名（Adaptor Signatures）
---

# 无脚本脚本 - Scriptless Scripts

**适配器签名**（也称为**签名适配器**）是一种辅助签名数据，它承诺隐藏一个值。当适配器与相应的签名结合时，它会揭示这个隐藏值。相反，当与隐藏值结合时，适配器揭示签名。其他人可以创建二次适配器，即使他们不知道隐藏值，也可以重用承诺。这使得适配器成为实现比特币合约中锁定的强大工具。

在比特币合约中，经常需要一个锁定机制来确保一组支付的原子性——要么所有支付都成功，要么都失败。这种锁定传统上是通过让集合中的所有支付承诺相同的哈希原像（preimage）来完成的；当知道前置的一方在链上（onchain）揭示它时，其他人也会了解它，并且可以解锁他们自己的支付。在比特币中常用的哈希锁（hashlocks）消耗大约 67 字节，并因为它们都使用相同的前置和摘要而揭示了支付集合之间的联系。

相比之下，签名适配器从不需要在链上公开。对于没有对应适配器的任何人来说，使用适配器创建的签名看起来像任何其他数字签名，使得适配器在效率和隐私方面比哈希锁具有显著的优势。

## 示例

可以在简单的币换协议中看到签名适配器的多种用途。例如，Alice 可以给 Bob 一个未签名交易的适配器，承诺支付他 1 BTC。适配器本身不能作为 BIP340 签名使用，所以 Alice 还没有支付给 Bob。

适配器为 Bob 提供的是对 Alice 的隐藏值的承诺。这个承诺包括一个参数，Bob 可以使用它来创建第二个适配器，承诺与 Alice 的适配器相同的隐藏值。即使 Bob 不知道 Alice 的隐藏值或他自己对那个承诺的签名，他也可以做出这个承诺。Bob 给 Alice 他的适配器和一个对应的未签名交易，承诺支付给她 1 BTC。

Alice 一直知道隐藏值，所以她可以将隐藏值与 Bob 的适配器结合，得到支付给她的交易的签名。她广播交易并收到 Bob 的支付。当 Bob 在链上看到那笔交易时，他可以将它的签名与他给 Alice 的适配器结合，从而推导出隐藏值。然后他可以将那个隐藏值与 Alice 之前给他的适配器结合。Bob 广播那笔交易以接收 Alice 的支付，完成币换。

除了币换，还有几种其他[提出的适配器签名用途](https://github.com/ElementsProject/scriptless-scripts)。

* 点击显示相同币换示例的数学术语 \*
* 在以下示例中，我们假设使用 BIP340 施诺尔（Schnorr）签名。我们用小写变量表示标量，用大写变量表示

椭圆曲线点。我们用 `||` 表示连接，用 `H()` 表示哈希函数。\* Alice 使用她的私钥（`p`），对应于她的公钥（`P = pG`），为支付给 Bob 的交易（`m`）创建了一个有效的签名承诺（`s`）。她还使用了一个私有随机 nonce（`r`）、一个隐藏值（`t`）及其椭圆曲线点（`R = rG, T = tG`）：

`s = r + t + H(R + T || P || m) * p`

她从签名承诺中减去 `t`，产生一个签名适配器：

`s' = s - t`

她给 Bob 的适配器包含以下数据：

`s', R, T`

Bob 可以验证适配器：

`s' * G ?= R + H(R + T || P || m) * P`

但适配器不是有效的 BIP340 签名。对于有效的签名，BIP340 期望 `x` 和 `Y`，使用表达式：

`x * G ?= Y + H(Y || P || m) * P`

然而， · 如果 Bob 将 `Y = R` 设置为与他在适配器中收到的 `s'` 匹配，那么 BIP340 将会因为 `H(R || P || m)` 而失败，因为 Alice 计算她的哈希是用的 `H(R + T || P || m)`。 · 如果 Bob 将 `Y = R + T` 设置为与 `H(R + T || P || m)` 匹配，BIP340 将会因为初始的 `Y` 而失败，因为 Bob 提供的是 `R + T` 而不是所需的 `R`。 因此 Bob 不能将适配器用作 BIP340 签名。然而，他可以使用它创建他自己的适配器。这类似于 Alice 创建的签名，但 Bob 在这里不承诺 `t`，因为 Bob 不知道这个值。除了 `T` 外，这里的所有变量对于 Bob 来说都与 Alice 不同：

`s = r + H(R + T || P || m) * p`

与 Alice 不同，Bob 不需要调整他的签名。Bob 的签名承诺 `s` 不是有效签名的一部分，因为它承诺了 `r` 和 `R + T`，由于之前描述的相同原因，这些无法通过 BIP340 验证。要有效，签名需要承诺 `r + t` 和 `R + T`，而 Bob 无法产生这些，因为他不知道 `t`。 Bob 给 Alice 他的适配器：

`s, R, T`

Alice 已经知道 `T`，但 `(s, R, T)` 是标准的签名适配器，所以我们使用它的完整形式。Alice 可以使用她所知的隐藏的 `t` 值从那个适配器产生签名：

`(s + t) * G ?= R + T + H(R + T || P || m) * P`

Alice 使用该签名广播 Bob 的支付给她的交易。当 Bob 在链上看到 `(s + t)` 时，他可以学到 `t` 的值：

`t = (s + t) - s`

然后他可以使用 `t` 解决 Alice 早先给他的适配器：

`(s' + t) * G ?= R + T + H(R + T || P || m) * P`

Bob 使用该签名广播 Alice 最初给他的交易。

## 与多方签名的关系

通常，签名适配器本身无法完全保障合约的安全。例如，在上述币换（coinswap）的描述中，Alice 在学习到 Bob 的签名后，可能会对她支付给 Bob 的款项进行双重支付，或者 Bob 也可能尝试相反的操作（尽管我们假设 Alice 的交易已经获得了一个确认，这更难）。这个问题通常通过将签名适配器与多方签名相结合来解决。例如，Alice 将她的资金存入一个地址，只有在她和 Bob 合作创建有效签名时才能花费。现在，Alice 可以为她在多方签名中的一半提供给 Bob 一个适配器，Bob 可以完全安全地接受它，因为他知道 Alice 在没有他的参与下无法双重支付这些资金。这可能还需要一个定时锁定的退款选项，以防一方拒绝签名。

在[施诺尔签名方案（Schnorr Signature Scheme）](https://bitcoinops.org/en/topics/schnorr-signatures/)中，通常建议将签名适配器与多方签名方案（如 [MuSig](https://bitcoinops.org/en/topics/musig/)）结合起来，使发布的签名看起来像单方签名，从而提高隐私和效率。这在 ECDSA 中也是可能的，但它需要新颖的算法，这些算法要么相对较慢，要么需要额外的安全假设。相反，比特币存在一种使用 2-of-2 `OP_CHECKSIG` 多重签名的[适配器签名替代方案](https://github.com/LLFourn/one-time-VES/blob/master/main.pdf)；这种方法效率较低，可能隐私性也较差——但可以说更简单、更安全，而非多方 ECDSA。

## 主要代码与文档

* [无脚本脚本幻灯片 (PDF)](https://download.wpsoftware.net/bitcoin/wizardry/mw-slides/2017-05-milan-meetup/slides.pdf)
* [一次性可验证加密签名 (PDF)](https://github.com/LLFourn/one-time-VES/blob/master/main.pdf)
* [无脚本脚本协议文档](https://github.com/BlockstreamResearch/scriptless-scripts)

## Optech 新闻稿和网站提及

**2023 年**

* [适配器签名安全性分析](https://bitcoinops.org/en/newsletters/2023/05/03/#analysis-of-signature-adaptor-security)
* [使用签名适配器证明接受了 LN 异步支付](https://bitcoinops.org/en/newsletters/2023/02/01/#ln-async-proof-of-payment)

**2021 年**

* [为 taproot 准备：签名适配器](https://bitcoinops.org/en/newsletters/2021/08/18/#preparing-for-taproot-9-signature-adaptors)
* [问题：为什么区块范围的签名聚合会阻止适配器签名？](https://bitcoinops.org/en/newsletters/2021/06/30/#why-does-blockwide-signature-aggregation-prevent-adaptor-signatures)
* [Libsecp256k1-zkp #117 添加了对简化 ECDSA 签名适配器的支持](https://bitcoinops.org/en/newsletters/2021/04/28/#support-for-ecdsa-signature-adaptors-added-to-libsecp256k1-zkp)

**2020 年**

* [2020 年度回顾：LN 通道承诺的签名适配器](https://bitcoinops.org/en/newsletters/2020/12/23/#ptlcs)
* [修订的见证不对称通道提议与签名适配器](https://bitcoinops.org/en/newsletters/2020/10/14/#updated-witness-asymmetric-payment-channel-proposal)
* [使用签名适配器实现见证不对称支付通道](https://bitcoinops.org/en/newsletters/2020/09/02/#witness-asymmetric-payment-channels)
* [使用签名适配器支付 PTLC 点锁](https://bitcoinops.org/en/newsletters/2020/06/24/#continued-discussion-about-ln-atomicity-attack)
* [使用简化 ECDSA 签名适配器为 LN 的 PTLCs 工作](https://bitcoinops.org/en/newsletters/2020/04/08/#work-on-ptlcs-for-ln-using-simplified-ecdsa-adaptor-signatures)
* [使用安全多方计算的状态链上的 ECDSA 签名适配器](https://bitcoinops.org/en/newsletters/2020/04/01/#implementing-statechains-without-schnorr-or-eltoo)
* [使用签名适配器实现 LN 延迟和吞吐量的回旋合约](https://bitcoinops.org/en/newsletters/2020/02/26/#boomerang-redundancy-improves-latency-and-throughput-in-payment-channel-networks)
* [Taproot 隐私增益，包括签名适配器带来的增益](https://bitcoinops.org/en/newsletters/2020/02/19/#tap1)

**2019 年**

* [演讲：区块链设计模式：层次和扩展方法](https://bitcoinops.org/en/newsletters/2019/09/18/#blockchain-design-patterns-layers-and-scaling-approaches)
* [Libsecp256k1-zkp 库更新支持签名适配器](https://bitcoinops.org/en/newsletters/2019/02/26/#schnorr-ready-fork-of-libsecp256k1-available)
* [问答：taproot 和签名适配器有什么区别？](https://bitcoinops.org/en/newsletters/2019/02/26/#taproot-and-scriptless-scripts-both-use-schnorr-but-how-are-they-different)

**2018 年**

* [关于使用签名适配器解决 LN 问题的讨论](https://bitcoinops.org/en/newsletters/2018/11/06/#discussion-about-improving-lightning-payments)
* [与签名适配器兼容的快速多方 ECDSA](https://bitcoinops.org/en/newsletters/2018/10/23/#two-papers-published-on-fast-multiparty-ecdsa)
* [无脚本 LN 通道的多方 ECDSA](https://bitcoinops.org/en/newsletters/2018/10/09/#multiparty-ecdsa-for-scriptless-lightning-network-payment-channels)

## 参见

* [施诺尔签名](https://bitcoinops.org/en/topics/schnorr-signatures/)
* [MuSig 密钥和签名聚合](https://bitcoinops.org/en/topics/musig/)
* [使用施诺尔减法创建更私密的币换](https://joinmarket.me/blog/blog/flipping-the-scriptless-script-on-schnorr/)
* [离散对数合约中的适配器签名](https://lists.launchpad.net/mimblewimble/msg00485.html)
