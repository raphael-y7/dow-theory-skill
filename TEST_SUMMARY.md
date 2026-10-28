# Stage 4 压力测试摘要

> 本文件汇总《道氏理论（专业解读版）》skill 包在 cangjie-skill 流水线阶段 4 的测试资产与结果。测试材料分两处存放：触发用例在各 skill 目录下的 `test-prompts.json`（`pack/` 下 7 个晋级 skill 各一份，共 68 条），逐项评分报告在仓库根目录 `test-results-u01-u05.md`、`test-results-u06-u09.md`、`test-results-u10-u13.md`。

## 测试范围（2026-10-29 实测）

- **能力单元**：13 个（7 个 promoted 晋级能力 + 6 个 router 能力），与 `bundle/verified.yaml` 的 `capabilities` 条目数（13）一致；编译为两种形态——`single/` 1 个入口（13 张卡全部在入口的 `references/capabilities/` 内）、`pack/` 8 个入口（1 个来源路由入口 + 7 个晋级独立 skill）。
- **test-prompts 文件**：7 份，全部位于 `pack/<slug>/test-prompts.json`，即 7 个晋级 skill 各一份；router 入口与 `single/` 入口不带用例文件。
- **用例总数**：68 条，按 `type` 分布：
  - `should_trigger`（应触发）29 条；
  - `should_not_trigger`（诱饵，零容忍）21 条；
  - `edge_case`（边界）18 条。
- **关于 `output_case`**：用例 JSON 中**没有** `output_case` 这个 type（实测 `type` 只出现上述三种）。输出评测不走 test-prompts，而以"固定输入 + 机械断言"的形式记录在三份 test-results 中，共 115 条断言（11 个能力 × 9 条 + 2 个能力 × 8 条，u09 与 u13 各 8 条；按批次为 u01–u05 共 45 条、u06–u09 共 35 条、u10–u13 共 35 条）；边界判停另以 `boundary-input.md` / `boundary.md` 记录（随生成过程的工作目录，未随本仓库发布）：按批次计 13 项全部通过（u01–u05 5、u06–u09 4 份场景、u10–u13 4），按判停点计为 14 个（u06–u09 的 4 份场景含 5 个判停点）。

## 结构检查

- **JSON 可解析性**：7 份 test-prompts JSON 逐份 `json.load` 解析，7/7 通过、0 失败；每份均含 `skill` / `version` / `test_cases` 字段，`type` 取值仅 `should_trigger` / `should_not_trigger` / `edge_case` 三种，无未知取值。
- **frontmatter**：9 个 `SKILL.md`（`pack/` 8 个 + `single/` 1 个）全部以 `---` 开头，`name` 与 `description` 齐备，`name` 与所在目录名一致，0 异常。
- **六段完整性**：33 张 RIA++ 能力卡（`bundle/cards/` 13 + `single/dow-theory-skill/references/capabilities/` 13 + `pack/` 7 个晋级 skill 的 `SKILL.md`）逐份检查 `## R —` / `## I —` / `## A1 —` / `## A2 —` / `## E —` / `## B —` 六个标题，全部齐备，0 缺段。`pack/dow-theory-skill-router/SKILL.md` 是路由入口卡而非能力卡，不采用六段结构（检查中按预期排除，非缺陷）。
- **用例数量分布**：9 条/卡 2 张（`bear-bottom-checklist`、`bull-top-exit-signals`），10 条/卡 5 张（`primary-trend-identification`、`dual-index-confirmation-filter`、`secondary-reaction-assessment`、`line-formation-reading`、`trading-discipline-rules`）。
- **candidates 资产**：`candidates/` 5 份文本（`frameworks` 21 / `principles` 90 / `cases` 42 / `counter-examples` 22 / `glossary` 26 ＝ 201 条候选）；三组验证结果（原 verified-A/B/C）已合并进根目录 `verified.md`，其中 174 条 verified、26 条 reference、1 条 needs_review。

## 结果

- skills: 13
- test_json: 7
- 通过情况（逐批取自三份 test-results，均为**主流程回退 fallback 自测**，非独立盲测）。下表记录的是**全轮 13 份用例文件 / 127 条用例**的成绩，其中 7 个晋级 skill 的 68 条用例文件随仓库保留：

| 批次 | 覆盖能力 | 触发/可达 | 诱饵 | edge | 输出断言 | 边界判停 |
|---|---|---|---|---|---|---|
| u01–u05 | primary-trend-identification、dual-index-confirmation-filter、secondary-reaction-assessment、line-formation-reading、volume-price-health | 50/50 | 15/15 | 15/15 | 45/45 | 5/5 |
| u06–u09 | bull-bear-stage-positioning、bear-bottom-checklist、bull-top-exit-signals、stock-preflight-market-check | 35/37 | 11/12 | 8/8 | 35/35 | 4/4（5 个判停点） |
| u10–u13 | trading-discipline-rules、forecast-self-training、secondary-reaction-stat-baseline、pseudo-signal-troubleshooting | 40/40 | 12/12 | 8/8 | 35/35 | 4/4 |
| **合计** | 13 | **125/127** | **38/39** | **31/31** | **115/115** | **13/13** |

- **失败项如实记录**：u06–u09 批次存在 1 条诱饵违例（`bull-top-exit-signals` 的 snt-03 被判给近邻卡，零容忍未达标）与 1 条对 u10 的竞争落败（u09 st-02）；两条根因同为 description 层未携带卡内排除/承接条款。
- **修复与回归**：u08 description（补指数层边界）、u09 description（补摊平/补仓触发语）、u07 E-2（降权释义）、u10 E-3（敞口公式）4 处已修，并做过 fallback 回归验证通过（详见 `test-results-u06-u09.md` 末尾"回归验证"节）。
- **重要限制（不得省略）**：三份结果文件均声明触发判定为主流程回退（fallback）自测——由设计用例的同一代理执行，存在自我证实偏差，**不得当作独立盲测通过率引用**。输出断言与边界判停为断言式核对，受该偏差影响较小。**独立盲测尚未执行**（当时环境无子代理）。

## 可接入 darwin-skill 的后续动作

1. **作为回归样本直接接入**：68 条随仓库发布的用例（全轮共 127 条）已按能力分文件、带 `type` 与 `expected_behavior`，可直接作为 darwin-skill 的回归集。建议按 `type` 分层评估——诱饵（`should_not_trigger`）单独统计为零容忍指标，不与正向触发混算。
2. **补跑独立盲测**：环境具备子代理后，用 `pack/<slug>/test-prompts.json` 原样复跑，盲测时只给 prompt，不提供 `type` / `expected_behavior` / `notes`；这是把 fallback 自评换成真实成绩的唯一路径。
3. **已修缺陷作为回归锚点**：u08 snt-03（个股清仓诉求误入顶部卡）、u09 st-02（摊平/补仓未命中前置检查）、u07 E-2、u10 E-3 四处修复应固化为必跑用例，防止后续改 description 时回退。
4. **登记未收敛的触发竞争**：u12（次级反应统计基准）与 u03（次级运动评估）共享 57.6% / 33%~66% 数字与"回调多深"语言，fallback 自评无冲突但独立盲测中很可能互抢；接入时应把两类 prompt 同表对照，收集分流证据。
5. **保持"统计不作触发器"的负例**：u12 的用例刻意包含"把历史均值当买入理由"的边界题，接入 darwin-skill 后建议保留，用于检验模型是否把统计预期误用为买卖信号。
6. **判停维度单独成表**：13 个判停点（拒答、追问、声明数据不足）与输出断言是两类不同能力，建议在 darwin-skill 报告中分列，不要合并成单一通过率。
