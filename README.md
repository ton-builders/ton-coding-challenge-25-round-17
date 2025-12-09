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
1. 你的 Telegram 用户名 = @finterov
2. 你的主网 TON 钱包地址 = UQCWFuq6WOIk1XmR3ncaYVYRh1j9WcXAGkzWcNhHq3IKCdGd

## 任务：Cocoon 合约分析
### 任务描述：

https://github.com/TelegramMessenger/cocoon-contracts/tree/main/contracts_tolk

1. 分析 cocoon-contracts 仓库中的 contracts_tolk 目录中的合约
2. 找出其中 Tolk 代码中可以优化的地方
3. 如果能找出代码中潜在的 bug 或者风险点是加分项

### 你的答案：

异步消息的原子性 (Asynchronous Message Atomicity): TON 的交易是基于异步消息传递的。如果一个操作需要发送多个消息或依赖于外部合约的回复，必须设计严谨的状态机或回调机制。如果中间消息失败，可能导致合约处于不一致的中间状态（非原子性风险）。

消息过期和处理顺序 (Message Expiration and Ordering): 消息可以设置过期时间。如果关键的回复消息过期或顺序被打乱，合约逻辑可能会失败。必须设计逻辑来优雅地处理丢失或延迟的消息，例如使用序列号或时间戳进行验证。

Gas 耗尽导致的交易回滚 (Gas Exhaustion Rollback): FunC 合约需要仔细管理其 Gas 消耗，特别是处理复杂的循环或递归结构时。如果一条消息处理的 Gas 耗尽，当前事务会回滚，但已经发送的出站消息可能会丢失，导致整个流程中断。必须保守地估计和分配 Gas。

Writability 检查： 在 TON 中，合约在没有资金的情况下可能无法写入。需要确保合约的可写性 (Writability) 得到保证，即在执行关键的存储写入操作时，合约账户中有足够的 TON Coin 余额来支付存储租金和 Gas





