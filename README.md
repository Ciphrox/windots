# Run the following in the `Powershell`

## 1. Tell komorebi & whkd where to look for config files

> Run this as Administrator Powershell
```powershell
[Environment]::SetEnvironmentVariable(
     'KOMOREBI_CONFIG_HOME',
     (Join-Path $env:USERPROFILE '.config\komorebi'),
     'User')

[Environment]::SetEnvironmentVariable(
    'WHKD_CONFIG_HOME',
    (Join-Path $env:USERPROFILE '.config\whkd'),
    'User')

```

## 2. Pull the dot-files into your home folder (no extra sub-dir)

```powershell
cd $env:USERPROFILE/.config
git clone https://github.com/Ciphrox/komorebi-config-files/ .
```
