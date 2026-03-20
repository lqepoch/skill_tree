# AGENTS.md

## 1. 仓库定位

本仓库是一个开源的、参考型的 Agent Skills 仓库。

目标：
- 沉淀可复用的常用 skills；
- 统一收纳适合 Claude Code、Codex 等 AI agent 生态参考的 skill 写法；
- 以标准化、可维护、可扩展的方式组织 skills；
- 为个人使用、开源协作、二次改造提供高质量样例。

本仓库不是“一次性 prompt 收藏夹”，也不是“随手记录的零散经验”。
本仓库收录的内容必须是：
- 可复用的；
- 有明确任务边界的；
- 能被 agent 理解和执行的；
- 适合作为长期维护资产的。

---

## 2. 兼容性说明

本仓库的目标是提供 **兼容 Claude Code / Codex 风格的 skills 编写参考**。

说明：
- 本仓库同时维护 `skills-en/` 和 `skills-zh/`；
- `skills-en/` 与 `skills-zh/` 都是事实源和示例展示目录；
- 新增 skill、修改 skill、重构 skill 时，两个目录必须同步更新；
- 任何只修改单一语言目录的变更都视为不完整；
- 两个目录下相同 skill 的目录结构、文件命名、内容边界应保持一致，只允许语言内容不同；
- 本仓库不承诺默认目录发现；
- 本仓库不承诺开箱即用自动接入某个具体客户端；
- 使用者如需接入 Claude Code、Codex 或其他 agent 工具，应自行按对应工具的目录约定进行复制、映射或二次分发。

因此，本仓库强调的是：
- 格式兼容思路
- 结构兼容思路
- 写法兼容思路
- 中英文双语同步维护思路

---

## 3. 目录规则

本仓库只维护以下核心目录：

```text
skills-en/
  <skill-name>/
    SKILL.md
    scripts/
    references/
    assets/
```

```text
skills-zh/
  <skill-name>/
    SKILL.md
    scripts/
    references/
    assets/
```

规则：
- 新建 skill 时，必须同时在 `skills-en/` 和 `skills-zh/` 下创建对应目录；
- 修改 skill 时，必须同时修改两个目录中对应的内容；
- 若某一侧暂时无法同步，视为未完成，不应合并为最终状态；
- 两个目录中的结构应尽量一一对应，便于长期维护与迁移。
