# 添加一个 skill

1. 在 `skills/` 下新建目录，例如 `skills/meeting-notes/`。
2. 在目录内写入 `SKILL.md`。`name` 与目录名一致，`description` 说明什么时候使用、会交付什么。正文写清执行步骤。
3. 把该 skill 专用的资料放在同目录的 `references/`，可执行脚本放在 `scripts/`。多个 skill 共用的资料放在仓库的 `shared/references/`，并在 `shared/manifest.json` 中记录文件名及使用它的 skill 名称列表。
4. 在仓库首页的 README 中登记名称、用途和相对链接。加入首个 skill 时，一并更新首页的空目录说明。

下面是 `SKILL.md` 的最小示例。

```markdown
---
name: meeting-notes
description: 当用户提供会议逐字稿并要求整理纪要时，提取决定、待办事项和待确认的问题。
---

# 整理会议纪要

1. 从逐字稿中提取已作出的决定。
2. 列出待办事项，并附上发言中明确指定的负责人和日期。
3. 将会上遗留的问题单独列出，供下次跟进。
```

Claude Code 会从插件根目录的 `skills/` 发现新条目。在仓库根目录运行以下命令可检查插件与市场清单。

```sh
claude plugin validate .claude-plugin/plugin.json
claude plugin validate .claude-plugin/marketplace.json
```
