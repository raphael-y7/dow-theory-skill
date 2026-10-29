<h1 align="center">道氏理论 Skill</h1>

<p align="center">中文 | <a href="README.en.md">English</a></p>

一套可直接使用的 AI skill 工具包——把罗伯特·雷亚《道氏理论（专业解读版）》里那套"只看两种平均价格指数的行为就判断股市主要趋势"的方法，蒸馏成 13 张可单独触发、也可组合调用的能力卡。

它不是原书摘要，也不是读后感，而是把书中可复用的方法论拆成可触发、可执行、可测试的 skill 模块。

## 这套 skills 能解决什么问题

- 现在到底是牛市还是熊市？指数创了新高（或新低），是趋势反转还是又一次次级波动
- 一个指数发出了信号、另一个没跟上，这个信号能不能算数——什么情况下"未确认"就该当假象忽略
- 这波回调是次级运动还是趋势反转，一般会跌多深、持续多久
- 指数横着走了两三周，是在吸筹还是派发，会往哪边突破
- 牛市顶部该不该清仓、熊市底部能不能抄底，按什么信号分级减仓
- 大盘走弱时还能不能买个股；止损放哪、要不要摊平、仓位多重、一年赚多少才算现实

## 蒸馏了什么

13 张能力卡，按"先定方向、再验信号、再看形态与位置、最后落到执行"的顺序组织：

- **方向与确认**：`primary-trend-identification`（主要趋势判定：高低点阶梯＋3% 净逆转＋牛熊反转判据）、`dual-index-confirmation-filter`（双指数相互确认过滤器：未确认信号＝假象）
- **运动性质与盘整形态**：`secondary-reaction-assessment`（次级运动识别与幅度评估：33%~66%＋速度不对称＋完成序列）、`line-formation-reading`（线态窄幅盘整判读：吸筹/派发推断与突破方向）、`secondary-reaction-stat-baseline`（次级反应统计基准与数据基建：35 年分布预期＋记录模板＋除数法）
- **位置与阶段**：`bull-bear-stage-positioning`（牛熊三阶段定位器：按驱动锚定位并校准风险态度）、`bear-bottom-checklist`（熊市底部特征核查清单：图 1 九次熊市统计画像）、`bull-top-exit-signals`（牛市顶部信号分级与清仓决策：1929 年 9—10 月标本）
- **量价与伪信号**：`volume-price-health`（量价关系健康度评估：超买超卖与沉闷/活跃语义）、`pseudo-signal-troubleshooting`（伪信号与归因排查：前提门槛＋反模式清单）
- **执行与训练**：`stock-preflight-market-check`（个股操作的大盘趋势前置检查：防呆闸门）、`trading-discipline-rules`（交易纪律与资金管理原则包：止损/仓位/加码方向/收益预期）、`forecast-self-training`（预测自检训练法：盖图预测—对照道的评论—归因差异）

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
- `dual-index-confirmation-filter-skill` — 双指数相互确认过滤器（未确认信号＝假象）
- `secondary-reaction-assessment-skill` — 次级运动识别与幅度评估
- `line-formation-reading-skill` — 线态窄幅盘整判读（吸筹/派发与突破方向）
- `bear-bottom-checklist-skill` — 熊市底部特征核查清单
- `bull-top-exit-signals-skill` — 牛市顶部信号分级与清仓决策
- `trading-discipline-rules-skill` — 交易纪律与资金管理原则包

留在 router 里的 6 张卡：`volume-price-health`（量价健康度）、`bull-bear-stage-positioning`（牛熊三阶段定位）、`stock-preflight-market-check`（个股大盘前置检查）、`pseudo-signal-troubleshooting`（伪信号排查）、`forecast-self-training`（预测自检训练）、`secondary-reaction-stat-baseline`（统计基准）。

### 该装哪一种

按你的工作方式选，**只装一种**：

| 你的工作方式 | 推荐 | 原因 |
|---|---|---|
| 用 DSH / Codex / Claude Code 等有 skills 目录，希望列表干净 | single | 只占 1 个入口，能力一张不少 |
| 日常问题高度集中在"现在牛还是熊 / 这个信号算不算数 / 该不该清仓 / 能不能抄底" | pack | 这 4 类正是被晋级的独立 skill，能直接命中 |
| 要分发给多个 agent 或团队，各自按需取用 | pack | 可以只装其中几个独立 skill，不必整包 |
| 只想装一次、不想维护多个目录 | single | 升级时只替换 1 个目录 |

> 两版由同一个 Bundle 编译，能力内容一致。**同时安装会重复触发**，请只装一种。

## 效果示例

### 示例 1：一个指数创新高、另一个没跟上，这算牛市确认吗

**用户问题**

"沪深300 已经过了前高，但中证流通还在下面磨，这算牛市确认了吗？能不能加仓？"

**skill 如何判断**

- 进 `primary-trend-identification`：先用"任一指数净变动超 3%"把日间波动切成一段段回升与下跌，再逐段记录两条指数各自的高点／低点，形成阶梯
- 接 `dual-index-confirmation-filter`：任何一个指数的新高都要先判三态——另一指数跟进＝已确认可采信、暂未跟进＝等待确认按兵不动、始终未跟进＝按假象忽略；确认不必同日，甚至不必同周
- 回 `primary-trend-identification` 做反转判据：牛转熊要求"合理时间内不创新高＋双指数跌破前期次级低点"，熊转牛要求"不再创新低＋双指数越过上次重大反弹高点"，两条都是二值判据，单指数破位不改判
- 最后补一句证伪条件：什么走势出现就证明这次判断错了

**最终回答示例**

> 先别叫它牛市确认。按规则，沪深300 过前高只是"一方信号"，中证流通没跟上就处在"等待确认"这一态——此时的动作是维持原判断、不动仓位，而不是把它当利好加仓；如果中证流通始终不跟，这个新高就按假象归档。确认本来就不要求同日同周，所以"它今天没跟"本身不构成否定，你需要的是一条时间线：把两边的最后有效高点、低点连同日期列出来，看阶梯是抬升还是递降。另外提醒两点：3% 是切分运动的讨论单位，不是买卖阈值，点位高的时候要按百分比口径放宽；也别用单条指数的破位去改牛熊判断。要加仓请另走 `stock-preflight-market-check`（个股）与 `trading-discipline-rules`（仓位）两张卡，趋势卡只给方向，不给买卖点位。

### 示例 2：从高点跌了 8%，反弹一次比一次弱，该清仓吗

**用户问题**

"指数从高点下来跌了 8%，这两次反弹一次比一次弱，是不是见顶了？要清仓吗？"

**skill 如何判断**

- 进 `bull-top-exit-signals`：本卡不做点位预测，只做信号分级——先查前兆（成交量持续增加而价格推进甚微的"过度活跃"、借贷利率高企、垃圾股飞涨、龙头股收益低于债券）
- 顶后第一次下跌先按次级回调处理，同时开始登记每次反弹的高点与对应成交量（这一步与 `secondary-reaction-assessment` 互参）
- 核对恶化序列：反弹高点是否一次比一次低、反弹是否缩量而下跌放量（量价背离的证据由 `volume-price-health` 供给，成交量永远排在指数之后）
- 确认触发：跌破前期低点并获另一指数确认，才判定进入熊市第一阶段并分级清仓；仅单指数破位按 `dual-index-confirmation-filter` 的"假象"处理，不下清仓结论
- 输出双边阈值：收复哪个点位则下跌预示收回、跌破哪个点位则预示增强

**最终回答示例**

> "跌了 8%＋反弹变弱"够不上清仓结论，它只是把信号级别往上抬了一档。按卡里的顺序：第一，前兆查了吗——量增而价推进甚微、垃圾股飞涨、龙头股收益低于债券，这几项有没有；第二，顶后首跌先按次级处理，把每次反弹的高点和成交量登记下来，看是不是真的递降又缩量；第三，也是最关键的一步，破位必须两个指数都确认，只有一个指数跌破前低时按假象处理，不减仓也不反手做空。真要减，也是分级的：信号到哪一级减到哪一级，不是一次清光。另外提醒，1929 年那个"低于峰值 10% 即构成明确清仓信号"是该点位下的标本判例，不是通用公式，别把它当止损线套到今天的点位上；顶部信号天然偏迟，这是体系的成本，用分级减仓消化，不靠猜最高点。

## 这些 skill 是怎么生成出来的

这套 skill 使用 **[cangjie-skill](https://github.com/kangarooking/cangjie-skill)** 的 RIA-TV++ 流水线生成，整个流程分六个阶段：

1. **整书理解（Adler 分析）**——用 Mortimer Adler 的分析阅读法，对全书做结构、解释、批判、应用四步拆解，产出 `BOOK_OVERVIEW.md` 与 12 项读者任务清单
2. **并行提取**——同时派多个专项提取器（框架、原则、案例、反例、术语），从原文中提取候选方法论单元
3. **三重验证筛选**——每个候选必须通过三项检验：书内至少有 2 处独立佐证（跨域）、能回答书中未明说的新问题（预测力）、不是常识（独特性）；本轮的 V2 验证是纸面演练，结论登记在 `verified.md`
4. **RIA++ 构造**——按 R（原文引用）/ I（用自己的话重写）/ A1（书中案例）/ A2（未来触发场景）/ E（可执行步骤）/ B（边界与盲点）六个维度结构化
5. **Zettelkasten 链接**——找出能力卡之间的依赖、对比、组合关系，生成能力索引与路由表；`also_read` 字段就是这一步的产物，汇总在 `INDEX.md`
6. **触发与输出测试**——为每张卡设计触发盲测题（含诱饵题：该触发时要触发，不该触发时要沉默）与输出评测场景，未通过的卡回炉重做，回炉后再做回归验证

## 测试与验证

本仓库连生成过程的测试材料一起发布：触发用例在各 skill 目录下的 `test-prompts.json`（`pack/` 下 7 个晋级 skill 各一份，共 68 条），三份逐项评分结果在仓库根目录（`test-results-u01-u05.md`、`test-results-u06-u09.md`、`test-results-u10-u13.md`），包含失败与回炉修复的完整过程，不是只留通过记录。

- **触发与边界用例**：本轮共设计 127 条（每张卡 9–10 条：should_trigger、should_not_trigger 诱饵、edge_case），其中 68 条（7 个晋级 skill）的用例文件随仓库发布；全轮成绩为触发 56 / 57、诱饵 38 / 39、edge 31 / 31
- **诱饵违例 1 条**：`bull-top-exit-signals` 的 snt-03 被判给了近邻卡——如实记录，未做美化
- **输出评测**：13 个单元 × normal / boundary 场景，机械断言 115 / 115 通过
- **判停维度**：13 个判停点全部通过——该拒答时拒答、该追问时追问，不硬给结论
- **无卡对照**：13 组同题不带 skill 的基线对照，记录了卡在哪些维度上出现方向性差异（例如"蓝筹抗跌"vs"绩优股更脆弱"、"未确认不入场"vs"小仓试探"）

> 需要说明的限制：三份结果文件里的触发判定是**主流程回退（fallback）自测**，不是独立盲测，报告里已逐份声明。输出评测与判停是断言式核对，受该偏差影响较小。环境具备子代理后，可用各 skill 目录下的 `test-prompts.json` 原样重跑独立盲测。

## 仓库结构

```text
dow-theory-skill/
├── README.md                ← 你正在看的
├── README.en.md             ← English version
├── LICENSE                  ← MIT
├── BOOK_OVERVIEW.md         ← 阶段 0 产出：全书 Adler 分析
├── DIGEST.md                ← 阶段 5 产出：面向读者的整书精华长文
├── INDEX.md                 ← 阶段 3 产出：skill 总览 + 依赖关系
├── verified.md              ← 通过三重验证的 174 个单元
├── coverage-audit.md      ← 阶段 1.5 产出：原书任务覆盖审计
├── needs-review.md        ← 阶段 1.5 产出：待核查事项与缺口
├── TEST_SUMMARY.md          ← 阶段 4 产出：压力测试摘要
├── CANGJIE_ADAPTATION.md    ← 仓颉适配说明
├── GITHUB_REPO.md           ← 仓库元数据
├── test-results-u01-u05.md  ← 测试结果记录：u01–u05 批次
├── test-results-u06-u09.md  ← 测试结果记录：u06–u09 批次
├── test-results-u10-u13.md  ← 测试结果记录：u10–u13 批次
├── candidates/              ← 阶段 1 产出：原始候选池（201 条）
│   ├── frameworks.md        ← 框架与方法候选
│   ├── principles.md        ← 原则 / 规则 / 计算候选
│   ├── cases.md             ← 书中案例候选
│   ├── counter-examples.md  ← 反例与边界候选
│   └── glossary.md          ← 术语候选
├── rejected/                ← 阶段 1.5 产出：被淘汰的单元 + 原因
├── bundle/                  ← 编译事实源
│   ├── verified.yaml        ← 能力元数据、判据与去向
│   ├── cards/               ← 能力卡源文件（六段结构）
│   └── book/                ← overview.md + glossary.md
├── single/                  ← single 模式（1 个入口 + 全部能力卡）
│   └── dow-theory-skill/SKILL.md  ← 入口：触发 + 路由表 + 加载规则
└── pack/                    ← pack 模式（1 个路由入口 + 7 个晋级 skill）
    └── */SKILL.md           ← 8 个 skill，其中 7 个晋级 skill 各附 test-prompts.json
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

装完问一句"沪深300 过了前高、中证流通没跟，这算牛市确认吗"，看 agent 是否直接进入"单指数信号三态判定 + 高低点阶梯"的流程，而不是给你一段泛泛的行情评论。装的是 single 时，它会先读入口再按路由表进能力卡；装的是 pack 时，对应能力会被直接命中。

## 来源

《道氏理论》罗伯特·雷亚 著

## 声明

本仓库只发布蒸馏后的 skill、索引与规则速查材料，不包含原书 PDF、EPUB、OCR 文件、截图或全书转写稿。能力卡中出现的原文引用仅用于标注方法论出处和保持可审计性。

书中所有数字判据（3% 净逆转、5% 线态宽度、33%~66% 回撤区间、60~90 天谷底时长、低于峰值 10% 的清仓标尺等）都是案例与经验归纳，原书未提供统计回测背书；其参数基于 1897—1931 年美股，迁移到 A 股前须用新数据重估并声明所用口径。本仓库内容不构成投资建议。


## License

[MIT](./LICENSE)
