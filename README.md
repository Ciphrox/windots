
# Windows Dotfiles

My personal configuration files for a tiling window manager workflow on Windows.

## 📦 Included Configurations

- **[Komorebi](https://github.com/LGUG2Z/komorebi)** - Tiling Window Manager
- **[WHKD](https://github.com/LGUG2Z/whkd)** - Windows Hotkey Daemon
- **[YASB](https://github.com/amnweb/yasb)** - Yet Another Status Bar
- **[Fastfetch](https://github.com/fastfetch-cli/fastfetch)** - System Information Tool

## 🛠️ Prerequisites

### 1. Enable Developer Mode

Symlinks require Developer Mode to be enabled on Windows.

1. Open **Settings**.
2. Go to **System** > **For developers**.
3. Toggle **Developer Mode** to **On**.

### 2. Install Tools

Run the following in PowerShell to install the required tools via `winget`:

```powershell
winget install LGUG2Z.komorebi
winget install LGUG2Z.whkd
winget install --id AmN.yasb
winget install fastfetch
```

### 3. Install Dotfile Manager

I recommend using **[tuckr](https://github.com/RaphGL/tuckr)** to manage symlinks.

```powershell
# Requires Rust/Cargo installed
cargo install tuckr
```

## 🚀 Setup

### 1. Configure Environment Variables

Set the configuration paths for `komorebi` and `whkd`. Run the following in **Administrator PowerShell**:

```powershell
[Environment]::SetEnvironmentVariable('KOMOREBI_CONFIG_HOME', "$env:USERPROFILE\.config\komorebi", 'User')
[Environment]::SetEnvironmentVariable('WHKD_CONFIG_HOME', "$env:USERPROFILE\.config\whkd", 'User')
```

### 2. Installation

#### Option A: Using Tuckr (Recommended)

```powershell
# Create directory
mkdir -Force "$env:APPDATA/dotfiles"

# Clone repository
git clone https://github.com/Ciphrox/windots.git "$env:APPDATA/dotfiles"

# Link configurations
tuckr add windots
```

#### Option B: Manual Installation

1. Clone the repository:

   ```powershell
   git clone https://github.com/Ciphrox/windots.git
   ```

2. Copy the contents of `windots/Configs/windots/*` to your `C:/Users/<username>/*`/ directory

## 🏃 Usage

### Managing Komorebi & WHKD

```powershell
# Start Komorebi and WHKD
komorebic start --whkd

# Stop Komorebi and WHKD
komorebic stop --whkd

# Enable Autostart on login
komorebic enable-autostart
```

### Status Bar

```powershell
# Run YASB
yasb
```

## ⌨️ Keybindings

- Press `Alt + i` to view a list of available shortcuts.
- Check the `whkd` configuration file in `.config/whkd/whkdrc` for the full list of hotkeys.
