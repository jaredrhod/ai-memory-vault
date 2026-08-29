# Troubleshooting

Written for humans AND for AI assistants. If you're an AI helping someone with their vault: read this file, then diagnose from their actual files and paths, never from guesses.

## Where is my vault, physically?

Open `VAULT-INDEX.md` at the vault root: its "Vault location" section records the full path. Fresh vaults created by this system live at `~/<vault name>`, directly in your home folder, on Mac, Windows, and Linux alike: the same place the agent folder lives, and on a Mac the one place that anything your agent does without you at the keyboard can reach (Documents, Desktop, and cloud folders are walled off from background work). A vault from an older install may live in Documents; that is fine, see the entry below. If the index is missing that section, Obsidian itself knows: its vault switcher lists every vault with its path.

## Obsidian opened to a welcome screen instead of my vault

Obsidian only opens vaults it knows about, and it learns about them from a registry file called `obsidian.json` (macOS: `~/Library/Application Support/obsidian/obsidian.json` · Windows: `%APPDATA%\obsidian\obsidian.json` (lowercase folder) · Linux: `~/.config/obsidian/obsidian.json`). A vault created as a plain folder isn't in that registry yet, so a fresh Obsidian shows the picker. Two fixes:

1. **By hand, one time:** on the welcome screen choose "Open folder as vault" and pick your vault folder (fresh installs put it at `~/<vault name>` in your home folder; older installs used `~/Documents/<vault name>`). Obsidian remembers it from then on.
2. **Ask your agent:** have it register the vault in `obsidian.json` with `"open": true` (Obsidian must be closed while it edits, because the app rewrites that file on quit). Current versions of the setup wizard do this automatically; hitting this screen usually means the vault was created by an older run.

## How do I back up my vault?

A fresh vault lives in your home folder and is not cloud-synced, by design, so it exists on exactly one disk. Free options, any one of which is enough:

- **Whole-machine backup:** Time Machine (Mac) covers your home folder automatically. File History (Windows) skips a home-folder vault unless you add the folder to its list, one time.
- **A private GitHub repo:** your agent can set this up and push on a schedule. Notes are small; even years of them fit in any free account.

The one thing to avoid is moving the vault into iCloud Drive or OneDrive to get sync: on a Mac that puts it back behind the wall that blocks your agent's background work.

## My vault is in Documents from an older install. Should I move it?

Not today, and not by hand. It works fine for everyday use. The one catch is on a Mac: anything your agent does without you at the keyboard can't reach into Documents, so when you add background automation, the vault needs to be in your home folder. Don't drag it there: too many things point at that folder (Obsidian's registry, your boot config, the index, any connector configs). A dedicated move tool that re-points all of them is the right way, and you run it when you are ready. Until then, nothing about your setup is wrong.

## My vault is in a folder that syncs to iCloud or OneDrive (an older install). Is that a problem?

Mostly it's a gift: the cloud is keeping a free, automatic backup of your agent's entire memory. Two things to know:

1. **Run ONE sync service per vault.** If iCloud or OneDrive already syncs the folder, don't also turn on Obsidian's paid Sync add-on for that vault. Two sync engines editing the same files fight, and the fight produces conflicted copies.
2. **Stop the cloud from evicting your notes.** To save disk space, iCloud ("Optimize Mac Storage") and OneDrive ("Files On-Demand") can quietly replace files with internet-only placeholders. Your notes aren't lost, but reads get slow or fail offline. The fix is one click: right-click the vault folder, then "Keep Downloaded" on Mac or "Always keep on this device" on Windows. Done once, it sticks.

## I want the vault OUT of cloud sync entirely

- **Windows (OneDrive):** OneDrive settings, then Sync and backup, then Advanced settings, then "Choose folders": untick the vault's folder. It stays on disk, OneDrive ignores it.
- **Mac (iCloud Desktop & Documents):** iCloud offers no per-folder exclusion inside Documents. Two honest options: rename the vault folder with a `.nosync` suffix (iCloud skips it, but the ugly name shows everywhere, including Obsidian), or move the vault to your home folder, which is a proper job, not a drag in Finder: too many things point at the folder, and a dedicated move tool that re-points all of them is the way to do it (see the entry above). Until you run that, the `.nosync` rename is the safe option.

## The AI says it can't read or find the vault

The vault path lives in two places: the `CLAUDE.md` boot config in your working folder, and VAULT-INDEX's "Vault location" section. If the vault moved (or a cloud service relocated it), those paths went stale. Tell your agent the new path and have it update both. If reads fail only sometimes, see the placeholder eviction fix above.
