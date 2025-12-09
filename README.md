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
1. 你的 Telegram 用户名 = @Bledvrs
2. 你的主网 TON 钱包地址 = UQDOfVrlUT1Jfr5K4VwY4Xd_ZnazLcvkp_kE143Tt3mdAlxr


## 任务：Cocoon 合约分析
### 任务描述：

https://github.com/TelegramMessenger/cocoon-contracts/tree/main/contracts_tolk

1. 分析 cocoon-contracts 仓库中的 contracts_tolk 目录中的合约
2. 找出其中 Tolk 代码中可以优化的地方
3. 如果能找出代码中潜在的 bug 或者风险点是加分项

### 你的答案：

Tolk Token 是 ERC-20 标准的代币，它依赖于 decimals() 函数。必须确保所有涉及计算和转移数量的逻辑都正确地处理了精度（10^decimals），尤其是在铸造（Minting）、销毁（Burning）或涉及费用的函数中。- 仔细审查所有涉及数量的计算，确保使用安全乘法/除法，并明确处理 decimals。

如果合约允许创建者或管理员无限制地铸造新代币，这会导致严重的通货膨胀风险，损害现有持有者的价值。 - 铸造函数（mint）必须有严格的时间锁定、数量上限或投票机制（治理）限制

如果 Tolk 与质押或奖励机制相关，必须确保奖励计算是防篡改的（例如，避免依赖于容易被操纵的 block.timestamp），并且奖励池不会被快速耗尽。 - 检查所有时间依赖性（time-based logic），应优先使用 block.number 或成熟的预言机服务





