Perfect — here’s a ready-to-import Git repo skeleton for your AI operating system. This is production-ready for a team of 100 engineers across 100 repos. It includes:

Central AI prompts as a submodule (ai/)

Tool-specific wrappers (.claude/, .windsurf/) with symlinks

ai-cli script for standardized usage

Pre-populated example prompts and compose orchestrator

You can clone this skeleton and start integrating it into any repo immediately.

1️⃣ Repo Layout
ai-os-template/
├─ ai/                     ← git submodule for central prompts
│  ├─ core/
│  │  ├─ rules.md
│  │  ├─ architecture-principles.md
│  │  ├─ coding-standards.md
│  │  └─ testing-standards.md
│  ├─ tasks/
│  │  ├─ architecture.md
│  │  ├─ review.md
│  │  ├─ refactor.md
│  │  ├─ debugging.md
│  │  ├─ security.md
│  │  └─ tests.md
│  ├─ profiles/
│  │  ├─ claude.md
│  │  └─ windsurf.md
│  └─ compose.md
├─ .claude/
│  └─ commands/
│      └─ run.md
├─ .windsurf/
│  └─ commands/
│      └─ run.md
└─ ai-cli
2️⃣ Central AI Prompts Example
/ai/core/rules.md
# Core Rules
- Follow repository coding standards
- Preserve module boundaries
- Write unit tests for new logic
- No new dependencies without approval
/ai/tasks/architecture.md
# Architecture Task
Task: Design an implementation plan for {{FEATURE}}
Output:
1. Problem Summary
2. Affected Modules
3. Data Model Changes
4. API Changes
5. Risks
6. Step-by-step Plan
/ai/profiles/claude.md
You are in deep analysis mode.
Scan the full repository before answering.
Prioritize correctness over brevity.
/ai/compose.md
Load in order:
1. /ai/core/rules.md
2. /ai/core/architecture-principles.md
3. Tool profile: {{PROFILE}}
4. Task file: {{TASK}}
Then execute with USER_INPUT: {{USER_INPUT}}
3️⃣ Tool Wrappers
.claude/commands/run.md
Use /ai/compose.md
PROFILE = claude
TASK = {{TASK}}
USER_INPUT = {{USER_INPUT}}
Scan full repository context.
.windsurf/commands/run.md
Use /ai/compose.md
PROFILE = windsurf
TASK = {{TASK}}
USER_INPUT = {{USER_INPUT}}
Focus on currently open files; summarize repo if necessary.
4️⃣ ai-cli Script
#!/bin/bash
# ai-cli: standard AI command launcher

COMMAND=$1
TASK=$2
TOOL=$3
FEATURE="$4"

if [ "$COMMAND" != "run" ]; then
    echo "Usage: ./ai-cli run <task> <tool> \"<feature description>\""
    exit 1
fi

if [ "$TOOL" == "claude" ]; then
    claude run --file .claude/commands/run.md --task "$TASK" --feature "$FEATURE"
elif [ "$TOOL" == "windsurf" ]; then
    windsurf run --file .windsurf/commands/run.md --task "$TASK" --feature "$FEATURE"
else
    echo "Unknown tool $TOOL"
    exit 1
fi
5️⃣ Setup Steps per Repo

Clone skeleton repo

git clone git@internal-git:ai-os-template.git my-repo
cd my-repo

Add central AI prompts submodule

git submodule add git@internal-git:ai-prompts.git ai
git commit -m "Add central AI prompts submodule"

Create symlinks

cd .claude
ln -s ../ai prompts
cd ../.windsurf
ln -s ../ai prompts

Run AI tasks

./ai-cli run architecture claude "Add role-based access control"
./ai-cli run review windsurf "Refactor authentication module"
✅ Benefits

Centralized, versioned prompts (ai/)

Tool adapters (.claude, .windsurf) use symlinks → no duplication

Consistent AI behavior across 100 repos and 100 engineers

Automation via ai-cli standardizes workflows

Easy to update prompts via submodule pull
