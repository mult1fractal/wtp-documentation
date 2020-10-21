## Setting up Conda 

```bash
conda create -n wtp nextflow==20.07.01 singularity==3.6
conda activate wtp
(wtp) $ nextflow run replikation/What_the_Phage -r 0.9.0 --setup ...
```
now you should be able to run `nextflow run replikation/What_the_Phage -r 0.9.0 --setup`