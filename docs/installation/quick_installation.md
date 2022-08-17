# Local, docker usage
 
* "None informaticians / newcomer to bioinformatics" approach using ubuntu [admin rights required] 
* **we do not recommend this installation-process**(an older version of Docker will be installed. This installation method is not suitable for a cluster), but it is probably the fastest way to get WtP to run
 
```bash
sudo apt-get update
sudo apt install -y default-jre
curl -s https://get.nextflow.io | bash
sudo mv nextflow /usr/bin/
sudo apt-get install -y docker-ce docker-ce-cli containerd.io
sudo usermod -a -G docker $USER
```
 
* Restart your computer


## Conda usage:
```bash
conda create -n wtp nextflow==20.07.01 singularity==3.6.1
conda activate wtp
(wtp) $ nextflow run replikation/What_the_Phage -r v1.2.0 --setup ...
```
now you should be able to run `nextflow run replikation/What_the_Phage -r v1.2.0 --setup -profile local,singularity`

-------------------------------------------------------

## Test the workflow

* latest workflow release  
```bash
nextflow pull replikation/What_the_Phage
```
* for docker (local use)  
```bash
nextflow run replikation/What_the_Phage -r v1.2.0 --cores 8 -profile smalltest,local,docker
```
* for singularity (slurm use)  
```bash
nextflow run replikation/What_the_Phage -r v1.2.0 --cores 8 -profile smalltest,slurm,singularity
```
