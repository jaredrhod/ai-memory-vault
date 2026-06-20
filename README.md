# AI Memory Vault

Give your AI a real, persistent memory. This is the open-source system that turns an Obsidian vault into your AI's working memory, so it remembers everything across sessions, lives outside the model with no size ceiling, and pulls back exactly what it needs in one step. Free to use, share, and build on, just not to resell (see LICENSE).

## The build

- **[Second Brain Builder](second-brain-builder.md):** the interactive builder that sets the whole thing up. You run it inside Claude and it interviews you, then builds a complete, self-maintaining system: a boot config, a folder structure around your real projects, daily notes that write themselves, a profile that updates as the AI learns about you, and "Jobs" that teach it to do your recurring tasks your way. Your vault becomes the AI's memory, so it lives outside the model with no size ceiling, and the AI holds only what the current task needs while reaching anything else in one step. Watch the walkthrough: https://www.youtube.com/watch?v=z9YzRqjJo4k

## Templates

Starter files for the system, ready to drop in and fill out. Each one carries a sample vault path so the AI knows where your vault lives.

- **[CLAUDE.md](templates/CLAUDE.md):** the boot config. Goes in the folder you run Claude Code from (your **working directory**), kept **out of your vault** so the vault stays pure notes and doesn't get tangled once you have more than one project. Claude Code auto-loads it every session and points the AI to your vault. Holds your startup sequence and the rules that can't lapse.
- **[VAULT-INDEX.md](templates/VAULT-INDEX.md):** the operating manual. This one lives **inside your vault** (it's a note, not config). Your profile, your projects, the full vault rules, and how you like to work with the AI.
- **[MEMORY.md](templates/MEMORY.md):** the pointer for Claude Code's own memory. Goes in **Claude Code's project folder** (`~/.claude/projects/...`, not your vault). It redirects the native memory back into the vault so you never end up with two memory layers that drift apart.

## License

Copyright (c) 2026 Jared Rhodenizer.

The contents of this repository are licensed under the Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License (CC BY-NC-SA 4.0). You are free to share and adapt them, with attribution, for noncommercial purposes, as long as you license your contributions under these same terms. Full terms are in the LICENSE file and at https://creativecommons.org/licenses/by-nc-sa/4.0/
