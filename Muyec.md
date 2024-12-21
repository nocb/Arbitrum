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

# Muyec

1. 自我介绍

   web3新新人。

2. 你认为你会完成本次残酷学习吗？

   能

## Notes

<!-- Content_START -->

### 2024.12.10

1.Arbitrum是什么：Arbitrum 是一个旨在扩展以太坊的技术套件，其核心产品 Arbitrum Rollup 是一种继承以太坊安全性的 Optimistic Rollup 协议，通过降低交易费用和提高交易速度解决了以太坊每秒交易量有限的问题。

2.Arbitrum的技术特点：Arbitrum Rollup 通过将用户交易数据压缩后批量提交至以太坊，并采用“乐观假设”机制，仅在争议情况下触发 L1 验证，从而显著减轻以太坊主网的负担，同时继承以太坊的安全性。

3.多链支持与灵活选择：Arbitrum 支持多条链并行运行，在以太坊主网上，有 2 条 Arbitrum 链：一条 Arbitrum Rollup 链，称为[“Arbitrum One”，](https://portal.arbitrum.one/)一条 AnyTrust 链[，称为“Nova](https://nova.arbitrum.io/)”;用户和开发人员可以选择适合他们的安全/交易成本需求的任何选项。


### 2024.12.11

欺诈证明:欺诈证明是一种逐步细分争议的机制，旨在通过不断缩小争议范围来验证区块和机器状态的正确性。在质询过程中，首先会将全局状态和区块哈希分为两部分，然后逐渐集中到单个区块。在执行阶段，质询被分解为更小的步骤，响应方需要提供数据证明每个步骤的执行状态与预期一致。每一轮质询中，响应方选择相邻的段进行挑战，逐步反驳对方的断言，并细分争议范围。质询的“度数”决定了每次分段的数量，确保挑战不断向前推进。与传统的等分协议不同，本协议采用非对称方式，由挑战者选择要质询的段，响应方提供校样数据。当质询无法得到有效解决时，响应方的状态哈希会被置为 0，从而导致超时失败，最终通过合同升级诊断和修复错误。这种机制不仅确保了挑战过程的透明性，也为错误修复提供了时间窗口。


### 2024.12.12

Nitro 与 Classic:Arbitrum Nitro 是对 Arbitrum Classic 技术栈的升级，代表了 Arbitrum 技术发展的最新一步。两者的目标相似，都是创建一个接近以太坊的执行环境，用以太坊的欺诈证明保证 L2 状态的安全性。但 Nitro 相比 Classic 有显著的改进。在 Classic 中，Arbitrum 使用定制的虚拟机（AVM）执行代码，而在 Nitro 中，采用了 WebAssembly（Wasm），并将 Go 代码编译为 Wasm，这使得 Arbitrum 的 L2 状态机（ArbOS）能够直接包含以太坊的 Geth 实现，从而提高了兼容性。Nitro 的架构选择带来了多方面的优势：更低的费用、更好的以太坊兼容性和系统简化。


### 2024.12.13

Arbitrum Orbit 是一个开发框架，允许用户基于 Arbitrum Rollup 的 L2 创建和启动 L3 网络。Orbit 支持用户定制链功能，包括隐私、权限、费用代币和治理等，同时提供专用吞吐量、流量隔离以及可靠的 Gas 价格，适合特定领域的快速机制设计与迭代，帮助实现更多的价值捕获。
XAI 是基于 Arbitrum Orbit 的首个 L3，定位为专注游戏场景的链，相较于 Nova 通用链，XAI 能够提供更高的性能。它具备专属的计算和存储资源，适合计算密集型场景（如 AI 模型）。同时，XAI 原生集成了 Arbitrum 技术栈，包括 Nitro、BOLD 和 Stylus。
Nitro 是 Arbitrum 的核心技术栈之一，通过直接编译 Geth 核心，显著提升了以太坊的兼容性和性能。这一升级使得 Orbit 链能够以更高效的方式运行，进一步优化用户体验。


### 2024.12.14

交互型 Rollup 确保断言（assertion）正确性的方式分为单轮和多轮交互两种。单轮交互型 Rollup（如 Optimism）中，断言包含调用结果，挑战者可在挑战窗口期内指出具体错误，链上合约模拟执行验证后，如果确有错误，则取消断言并罚没断言者保证金；若无挑战，断言最终确定。多轮交互型 Rollup（如 Arbitrum）通过挑战者与断言者的多轮交互缩小争议范围，最终由链上仲裁合约判定结果并惩罚错误方，设计目的是将链上仲裁的计算量降至最低。


### 2024.12.15

交互式证明:Arbitrum 通过交互式证明机制高效解决争议。以链下处理为主，仅在争议缩小到单步操作时，让 L1 合约参与验证，从而显著降低链上的计算和存储负担。这种机制基于双方的回合制交互，将争议逐步缩小至最小范围，最终解决问题。与重执行交易模式相比，交互式证明更加高效。乐观情况下，它允许一个 Rollup 区块仅包含一个断言，覆盖整条链的状态变化，从而节省 L1 空间开销；在悲观情况下，L1 合约也只需验证操作方向正确，而非重执行整笔交易。此外，交互式证明不受以太坊交易 Gas Limit 和合约大小的限制，这为 Arbitrum 提供了更高的交易吞吐量和合约灵活性。交互式证明是 Arbitrum 设计的核心驱动力，决定了其高效性和灵活性。大多数特性都围绕这一机制展开，显著提升了 Rollup 的性能和实用性，突破了传统 Rollup 设计的限制。


### 2024.12.16

Arbitrum One 是基于 Optimistic Rollup 技术的以太坊扩展链，结合 L1 和 L2 架构，通过 EthBridge 和 Arbitrum 虚拟机（AVM）实现智能合约执行和数据交互。Nitro 是 Arbitrum One 的升级版本，提供更低费用、更高以太坊兼容性，并通过 zk 证明和优化的 Geth 引擎提升性能。Arbitrum Nova 则是专为游戏和社交应用等高频交互的 DApp 设计的链，采用 AnyTrust 技术，提供两种数据发布方式，通过牺牲部分安全性提升性能，适合成本敏感的用例。


### 2024.12.17
Nitro 代表了 Arbitrum 技术发展的重要一步，是 Arbitrum One 主网的技术堆栈的升级版，我们现在称之为“Arbitrum Classic”，它比 2018 年最初的 Arbitrum 白皮书描述的技术更为先进。本文将解释 Nitro 升级的原因，并概述其相对于经典系统的核心优势。
从宏观来看，Classic 和 Nitro 系统的目标相似：都旨在提供一个尽可能接近 EVM（以太坊虚拟机）的执行环境，作为以太坊的第二层（L2）解决方案。即，通过以太坊自身的简洁欺诈证明来确保和执行 L2 虚拟机状态更新的安全性。
在 Arbitrum Classic 中，我们通过定制的虚拟机（AVM）实现这一目标，而 Arbitrum 的 L2 状态机实现（称为“ArbOS”）则是一个编译后上传到 AVM 的程序，具备模拟 EVM 执行能力的功能。
在 Nitro 中，我们采用 WebAssembly (Wasm) 替代 AVM 执行低级指令。由于 Go 代码可以编译为 Wasm，因此我们能够使用 Go 实现 ArbOS，并将 Geth（最广泛使用的以太坊实现）作为子模块嵌入其中。这一架构（直接使用 Geth 的 EVM 实现）是 Nitro 的核心特征，也是 Nitro 升级的关键。


### 2024.12.18
$ARB 代币:$ARB 代币是一种 ERC-20 治理代币，持有者可以通过它参与 Arbitrum DAO 的链上治理，决定 Arbitrum One 和 Arbitrum Nova 链的运行和升级。代币的投票权根据持有数量加权，更多代币意味着更大的投票影响力。$ARB 代币可以委托给他人使用，方便没有时间审查提案的成员参与治理。$ARB 的初始供应量为 100 亿枚，每年最多铸造 2% 的新币，铸币活动由 DAO 通过提案管理。通过 $ARB 代币，持有者可以民主地影响 Arbitrum 生态系统的未来。


### 2024.12.19
治理框架:ArbitrumDAO的修订宪法设定了治理规则和程序，其中部分规则通过链上智能合约执行，其他则通过链下行动。所有规则具有同等约束力，且包括推荐指南，虽然不具约束力，但作为良好治理的建议。该宪法描述了ArbitrumDAO和Arbitrum基金会的治理框架，并明确了可修改的程序。

链所有权:ArbitrumDAO可授权创建额外的Layer-2链，这些链使用Arbitrum技术结算到以太坊。每个新增的链必须通过AIP授权，且根据是否受到$ARB代币管理，分为治理链和非治理链。治理链受到$ARB代币管理，而非治理链则不受代币管理，但都需在以太坊上结算。

DAO提案和投票程序:AIP提案的提交和投票遵循严格的程序。首先，提案会进行体温检查（1周讨论），然后进行正式AIP提交并进行为期3天的投票。投票期后，DAO成员将在14-16天内投票决定提案是否通过。每个提案需标明是否为宪法AIP，宪法AIP修改章程，而非宪法AIP包括资金申请和信息性提案。

提案通过标准:AIP提案的通过需要满足特定的投票条件：宪法AIP要求至少5%的$ARB代币参与投票，非宪法AIP要求至少3%。投票期间，如果达成条件，提案会进入下一阶段。若未通过，则结束流程。通过后，宪法AIP将进入后续阶段执行，非宪法AIP则直接执行。

提案实施阶段:提案通过后的实施分为多个阶段：L2等待期、L1消息和L1等待期。经过这些阶段后，AIP将最终实施。实施可以通过L1上的确认消息来启动，也可以通过治理链间的交易来完成。整个AIP提案和执行流程一般需要27到37天，具体时长取决于提案的类型。
<!-- Content_END -->
