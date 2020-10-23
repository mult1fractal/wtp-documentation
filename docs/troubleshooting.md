## FAQ
In this section I (mult1fractal) have some troubleshooting advice with problems I faced when I started with bioinformatics and testing with WtP

### Problems with storage while running WtP

WtP produces temporary data.
Depending on your input file, this temporary data can take up a lot of GB of storage space after several WtP runs
By default, all temporary data files are stored in `/tmp/nextflow-phage-$USER`. i.e. When you restart, the temporary data files will be removed.

For users who run WtP on a cluster and can't restart it, we have the `-work-dir` flag.  
This makes it possible to change the storage location for the temporary workflow files.  
With the flag `-work-dir work`, a folder with the name ` work` will be created in your current working dir.  
All of WtP temporary workflow files will be stored in this directory.  
With `sudo rm -r / work *` they can become demanding. 


```bash
-work-dir /path/to/dir    # defines the path where nextflow writes temporary files, default: '/tmp/nextflow-phage-$USER'
```

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

### Singularity image problems 

Sometimes the singularity runs fail because some singularity images are failing in their build process:   
* you can retry the the execution command
* or you can run the [Pre-download for Offline-mode](Workflow-execution/command.md) and start WtP with the 'preloaded' images


