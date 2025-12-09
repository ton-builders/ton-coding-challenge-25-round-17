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
1. 你的 Telegram 用户名 = UQBGvuZjAitfIxWD4UTPfNdJekRZiSD7u2mbZhYMARsu9F29
2. 你的主网 TON 钱包地址 = @Vk5035


## 任务：Cocoon 合约分析
### 任务描述：

https://github.com/TelegramMessenger/cocoon-contracts/tree/main/contracts_tolk

1. 分析 cocoon-contracts 仓库中的 contracts_tolk 目录中的合约
2. 找出其中 Tolk 代码中可以优化的地方
3. 如果能找出代码中潜在的 bug 或者风险点是加分项

### 你的答案：
消息转发和 Gas 费 (Message Forwarding & Gas Fees): TON 合约需要负责支付出站消息 (outbound messages) 的 Gas 费用。如果合约未能正确计算或保留足够的 TON Coin 来支付未来的消息费用，可能会导致合约“卡住”（无法发送后续消息）。

内部消息身份验证： 必须确保所有内部消息的发送者身份验证是正确的（例如，确保消息来自预期的钱包地址或父合约地址）。TON 合约依赖消息的来源和内容来执行逻辑。

持久化存储限制： TON 合约的存储在单个 cell 中，对其大小和结构有严格的限制。复杂的状态更新可能会因为 cell 操作的复杂度而变得昂贵或难以管理






