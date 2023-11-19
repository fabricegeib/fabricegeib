# Powershell

Set-ExecutionPolicy Unrestricted

## Folders color

change color

open `code $PROFILE` or `code $PSHOME\Profile.ps1`

```shell
# for a blue #6CA4F8 (GitHub Dark)
$PSStyle.FileInfo.Directory = "`e[38;2;108;164;248m"
```

## Oh My Posh

```shell
# install
winget install JanDeDobbeleer.OhMyPosh -s winget

# update
winget upgrade JanDeDobbeleer.OhMyPosh -s winget

# default theme and prompt initialization
oh-my-posh init pwsh --config "$env:POSH_THEMES_PATH\jandedobbeleer.omp.json"

# install font
oh-my-posh font install
```

## Resources

- https://docs.microsoft.com/fr-fr/powershell/module/microsoft.powershell.core/about/about_execution_policies?view=powershell-7.2
