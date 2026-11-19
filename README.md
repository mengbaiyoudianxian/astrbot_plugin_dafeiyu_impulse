# 大肥鱼的念头

> `astrbot_plugin_dafeiyu_impulse` · v0.1.0 · [大肥鱼](https://github.com/mengbaiyoudianxian/dafeiyu) 的自写插件之一

像人一样突然想做点什么：找主人聊天、群里冒泡、@群友、找好友、刷B站、逛贴吧、看看并修改自己的资料；能看到自己 QQ/B站/贴吧 的头像和 ID

## 安装

AstrBot（4.x）后台 → 插件 → 右上角「+」→ 从链接安装，填：

```
https://github.com/mengbaiyoudianxian/astrbot_plugin_dafeiyu_impulse
```

装完在插件列表里点开它的配置，按需改。平台目前只适配 aiocqhttp（NapCat / OneBot v11）。

## 怎么用

管理员 /念头 让她马上冒一个念头（/念头 群、/念头 主人、/念头 资料 …）；后台「大肥鱼控制中心」页：QQ 登录二维码、音乐账号登录、念头记录、表情包、插件推荐都在这一页

## 搭配

这个插件会读写下面这些大肥鱼插件的数据，单独装也能跑，但相关功能会少一块：

- [`astrbot_plugin_dafeiyu_heart`](https://github.com/mengbaiyoudianxian/astrbot_plugin_dafeiyu_heart)
- [`astrbot_plugin_dafeiyu_memesearch`](https://github.com/mengbaiyoudianxian/astrbot_plugin_dafeiyu_memesearch)
- [`astrbot_plugin_dafeiyu_pluginscout`](https://github.com/mengbaiyoudianxian/astrbot_plugin_dafeiyu_pluginscout)
- [`astrbot_plugin_dafeiyu_sing`](https://github.com/mengbaiyoudianxian/astrbot_plugin_dafeiyu_sing)
- [`astrbot_plugin_dafeiyu_tieba`](https://github.com/mengbaiyoudianxian/astrbot_plugin_dafeiyu_tieba)
- [`astrbot_plugin_dafeiyu_x`](https://github.com/mengbaiyoudianxian/astrbot_plugin_dafeiyu_x)

## 配置项

| 键 | 说明 | 提示 |
|---|---|---|
| `enable` | 开启随机念头 | 每隔一段随机时间，她会突然想做点什么：找你聊天、去群里冒泡、@群友、找好友、刷B站、逛贴吧、看看自己的资料 |
| `interval_min` | 两次念头最短间隔（分钟） |  |
| `interval_max` | 两次念头最长间隔（分钟） |  |
| `quiet_hours` | 免打扰时段 | 这段时间她在睡觉，不会冒念头。比如 1-8 就是凌晨 1 点到早上 8 点 |
| `w_owner` | 权重：找主人聊天 | 权重越大越容易抽到，0 就是永远不抽 |
| `w_group` | 权重：去群里冒泡 |  |
| `w_at` | 权重：@一个群友 |  |
| `w_friend` | 权重：找QQ好友聊天 |  |
| `w_bili` | 权重：刷B站 |  |
| `w_tieba` | 权重：逛贴吧 |  |
| `w_profile` | 权重：看看自己的资料（可能顺手改） |  |
| `w_idle` | 权重：发会儿呆（什么都不做） |  |
| `cap_owner` | 每天最多主动找主人几次（没回的才算） | 主人回了的那次不占名额，一直有回应就不限 |
| `cap_group` | 每天最多去群里冒泡几次（所有群加起来） | 没人接话的才算次数，有人接话的不占名额 |
| `cap_at` | 每天最多 @ 群友几次（没回的才算） |  |
| `cap_friend` | 每天最多主动找好友几次（没回的才算） |  |
| `cap_bili` | 每天最多因为念头去刷B站几次 | 不算B站插件自己排的时间 |
| `cap_tieba` | 每天最多因为念头去逛贴吧几次 | 不算贴吧插件自己排的时间 |
| `cap_profile` | 每天最多看几次自己的资料 |  |
| `per_group_daily` | 同一个群每天最多被她主动找几次（没人接话的才算） |  |
| `group_cooldown_hours` | 同一个群两次主动之间至少隔几小时 | 上次有人接话就不用等 |
| `friend_cooldown_hours` | 同一个好友两次主动之间至少隔几小时 | 上次对方回了就不用等 |
| `at_cooldown_hours` | 同一个人两次被 @ 之间至少隔几小时 | 上次对方回了就不用等 |
| `only_groups` | 只在这些群里主动（群号） | 留空就是她在的所有群 |
| `exclude_groups` | 这些群永远不主动（群号） |  |
| `balance_check_minutes` | 多久查一次 DeepSeek 余额（分钟） | 用 API Key 查，不用登录账号，不花钱 |
| `balance_low` | 余额低于多少开始找主人要（元） |  |
| `balance_critical` | 余额低于多少算快没了（元） |  |
| `ask_owner_for_money` | 钱不够了主动找主人要 | 会附上 DeepSeek 充值页二维码；免打扰时段不发 |
| `ask_gap_low_hours` | 不太够时隔几小时要一次 |  |
| `ask_gap_critical_hours` | 快没了时隔几小时要一次 |  |
| `inject_balance` | 聊天时让她知道自己还剩多少钱 |  |
| `voice_tempo` | 语音语速倍数 | 1 是原速，小于 1 变慢（不变调），比如 0.88 |
| `voice_pad_seconds` | 语音前后各留几秒空白 |  |
| `voice_max_chars` | 超过多少字的回复不转语音 | 带链接的回复也不转语音，直接发文字 |
| `notify_owner_on_change` | 改资料后私聊告诉主人 |  |
| `inject_self` | 聊天时告诉她自己在各平台叫什么 |  |
| `owner_umo` | 主人的会话 ID | 留空就用 B 站插件的 OWNER_QQ_UMO |
| `platform_id` | QQ 平台名 |  |
| `persona_id` | 人格名（取不到默认人格时用） |  |
| `provider_id` | 念头用哪个模型 | 留空用她平时聊天的模型 |
| `human_pace` | 像人一样回消息（按日程决定多久回，连发的消息合在一起回） |  |
| `max_reply_delay` | 最多晚多少秒回 | 睡觉/上课时会晚回，这里是上限 |
| `interruptible` | 分段说话时对方插话就停下先回 |  |
| `group_stale_seconds` | 群消息过去多少秒就不回了 | 掉线重连后不去回几个小时前的消息 |

## 许可

[大肥鱼 非商业许可协议 v1.0](LICENSE)：可以看、可以自己用、可以改，**不得商用**——不得收费代部署 / 代托管 / 做成 SaaS，不得改成别家 Agent 或产品卖。整套部署方法见 [大肥鱼主仓库](https://github.com/mengbaiyoudianxian/dafeiyu)。
