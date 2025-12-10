# TON Coding Challenge 2025 Round 17

> 时间：2025/12/04 - 2025/12/12

为了帮助大家快速掌握 TON 生态的开发技能，我们特别设计了有趣的编程入门挑战赛。快来参与并有机会赢取 Telegram Premium 大会员！详细的比赛规则请查看群组公告。

https://t.me/toneachat

> 如何参与？
>
> Fork 本仓库的代码，回答下面的问题，然后发起一个 Pull Requests 就算成功参与。

---

课件地址：https://ton-org.notion.site/Cocoon-2bd5274bd2cf80cbadcac29208639b0f

领奖信息收集：
1. 你的 Telegram 用户名 = @big_big_fish1011
2. 你的主网 TON 钱包地址 = UQAq_FBCWCGufLvxQY_ivhogT8TeC16VwYQtPHXlUK80vjSv


## 任务：Cocoon 合约分析
### 任务描述：

https://github.com/TelegramMessenger/cocoon-contracts/tree/main/contracts_tolk

1. 分析 cocoon-contracts 仓库中的 contracts_tolk 目录中的合约
2. 找出其中 Tolk 代码中可以优化的地方
3. 如果能找出代码中潜在的 bug 或者风险点是加分项

### 你的答案：


链下计算与链上验证的分离（Off-Chain Proof）： 对于复杂的算力评估、奖励比例计算等业务逻辑，我们将其移至链下执行。合约仅负责验证由授权 Cocoon 核心服务提供的 加密签名证明（Signed Proof） 的有效性，并根据验证结果执行代币转移。这种模式确保了激励机制的复杂性不会导致链上 Gas 消耗失控。

资产管理采用 Pull-based 模式： 对于 Worker 质押的 Tolk 代币或已结算的奖励，我们采用 “拉取 (Pull)” 模式。Worker 必须在冷却期结束后主动发送交易来申领（Claim）资金。这种设计避免了合约维护昂贵的推送调度列表，简化了状态并提高了效率。




