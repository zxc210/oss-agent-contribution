# oss-agent-contribution

为开源项目做贡献的全流程 skill（面向 GitHub，产出 PR），主题 / 领域不限（AI Agent、数据库、前端组件库、CLI 工具等均可，由用户声明）。整理自作者 Lucian 的方法论文章《手把手教你为 AI Agent 开源项目做贡献》，并把流程泛化到任意主题。

## 结构

```
oss-agent-contribution/
├── SKILL.md                           # 总调度：定位、触发词、四阶段总览、步骤路由、红线
├── .gitignore                         # 忽略 _oss-work/、.idea/、凭据/临时文件等
├── steps/
│   ├── 00-progress-log.md             # §0 贯穿全程：进度存档与恢复（断点续跑）
│   ├── 01-find-project.md             # ① 找项目：GitHub 高级搜索 + 健康度筛选
│   ├── 02-find-entry-point.md         # ② 找切入点：Label 过滤 + 架构缺陷分析 + Top3
│   ├── 03-tech-design.md              # ③ 技术方案设计 + 维护者沟通草稿
│   ├── 04-implement.md                # ③ 代码实现 + 测试 + commit 计划
│   ├── 05-submit-pr.md                # ③ 提交 PR（gh CLI）
│   └── 06-followup-and-retrospective.md # ④ PR 跟进 + 经验总结沉淀
└── _oss-work/                         # 本地作战记录（被 .gitignore 忽略，不入库）
    ├── preferences.md                 # 贡献偏好：主题/领域 + 技术栈（§1 读它定主题，不写死）
    ├── identity.md                    # 提 PR 用的 git 身份（本地私有）
    └── <repo>/                        # 按目标仓库分目录
        └── <task-slug>/               # 同一仓库下每个 issue/PR 一个任务目录：progress.md + 草稿
```

## 怎么用

从 `SKILL.md` 入手，按用户当前进度路由到对应 step。每步带结构化提示词，把 `{REPO_URL}` / `{LOCAL_PATH}` / 技术栈等占位符替换后使用，并把上一步产物作为下一步的上下文注入。

整个流程跨度长（等维护者回 issue、等 PR review），§0 约定在关键节点把进度写进 `_oss-work/<repo>/<task-slug>/progress.md`，换个会话靠它断点续跑。同一仓库下多个 issue/PR 按 `<task-slug>` 各自成档、互不干扰。该目录已被 `.gitignore` 忽略，不进 skill 仓库。
