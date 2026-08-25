# Dataset Card Skill

`dataset-card` 是一个 Codex Skill，用于为生物与组学数据集创建、更新和审计固定格式的 `DATASET.md`。每份卡片作为 Agent 理解对应数据集的入口。

Skill 位于 [`dataset-card/`](dataset-card/)，固定模板位于 [`dataset-card/assets/DATASET.template.md`](dataset-card/assets/DATASET.template.md)。

可以直接使用自然语言：

```text
请为 /path/to/dataset 创建或更新 DATASET.md。
```

也可以显式调用：

```text
Use $dataset-card to update DATASET.md for /path/to/dataset.
```

批量处理时必须明确列出每个数据集目录；审计模式默认只报告问题，不修改文件。
