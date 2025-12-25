
# Komorebi Config Files

## Prerequisites

Install the required tools using `winget`:

```powershell
winget install LGUG2Z.komorebi
winget install LGUG2Z.whkd
winget install --id AmN.yasb
```

You will also need `dploy` for managing symlinks:

```powershell
pip install dploy
```

## Setup

### 1. Configure Environment Variables

Tell `komorebi` and `whkd` where to look for configuration files. Run the following in **Administrator PowerShell**:

```powershell
[Environment]::SetEnvironmentVariable(
    'KOMOREBI_CONFIG_HOME',
    (Join-Path $env:USERPROFILE '.config\komorebi'),
    'User'
)

[Environment]::SetEnvironmentVariable(
    'WHKD_CONFIG_HOME',
    (Join-Path $env:USERPROFILE '.config\whkd'),
    'User'
)
```

### 2. Installation

Clone the repository and create symlinks:

```powershell
# Clone the repo
git clone https://github.com/Ciphrox/win_dotfiles
cd win_dotfiles

# Create symlinks
dploy stow . $ENV:USERPROFILE\
```

> **Note:** If `dploy` fails, you can manually copy the files to your user profile.


