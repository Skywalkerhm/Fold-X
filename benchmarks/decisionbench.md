# DecisionBench：Fold-X 决策能力评测

[English](../en/benchmarks/decisionbench.md)

核查日期：2026-11-14。DecisionBench 1.0 全量 23,900 题。

产品名称与提交身份对应：**Fold-X Flash = Fold-X 9B 1.3 Deep**；**Fold-X Light = Fold-X 4B 1.0 Deep**；**Fold-X Pro = 27B**。产品更名不改变原始提交名称、版本或评测成绩。

## 全量成绩与参考位置

|模型|主准确率|参考位置（同时加入）|成功题数|结果来源|
|---|---:|---:|---:|---|
|Fold-X Flash（9B）|**76.85%**|**第 4 / 61**|23,900 / 23,900|[PR #85](https://github.com/Hanno-Labs/decision-bench-results/pull/85)|
|Fold-X Light（4B）|**74.48%**|**第 7 / 61**|23,900 / 23,900|[PR #82](https://github.com/Hanno-Labs/decision-bench-results/pull/82)|

两项结果均实现 100% 覆盖率，调用记录无错误或不支持题目；这指任务完成情况，不表示所有回答正确。参考位置体现提交成绩在同一基准中的相对水平，不是官方已收录名次。

### Top 10 参考清单 · DecisionBench 1.0

|参考名次|模型 / 提交版本|准确率|记录来源|
|---:|---|---:|---|
|1|Hanno-Labs/bosun-v3.1-1.7b|84.90%|[主榜归档](https://github.com/Hanno-Labs/decision-bench-results/tree/e2d6a133cee91b9d8c6fbd076b21f32f3d75c81f)|
|2|Hanno-Labs/bosun-v3.1-0.6b|81.18%|[主榜归档](https://github.com/Hanno-Labs/decision-bench-results/tree/e2d6a133cee91b9d8c6fbd076b21f32f3d75c81f)|
|3|mohit67890/imajev-4b|79.69%|[主榜归档](https://github.com/Hanno-Labs/decision-bench-results/tree/e2d6a133cee91b9d8c6fbd076b21f32f3d75c81f)|
|**4**|**Fold-X Flash (9B · 1.3 Deep)**|**76.85%**|**[已提交，尚未收录](https://github.com/Hanno-Labs/decision-bench-results/pull/85)**|
|5|EldanRing/Winnow-12B|76.65%|[主榜归档](https://github.com/Hanno-Labs/decision-bench-results/tree/e2d6a133cee91b9d8c6fbd076b21f32f3d75c81f)|
|6|ekzhang/openjev-sglang|74.82%|[主榜归档](https://github.com/Hanno-Labs/decision-bench-results/tree/e2d6a133cee91b9d8c6fbd076b21f32f3d75c81f)|
|**7**|**Fold-X Light (4B · 1.0 Deep)**|**74.48%**|**[已提交，尚未收录](https://github.com/Hanno-Labs/decision-bench-results/pull/82)**|
|8|z-ai/glm-5.3-flash|74.09%|[主榜归档](https://github.com/Hanno-Labs/decision-bench-results/tree/e2d6a133cee91b9d8c6fbd076b21f32f3d75c81f)|
|9|typesafe/jev-1.13|72.03%|[主榜归档](https://github.com/Hanno-Labs/decision-bench-results/tree/e2d6a133cee91b9d8c6fbd076b21f32f3d75c81f)|
|10|deepseek/deepseek-v4.1-flash|71.00%|[主榜归档](https://github.com/Hanno-Labs/decision-bench-results/tree/e2d6a133cee91b9d8c6fbd076b21f32f3d75c81f)|

依据 2026-11-14 归档快照：59 条主榜当前记录，同时加入 Fold-X Flash、Light 两项已提交，尚未收录，共 61 条，按全量准确率降序排列。以下为参考 Top 10，不是官方已收录排名；Pro 尚无可核验的全量提交，不列入此表。

## Fold-X Pro（27B）：内部成绩与条件参考位置

团队内部测试报告：**文字判断准确率超过 82%**。该数据尚未核验为同一 DecisionBench 1.0 的 23,900 题全量结果。

若该成绩在同一数据版本、全量题目及 primary_accuracy 计分口径下复现，将 Pro 单独加入当前 59 条参照记录，可进入 **前 2 / 60（条件估算，待验证）**。当前最高两项成绩为 84.8996% 和 81.1841%；超过 82% 可超过第二项，但不能据此判断是否超过第一项。因此不能直接标注“第 2 名”或“已上榜”。

该位置属于条件估算，不与 Flash、Light 已提交结果的参考位置视为同等证据。需补齐 Pro 全量结果、逐题记录和模型版本后，才能给出可核验的具体参考名次。

## Fold-X Flash 的任务表现

|任务类型|准确率|题数|
|---|---:|---:|
|二分类判断|87.45%|6,388|
|候选项选择|76.54%|15,814|
|有序评分|39.87%|1,698|

这组结果显示，当前版本在二分类和候选选择上的表现较强，有序评分仍是需要继续提升的方向。整体准确率按题目数量加权，不是三类准确率的简单平均。

## 固定基线对照

DecisionBench 仓库自动对比评论提供了相同基准下的固定版本对照：

|提交模型|相对 Jev 1.13（72.03%）|相对 GPT-5.6 Luna（69.90%）|
|---|---:|---:|
|Fold-X Flash（9B）|**+4.82 个百分点**|**+6.95 个百分点**|
|Fold-X Light（4B）|**+2.45 个百分点**|**+4.58 个百分点**|

来源：[9B 自动对比](https://github.com/Hanno-Labs/decision-bench-results/pull/85#issuecomment-6383351153)、[4B 自动对比](https://github.com/Hanno-Labs/decision-bench-results/pull/82#issuecomment-6291636964)。这里比较的是完整测试集的整体准确率，具体任务上的优势存在差异。

## 排序与证据口径

- 基准为 DecisionBench 1.0，共 23,900 题；按 primary_accuracy 排序，错误和不支持题目计为未答对。
- 主仓库快照日期为 2026-11-14，提交 SHA 为 `e2d6a133cee91b9d8c6fbd076b21f32f3d75c81f`。60 个结果文件按榜单前端的最新修订选择规则整理后，得到 59 条当前结果。
- 依据 2026-11-14 归档快照：59 条主榜当前记录，同时加入 Fold-X Flash、Light 两项已提交，尚未收录，共 61 条，按全量准确率降序排列。以下为参考 Top 10，不是官方已收录排名；Pro 尚无可核验的全量提交，不列入此表。
- 此前分别单独加入时为 Flash 第 4/60、Light 第 6/60；本页统一使用同时加入的 61 条口径，准确率未发生变化。
- 4B 的 PR 已由机器人关闭且未合并；9B 的 PR 仍开放且未合并。两项成绩均为作者提交结果，自动对比不代表主办方独立复现或认证。

可查阅[冻结的结果仓库](https://github.com/Hanno-Labs/decision-bench-results/tree/e2d6a133cee91b9d8c6fbd076b21f32f3d75c81f)及[前端版本选择规则](https://github.com/Hanno-Labs/decision-bench-leaderboard/blob/1aa3f4d5273dcf3e450be473e96df0a74def4b82/src/lib/data/service.ts)。

## 结论适用范围

结果用于说明指定版本在该测试集上的判断能力，不代表所有任务均领先，也不能据此推导 Token、成本或中文能力优势。Fold-X Pro 尚无本次可核验的 DecisionBench 完整结果，仅展示上述条件估算，不主张已取得该名次。

[返回 Fold-X 首页](../README.md)

