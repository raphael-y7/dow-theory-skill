# Skill 地图 — 道氏理论（专业解读版）

13 张能力卡的分工、去向与依赖关系一览；先读入口 `SKILL.md`，再按路由表只加载命中的 1–2 张卡。

## 能力总表

| capability_id | slug | 中文标题 | 重要度 | 去向 |
|---|---|---|---|---|
| `cap.dow-theory-skill.primary-trend-identification-skill` | `primary-trend-identification-skill` | 主要趋势判定（高低点阶梯＋3%净逆转＋牛熊反转判据） | critical | promoted → 独立 skill |
| `cap.dow-theory-skill.dual-index-confirmation-filter-skill` | `dual-index-confirmation-filter-skill` | 双指数相互确认过滤器（未确认信号＝假象） | critical | promoted → 独立 skill |
| `cap.dow-theory-skill.secondary-reaction-assessment-skill` | `secondary-reaction-assessment-skill` | 次级运动识别与幅度评估（33%~66%＋速度不对称＋完成序列） | critical | promoted → 独立 skill |
| `cap.dow-theory-skill.line-formation-reading-skill` | `line-formation-reading-skill` | 线态窄幅盘整判读（吸筹/派发推断与突破方向） | high | promoted → 独立 skill |
| `cap.dow-theory-skill.bear-bottom-checklist-skill` | `bear-bottom-checklist-skill` | 熊市底部特征核查清单（图 1 九次熊市统计画像） | high | promoted → 独立 skill |
| `cap.dow-theory-skill.bull-top-exit-signals-skill` | `bull-top-exit-signals-skill` | 牛市顶部信号分级与清仓决策（1929 年 9—10 月标本） | high | promoted → 独立 skill |
| `cap.dow-theory-skill.trading-discipline-rules-skill` | `trading-discipline-rules-skill` | 交易纪律与资金管理原则包（止损/仓位/加码方向/收益预期） | high | promoted → 独立 skill |
| `cap.dow-theory-skill.volume-price-health-skill` | `volume-price-health-skill` | 量价关系健康度评估（超买超卖与沉闷/活跃语义） | high | router → 路由入口 |
| `cap.dow-theory-skill.bull-bear-stage-positioning-skill` | `bull-bear-stage-positioning-skill` | 牛熊三阶段定位器（按驱动锚定位并校准风险态度） | high | router → 路由入口 |
| `cap.dow-theory-skill.stock-preflight-market-check-skill` | `stock-preflight-market-check-skill` | 个股操作的大盘趋势前置检查（防呆闸门） | high | router → 路由入口 |
| `cap.dow-theory-skill.pseudo-signal-troubleshooting-skill` | `pseudo-signal-troubleshooting-skill` | 伪信号与归因排查（前提门槛＋反模式清单） | high | router → 路由入口 |
| `cap.dow-theory-skill.forecast-self-training-skill` | `forecast-self-training-skill` | 预测自检训练法（盖图预测—对照道的评论—归因差异） | medium | router → 路由入口 |
| `cap.dow-theory-skill.secondary-reaction-stat-baseline-skill` | `secondary-reaction-stat-baseline-skill` | 次级反应统计基准与数据基建（35 年分布预期＋记录模板＋除数法） | medium | router → 路由入口 |

统计：13 张卡＝7 张 promoted（晋级为独立 skill）＋6 张 router（由来源路由入口持有）；重要度 critical 3 张、high 8 张、medium 2 张。

## 依赖关系

下表取自 `bundle/verified.yaml` 每张卡的 `also_read` 字段（"读了这张还要顺带读哪些"），箭头右侧为被引用的卡：

| 能力卡 | also_read（依赖 / 顺读） |
|---|---|
| `primary-trend-identification` | `dual-index-confirmation-filter`、`secondary-reaction-assessment`、`bear-bottom-checklist`、`bull-top-exit-signals` |
| `dual-index-confirmation-filter` | `primary-trend-identification`、`line-formation-reading`、`pseudo-signal-troubleshooting` |
| `secondary-reaction-assessment` | `primary-trend-identification`、`secondary-reaction-stat-baseline`、`volume-price-health` |
| `line-formation-reading` | `dual-index-confirmation-filter`、`primary-trend-identification`、`bull-top-exit-signals` |
| `volume-price-health` | `primary-trend-identification`、`bull-top-exit-signals`、`trading-discipline-rules` |
| `bull-bear-stage-positioning` | `primary-trend-identification`、`bear-bottom-checklist`、`bull-top-exit-signals` |
| `bear-bottom-checklist` | `primary-trend-identification`、`dual-index-confirmation-filter`、`bull-top-exit-signals`、`secondary-reaction-assessment` |
| `bull-top-exit-signals` | `bear-bottom-checklist`、`secondary-reaction-assessment`、`dual-index-confirmation-filter`、`volume-price-health` |
| `stock-preflight-market-check` | `primary-trend-identification`、`bear-bottom-checklist`、`trading-discipline-rules` |
| `trading-discipline-rules` | `volume-price-health`、`secondary-reaction-stat-baseline`、`bull-top-exit-signals` |
| `forecast-self-training` | `secondary-reaction-stat-baseline`、`secondary-reaction-assessment`、`primary-trend-identification`、`pseudo-signal-troubleshooting` |
| `secondary-reaction-stat-baseline` | `secondary-reaction-assessment`、`forecast-self-training`、`bear-bottom-checklist` |
| `pseudo-signal-troubleshooting` | `dual-index-confirmation-filter`、`primary-trend-identification`、`secondary-reaction-assessment`、`stock-preflight-market-check` |

读法：`primary-trend-identification` 是被引用最多的一张（10 张卡把它列为顺读项），它是整个体系的方向底座；`dual-index-confirmation-filter` 是它的确认动作，两者几乎总是成对出现。`volume-price-health` 与 `secondary-reaction-stat-baseline` 属于"只做辅助"的卡——前者永远排在指数判读之后，后者只校准预期、不得当触发器。

## 加载顺序

1. **先读入口**：`single/dow-theory-skill/SKILL.md`（或 pack 里的 `dow-theory-skill-router/SKILL.md`）。入口带着触发/不触发条件、5 条核心原则、13 行意图路由表与判停规则；概览类问题读到这里就可以回答，不必加载能力卡。
2. **再按路由表加载 1 张卡**：一次任务默认只加载命中的那一张。任务明确跨域时最多 2 张，优先"主卡＋它的 also_read 里被标为依赖的那张"（例如判趋势时 `primary-trend-identification` ＋ `dual-index-confirmation-filter`）。
3. **不要整包加载**：13 张卡全读会互相干扰触发判据（同一句话可能同时命中"趋势方向"与"信号确认"），也会让判停规则失去意义。入口的路由表与 `references/capability-index.md` 都命中不了时，明确告知超出本书范围，不要硬套。
