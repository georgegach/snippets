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

# modules
```
#!/bin/bash
declare -a modules=(
        "cuda92/toolkit/9.2.148"
        "cuda92/blas/9.2.148"
        "cuda92/fft/9.2.148"
        "cuda92/nsight/9.2.148"
        "cuda92/profiler/9.2.148"
)

for m in "${modules[@]}"
do
  	cmd="module load $m"
        echo "\$ $cmd"
        eval $cmd
done
echo
eval nvcc --version | tail -n 1
echo
```
```
source ~/scripts/modules.sh
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


