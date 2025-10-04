# 🚀 永续合约 DEX 学习计划

> 从零开始构建一个高质量的简化版永续合约去中心化交易所

## 📋 目录

- [项目概述](#-项目概述)
- [学习计划](#-学习计划)
  - [题目集合](./question.md)
- [项目质量保证](#-项目质量保证)
- [学习资源汇总](#-学习资源汇总)
- [重要提示](#-重要提示)

---

## 🎯 项目概述

### 为什么选择永续合约 DEX？

作为初级 EVM 智能合约开发者，永续合约 DEX（简化版）是最适合的挑战目标：

**✅ 优势：**
- **专注核心技能**：深入实践高级 Solidity 编程、安全模式和 Gas 优化
- **逻辑自包含**：大部分核心逻辑在合约内部，依赖外部协议较少
- **可验证性强**：通过严格单元测试证明实现的正确性
- **学习路径清晰**：有成熟的理论和实现参考（GMX, Perpetual Protocol）

**❌ 相比收益聚合器：**
- 不需要复杂的链上策略设计
- 避免多协议集成的复杂性
- 降低学习曲线的陡峭程度

### 项目目标

构建一个功能完整的简化版永续合约 DEX，包含：
- ✅ 虚拟 AMM (vAMM) 交易机制
- ✅ 保证金管理和头寸追踪
- ✅ 资金费率计算和支付
- ✅ 清算引擎
- ✅ 预言机价格集成
- ✅ 完整测试覆盖
- ✅ 测试网部署和演示

---

## 📚 学习计划

> **总时间：400小时** | **预计周期：8-10周** | **难度：高**

### 📝 学习资料
- [题目集合](./question.md) - 相关的题目和解答

### 阶段一：理论研究与学习 (80小时 - 第1-2周)

**🎯 目标：** 彻底理解永续合约的金融原理和主流实现

#### 📖 学习任务

| 模块 | 时间 | 内容 |
|------|------|------|
| **永续合约原理** | 20h | 定义、与传统期货区别、资金费率机制、清算流程、保证金计算 |
| **主流协议分析** | 30h | GMX、Perpetual Protocol v2 白皮书研究，理解 AMM 模型、清算逻辑 |
| **预言机学习** | 15h | Chainlink/Pyth 工作原理、集成方式、价格聚合机制 |
| **Solidity 进阶** | 15h | 高级技巧（delegatecall、库应用）、安全最佳实践 |

#### 📚 推荐资源

**权威文档：**
- [Solidity 官方文档](https://docs.soliditylang.org/) - 语言基础
- [以太坊黄皮书](https://ethereum.github.io/yellowpaper/Paper.pdf) - EVM 原理
- [Perpetual Protocol v1 白皮书](https://docs.perp.fi/v/v1-docs/learn/whitepaper) - vAMM 概念
- [GMX 文档](https://gmx.io/docs/gmx-overview/overview) - 流动性提供者模式

**交互式学习：**
- [CryptoZombies](https://cryptozombies.io/) - Solidity 基础
- [Cyfrin Updraft](https://www.cyfrin.io/updraft) - 免费综合课程

#### 🎯 预期产出
- 永续合约金融原理理解笔记
- 预言机集成方案选择
- 项目架构设计方向确定

---

### 阶段二：架构设计与核心合约开发 (120小时 - 第3-5周)

**🎯 目标：** 完成项目整体架构设计，实现核心交易和资金费率合约

#### 🏗️ 开发任务

| 模块 | 时间 | 内容 |
|------|------|------|
| **系统架构设计** | 30h | 合约模块划分、接口定义、UML 图绘制 |
| **开发环境搭建** | 10h | Hardhat/Foundry 项目骨架、测试框架 |
| **基础合约实现** | 40h | PerpetualLite.sol - 开仓/平仓、保证金管理、头寸追踪 |
| **预言机集成** | 20h | OracleAdapter.sol - Chainlink/Pyth 价格源封装 |
| **资金费率计算** | 20h | FundingRateCalculator.sol - 简化费率计算逻辑 |

#### 📚 参考代码库

**基础合约：**
- [OpenZeppelin Contracts](https://github.com/OpenZeppelin/openzeppelin-contracts) - 标准实现
- [Uniswap V2 Core](https://github.com/Uniswap/v2-core) - AMM 参考

**开发工具：**
- [Foundry Book](https://book.getfoundry.sh/) - 高效测试框架
- [Hardhat 文档](https://hardhat.org/) - 全面开发体验

#### 🎯 预期产出
- 详细项目架构文档
- 开发环境搭建完成
- 核心合约初始代码
- 基础单元测试

---

### 阶段三：清算引擎开发与风险管理 (100小时 - 第6-7周)

**🎯 目标：** 实现关键清算机制和基本风险管理

#### ⚡ 核心任务

| 模块 | 时间 | 内容 |
|------|------|------|
| **清算逻辑实现** | 50h | LiquidationEngine.sol - 清算识别、计算、执行 |
| **保证金检查** | 20h | 交易和清算中的健康检查集成 |
| **安全模块增强** | 20h | 访问控制、重入防护、外部调用安全 |
| **错误处理和事件** | 10h | 清晰错误消息和事件记录 |

#### 📚 参考实现

**清算逻辑参考：**
- [dYdX Solo Margin](https://github.com/dydxprotocol/solo) - 保证金计算和清算逻辑
- [GMX Contracts](https://github.com/gmx-io/gmx-contracts) - 仓位管理和清算

#### 🎯 预期产出
- 清算引擎合约代码
- 增强安全功能
- 完整单元测试

---

### 阶段四：测试、优化、文档与部署 (100小时 - 第8周)

**🎯 目标：** 确保代码健壮性、高效性和安全性，做好求职展示准备

#### 🔧 完善任务

| 模块 | 时间 | 内容 |
|------|------|------|
| **全面测试** | 40h | 集成测试、端到端测试、模糊测试 |
| **Gas 优化** | 20h | 合约操作 Gas 消耗分析和优化 |
| **安全自查** | 20h | OWASP/SWC 标准审计，漏洞修复 |
| **项目文档** | 10h | 详细 README、技术说明、部署指南 |
| **测试网部署** | 10h | Sepolia 部署、合约验证、交互演示 |

#### 🎯 预期产出
- 高测试覆盖率代码库
- Gas 优化和安全审计后的最终代码
- 专业 GitHub README 文档
- 测试网可交互合约

---

## 🏆 项目质量保证

### 如何区分"草草了事"和"全力以赴"的项目

#### 1. 代码质量与可读性 ⭐⭐⭐⭐⭐
- **命名规范**：变量、函数、合约名清晰、一致、有意义
- **代码结构**：按逻辑模块划分，函数职责单一
- **DRY 原则**：避免不必要的重复代码
- **注释质量**：关键逻辑、复杂计算、安全考量有清晰注释
- **可维护性**：代码易于理解和修改

#### 2. 测试覆盖率与质量 ⭐⭐⭐⭐⭐
- **测试框架**：使用 Foundry 或 Hardhat 专业框架
- **覆盖率**：超过 80% 的测试覆盖率
- **测试用例**：
  - ✅ 所有核心功能（开仓、平仓、资金费率、清算）
  - ✅ 边界条件（零保证金、最大杠杆、最小头寸）
  - ✅ 错误路径（保证金不足、未授权清算）
  - ✅ 真实场景（多用户并发、价格波动清算）
- **模糊测试**：使用 Foundry 进行非预期输入探索

#### 3. 文档质量 ⭐⭐⭐⭐⭐
- **项目概述**：清晰介绍目的、核心功能、解决问题
- **核心机制**：解释资金费率、清算机制、AMM 模型
- **架构设计**：UML 图或流程图展示合约交互
- **安全考量**：明确安全措施（重入防护、访问控制）
- **部署指南**：详细的环境搭建、测试、部署说明
- **挑战解决**：讨论主要挑战和解决方案

#### 4. 提交历史 ⭐⭐⭐
- **提交消息**：清晰、有意义的提交说明
- **提交频率**：频繁且有规律的提交
- **分支管理**：清晰的分支合并记录

#### 5. 部署演示 ⭐⭐⭐⭐
- **测试网部署**：部署到 Sepolia 等公共测试网
- **合约验证**：在 Etherscan 上验证合约代码
- **交互演示**：提供交互脚本和说明

---

## 📚 学习资源汇总

### 权威文档
| 类型 | 资源 | 链接 | 说明 |
|------|------|------|------|
| **Solidity** | 官方文档 | [docs.soliditylang.org](https://docs.soliditylang.org/) | 最权威的语言参考 |
| **EVM** | 黄皮书 | [ethereum.github.io/yellowpaper](https://ethereum.github.io/yellowpaper/Paper.pdf) | 协议正式定义 |
| **以太坊** | 官方文档 | [ethereum.org/developers](https://ethereum.org/zh-cn/developers/docs/) | EVM 和智能合约概述 |
| **ERC-20** | 标准定义 | [EIP-20](https://eips.ethereum.org/EIPS/eip-20) | 代币标准基础 |

### 协议白皮书
| 协议 | 文档 | 链接 | 核心概念 |
|------|------|------|----------|
| **Uniswap V2** | 白皮书 | [uniswap.org/whitepaper](https://uniswap.org/whitepaper.pdf) | AMM 机制 (x*y=k) |
| **Perpetual Protocol** | v1 白皮书 | [docs.perp.fi](https://docs.perp.fi/v/v1-docs/learn/whitepaper) | Virtual AMM 概念 |
| **GMX** | 文档 | [gmx.io/docs](https://gmx.io/docs/gmx-overview/overview) | 流动性提供者模式 |
| **dYdX** | 白皮书 | [trade.dydx.exchange/whitepaper](https://trade.dydx.exchange/whitepaper) | 订单簿模型与清算 |

### 开源代码库
| 项目 | 仓库 | 链接 | 用途 |
|------|------|------|------|
| **OpenZeppelin** | Contracts | [github.com/OpenZeppelin](https://github.com/OpenZeppelin/openzeppelin-contracts) | 标准合约实现 |
| **Uniswap V2** | Core | [github.com/Uniswap/v2-core](https://github.com/Uniswap/v2-core) | AMM 参考实现 |
| **Perpetual Protocol** | v1 Contracts | [github.com/perpetual-protocol](https://github.com/perpetual-protocol/perp-v1-contract) | vAMM 实现参考 |
| **dYdX** | Solo Margin | [github.com/dydxprotocol/solo](https://github.com/dydxprotocol/solo) | 清算逻辑参考 |
| **GMX** | Contracts | [github.com/gmx-io/gmx-contracts](https://github.com/gmx-io/gmx-contracts) | 仓位管理参考 |

### 开发工具
| 工具 | 文档 | 链接 | 特点 |
|------|------|------|------|
| **Foundry** | Book | [book.getfoundry.sh](https://book.getfoundry.sh/) | 高效测试和部署 |
| **Hardhat** | 文档 | [hardhat.org](https://hardhat.org/) | 全面开发体验 |
| **Scaffold-ETH** | 2 | [github.com/scaffold-eth](https://github.com/scaffold-eth/scaffold-eth-2) | 全栈开发模板 |

### 学习课程
| 课程 | 链接 | 特点 |
|------|------|------|
| **CryptoZombies** | [cryptozombies.io](https://cryptozombies.io/) | 游戏化 Solidity 学习 |
| **Cyfrin Updraft** | [cyfrin.io/updraft](https://www.cyfrin.io/updraft) | 免费综合课程 |

---

## ⚠️ 重要提示

### 🎯 成功关键因素

1. **严格控制范围**：严格遵守"简化版"功能范围，不被额外功能诱惑
2. **测试驱动开发**：先写测试，再写代码，确保接口设计和代码正确性
3. **寻求反馈**：邀请有经验开发者审阅代码和设计
4. **保持健康**：400小时高强度任务需要适当休息，保持身心健康

### 🚨 风险控制

1. **时间管理**：建议将 400 小时调整为 600-800 小时（15-20周）
2. **里程碑检查**：每周设置小目标验证进度
3. **安全审计**：第6周邀请有经验开发者进行代码审查
4. **备选方案**：准备功能降级策略，确保核心功能完整

### 💡 最佳实践

- 使用标准库（OpenZeppelin）处理安全模式
- 遵循 Solidity 风格指南
- 进行模糊测试探索边界条件
- 阅读知名 DeFi 协议的审计报告
- 保持清晰的 Git 提交历史

---
