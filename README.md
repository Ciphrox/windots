# Run the following in the `Powershell`

## 1. Tell komorebi & whkd where to look for config files

```powershell
$Env:KOMOREBI_CONFIG_HOME = "$Env:USERPROFILE\.config\komorebi"
$Env:WHKD_CONFIG_HOME = "$Env:USERPROFILE\.config\whkd"
```

## 2. Pull the dot-files into your home folder (no extra sub-dir)

```powershell
cd $env:USERPROFILE
git clone https://github.com/Ciphrox/komorebi-config-files/ .
```
