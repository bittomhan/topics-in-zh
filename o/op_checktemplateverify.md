# OP\_CHECKTEMPLATEVERIFY

**OP\_CHECKTEMPLATEVERIFY (CTV)** 是一种提议的新操作码，它以一个承诺哈希作为参数，并要求执行该操作码的任何交易包括与该承诺相匹配的一组输出。这使得可以创建一个地址，指定发送到该地址的任何资金如何被花费——在比特币中被称为 \* 契约 \* 的设计。

最初以 **OP\_CHECKOUTPUTSHASHVERIFY**（COSHV）的名字引入，该提议最初侧重于创建_拥塞控制交易_的能力，其中花费者使用 CTV 支付给单个地址，一旦确认到适当的深度，就确保几个接收者中的每一个都可以被支付。这个两步过程可能可以在任何支付批处理是一个选项的地方使用，但它可能进一步降低费用，甚至超过支付批处理。

该提议的后续版本更加强调使用新操作码创建其他合约和[契约](https://bitcoinops.org/en/topics/covenants/)的能力，例如创建[通道工厂](https://bitcoinops.org/en/topics/channel-factories/)、[金库](https://bitcoinops.org/en/topics/vaults/)和[混币交易](https://bitcoinops.org/en/topics/coinjoin/)的能力，这些可能以简化构建或降低费用的新方式实现。其他作者提到，新操作码可能被用于允许用户无信任地[合并他们的资金](https://gist.github.com/harding/a30864d0315a0cebd7de3732f5bd88f0)到一个单一的 UTXO 中，以增加隐私。

对该提议的批评集中于它对拥塞控制用例过于[具体](https://bitcointalk.org/index.php?topic=5220520.msg53710072#msg53710072)，而不是提供一个[通用](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2019-May/016946.html)的契约能力。

## 主要代码和文档

* [BIP119](https://github.com/bitcoin/bips/blob/master/bip-0119.mediawiki)

## Optech 新闻简报和网站提及

**2023**

* [使用 OP\_CTV 和 APO 等契约改进 LN 的可扩展性](https://bitcoinops.org/en/newsletters/2023/09/27/#using-covenants-to-improve-ln-scalability)
* [使用 OP\_CSFS 和 OP\_TXHASH 提出的 OP\_CTV 和 APO 的混合](https://bitcoinops.org/en/newsletters/2023/08/30/#covenant-mashup-using-txhash-and-csfs)
* [使用 MATT 风格的契约复制 CTV 特性的示例](https://bitcoinops.org/en/newsletters/2023/06/07/#using-matt-to-replicate-ctv-and-manage-joinpools)
* [使用 MATT 风格的契约和 CTV 分析 `OP_VAULT` 的替代设计](https://bitcoinops.org/en/newsletters/2023/05/03/#matt-based-vaults)
* [提出 `OP_UNVAULT` 操作码，可以模仿 CTV](https://bitcoinops.org/en/newsletters/2023/01/18/#proposal-for-new-vault-specific-opcodes)

**2022**

* [用于测试的比特币核心软件分支的新版本，包括对 CTV 的支持](https://bitcoinops.org/en/newsletters/2022/09/28/#bitcoin-implementation-designed-for-testing-soft-forks-on-signet)
* [提议最初限制 `OP_TX` 到 `OP_CTV` 提供的功能](https://bitcoinops.org/en/newsletters/2022/05/18/#updated-op-tx-proposal)
* [BIPs #1309 更新 BIP119 的示例实现，使用 Python 风格的伪代码](https://bitcoinops.org/en/newsletters/2022/05/18/#bips-1309)
* [关于裸露的 CTV 没有地址格式的影响](https://bitcoinops.org/en/newsletters/2022/04/27/#noted)
* [关于激活 CTV 的讨论](https://bitcoinops.org/en/newsletters/2022/04/27/#discussion-about-activating-ctv)
* [关于 CTV 的持续讨论和基于 CTV 的金库设计](https://bitcoinops.org/en/newsletters/2022/03/16/#continued-ctv-discussion)
* [发布 `OP_CHECKTEMPLATEVERIFY` 的 signet 参数](https://bitcoinops.org/en/newsletters/2022/02/23/#ctv-signet)
* [作为 CTV 和 APO 替代方案的 OP\_TXHASH 提议](https://bitcoinops.org/en/newsletters/2022/02/02/#composable-alternatives-to-ctv-and-apo)
* [关于 CTV 或其他契约功能如何使 DLCs 更加高效的讨论](https://bitcoinops.org/en/newsletters/2022/02/02/#improving-dlc-efficiency-by-changing-script)
* [关于 CTV 的邮件列表和 IRC 讨论，包括批评和反驳](https://bitcoinops.org/en/newsletters/2022/01/19/#op-checktemplateverify-discussion)
* [为审查和讨论 `OP_CHECKTEMPLATEVERIFY` 定期安排双周 IRC 会议](https://bitcoinops.org/en/newsletters/2022/01/05/#bip119-ctv-review-workshops)

**2021**

* [BIPs #1215 对 BIP119 OP\_CHECKTEMPLATEVERIFY 提议进行了多项更新](https://bitcoinops.org/en/newsletters/2021/11/10/#bips-1215)
* [Sapio 的公开发布，支持使用 `OP_CHECKTEMPLATEVERIFY`](https://bitcoinops.org/en/newsletters/2021/04/21/#sapio-public-launch)

**2020**

* [Sapio：使用 OP\_CHECKTEMPLATEVERIFY 构建合约的新语言](https://bitcoinops.org/en/newsletters/2020/08/05/#sapio)
* [使用 OP\_CHECKTEMPLATEVERIFY 的金库原型和示例实现](https://bitcoinops.org/en/newsletters/2020/04/22/#vaults-prototype)
* [OP\_CHECKTEMPLATEVERIFY 研讨会总结](https://bitcoinops.org/en/newsletters/2020/02/12/#op-checktemplateverify-ctv-workshop)
* [BIPs #875 将 BIP119 分配给 OP\_CHECKTEMPLATEVERIFY 提议](https://bitcoinops.org/en/newsletters/2020/01/29/#bips-875)

**2019**

* [2019 年回顾：OP\_CHECKTEMPLATEVERIFY](https://bitcoinops.org/en/newsletters/2019/12/28/#ctv)
* [OP\_CHECKTEMPLATEVERIFY (CTV)替代 COSHV 提议；重新阐述关注点](https://bitcoinops.org/en/newsletters/2019/12/04/#op-checktemplateverify-ctv)
* [潜在脚本更改，包括新的 COSHV 操作码](https://bitcoinops.org/en/newsletters/2019/06/12/#potential-script-changes)
* [替换 COSHV 提议](https://bitcoinops.org/en/newsletters/2019/06/05/#coshv-proposal-replaced)
* [关于交易输出承诺的新操作码提议](https://bitcoinops.org/en/newsletters/2019/05/29/#proposed-new-opcode-for-transaction-output-commitments)
* [**详细总结：提议的交易输出承诺**](https://bitcoinops.org/en/newsletters/2019/05/29/#proposed-transaction-output-commitments)

## 参见

* [契约](https://bitcoinops.org/en/topics/covenants/)
