# ffmpeg

## PNGs to MP4 
Simplest image compiler without glob pattern
```
ffmpeg -framerate 5 -i "base%6d.png" out.mp4 
```





# Powershell scripts

## Rename files 
```
dir *.png | %{$x=0} {Rename-Item $_ -NewName "Base$($x.tostring('000000')).png"; $x++ }
```
