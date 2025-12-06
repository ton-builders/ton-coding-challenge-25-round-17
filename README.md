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
1. 你的 Telegram 用户名 = @wxrkxrzz
2. 你的主网 TON 钱包地址 = UQDKTP3KR_ZSBiKGrP3pj-FwZ91B09wwvDOA2u8OvXFQuhtj


## 任务：Cocoon 合约分析
### 任务描述：

https://github.com/TelegramMessenger/cocoon-contracts/tree/main/contracts_tolk

1. 分析 cocoon-contracts 仓库中的 contracts_tolk 目录中的合约
2. 找出其中 Tolk 代码中可以优化的地方
3. 如果能找出代码中潜在的 bug 或者风险点是加分项

### 你的答案：
 整数溢出： 检查所有涉及余额、计数或时间戳的加减乘除，必须进行边界检查以防止溢出或下溢。这是最直接的逻辑 Bug 来源。 消息体注入： 对所有来自外部的 slice 数据，进行非详尽性检查。攻击者可能在消息末尾添加额外数据（Padding），若合约未完全消费整个 slice，可能导致数据解析错误或意外状态。代码优化建议：常量化 Op-Codes： 将所有操作码 定义为具名常量，避免在代码中散布魔术数字。Get 方法纯净性： 确保所有查询状态的 get-methods 是 纯净（Pure） 的，不包含任何副作用或状态修改逻辑。地址规范化： 确保在存储和比较地址时，始终使用标准化的格式（例如，统一处理工作链 ID）






