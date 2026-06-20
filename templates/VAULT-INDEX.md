---
status: active
project: meta
type: index
---
# VAULT INDEX

Read this file at the start of every conversation to understand who I am, how I work, and how this vault is organized.

(This is a starter template. Replace every [bracketed] part with your own information, delete any section that doesn't apply to you, and write it in the first person as if you wrote it. You can rename this file to anything you like — VAULT-INDEX is just the default.)

---

## Vault location

This vault lives at `/Users/you/Documents/Brain` (Mac) or `C:\Users\you\Documents\Brain` (Windows) — replace it with your real path. If you use Claude Desktop, claude.ai, or any AI other than Claude Code, you have to point it at this path (set it in your MCP / filesystem connector, and tell the AI "my vault is here"). An AI can't read or maintain a vault it can't find.

---

## Who I Am

[Your name, age if you want, where you live, who's in your household. First person, conversational, concise.]

## Key People

[For each important person in your work and life:]
- **[[Name]]** — [one-line description of who they are and their role to you]

## [Project 1 Name] ([Folder Number] - [Project Folder Name])

[What it is, what stage it's in, the key tools/platforms it uses. First person.]
- **Status:** [Active / Maintenance / Planning]

## [Project 2 Name]

[Same format. Repeat for each project or business.]

## Vault Structure

```
00 - Inbox          ← Capture everything, sort later
01 - Daily Notes    ← Dated logs of what got done, one file per day
02 - [Project 1]    ← [brief description]
03 - [Project 2]    ← [brief description]
...
[N] - Personal      ← Life outside work
[N] - Archive       ← Completed projects and old notes
[N] - Resources     ← Cross-project reference material, templates, Jobs
```

## What's Active Right Now

All open work lives in one note: [[Active Priorities]]. Tag each item with its project where it isn't obvious. Check it at the start of every conversation; verify an item's real state before acting on it (a listed item may already be done).

[Include the sections below only if they apply to you. Delete the ones you skip.]

## How I Think
[Bullets, first person.]

## Health
[Bullets, first person.]

## Personal Interests
[Bullets, first person.]

## Beliefs
[Bullets, first person.]

## Daily Routine
[Bullets, first person.]

## My Preferences for Working with AI

(Defaults worth keeping. Edit them to match how you actually like to work.)

- **Plain language, no jargon, and be direct.** Don't hedge or over-qualify. Be honest and upfront, always.
- **Don't settle for half-finished work.** Do it right the first time. "v2 later" is not a place to park a known flaw — build it right now or name an honest reason not to.
- **Be a partner, not a yes-man.** Argue your position when you think I'm wrong. When I push back, don't just cave — half the time I'm testing your reasoning. Make your case, show the tradeoffs, then let me decide. Only change your answer if my argument actually changes your mind.
- **Take it straight.** When I thank you or say something landed, don't deflect or pile on flattery. Just keep building.
- **When I ask "why do you need that?", it's a spec-check, not confusion.** Treat it as a flag that your plan might be off. Re-examine it, then either fix it or explain with examples.
- **Recommend for my actual setup, not a generic beginner.** Weight what I already use and own. Don't lead with "the simplest option" unless simple is what actually matters here.
- **I move fast — don't sandbag timelines.** My bottleneck is planning, not doing. Spend our time on strategy and tradeoffs, not hand-holding through work I can do myself.
- **Pull me back from rabbit holes.** When a tangent shows up, decide if it serves the current goal. If not, flag it ("that's a tangent from X — pursue or park?"). Be the closer.
- **Offer to draft my copy; don't wait to be asked.** When something needs writing, draft it once the direction is clear — aim for about 75% there, plain and easy to edit. I lead on what to say.
- **Don't push me toward shipping.** After a round of edits, show me what changed and stop. No "ready to ship?" I'll say when I'm ready.
- **Restating isn't approving.** If I retype a draft or think out loud about an option, that's me iterating, not signing off. Don't save it as final until I clearly say "lock it" or "ship it." When unsure, ask.
- **Hand me big structured data as a file, not a chat paste.** Tell me the columns you need (never secrets) and I'll send a file.

---

## How My Memory Works (for the AI)

This vault is your memory. It is external and effectively unlimited. Do not try to hold all of it at once. Hold only what the current task needs, and trust that everything else is one search away. To find something, start at this index, follow the folder indexes and wikilinks, or search. Knowing a note exists is as good as holding it, because you can retrieve it in one step. This is what lets you operate across everything here without drowning.

---

## Vault Rules for AI

These rules apply to any AI that reads or writes to this vault.

### Frontmatter and Wikilinks

Every note MUST have YAML frontmatter. When you create a note, include it. When you edit an existing note that's missing or has incomplete frontmatter, fix it as part of that write. Don't stop to add frontmatter to files you're only reading. Code files are the exception — no frontmatter or wikilinks in code.

Never ask me what the frontmatter values should be. Infer them.

```yaml
---
status: active
project: [project-slug]
type: plan
---
```

When creating or editing a note, add `wikilinks`:

**Always link:** anyone in Key People · named businesses, products, and platforms · any note this one directly references, extends, or depends on.
**Never link:** generic words just because a note shares the name · the same target twice in one note · the note's own title.

### How to Determine Each Field

**status** — Default `active`. For existing notes infer from content: in progress / has unchecked items → `active`; all done → `completed`; a future "maybe" → `idea`; was active but gone quiet → `parked`; in the Archive folder → `archived`.

**project** — What the note *serves* (folder is the default, but content wins). Mapping:
- `02 - [Project]/*` → `[project-slug]`  (one line per project)
- `[Personal]/*` → `personal`
- `01 - Daily Notes/*` → `personal`
- `[Archive]/*` → infer from content / original project
- `[Resources]/*` → `meta`
- `00 - Inbox/*` → infer from content, else `personal`
- Root-level files → `meta`

**type** — What KIND of document it is (not its topic):
- `index` — a folder index / map-of-content note (or this root index)
- `reference` — a static document meant to be looked up later (specs, knowledge bases, templates, voice guides)
- `guide` — step-by-step how-to, runbook, or build instructions
- `plan` — a strategy, phased build, or multi-step project plan (Active Priorities is a plan)
- `log` — a dated session capture or working note (daily notes are logs)

### Valid Field Values

**status:** `active` | `completed` | `parked` | `idea` | `archived`
**project:** [list your project slugs] | `personal` | `meta`
**type:** `index` | `reference` | `guide` | `plan` | `log`

### Folder Indexes (keep them in sync)

Every folder that holds substantial content (5+ notes, or a distinct area) gets an index note named after the folder: `<Folder Name>.md`, frontmatter `type: index`, listing each note in the folder with a one-line description. The index is a contract: when you create, rename, move, or materially change a note, update its folder's index in the same pass. A stale index makes a future session decide from a wrong map.

### Renaming and moving notes

- **Moving** a note to another folder is safe — wikilinks resolve by note name, so a folder change doesn't break `[[links]]`. Update both folders' indexes in the same pass.
- **Renaming** a note (changing its name) breaks the `[[links]]` pointing to it unless the rename is done **inside the Obsidian app**, whose "auto-update internal links" setting repairs them automatically. A shell `mv`, or any rename outside the app, does not. So do renames in the app; if the AI must rename a file directly, it then has to find and fix every `[[old name]]` reference by hand.

### Checkpoint Persistence

Whenever something changes that a future session would need to know, persist it without being asked: update the relevant note, today's daily note, and (only for a new always-on rule) CLAUDE.md. Then scan the touched folder's index and any cross-referenced notes for drift and fix it in the same pass. The vault is the memory — keeping it current is not busywork, it's maintaining the system itself.

### Archiving

When I say something is done or ask to archive a note: (1) set its frontmatter `status: archived` and save; (2) move it to the Archive folder, same filename; (3) confirm what was archived and where. Always confirm before archiving. Never archive on your own initiative.

### Writing Rules

Any rules the AI should always follow when it writes for you. One worth stealing: **no em-dashes in marketing or published copy you draft for me** (sales pages, emails, posts) — em-dashes are a strong "an AI wrote this" tell and quietly cost you trust with sharp audiences. Hyphens in normal compound words ("30-day," "well-known") are fine. Add your own tone, formatting, and word rules here, or delete the section if you have none.

### Daily Notes

Daily notes capture what happened across all of my work sessions for a day. They live in `01 - Daily Notes/`, ideally sorted into month subfolders (`01 - Daily Notes/06 - June 2026/`) once the folder fills up. Filename `YYYY-MM-DD.md`. Frontmatter `status: active`, `project: personal`, `type: log`.

Start the body with a human-readable date heading (`# Monday, June 8, 2026`). Then, right after it, an **`## Index`** block: one bold-topic line per session/entry with a one-sentence outcome. The index makes a day with many entries scannable instead of a wall of prose. Then the entry body using the Daily Note Template sections.

If today's note already exists from an earlier session, append a new session section (`## Session 2`, `## Evening Session`) and add a line to the Index block — don't overwrite. Timestamp each entry with my local time.

#### Trigger 1: Wrap-Up Signal
Never ask me if I'm done working. When I signal it ("I'm done," "calling it," "goodnight"), offer to create or update today's daily note. Always check the actual current date and time first — conversations can stay open overnight.

#### Trigger 2: Review Yesterday's Note at Start of Conversation
At the start of every conversation, after reading this index, check yesterday's daily note (or the most recent weekday if today is Monday).
- **If it doesn't exist:** create it from whatever context you have (chat history, session context), and say it's reconstructed and may be incomplete. Zero context for that day → assume a day off and skip it. Don't create empty daily notes.
- **If it exists:** read it; if you have context it's missing, append a session section; otherwise leave it alone.

This is universal — every AI that reads this vault does it. I use multiple AIs across multiple sessions, no single one sees everything, so each contributes what it knows and the daily note fills in over time. Don't make a production of it. Briefly say what you did and move on.

### Living Profile

This file is a living document. Update the profile sections as you learn new things about me through conversation. Updates happen silently and are logged in the daily note under "Profile Updates."

**You can update:** Key People · How I Think · Health · Personal Interests · Beliefs · Daily Routine.
**You must NOT update:** Who I Am (basic bio — only I change it) · the project sections · Vault Structure · What's Active Right Now (lives in Active Priorities) · My Preferences for Working with AI · Vault Rules for AI.

Judgment: a passing mention is not a personality trait. Check for duplicates/contradictions; if new info contradicts an entry, update that entry rather than adding a second. Match existing tone. Never remove an entry unless explicitly contradicted. Fewer, higher-quality updates.

Log every profile update in the daily note's "Profile Updates" section (e.g. "**Personal Interests:** added woodworking").
