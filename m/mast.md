# MAST

**MAST（Merkleized Alternative Script Trees）** 是一种使用默克尔树（merkle tree）来存储各种用户选择的条件的方法，这些条件必须得到满足才能花费被约束的比特币。使用默克尔树允许花费者选择他们将满足的条件之一，而无需向区块链透露其他条件的细节。

能够将未使用的条件保持在区块链之外的 MAST 用户将享受更低的费用，能够创建目前可能的更大的合约，将拥有更好的隐私，并将提高他们比特币的可替代性。

自 2013 年以来，MAST 在比特币中一直被泛泛讨论，提出了几个具体的提案以将其加入比特币：

* [BIP114](https://github.com/bitcoin/bips/blob/master/bip-0114.mediawiki) `OP_MAST`
* [BIP116](https://github.com/bitcoin/bips/blob/master/bip-0116.mediawiki) `OP_MERKLEBRANCHVERIFY` 和 [BIP117](https://github.com/bitcoin/bips/blob/master/bip-0117.mediawiki) 尾部调用执行语义
* [bip-taproot](https://github.com/bitcoin/bips/blob/master/bip-0341.mediawiki) 的默克尔树

注意：MAST 最初的缩写代表 _Merkleized Abstract Syntax Trees_，由 Russell O’Connor 基于 [默克尔树](https://en.wikipedia.org/wiki/Merkle\_tree) 和 [抽象语法树](https://en.wikipedia.org/wiki/Abstract\_syntax\_tree) [提出](https://bitcointalk.org/index.php?topic=255145.msg2757327#msg2757327)。后续的提案不再使用类似抽象语法树的东西，但人们继续使用“MAST”这个名字，导致 Anthony Towns [提出](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2018-November/016500.html) 后缀式缩写 _Merkleized Alternative Script Trees_。

## 主要代码和文档

* [BIP114](https://github.com/bitcoin/bips/blob/master/bip-0114.mediawiki)
* [BIP116](https://github.com/bitcoin/bips/blob/master/bip-0116.mediawiki)
* [BIP117](https://github.com/bitcoin/bips/blob/master/bip-0117.mediawiki)
* [bip-taproot](https://github.com/bitcoin/bips/blob/master/bip-0341.mediawiki)

## Optech 新闻简报和网站提及

**2020**

* [什么是 Merkleized Alternative Script Trees？](https://bitcoinops.org/en/newsletters/2020/10/28/#what-are-merklized-alternative-script-trees)
* [关于 MAST（和其他事项）如何演变成 taproot 的讨论](https://bitcoinops.org/en/newsletters/2020/08/05/#bip-taproot)
* [关于 taproot 与其他启用 MAST 的替代提案的讨论](https://bitcoinops.org/en/newsletters/2020/02/19/#discussion-about-taproot-versus-alternatives)

**2019**

* [Taproot 及其基于 MAST 的约束概述](https://bitcoinops.org/en/newsletters/2019/05/14/#overview-of-the-taproot--tapscript-proposed-bips)
* [应该能够升级 miniscript 以支持像 MAST 这样的功能](https://bitcoinops.org/en/newsletters/2019/02/05/#miniscript)
* [MAST 脚本中应该禁用 `OP_CODESEPARATOR` 吗？](https://bitcoinops.org/en/newsletters/2019/01/08/#continued-sighash-discussion)

**2018**

* [Taproot：对 MAST 的优化](https://bitcoinops.org/en/newsletters/2018/12/28/#taproot)

## 参见

* [Taproot](https://bitcoinops.org/en/topics/taproot/)
