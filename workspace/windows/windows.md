### Language

```shell
$LangList = Get-WinUserLanguageList
Set-WinUserLanguageList $LangList -Force
```

### Network

```shell
netsh winsock reset
netsh int ip reset all
netsh winhttp reset proxy
ipconfig /flushdns
```

### Repair Win

```shell
DISM /Online /Cleanup-Image /RestoreHealth Source:WIM:X:/sources/install.wim
```

### Hibernate

```shell
powercfg -restoredefaultschemes
powercfg.exe /hibernate on
powercfg -h on
powercfg -h /type full
```
