# Taproot

**Taproot** 是对比特币的一项建议的软分叉更改，将允许对 Schnorr 公钥进行支付，这些公钥可能选择性地承诺在花费时透露脚本。

通过塔普鲁特保护的硬币可以通过满足其中一个承诺的脚本来花费，或者仅通过提供针对公钥验证的签名来花费（允许脚本保持私密）。塔普鲁特旨在与简化多方构造的 Schnorr 签名（例如使用 [MuSig](https://bitcoinops.org/en/topics/musig/)）以及 MAST 一起使用，以允许承诺多个脚本，花费时可以使用其中任何一个。

## 主要代码和文档

* [BIP341](https://github.com/bitcoin/bips/blob/master/bip-0341.mediawiki)
* [原始描述](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2018-January/015614.html)
* [原始实现](https://github.com/bitcoin/bitcoin/pull/19953)

## Optech 新闻简报和网站提及

**2023**

* [LND v0.17.0-beta 发布，实验性支持塔普鲁特和 MuSig2 闪电网络通道](https://bitcoinops.org/en/newsletters/2023/10/04/#lnd-v0-17-0-beta)
* [塔普鲁特和 MuSig2 闪电网络通道](https://bitcoinops.org/en/newsletters/2023/07/26/#taproot-and-musig2-channels)

**2022**

* [为什么 P2TR 输出应当在只需密钥路径花费时使用 noscript 承诺](https://bitcoinops.org/en/newsletters/2022/06/29/#bip-341-should-key-path-only-p2tr-be-eschewed-altogether)
* [LND #6450 增加了对消费塔普鲁特输出的 PSBT 签名的支持](https://bitcoinops.org/en/newsletters/2022/05/18/#lnd-6450)
* [Bitcoin Core #23536 开始对所有区块（除一个外）强制执行塔普鲁特](https://bitcoinops.org/en/newsletters/2022/04/06/#bitcoin-core-23536)
* [问题：是否可以将塔普鲁特地址转换为 v0 原生隔离见证地址？](https://bitcoinops.org/en/newsletters/2022/01/26/#is-it-possible-to-convert-a-taproot-address-into-a-v0-native-segwit-address)

**2021**

* [2021 年回顾：Taproot](https://bitcoinops.org/en/newsletters/2021/12/22/#taproot)
* [Taproot 在区块高度 709,632 激活](https://bitcoinops.org/en/newsletters/2021/11/17/#taproot-activated)
* [BIPs #1225 更新了 BIP341，增加了扩展的 Taproot 测试向量](https://bitcoinops.org/en/newsletters/2021/11/17/#bips-1225)
* [发布了针对 Taproot 的扩展测试向量](https://bitcoinops.org/en/newsletters/2021/11/03/#taproot-test-vectors)
* [Taproot 琐事：起源、命名及相关先前工作](https://bitcoinops.org/en/newsletters/2021/10/20/#preparing-for-taproot-18-trivia)
* [准备 Taproot：合作是否总是一个选项？](https://bitcoinops.org/en/newsletters/2021/10/13/#preparing-for-taproot-17-is-cooperation-always-an-option)
* [Specter v1.6.0 增加了对单键 Taproot 的支持](https://bitcoinops.org/en/newsletters/2021/09/22/#specter-v1-6-0-supports-single-key-taproot)
* [Fully Noded v0.2.26 增加了对 P2TR 接收和支出的支持](https://bitcoinops.org/en/newsletters/2021/09/22/#fully-noded-v0-2-26-released)
* [BTCPay 服务器 #2830 增加了对 P2TR 接收和支出的支持](https://bitcoinops.org/en/newsletters/2021/09/15/#btcpay-server-2830)
* [为 Taproot 更新 LN：P2TR 通道](https://bitcoinops.org/en/newsletters/2021/09/01/#preparing-for-taproot-11-ln-with-taproot)
* [Sparrow 钱包增加了对 P2TR 键路径花费在 regtest 和 signet 上的支持](https://bitcoinops.org/en/newsletters/2021/07/21/#sparrow-1-4-3-supports-p2tr)
* [BIPs #1137 增加了 BIP86，为单键 P2TR 输出提供了密钥派生方案](https://bitcoinops.org/en/newsletters/2021/07/07/#bips-1137)
* [提议的 BIP 以标准化单签名 P2TR 地址的钱包路径](https://bitcoinops.org/en/newsletters/2021/06/30/#key-derivation-path-for-single-sig-p2tr)
* [Bitcoin Core #21365 允许钱包为 P2TR 支出创建签名](https://bitcoinops.org/en/newsletters/2021/06/23/#bitcoin-core-21365)
* [Taproot 锁定；激活将在区块 709,632 发生](https://bitcoinops.org/en/newsletters/2021/06/16/#taproot-locked-in)
* [Bitcoin Core #22051 增加了对导入 Taproot 输出描述符的支持](https://bitcoinops.org/en/newsletters/2021/06/09/#bitcoin-core-22051)
* [Rust Bitcoin #589 开始实现对 Taproot 和 Schnorr 签名的支持](https://bitcoinops.org/en/newsletters/2021/05/12/#rust-bitcoin-589)
* [鼓励矿工开始为 Taproot 做好准备](https://bitcoinops.org/en/newsletters/2021/05/05/#miners-encouraged-to-start-signaling-for-taproot)
* [发布 Bitcoin Core 0.21.1，准备激活 Taproot](https://bitcoinops.org/en/newsletters/2021/05/05/#bitcoin-core-0-21-1)
* [BIPs #1104 为 BIP341 Taproot 规范增加了激活参数](https://bitcoinops.org/en/newsletters/2021/05/05/#bips-1104)
* [Bitcoin Core #21377 和 #21686 增加了 Taproot 激活机制和参数](https://bitcoinops.org/en/newsletters/2021/04/21/#bitcoin-core-21377)
* [提出了使用 MTP 进行 Taproot 快速试验激活的妥协方案](https://bitcoinops.org/en/newsletters/2021/04/14/#taproot-activation-discussion)
* [定期会议安排以帮助激活 Taproot](https://bitcoinops.org/en/newsletters/2021/03/24/#weekly-taproot-activation-meetings)
* [关于量子计算机对 Taproot 的攻击讨论](https://bitcoinops.org/en/newsletters/2021/03/24/#discussion-of-quantum-computer-attacks-on-taproot)
* [记录使用和建立在 Taproot 之上的意图](https://bitcoinops.org/en/newsletters/2021/03/10/#documenting-the-intention-to-use-and-build-upon-taproot)
* [讨论了激活 Taproot 的其他方法](https://bitcoinops.org/en/newsletters/2021/03/10/#taproot-activation-discussion)
* [关于 BIP8 `LOT` 参数的 Taproot 激活讨论摘要](https://bitcoinops.org/en/newsletters/2021/02/24/#taproot-activation-discussion)
* [Taproot 激活讨论摘要和安排了额外会议](https://bitcoinops.org/en/newsletters/2021/02/10/#taproot-activation-meeting-summary-and-follow-up)
* [讨论 Taproot 激活机制的会议](https://bitcoinops.org/en/newsletters/2021/01/27/#scheduled-meeting-to-discuss-taproot-activation)

**2020**

* [2020 年回顾：Taproot、Tapscript 和 Schnorr 签名](https://bitcoinops.org/en/newsletters/2020/12/23/#taproot)
* [在信号开始前追踪矿工对 Taproot 支持的网站](https://bitcoinops.org/en/newsletters/2020/11/25/#website-listing-miner-support-for-taproot-activation)
* [关于向开发者调查 Taproot 激活的结果摘要](https://bitcoinops.org/en/newsletters/2020/11/04/#taproot-activation-survey-results)
* [Bitcoin Core #19953 合并了 BIP341 的共识实现](https://bitcoinops.org/en/newsletters/2020/10/21/#bitcoin-core-19953)
* [关于 Taproot 激活参数的讨论](https://bitcoinops.org/en/newsletters/2020/09/02/#taproot-activation)
* [讨论了各种主题，包括 Taproot 激活](https://bitcoinops.org/en/newsletters/2020/08/05/#sydney-meetup-discussion)
* [升级 LN 承诺格式，包括对 Taproot 的支持](https://bitcoinops.org/en/newsletters/2020/07/29/#upgrading-channel-commitment-formats)
* [关于 Taproot 升级中不同功能的问题](https://bitcoinops.org/en/newsletters/2020/07/29/#what-are-the-different-upgradability-features-in-the-bip-taproot-bip341-proposal)
* [关于 Taproot 中叶版本的问题](https://bitcoinops.org/en/newsletters/2020/07/29/#what-are-leaf-versions-in-taproot)
* [关于为 Taproot 激活回溯 wtxid 中继的讨论](https://bitcoinops.org/en/newsletters/2020/07/29/#bitcoin-core-18044)
* [为讨论 Taproot 激活而新设的聊天室](https://bitcoinops.org/en/newsletters/2020/07/22/#new-irc-room)
* [Coinpool：使用 Taproot 帮助创建支付池](https://bitcoinops.org/en/newsletters/2020/06/17/#coinpool-generalized-privacy-for-identifiable-onchain-protocols)
* [Taproot 消除了与 Segwit 费用过支付攻击相关的漏洞](https://bitcoinops.org/en/newsletters/2020/06/10/#fee-overpayment-attack-on-multi-input-segwit-transactions)
* [BIP341 交易摘要修订，增加了对 scriptPubKeys 的额外承诺](https://bitcoinops.org/en/newsletters/2020/06/10/#bips-920)
* [多签名 Taproot 交易的示例大小](https://bitcoinops.org/en/newsletters/2020/05/27/#what-are-the-sizes-of-single-sig-and-2-of-3-multisig-taproot-inputs)
* [关于修改 BIP341 Taproot 交易摘要的意见征求](https://bitcoinops.org/en/newsletters/2020/05/20/#evaluate-proposed-changes-to-bip341-taproot-transaction-digest)
* [要求对之前的 scriptPubKeys 增加额外的签名承诺](https://bitcoinops.org/en/newsletters/2020/05/13/#request-for-an-additional-taproot-signature-commitment)
* [安全分析：在通用组模型中的 Taproot](https://bitcoinops.org/en/newsletters/2020/03/04/#taproot-in-the-generic-group-model)
* [Taproot 对量子计算威胁的安全性](https://bitcoinops.org/en/newsletters/2020/02/26/#could-taproot-create-larger-security-risks-or-hinder-future-protocol-adjustments-re-quantum-threats)
* [关于 Taproot 与其他替代方案的讨论](https://bitcoinops.org/en/newsletters/2020/02/19/#discussion-about-taproot-versus-alternatives)
* [btcdeb 增加了 `tap` 命令，用于实验 Taproot 和 Tapscript](https://bitcoinops.org/en/newsletters/2020/02/05/#taproot-and-tapscript-experimentation-tool)
* [最终的组织审查、演示幻灯片和 LN 集成思路](https://bitcoinops.org/en/newsletters/2020/01/08/#final-week-of-organized-taproot-review)

**2019**

* [2019 年回顾：Taproot](https://bitcoinops.org/en/newsletters/2019/12/28/#taproot)
* [bech32 长度变化可变性对 v1 Segwit 脚本长度的影响](https://bitcoinops.org/en/newsletters/2019/11/13/#taproot-review-discussion-and-related-information)
* [关于仅 x 坐标的 Schnorr 公钥的博客文章](https://bitcoinops.org/en/newsletters/2019/11/13/#x-only-pubkeys)
* [**Bitcoin Optech Schnorr/Taproot 研讨会**](https://bitcoinops.org/en/schorr-taproot-workshop/)
* [Taproot 结构化审查的公告](https://bitcoinops.org/en/newsletters/2019/10/23/#taproot-review)
* [关于 Schnorr、Taproot 和 Tapscript 变更的更新](https://bitcoinops.org/en/newsletters/2019/10/16/#taproot-update)
* [建议从 Taproot 提案中移除 P2SH 地址包装](https://bitcoinops.org/en/newsletters/2019/09/25/#comment-if-you-expect-to-need-p2sh-wrapped-taproot-addresses)
* [**执行简报：下一个软分叉**](https://bitcoinops.org/en/2019-exec-briefing/#the-next-softfork)
* [减小 Taproot 承诺大小](https://bitcoinops.org/en/newsletters/2019/05/29/#move-the-oddness-byte)
* [Taproot 和 Tapscript 概览](https://bitcoinops.org/en/newsletters/2019/05/14/#soft-fork-discussion)
* [**BIP-Taproot 和 BIP-Tapscript 扩展摘要**](https://bitcoinops.org/en/newsletters/2019/05/14/#overview-of-the-taproot--tapscript-proposed-bips)

**2018**

* [Taproot（2018 年 1 月的主要发展）](https://bitcoinops.org/en/newsletters/2018/12/28/#taproot)
* [Taproot 软分叉可能的样子](https://bitcoinops.org/en/newsletters/2018/12/18/#description-about-what-might-be-included-in-a-schnorr-taproot-soft-fork)

## 参见

* [MAST（Merklized Abstract Syntax Trees，默克尔化抽象语法树）](https://bitcoinops.org/en/topics/mast/)
* [Tapscript](https://bitcoinops.org/en/topics/tapscript/)
* [Schnorr 签名](https://bitcoinops.org/en/topics/schnorr-signatures/)
* [付费至合约（Pay-to-contract）](https://bitcoinops.org/en/topics/pay-to-contract-outputs/)
