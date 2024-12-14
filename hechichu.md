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


# {hechichu}

1. 自我介绍
  第一次参加共学活动,大三理科学生

2. 你认为你会完成本次残酷学习吗？
  可以的

## Notes

<!-- Content_START -->

### 2024.12.10

Arbitrum 简介
什么是 Arbitrum？
Arbitrum 是一个为扩展以太坊而设计的技术套件，提供比以太坊更低成本、更快速度的交易环境，同时保留以太坊级别的安全性。其核心产品 Arbitrum Rollup 是一种乐观汇总（Optimistic Rollup）协议。
为什么需要 Arbitrum 来扩展以太坊？
以太坊虽然强大，但其每秒交易量（TPS）有限（约 20-40），当达到上限时，用户竞争会导致交易费用上升。这种限制是为了确保以太坊的去中心化性质，使节点运行成本相对可控。

Arbitrum 简介
什么是 Arbitrum？
Arbitrum 是一个为扩展以太坊而设计的技术套件，提供比以太坊更低成本、更快速度的交易环境，同时保留以太坊级别的安全性。其核心产品 Arbitrum Rollup 是一种乐观汇总（Optimistic Rollup）协议。

为什么需要 Arbitrum 来扩展以太坊？
以太坊虽然强大，但其每秒交易量（TPS）有限（约 20-40），当达到上限时，用户竞争会导致交易费用上升。这种限制是为了确保以太坊的去中心化性质，使节点运行成本相对可控。

Arbitrum Rollup 的工作原理
乐观执行：
Arbitrum Rollup 通过将链上的大部分计算和存储转移到链下，降低以太坊主链（L1）的负担。主链假设 Arbitrum 上的活动是合法的，只有在发现违规时才会通过争议解决机制回到 L1 证明欺诈。

数据透明性：
所有交易数据都会被发布到以太坊主链上，即使出现争议，也能通过这些数据验证欺诈行为，从而继承以太坊的安全性。

验证者机制：
验证者推动 Arbitrum 链的状态更新，并在发现欺诈时提出争议。只要有一个诚实的验证者，链的安全性就能得到保障。


用户体验与开发者优势
与以太坊兼容：
用户可以使用熟悉的以太坊钱包与 Arbitrum 交互，开发者也能使用现有的以太坊工具部署智能合约。

更高效的交易处理：
Arbitrum 通过批量提交交易和数据压缩等技术，大幅降低了交易成本。

扩展性：
除了 Rollup，Arbitrum 还提供 AnyTrust 链 和 Orbit 链：

AnyTrust 链适用于不需要完全去中心化的应用，提供更低成本。
Orbit 链允许开发者创建自己的链，进一步扩展应用场景。


Arbitrum 简介
什么是 Arbitrum？
Arbitrum 是一个为扩展以太坊而设计的技术套件，提供比以太坊更低成本、更快速度的交易环境，同时保留以太坊级别的安全性。其核心产品 Arbitrum Rollup 是一种乐观汇总（Optimistic Rollup）协议。

为什么需要 Arbitrum 来扩展以太坊？
以太坊虽然强大，但其每秒交易量（TPS）有限（约 20-40），当达到上限时，用户竞争会导致交易费用上升。这种限制是为了确保以太坊的去中心化性质，使节点运行成本相对可控。

Arbitrum Rollup 的工作原理
乐观执行：
Arbitrum Rollup 通过将链上的大部分计算和存储转移到链下，降低以太坊主链（L1）的负担。主链假设 Arbitrum 上的活动是合法的，只有在发现违规时才会通过争议解决机制回到 L1 证明欺诈。

数据透明性：
所有交易数据都会被发布到以太坊主链上，即使出现争议，也能通过这些数据验证欺诈行为，从而继承以太坊的安全性。

验证者机制：
验证者推动 Arbitrum 链的状态更新，并在发现欺诈时提出争议。只要有一个诚实的验证者，链的安全性就能得到保障。

用户体验与开发者优势
与以太坊兼容：
用户可以使用熟悉的以太坊钱包与 Arbitrum 交互，开发者也能使用现有的以太坊工具部署智能合约。

更高效的交易处理：
Arbitrum 通过批量提交交易和数据压缩等技术，大幅降低了交易成本。

扩展性：
除了 Rollup，Arbitrum 还提供 AnyTrust 链 和 Orbit 链：

AnyTrust 链适用于不需要完全去中心化的应用，提供更低成本。
Orbit 链允许开发者创建自己的链，进一步扩展应用场景。

当前的 Arbitrum 产品
Arbitrum One：一个 Rollup 链，强调去中心化和安全性。
Nova：一个 AnyTrust 链，适合需要高吞吐量、低费用的应用。
此外，开发者可以基于 Arbitrum 的技术栈（如 Nitro 和 Stylus）创建高性能的智能合约，甚至使用如 Rust、C++ 等编程语言。

### 2024.12.11
### Arbitrum 概述

Arbitrum 是一套以太坊扩容解决方案，旨在简化去中心化应用的构建和使用。其提供了多个协议、链、服务和 SDK，支持 Arbitrum 生态系统的运行。

#### Arbitrum 组件：
1. **Arbitrum Rollup**  
   - 用于扩展以太坊智能合约的协议。
   
2. **Arbitrum AnyTrust**  
   - 更进一步扩展以太坊智能合约的协议，采用轻度信任假设。
   
3. **Arbitrum Nitro**  
   - 实现 Rollup 和 AnyTrust 协议的节点软件。
   
4. **Arbitrum 节点**  
   - 运行 Nitro 软件的机器，用于服务或与 Arbitrum 链交互。
   
5. **Arbitrum One**  
   - 公共的 Rollup 链。
   
6. **Arbitrum Nova**  
   - 公共的 AnyTrust 链。
   
7. **Arbitrum 桥接**  
   - 支持在以太坊、Arbitrum 和部分 Orbit 链之间转移 ETH 和 ERC-20 代币。
   
8. **Arbitrum Orbit**  
   - 支持运行自定义的 Rollup 和 AnyTrust 链。
   
9. **Arbitrum Stylus**  
   - 支持用 Rust 或其他编译成 Wasm 的语言编写与 EVM 兼容的智能合约。

#### Arbitrum 面向用户：
- **Arbitrum 桥接**  
  - 用户可以通过 Arbitrum 桥接在以太坊、Arbitrum 和部分 Orbit 链之间转移 ETH 和 ERC-20 代币。
  
- **Arbitrum Portal**  
  - 提供一个 Arbitrum 上 DApp 的目录。

- **快速入门（桥接）**  
  - 为第一次使用桥接的用户提供逐步指导。

#### Arbitrum 面向开发者：
- **Arbitrum 简介**  
  - Arbitrum 扩容解决方案的技术介绍。

- **快速入门（Solidity）**  
  - 针对 Web2 开发者，帮助其将 Solidity 智能合约部署到 Arbitrum。

- **快速入门（Rust）**  
  - 针对 Web3 开发者，帮助其使用 Stylus 将 Rust 智能合约部署到 Arbitrum。

#### Arbitrum 面向节点运行者：
- **运行完整节点**  
  - 帮助节点运行者在不依赖第三方节点的情况下访问 Arbitrum 链。

- **配置数据可用性委员会**  
  - 面向数据可用性委员会成员和 Orbit 链运营者，帮助其运行数据可用性服务器。

#### Arbitrum 面向链运营者：
- **Orbit 简介**  
  - 为有意了解 Orbit 价值主张和使用场景的读者提供的内容。

- **Orbit 快速入门**  
  - 帮助链运营者使用 Arbitrum Orbit 部署其第一个 Arbitrum 链。

#### 技术原理：
- **Nitro 内部架构**  
  - 对 Nitro 架构的技术深入分析。

- **AnyTrust 协议内部**  
  - 对 AnyTrust 协议的技术深入分析。

- **Arbitrum 白皮书**  
  - 介绍 Nitro 的原始白皮书。

- **DAO 文档**  
  - 支持 Arbitrum DAO 成员的文档。

### 2024.12.12
### Rollup 学习笔记

**1. 什么是 Rollup**

Rollup 的核心是“归纳整理”，目的是缓解以太坊网络拥堵、提高 TPS（每秒交易量）并降低 Gas 费用。它的工作原理是将以太坊上的计算任务转移到 Layer 2 层协议进行处理，将计算结果压缩后再返回以太坊主网。

Rollup 类比：  
就像节假日景区的排队问题，平日直接排队效率较低，但节假日通过可信赖的代表来集中处理问题，可显著提升效率。

主要作用：  
- 将大量交易签名压缩成一个“VIP”签名块。
- 提升以太坊网络的吞吐量与运行效率。
- 同时保留链上部分数据以保障安全性。

Rollup 的两种主要实现方式为 **ZK Rollups** 和 **Optimistic Rollups**，它们分别有不同的特点和应用场景。

---

**2. 什么是 ZK Rollups**

**ZK Rollups** 利用零知识证明技术（ZK-SNARK），通过 Layer 2 验证者进行交易真实性认证，并将结果压缩后返回以太坊。

ZK 的四大特点：
1. **Zero Knowledge**：无需查看完整交易数据即可验证交易。  
2. **Succinct**：认证过程简洁高效。  
3. **Non-Interactive**：验证无需交互。  
4. **Argument of Knowledge**：确保数据的真实性和正确性。  

**优点**：
- 验证速度快，可快速将 Layer 2 的资产转回 Layer 1。
- 适合支付、银行和交易所等快速结算业务。

**缺点**：
- 算法复杂，对开发者有较高的技术门槛。

---

**3. 什么是 Optimistic Rollups**

**Optimistic Rollups** 采取“乐观假设”的方式，默认所有交易都是可信的，并由验证者通过奖惩机制发现和处理异常。

工作原理：  
验证者需要质押代币作为保证金，若其他验证者发现问题，可通过欺诈证明对其进行罚款。

**优点**：
- 开发友好，适合迁移原本在 Layer 1 的 Dapp 项目。
- 具有智能合约功能，可通过相应的治理代币进行治理。

**缺点**：
- 从 Layer 2 提币到 Layer 1 速度较慢（通常需要 1 周以上）。  
- 存在验证者作恶的潜在风险。

---

**4. 什么是 Arbitrum**

Arbitrum 是基于 Optimistic Rollups 的 Layer 2 协议项目，目前 TVL（总锁仓价值）位居前列。与 Optimism 项目相比，Arbitrum 采用多轮欺诈证明，更加高效，并且具有自己的虚拟机，增强了与以太坊网络的兼容性。

---

**总结**：
- **Rollup**：通过将任务“外包”给 Layer 2，提升以太坊运行效率。
- **ZK Rollups**：基于零知识证明算法，适合支付类业务，验证速度快但算法复杂。
- **Optimistic Rollups**：通过默认信任和奖惩机制，适合 Dapp 和 DeFi 项目，提币速度较慢。
- **Optimism 和 Arbitrum**：两者都属于基于 Optimistic Rollups 的协议项目，适配不同场景需求。  
- **ZKSync**：基于 ZK Rollups 的典型项目之一。

ZK Rollups 未来潜力大，但目前 Optimistic Rollups 更适合 Dapp 生态发展。

### 2024.12.13
### 挑战机制笔记

#### 区块挑战
1. **起始阶段**：挑战从全局状态（包括区块哈希）开始进行二分操作。
2. **缩小范围**：在实际的机器执行争议之前，争议会逐步缩小到单个区块。
3. **执行挑战**：当争议缩小到单个区块后，当前响应者可以调用 `challengeExecution`。  
   - 这类似于二分操作，响应者需提供一个竞争的全局状态和机器状态。
   - 根据这些信息，挑战会进入具体的执行挑战阶段。

#### 执行挑战
1. **单步执行验证**：当争议被进一步缩小到单步执行时，当前响应者可以调用 `oneStepProveExecution`。
2. **证明步骤**：响应者需提供执行机器某一步所需的证明数据。
   - 如果执行该步骤后结果状态与之前声明的状态不一致，当前响应者胜出挑战。

#### 通用二分协议
1. **定义**：协议中的“二分”泛指对任意程度的切分。
2. **挑战过程**：
   - 使用 `ChallengeLib` 的 `hashChallengeState` 方法计算挑战状态哈希（`challengeStateHash`），其基于分段哈希列表、起始位置和总段数长度。
   - 每段的步数距离为 `floor(segmentsLength / degree)`，最后一对段则加上 `segmentsLength % degree`，确保总步数一致。
3. **初始阶段**：
   - 挑战以两个分段（程度为 1）开始，即提出者的初始声明。
   - 挑战者回合中，需选择相邻的一对分段进行质疑，并提供与第二段不同的结束分段，将挑战进一步细化。
4. **递进规则**：
   - 每次二分的最大程度为 `min(40, numStepsInChallengedSegment)`，确保挑战持续推进。
   - 长度为 1 步的分段无法继续二分，此时挑战具体进入 `challengeExecution` 或 `oneStepProveExecution`。

5. **对称性**：与传统二分协议不同，双方轮流选择挑战位置并在质疑时提出二分。

#### 获胜条件
1. **胜利机制**：当前响应者胜出后，挑战状态哈希被设置为 0，对手无法继续有效操作，最终超时失败。
2. **延时胜利**：胜利不是即时的，此设计用于在挑战结果出错时，可以通过合约升级解决问题。

### 2024.12.14
### Arbitrum One 笔记：交互式证明及设计核心

#### **Arbitrum 的设计背景**  
1. **Optimistic Rollups 的争议解决方式**  
   - 两种方法：交互式证明和重执行交易。  
   - Arbitrum 采用交互式证明，注重效率与灵活性。  

2. **历史发展**  
   - 2014 年开始开发交互式欺诈证明。  
   - 核心机制发表于 2018 年，现已进行多次升级。  

---

#### **交互式证明（Interactive Proofs）**  
1. **基本原理**  
   - 通过 L1 合约引导，Alice 和 Bob 参与回合制协议以缩小争议范围。  
   - 如果 N 步执行步骤有争议，Alice 将其分为两部分，Bob 挑战其中一部分。  
   - 争议逐步缩小到单步指令，由 L1 合约验证单步断言的正确性。  

2. **优势**  
   - **链下处理优先**：Alice 和 Bob 在链下尽量解决分歧，降低 L1 合约负担。  
   - **效率高**：大多数争议处理都无需在链上模拟执行完整交易。  

---

#### **重执行交易（Re-execution of Transactions）**  
1. **方法描述**  
   - 每笔交易附带状态哈希值断言。  
   - 在争议中，L1 合约模拟完整交易以验证结果。  

2. **局限性**  
   - L1 合约需要更多计算资源。  
   - 受限于以太坊的交易 Gas Limit 和区块容量。  

---

#### **交互式证明的优势**  
1. **乐观情形下的高效**  
   - 一个 Rollup 区块只需一个状态断言，节省 L1 区块空间。  
   - 相比重执行方法，减少状态断言的存储和验证成本。  

2. **悲观情形下的高效**  
   - 仅需检查争议步骤是否正确缩小，而非模拟完整交易。  
   - L1 合约开销更低，仅需验证单步指令。  

3. **突破 Gas Limit**  
   - 允许 Gas 消耗较大的交易，适应更复杂的操作。  
   - 重执行模式无法支持超过以太坊区块 Gas Limit 的交易。  

4. **合约大小无限制**  
   - 无需为每个 L2 合约创建对应的以太坊合约。  
   - 合约大小可超出以太坊限制。  

5. **更高的实现弹性**  
   - 支持 EVM 尚未定义的新指令。  
   - 不受限于 EVM 的原生功能，适配性更强。  

---

#### **Arbitrum 的设计核心**  
1. **交互式证明的驱动作用**  
   - Arbitrum 的许多设计特性为支持交互式证明而存在。  
   - **思考方向**：  
     - 该功能是否支持交互式证明？  
     - 如何利用交互式证明实现？  

2. **总结**  
   - 交互式证明是 Arbitrum 整体架构的核心，贯穿其设计的方方面面。
<!-- Content_END -->
