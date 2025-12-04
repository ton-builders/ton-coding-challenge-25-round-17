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
1. 你的 Telegram 用户名 = @screenshot1021
2. 你的主网 TON 钱包地址 = UQCM7ba6FjN_e6NZNxTGoE6dygQtoPBLVGZ4QgJbYGihcggW


## 任务：Cocoon 合约分析
### 任务描述：

https://github.com/TelegramMessenger/cocoon-contracts/tree/main/contracts_tolk

1. 分析 cocoon-contracts 仓库中的 contracts_tolk 目录中的合约
2. 找出其中 Tolk 代码中可以优化的地方
3. 如果能找出代码中潜在的 bug 或者风险点是加分项

### 你的答案：
https://github.com/TelegramMessenger/cocoon-contracts/blob/9f712572e889a0aac148159b0a5a89108594c760/contracts_tolk/cocoon_proxy.tolk#L102 
```
    val params = self.params.load(); // 解包
    val workerParams = params.withoutCode(); // 置部分值为 null

    val calculatedWorkerAddress = calculateContractAddress(
        params.workerScCode!,
        WorkerStorage {
            ownerAddress: msg.ownerAddress,
            proxyAddress: contract.getAddress(),
            proxyPublicKey: self.proxyPublicKey,
            state: worker_state_normal,
            tokens: 0,
            params: workerParams.toCell(), // 重新打包 cell
        }.toCell()
    );
```
这里可以把需要置为 null 的部分， 和不需要动的部分，分为两个 cell。 这样可以节省这部分工作。
涉及到 params.withoutCode() 都可以这样调整







