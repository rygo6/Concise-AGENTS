# Concise

A writing skill for minimal, direct responses from Claude, Fable, Sol, Astra, and other agents. Ordinary replies target 40 words or fewer: answer, essential verification or limitation, then stop. Requested detail and deliverables can be longer.

[SKILL.md](SKILL.md) defines response budgets, explicit cuts, and short target examples. It suppresses work logs, repeated explanations, unsolicited advice, and unnecessary formatting without reducing the work performed.

Code comments explain only the nearby code's current reason or constraints, usually in one short line. No edit or conversation history.

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
