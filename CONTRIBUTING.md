# 向唯庸创作盒添加 skill

1. 在 `skills/` 下新建一级目录，例如 `skills/interview-outline/`。用小写英文和连字符命名，让名称能说明这个工具做什么。
2. 在目录内写入 `SKILL.md`。`name` 与目录名一致，`description` 说明什么时候使用、需要哪些输入、会交付什么。正文写清执行步骤。
3. 将这个 skill 用到的示例和参考资料放在同目录的 `references/`，可执行脚本放在 `scripts/`。多项工具共用的源资料可集中维护在仓库的 `shared/references/`，并在 `shared/manifest.json` 登记文件名与使用它的 skill。如果单独安装也需要某份资料，请将发布所需的副本随 skill 一起提供。
4. 在[首页](./README.md)对应的创作场景下添加相对链接，用一句话说明交付物。一个工具适合多个场景时，各处都链接到同一份 `SKILL.md`。发布第一项工具时，同步更新首页的收录状态。

下面用「把采访整理成文章提纲」演示 `SKILL.md` 的写法。

```markdown
---
name: interview-outline
description: 当用户提供采访逐字稿并准备写文章时，按主题整理文章提纲，标出可引用的原话和需要补问的细节。
---

# 把采访整理成文章提纲

1. 找出这次采访能回答的读者问题，按问题组织小标题。
2. 为每个小标题选一段原话，保留说话人和原文，便于回查。
3. 单列还需要补问的事实，供作者下一次采访使用。
```

Claude Code 会从插件根目录的 `skills/` 发现新条目。在仓库根目录运行以下命令可检查插件与市场清单。

```sh
claude plugin validate .claude-plugin/plugin.json
claude plugin validate .claude-plugin/marketplace.json
```
