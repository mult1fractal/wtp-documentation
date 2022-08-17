# Detailed Flag explanation  


-----------------------------------------


## Run option
* by default WtP deploys only a selection of phage prediction tools that was benchmarked by [Ho ***et al.***](https://www.biorxiv.org/content/10.1101/2021.04.12.438782v2)
* if you wish to run all integrated phage prediction tools: 
```bash
`--all_tools` # activate all included phage prediction tools
```


-----------------------------------------

 
## Inputs
* Input examples:
 * wildcards need single quotes around the path (`'`)
```bash
--fasta /path/to/phage-assembly.fa  # path to your fasta-file
--fasta '/path/to/*.fa'             # path to all .fa files in a dir
```
 
-----------------------------------------


## Profiles
1. Choose the environment: `local`, `slurm`, `lsf` or `ebi`
2. Choose the engine: `docker` or `singularity`
* examples:
```bash
-profile local,docker
-profile local,singularity
-profile lsf,docker
```

-----------------------------------------
## Custom phage annotation Database

`--annotation_db` will allow you to provide your own database instead of the default [pvog database](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5210652/)  

* you need the following file types for the annotation process (hmmscan),   

|needed files|    
|-|  
|custom.hmm|  
|custom.hmm.h3f|   
|custom.hmm.h3i|   
|custom.hmm.h3m|   
|custom.hmm.h3p|   
    
* `tar -czvf custom_db.tar.gz custom.hmm custom.hmm.h3f custom.hmm.h3i custom.hmm.h3m custom.hmm.h3p`  
* with `--annotation_db custom_db.tar.gz` you can provide your own custom phage annotation database  

-----------------------------------------
 
## Release candidate
* A release candidate is a [released version of WtP](https://github.com/replikation/What_the_Phage/releases) which ensures proper functionality
* version control ensures reproducibility as each tools version is also "locked" within the release candidate
 * databases have no automatic version control (they are downloaded from the source)
 * if you need version control for databases, just make a copy of the database dir after download
 * you can specify the database dir via the `--database` flag (see below)
   * WtP only downloads a database if it's missing, it is not "auto-updating" them
* add this flag to your command and a specific release is used instead
```bash
-r v1.1.0
```
 
-----------------------------------------
 
## Data handling
 
* WtP handles everything by default
* If you need to change paths use the following commands
 * It's useful to specify `--workdir` to your current working dir if `/tmp` (default) has limited space
```bash
-work-dir /path/to/dir    # defines the path where nextflow writes temporary files, default: '/tmp/nextflow-phage-$USER'
--databases /path/to/dir  # specify download location of databases, default './nextflow-autodownload-databases'
--cachedir /path/to/dir   # defines the path where singularity images are cached, default './singularity-images'
--output results          # path of the outdir, default './results'
```
 
---------------------------------------------
 
## Pre-download for Offline-mode
 
* `--setup` skips analysis and just downloads all databases and containers
* Needs roughly 30 GB storage for databases, excluding programs
 
`nextflow run replikation/What_the_Phage --setup -r v1.1.0 -profile singularity,local` 
 
* you can change the database download location via (--databases)
* make sure that you specify the database location when executing WtP, if you change the default path
* singularity images sometimes fail during building, just try to re-execute `--setup`
 * WtP attempts to build images up to 3 times, image building is individually skipped if present

