# Human language / No-BS

通用 Agent 系统提示词与项目内容去 AI 味 Skill，支持中文和英文，不绑定特定客户端。

系统提示词用于减少对话中的套话、重复、自我解说、防御性表达和无条件附和。Skill 用于清理 README、文档、网站文案、发布说明和其他项目内容，保留事实、技术含义和项目原有语气。

## 安装 Skill

### 通过 Skills CLI

在支持 Skills CLI 的 Agent 中运行：

```bash
npx skills add muwenyan521/human-language-no-bs --skill project-content-unslop
```

按提示选择目标 Agent 和安装范围。可用客户端及安装位置由 Skills CLI 决定。

### 手动安装

克隆仓库：

```bash
git clone https://github.com/muwenyan521/human-language-no-bs.git
```

将 `skills/project-content-unslop/` 整个目录复制到 Agent 的技能目录。必须一起复制其中的 `references/`，不能只复制 `SKILL.md`。

例如，安装到当前项目的 Claude Code 技能目录：

```bash
mkdir -p .claude/skills
cp -R human-language-no-bs/skills/project-content-unslop .claude/skills/
```

其他 Agent 使用各自支持的技能目录；安装后按客户端要求重新加载技能或启动新会话。

### 不支持 Skill 的 Agent

让 Agent 读取 `skills/project-content-unslop/SKILL.md`，并在需要时读取其中引用的参考文件。也可以将这些文件作为附件提供：

```text
请按 project-content-unslop 的规则检查并修改项目文档。
保留事实、命令、链接、技术术语和必要警告，不要改源代码。
```

## 使用系统提示词

从 `prompts/` 选择一个版本，复制到 Agent 支持的系统指令或自定义指令位置：

- [英文版](prompts/human-language-no-bs-system-prompt.en.txt)
- [简体中文版](prompts/human-language-no-bs-system-prompt.zh-CN.txt)
- [带来源注释的简体中文版](prompts/human-language-no-bs-system-prompt.zh-CN.annotated.txt)

带注释版本用于查阅和维护来源。部署时一般使用无注释版本。不同客户端对指令的加载方式和优先级不同，粘贴到普通消息中不等于设置了系统提示词。

## Skill 处理什么

- 宣传腔、空泛抽象词、假深刻、重复总结和客服式开场收尾；
- 不必要的“契约”“矩阵”“门禁”等包装词；
- 把文档写成字段、伪数据结构和示例代码的堆砌；
- 不必要的中英混杂和技术术语；
- 中文翻译腔，包括长定语、空壳动词、机械被动句和英文语序；
- 同一事实在功能、支持范围、依赖、安全和测试说明中反复出现。

规则不用于判定作者身份或规避 AI 检测。不会为了“像人”而编造经历、数据、观点或错误，也不会把正式文档统一改成聊天口吻。

## 文件

```text
prompts/                           三份系统提示词
skills/project-content-unslop/
  SKILL.md                         Skill 入口
  references/
    translationese.md              中文翻译腔参考
    project-content-patterns.md    项目文档常见问题
NOTICE.md                          来源与许可说明
```

## 来源

内容根据公开的写作提示词、Skill 和实际使用反馈整理。来源见 [NOTICE.md](NOTICE.md) 及带注释的中文提示词，不是这些上游项目的官方版本。上游许可不完全一致，重新分发前请核对相应来源的许可。
