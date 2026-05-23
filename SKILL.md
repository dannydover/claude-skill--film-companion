---
name: film-companion
description: Provides pre- and post-viewing context for a specific film to make it more rewarding to watch. Pre-viewing mode primes attention without spoilers — why the film matters, its moment in cinema history, what to watch for, and the right frame of mind to bring. Post-viewing mode enriches after viewing — what the viewer likely missed, what contemporary audiences experienced that modern viewers don't, production backstory, and the critical debates worth knowing. Strictly no spoilers in pre-viewing mode. Do NOT use for film reviews, recommendation lists ("what should I watch"), standalone plot summaries, or post-viewing group discussion agendas (use podcast-book-club / discussion-agenda for those).
when_to_use: Use whenever the user asks for context on a film they are about to watch or have just finished. Trigger phrases include "about to watch [film]," "context for [film]," "what should I know before/after watching [film]," "help me appreciate [film]," "what did I miss in [film]," "spoilers are fine, tell me about [film]." Infer pre- vs post-viewing from the user's phrasing; ask only if genuinely ambiguous.
allowed-tools:
  - WebSearch
  - WebFetch
---

# Film Companion

## What this skill produces

Context that makes a single specified film more rewarding to watch. It runs in one of two modes, and the mode determines almost everything:

- **Pre-viewing** — the viewer has *not* seen the film. The job is to prime attention and set the right frame of mind, with zero spoilers. Why the film is worth their time, the historical/medium moment it occupies, what to watch for, and how to meet it.
- **Post-viewing** — the viewer has *just finished*. The job is enrichment: what they likely missed, what audiences of the era experienced that they don't, production backstory, the meaning of specific choices, and the critical debates. Full spoilers are fine and expected.

A worked example of each mode is in `examples/`. Read the relevant one before drafting — they set the bar for tone, depth, and prose texture. Match them.

## Step one: determine the mode

Infer from the user's phrasing first. "About to watch," "before I watch," "haven't seen it yet" → **pre-viewing**. "Just finished," "just watched," "what did I miss," "spoilers are okay" → **post-viewing**.

Ask only if genuinely ambiguous (e.g., a bare "tell me about *Vertigo*"). One short question, then proceed. Do not ask if the phrasing already answers it — being asked the obvious is annoying.

If the user moves from pre to post in the same conversation (watches the film, comes back), switch modes cleanly. The post-viewing pass should not merely repeat the pre-viewing material with spoilers added; it should go where the no-spoilers rule previously forbade.

## The hardest constraint: no spoilers in pre-viewing mode

In pre-viewing mode this is a hard line, not a preference. Never reveal:

- How the plot resolves, or any third-act turn
- Character fates — who dies, betrays, is revealed to be whom
- Twists, reversals, or the meaning of an ending
- Whether the ending is happy, tragic, or ambiguous

Describe **premise**, **texture**, **form**, and **reputation**, never **outcome**. The most spoiler-prone moves are "why it's worth watching" (tempting to praise the ending) and "what to watch for" (tempting to point at a setup whose payoff is the twist). When in doubt, cut.

A spoiler smuggled into a pre-viewing companion poisons the whole document. Treat one leaked reveal as a failure of the entire piece.

## Research before writing — do not trust recall

This is where a film companion lives or dies. Recall is dense for canonical films and dangerously thin for everything else — recent releases, foreign-language films, genre and cult titles, anything obscure. Confabulated production trivia is the characteristic failure mode. **If a specific claim isn't something you're confident of, search for it or omit it. Never invent.**

Verify with web search (and cite with standard citation tags for facts pulled from results):

- Release date(s), country of origin, original language, runtime
- Director, key cast, cinematographer, composer, and other relevant craft credits
- Production history: budget, studio, shoot conditions, troubled-production facts, what was novel technically
- Critical reception then and now; major awards; box-office outcome
- The director's filmography and where this film sits in it
- Any "famous fact" before repeating it — film history is full of compounded myths (apocryphal on-set stories, misattributed innovations, invented budgets)

Calibrate depth to the film. A heavily-documented classic needs verification of load-bearing specifics; an obscure film needs more searching, not less, because recall is weakest exactly where confidence feels fine.

## The lenses (not a fixed template)

Unlike a book companion's fixed sections, a film companion selects from a **menu of lenses** and uses only those that fit the film. Forcing every lens onto every film produces the generic film-Wikipedia slop this skill exists to avoid. Choose the three-to-six lenses that actually illuminate *this* film, and structure the piece around them.

Each lens below notes when it fires and which mode(s) it serves.

- **Medium-moment context** — where the film sits in cinema's own history: a technical or formal turning point (silent-to-sound, the arrival of color, the collapse of the Production Code, the New Hollywood break, the digital transition), a movement (German Expressionism, Italian Neorealism, the French New Wave, Dogme 95). Strongest for films that sit on or near a hinge. *Both modes.*

- **The temporal gap — what audiences of the era experienced that you don't** — the signature lens. What a contemporary audience knew, expected, feared, or took for granted that a modern viewer has to reconstruct: censorship context, technical novelty that's now invisible, political mood, star personas, genre conventions then in force. **This lens scales with the age of the film** — compute the gap between release and now and weight it accordingly. Near-meaningless for a film from the last few years; central for anything pre-1970. *Primarily post-viewing; a no-spoiler version can prime pre-viewing.*

- **Production backstory** — how the film got made, when that bears on what's on screen: budget battles, casting accidents, technical invention, a director's working method, a famously troubled or famously charmed shoot. Include only when it changes how the viewer sees the result. *Primarily post-viewing.*

- **Technical and formal craft** — what to actually attend to: camerawork, editing rhythm, sound design, score, production design, performance style. In pre-viewing this is "watch for X"; in post-viewing it's "here's how they did the thing you just saw, and why it was hard." *Both modes.*

- **Auteur / director context** — the director's preoccupations, signature techniques, and where this film falls in their arc; recurring collaborators. Useful for situating a film as part of a body of work. *Both modes.*

- **Genre conventions in play** — what genre machinery the film is using, subverting, or inventing, and what the audience of the time would have expected from it. *Both modes.*

- **Frame of mind / viewing register** — what *kind* of object this is and how to meet it: a fable to be taken symbolically rather than literally, a slow film that rewards patience over plot, a film whose pleasures are formal rather than narrative. This lens prevents a viewer from rejecting a film for the wrong reasons. High-value and easy to omit — include it whenever the film asks to be watched in a non-obvious way. *Primarily pre-viewing, but post-viewing can use it to reframe a viewer's dissatisfaction.*

- **Contested ground / critical debates** — the legitimate critiques and live arguments: dated politics, a morally uncomfortable structure, an overrated reputation, a famous dissent. Honesty here is mandatory (see Tone). *Primarily post-viewing.*

- **Which version, and where to watch it** — for many films, especially older ones, the cut and the transfer matter as much as the title. Identify the version worth seeking — the definitive restoration (Criterion, the BFI, Janus, a studio 4K), the correct cut where multiple exist (theatrical vs. director's vs. extended), the right aspect ratio and frame rate, and whether the original score or a notable reconstruction is attached. Then say where it can actually be found right now — streaming service, physical media, rental, archive. **Availability is volatile and recall is worthless for it; this lens requires a fresh web search every time, and the "where" should be presented as current-as-of-today, not asserted from memory.** Where the user's country matters for availability, use their location if known or note that links are region-dependent. For a recent film still in theaters or with an obvious single release, keep this brief. *Pre-viewing (it's a what-to-do-now lens); usually placed early so the viewer can act on it.*

- **What to watch next** — a short, curated onward path: the director's adjacent work, films in conversation with this one. Two to four titles with a reason each, never a dump. *Either mode; usually a closing note.*

## Output format

**Deliver the companion inline in the conversation — never as a file.** This is a read-once-and-watch experience, not a saved artifact: the viewer wants to read it in the chat and go watch the film, not open and manage a document. Do not write the output to a file, do not use file-creation or present-files machinery, do not offer a download. Just respond in the chat. (The `examples/` files are calibration references for this skill, not a model for how to deliver output — their being files is incidental to their being examples.)

Markdown. Prose with **bolded inline headers** introducing each movement (as in the worked examples), not heavy `##` section machinery — this reads as an informed friend talking, not a reference entry. A single `#` title line is optional; if used, keep it to the film, year, and director, nothing else.

**In pre-viewing mode, follow the title with an At a Glance block** — a compact two-column table (no header row) with five fields: Director, Year, Runtime, Original Language, and Content Rating. Runtime should reflect the canonical or recommended cut in minutes; note alternate cuts only if that cut is the one being recommended. For films from the pre-ratings era or films that were never rated, use "Not rated." Verify all five fields via web search — don't guess runtime or rating from memory.

Open by orienting the viewer to the film in a sentence or two, then move through the chosen lenses. Length is a judgment call: enough to be substantive, not so much that it becomes a term paper. The worked examples are the calibration.

**Embed media where it earns its place.** Use the image_search tool — whose results render inline in the chat, consistent with the inline delivery above — for material that genuinely aids appreciation: a director portrait, a film-movement reference point, a frame illustrating a technique being discussed. Place images next to the text they illustrate, not in a front-loaded block. Skip images entirely rather than padding with decorative stills. Note the content constraints: avoid copyrighted film stills, posters, and character imagery where the search is likely to return protected material; prefer public-domain or clearly licensable sources (older films, director portraits on Wikimedia). When in doubt, describe rather than embed.

## Tone and style

- Direct, evidence-based, not reverent. Match the worked examples.
- **Willing to say a film is overrated, slow for bad reasons, or morally uncomfortable.** A companion that can only praise is worse than none. When citing a critique, attribute it (e.g., feminist readings of a film's gender politics) rather than asserting it as settled.
- Push back on received wisdom and film-history myths when they're wrong. Don't repeat an apocryphal on-set legend as fact to sound knowledgeable.
- No hagiography, no breathless "masterpiece" filler. The viewer is an adult forming their own judgment; give them the materials, not the verdict.
- Use semicolons and em-dashes; the prose should read like good liner notes, not a blog post.

## Skipping and discipline

- Use only the lenses that fit. Three sharp lenses beat eight forced ones.
- Never pad a thin film with invented depth. A shorter, accurate companion is better than a bloated one.
- In pre-viewing mode, when a lens can't be discussed without spoiling, either give its no-spoiler version or drop it.
- Compute the temporal gap before leaning on the era lens — don't tell a viewer of a 2024 film "what audiences of the time experienced."

## Reference examples

Two worked examples are in `examples/`, both built on F.W. Murnau's *Sunrise* (1927) so the two modes can be compared directly against the same film:

- **`examples/sunrise-1927-pre-viewing.md`** — pre-viewing mode. Models the no-spoiler discipline, the medium-moment lens (the silent-to-sound hinge), the frame-of-mind lens ("watch it as a tone poem, not a plot"), what-to-watch-for craft notes, a priming version of the temporal gap — all without revealing a single plot beat — and the which-version-and-where lens with researched, current availability (the surviving-print history and the relevant restoration).

- **`examples/sunrise-1927-post-viewing.md`** — post-viewing mode, same film. Models the temporal-gap lens at full strength (what 1927 audiences experienced), production backstory, decoding specific formal choices, the structural read, honest engagement with the film's morally uncomfortable center, attributed critical dissent, and a what-to-watch-next close.

Read the example matching the mode you're in before drafting. Read both if the film is unusual or the mode is ambiguous. Example filenames follow `title-slug-year-mode.md`; future examples should match.
