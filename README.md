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
1. 你的 Telegram 用户名 = @dudhhsbshs
2. 你的主网 TON 钱包地址 = UQBicUiXrZqxzPExSjw4UP4a4ltFscS-cX50SeLj4_eZ-4uN


## 任务：Cocoon 合约分析
### 任务描述：

https://github.com/TelegramMessenger/cocoon-contracts/tree/main/contracts_tolk

1. 分析 cocoon-contracts 仓库中的 contracts_tolk 目录中的合约
2. 找出其中 Tolk 代码中可以优化的地方
3. 如果能找出代码中潜在的 bug 或者风险点是加分项

### 你的答案：
主要改进建议：

为所有外部调用增加严格的发送者校验。

加强 TON 转账的 bounce/错误处理。

减少存储写入（仅在值变化时写入）。

限制循环长度，避免 gas DoS。

为关键操作添加事件日志。

增加基础的重入保护，并采用“先更新状态 → 再外部调用”的顺序。

增加测试覆盖，包括失败与 bounce 情况。

潜在风险：未授权调用、未处理的 bounce、大循环 DoS、无效地址、序列化错误。






