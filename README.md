# TON Coding Challenge 2025 Round 17

> 时间：2025/12/04 - 2025/12/12

为了帮助大家快速掌握 TON 生态的开发技能，我们特别设计了有趣的编程入门挑战赛。快来参与并有机会赢取 Telegram Premium 大会员！详细的比赛规则请查看群组公告。

https://t.me/toneachat

> 如何参与？
>
> Fork 本仓库的代码，回答下面的问题，然后发起一个 Pull Requests 就算成功参与。

---

课件地址：https://ton-org.notion.site/Cocoon-2bd5274bd2cf80cbadcac29208639b0f

1. 你的 Telegram 用户名 = @nft_patrick
2. 你的主网 TON 钱包地址 = UQBKXFMtekdp2Mu0P_PnYdYU3GtsFlj15wdv4eLHI0Av2mD6


## 任务：Cocoon 合约分析
### 任务描述：

https://github.com/TelegramMessenger/cocoon-contracts/tree/main/contracts_tolk

1. 分析 cocoon-contracts 仓库中的 contracts_tolk 目录中的合约
2. 找出其中 Tolk 代码中可以优化的地方
3. 如果能找出代码中潜在的 bug 或者风险点是加分项

### 你的答案：
我们观察到，Tolk 的优势在于其强大的静态类型系统。优化应侧重于最大化利用这一特性。建议对所有关键输入参数和状态变量进行显式类型断言，而不是依赖 FunC 的隐式类型转换，这能有效在编译阶段捕获错误，并可能生成更优化的 TVM 字节码。对于代币余额和时间戳等涉及算术操作的变量，必须确保使用 Tolk 提供的安全数学原语，或手动实施溢出/下溢检查。

关键风险与 Bug 预测：
最大的潜在风险来源于 TON 运行时环境的异步特性与合约的资金管理。如果合约逻辑涉及复杂的循环或字典（Dict）遍历，必须对其进行 Gas 成本分析。如果循环次数不可预测，极有可能导致 Gas 耗尽（Out-of-Gas），进而引发交易失败和 Bounced 消息。此外，如果合约的消息发送模式（Mode） 设置不当，例如在发送资金时未使用 mode 64（包含全部剩余余额），可能导致合约本身无法保留足够的 TON 来支付未来的存储和网络费用，最终导致合约进入不可操作的冻结状态。






