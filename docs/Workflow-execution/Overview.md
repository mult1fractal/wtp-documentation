# Command overview
 
## The basic command
 
```bash
nextflow run \                   # calling the workflow
 replikation/What_the_Phage \    # WtP Git-Repo
 --fasta /path/to/file.fa \      # provide a fasta-file as input
 --cores 8 \                     # number of cores you want to use
 -profile local,docker           # choose the environment:local and docker
 -r v1.1.0                       # WtP release version
```

## Flag overview  

### Mandatory
|Flag          |simple explanation                                    |
|--------------|------------------------------------------------------|
| --fasta      |  path/to/phage-assembly.fa *or*  '/path/to/*.fa'     |
| -profile     |  local,docker *or* local,singularity *or* lsf,docker |
| -r           |  v1.1.0                                              |

### Options

|Flag          |simple explanation                                    |
|--------------|------------------------------------------------------|
| --help       |  will show you this page in your terminal            |
| --filter     |  e.g. 1500 bp (sequences below 1500 bp won't be analyzed)|
| --cores      |  e.g. 10                                             |
| --setup      |  pre-downloads all you need to run WtP               |

### Pathing

|Flag          |simple explanation                                    |
|--------------|------------------------------------------------------|
| --workdir    |  /path/to/dir                                        |
| --database   |  /path/to/dir                                        |
| --cachedir   |  /path/to/dir                                        |
| --output     |  e.g. results                                        |


### Workflow control

|Flag          |simple explanation                                    |
|--------------|------------------------------------------------------|
| --dv         |  deactivates deepvirfinder                           |
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


-----------------------------------------