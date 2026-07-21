# Concise

An agent skill that shapes output for fast, low-friction reading — leading with concrete next actions, numbering multi-step work, restating state across turns, suppressing tangents, giving specific time estimates, and making wins visible. It is agent-agnostic and works with any coding agent that supports skills (Claude Code, Codex, etc.).

Unlike a reference skill, it vendors no repositories — the behavior lives entirely in `SKILL.md`.

Credit: adapted from [ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd).

## What changes

<table>
<tr>
<td width="50%">

## Before

> Great question! Let me think about this. Your auth flow has a few moving pieces: the middleware, the token verification, and the cookie handling. Looking at `src/auth.ts`, the `verifyToken` function (around lines 42-58) seems to be using an older `jsonwebtoken` API. One approach would be to update the package and rewrite that function. After making the change, you'd want to run the auth tests to confirm nothing breaks. By the way, you might also want to look at your dependency versions overall. Hope this helps! Let me know if you want to dig deeper.

</td>

<td width="50%">

## After

> Run `npm install jsonwebtoken@latest`, then edit `src/auth.ts:42`.
>
> 1. Open `src/auth.ts`
> 2. Replace `verifyToken` (lines 42–58) with the snippet below
> 3. Run `npm test -- auth.spec.ts`
>
> Next: paste the first failing line if any test fails.

</td>
</tr>
</table>

### What it does

| Rule | Effect |
|------|--------|
| Lead with the next action | First line is a command, path, or snippet — never context |
| Number multi-step tasks | Each step is one bounded action |
| End with one concrete next action | Something doable in under two minutes |
| Restate state every turn | Reader never has to hold multi-turn context |
| Specific time estimates | Concrete units, never "some work" |
| Make wins visible | Show what now works, don't bury it in a recap |
| No preamble, recap, or pleasantries | Start with the answer, end when it's done |

## Installation

Install once into the shared agent skills directory, then symlink it into each agent's skills folder.

```bash
git clone git@github.com:rygo6/ADHD-AGENTS.git ~/.agents/skills/concise
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

Once installed, invoke `/concise` from any agent that supports skills.
