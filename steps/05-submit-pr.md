# §5 提交 PR

目标：把 §4 的改动提成一个结构清晰、评审友好的 GitHub PR。

## 提交前的 git 操作（GitHub 场景，用 gh CLI）

1. Fork 目标仓库（若无写权限）：`gh repo fork {REPO_URL} --clone`。
2. **新建分支**，不要直接在 main/master 上改：`git checkout -b feat/<简短描述>`。
3. 按 §4 的 commit 计划分 2~4 个逻辑 commit 提交。
4. 推到你的 fork：`git push -u origin feat/<简短描述>`。
5. 创建 PR：`gh pr create --title "..." --body "..."`（标题 ≤ 70 字符，细节放描述）。

> 红线：永远提到新分支；commit 信息遵循项目既有风格（多数用 Conventional Commits）。

## 提 PR 提示词

```
请帮我提交 PR，以下是要求：
提交类型参考：feat / fix / refactor / test / docs

### PR 描述草稿
标题：{type}({scope}): {一句话描述}

Problem
（描述当前存在的问题，客观陈述，不带情绪）

Solution
（描述本 PR 的解决思路，以及为什么选择这个方案）

Changes
- 新增 / 修改了什么

Testing
- 如何验证这个改动有效
- 测试用例覆盖了哪些场景

Notes for Reviewer
（需要 reviewer 重点关注的地方，或有意为之的设计决策）
```

## 出口

PR 已提交。记录 PR 链接与状态，进入 §6 做跟进和面试素材整理。
