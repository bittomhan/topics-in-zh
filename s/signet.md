# Signet

**Signet** 既是一个工具，允许开发人员创建网络以测试不同比特币软件之间的交互，也是这些测试网络中最流行的名称。

Signet 上的区块只有在由创建该 signet 的密钥签名后才有效。这使得创建者完全控制区块产生，允许他们选择区块产生的速率或分叉发生的时间。这可以提供一个比工作量证明测试网更受控的网络环境，因为在测试网中，敌对矿工可以使用各种技巧使网络在长时间内实际上无法使用。

## 主要代码和文档

* [BIP325](https://github.com/bitcoin/bips/blob/master/bip-0325.mediawiki)
* [Signet](https://en.bitcoin.it/wiki/Signet)

## Optech 新闻简报和网站提及

**2023**

* [Mutinynet 推出一个具有 30 秒区块时间和托管基础设施工具的 signet](https://bitcoinops.org/en/newsletters/2023/05/24/#mutinynet-announces-new-signet-for-testing)
* [关于为什么 signet 使用与测试网相同的 bech32 地址前缀的问题](https://bitcoinops.org/en/newsletters/2023/01/25/#why-doesn-t-signet-use-a-unique-bech32-prefix)

**2022**

* [Eclair #2387 为 signet 添加支持](https://bitcoinops.org/en/newsletters/2022/08/31/#eclair-2387)
* [CTV signet 上交易的分析](https://bitcoinops.org/en/newsletters/2022/04/27/#analyzed)
* [为 `OP_CHECKTEMPLATEVERIFY` signet 发布的参数](https://bitcoinops.org/en/newsletters/2022/02/23/#ctv-signet)

**2021**

* [2021 年回顾：signet](https://bitcoinops.org/en/newsletters/2021/12/22/#signet)
* [为 taproot 做准备：在 signet 上测试](https://bitcoinops.org/en/newsletters/2021/09/22/#preparing-for-taproot-14-testing-on-signet)
* [关于在默认 signet 中添加定期重组的讨论](https://bitcoinops.org/en/newsletters/2021/09/15/#signet-reorg-discussion)
* [LND #5025 为使用 signet 添加基本支持](https://bitcoinops.org/en/newsletters/2021/06/02/#lnd-5025)
* [关于多个 signet 与软分叉激活的兼容性讨论](https://bitcoinops.org/en/newsletters/2021/04/14/#taproot-activation-discussion)
* [比特币核心 0.21.0 发布，支持 signet](https://bitcoinops.org/en/newsletters/2021/01/20/#bitcoin-core-0-21-0)
* [比特币核心 #19937 为挖掘 signet 区块添加实用工具](https://bitcoinops.org/en/newsletters/2021/01/20/#bitcoin-core-19937)

**2020**

* [2020 年回顾：signet](https://bitcoinops.org/en/newsletters/2020/12/23/#signet)
* [比特币核心 #20145 添加脚本请求 signet 硬币的支持](https://bitcoinops.org/en/newsletters/2020/11/25/#bitcoin-core-20145)
* [关于添加 signet 支持的比特币核心 PR 审查会议摘要](https://bitcoinops.org/en/newsletters/2020/10/14/#bitcoin-core-pr-review-club)
* [C-Lightning #4068 和 #4078 更新 C-Lightning 的 signet 实现](https://bitcoinops.org/en/newsletters/2020/09/30/#c-lightning-4068)
* [比特币核心 #18267 和 #19993 为 signet 添加支持](https://bitcoinops.org/en/newsletters/2020/09/30/#bitcoin-core-18267)- [BIPs #983 为新的 signet 区块签名方法更新 BIP325](https://bitcoinops.org/en/newsletters/2020/09/09/#bips-983)
* [关于默认 signet 的参数讨论](https://bitcoinops.org/en/newsletters/2020/09/02/#default-signet-discussion)
* [关于 signet 设计决策的讨论](https://bitcoinops.org/en/newsletters/2020/09/02/#signet)
* [signet 的可用性是否会消除对新测试网的需求？](https://bitcoinops.org/en/newsletters/2020/08/26/#will-there-be-a-testnet4-or-do-we-not-need-a-testnet-reset-once-we-have-signet)
* [BIP325 更新：所有 signet 使用相同的创世区块但不同的魔术](https://bitcoinops.org/en/newsletters/2020/05/06/#bips-900)

**2019**

* [2019 年回顾：signet](https://bitcoinops.org/en/newsletters/2019/12/28/#signet)
* [作为 BIP325 的 signet 协议发布](https://bitcoinops.org/en/newsletters/2019/11/13/#bips-803)
* [使用自定义 signet 实现 eltoo 的演示](https://bitcoinops.org/en/newsletters/2019/09/11/#eltoo-sample-implementation-and-discussion)
* [C-Lightning 0.7.2.1 发布，支持 signet](https://bitcoinops.org/en/newsletters/2019/08/21/#upgrade-to-c-lightning-0-7-2-1)
* [关于 signet 的进展](https://bitcoinops.org/en/newsletters/2019/07/24/#progress-on-signet)
* [C-Lightning 为 signet 添加支持](https://bitcoinops.org/en/newsletters/2019/07/24/#c-lightning-2816)
* [CoreDev.tech 讨论：signet](https://bitcoinops.org/en/newsletters/2019/06/12#signet)
* [关于 signet 的反馈请求](https://bitcoinops.org/en/newsletters/2019/03/12/#feedback-requested-on-signet)

## 参见

* [比特币核心 #16411：signet 支持](https://github.com/bitcoin/bitcoin/pull/16411)
