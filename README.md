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
1. 你的 Telegram 用户名 = @chargebackoff
2. 你的主网 TON 钱包地址 = UQDkYCBG1mW7nMCJVaCBKd6X66ZzZyiyXUgAKbHkIKlwzYiv


## 任务：Cocoon 合约分析
### 任务描述：

https://github.com/TelegramMessenger/cocoon-contracts/tree/main/contracts_tolk

1. 分析 cocoon-contracts 仓库中的 contracts_tolk 目录中的合约
2. 找出其中 Tolk 代码中可以优化的地方
3. 如果能找出代码中潜在的 bug 或者风险点是加分项

### 你的答案：

1. 高等级 Reentrancy 防御：严格执行 CEI 模式，确保所有状态更新在外部代币转移（Interaction）之前完成。2. Gas 转发安全：强制使用 send_raw_message 配合 mode: 1 或 mode: 64 进行 TON 转发，防止 Gas 估算错误导致资产锁定。3. 去中心化权限：关键参数修改权限必须由 Multi-sig (多签) + Timelock (时间锁) 机制控制，避免单点故障。





