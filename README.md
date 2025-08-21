# sysup – Universal System Updater 🛠️

`sysup` is a cross‑manager system update tool.  

It automatically detects available package managers and runs updates.

I'm not very good at writing shell scripts so any suggestions and help would be great.


## ✨ Features

- **Multi‑manager updates** in a single run (`apt`, `dnf`, `brew`, `flatpak`, `npm`, etc.)
- **Robust argument parsing** with both short and long flags
- **Selective updates**: run only specific managers or skip others
- **Verbose mode** to match your workflow
- **Sudo keep‑alive** for uninterrupted privileged operations

---

## 📦 Installation

Clone this repo and install `sysup` to a directory in your `$PATH`:

```bash
git clone https://github.com/shufflse/sysup.git
cd sysup
sudo mkdir -p ~/.local/bin
sudo cp sysup ~/.local/bin/sysup
sudo chmod +x ~/.local/bin/sysup
```

---

## 🚀 Usage

Basic full‑system update:

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

Test the command set without running updates:

```bash
sysup --dry-run
```

Verbose output (scrolls above the pinned UI):

```bash
sysup --verbose
```

---

## ⚙️ Options

| Flag / Option       | Description |
|---------------------|-------------|
| `-h`, `--help`      | Show help & usage info |
| `-v`, `--verbose`   | Show full package manager output |
| `-d`, `--dry-run`   | Print commands, don’t execute |
| `-o`, `--only LIST` | Run only these managers (comma‑separated) |
| `-s`, `--skip LIST` | Skip these managers |
| `-n`, `--no-sudo`   | Skip sudo keep‑alive |

---

## 🖥️ Supported Managers

`sysup` currently detects and can run updates for:

```
apt   dnf   pacman   yay   paru
brew  flatpak
npm   pnpm  yarn
cargo gem   go
zypper
```

Only managers found on your system will be executed.

---

## 📊 Progress UI

```
⏳ Remaining: npm, dnf         
 50% ██████░░░░░░░░░░░░░░░░░░ ETA: 00:05 
```

- **Line 1**: Remaining package managers
- **Line 2**: Percentage, ETA

