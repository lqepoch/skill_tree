# Issue 指南

当仓库要求 issue-first 工作流时，先用 issue 作为唯一事实源，再开始实施。

## 什么时候必须先建 issue

- 用户明确要求先分析问题、再修复
- 任务会涉及代码、配置、迁移、回归或发布
- 需要多人协作、跨文件修改或后续追踪
- 需要记录根因、验证和回滚信息

## 标准流程

1. Triage
   - 先确认问题、影响、环境、范围和验收标准
   - 信息不足时，先开 triage issue，并标记 `status: needs-info`
   - 不要用猜测替代事实
2. 创建或更新 issue
   - 优先使用 issue 模板
   - 标题建议使用 `[type] 简短摘要`
   - bug、feature、task 采用各自对应模板
3. 补充标签
   - 至少使用一个 `type:*`
   - 至少使用一个 `status:*`
   - 需要时再加 `priority:*` 和 `area:*`
4. 实时记录进度
   - 在每个关键检查点更新 issue 评论
   - 不要等到最后一次性回填
   - 如果遇到阻塞，第一时间说明阻塞点
5. 关联 PR
   - PR 正文必须写入会自动关闭 issue 的引用
   - 对于多个 issue，要逐个列出
6. 收尾
   - 验证完成后补最终总结评论
   - 只有修复已验证且足够稳定时再关闭 issue

## 必填内容

每个 issue 都应该写清楚：

- 问题 / 需求 / 任务是什么
- 在哪里发生
- 如何复现或证明
- 预期结果是什么
- 为什么重要
- 相关文件、模块、服务或配置
- 推荐修复或下一步
- 如何验证成功
- 是否需要回滚或缓解

## Bug 额外要求

bug issue 至少要包含：

- 观察到的行为
- 预期行为
- 复现步骤
- 证据：日志、截图、trace、链接、测试结果
- 根因假设
- 候选修复路径
- 验证计划

### 示例

```text
Checkpoint: triage
Change: 已确认问题只在支付确认链路出现
Remaining: 需要验证是否为重试逻辑导致
Blocker: 暂无
Evidence: request_id=...
```

## Feature 额外要求

feature issue 至少要包含：

- 业务目标
- 非目标
- 约束和依赖
- 影响范围
- 发布或迁移说明
- 验收标准

## Task 额外要求

task issue 至少要包含：

- 交付物
- 范围边界
- 可能涉及的文件或系统
- 执行计划
- 验证步骤
- 后续或回滚说明

## 进度评论规范

在 issue 评论中使用统一格式，方便快速扫描：

- `Checkpoint`
- `Change`
- `Remaining`
- `Blocker`
- `Evidence`

建议在这些时点更新：

- triage 完成
- 方案确认
- 实现开始
- 验证完成
- 准备关闭

## PR 关联规则

如果一个 PR 会解决一个或多个 issue，PR 正文必须写清楚：

- `Closes #123`
- `Fixes #123`
- `Closes owner/repo#123`

如果一个 PR 会关闭多个 issue，每个 issue 都要单独列出，不能只写一个笼统引用。

### 示例

```text
Closes #123
Closes #124
Closes #125
```

## 模板位置

参考模板放在 `references/`，而不是 `assets/`。

这样做的原因是：

- `references/` 适合放可读、可复用的说明和样例
- `assets/` 更适合放图片、二进制素材或不需要直接阅读的辅助内容
- 模板本身就是“可复制的说明书”，更符合 `references/` 的定位

## 推荐标签

- `type: bug`
- `type: feature`
- `type: task`
- `type: docs`
- `status: needs-triage`
- `status: needs-info`
- `status: in-progress`
- `status: blocked`
- `priority: high`
- `priority: medium`
- `priority: low`
- `area:*`

## 最后检查

在准备关闭 issue 前，确认：

- 事实和假设已经分开写清楚
- 关键证据已经留下
- 修复和验证都已完成
- PR 已正确关联 issue
- 没有遗漏后续动作
