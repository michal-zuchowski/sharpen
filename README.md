# sharpen

An AI-agent skill that fights skills erosion without slowing you down:

1. **Predict first** — before a non-trivial change the agent asks one question and waits for your answer (`skip` skips it).
2. **One lesson** — a single sentence after each task.
3. **Log** — `~/.sharpen-log.md`; `/sharpen review` turns it into 5 quiz questions.

Doesn't work in fully autonomous modes (e.g. autopilot), since the agent won't wait for answers there.

## Install

Clone the repo first:

```sh
git clone https://github.com/michal-zuchowski/sharpen ~/src/sharpen
```

### GitHub Copilot CLI

```sh
copilot skill add https://raw.githubusercontent.com/michal-zuchowski/sharpen/main/sharpen/SKILL.md
# or symlink the clone:
mkdir -p ~/.copilot/skills && ln -s ~/src/sharpen/sharpen ~/.copilot/skills/sharpen
```

Verify with `copilot skill list` or `/skills` in a session.

### Claude Code

```sh
mkdir -p ~/.claude/skills && ln -s ~/src/sharpen/sharpen ~/.claude/skills/sharpen
```

### OpenAI Codex CLI

```sh
mkdir -p ~/.codex/skills && ln -s ~/src/sharpen/sharpen ~/.codex/skills/sharpen
```

### Shared `.agents` location (read by several tools, incl. Copilot CLI)

```sh
mkdir -p ~/.agents/skills && ln -s ~/src/sharpen/sharpen ~/.agents/skills/sharpen
```

### Per project

Copy `sharpen/` into `.github/skills/`, `.claude/skills/` or `.agents/skills/` in your repo.

### Tools without skill support (Cursor, Gemini CLI, Aider…)

Paste the body of `sharpen/SKILL.md` (without frontmatter) into the rules file: `.cursor/rules/sharpen.mdc`, `GEMINI.md`, `AGENTS.md` or `CONVENTIONS.md`.

## Update

```sh
git -C ~/src/sharpen pull
```

Symlinks pick up changes automatically. `copilot skill add` copies the file — re-run it to update.
