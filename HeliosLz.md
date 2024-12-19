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

# Helios

1. hi, 大家好。Arbitrum 最近不断的涌入资金，想来生态的发展正在日渐繁荣，刚好 LXDAO 开启了这场共学，那我一定要报名。欢迎和我组队，大家可以一起激发些 idea，看看能不能学完后开发个 demo，去参加黑客松。
2. 你认为你会完成本次残酷学习吗？ Maybe，哈哈哈哈哈 主要是我确实有点忙。 我尽量完成✅。 没有完成我也后面抽时间学完。

## Notes

<!-- Content_START -->

### 2024.12.10

1. 什么是 Arbitrum？
定义：Arbitrum 是一种专注于扩展以太坊的 Layer 2 解决方案，旨在提供更快、更便宜的交易处理，同时继承以太坊的安全性。
核心技术：
Arbitrum Rollup：一种 Optimistic Rollup 技术，利用欺诈证明（Fraud Proof）确保链上交易的正确性。

2. 为什么需要 Arbitrum？

以太坊的瓶颈：
* 每秒只能处理约 20-40 笔交易。
* 当网络拥堵时，Gas 费用会显著增加，导致交易成本高昂。

Arbitrum 的解决方案：
* 把大部分交易的计算和存储转移到 Layer 2（链下）处理，仅将结果提交到以太坊 Layer 1。
* 提供与以太坊主网相同的安全性，同时显著提高交易速度和降低费用。

3. Arbitrum 的工作原理

### Layer 2 和 Layer 1 的协作

Layer 2 处理：
* Arbitrum 在链下处理交易，并生成状态更新（如余额变化）。
* 将交易结果（如状态根或交易摘要）发送到以太坊 Layer 1。

Layer 1 验证：
* 以太坊“乐观地假设”所有 Layer 2 交易是正确的。
* 如果有问题（如恶意操作），任何验证者都可以提交“欺诈证明”，要求重新验证。

### 欺诈证明（Fraud Proof）机制

核心逻辑：
* 如果有人认为 Layer 2 的结果错误，可以提交欺诈证明。
* 验证者在以太坊上重新计算交易，判断提交结果的正确性。

结果：
如果发现错误：
提交错误数据的验证者会被经济惩罚（质押资金被扣除）。
恢复到正确的状态。
如果无误，挑战者会失去质押资金。

4. Arbitrum 的关键特点

安全性
* Arbitrum 继承了以太坊的安全性：
* 数据直接存储在以太坊上，任何人都可以验证交易是否正确。
* 只需一个诚实的验证者，就可以确保系统安全。

去信任化：
* 验证者的操作通过以太坊智能合约裁定，减少对中介的信任需求。

高效性

交易速度快：
* 链下计算减少了以太坊的负载，提升了吞吐量。
* 费用更低：
* 仅需支付链上存储结果的 Gas 费用，而非每笔交易的计算费用。

开放性
* 任何人都可以成为验证者：
* 无需许可，只需运行开源软件并质押 ETH 即可。
* 开发者友好：
* 支持以太坊智能合约的部署，无需修改现有代码。

 5. Arbitrum 的生态系统

开发者应用：
* 开发者可以在 Arbitrum 上部署与以太坊完全兼容的智能合约。
* 支持所有现有的以太坊工具（如 Remix、Truffle）。

用户体验：
* 用户可以通过钱包（如 MetaMask）直接与 Arbitrum 网络交互。

6. 总结：Arbitrum 的优势

安全性：数据存储在以太坊上，继承以太坊的强大安全性。

高效性：快速处理交易，降低 Gas 费用。

开发者友好：兼容以太坊工具链，无需额外学习成本。

灵活性：验证者开放，任何人都可以参与。

### 2024.12.11

### Rollup
说白了就是把交易的信息打包到 L2 执行，然后把证明存储到以太坊

### ZK Rollups
使用零知识证明来验证交易信息，（零知识证明是一种算法：比如你告诉我房间里有什么东西来证明，这个房子是你的，而不是拿出钥匙打开房门。）

### Optimistic Rollups
乐观假设 + 欺诈证明

Arbitrum 是一个基于 Optimistic Rollups 的 L2 扩展方案，但它在以下方面有所优化：
	•	更高效的欺诈证明机制：Arbitrum 将欺诈证明分解为多轮挑战，使得欺诈检测的成本更低。
	•	EVM 兼容性强：支持直接迁移以太坊智能合约。
	•	性能优化：相较于其他 Rollup 方案，Arbitrum 在处理复杂合约时更高效。

### ZK Rollups vs. Optimistic Rollups
<img width="380" alt="image" src="https://github.com/user-attachments/assets/87bc5dcd-2910-4e51-ad00-f1182869258c">

### 2024.12.12
挑战状态流程图：

<img width="837" alt="image" src="https://github.com/user-attachments/assets/04119a56-3176-4e47-af4a-6849fa5c8350" />

**1. 起点：Start**
挑战游戏从这里开始，当一个验证者对 Layer 2 的状态（通常是区块或执行结果）提出质疑时。

**2. 阶段一：Block Challenge（区块挑战）**
目标：验证某个区块的输入状态和输出状态之间的过渡是否正确。
过程：
* 验证者对区块状态提出争议，二分协议（bisectExecution）逐步将争议范围从整个区块缩小到具体的有问题区域。
* 当争议锁定到一个单独的区块时，状态会转移到 Execution Challenge（执行挑战）阶段。

**3. 阶段二：Execution Challenge（执行挑战）**
目标：验证具体的交易执行步骤是否正确。
过程：
* 争议范围进一步缩小到某一笔交易的执行步骤。
* 通过多轮二分协议（bisectExecution），争议最终聚焦到单步执行。
* 当争议范围缩小到一步执行时，当前响应者可以调用 oneStepProveExecution，提供具体证明来展示某一步执行的结果是否正确。

**4. Timeout（超时）**
意义：为每个阶段设置了时间限制，确保挑战不会无限期拖延：
如果一方未在规定时间内响应挑战，则该方被判负。
超时处理是系统避免死锁的重要机制。

**5. Emergency Upgrade（紧急升级）**
目的：如果挑战结果可能出错或存在争议，系统会进入“等待超时”的状态，为潜在的紧急合约升级预留时间。
应用场景：
在极端情况下（如合约代码错误），开发团队可以利用这段时间对合约进行修复或升级。

**6. 结束状态：End**
挑战完成后，系统进入最终状态：
胜方：获胜方的状态声明被接受，并可能获得作恶方的押金作为奖励。
败方：失败方丧失押金，并且之前提交的状态被撤销。

**重点解析关键路径**
* bisectExecution：表示二分协议的操作，用来逐步缩小争议范围。
* oneStepProveExecution：表示争议最终锁定到单步执行时的证明操作。
* timeout：超时机制确保挑战有明确的时间界限，防止无休止争议。


假设 Layer 2 系统包含以下全局状态：
1. 输入状态（全局状态 S0）：
* 区块 X-1 的全局状态根。
* 包括账户 A 的余额 100 和账户 B 的余额 50。
2. 输出状态（全局状态 S1）：
* 区块 X 的执行后状态根。
* 声明账户 A 的余额为 80，账户 B 的余额为 70。
3. 问题：
* 挑战者（验证者）检查区块 X 的交易，发现某笔交易未正确更新余额（比如账户 A 实际应该剩余 90，而不是 80）。
* 挑战者发起挑战，逐步缩小到区块 X 的具体交易段或交易步骤。
4. 结果：
* 如果挑战成功，全局状态 S1 被撤销，系统回滚到 S0，或者部分交易被重新验证。

### 2024.12.13
断言：在 Arbitrum 等基于 Optimistic Rollup 技术的系统中，断言（Assertion） 是验证者对某一交易或状态转换的声明或主张。简单来说，断言是验证者向主链提交的一种“保证”或“承诺”，它描述了某个区块或交易的初始状态和最终状态之间的关系。

**断言的作用：**
* 主链记录：Layer 2 的执行结果以断言的形式提交到主链，供其他验证者审查。
* 性能优化：主链并不立即验证每个断言，而是假定它们是正确的，只有在有验证者提出挑战时才检查。

Arbitrum 的交互式欺诈证明机制通过引导争议双方在链下进行多轮交互，逐步缩小争议范围，最终在链上验证最小的争议单元，从而高效解决分歧，减轻主链负担。

![image](https://github.com/user-attachments/assets/7e6f4e7a-204a-4d57-99b0-a5252946c212)

**Arbitrum One**

Arbitrum One 是 Arbitrum 的首个主网，采用交互式欺诈证明机制来确保交易的正确性。其架构分为 Layer 1（以太坊主网）和 Layer 2（Arbitrum 链）两部分。在 Layer 1 上，EthBridge 作为一组以太坊合约，负责仲裁 Arbitrum Rollup 协议，并维护 Arbitrum 在以太坊链上的收件箱和发件箱。用户、Layer 1 合约和全节点可以通过这些收件箱和发件箱与 Arbitrum 链交互。在 Layer 2 上，Arbitrum 虚拟机（AVM）运行 ArbOS，确保智能合约的执行。

**Arbitrum Nitro**

Arbitrum Nitro 是对 Arbitrum One 的技术栈升级，旨在降低费用、提高以太坊兼容性，并简化零知识证明。Nitro 的关键创新包括：
* 无需共识机制的证明程序：由于 Sequencer 的状态转移函数是公开的，任何人都可以根据已知的交易顺序计算状态转移结果，因此节点无需共识机制，只需获取交易序列并在本地运行即可。
* 用 Go 语言重写的节点软件 Geth：通过直接编译 Geth 的核心，实现更高的以太坊兼容性。
* 执行与证明的分离：将执行和证明分别用不同的代码实现，以提高执行速度和证明的可移植性。
* 交互式欺诈证明的 Optimistic Rollup：采用多轮欺诈证明机制，通过二分查找找到引起分歧的操作码，并在链上执行该操作码以解决争议。

**Arbitrum Nova**

Arbitrum Nova 基于 AnyTrust 技术，专为游戏、社交应用程序和对成本更敏感的用例设计。其特点包括：
* 数据可用性委员会：引入数据可用性委员会，将原本应存储在收件箱合约中的 calldata 数据转移到链下存储。委员会为批量交易签署数据可用性证书（DACerts），并将其上传到主网的收件箱合约，从而降低发送到主网的数据量。
* 最小信任假设：委员会有 N 名成员，只需确保至少有 2 名成员是诚实的，即可保证 Rollup 协议的正常运行。
* 数据发布方式：Nova 提供两种数据发布方式：一种是像 Nitro 一样以 calldata 的形式发布完整数据，另一种是发布 DACert 以证明数据的可用性。

通过这些设计，Arbitrum Nova 在一定程度上牺牲了去中心化特性，但相比其他侧链和采用 BFT 共识的链，仍具有较高的优势。

### 2024.12.15
![image](https://github.com/user-attachments/assets/982ba281-f27a-47fc-b326-7ef7f69b96f4)
Original napkin sketch drawn by Arbitrum co-founder Ed Felten

![image](https://github.com/user-attachments/assets/fe1421b3-85c1-402f-8359-2e13356ac8ad)
Nitro 如何处理事务

![image](https://github.com/user-attachments/assets/d4c12796-a5dc-4218-ad7f-27b59db86281)

<img width="844" alt="image" src="https://github.com/user-attachments/assets/f5567c23-ed1b-4eb4-938a-92550bee95f0" />


### 2024.12.17
![image](https://github.com/user-attachments/assets/fe1ba14c-f33b-4299-8e41-fb209ffff083)

**技术路线图：**
1. Stylus：多语言智能合约开发
2. BoLD（Layer 1 区块的批次上链数据）：实现去中心化验证
3. 审查超时：在 BoLD 的基础上，审查超时可限制重复审查或离线排序器对 Arbitrum 链造成的负面影响（可能由于攻击而造成）。这为 Arbitrum 链提供了更强的抗审查保证，并改善了用户资金访问。
4. 去中心化排序器：去中心化排序器将交易排序的责任分散到更广泛的去中心化参与者网络中，从而降低审查攻击的风险并提高可靠性。

**互操作解决方案**
1. 快速提款
2. 链集群通过允许多个 Orbit 链紧密结合其生态系统和基础设施，链集群可用于将跨链通信时间从几分钟缩短到近乎即时。

**性能和效率**
1. 多客户端支持
2. 零知识证明：ZK+乐观混合证明

**Arbitrum 网络概述**

![image](https://github.com/user-attachments/assets/7fa0cb82-06e6-45d5-be05-b6aabc8c50df)

应用生态系统
![image](https://github.com/user-attachments/assets/dfa322ce-aca1-44b8-b168-8221cbcdc2c0)

### 2024.12.18

**Arbitrum 生态汇总**

经不完全统计，Arbitrum 生态门户共列出了 170 多个项目，在重新优化分类之后，我们发现 Arbitrum One 主网上线半年后，Arbitrum 已日渐成型，目前，从参与入口来看，支持出入金、钱包、交易所以及桥和跨链项目就有 60 来个；统计的近 40 多个 DeFi 应用主要分布在衍生品、AMM 和收益优化方面；另外，NFT 方面，3 个 NFT 市场中 TreasureDAO 占据主导角色，TreasureDAO 旗下元宇宙游戏 Bridgeworld 内的 NFT 系列热度偏高，其他 NFT 项目大多数缺乏持久热度；另外还有 30 来个支持 Arbitrum 的工具、基础设施以及节点提供方。

纳入 The Arbitrum Odyssey 生态采用计划的 56 个项目中，在经过社区投票后，Yield Protocol、Hashflow、Aboard Exchange、tofuNFT、Uniswap、ApeX、1inch、Yin Finance、DODO、Swap…

Arbitrum Orbit 允许无需许可地构建自己的专用链。每个 Orbit 链都可以配置为使用 Rollup 或 AnyTrust，自定义设置吞吐量、隐私、Gas 代币、治理、协议逻辑、独立产品路线图，同时受益于 Stylus 引入的相同 EVM+ 兼容性，也允许用 Solidity、C、C++ 和 Rust 部署与 EVM 兼容的智能合约。

**$ARB 代币：**
$ARB 代币在 Arbitrum 网络的去中心化治理和生态系统中扮演着核心角色。以下是其主要功能概述：
1. 治理代币
2. 激励机制
3. 安全性与质押
4. 费用模型
5. 生态系统扩展


$ARB 代币创新点：支持多种安全模型，尤其是 Arbitrum Orbit 的多样化选择（Rollup 或 AnyTrust）。这些模型不仅为开发者提供了灵活的选择，还可以根据项目的不同需求调整安全性和交易成本。

Arbitrum Orbit 支持自定义 Gas 代币，这使得每个 Orbit 链可以选择特定的 ERC-20 代币作为交易费用，而不是依赖于固定的原生代币。

### 2024.12.19

代币分配概览：
* Arbitrum DAO 国库：35.28%（35.28 亿枚）
* 团队、贡献者和顾问：26.94%（26.94 亿枚）
* 投资者：17.53%（17.53 亿枚）
* Arbitrum 平台用户（通过空投分配）：11.62%（11.62 亿枚）
* Arbitrum 基金会：7.5%（7.5 亿枚）
* 在 Arbitrum 上构建应用的 DAO（通过空投分配）：1.13%（1.13 亿枚）

积分获取方式：
1. 在 Arbitrum One 上的活动：
桥接资金到 Arbitrum One：1 分
在不同月份进行交易：
* 2 个月：1 分
* 6 个月：1 分
* 9 个月：1 分

交易次数或与智能合约交互数量：
* 超过 4 次：1 分
* 超过 10 次：1 分
* 超过 25 次：1 分
* 超过 100 次：1 分

交易总价值：
* 超过 $10,000：1 分
* 超过 $50,000：1 分
* 超过 $250,000：1 分

桥接资产总价值：
* 超过 $10,000：1 分
* 超过 $50,000：1 分
* 超过 $250,000：1 分

2. 在 Arbitrum Nova 上的活动：
* 活动可增加至多 1 分，或在 Arbitrum One 上已获得 4 分或以上的情况下，再增加 1 分。

重要提示：
* 每项符合条件的操作最多可获得 1 分，积分上限为 15 分。
* 在 Arbitrum Nitro 于 2022 年 8 月 31 日上线之前（区块高度 #22207817）获得的积分（至少 3 分）将计为双倍。

当前流通供应量（截至 2024 年 3 月 7 日）：
总流通量：约 15.37 亿枚 $ARB
具体分配：
* Arbitrum DAO 国库：1.26 亿枚
* 平台用户（通过空投）：10.93 亿枚
* Arbitrum 基金会：2.06 亿枚
* 在 Arbitrum 上构建应用的 DAO：1.13 亿枚

![image](https://github.com/user-attachments/assets/9ca419fe-6d28-48b3-a6f2-96dc03e5d6cc)


Arbitrum 对其生态系统中符合条件的 DAO 的初始 ARB 代币分配。
主要接收 DAO 及其分配情况：
* Treasure：800 万枚 ARB
* SushiSwap：约 4,249,418 枚 ARB
* Dopex：3,867,103 枚 ARB
* Radiant Capital：3,348,026 枚 ARB
* Balancer：3,090,486 枚 ARB

后续行动主要发现：
* 多数协议尚未动用空投代币：约 80% 的空投代币仍然保留在多重签名钱包中，未被使用。

部分协议已制定代币使用计划：
* Balancer：计划将 100 万枚 ARB 分批（每两周 10 万枚）奖励给活跃的流动性提供者，剩余的 200 万枚用于协议拥有的流动性（POL）。
* Radiant Capital：已批准将 40% 的代币空投给新的 6 个月和 1 年期的 dLP 锁仓用户，30% 分配给所有 Arbitrum dLP 锁仓用户，剩余 30% 保留用于未来使用。
* Stargate DAO：计划将 70% 的代币用于 Arbitrum 上的流动性挖矿激励，30% 分配给合作伙伴，以促进生态系统发展。

个别协议直接出售空投代币：一些协议选择将收到的 ARB 代币出售，以获取运营资金。

### $ARB 的估值方法

市场估值采用以下两种方法进行分析：

（1）完全稀释估值（Fully Diluted Valuation, FDV）
* FDV = $ARB 的单价 × 总供应量。
* 假设 $ARB 的初始交易价格为 1.5 美元：
* FDV = 1.5 美元 × 100 亿 = 150 亿美元。

这是市场对整个 Arbitrum 网络的长期估值。

（2）流通市值（Circulating Market Cap）
* 流通市值 = $ARB 的单价 × 流通供应量。
* 假设初期流通供应量为 12.75 亿枚（11.62% 用户空投 + 1.13% DAO 空投部分 + 其他分配），单价为 1.5 美元：
* 流通市值 = 1.5 美元 × 12.75 亿 = 19.125 亿美元。

这反映了早期流通市场的实际估值，通常低于 FDV。

<img width="737" alt="image" src="https://github.com/user-attachments/assets/5e4769fa-4356-40c2-a515-83d3f2ccbf47" />

<!-- Content_END -->
