---
name: pme
description: Explicit-only product execution workflow. Use only when the user invokes $pme; do not activate from ordinary mentions of PRDs, roadmaps, stories, acceptance criteria, sprints, tests, releases, or delivery.
---

# PME：产品执行

把已确认的产品决定转成可评审、可开发、可测试、可验收的交付材料。只在用户显式输入 `$pme` 时运行。

## 工作边界

- 先确认上游决定是否已经成立；发现关键定位或需求仍未确认时，明确退回 `$pmd` 或 `$pms`，不要用完整文档掩盖未知。
- 优先读取工作区现有 PRD、设计、计划和进度材料，保持术语、版本和文档边界一致。
- 需求、设计、计划、实际进度必须分开；原型通过不等于正式功能完成，测试通过不等于用户验收。
- 用户负责产品选择、必要账号/密钥和最终验收；技术实现、测试和修复在用户明确要求实施时由 AI 完成，不把编程任务推回用户。
- 未经要求，不写代码、不提交 Git、不推送、不部署，也不把“草案”写成“已完成”。

## 路由

根据请求选择一个交付模式。需要详细结构时读取 [references/playbook.md](references/playbook.md)：

- `PRD/需求规格`
- `用户故事与验收标准`
- `结果型路线图/里程碑`
- `OKR 与成功指标`
- `迭代或 Sprint 计划`
- `测试场景与验收清单`
- `预演失败/风险审查`
- `利益相关者沟通`
- `会议纪要或发布说明`

## 默认交付规则

- 每条需求说明来源、优先级、状态和验收方式。
- 验收标准必须可观察、可判定，覆盖主流程、边界、异常、权限、数据保存与恢复；按实际风险增减。
- 用 `已确认`、`建议`、`假设`、`待决定`、`已验证` 标识状态。
- 明确范围内、范围外、依赖、风险和未决问题。
- 如果产物进入工作区，先检查目标文件和未提交修改，做最小必要编辑并执行与改动相称的检查。
- 完成后说明改了什么、验证了什么、尚未验证什么，以及下一项需要用户验收的内容。

## 来源

本技能是面向个人工作方式重新整理的工作流。来源和许可说明见 [references/attribution.md](references/attribution.md)。
