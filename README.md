# film-companion

A [Claude Code skill](https://docs.anthropic.com/en/docs/claude-code/skills) that helps a film viewer get more value from any given film. It runs in two modes — one for before you watch which contains no spoilters, and one for after you watch to tell you what you might have missed.

## What it does

**Pre-viewing mode** — primes attention without spoilers. You get: why the film is worth your time, the historical and cinematic moment it occupies, what to watch for technically and formally, the right frame of mind to bring, and where to find the best version to watch.

**Post-viewing mode** — enriches after you've seen it. Full spoilers are on the table. You get: what you likely missed as a modern viewer, what contemporary audiences experienced that you can't, the production backstory, how specific formal choices work, the live critical debates, and what to watch next.

The skill uses a menu of lenses rather than a fixed template — it picks the three to six that actually illuminate the film, and skips the rest. It also does fresh web searches for facts and availability rather than trusting recall, so it's less likely to confabulate production trivia or cite unavailable streaming links.

## Usage

Trigger phrases Claude will recognize:

- *"I'm about to watch [film] — give me some context"*
- *"What should I know before watching [film]?"*
- *"Help me appreciate [film]"*
- *"I just finished [film] — what did I miss?"*
- *"Spoilers are fine, what should I know about [film]?"*
- *"Context for [film]"*

Claude infers the mode from your phrasing. It will ask only if genuinely ambiguous (e.g., a bare "tell me about *Vertigo*").

**What this skill is not for:**
- Film recommendations ("what should I watch?")
- Standalone plot summaries
- Reviews or star ratings
- Post-viewing group discussion agendas (use the `discussion-agenda` or `podcast-book-club` skills for those)

## Installation

Skills can be installed at the user level (available in all projects) or the project level.

**User-level** (recommended for personal use):
```bash
mkdir -p ~/.claude/skills
git clone https://github.com/yourusername/claude-skill--film-companion ~/.claude/skills/film-companion
```

**Project-level** (available only in a specific project):
```bash
mkdir -p .claude/skills
git clone https://github.com/yourusername/claude-skill--film-companion .claude/skills/film-companion
```

After installing, restart Claude Code (or reload the window) so it picks up the new skill.

## Examples

The [`examples/`](examples/) directory contains worked output for *Sunrise: A Song of Two Humans* (1927):

- [`sunrise-1927-pre-viewing.md`](examples/sunrise-1927-pre-viewing.md) — models no-spoiler discipline, medium-moment context (the silent-to-sound hinge), what-to-watch-for craft notes, and a researched version/availability note.
- [`sunrise-1927-post-viewing.md`](examples/sunrise-1927-post-viewing.md) — models the temporal-gap lens at full strength, production backstory, structural analysis, and honest engagement with the film's contested moral center.

## Adding new examples

Example filenames follow the pattern `title-slug-year-mode.md` (e.g., `vertigo-1958-post-viewing.md`). Add new examples by placing a file in `examples/` and referencing it in `SKILL.md` if appropriate.

## License

Apache 2.0
