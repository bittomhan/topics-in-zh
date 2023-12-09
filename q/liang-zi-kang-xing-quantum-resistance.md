---
description: 也涵盖后量子密码学（Post-quantum cryptography）
---

# 量子抗性 - Quantum resistance

**量子抗性**是指加密协议在快速量子计算机存在的情况下仍然保持安全的能力。

比特币使用了各种加密协议，这些协议对快速量子计算机的脆弱程度各不相同：

* **SHA256、SHA256d 和 RIPEMD160**：在比特币的工作证明中以及唯一标识区块、脚本、单个交易和交易集合中有不同的应用，同时用于 [HTLCs](https://bitcoinops.org/en/topics/htlc/) 中的哈希锁。这些算法在理想化的量子计算机上运行的 [Grover 算法](https://en.wikipedia.org/wiki/Grover's\_algorithm)下，其安全强度将降至其平方根。例如，当前估计有 256 位（2^256）第二前像抗性的 SHA256 将降至 128 位（2^128 是 2^256 的平方根）。通过使用具有两倍安全位的大致等效算法（例如从 SHA256 升级到 SHA512），可以克服这种损失。
* **ECDSA**：比特币中使用的 ECDSA 公钥容易受到使用 [Shor 算法](https://en.wikipedia.org/wiki/Shor's\_algorithm)的因式分解攻击的影响。这将彻底消除 ECDSA 的安全性，假设有一个理想化的量子计算机。由于用于拟议的[椭圆曲线数字签名算法（Schnorr 签名）](https://bitcoinops.org/en/topics/schnorr-signatures/) 的公钥本质上与 ECDSA 使用的公钥相同，因此同样的攻击适用。已知 ECDSA 的量子抗性替代方案，但它们涉及更大的密钥和签名大小，因此大多数开发者似乎更愿意推迟升级，直到必要时再进行。
* **Noise**：是用于闪电网络（LN）中加密通信的[协议框架](https://duo.com/labs/tech-notes/noise-protocol-framework-intro)。Optech 尚未看到其量子抗性的讨论，但我们认为 LN 当前对其的依赖取决于 ECDSA 的安全性，因此如果快速量子计算机被开发出来，它们可能能够解密 LN 节点之间的旧通信。已知其他密钥交换机制，例如 [NewHope](https://newhopecrypto.org/)，并且提议在比特币的其他部分实施，例如[第 2 版比特币传输协议](https://bitcoinops.org/en/topics/v2-p2p-transport/)。

攻击的最坏情况假设有足够容量和可靠性以执行攻击的理想化量子计算机。量子计算机的容量和可靠性可能会随着时间的推移逐渐增加，这意味着比特币中使用的加密学的安全性也将随着时间逐渐降低，攻击将从计算上不可行，理论上可能但不太可能，到极其昂贵，到非常昂贵，到实际可行。只要这种进展得以遵循并且能够公开追踪，比特币就可能在其安全时继续使用目前高度空间效率的加密学，并在看起来将很快变得必要时升级到后量子密码学。

## Optech 新闻简报和网站提及

**2022**

* [2022 年回顾：量子安全密钥交换](https://bitcoinops.org/en/newsletters/2022/12/21/#quantum-safe-keys)
* [关于量子安全密钥交换的讨论](https://bitcoinops.org/en/newsletters/2022/04/20/#quantum-safe-key-exchange)

**2021**

* [关于量子计算机对 Taproot 攻击的讨论](https://bitcoinops.org/en/newsletters/2021/03/24/#discussion-of-quantum-computer-attacks-on-taproot)

**2020**

* [关于直接支付公钥与哈希间接的问题](https://bitcoinops.org/en/newsletters/2020/04/29/#what-are-the-potential-attacks-against-ecdsa-that-would-be-possible-if-we-used-raw-public-keys-as-addresses)
* [关于 Taproot 是否会创造来自量子威胁的安全风险的问题](https://bitcoinops.org/en/newsletters/2020/02/26/#could-taproot-create-larger-security-risks-or-hinder-future-protocol-adjustments-re-quantum-threats)

**2019**

* [关于哈希公钥是否真的提供量子抗性的问题](https://bitcoinops.org/en/newsletters/2019/10/30/#why-does-hashing-public-keys-not-actually-provide-any-quantum-resistance)
* [Bitcoin Core 贡献者会议记录：Taproot 量子讨论](https://bitcoinops.org/en/newsletters/2019/06/12/#taproot-accumulator-quantum)

**2018**

* [BIP151 讨论，包括关于 NewHope 量子抗性密钥交换的内容](https://bitcoinops.org/en/newsletters/2018/09/11/#bip151-discussion)
* [为 BIP151 支持打开的 PR，后续将跟进 NewHope 量子抗性](https://bitcoinops.org/en/newsletters/2018/08/28/#pr-opened-for-initial-bip151-support)

## 参见

* [Taproot](https://bitcoinops.org/en/topics/taproot/)
* [第 2 版 P2P 传输](https://bitcoinops.org/en/topics/v2-p2p-transport/)
