# §1 找合适的开源项目

目标：从 GitHub 上筛出一批**跟 Agent 强相关、热度够、仍活跃**的候选项目，供 §2 深入分析。

## 一个合格项目的三条硬要求

1. **跟 Agent 强相关**（AI Agent / LLM 框架、工具链、应用）。
2. **Star 数量够多**（有社区、有维护投入）。
3. **仍然活跃**，用下面的健康度信号判断。

## 健康度信号（逐条核对，别只看 Star）

| 指标 | 健康信号 |
|---|---|
| Last commit | 近 1 个月内有提交 |
| Issues 关闭率 | closed / open 比例 > 1 |
| PR 合并速度 | 一般 < 2 周有回应 |
| Release 频率 | 每月或每季度有版本 |

任一指标明显不达标（如半年没提交、PR 堆积无人理），即便 Star 很高也要谨慎——很可能已经停更，贡献难被 merge。

## GitHub Search 高级语法

用 GitHub 的高级搜索按主题 + 热度 + 活跃度一次性收窄。示例：

```
topic:ai-agent stars:>1000 pushed:>2026-04-01
```

- `topic:ai-agent`：按主题标签过滤（可换 `llm`、`autonomous-agents`、`langchain` 等相关 topic）。
- `stars:>1000`：热度下限，按需调整。
- `pushed:>YYYY-MM-DD`：最近有推送，直接过滤掉停更项目（把日期设成"近 1 个月"对齐 last commit 要求）。

> 执行提示：可在 GitHub 网页搜索栏直接输入上述语法；若要自动化，用 `gh search repos "topic:ai-agent stars:>1000 pushed:>2026-04-01" --limit 20` 拉取候选列表。

## 出口

产出一份候选项目清单（建议 3~8 个），每个标注：仓库地址、Star、last commit、issue 关闭率、是否仍活跃的结论。和用户一起选定 **1 个**项目，拿到它的 `{REPO_URL}`，进入 §2。
