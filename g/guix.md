---
description: 同时涵盖可重现构建（Reproducible builds） 和 Guix
---

# Guix

**可重现构建**是指以确定性的方式编译的软件，使得多人能够从相同的源代码编译出完全相同的二进制文件。

这意味着无需信任任何一个人或计算机来生产大多数人使用的可执行二进制文件。此外，自行编译软件的人可以确保他们得到的可执行文件与其他人接收到的相同，有助于确保他们的软件将与其他软件保持兼容，例如，一个全节点与网络中的其他节点保持共识。

## 主要代码和文档

* [比特币核心 PR #15277：启用在 Guix 容器中构建](https://github.com/bitcoin/bitcoin/pull/15277)

## Optech 新闻简报和网站提及

**2022**

* [监控各种比特币项目可重现构建当前状态的新网站](https://bitcoinops.org/en/newsletters/2022/12/14/#coinkite-launches-binarywatch-org)

**2021**

* [比特币核心 #22642 允许连接基于 Guix 的证明，以进行批量验证](https://bitcoinops.org/en/newsletters/2021/08/18/#bitcoin-core-22642)
* [问题：Guix 在 Gitian 中的作用是什么？](https://bitcoinops.org/en/newsletters/2021/07/28/#what-s-the-purpose-of-using-guix-within-gitian-doesn-t-that-reintroduce-dependencies-and-security-concerns)
* [比特币核心 #21462 添加用于证明基于 Guix 构建的工具](https://bitcoinops.org/en/newsletters/2021/05/19/#bitcoin-core-21462)
* [比特币核心 #17920 为 macOS 构建添加 Guix 支持](https://bitcoinops.org/en/newsletters/2021/01/27/#bitcoin-core-17920)

**2020**

* [比特币核心 #17595 为 Windows 构建添加 Guix 支持](https://bitcoinops.org/en/newsletters/2020/04/22/#bitcoin-core-17595)
* [Eclair #1307 更新打包以可重现构建 Eclair GUI](https://bitcoinops.org/en/newsletters/2020/03/04/#eclair-1307)
* [Eclair #1295 允许 eclair-core 模块可重现构建](https://bitcoinops.org/en/newsletters/2020/02/05/#eclair-1295)

**2019**

* [2019 年回顾：可重现构建](https://bitcoinops.org/en/newsletters/2019/12/28/#reproducibility)
* [合并 PR，使用 GNU Guix 可重现构建比特币核心](https://bitcoinops.org/en/newsletters/2019/07/17/#bitcoin-core-15277)
* [Breaking Bitcoin 总结：比特币构建系统安全性](https://bitcoinops.org/en/newsletters/2019/06/19/#bitcoin-build-system-security)
* [比特币核心新的可重现构建架构和 Snap 包](https://bitcoinops.org/en/newsletters/2019/05/07/#new-architecture-and-new-ubuntu-snap-package)
* [值得注意的比特币核心 PR：使用 GNU Guix 实现可重现构建](https://bitcoinops.org/en/newsletters/2019/02/19/#bitcoin-core-freeze-week)

## 参见

* [演讲：比特币构建系统安全](https://youtu.be/I2iShmUTEl8)
