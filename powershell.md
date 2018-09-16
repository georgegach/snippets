# Powershell scripts

## Rename files 
```
dir *.png | %{$x=0} {Rename-Item $_ -NewName "Base$($x.tostring('000000')).png"; $x++ }
```
