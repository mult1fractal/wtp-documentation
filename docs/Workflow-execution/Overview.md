# Command overview
The execution command:
 
**Part 1** 
`nextflow run replikation/What_the_Phage` : calling the workflow
 
**Part 2** 
`--flag` : tell WtP what to analyze and how 
 
**Note:** The order of flags does not matter
 
**Bold-flags** are mandatory for WtP to work
 
## Flag overview  
  
  
|Flag          |simple explanation                                    |
|--------------|------------------------------------------------------|
| --help       |  will show you this page in your terminal            |
| **--fasta**  |  path/to/phage-assembly.fa *or*  '/path/to/*.fa'     |
| --fastq      |  /path/to/phage-read.fastq *or*  '/path/to/*.fastq'  |
| --filter     |  e.g. 1500                                           |
| **-profile** |  local,docker *or* local,singularity *or* lsf,docker |
| **-r**       |  v0.9.0                                              |
| --workdir    |  /path/to/dir                                        |
| --database   |  /path/to/dir                                        |
| --cachedir   |  /path/to/dir                                        |
| --output     |  e.g. results                                        |
| --cores      |  e.g. 10                                             |
| --dv         |  deactivates deepvirfinder                           |
| --ma         |  deactivates marvel                                  |
| --mp         |  deactivates metaphinder                             |
| --pp         |  deactivates PPRmeta                                 |
| --sm         |  deactivates sourmash                                |
| --vb         |  deactivates vibrant                                 |
| --vf         |  deactivates virfinder                               |
| --vn         |  deactivates virnet                                  |    
| --vs         |  deactivates virsorter                               |
| --ph         |  deactivates phigaro                                 |
| --vs2        |  deactivates virsorter2                              |
| --identify   |  only phage identification, skips analysis           |
| --annotate   |  only annotation, skips phage identification         |
    


## The basic command
 
```bash
nextflow run \                   # calling the workflow
 replikation/What_the_Phage \   # WtP Git-Repo
 --fasta /path/to/file.fa \     # provide a fasta-file as input
 --cores 8 \                    # number of cores you want to use
 -profile local,docker           # choose the environment:local and docker
 -r v0.9.0                       # WtP release version
```
 
-----------------------------------------