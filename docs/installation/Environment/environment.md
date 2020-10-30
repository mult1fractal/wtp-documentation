WtP can be executed in different environments (workload management platforms)

# Configurations

* providing your own "config" is something we will look into in the future  

## local 

```bash
local {
        executor {
                name = "local"
               	cpus = params.max_cores
        }
        workDir = params.workdir
        params.cloudProcess = false
        includeConfig 'configs/local.config'
    }

```



## slurm  

```bash

slurm {
        executor {
            name = "slurm"
            queueSize = 200
        }
        workDir = params.workdir
        params.cloudProcess = true
        process {
            cache = "lenient"
            time = '2h'
            memory = '4 GB'
        }
        includeConfig 'configs/node.config'
    }


```

## lsf  

```bash
lsf {
        executor {
                name = "lsf"
                queueSize = 200
        }
        workDir = params.workdir
        params.cloudProcess = true
        process.cache = "lenient"
        includeConfig 'configs/node.config'
    }

```

## ebi  

```bash

ebi {
        executor {
                name = "lsf"
                queueSize = 200
        }
        process.cache = "lenient"
        params.cloudProcess = true
        params.workdir = "/hps/nobackup2/production/metagenomics/$USER/nextflow-work-$USER"
        workDir = params.workdir
        params.databases = "/homes/$USER/data/nextflow-databases/"
        params.cachedir = "/hps/nobackup2/singularity/$USER"	
        includeConfig 'configs/node.config'
    }

```