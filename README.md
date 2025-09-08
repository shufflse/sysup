# sysup – Universal System Updater 🛠️

`sysup` is a cross‑manager system update tool that automatically detects available package managers on your system and runs updates.  


---

## 📦 Installation

Place `sysup` in a directory in your `$PATH`.  
For a system‑wide install (recommended), copy it to `/usr/local/bin`:

```bash
git clone https://github.com/shufflse/sysup.git
cd sysup
sudo cp sysup /usr/local/bin/sysup
sudo chmod +x /usr/local/bin/sysup
```

---

## 🚀 Usage

Run a full update across all detected managers:

```bash
sysup
```

Run **only** specific managers:

```bash
sysup --only apt,flatpak
```

Skip certain managers:

```bash
sysup --skip npm,yarn
```

Show full output from each manager:

```bash
sysup --verbose
```

---

## ⚙️ Options

| Flag / Option       | Description |
|---------------------|-------------|
| `-h`, `--help`      | Show help & usage info |
| `-v`, `--verbose`   | Show full package manager output |
| `-o`, `--only LIST` | Run only these managers (comma‑separated) |
| `-s`, `--skip LIST` | Skip these managers |
| `-c`, `--edit-config` | Edit your per‑user config file in `$EDITOR` |

---

## 🖥️ Supported Managers

`sysup` currently detects and can run updates for:

```
apt   dnf   pacman   yay   paru   zypper
brew  flatpak
npm   pnpm  yarn
cargo gem   go
```

Only managers found on your system will be executed.  
If both `yay`/`paru` and `pacman` are present, `pacman` will be skipped to avoid duplicate runs.

---

## 📊 Progress UI

```
⏳ Remaining: npm, dnf
 50% ██████░░░░░░░░░░░░░░░░░░ ETA: 00:05
```

- **Line 1**: Remaining package managers  
- **Line 2**: Percentage complete, progress bar, and estimated time remaining
