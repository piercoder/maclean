# maclean

## Dev-friendly macOS cleanup & sane defaults.

maclean is a shell script that helps developers keep their macOS environment fast and tidy.
It reclaims disk space, clears caches/logs, prunes Docker/Xcode leftovers, thins APFS snapshots, and applies sane Finder/Dock defaults.

⸻

✨ Features

	•	Cleanup tasks
	•	Purge user/system caches and old logs
	•	Clear Trash (local + external volumes)
	•	Remove old iOS backups, Xcode derived data, archives, and simulator junk
	•	Clean Homebrew caches and run brew autoremove/cleanup
	•	Prune Docker images/containers older than N hours
	•	Thin APFS local snapshots
	•	Defaults tweaks
	•	Disable/shorten animations
	•	Speed up key repeat
	•	Finder: show path bar, status bar, full POSIX path, extensions
	•	Dock: disable recents, hide launch animation, sort folders first
	•	Reduce transparency/motion
	•	Reveal ~/Library
	•	Safety first
	•	Refuses to run as root
	•	Only asks for sudo when required (system caches, APFS snapshots)
	•	Tested on macOS Sequoia

⸻

🚀 Usage

./maclean [--clean] [--defaults] [--all] [-h|--help]

Flags

	•	--clean → Run cleanup tasks (disk, caches, logs, Trash, Docker, Xcode)
	•	--defaults → Apply performance defaults (UI/animation tweaks, Finder/Dock)
	•	--all → Run both cleanup and defaults
	•	-h | --help → Show help and exit

Default behavior: with no flags, --clean is assumed.

⸻

⚙️ Environment Variables

	•	BACKUP_AGE_DAYS — Prune iOS backups older than N days (default: 90)
	•	DOCKER_PRUNE_UNTIL_HOURS — Prune Docker images/containers older than N hours (default: 720)
	•	SNAPSHOT_THIN_TARGET_BYTES — Target bytes to reclaim from APFS snapshots (default: 5000000000)
	•	NO_COLOR — Disable colorized output

⸻

📋 Requirements

	•	macOS + zsh
	•	Optional: Homebrew, Xcode tools, Docker, sudo, tmutil

⸻

🛡️ Safety Notes

	•	Never run as root — the script will refuse.
	•	System caches & APFS thinning will prompt for sudo.
	•	Most defaults take effect immediately; some may require logout/restart.

⸻

📄 License

MIT © Pierpaolo Pattitoni
github.com/piercoder