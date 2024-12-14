---
timezone: Asia/Shanghai
---

> 请在上边的 timezone 添加你的当地时区，这会有助于你的打卡状态的自动化更新，如果没有添加，默认为北京时间 UTC+8 时区
> 时区请参考以下列表，请移除 # 以后的内容

timezone: Pacific/Honolulu # 夏威夷-阿留申标准时间 (UTC-10)

timezone: America/Anchorage # 阿拉斯加标准时间 (UTC-9)

timezone: America/Los_Angeles # 太平洋标准时间 (UTC-8)

timezone: America/Denver # 山地标准时间 (UTC-7)

timezone: America/Chicago # 中部标准时间 (UTC-6)

timezone: America/New_York # 东部标准时间 (UTC-5)

timezone: America/Halifax # 大西洋标准时间 (UTC-4)

timezone: America/St_Johns # 纽芬兰标准时间 (UTC-3:30)

timezone: America/Sao_Paulo # 巴西利亚时间 (UTC-3)

timezone: Atlantic/Azores # 亚速尔群岛时间 (UTC-1)

timezone: Europe/London # 格林威治标准时间 (UTC+0)

timezone: Europe/Berlin # 中欧标准时间 (UTC+1)

timezone: Europe/Helsinki # 东欧标准时间 (UTC+2)

timezone: Europe/Moscow # 莫斯科标准时间 (UTC+3)

timezone: Asia/Dubai # 海湾标准时间 (UTC+4)

timezone: Asia/Kolkata # 印度标准时间 (UTC+5:30)

timezone: Asia/Dhaka # 孟加拉国标准时间 (UTC+6)

timezone: Asia/Bangkok # 中南半岛时间 (UTC+7)

timezone: Asia/Shanghai # 中国标准时间 (UTC+8)

timezone: Asia/Tokyo # 日本标准时间 (UTC+9)

timezone: Australia/Sydney # 澳大利亚东部标准时间 (UTC+10)

timezone: Pacific/Auckland # 新西兰标准时间 (UTC+12)

---


# {猪大虫}

1. 自我介绍
  第一次参加共学活动

2. 你认为你会完成本次残酷学习吗？
  可以的

## Notes

<!-- Content_START -->

### 2024.12.10

笔记内容
什么是 Arbitrum？

Arbitrum是一个生态系统，涵盖了多个基于以太坊的 Layer 2 解决方案，Arbitrum Rollup是Arbitrum的核心产品，是Optimistic Rollup 技术的一种具体实现。

什么是Optimistic Rollup？

Optimistic Rollup 是一种 Layer 2 扩展技术的协议和机制，主要特点是：
假设机制：默认认为提交的交易和状态是正确的（Optimistic）。
欺诈证明：允许用户通过欺诈证明（Fraud Proof）挑战提交的错误交易或状态。
设计目标：减少主链上的计算和存储负担，同时保持高性能和低成本。
所以Optimistic Rollup 是一个技术框架。

Arbitrum Rollup相比于原生的Optimistic Rollup做出了什么优化？

更短的挑战期：Arbitrum Rollup使用了增强的挑战期，允许挑战者使用简化的证据提交，从而加快挑战的响应速度，并且只针对有争议部分进行挑战，不需要完全重新计算整个交易。
更低的复杂度与更高的效率：Arbitrum Rollup只对争议部分进行验证，使用n/2的方式缩小每一步的范围，直到欺诈证明的某一具体步骤，降低了挑战成本与时间。
回滚与确认速度：更快，快速回滚错误状态
经济激励：更明确和灵活的经济激励与惩罚机制

### 2024.12.11

什么是Rollup？

Rollup 是一种区块链扩展技术，旨在提升以太坊等区块链的交易吞吐量和性能，同时保留去中心化和安全性。它是一种 二层（Layer 2）解决方案，将交易从主链（例如以太坊主链）“滚动”到更高效的链外环境处理，然后将结果提交回主链。

Arbitrum Rollup的概念？

Rollup 通过批量处理大量交易，减少每笔交易在主链上的计算和存储负担。其核心思想是将交易数据和状态变化从主链移到二层，而主链只需要验证结果。
Arbitrum Rollup是使用乐观 Rollup（Optimistic Rollup）方案
工作原理：假定提交的交易都是有效的（“乐观假设”），不需要逐笔验证。只有在怀疑交易无效时，才会触发争议和验证机制。
争议解决机制：如果有人怀疑 Rollup 中的某笔交易无效，可以发起挑战（challenge），并通过验证智能合约重新计算，裁定交易是否有效。
优点：支持复杂的智能合约和更通用的应用场景。
缺点：争议解决可能耗时，通常需要等待几天的“挑战期”。

Rollup 的运行过程及细节？

交易处理：用户将交易发送到 Rollup 二层网络。
批量打包：Rollup 将多笔交易打包成批，并生成一个状态更新。
结果提交：Rollup 将状态根及证明提交到主链，主链验证这些结果。
状态同步：主链上的验证合约更新全局状态。

什么是状态根？

状态根是区块链当前状态（即账户余额、存储数据等）的加密摘要，通常存储在区块的头部。它使用 Merkle Trie（默克尔树的变体）来表示整个区块链系统的状态，并生成一个唯一的哈希值作为状态的标识。
每当区块链发生交易，改变了账户或智能合约的状态（例如转账、调用合约函数），状态 Trie 中的节点会被更新，新的状态根将被计算并存储在下一个区块中。

状态根在 Rollup 中的作用？

状态根用作主链追踪的标识。
在争议解决期间，状态根和交易数据被用于验证。
比如在 Arbitrum 和 Optimism 中，状态根是争议期间重要的依据。

状态根在挑战机制中的作用？

挑战的本质：挑战机制用于验证某个提交的状态根是否是由合法交易计算而得。
在乐观 Rollup 中，假设交易和状态更新默认是正确的，只有当有人怀疑提交的状态有误时，才会触发挑战。
挑战的核心：证明当前提交的状态根是否与执行这些交易的实际结果一致。

挑战者需提供：有疑问的交易数据，交易的中间状态或最终状态
被挑战者需提供：交易的最初状态，交易逻辑的某一步具体证明

状态根在挑战中的优点
高效性：
状态根的 Merkle Trie 结构允许分层验证，仅需验证相关数据，而不需要加载整个状态。
数据完整性：
状态根确保提交的状态与交易结果匹配，任何不一致都会导致挑战失败。
安全性：
即使没有所有状态数据，通过状态根和 Merkle 证明，仍然可以验证某一部分状态是否正确。

### 2024.12.12

对挑战机制了解不够深，再补充一下

交互式欺诈证明是挑战机制的一种，是Arbitrum rollup的证明方法，使用二分法的方式缩小每一步，这样每此都可以缩小一半的争议范围，直到最终步骤，并确认谁才是真正的诚实者。

交互式欺诈证明的漏洞？

挑战期时的网络拥堵，导致挑战者不能在规定时间内完成交互，将会导致挑战失败。

过了挑战期后发现漏洞，但因为区块的不可篡改机制，系统默认状态根合法，如果设置抵押金，会让骗子的获利程度缩小，或者使用激励机制，让更多的人审查代码，确保交易合法，如果有漏洞也可以在挑战期内发现。

### 2024.12.11

Arbitrum One

Arbitrum One 是目前最广泛使用的 Arbitrum Rollup，前几天的知识点都是基于Arbitrum One的技术。

Arbitrum Nitro

### 2024.12.14

路线图
当我们在 2021 年 8 月 31 日（Arbitrum 日）推出 Arbitrum 时，我们解决了区块链采用的第一个主要障碍：可扩展性。在过去的三年里，我们不断扩大规模，引入了全新的功能，并创建了技术上最可靠、最开放的区块链平台

分散
区块链技术的核心理念是重视去中心化和去信任化，这是我们在 Offchain Labs 构建的一切以及我们对 Arbitrum 技术栈的未来发展计划的核心。我们正在研究一些近期和未来的发展，以加强基础设施，确保去中心化不仅仅是一个理论概念，而是生态系统中的实际现实

我们已经开始为多个客户端测试和评估性能和基准，包括 Paradigm 新发布的 Reth 1.0、Erigon 3.0 和 Nethermind，目标是在 2025 年提供生产就绪的多客户端实现，并简化未来添加其他客户端的流程。尽管我们目前的分析表明，一些替代客户端在一些性能基准上仍然落后于 Geth，但我们认为，随着这些客户端的进一步优化，为 Arbitrum 的采用做好准备是谨慎的。

<!-- Content_END -->
