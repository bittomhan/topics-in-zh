# 施诺尔签名 - Schnorr signatures

**施诺尔签名（Schnorr signatures）**是数字签名，提供与自比特币原始实现以来使用的 ECDSA 方案相似的安全性，并且可以使用比特币相同的椭圆曲线参数，但可以提供其他好处。

Schnorr 在与 [ECDSA（Elliptic Curve Digital Signature Algorithm）](https://en.wikipedia.org/wiki/Elliptic\_Curve\_Digital\_Signature\_Algorithm) 相同的密码学假设下是安全的，使用 Schnorr 的多方签名协议（如 [MuSig（Multi-Signature）](https://bitcoinops.org/en/topics/musig/)）创建安全的多方签名更简单、更快。新的签名类型还提供了将签名序列化格式从 [BER/DER（Basic Encoding Rules/Distinguished Encoding Rules）](https://en.wikipedia.org/wiki/Basic\_Encoding\_Rules) 更改为更紧凑、更易于实现的格式的机会。

## 主要代码和文档

* [BIP340](https://github.com/bitcoin/bips/blob/master/bip-0340.mediawiki)

## Optech 新闻简报和网站提及

**2023**

* [BIPs #1446 对 BIP340 规范进行了一些小改动和多项增加](https://bitcoinops.org/en/newsletters/2023/05/31/#bips-1446)

**2022**

* [BDK #718 在钱包创建 Schnorr 签名后立即开始验证](https://bitcoinops.org/en/newsletters/2022/08/31/#bdk-718)
* [LND #6722 添加了使用 Schnorr 签名对任意消息进行签名的支持](https://bitcoinops.org/en/newsletters/2022/07/20/#lnd-6722)
* [为什么 `OP_CHECKMULTISIG` 与 Schnorr 签名的批量验证不兼容？](https://bitcoinops.org/en/newsletters/2022/05/25/#why-isn-t-op-checkmultisig-compatible-with-batch-verification-of-schnorr-signatures)

**2021**

* [Libsecp256k1 #844 更新 Schnorr API 以允许对任意长度消息进行签名](https://bitcoinops.org/en/newsletters/2021/07/14/#libsecp256k1-844)
* [Rust Bitcoin #589 开始实现对 Taproot 和 Schnorr 签名的支持](https://bitcoinops.org/en/newsletters/2021/05/12/#rust-bitcoin-589)
* [SSS 与 `OP_CHECKMULTISIG` 相比，Schnorr 多签名的对比](https://bitcoinops.org/en/newsletters/2021/02/24/#is-sharding-a-good-alternative-to-multisig)

**2020**

* [2020 年回顾：Taproot、Tapscript 和 Schnorr 签名](https://bitcoinops.org/en/newsletters/2020/12/23/#taproot)
* [比特币核心 #19953 合并了 BIP340 的共识实现](https://bitcoinops.org/en/newsletters/2020/10/21/#bitcoin-core-19953)
* [Libsecp256k1 #558 实现了 Schnorr 签名的验证和签名](https://bitcoinops.org/en/newsletters/2020/09/16/#libsecp256k1-558)
* [BIPs #982 更新 BIP340 使用均匀性分解器和标记哈希](https://bitcoinops.org/en/newsletters/2020/09/02/#bips-982)
* [提议更新 BIP340 Schnorr 签名以使用均匀性分解器](https://bitcoinops.org/en/newsletters/2020/08/19/#proposed-uniform-tiebreaker-in-schnorr-signatures)
* [关于 Schnorr 签名的演讲和讨论](https://bitcoinops.org/en/newsletters/2020/07/01/#schnorr-signatures-and-multisignatures)
* [RFC6979 生成器与 BIP340 推荐程序的比较](https://bitcoinops.org/en/newsletters/2020/05/27/#why-isn-t-rfc6979-used-for-schnorr-signature-nonce-generation)
* [BIP340 Schnorr 更新了替代 x-only pubkey 分解器和标记哈希](https://bitcoinops.org/en/newsletters/2020/05/06/#bips-893)
* [减轻 Schnorr 签名中的差分功率分析](https://bitcoinops.org/en/newsletters/2020/04/01/#mitigating-differential-power-analysis-in-schnorr-signatures)
* [在没有 Schnorr 签名或 Eltoo 的情况下实现 Statechains](https://bitcoinops.org/en/newsletters/2020/04/01/#implementing-statechains-without-schnorr-or-eltoo)
* [提议更新 Schnorr 密钥选择和签名生成](https://bitcoinops.org/en/newsletters/2020/03/04/#updates-to-bip340-schnorr-keys-and-signatures)
* [BIP340 Schnorr 签名推荐更新以提高安全性](https://bitcoinops.org/en/newsletters/2020/03/04/#bips-886)
* [关于 Taproot 与其他 Schnorr 启用提案的讨论](https://bitcoinops.org/en/newsletters/2020/02/19/#discussion-about-taproot-versus-alternatives)
* [Schnorr 签名中预计算公钥的安全性](https://bitcoinops.org/en/newsletters/2020/02/05/#safety-concerns-related-to-precomputed-public-keys-used-with-schnorr-signatures)
* [BIP340 替代 x-only 公钥分解器和标记哈希](https://bitcoinops.org/en/newsletters/2020/02/05/#alternative-x-only-pubkey-tiebreaker)

**2019**

* [关于用于 Schnorr 签名方案的 x-only 公钥的博客文章](https://bitcoinops.org/en/newsletters/2019/11/13/#x-only-pubkeys)
* [**比特币 Optech Schnorr/Taproot 研讨会**](https://bitcoinops.org/en/schorr-taproot-workshop/)
* [关于结构化 Taproot 审查（包括 Schnorr）的公告](https://bitcoinops.org/en/newsletters/2019/10/23/#taproot-review)
* [关于 Schnorr、Taproot 和 Tapscript 的更新](https://bitcoinops.org/en/newsletters/2019/10/16/#taproot-update)
* [关于实用阈值 Schnorr 签名的追求演讲摘要](https://bitcoinops.org/en/newsletters/2019/10/16/#the-quest-for-practical-threshold-schnorr-signatures)
* [提议更改 Schnorr 公钥](https://bitcoinops.org/en/newsletters/2019/08/14/#proposed-change-to-schnorr-pubkeys)
* [**高管简报：下一个软分叉**](https://bitcoinops.org/en/2019-exec-briefing/#the-next-softfork)

**2018**

* [继续讨论 bip-schnorr（Schnorr 签名提案）](https://bitcoinops.org/en/newsletters/2018/07/17/#continuing-discussion-about-schnorr-signatures)
* [提议的 Schnorr BIP（Schnorr 签名提案）](https://bitcoinops.org/en/newsletters/2018/07/10/#featured-news-schnorr-signature-proposed-bip)

## 另见

* [Schnorr 软分叉是否会引入新的地址格式？](https://bitcoin.stackexchange.com/questions/82952/will-a-schnorr-soft-fork-introduce-a-new-address-format-i-e-not-bech32)
* [Taproot（隐形脚本）](https://bitcoinops.org/en/topics/taproot/)
* [无脚本多重签名（Scriptless multisignatures）](https://bitcoinops.org/en/topics/multisignature/)
