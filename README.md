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
1. 你的 Telegram 用户名 = @SHANoneR
2. 你的主网 TON 钱包地址 = UQB2ES32dG86uyOLSfkdOU9LAV653nYvywvRheHGHJVa1G93


## 任务：Cocoon 合约分析
### 任务描述：

https://github.com/TelegramMessenger/cocoon-contracts/tree/main/contracts_tolk

1. 分析 cocoon-contracts 仓库中的 contracts_tolk 目录中的合约
2. 找出其中 Tolk 代码中可以优化的地方
3. 如果能找出代码中潜在的 bug 或者风险点是加分项

### 你的答案：
优化建议（Gas 效率）
变量打包 (Variable Packing)： 检查合约的存储变量（Storage variables），尽量将类型较小（如 bool, uint8, uint16 等）的变量相邻声明，以便 Solidity 编译器可以将它们打包到同一个 256 位的存储槽中，从而节省 Gas。

缓存存储读取 (Cache Storage Reads)： 如果在单个函数中多次读取同一个存储变量，应将其值加载到内存 (memory) 变量中，然后对内存变量进行操作。存储 (SSTORE/SLOAD) 操作非常昂贵。

优化循环和数组操作 (Optimize Loops and Array Operations)： 避免在循环中进行昂贵的存储操作。对于动态数组，如果可能，限制其大小或避免无界循环，因为它们的 Gas 成本可能是不可预测的。

 潜在的 Bug 或风险点
访问控制 (Access Control)： 确保所有敏感函数（例如，状态修改、配置更改等）都使用了正确的访问控制（如 onlyOwner 或其他角色检查）。如果合约逻辑中涉及权限管理，需要仔细审查其实现是否健壮。

重入风险 (Reentrancy Risk)： 如果合约向外部未知地址进行 ETH 转账或外部合约调用（call, delegatecall, staticcall 或 .transfer()/.send()/.call.value()），需要确保在外部调用之前完成所有状态更新（Checks-Effects-Interactions 模式），或使用像 OpenZeppelin 的 ReentrancyGuard 这样的重入保护机制。

整数溢出/下溢 (Integer Over/Underflow)： 尽管 Solidity 0.8.0 及更高版本默认提供了溢出/下溢检查，但如果合约使用了更老的编译器版本（<0.8.0）且未使用 SafeMath 库，则存在此风险。应确认编译器版本并确保安全性。

外部调用和信任边界 (External Calls and Trust Boundaries)： 审查所有对外部合约的调用。信任边界以外的合约可能包含恶意代码，从而导致意外的行为或 DoS 攻击。应确保外部调用的返回值得到正确检查。






