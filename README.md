# Concise

A writing skill for short, focused responses from Claude, Fable, Sol, Astra, and other agents. Default to one to three short sentences, lead with the answer, and stop when the request is satisfied. Add detail only when needed.

[SKILL.md](SKILL.md) contains the instructions. It covers answers, progress updates, completion reports, and code comments. Brevity changes how the work is reported, not how thoroughly it is performed.

Code comments briefly explain the nearby code's current purpose or constraints. They omit edit history, prior attempts, and conversation details.

```cpp
// Keep the buffer alive until the GPU finishes reading it.
```

Original inspiration: [Ayoub Ghriss](https://github.com/ayghri). See [LICENSE](LICENSE).

## Installation

Install once into the shared agent skills directory, then symlink it into each agent's skills folder.

```bash
git clone git@github.com:rygo6/Concise-AGENTS.git ~/.agents/skills/concise
```

Then link it into the agents you use:

```bash
mkdir -p ~/.claude/skills ~/.codex/skills
ln -s ~/.agents/skills/concise ~/.claude/skills/concise
ln -s ~/.agents/skills/concise ~/.codex/skills/concise
```

On Windows, use `mklink /J` to create a junction instead (run in `cmd`, no admin rights needed):

```bat
mklink /J "%USERPROFILE%\.claude\skills\concise" "%USERPROFILE%\.agents\skills\concise"
mklink /J "%USERPROFILE%\.codex\skills\concise"  "%USERPROFILE%\.agents\skills\concise"
```

## Usage

Once installed, request the `concise` skill by name or use your agent’s skill picker or invocation syntax.
