<h1 align="center">道氏理论 Skill</h1>

<p align="center">中文 | <a href="README.en.md">English</a></p>

一套可直接使用的 AI skill 工具包——把罗伯特·雷亚《道氏理论（专业解读版）》中的指数判读方法，蒸馏成 13 张可单独触发、也可组合调用的能力卡。

它不是原书摘要，也不是读后感，而是把书中可复用的方法论拆成可触发、可执行、可测试的 skill 模块。

## 这套 skills 能解决什么问题

- 一条指数创了新高，另一条没跟上——这个信号该采信、该等，还是该按假象忽略，三种情况对应三种完全不同的动作
- 这波下跌是"最具欺骗性"的次级运动，还是主要趋势已经反转？次级运动通常回撤前一主要运动的 33%~66%、速度快于主要运动，把它当反转是亏损主因
- 现在是牛市的第几阶段、熊市走到哪一步，对应该激进还是该保守
- 熊市跌了很久，利空不断但指数不跌了，到底能不能抄底；反过来，是不是见顶了、该不该减仓清仓——这两件事是两套清单，阈值不能互借
- 量价配不配合、是不是超买超卖；以及"主力砸盘""双顶成立了""重大消息出来了"这类说法该不该跟
- 止损放哪、仓位多重才睡得着、要不要摊平加码、一年赚多少算现实

## 蒸馏了什么

13 张能力卡，按"先定方向、再定位置、再验证据、最后落到执行"的顺序组织：

- **趋势与结构判定**：`primary-trend-identification-skill`（主要趋势判定：高低点阶梯＋3% 净逆转＋牛熊反转判据）、`dual-index-confirmation-filter-skill`（双指数相互确认过滤器：未确认信号＝假象）、`secondary-reaction-assessment-skill`（次级运动识别与幅度评估：33%~66%＋速度不对称＋完成序列）、`line-formation-reading-skill`（线态窄幅盘整判读：吸筹 / 派发推断与突破方向）
- **牛熊位置与顶底**：`bull-bear-stage-positioning-skill`（牛熊三阶段定位器：按驱动锚定位并校准风险态度）、`bear-bottom-checklist-skill`（熊市底部特征核查清单：图 1 九次熊市统计画像）、`bull-top-exit-signals-skill`（牛市顶部信号分级与清仓决策：1929 年 9—10 月标本）
- **证据与伪信号**：`volume-price-health-skill`（量价关系健康度评估：超买超卖与沉闷 / 活跃语义）、`pseudo-signal-troubleshooting-skill`（伪信号与归因排查：前提门槛＋反模式清单）
- **执行、统计与训练**：`stock-preflight-market-check-skill`（个股操作的大盘趋势前置检查：防呆闸门）、`trading-discipline-rules-skill`（交易纪律与资金管理原则包：止损 / 仓位 / 加码方向 / 收益预期）、`secondary-reaction-stat-baseline-skill`（次级反应统计基准与数据基建：35 年分布预期＋记录模板＋除数法）、`forecast-self-training-skill`（预测自检训练法：盖图预测—对照汉密尔顿评论—归因差异）

## 两种打包模式：single 与 pack

同一套 13 张能力卡，按两种粒度各编译了一次。两者内容完全相同，区别只在"agent 能看到几个入口"。

| | single（单一入口） | pack（compact pack，多入口） |
|---|---|---|
| 可发现入口 | **1 个**：`dow-theory-skill` | **8 个**：1 个来源路由入口 + 7 个已晋级独立 skill |
| 13 张能力卡放在哪 | 全部在入口的 `references/capabilities/` 里，由入口按路由表按需加载 1–2 张 | 7 张高频卡各自独立成 skill；其余 6 张仍在 router 的 `references/` 里 |
| 触发方式 | 只有入口的 description 参与匹配，进入后靠路由表分流 | 7 个高频能力可被 description 直接命中，少一跳 |
| 升级维护 | 替换 1 个目录 | 替换 8 个目录 |

pack 里被晋级为独立 skill 的 7 张卡：

- `primary-trend-identification-skill` — 主要趋势判定（高低点阶梯＋3% 净逆转＋牛熊反转判据）
- `dual-index-confirmation-filter-skill` — 双指数相互确认过滤器
- `secondary-reaction-assessment-skill` — 次级运动识别与幅度评估
- `line-formation-reading-skill` — 线态窄幅盘整判读
- `bear-bottom-checklist-skill` — 熊市底部特征核查清单
- `bull-top-exit-signals-skill` — 牛市顶部信号分级与清仓决策
- `trading-discipline-rules-skill` — 交易纪律与资金管理原则包

留在 router 里、由 router 直接承接的 6 张：`volume-price-health-skill`、`bull-bear-stage-positioning-skill`、`stock-preflight-market-check-skill`、`secondary-reaction-stat-baseline-skill`、`forecast-self-training-skill`、`pseudo-signal-troubleshooting-skill`。

### 该装哪一种

按你的工作方式选，**只装一种**：

| 你的工作方式 | 推荐 | 原因 |
|---|---|---|
| 用 DSH / Codex / Claude Code 等有 skills 目录，希望列表干净 | single | 只占 1 个入口，能力一张不少 |
| 日常问题高度集中在"现在牛还是熊 / 这个新高可信吗 / 这波回调多深 / 是不是底部 / 该清仓吗 / 止损放哪" | pack | 这 7 类正是被晋级的独立 skill，能直接命中 |
| 要分发给多个 agent 或团队，各自按需取用 | pack | 可以只装其中几个独立 skill，不必整包 |
| 只想装一次、不想维护多个目录 | single | 升级时只替换 1 个目录 |

> 两版由同一个 Bundle 编译，能力内容一致。**同时安装会重复触发**，请只装一种。

## 效果示例

### 示例 1：一条指数创新高，另一条没跟上

**用户问题**

"上证今天创了年内新高，深证没跟上来。这算有效突破吗？能不能加仓？"

**skill 如何判断**

- 先过 `dual-index-confirmation-filter-skill` 的数据质量门槛：判读之前先剔除公司行为造成的机械位移（分红除息、拆股、成分调整），再检查这对指数有没有被单一政策变量或个别股票主导。书里的标本很具体：1926 年 9 月那一周工业指数表面下跌 3.19 点，看起来是真实卖压，但通用汽车除息使指数机械下移 3.35 点，跌幅全部（且不止）来自机械位移，实际没有卖压
- 再做三态判定：深证已同方向跟进＝"已确认"；暂未跟进＝"等待确认"，此时唯一正确的动作是写下"深证做到什么才算确认"然后等；始终未确认＝"按假象忽略"归档。确认不必在同一天，甚至不必在同一周
- 消极保险规则：只有一条指数给出指示时，按"无信号"处理——不入场，也不反向做空。"一半的预示不比完全没有好"
- 如果结论要升级成"趋势反转"，还得转 `primary-trend-identification-skill` 走完整判据：牛转熊＝合理时间内不创新高＋双指数跌破前期次级低点；单指数破位只算警告，不算改判

**最终回答示例**

> 先别把它叫突破。这道过滤器的输出只有三态：已确认、等待确认、按假象忽略。你现在是第二态——深证还没跟进，正确的动作不是加仓，而是写下确认条件（深证要越过哪个点位或区间）然后等。等多久书里没给量化规则，确认时间窗口原文没有数字，只能按次级运动"3 周至数月"的统计口径自己设观察期，并把这个观察期明确写成约定，别事后改口。另外先自查一件事：这几天有没有大额分红除息或指数调样？书里 1926 年 9 月那周 3.19 点的"跌幅"全部来自通用汽车除息的 3.35 点机械下移，不是卖压。还有一层要说明：书里的双指数是道琼斯工业＋铁路，A 股没有对应物，"上证＋深证"这类替代组合在原文里只是译者的类比线索，不是雷亚的规则，也没做过联动性检验——所以这个结论请带上"替代指数对未经检验"的声明。如果之后要把它升级成"趋势反转"，那要另走一遍反转判据：双指数都跌破前期次级低点才算，单指数破位只是警告。

### 示例 2：跌了一年、利空不断，能不能抄底

**用户问题**

"大盘从高点跌了快一年，最近利空一个接一个，但指数好像不怎么跌了，成交量也缩下来了。是不是可以抄底了？"

**skill 如何判断**

- 进 `bear-bottom-checklist-skill`，按图 1 的九次熊市统计画像逐项勾检：谷底区持续 60~90 天且指数振幅在 3% 之内（9 次里 7 次，另 2 次接近 5%）；最低点前数月成交量已渐降（9 次里 6 次，另 3 次量能信号失效——只看量会误判）；对坏消息免疫、市场沉闷、悲观肆虐；谷底以线态窄幅盘整呈现并被明显向上突破、反弹低点逐级抬高
- 反向排除：双重底不作为判断指标。9 次熊市里 3 次仅单指数双底、3 次双指数双底、3 次完全没有——"双底＝见底"不成立
- 确认判据（熊转牛）：不再创新低＋双指数反弹越过上次重大反弹的高点；安全买点＝大涨后的巨幅反应不破熊市近期低点＋二次反弹上穿前次反弹高点
- 汇总：七项齐备才升"底部概率高＋做多时机确认"；任一缺省，结论固定为"降级观察"，禁止输出"可以抄底"

**最终回答示例**

> 你的两条论据只命中了清单里的两项，还不足以下"可以抄底"的结论。先把谷底区的两个数字量出来：持续了多少天、振幅是多少——书里 9 次熊市有 7 次是谷底区持续 60~90 天、振幅收在 3% 以内，另 2 次接近 5%，超出就要在结论里降权并注明。量能缩下来这条，9 次里只有 6 次成立，另 3 次量能信号是失效的，所以它只能当第二位证据，不能单独支撑抄底。然后逐条对照利空：是"利空还在但指数拒绝创新低"（这才叫利空钝化），还是利空刚出来、指数还在往下走。最后看确认判据：不再创新低＋双指数反弹越过上次重大反弹的高点，两条都达成才算熊转牛；任一没达成就只能是"降级观察"，不能输出"可以抄底"。两个预期要先接受：能在价格离开低点 10% 以内买到算走运，涨到 20% 之前趋势变化对熟悉这套方法的人已经显而易见——底部确认天然滞后。还要说清楚边界：图 1 的样本只有 1897—1923 年的 9 次美股熊市，没有权重打分、没有样本外检验，60~90 天与 3% 这些参数是基于旧点位与旧波动率定的，迁移到 A 股必须重估；书里也没有对底部信号做过命中率统计，这是概率语言，不是保证。

## 这些 skill 是怎么生成出来的

这套 skill 使用 **[cangjie-skill](https://github.com/kangarooking/cangjie-skill)** 的 RIA-TV++ 流水线生成，整个流程分六个阶段：

1. **整书理解（Adler 分析）**——用 Mortimer Adler 的分析阅读法，对全书做结构、解释、批判、应用四步拆解
2. **并行提取**——同时派多个专项提取器（框架、原则、案例、反例、术语），从原文中提取候选方法论单元
3. **三重验证筛选**——每个候选必须通过三项检验：书内至少有 2 处独立佐证（跨域）、能回答书中未明说的新问题（预测力）、不是常识（独特性）
4. **RIA++ 构造**——按 R（原文引用）/ I（用自己的话重写）/ A1（书中案例）/ A2（未来触发场景）/ E（可执行步骤）/ B（边界与盲点）六个维度结构化
5. **Zettelkasten 链接**——找出能力卡之间的依赖、对比、组合关系，生成能力索引与路由表
6. **触发与输出测试**——为每张卡设计触发场景与输出评测，逐项核对触发条件、边界与判停行为，发现问题的卡回炉重做

本书的结构也影响蒸馏：上篇雷亚正文（第 1—19 章）是理论主轴；夹嵌的 6 处"专业解析"节是中文版对 A 股语境的适配解读，只能当适配线索、不能升格为雷亚本人的规则；下篇第 20 章是汉密尔顿 1903—1929 年的专栏汇编，作为案例与引证库，同时是"预测自检训练法"的对照材料。每张能力卡的边界段都保留了阶段 0 的批判结论：全部参数基于 1897—1931 年美股，无样本外检验，迁移到 A 股须重新评估。

## 仓库结构

```text
dow-theory-skill/
├── README.md                      ← 你正在看的
├── README.en.md                   ← English version
├── LICENSE                        ← MIT
├── BOOK_OVERVIEW.md               ← 整书理解（Adler 四步拆解，阶段 0 产出）
├── verified.md                    ← 三重验证汇总（174 条 verified 单元）
├── single/                        ← 单一入口模式
│   └── dow-theory-skill/
│       ├── SKILL.md               ← 入口：触发条件 + 路由表 + 加载规则
│       ├── BUILD_MANIFEST.json    ← 编译清单与文件哈希
│       └── references/
│           ├── overview.md        ← 整书概览
│           ├── capability-index.md  ← 完整意图与关键词索引
│           ├── cheatsheet.md      ← 决策规则速查
│           ├── glossary.md        ← 术语表
│           └── capabilities/      ← 13 张能力卡
├── pack/                          ← 多入口模式（compact pack）
│   ├── BUILD_MANIFEST.json
│   ├── capability-destinations.json
│   ├── dow-theory-skill-router/
│   │   ├── SKILL.md               ← 来源路由入口
│   │   └── references/            ← 13 张卡 + 索引，供 router 内部调用
│   ├── primary-trend-identification-skill/
│   │   └── SKILL.md
│   ├── dual-index-confirmation-filter-skill/
│   │   └── SKILL.md
│   ├── secondary-reaction-assessment-skill/
│   │   └── SKILL.md
│   ├── line-formation-reading-skill/
│   │   └── SKILL.md
│   ├── bear-bottom-checklist-skill/
│   │   └── SKILL.md
│   ├── bull-top-exit-signals-skill/
│   │   └── SKILL.md
│   └── trading-discipline-rules-skill/
│       └── SKILL.md
```

## 如何使用

先把仓库克隆下来：

```bash
git clone https://github.com/raphael-y7/dow-theory-skill.git
```

### 装 single（推荐先试这个）

```bash
# macOS / Linux
cp -r dow-theory-skill/single/dow-theory-skill ~/.agents/skills/
```

```powershell
# Windows
Copy-Item -Recurse .\dow-theory-skill\single\dow-theory-skill "$env:USERPROFILE\.agents\skills\"
```

### 装 pack

只复制含 `SKILL.md` 的目录，不要把 `pack/` 下的两个 json 一起拷进 skills 目录：

```bash
# macOS / Linux
cd dow-theory-skill/pack
cp -r dow-theory-skill-router \
      primary-trend-identification-skill \
      dual-index-confirmation-filter-skill \
      secondary-reaction-assessment-skill \
      line-formation-reading-skill \
      bear-bottom-checklist-skill \
      bull-top-exit-signals-skill \
      trading-discipline-rules-skill ~/.agents/skills/
```

```powershell
# Windows
$pack = ".\dow-theory-skill\pack"
$dest = "$env:USERPROFILE\.agents\skills"
@('dow-theory-skill-router','primary-trend-identification-skill','dual-index-confirmation-filter-skill','secondary-reaction-assessment-skill','line-formation-reading-skill','bear-bottom-checklist-skill','bull-top-exit-signals-skill','trading-discipline-rules-skill') |
  ForEach-Object { Copy-Item -Recurse -LiteralPath (Join-Path $pack $_) -Destination $dest }
```

> `~/.agents/skills` 是 DSH 的 skill 目录；用别的 agent 时换成它自己的 skills 目录即可（例如 Claude Code 是 `~/.claude/skills`）。

### 怎么确认装好了

装完问一句"上证创新高了但深证没跟上，这算突破吗"，看 agent 是否直接进入双指数确认的三态判定（已确认 / 等待确认 / 按假象忽略），而不是给你一段泛泛的技术分析。装的是 single 时，它会先读入口再按路由表进能力卡；装的是 pack 时，对应能力会被直接命中。

## 来源

- 《道氏理论》罗伯特·雷亚 著
- 全书蒸馏，共产出 13 张能力卡

## 声明

本仓库只发布蒸馏后的 skill、索引与规则速查材料，不包含原书 PDF、EPUB、OCR 文件、截图或全书转写稿。能力卡中出现的原文引用仅用于标注方法论出处和保持可审计性。

书中所有数字判据（3% 净逆转、33%~66% 回撤区间、5% 线态幅度、60~90 天谷底区、3% 振幅、连续新高计数、止损与仓位口径等）都是案例与经验归纳，原书未提供统计回测背书，且全部参数基于 1897—1931 年美股，迁移到 A 股须自行重估并声明所用口径。本仓库内容不构成投资建议。

## License

[MIT](./LICENSE)

