# Outcome Guard · 目标与交付守护

**让 AI 按目标完成任务，避免研究与执行脱节、把半成品当成完成。**

一个适用于 Codex 多步骤任务的轻量 Skill：

- **开工前对齐**：明确本轮要交付什么，把研究结论变成具体要求。
- **执行中纠偏**：局部改好后检查整体，被否定的结果不能继续算通过。
- **交付前检查**：内部测试通过不等于完成，还有已授权的工作就继续做。

例如：用户要三个新人物设计，AI 只完成了旧人物的动作测试。这个技能会要求它继续完成新设计，而不是拿测试图交差。用户若只要求动作修改，则完成该修改即可，不擅自扩展任务。

## 安装

把仓库中的 `outcome-guard` 文件夹放入 `~/.agents/skills/`。

在 Codex 中输入 `$outcome-guard` 可显式使用；技能也允许按任务自动选用。若技能列表未刷新，重新启动 Codex。

若希望各项目的相关任务都默认使用，在 `~/.codex/AGENTS.md` 中**追加**下面这段，不要覆盖已有规则。使用自定义 `CODEX_HOME` 时，修改该目录中的 `AGENTS.md`。

```text
处理多步骤制作、实施、续做、返工或准备报告完成时，读取并应用用户级技能 ~/.agents/skills/outcome-guard/SKILL.md。
区分最终用途、本轮授权交付和内部步骤；内部验证通过不等于任务完成。
研究结论须落到产物要求和检查证据，局部修改后重查相关核心要求。
尊重用户最新的暂停、讨论和范围限制。普通问答与闲聊无需套用。
```

## 适用范围

适合设计、代码、文档等多步骤工作；简单问答不增加流程。尊重用户暂停、只规划或只修改局部的要求，不增加发布、付费等权限。

这是执行指导，不是强制拦截器，不能保证 AI 永不出错，也不会自动同步到普通 ChatGPT、其他设备或云端。已通过技能结构检查，长期效果仍需实际使用检验。

---

**English:** A lightweight Codex skill that keeps multi-step work aligned with the authorized outcome. It turns research into concrete requirements, rechecks the whole result after local edits, and prevents internal milestones from being presented as completed deliverables. It respects scope and pause requests; it is guidance, not a guarantee.
