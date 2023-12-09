---
description: 也涵盖软分叉激活（Soft Fork Activation）和 BIP8
---

# BIP9

**软分叉激活（Soft Fork Activation）** 描述了比特币全节点开始强制执行一个或多个额外共识规则的时刻。这些转变在网络上的节点之间引入了协调风险，因此开发者多年来致力于创造和改进软分叉激活机制，以最小化出现问题的可能性。

软分叉允许整个网络过渡到新的共识规则，即使不是每个节点都采用了这些规则。然而，任何时候不同节点执行不同的规则，都存在着一些节点接受而其他节点拒绝不符合非统一规则的区块的风险，这可能导致共识失败（链分裂），从而导致已确认交易的双重支付和对比特币系统安全性的信心丧失。这是激活机制试图缓解的主要问题。

## 历史

新的软分叉激活机制的提议通常旨在避免之前软分叉中遇到的问题，因此本节试图提供对过去显著激活尝试的概述。

#### \[2009 年] 硬编码高度：共识 nLockTime 执行

已知的 [最早](https://bitcoin.stackexchange.com/questions/90229/nlocktime-in-bitcoin-core/99104#99104) 软分叉实现在比特币 0.1.6（2009 年 11 月发布）中，并且被硬编码在第 31,000 个区块激活，这发生在 2009 年 12 月 22 日。这种 _硬编码高度_ 激活机制被用于至少一个 [其他](https://github.com/bitcoin/bitcoin/commit/8c9479c6bbbc38b897dc97de9d04e4d5a5a36730#diff-608d8de3fba954c50110b6d7386988f27295de845e9d7174e40095ba5efcf1bbR1421-R1423) 早期软分叉，当时大多数开发工作由中本聪完成。

#### \[2011 年] 硬编码时间和手动干预：BIP12 `OP_EVAL` 失败

在中本聪离开开发后，合并到比特币的第一个软分叉代码是[BIP12](https://github.com/bitcoin/bips/blob/master/bip-0012.mediawiki) `OP_EVAL`。该计划使用 \* 硬编码时间 \* 激活方法和手动干预（如果少于 50% 的网络算力准备执行更改）。引用自 BIP12：

> \[…] 新客户端和矿工将被编码为将 OP\_EVAL 解释为无操作，直到 2012 年 2 月 1 日。在此之前，矿工将被要求在他们生产的区块中放入字符串“OP\_EVAL”，以便可以衡量支持新操作码的哈希率。如果截至 2012 年 1 月 15 日，少于 50% 的矿工接受更改，推出将被推迟，直到超过 50% 的哈希率支持 OP\_EVAL（如果明确地不会获得大多数哈希率的支持，则推出将被拒绝）。

在这种情况下可能需要手动干预，因为在激活代码合并但尚未发布之后，发现了 `OP_EVAL` 的[严重漏洞](https://github.com/bitcoin/bitcoin/issues/729)。尽管这个特定的漏洞已被[修复](https://github.com/bitcoin/bitcoin/pull/730)，但一些开发者担心这样一个强大的新操作码可能存在额外的问题，软分叉尝试被放弃。

#### \[2012 年] 硬编码时间和手动干预再次尝试：BIP16 P2SH

在 `OP_EVAL` 之后，提出了几种简化的替代方案（参见 BIPs [13](https://github.com/bitcoin/bips/blob/master/bip-0013.mediawiki)/[16](https://github.com/bitcoin/bips/blob/master/bip-0016.mediawiki)、[17](https://github.com/bitcoin/bips/blob/master/bip-0017.mediawiki)、[18](https://github.com/bitcoin/bips/blob/master/bip-0018.mediawiki) 和 [19](https://github.com/bitcoin/bips/blob/master/bip-0019.mediawiki) 以及 [其他想法](https://bitcointalk.org/index.php?topic=58579.msg690093#msg690093)），其中 BIPs 13/16 支付脚本哈希（Pay-to-Script-Hash, P2SH）[在开发者中获得了最多的支持](https://en.bitcoin.it/wiki/P2SH\_Votes)。P2SH [使用](https://github.com/bitcoin/bitcoin/commit/7bf8b7c25c944110dbe85ef9e4eebd858da34158) 了与 `OP_EVAL` 相同的激活机制。首次计划激活日期为 2012 年 3 月 1 日，但到 2 月 15 日的投票日期，最近 1000 个区块中不到一半表示他们的矿工准备好在 3 月执行 BIP16 规则。这 [导致](https://github.com/bitcoin/bitcoin/issues/925) 了一次“相当长的另类链分叉”（链分裂），其中仍然执行 3 月 1 日开始日期的矿工拒绝了大多数不执行这些规则的矿工的区块。第二次对最近 1000 个区块的投票发生在 3 月 15 日；这次获得了足够的支持，因此开发者在 3 月 30 日发布了[比特币 0.6.0](https://bitcoin.org/en/release/v0.6.0)，并将激活日期定为 4 月 1 日。

#### \[2012 年] 硬编码时间：BIP30 拒绝重复的 txid

在 P2SH 激活进行的同时，发现可以创建具有相同 txid 的多个交易。本身而言，这个漏洞只会破坏尝试利用它的用户的资金，但它可以与比特币的默克尔树构造中的一个怪癖结合起来，破坏节点之间的共识（参见 [CVE-2012-2459](https://bitcointalk.org/?topic=102395)）。第一个软分叉修复是[BIP30](https://github.com/bitcoin/bips/blob/master/bip-0030.mediawiki)，它简单地将具有与另一个交易相同 txid 的交易标记为无效，前提是另一个交易有未使用的输出。这个修复在开发团队中没有争议，并被[激活](https://github.com/bitcoin/bitcoin/commit/a206b0ea12eb4606b93323268fc81a4f1f952531#diff-34d21af3c614ea3cee120df276c9c4ae95053830d7f1d3deaf009a4625409ad2R1271)，通过一个简单的硬编码时间包含在同一个[比特币 0.6.0](https://bitcoin.org/en/release/v0.6.0) 版本中，该版本包含了P2SH 的激活参数。

#### \[2012 年] IsSuperMajority (ISM)：BIP34 coinbase 前缀

尽管 BIP30 解决了重复 txid 的直接问题，但比特币开发者知道他们不想每次接收新交易时都必须搜索一个包含所有之前交易的未使用输出的索引，因此开发了第二种解决方案，以消除使重复 txid 变得实际可行的弱点。这就是[BIP34](https://github.com/bitcoin/bips/blob/master/bip-0034.mediawiki)。对于这个变更，开发者使用了类似于 BIP16 P2SH 矿工信号方法的东西，但这次要求准备好 BIP34 的矿工将他们的区块 `nVersion` 值增加。更值得注意的是，开发者在比特币代码中自动化了对新规则的强制执行，这样他们就可以在等待矿工升级时发布准备好软分叉的软件。BIP34 的规则在一个名为 `IsSuperMajority()`（ISM）的函数中实现，最初包括一个[单一激活阈值](https://github.com/bitcoin/bitcoin/commit/de237cbfa4c1aa7d4f9888e650f870a50b77de73#diff-34d21af3c614ea3cee120df276c9c4ae95053830d7f1d3deaf009a4625409ad2R1829-R1841)，该阈值将开始执行 BIP34 的新共识规则：

> 75% 规则：如果最近 1000 个区块中有 750 个或更多是版本 2 或更高版本，拒绝无效的版本 2 区块。

在 PR 的开发过程中，[决定](https://github.com/bitcoin/bitcoin/pull/1526#issuecomment-6717685)增加一个[第二激活阈值](https://github.com/bitcoin/bitcoin/commit/d18f2fd9d6927b1a132c5e0094479cf44fc54aeb#diff-34d21af3c614ea3cee120df276c9c4ae95053830d7f1d3deaf009a4625409ad2R1829-R1837)，这实际上通过要求使用 BIP34 来解决根本问题：

> 95% 规则：如果最近 1000 个区块中有 950 个或更多是版本 2 或更高版本，拒绝所有版本 1 区块。

拒绝旧版本区块的已知问题是，直到所有矿工升级之前，每天会产生多达几个无效区块（假设恰好 95% 的矿工升级，则每个区块有 5% 的几率）。升级后执行 ISM 规则的节点将拒绝这些区块，但不了解这些规则的旧节点和轻量级客户端将接受这些区块。这使得网络比平时更依赖于矿工拒绝构建在无效区块上。

作为一名资深区块链架构师，我将根据您提供的英文专业技术文档内容进行专业且准确的中文翻译，并在保留原专业名词的同时，确保文档内容的通顺性和准确性。以下是翻译内容：

#### \[2015 年] ISM 和无验证挖矿：BIP66 严格 DER 激活

2014 年 9 月，Pieter Wuill [发现](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2015-July/009697.html) OpenSSL 在不同平台处理 DER 编码签名的方式存在分歧。例如，这可以被用来创建一个在 Linux 上验证成功但在 Windows 上失败的区块，从而使攻击者能够创建针对性的链分叉。Wuille 和其他几名开发者私下开发了一个软分叉的补丁，以确保所有签名使用相同的格式。为此更改创建的 BIP66 在公开宣传时被描述为朝着消除比特币对 OpenSSL 依赖的一步（这是一个真实目标，并最终在 2019 年[实现](https://bitcoinops.org/en/newsletters/2019/12/28/#openssl)）。在 BIP66 获得用户和开发者的足够支持后——包括许多不知道安全漏洞的人——它使用与 BIP34 相同的 ISM 激活机制发布，将区块版本增加到 v3，并要求在达到 95% 阈值时拒绝所有 v2 或更低版本的区块。

75% 的阈值在 359,753 区块高度达到。2015 年 7 月 4 日，在 363,725 区块达到 95% 阈值，所有运行[比特币核心版本 0.10.0](https://bitcoin.org/en/release/v0.10.0#bip-66-strict-der-encoding-for-signatures) 或更高版本（或兼容实现）的节点开始强制执行新规则。然而，在 363,731 区块高度，一个未升级的矿工生产了一个不包含正确区块版本的区块，因此不符合新的 ISM 激活规则。其他矿工在这个无效区块之上构建，最终产生了一个包含六个无效区块的链。这意味着未升级的节点和许多轻量级客户端将第一个无效区块中的 96 笔交易视为已经获得了六次确认，尽管它们在有效区块中甚至没有被确认过一次。最终，开发者们能够联系矿池运营商，让他们手动重置他们的软件回到有效链。第二天发生了第二次此类事件，给交易带来了三次虚假确认。幸运的是，两个无效链中的所有常规交易后来都在有效区块中得到了确认，这意味着没有普通用户因此损失资金。

在 363,731 高度的最初无效区块是每天预期的大约 5% 无效区块之一，这仅仅是因为使用了旧版本号。下一个区块由另一个未升级的矿工生产的概率也是 5%，或累积概率为 `5% * 5% = 0.25%`。在假设 95% 的矿工已经升级的前提下，连续六个区块都由过时的矿工生产的累积概率是 0.000002%——但在这里不是非常不幸的运气是罪魁祸首。未考虑的是矿工进行 _无验证挖矿_（validationless mining），这是一种效率优化，矿工会在完成接收和验证新区块之前就基于新区块的头部构建。虽然理论上无验证挖矿软件可以轻松处理无效的区块版本，但这个功能并没有在创造了 #363,731 之后五个区块的矿工使用的软件中实现。最终，足够多的矿工改进了他们的无验证挖矿软件或升级了他们的节点，与 BIP66 激活相关的意外链分叉停止发生。

为了应对这些 [2015 年 7 月链分叉](https://en.bitcoin.it/wiki/July\_2015\_chain\_forks)的问题，开发者加倍努力减少无验证挖矿的需求，导致了 [BIP152](https://github.com/bitcoin/bips/blob/master/bip-0152.mediawiki) 紧凑区块中继和 [FIBRE](http://bitcoinfibre.org/) 软件等改进。开发者还开始致力于改进激活机制，这最终成为了后来描述的 BIP9 协议。

#### \[2015 年] ISM 最后一次：BIP65 `OP_CHECKLOCKTIMEVERIFY` 激活

在 BIP66 严格 DER 软分叉之前提出的一个添加新的 `OP_CHECKLOCKTIMEVERIFY`（CLTV）操作码到比特币的软分叉被 OpenSSL 漏洞修复的紧迫性所推迟。这再次展示了使用递增版本号的 ISM 机制的弱点——为最新提案（版本 _n_）发出准备就绪信号的矿工也隐含地为所有先前提案（例如版本 _n-1_）发出准备就绪信号。这限制了使用 ISM 并行协调多个升级的能力。

然而，尽管 BIP66 激活末期出现了问题，ISM 再次被用来避免进一步推迟 [BIP65](https://github.com/bitcoin/bips/blob/master/bip-0065.mediawiki)。这次没有激活问题。

#### \[2016 年] BIP9 版本位：BIP68/112/113 相对锁定时间激活

为了解决 ISM 的几个问题，提出了 [BIP9](https://github.com/bitcoin/bips/blob/master/bip-0009.mediawiki) 中记录的新激活机制：

* **不必要地惩罚矿工：** 当 ISM 激活并且最小区块版本增加时，任何未增加版本的矿工都会生产无效区块，即使这些区块没有违反软分叉的其他规则。例如，在 2015 年 7 月 4 日触发链分叉的区块中，所有交易都遵循了新的软分叉规则——矿工遭受超过 50,000 美元损失的唯一原因是升级要求区块头包含一个 `3`，而未升级的矿工使用了 `2`。
* **不切实际的并行化：** 使用 ISM 时，开发者觉得他们需要等待一个分叉激活后才能开始第二个分叉。
* **无法失败：** ISM 尝试没有到期日期。一旦发布了等待激活信号的节点软件，从那时起的所有节点都需要持续监控该信号，直到激活发生。没有办法决定软分叉不再需要。
* **不可预测的激活时间：** 事先不知道确切的激活时间意味着协议开发者、商户系统管理员和矿池运营商很难在激活后的几小时内随时待命，以防出现需要快速响应的问题。

BIP9 版本位试图通过将区块头版本字段用作位字段来解决这些问题。该字段中的位仅用于信号传递——永远不会因此拒绝区块为无效——并且可以并行设置。测量只在每 2,016 个区块进行一次，最小化了一小部分算力需要运气好到虚假地呈现 95% 信号的时间窗口。最终，当达到 95% 信号阈值时，会有一个 2,016 个区块（大约两周）的“锁定”期，直到激活发生，以便人们做好准备。如果在截止日期之前没有达到信号阈值，尝试就会结束，允许将未使用的代码从后续节点软件版本中移除。

这种激活方法首次用于增加 [BIP68](https://github.com/bitcoin/bips/blob/master/bip-0068.mediawiki) 共识强制序列号、[BIP112](https://github.com/bitcoin/bips/blob/master/bip-0112.mediawiki) `OP_CHECKSEQUENCEVERIFY`，以及 [BIP113](https://github.com/bitcoin/bips/blob/master/bip-0113.mediawiki) 基于过去中位时间的 nLockTime 强制执行的软分叉。该分叉迅速进入了锁定阶段，然后自动进行了激活。

#### \[2016-7 年] BIP9、BIP148 和 BIP91：BIP141/143 隔离见证激活

隔离见证（segwit）软分叉采用了 [BIP9](https://github.com/bitcoin/bips/blob/master/bip-0009.mediawiki) 激活参数发布。一些矿工很快开始表明准备就绪，但支持率远未达到 95% 的阈值。一些比特币用户感到矿工不合理地延迟了一个有用的新功能，于是开发了成为 [BIP148](https://github.com/bitcoin/bips/blob/master/bip-0148.mediawiki) 的强制性激活。BIP148 的最终形式规定，从某个特定日期开始拒绝任何不表示支持隔离见证的区块。

随着实现 BIP148 的软件的引入，网络上出现了三组节点——未升级的节点、BIP9/141 节点和 BIP148/141 节点——增加了可能导致共识失败的情况数量。如果矿工未表示支持隔离见证，且大多数用户继续认为这些矿工的区块有效，BIP148 的用户可能接受大多数其他比特币用户认为无效的比特币。另一方面，如果大多数比特币用户遵循 BIP148 规则——但矿工仍然产生许多 BIP148 无效的区块——那些不强制执行 BIP148 的用户可能接受 BIP148 用户认为无效的比特币。只有当所有用户遵循相同的规则，或者大多数挖矿算力遵循 BIP148 规则时，安全性才能得到保证。

减少这种风险的一种方法是给用户更多时间升级到强制激活隔离见证的节点。BIP148 无法做到这一点，因为其触发现有 BIP9 隔离见证部署的目标意味着它必须强制矿工长时间在隔离见证的 BIP9 截止日期之前开始标记。作为替代方案，以防 BIP148 未能获得足够支持，提出了 [BIP149](https://github.com/bitcoin/bips/blob/master/bip-0149.mediawiki)，给用户另外一年时间升级。BIP149 没有获得太多公众支持，但它是第一个使用 [BIP8](https://github.com/bitcoin/bips/blob/master/bip-0008.mediawiki) 的提案，在随后的几年中还会有更多讨论。

在 BIP148 开始获得显著公众支持后，一些矿工、交易所和其他商家签署了他们对两步提案的支持，该提案从以一种与支持 BIP148 的节点保持共识的方式激活隔离见证开始。这第一阶段在 [BIP91](https://github.com/bitcoin/bips/blob/master/bip-0091.mediawiki) 中提出，它是对 BIP9 规则的修改。矿工使用了 BIP9 版本位来标记他们是否会执行一个临时规则，拒绝任何不标记 BIP141/143 隔离见证版本位的区块。与 BIP9 相比，BIP91 的阈值从 95% 降低到了 80%，其监测和锁定期长度从 2,016 个区块减少到了 336 个区块。

BIP91 已锁定并激活。随后，BIP141/143 已锁定并激活。当 BIP141/143 锁定时，BIP148 强制标记到期。矿工、交易所和其他商家提案的第二阶段需要硬分叉；在大量个人用户和几家企业的强烈反对声中，代言人最终撤回了他们的提案。

关于上述各项事件及同时发生的其他事件究竟对隔离见证激活产生了多少影响，仍然是一个有争议的话题。

## 紧急激活

在发现共识代码中存在严重漏洞的几种情况下，开发者发布了没有任何激活条件的修复。这冒着共识失败的风险，但也为每个升级节点立即消除了紧迫的漏洞。值得注意的情况包括：

* **用链工作量（Chainwork）替换高度（2010 年 7 月）：** 比特币最初实现为遵循具有最多区块的有效链（“最长链”）。如果每个区块的难度都相同，那么这将是具有最多工作量证明（PoW）的链。但不同的区块可以有不同的难度，因此在 [Bitcoin 0.3.3](https://bitcointalk.org/index.php?topic=570.0) 中发布的[链工作量](https://github.com/bitcoin/bitcoin/commit/3b7cd5d89a226426df9c723d1f9ddfe08b7d1def#diff-608d8de3fba954c50110b6d7386988f27295de845e9d7174e40095ba5efcf1bbR1229)软分叉用于遵循具有最大累积工作量证明的有效链。
* **消除脚本绕过漏洞（2010 年 7 月）：** 比特币最初将花费 UTXO 的脚本（scriptSig）与保护该 UTXO 的脚本（scriptPubKey）结合在一起，并同时对其进行评估。这可能允许某人在锁定机制被评估之前（例如，在运行 `OP_CHECKSIG` 验证签名有效之前）使脚本成功终止。这个漏洞最初被[报告](https://bitcoin.stackexchange.com/questions/38037/what-is-the-1-return-bug)为 `OP_TRUE OP_RETURN` 的 scriptSig 可以用来花费任何人的比特币。最初这是在 [Bitcoin 0.3.6](https://bitcointalk.org/index.php?topic=626.msg6490) 中通过使 `OP_RETURN` 操作码总是导致失败以及对脚本施加许多其他限制来[修复](https://github.com/bitcoin/bitcoin/commit/a75560d828464c3f1138f52cf247e956fc8f937d#diff-27496895958ca30c47bbb873299a2ad7a7ea1003a9faa96b317250e3b7aa1fefR175)的。尽管所有这些更改都是软分叉更改，但同一代码修订也进行了一个硬分叉[更改](https://github.com/bitcoin/bitcoin/commit/a75560d828464c3f1138f52cf247e956fc8f937d#diff-27496895958ca30c47bbb873299a2ad7a7ea1003a9faa96b317250e3b7aa1fefR113-R116)，以后可以移除一些限制。尽管这些重大变化，scriptSigs 能够干扰 scriptPubKeys 执行的根本问题仍然存在，因此在 [Bitcoin 0.3.8](https://bitcointalk.org/index.php?topic=696.msg7364#msg7364) 中实现的[第二次软分叉](https://github.com/bitcoin/bitcoin/commit/6ff5f718b6a67797b2b3bab8905d607ad216ee21#diff-27496895958ca30c47bbb873299a2ad7a7ea1003a9faa96b317250e3b7aa1fefL1135)开始独立评估 scriptSigs 和 scriptPubKeys。
* **修复价值溢出漏洞（2010 年 8 月）：** 有人创建了一个交易，花费了 0.5 BTC 到两个总值为 92,233,720,368.54277039 BTC 的输出。比特币要求输出金额必须小于或等于输入金额，但这是通过将输出值加到一个单个的 64 位整数中来检查的，这个整数最多只能容纳 9,223,372,036,854,776 sats（约 920 亿 BTC）在翻转到负数之前，以 -9,223,372,036,854,776 sats 开始。这意味着交易看起来总共花费了 -0.1 BTC（负 0.1 BTC）。这绕过了另一个禁止单个负输出的规则——但不禁止负总额——因为它假设任何一组正值的总和也将是正的。这让创建该交易的人获得了 1840 亿 BTC。这个技巧可以无限制地重复，允许生产无限数量的比特币。在几小时内，发布了一个软分叉[修复](https://github.com/bitcoin/bitcoin/commit/2d12315c94f12d62b2f2aa39e63511a2042fe55d#diff-506a3b93711ef8e9623d329cf0a81447492e05867d2f923c6fa9fcffeca94f35R479)，将输出限制为 2100 万比特币，发布在 [Bitcoin 0.3.10](https://bitcointalk.org/index.php?topic=827.0) 中。这确实需要放弃包含溢出交易的链——一次故意的共识失败，但这是为了确保比特币保持有用性所必需的。
* **暂时修复 BDB 锁问题（2013 年 3 月）：** 2012 年初，比特币开发者[意识到](https://github.com/bitcoin/bitcoin/issues/925)同时对 UTXO 数据库（chainstate）进行太多更改可能会导致超出 chainstate 数据库的默认容量限制。由于当时比特币区块的小尺寸，这只在区块链重组期间发现，当时来自多个区块的交易都在同一时间被处理。一个简单的 [解决方案](https://github.com/bitcoin/bitcoin/pull/930) 被实施：在重组期间，一次只处理来自单个区块的交易。后来，一些人开始[要求矿工](https://bitcointalk.org/index.php?topic=149668.0)将可选的默认区块大小从 250 千字节提高到更大的尺寸。2013 年 3 月 12 日，其中一位矿工生产了一个[近 1 兆字节的区块](https://buildingbitcoin.org/bitcoin-dev/log-2013-03-12.html#l-229)，包含超过 1,700 笔交易——迄今为止比特币上最大的区块——这足以超过许多节点的数据库容量，导致它们认为该区块无效，尽管它遵循了所有比特币的明确共识规则。更复杂的是，一种使用不同数据库引擎的新版比特币核心已经发布，该数据库引擎没有这个限制，并且无问题地接受了这个大区块——在两种不同节点版本之间产生共识失败。在快速分析情况后，开发者鼓励用户暂时降级到旧版比特币（拒绝大区块的版本），然后升级到一个[紧急发布](https://bitcoin.org/en/release/v0.8.1)的版本，该版本实施了一个临时区块大小限制为 500,000 字节的软分叉，预先编程为几个月后到期，届时每个人都有机会升级到新的数据库引擎。

作为一名资深区块链架构师，我将根据您提供的英文专业技术文档内容进行专业且准确的中文翻译，并在保留原专业名词的同时，确保文档内容的通顺性和准确性。以下是翻译内容：

## 未来的激活

在隔离见证激活的问题之后，一些人开始致力于 [BIP8](https://github.com/bitcoin/bips/blob/master/bip-0008.mediawiki) 提案，该提案据称解决了 BIP9 的几个问题：

* **允许强制性激活：** BIP8 最初是 BIP148 的泛化，允许矿工在激活部署的大多数时间段内自愿发出激活信号，但要求他们在最后一个时期发出信号，否则有可能创建无效区块。后来，创建了一个参数 `LockinOnTimeout`（LOT），用于切换这种行为；使用 LOT=true 的节点将要求在超时前的最后一段时间内进行标记；使用 LOT=false 的节点不会要求进行标记，但如果有足够的区块进行标记，仍会强制执行新规则。
* **使用区块高度而不是时间：** BIP9 根据矿工在最近区块中编码的时间平均值开始和停止监控激活信号。矿工可以操纵这些时间，这可能会阻碍 LOT=true 的激活，因此 BIP8 提案改为使用区块高度。

BIP8 的灵活性使其能够用于比较针对拟议的 [taproot](https://bitcoinops.org/en/topics/taproot/) 软分叉的[多种激活提案](https://en.bitcoin.it/wiki/Taproot\_activation\_proposals)，尽管反对者对它的某些方面提出了几项批评，例如允许矿工拒绝激活具有广泛社区支持的提案的配置，鼓励一个群体[利用另一个群体使用的信号机制](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2021-March/018595.html)，要求矿工对他们生产的区块进行[无效的改变](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2020-January/017582.html)，似乎[赋予开发者对共识规则的控制权](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2021-February/018380.html)，以及[增加共识失败的风险](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2021-March/018723.html)。截至目前，关于 taproot 激活的讨论仍在进行中。

还讨论了其他激活想法，包括概率性软分叉激活（[sporks](https://bitcoinops.org/en/newsletters/2019/02/05/#probabilistic-bitcoin-soft-forks-sporks)），多阶段（“现代”）软分叉激活（[MSFA](https://bitcoinops.org/en/newsletters/2020/01/15/#discussion-of-soft-fork-activation-mechanisms)），降低阈值激活（[decthresh](https://bitcoinops.org/en/newsletters/2020/07/22/#mailing-list-thread)），回归到硬编码高度或时间激活（[flag days](https://bitcoinops.org/en/newsletters/2021/03/10/#flag-day)），

以及短暂的信号周期后跟随激活延迟（[speedy trial](https://bitcoinops.org/en/newsletters/2021/03/10/#a-short-duration-attempt-at-miner-activation)）。

## 主要代码和文档

* [BIP9](https://github.com/bitcoin/bips/blob/master/bip-0009.mediawiki)
* [BIP8](https://github.com/bitcoin/bips/blob/master/bip-0008.mediawiki)

## Optech 新闻简报及网站提及

**2023**

* [关于为什么比特币核心尚未埋藏 Taproot 部署的问题](https://bitcoinops.org/en/newsletters/2023/03/29/#why-isn-t-the-taproot-deployment-buried-in-bitcoin-core)
* [关于在比特币审判中使用异端部署的 PR 审查俱乐部会议](https://bitcoinops.org/en/newsletters/2023/03/08/#bitcoin-core-pr-review-club)

**2022**

* [关于各种软分叉提案在激活之前如何被测试的历史](https://bitcoinops.org/en/newsletters/2022/10/26/#what-is-the-history-on-how-previous-soft-forks-were-tested-prior-to-being-considered-for-activation)
* [使用交易信号来衡量对共识变更的支持的提案](https://bitcoinops.org/en/newsletters/2022/05/04/#measuring-user-support-for-consensus-changes)
* [关于自动撤销软分叉的提案](https://bitcoinops.org/en/newsletters/2022/04/27/#relayed)
* [关于何时激活软分叉是合理的讨论](https://bitcoinops.org/en/newsletters/2022/04/27/#argued)
* [关于对有争议的软分叉使用快速审判激活的担忧](https://bitcoinops.org/en/newsletters/2022/03/23/#speedy-trial-discussion)

**2021**

* [关于在激活后将 Taproot 输出视为始终可用的分析](https://bitcoinops.org/en/newsletters/2021/12/08/#bitcoin-core-pr-review-club)
* [鼓励矿工开始为 Taproot 标记准备就绪](https://bitcoinops.org/en/newsletters/2021/05/05/#miners-encouraged-to-start-signaling-for-taproot)
* [发布准备激活 Taproot 的比特币核心 0.21.1 版本](https://bitcoinops.org/en/newsletters/2021/05/05/#bitcoin-core-0-21-1)
* [BIPs #1104 向 BIP341 Taproot 规范中添加了激活参数](https://bitcoinops.org/en/newsletters/2021/05/05/#bips-1104)
* [比特币核心 #21377 和#21686 添加了 Taproot 激活机制和参数](https://bitcoinops.org/en/newsletters/2021/04/21/#bitcoin-core-21377)
* [关于埋藏过去软分叉部署的 PR 审查俱乐部讨论](https://bitcoinops.org/en/newsletters/2021/04/14/#bitcoin-core-pr-review-club)
* [提议使用 MTP 与快速审判激活 Taproot 的妥协方案](https://bitcoinops.org/en/newsletters/2021/04/14/#taproot-activation-discussion)
* [Taproot 激活邮件列表讨论；提议进行快速审判尝试](https://bitcoinops.org/en/newsletters/2021/03/10/#taproot-activation-discussion)
* [BIPs #1069 使 BIP8 信号阈值可配置并降低默认值](https://bitcoinops.org/en/newsletters/2021/03/03/#bips-1069)
* [关于第二次 Taproot 激活会议和邮件列表讨论的总结](https://bitcoinops.org/en/newsletters/2021/02/24/#taproot-activation-discussion)
* [Taproot 激活会议总结和后续会议安排](https://bitcoinops.org/en/newsletters/2021/02/10/#taproot-activation-meeting-summary-and-follow-up)
* [BIPs #1021 降低了 BIP8 LockinOnTimeout=True 的标记要求](https://bitcoinops.org/en/newsletters/2021/02/10/#bips-1021)
* [BIPs #1020 更新了 BIP8，不再在锁定期间要求标记](https://bitcoinops.org/en/newsletters/2021/02/10/#bips-1020)
* [安排了讨论 Taproot 激活的会议](https://bitcoinops.org/en/newsletters/2021/01/27/#scheduled-meeting-to-discuss-taproot-activation)

**2020**

* [2020 年综述：软分叉激活机制](https://bitcoinops.org/en/newsletters/2020/12/23/#activation-mechanisms)
* [不同软分叉激活机制的比较问答](https://bitcoinops.org/en/newsletters/2020/12/16/#how-do-bip8-and-bip9-differ-how-are-they-alike)
* [列出矿工支持 Taproot 激活的网站](https://bitcoinops.org/en/newsletters/2020/11/25/#website-listing-miner-support-for-taproot-activation)
* [发布了开发者对软分叉激活的偏好调查](https://bitcoinops.org/en/newsletters/2020/11/04/#taproot-activation-survey-results)
* [比特币核心 #19953 添加了 Taproot 代码；激活仍在讨论中](https://bitcoinops.org/en/newsletters/2020/10/21/#bitcoin-core-19953)
* [作为 BIP8 一部分实施的“意外版本”警告变更](https://bitcoinops.org/en/newsletters/2020/10/07/#bitcoin-core-19898)
* [关于隔离见证激活历史和 Taproot 想法的对话](https://bitcoinops.org/en/newsletters/2020/09/02/#taproot-activation)
* [在新的 IRC 聊天室和邮件列表上进行的 Taproot 激活讨论](https://bitcoinops.org/en/newsletters/2020/07/22/#taproot-activation-discussions)
* [BIPs #550 修订了 BIP8，允许在没有初始强制锁定的情况下使用](https://bitcoinops.org/en/newsletters/2020/07/01/#bips-550)
* [包括潜在软分叉激活机制的聚会讨论](https://bitcoinops.org/en/newsletters/2020/06/03/#sydney-meetup-discussion)
* [OP\_CHECKTEMPLATEVERIFY 研讨会关于激活机制的讨论](https://bitcoinops.org/en/newsletters/2020/02/12/#op-checktemplateverify-ctv-workshop)
* [邮件列表上关于软分叉激活方法的讨论](https://bitcoinops.org/en/newsletters/2020/01/15/#discussion-of-soft-fork-activation-mechanisms)

**2019**

* [比特币核心中硬编码的之前软分叉的激活高度](https://bitcoinops.org/en/newsletters/2019/08/21/#hardcoded-previous-soft-fork-activation-blocks)
* [草案 Taproot 提案故意省略激活机制](https://bitcoinops.org/en/newsletters/2019/05/14/#no-activation-mechanism-specified)
* [共识清理软分叉提案（计划采用 BIP9 激活）](https://bitcoinops.org/en/newsletters/2019/03/05/#cleanup-soft-fork-proposal)
* [关于概率性软分叉激活（“sporks”）的演讲](https://bitcoinops.org/en/newsletters/2019/02/05/#probabilistic-bitcoin-soft-forks-sporks)

## 参见

* [BIP 激活高度、时间和阈值](https://gist.github.com/ajtowns/1c5e3b8bdead01124c04c45f01c817bc)
* [Taproot](https://bitcoinops.org/en/topics/taproot/)
