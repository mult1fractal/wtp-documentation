# Test the workflow


* for docker (local use)
```shell

nextflow run replikation/What_the_Phage -r v0.9.0 --cores 8 -profile smalltest,local,docker
```
* for singularity (slurm use)
```shell

nextflow run replikation/What_the_Phage -r v0.9.0 --cores 8 -profile smalltest,slurm,singularity
```
