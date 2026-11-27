# sharpen

Skill dla agentów AI ograniczający skills erosion bez spowalniania pracy:

1. **Najpierw zgadnij** — przed nietrywialną zmianą jedno pytanie, agent czeka na odpowiedź (`skip` pomija).
2. **Jedna lekcja** — 1 zdanie po zadaniu.
3. **Log** — `~/.sharpen-log.md`, `/sharpen review` robi z niego 5 pytań.

Nie działa w trybach autonomicznych (np. autopilot), bo tam agent nie czeka na odpowiedzi.

## Instalacja

Najpierw sklonuj repo (prywatne, wymaga dostępu):

```sh
gh repo clone michal-zuchowski/sharpen ~/src/sharpen
```

### GitHub Copilot CLI

```sh
copilot skill add ~/src/sharpen/sharpen/SKILL.md
# albo ręcznie:
mkdir -p ~/.copilot/skills && ln -s ~/src/sharpen/sharpen ~/.copilot/skills/sharpen
```

Sprawdź: `copilot skill list` lub `/skills` w sesji.

### Claude Code

```sh
mkdir -p ~/.claude/skills && ln -s ~/src/sharpen/sharpen ~/.claude/skills/sharpen
```

### OpenAI Codex CLI

```sh
mkdir -p ~/.codex/skills && ln -s ~/src/sharpen/sharpen ~/.codex/skills/sharpen
```

### Standard `.agents` (wspólny dla kilku narzędzi, m.in. Copilot CLI)

```sh
mkdir -p ~/.agents/skills && ln -s ~/src/sharpen/sharpen ~/.agents/skills/sharpen
```

### Per projekt

Skopiuj `sharpen/` do `.github/skills/`, `.claude/skills/` lub `.agents/skills/` w repo.

### Narzędzia bez obsługi skilli (Cursor, Gemini CLI, Aider…)

Wklej treść `sharpen/SKILL.md` (bez frontmattera) do pliku reguł: `.cursor/rules/sharpen.mdc`, `GEMINI.md`, `AGENTS.md` lub `CONVENTIONS.md`.

## Aktualizacja

```sh
git -C ~/src/sharpen pull
```

Symlinki podchwycą zmiany automatycznie (`copilot skill add` kopiuje plik — dodaj go ponownie).
