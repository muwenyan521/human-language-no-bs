# Human language / No-BS prompts

一组用于减少 Agent AI 腔的通用提示词，以及一个用于项目内容去 AI 味的 Miyu Skill。

## Contents

- `prompts/human-language-no-bs-system-prompt.en.txt`：英文通用系统提示词
- `prompts/human-language-no-bs-system-prompt.zh-CN.txt`：简体中文通用系统提示词
- `prompts/human-language-no-bs-system-prompt.zh-CN.annotated.txt`：带来源注释的中文版本
- `skills/project-content-unslop/`：项目内容去 AI 味 Skill
- `package.toml`：Miyu package metadata

## What it targets

- boilerplate, apologies, defensive writing, repetition, process narration, and sycophancy;
- inflated abstractions such as unnecessary "contract", "matrix", and Chinese "契约", "矩阵", "门禁";
- documentation written as field dumps, pseudo-schemas, and example-code piles;
- unnecessary Chinese-English mixing and technical vocabulary;
- Chinese translationese, including English-shaped modifiers, passives, empty verbs, literal preposition frames, and comma-heavy sentences;
- project documentation that repeats the same fact across features, support, dependencies, security, and verification sections.

The rules preserve facts, evidence strength, links, technical terms, code, structured data, warnings, citations, and the project's existing voice. They do not try to evade AI detectors or manufacture human mannerisms.

## Miyu

Install the Skill package from the repository root:

```bash
miyu pkg install ./
```

The Skill takes effect in the next turn.

## Use the system prompt

Copy the prompt that matches the Agent and language. Use the annotated Chinese version for maintenance and source review, not as the deployed prompt unless you want the comments included.

## Scope

The system prompts are general behavior and writing rules. The Skill is narrower: it edits prose written for people in a project, such as README files, documentation, release notes, UI copy, issues, pull requests, and announcements. It does not rewrite source code or structured data.

## Status

This is a composite prompt and Skill assembled from the sources listed in `NOTICE.md`. The files are maintained as a practical fork and are not official releases of those projects.
