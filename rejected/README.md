# rejected/ — 淘汰单元留档（本书为 0 条，附审计说明）

## 结论

《道氏理论（专业解读版）》拆书流水线**没有淘汰任何候选单元**，因此本目录除本说明外为空。
这不是遗漏归档，而是阶段 1.5 的真实判定结果。

## 证据（可复核）

阶段 1.5 三重验证共处理 201 条候选（框架 21 / 原则 90 / 案例 42 / 反例 22 / 术语 26），判定分布：

| decision | 数量 | 去向 |
|---|---|---|
| verified | 174 | 能力卡池（13 个能力单元） |
| reference | 26 | references.md → GLOSSARY.md、Bundle book/overview.md 参考区 |
| needs_review | 1（p32"全体反弹均值 49.5%"） | needs-review.md，禁入 active 能力池 |
| **rejected** | **0** | — |

三组验证文件的机器统计（`candidates/verified-A.yaml`、`verified-B.yaml`、`verified-C.yaml`）：
A 组 26 verified + 21 reference；B 组 85 verified + 4 reference + 1 needs_review；C 组 63 verified + 1 reference。
合计 201 = 174 + 26 + 1 + 0，与上表一致。

## 为什么 0 淘汰

1. **无"无原文依据"项**：全部 201 条都能回核到合并转写稿的具体位置（章号／表号／图号／专栏日期），验证时逐条 grep 复核过引文。
2. **无"错误归因"项**：候选均绑定雷亚正文或汉密尔顿专栏原文；译者层（"专业解析"）内容单独标注，未冒充作者方法论。
3. **无"被完整覆盖"的重复项**：同行情多候选（1921 底部、1926 误判、1929 顶部、1907 恐慌等）分别承担亲历面／复盘面／专栏原文面／演算面，互不完整覆盖，已在 bound_to 中标注分工互参。
4. **不合格的去向不是淘汰而是降级**：不可独立执行但有来源价值的 26 条转 reference；关键条件缺失的 1 条转 needs_review。方法论规定这两类不写入 rejected/。

## 复核入口

- 判定明细：`审计过程/candidates/verified-A.yaml`、`verified-B.yaml`、`verified-C.yaml`
- 参考项与交付映射：`审计过程/references.md`
- 待核查项与全部引文瑕疵：`审计过程/needs-review.md`
- 任务覆盖审计：`审计过程/coverage-audit.md`
