# Detailed Flag explanation  
* e.g.:
 
```shell
nextflow run replikation/What_the_Phage \
 --fasta '/path/to/*.fasta' \
 -profile local,docker \
 --cores 20 \
 -r v0.8.0 \
 --anno \
 --dv \
 --vf \
 --ma
```
 
-----------------------------------------
 
## Inputs
* Input examples:
 * wildcards need single quotes around the path (`'`)
```bash
--fasta /path/to/phage-assembly.fa  # path to your fasta-file
--fasta '/path/to/*.fa'             # path to all .fa files in a dir
--fastq /path/to/phage-read.fastq   # path to your fastq-file
--fastq '/path/to/*.fastq'          # path to all .fastq files in a dir
```
* the `fastq` input is currently experimental 
 
-----------------------------------------
 
## Workflow control
* By default: all included phage identification tools are activated
* but, you can turn off tools (check `--help` for more)
 
```bash
   --dv             #   deactivates deepvirfinder
   --ma             #   deactivates marvel
   --mp             #   deactivates metaphinder
   --pp             #   deactivates PPRmeta
   --sm             #   deactivates sourmash
   --vb             #   deactivates vibrant
   --vf             #   deactivates virfinder
   --vn             #   deactivates virnet
   --vs             #   deactivates virsorter
   --ph             #   deactivates phigaro
   --vs2            #   deactivates virsorter2
   --identify       #   only phage identification, skips analysis
   --annotate       #   only annotation, skips phage identification
```
 
* minimal size of contigs for identification
 * sequences below the default size: 1500bp will not be analyzed
```bash
--filter             #   minimal contig size [bp] to analyse e.g. --filter 2000
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
 
## Release candidate
* A release candidate is a [released version of WtP](https://github.com/replikation/What_the_Phage/releases) which ensures proper functionality
* version control ensures reproducibility as each tools version is also "locked" within the release candidate
 * databases have no automatic version control (they are downloaded from the source)
 * if you need version control for databases, just make a copy of the database dir after download
 * you can specify the database dir via the `--database` flag (see below)
   * WtP only downloads a database if it's missing, it is not "auto-updating" them
* add this flag to your command and a specific release is used instead
```bash
-r v0.9.0
```
 
-----------------------------------------
 
## Data handling
 
* WtP handles everything by default
* If you need to change paths use the following commands
 * It's useful to specify `--workdir` to your current working dir if `/tmp` (default) has limited space
```bash
-work-dir /path/to/dir    # defines the path where nextflow writes temporary files, default: '/tmp/nextflow-phage-$USER'
--databases /path/to/dir   # specify download location of databases, default './nextflow-autodownload-databases'
--cachedir /path/to/dir   # defines the path where singularity images are cached, default './singularity-images'
--output results          # path of the outdir, default './results'
```
 
---------------------------------------------
 
## Pre-download for Offline-mode
 
* `--setup` skips analysis and just downloads all databases and containers
* Needs roughly 30 GB storage for databases, excluding programs
 
`nextflow run replikation/What_the_Phage --setup -r v0.9.0 -profile singularity,local` 
 
* you can change the database download location via (--databases)
* make sure that you specify the database location when executing WtP, if you change the default path
* singularity images sometimes fail during building, just try to re-execute `--setup`
 * WtP attempts to build images up to 3 times, image building is individually skipped if present

