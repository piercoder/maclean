![Shell](https://img.shields.io/badge/shell-zsh-blue) ![macOS](https://img.shields.io/badge/macOS-Sequoia-green) ![License: MIT](https://img.shields.io/badge/license-MIT-yellow)
# maclean

## A dev-friendly macOS cleanup script with sane defaults

maclean is a shell script that helps developers reclaim disk space, clear caches, and apply sensible Finder/Dock defaults to keep macOS fast and tidy.
It reclaims disk space, clears caches/logs, prunes Docker/Xcode leftovers, thins APFS snapshots, and applies sane Finder/Dock defaults.

---

## ✨ Features

- Cleanup tasks
- Purge user/system caches and old logs
- Clear Trash (local + external volumes)
- Remove old iOS backups, Xcode derived data, archives, and simulator junk
- Clean Homebrew caches and run brew autoremove/cleanup
- Prune Docker images/containers older than N hours
- Thin APFS local snapshots
- Defaults tweaks
- Disable/shorten animations
- Speed up key repeat
- Finder: show path bar, status bar, full POSIX path, extensions
- Dock: disable recents, hide launch animation, sort folders first
- Reduce transparency/motion
- Reveal ~/Library
- Safety first
- Refuses to run as root
- Only asks for sudo when required (system caches, APFS snapshots)
- Tested on macOS Sequoia

---

## 📦 Installation

Clone the repo and make the script executable:

```bash
git clone https://github.com/piercoder/maclean.git
cd maclean
chmod +x maclean
./maclean --help
```

Optionally, symlink to your PATH for global usage:
```bash
ln -s $(pwd)/maclean /usr/local/bin/maclean
```

---

## 🚀 Usage

./maclean [--clean] [--defaults] [--all] [--help]

```
--clean       Run cleanup tasks (disk, caches, logs, Trash, Docker, Xcode)
--defaults    Apply performance defaults (UI/animation tweaks, Finder/Dock)
--all         Run both cleanup and defaults
-h, --help    Show help and exit
```

---

### Examples

```bash
./maclean --clean          # Clean caches, logs, Trash, Docker, Xcode
./maclean --defaults       # Apply Finder/Dock/animation tweaks
./maclean --all            # Run both cleanup + defaults
DOCKER_PRUNE_UNTIL_HOURS=48 ./maclean --clean   # Clean with custom Docker prune threshold
```

If no flag is provided, --clean is run by default.

---

## ⚙️ Environment Variables

```txt
BACKUP_AGE_DAYS — Prune iOS backups older than N days (default: 90)
DOCKER_PRUNE_UNTIL_HOURS — Prune Docker images/containers older than N hours (default: 720)
SNAPSHOT_THIN_TARGET_BYTES — Target bytes to reclaim from APFS snapshots (default: 5000000000)
NO_COLOR — Disable colorized output
```

---

## 📋 Requirements

- macOS Sequoia or newer with zsh as default shell
- Optional: [Homebrew](https://brew.sh/), [Xcode Command Line Tools](https://developer.apple.com/xcode/), [Docker](https://www.docker.com/), sudo, tmutil

---

## 🛡️ Safety Notes

- Never run as root (the script will refuse execution).
- System caches & APFS thinning will prompt for sudo.
- Most defaults take effect immediately; some may require logout/restart.

---

## 📄 License

MIT © Pierpaolo Pattitoni
[github.com/piercoder](https://github.com/piercoder)