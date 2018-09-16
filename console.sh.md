# ffmpeg

## PNGs to MP4 

```
ffmpeg -framerate 5 -i "base%6d.png" out.mp4 
```
```
ffmpeg -framerate 24 -pattern_type glob -i 'orand/*/*.png' \
        -c:v libx264 -r 24 -pix_fmt yuv420p occlusions2.mp4
```




# Powershell scripts

## Rename files 
```
dir *.png | %{$x=0} {Rename-Item $_ -NewName "Base$($x.tostring('000000')).png"; $x++ }
```
