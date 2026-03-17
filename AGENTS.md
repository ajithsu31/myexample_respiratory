# AGENTS.md

## Cursor Cloud specific instructions

### Project overview

This is **Project Finch Auto-Rater** — a documentation/configuration-only repository. It contains no application code, no build system, no package manager, and no runtime dependencies. The "product" is a structured evaluation rubric delivered in two formats:

- **Cursor rule** (`.cursor/rules/project-finch-auto-rate.mdc`) — auto-applies inside Cursor IDE when a Project Finch agent conversation is pasted.
- **GPT prompt** (`GPT_Prompt_for_Auto_Rating.txt`) — standalone system prompt for ChatGPT.

### No services to run

There are no servers, databases, containers, or processes to start. The repository is entirely static text files (Markdown, `.mdc`, `.txt`).

### Lint / Test / Build

There is no linter, test framework, or build system configured. Validation consists of verifying:
- The `.mdc` file has valid YAML frontmatter (`---` delimiters, `description` and `alwaysApply` fields).
- All 4 evaluation sections are present in both the Cursor rule and GPT prompt (Solvability, Expected Solution, Agent Solution, Evaluators).
- The README documents usage, workflow categories, and common annotator mistakes.

### Branch topology

Content lives on feature branches (not yet merged to `main`). The `main` branch only has the initial commit with a stub README. Check `git log --all --graph --oneline` to see the full branch structure.

### How to use the Cursor rule

1. Ensure `.cursor/rules/project-finch-auto-rate.mdc` exists in the project.
2. Open Cursor IDE and paste a Project Finch agent conversation.
3. The rule auto-applies and evaluates across 4 sections.

### How to use the GPT prompt

1. Copy `GPT_Prompt_for_Auto_Rating.txt` as a system prompt in ChatGPT.
2. Paste a Project Finch agent conversation as the user message.
