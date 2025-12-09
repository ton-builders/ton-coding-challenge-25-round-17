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
1. 你的 Telegram 用户名 = @kooal111
2. 你的主网 TON 钱包地址 = UQAjKYAsbCbskV_DlGpaQtPpBv78Bo0iITVtAlvD1IU01kDa

## 任务：Cocoon 合约分析
### 任务描述：

https://github.com/TelegramMessenger/cocoon-contracts/tree/main/contracts_tolk

1. 分析 cocoon-contracts 仓库中的 contracts_tolk 目录中的合约
2. 找出其中 Tolk 代码中可以优化的地方
3. 如果能找出代码中潜在的 bug 或者风险点是加分项

### 你的答案：

单点故障 (Single Point of Failure - SPOF)	如果所有关键权限（如升级、停止合约、铸造）都集中在一个 owner 地址上，一旦该私钥丢失或被盗，将导致灾难性后果。	考虑使用多重签名钱包 (Multi-sig) 来管理 Owner 地址，或使用 DAO 治理模式分配权限。
功能暂停/开关 (Pause/Emergency Stop)	如果合约包含 pause 或 stop 功能以应对紧急情况，必须确保其触发机制和恢复机制设计合理且安全。暂停功能必须只能被授权方触发。	确保暂停状态下的资金安全，并且恢复流程清晰可靠，避免永久性锁定资产。





