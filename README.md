# Codex Skills 中文合集

一套可复用的 Codex Skills 集合，覆盖产品发现、产品战略、产品执行、前端产品设计与 UI/UX 视觉设计。

这个仓库的重点不是“让所有 Skill 自动运行”，而是把不同阶段的职责分开：产品经理三件套只接受明确指令，前端两件套则按任务范围自动匹配。

## 包含哪些 Skills

| Skill | 作用 | 触发方式 |
|---|---|---|
| `pmd` | 产品发现：用户问题、需求真伪、访谈、假设与验证实验 | 仅在输入 `$pmd` 时触发 |
| `pms` | 产品战略：目标用户、定位、价值、取舍、商业模式与指标 | 仅在输入 `$pms` 时触发 |
| `pme` | 产品执行：PRD、用户故事、验收标准、计划与测试材料 | 仅在输入 `$pme` 时触发 |
| `product-design-and-ux` | 前端需求、信息架构、任务流程、页面状态、异常恢复与验收标准 | 符合描述时自动匹配，也可点名使用 |
| `ui-ux-pro-max` | 视觉方向、设计系统、配色、字体、间距、布局、动效与 UI/UX 审查 | 需求和流程确认后自动匹配，也可点名使用 |

## 推荐工作流

产品工作：

```text
$pmd 发现和验证问题
  ↓ 用户确认机会值得做
$pms 确定定位、价值与取舍
  ↓ 用户确认战略方向
$pme 形成 PRD、故事、验收与交付材料
```

前端设计：

```text
product-design-and-ux
梳理页面、流程、状态与验收标准
  ↓ 用户确认
ui-ux-pro-max
确定视觉方向、设计系统与交互表现
  ↓ 用户确认
正式开发与测试
```

不要求每次走完整流程。已有明确需求时可以直接使用 `$pme`；只做已有页面的视觉审查时可以直接点名 `ui-ux-pro-max`。

## 目录结构

```text
.
├─ 产品经理-skills合集/
│  ├─ pmd/
│  ├─ pms/
│  ├─ pme/
│  └─ 产品经理Skills使用说明.md
├─ product-design-and-ux/
├─ ui-ux-pro-max/
├─ 两份前端Skills使用说明.md
├─ FRONTEND_SKILLS_POLICY.md
└─ THIRD_PARTY_NOTICES.md
```

每个可安装的 Skill 目录都包含 `SKILL.md`。`references/`、`templates/`、`scripts/` 和 `evals/` 是按需加载的辅助材料，不需要把所有内容一次性写进提示词。

## 安装到 Codex

先把仓库克隆到本地，然后把五个 Skill 目录复制到 Codex 的 Skills 目录。Windows PowerShell 示例：

```powershell
git clone https://github.com/zhangyudai/codex-skills-library.git
Set-Location .\codex-skills-library

$skillsHome = Join-Path $env:USERPROFILE '.codex\skills'
New-Item -ItemType Directory -Force -Path $skillsHome | Out-Null

Copy-Item -Recurse -Force '.\产品经理-skills合集\pmd' $skillsHome
Copy-Item -Recurse -Force '.\产品经理-skills合集\pms' $skillsHome
Copy-Item -Recurse -Force '.\产品经理-skills合集\pme' $skillsHome
Copy-Item -Recurse -Force '.\product-design-and-ux' $skillsHome
Copy-Item -Recurse -Force '.\ui-ux-pro-max' $skillsHome
```

安装或更新后，建议新建一个 Codex 对话；如果仍未识别，再完全退出并重新打开 Codex。

> 不要把外层的 `产品经理-skills合集` 整体当成一个 Skill 安装。真正的三个 Skill 是里面的 `pmd`、`pms` 和 `pme`。

## 使用示例

```text
$pmd 帮我判断“同时比较四个大模型回答”是不是真需求，并设计最低成本验证方法。
```

```text
$pms 根据已有调研，确定首批目标用户、核心价值和明确不做的方向。
```

```text
$pme 根据现有 PRD 补充遗漏内容，只修改受影响章节，并标出待确认项。
```

```text
使用 product-design-and-ux，帮我梳理这个功能的页面、操作流程、异常状态和验收标准，先不要设计视觉。
```

```text
使用 ui-ux-pro-max，根据已经确认的前端需求给出三套视觉方向，先不要修改正式代码。
```

更完整的说明见：

- [产品经理 Skills 使用说明](./产品经理-skills合集/产品经理Skills使用说明.md)
- [两份前端 Skills 使用说明](./两份前端Skills使用说明.md)
- [前端 Skills 共用规则](./FRONTEND_SKILLS_POLICY.md)

## 使用边界

- Skill 负责提供工作方法和输出规范，不代表自动获得写代码、提交 Git、部署或修改外部系统的权限。
- `$pmd`、`$pms`、`$pme` 必须显式输入对应触发码，普通聊天不会自动启用。
- `product-design-and-ux` 先解决“做什么、怎么用”；`ui-ux-pro-max` 再解决“长什么样、如何保持一致”。
- 上游资料中提到但本仓库未包含的相邻 Skills 属于可选扩展，不影响本合集中的核心 Skill 独立使用。
- 本仓库含本地改编内容；它不是上游项目的官方发行版。

## 验证

发布前执行以下检查：

- 所有 `SKILL.md` 的结构校验；
- `ui-ux-pro-max` 数据校验和可独立运行的单元测试；
- 敏感信息文件名扫描；
- Git 暂存区差异检查，确保缓存文件没有进入仓库。

`ui-ux-pro-max/scripts/tests` 中另有 4 个面向上游完整项目的仓库级集成测试，它们依赖本合集未收录的维护脚本；这 4 项不作为独立 Skill 包的通过条件。

## 来源与许可证

本合集包含来自多个 MIT 许可项目的内容，并在此基础上做了本地化与工作流调整：

- 产品经理 Skills 的上游灵感：[phuryn/pm-skills](https://github.com/phuryn/pm-skills)
- `product-design-and-ux`：[magnus919/agent-skills](https://github.com/magnus919/agent-skills/tree/main/product-design-and-ux)
- `ui-ux-pro-max`：[nextlevelbuilder/ui-ux-pro-max-skill](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill)

完整版权与许可说明见 [THIRD_PARTY_NOTICES.md](./THIRD_PARTY_NOTICES.md)，各 Skill 目录中也保留了相应许可证。
