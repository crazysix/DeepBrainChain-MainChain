If you want to read the English version, click [here](README_EN.md)

# 如何参与DBC深脑链

如果你有一些DBC，并想获取更多，你可以选择**成为一个`验证人`**，这需要7*24小时运行一个节点。如果你不想运行节点，但仍想获取收益，你可以通过 **提名`验证人`** 来获取收益。

+ `验证人(Validator)`：验证人需要维护全节点，主要负责验证交易并依据共识生成区块。
+ `提名人(Nominator)`： 提名人需要质押`DBC`并提名`验证人`，这样有可能推举出网络中的`验证人`，并与`验证人`共享挖矿的收益，同时也会承担验证人被惩罚时带来的DBC的损失。

## 指南

#### 区块时间
  + 出块时间：6 seconds
  + Epoch duration：1 hour
  + Era duration：6 hours (一个选举周期，也是奖励计算周期)
+ 第n-1个Era选举（选举间隔1个Era）会产生新的一组Validator，负责n+1个Era出块。

#### 总奖励数量：

+ [0～3)年：每年 10^9 DBC
+ [3~8)年: 每年 0.5 * 10^9 DBC
+ [8, 8+)年：每年 0.5 * (2.5 * 10^9 + DBC_from_renter) / 5 DBC

#### 奖励规则：

+ 每个区块生成后，将记录区块生产者获得的奖励到的`ErasRewardPoints`，`EraRewardPoints`增加规则为：
  + 主链区块生产者增加20点reward
  + 叔区块生产者增加2点reward
  + 引用叔区块的生产者增加1点reward

+ 验证人在相同的工作中获得相同数量的奖励

+ **奖励保留时间**：**84 era (21天)**，超过保留时间的奖励将不会被记录。 任何人都可以去发Payout的交易来领取奖励 (即使没有参与质押)，所有人都能获得奖励。

+ **验证人奖励** = 总奖励 * 自定义比例的分佣 + 生于部分的奖励 * 验证人stake占节点的比例

+ **提名人奖励**：**按stake数量排名前128名才能获得奖励。**`奖励数量 =（节点总奖励 - 验证人自定义比例分佣 ）* 占节点总stake比例`


#### 如何成为`提名人`

[质押DBC成为提名人](docs/staking_dbc_and_voting.md) -- 质押DBC，成为提名人获取收益


#### 如何成为`验证人`

[如何成为DBC验证人](docs/join_dbc_testnet.md) -- 运行验证节点，成为验证人获取收益


