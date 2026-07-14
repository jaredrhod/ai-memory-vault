# AI Memory Vault

Give your AI a real, persistent memory. This is the open-source system that turns an Obsidian vault into your AI's working memory, so it remembers everything across sessions, lives outside the model with no size ceiling, and pulls back exactly what it needs in one step. Free to use, share, and build on, just not to resell (see LICENSE).

## The build

- **[ai-memory-vault.md](ai-memory-vault.md):** the build script. Run it inside Claude and it interviews you, then builds a complete, self-maintaining system: a boot config, a folder structure around your real projects, daily notes that write themselves, a profile that updates as the AI learns about you, and "Jobs" that teach it to do your recurring tasks your way. Your vault becomes the AI's memory, so it lives outside the model with no size ceiling, and the AI holds only what the current task needs while reaching anything else in one step. Watch the walkthrough: https://www.youtube.com/watch?v=0VEisejtRJY

## AI Priming

AI Priming is having your AI read a specific set of your notes before it gives you the answer or output you want. For example, before my agent writes a marketing email, it reads my copywriting notes, my email marketing notes, my customer avatar, and my company knowledge base. Then it writes. This is extremely powerful because, with AI, context is king. When you "prime" your AI with the knowledge and skills it needs prior to its output, your results will always be better and more accurate.

Every job gets its own set of notes. An email needs different notes than a Facebook ad. The vault keeps all of your notes organized in one place and tells your AI which notes to read for which job. You set that up once, and your AI primes itself on every task after that.

Full definition and examples: https://jaredrhod.com/ai-priming

## Templates

Starter files for the system. Every spot that needs your information is marked `[FILL IN: ...]` — drop a template in and tell your AI "fill this in for me," and it will interview you and write it in your voice (each template carries that instruction for the AI). Or fill them out by hand if you prefer.

- **[CLAUDE.md](templates/CLAUDE.md):** the boot config. Goes in the folder you run Claude Code from (your **working directory**), kept **out of your vault** so the vault stays pure notes and doesn't get tangled once you have more than one project. Claude Code auto-loads it every session and points the AI to your vault. Holds your agent's identity — its name, role, and personality — plus your startup sequence and the rules that can't lapse.
- **[VAULT-INDEX.md](templates/VAULT-INDEX.md):** the operating manual. This one lives **inside your vault** (it's a note, not config). Your profile, your projects, the full vault rules, and how you like to work with the AI.
- **[DAILY-NOTE.md](templates/DAILY-NOTE.md):** the daily-note template. Goes **inside your vault** at `01 - Daily Notes/Daily Note Template.md`. Every daily note gets created from it, so the log keeps one consistent, scannable shape.
- **[MEMORY.md](templates/MEMORY.md):** the pointer for Claude Code's own memory. Goes in **Claude Code's project folder** (`~/.claude/projects/...`, not your vault). It redirects the native memory back into the vault so you never end up with two memory layers that drift apart.

## Support

Free to use, and always will be. If this helped you out, you can buy me a coffee:

[![Support me on Ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/jaredrhod)

## License

Copyright (c) 2026 Jared Rhodenizer.

The contents of this repository are licensed under the Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License (CC BY-NC-SA 4.0). You are free to share and adapt them, with attribution, for noncommercial purposes, as long as you license your contributions under these same terms. Full terms are in the LICENSE file and at https://creativecommons.org/licenses/by-nc-sa/4.0/
