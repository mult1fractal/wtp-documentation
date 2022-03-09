# FAQ
In this section I have some troubleshooting advice with problems I faced when I started with bioinformatics and testing with WtP

## Problems with storage while running WtP

WtP produces temporary data.
Depending on your input file, this temporary data can take up a lot of GB of storage space after several WtP runs
By default, all temporary data files are stored in `/tmp/nextflow-phage-$USER`. i.e. When you restart, the temporary data files will be removed.

For users who run WtP on a cluster and can't restart it, we have the `--work-dir` flag.  
This makes it possible to change the storage location for the temporary workflow files.  
With the flag `--work-dir work`, a folder with the name ` work` will be created in your current working dir.  
All of WtP temporary workflow files will be stored in this directory.  
With `sudo rm -r / work *` they can become demanding. 


```bash
--work-dir /path/to/dir    # defines the path where nextflow writes temporary files, default: '/tmp/nextflow-phage-$USER'
```


## Docker-files needed and their size

REPOSITORY|TAG|SIZE
|-|-|-|
multifractal/template_pandas|v3.8.p|817MB
nanozoo/rmarkdown|2.10--a3f4088|3.72GB
papanikos/marvel|0.2-29b3c73|6.42GB
papanikos/virsorter-2|2.2.1--fa935f8|1.19GB
multifractal/seeker|0.1|1.66GB
multifractal/phigaro|0.5.2|2.6GB
nanozoo/seqkit|0.13.2--cd66104|469MB
multifractal/virnet-hack|0.1|1.62GB
nanozoo/emboss|6.6.0--418c521|1.07GB
multifractal/ppr-meta|0.3.1|5.3GB
multifractal/virfinder|0.2|3.91GB
multifractal/vibrant|0.5|1.42GB
nanozoo/sourmash|3.4.1--16a8db7|788MB
nanozoo/hmmer|3.3--3db9dd1|484MB
nanozoo/checkv|0.6.0--e97f45e|1.72GB
nanozoo/altair|4.1.0--086b80e|1.02GB
nanozoo/samtools|1.9--76b9270|487MB
multifractal/virsorter|0.1.2|2.84GB
nanozoo/r_fungi|0.1--097b1bb|3.11GB
nanozoo/template|3.8--ccd0653|681MB
nanozoo/basics|1.0--962b907|79.1MB
nanozoo/upsetr|1.4.0--0ea25b3|3.21GB
nanozoo/r_ggplot2|0.1--6405f6d|3.26GB
multifractal/metaphinder|0.1|767MB
multifractal/deepvirfinder|0.1|2.37GB
nanozoo/prodigal|2.6.3--2769024|531MB


-----------------------------------


## Installing WTP in a centralized way for multi-users

Run WtP on a cluster environment:  

* Let the Users run WtP from their individual accounts (e.g., via ssh connection)  
* create special locations (shared locations) where to store the singularity images, docker images, the databases and the cache  
* let each run of WtP (from a user) use the shared locations but the usage provided forces the users to specify params --workdir, --databases and --cache......
* the shared locations should be transparent to the users .. 

 
**Quick Solution:** 

* "install" WtP via `git clone --branch v1.1.0 https://github.com/replikation/What_the_Phage.git`
* then change the nextflow config and let the user use this "git"  (the version would then be fixed to the git clone)
* e.g.:
````bash
./phage.nf \
  --fasta /path/to/file.fa \      # provide a fasta-file as input
  --cores 8 \                     # number of cores you want to use
  -profile local,docker           # choose the environment:local and docker
````
-----------------------------------

## Error ignored:

* some tools can fail during the identification process e.g. if a tool can't process a fasta-inputfile (sometimes MARVEL with really large multi fasta files)
then you will get an error-message like this :

```bash
[34/31d18f] NOTE: Process `identify_fasta_MSF:upsetr_plot (1)` terminated with an error exit status (1) -- Error is ignored
```

* even if an error occures WtP continues its work, but won't include the results of the failed process

-----------------------------------

### Chromomap issues: terminated with an error exit status (1)

In the Annotation process of WtP, wird eine Genkarte mit den annotierten/gefundenen Genen erstellt
Bei der erstellung der Genkarte kann es manchmal zu folgendem Error-code kommen:


```bash
[4e/57d82d] NOTE: Process 'phage_annotation_MSF:chromomap (1)' terminated with an error exit status (1) -- Execution is retried (1)
```

The workflow works as intended. We included a few "failsafe" processes for chromomap, so if one plotting approach fails it retries another approach to render it,  
thus you get the fail but the retry will work.
In the end you will get the result

-----------------------------------

## Singularity image problems 

Sometimes the singularity runs fail because some singularity images are failing in their build process:   

* you can retry the the execution command  
* or you can run the [Pre-download for Offline-mode](https://mult1fractal.github.io/wtp-documentation/Workflow-execution/commands/#pre-download-for-offline-mode) and start WtP with the 'preloaded' images  



## Download Databases manually

* usually there is no problem with database download.
* in case there is a problem you can download them [here](https://osf.io/wtfrc/)
