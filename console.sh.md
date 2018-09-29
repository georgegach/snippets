# ffmpeg
```
ffmpeg -framerate 5 -i "base%6d.png" out.mp4 
```
```
ffmpeg -framerate 24 -pattern_type glob -i 'orand/*/*.png' \
        -c:v libx264 -r 24 -pix_fmt yuv420p occlusions2.mp4
```

# slurm
```
salloc --nodes=1 --mem=16G --constraint=V100
ssh `squeue | grep ggach | awk '{print $8}'`

```
```
scancel `squeue | grep ggach | awk '{print $1}'`
```


# Enviromental variables
```
echo 'export MPI_TRAINING="/home/george/Projects/Datasets/MPI-Sintel-complete/training"' >> ~/.bashrc
source ~/.bashrc
```
```
echo 'export PATH="/home/george/Scripts:$PATH"' >> ~/.bashrc
source ~/.bashrc
```



# Powershell scripts
```
dir *.png | %{$x=0} {Rename-Item $_ -NewName "Base$($x.tostring('000000')).png"; $x++ }
```


