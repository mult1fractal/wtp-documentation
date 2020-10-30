# WtP terminal execution:
In this section we want to explain what you see in the Terminal when you execute WtP:

**I'm currently writing on this part**  


## Let's do a Testrun
Open your terminal, move to a directory where you want to execute WtP and type/copy the following command  

```bash
nextflow run phage.nf -profile smalltest,local,docker --work-dir work --cores 16
```

A lot of stuff will pop up but we will quide you through it:  

```bash
N E X T F L O W  ~  version 20.07.1
Launching `phage.nf` [admiring_pesquet] - revision: 1b76c726d3
_____ _____ ____ ____ ___ ___ __ __ _ _ 
  __      _______________________ 
 /  \    /  \__    ___/\______   \
 \   \/\/   / |    |    |     ___/
  \        /  |    |    |    |    
   \__/\  /   |____|    |____|    
        \/                        
_____ _____ ____ ____ ___ ___ __ __ _ _ 
 
Profile: smalltest,local,docker
 
Current User: mike
Nextflow-version: 20.07.1
WtP intended for Nextflow-version: 20.01.0
Starting time: 24-07-2020 15:18 UTC
Workdir location [--workdir]:
  /home/mike/bioinformatics/What_the_Phage/cores=16
Output location [--output]:
  results
Database location [--databases]:
  nextflow-autodownload-databases
 
CPUs to use: 8, maximal CPUs to use: 20
```

 * this is the first thing that will pop up and will give you some basic workflow information: eg where output is stored or how many cores you are using for computing  

--------------------------------------------------

 * An overview about all the WtP processes will show up and looks like this:
 
```bash
[6b/79564a] process > identify_fasta_MSF:fasta_validation_wf:input_suffix_check (1)           [100%] 1 of 1 ✔
[c7/d34016] process > identify_fasta_MSF:fasta_validation_wf:seqkit (1)                       [100%] 1 of 1 ✔
[-        ] process > identify_fasta_MSF:virsorter_wf:virsorter                               [  0%] 0 of 1
[-        ] process > identify_fasta_MSF:virsorter_wf:filter_virsorter                        -
[-        ] process > identify_fasta_MSF:virsorter_wf:virsorter_collect_data                  -
[ff/f698ec] process > identify_fasta_MSF:virsorter2_wf:virsorter2 (1)                         [  0%] 0 of 1
[-        ] process > identify_fasta_MSF:virsorter2_wf:filter_virsorter2                      -                 
*
*
*
executor >  local (9)
[skipped  ] process > phage_references:download_references                                    [100%] 1 of 1, stored: 1 ✔
[skipped  ] process > phage_blast_DB:phage_references_blastDB                                 [100%] 1 of 1, stored: 1 ✔
[skipped  ] process > ppr_dependecies:ppr_download_dependencies                               [100%] 1 of 1, stored: 1 ✔
[skipped  ] process > vibrant_database:vibrant_download_DB                                    [100%] 1 of 1, stored: 1 ✔
[skipped  ] process > virsorter_database:virsorter_download_DB                                [100%] 1 of 1, stored: 1 ✔
[skipped  ] process > pvog_database:pvog_DB                                                   [100%] 1 of 1, stored: 1 ✔
[skipped  ] process > vogtable_database:vogtable_DB                                           [100%] 1 of 1, stored: 1 ✔
[skipped  ] process > vog_database:vog_DB                                                     [100%] 1 of 1, stored: 1 ✔
[skipped  ] process > rvdb_database:rvdb_DB                                                   [100%] 1 of 1, stored: 1 ✔
[skipped  ] process > checkV_database:download_checkV_DB                                      [100%] 1 of 1, stored: 1 ✔
[skipped  ] process > sourmash_database:sourmash_download_DB                                  [100%] 1 of 1, stored: 1 ✔
[6b/79564a] process > identify_fasta_MSF:fasta_validation_wf:input_suffix_check (1)           [100%] 1 of 1 ✔
[c7/d34016] process > identify_fasta_MSF:fasta_validation_wf:seqkit (1)                       [100%] 1 of 1 ✔
[-        ] process > identify_fasta_MSF:virsorter_wf:virsorter                               [  0%] 0 of 1
[-        ] process > identify_fasta_MSF:virsorter_wf:filter_virsorter                        -
[-        ] process > identify_fasta_MSF:virsorter_wf:virsorter_collect_data                  -
[ff/f698ec] process > identify_fasta_MSF:virsorter2_wf:virsorter2 (1)                         [  0%] 0 of 1
[-        ] process > identify_fasta_MSF:virsorter2_wf:filter_virsorter2                      -
[-        ] process > identify_fasta_MSF:virsorter2_wf:virsorter2_collect_data                -
* 
* 
* 
[fc/e0fcc7] process > identify_fasta_MSF:pprmeta_wf:pprmeta (1)                               [  0%] 0 of 1
[-        ] process > identify_fasta_MSF:pprmeta_wf:filter_PPRmeta                            -
[-        ] process > identify_fasta_MSF:pprmeta_wf:pprmeta_collect_data                      -
[-        ] process > identify_fasta_MSF:vibrant_wf:vibrant                                   [  0%] 0 of 1
[-        ] process > identify_fasta_MSF:vibrant_wf:filter_vibrant                            -
[-        ] process > identify_fasta_MSF:vibrant_wf:vibrant_collect_data                      -
[-        ] process > identify_fasta_MSF:vibrant_virome_wf:vibrant_virome                     [  0%] 0 of 1
[-        ] process > identify_fasta_MSF:vibrant_virome_wf:filter_vibrant_virome              -
[-        ] process > identify_fasta_MSF:vibrant_virome_wf:vibrant_virome_collect_data        -
[08/50ce71] process > identify_fasta_MSF:virnet_wf:normalize_contig_size (1)                  [100%] 1 of 1 ✔
[-        ] process > identify_fasta_MSF:virnet_wf:virnet                                     [  0%] 0 of 1
[-        ] process > identify_fasta_MSF:virnet_wf:filter_virnet                              -
[-        ] process > identify_fasta_MSF:virnet_wf:virnet_collect_data                        -
[4e/ca5a07] process > identify_fasta_MSF:phigaro_wf:phigaro (1)                               [  0%] 0 of 1
[-        ] process > identify_fasta_MSF:phigaro_wf:phigaro_collect_data                      -
[-        ] process > identify_fasta_MSF:seeker_wf:seeker                                     [  0%] 0 of 1
[-        ] process > identify_fasta_MSF:seeker_wf:filter_seeker                              -
[-        ] process > identify_fasta_MSF:seeker_wf:seeker_collect_data                        -
[-        ] process > identify_fasta_MSF:filter_tool_names                                    -
[-        ] process > identify_fasta_MSF:r_plot                                               -
[-        ] process > identify_fasta_MSF:upsetr_plot                                          -
[-        ] process > identify_fasta_MSF:samtools                                             -
[-        ] process > phage_annotation_MSF:prodigal                                           -
[-        ] process > phage_annotation_MSF:hmmscan                                            -
[-        ] process > phage_annotation_MSF:chromomap_parser                                   -
[-        ] process > phage_annotation_MSF:chromomap                                          -
[-        ] process > checkV_wf:checkV                                                        -
[-        ] process > phage_tax_classification:split_multi_fasta                              -
[-        ] process > phage_tax_classification:sourmash_for_tax                               -
```

### Started process
```bash
[4e/ca5a07] process > identify_fasta_MSF:phigaro_wf:phigaro (1)                               [  0%] 0 of 1
```
* `[4e/ca5a07]`: is the process folder where the tasks of this process is started/executed 
* `identify_fasta_MSF`: is one of two sub workflows (identify sequence; phage annotation) 
* `phigaro_wf:`: the Phigaro identification process contains a smaller workflow with phigaro and phigaro_collect_data (raw output of Phigaro) 
* `phigaro`: is the actual phage identification task 
* `[  0%] 0 of 1`: Process has not finished yet 
 
--------------------------------------------------
 
### Finished Process
 
* this is how a finished process will look like this:
 
```bash
[6b/79564a] process > identify_fasta_MSF:fasta_validation_wf:input_suffix_check (1)           [100%] 1 of 1 ✔
```
* `[6b/79564a]`: is the process folder where the tasks of this process (input_suffix_check) is executed  
* you can access the folder: 
    * default: `cd /tmp/nextflow-phage-$USER/6b/79564a` and tabcompletion 
    * in our case with --work-dir : `cd work/6b/79564a` and tab completion
    * you will see the files used/created in this process
 
* `identify_fasta_MSF`: is one of two sub workflows (identify sequence; phage annotation) 
 
* `input_suffix_check (1)`: is the actual task (in this case: checks if the fasta file has the correct format)   
 
* `[100%] 1 of 1 ✔`: tells you that the process is complete 
 
--------------------------------------------------
 
### Stored process
```bash
[skipped  ] process > phage_blast_DB:phage_references_blastDB                                 [100%] 1 of 1, stored: 1 ✔
```
 
* this is shown when you already e.g. downloaded the database so WtP won't execute this process again because the data is already stored
 
--------------------------------------------------
 
### Process in Queue
```bash
[-        ] process > identify_fasta_MSF:phigaro_wf:phigaro_collect_data                      -
```
 * this is shows you that the process has not been started yet and is queued and waiting for execution
 
--------------------------------------------------
 
### OnComplete
```bash
Done! Results are stored here --> results
Thank you for using What the Phage
Please cite us: https://doi.org/10.1101/2020.07.24.219899                                      
 
Please also cite the other tools we use in our workflow --> results/literature
Completed at: 30-Oct-2020 10:15:27
Duration    : 49m 34s
CPU hours   : 5.2
Succeeded   : 61
```
 
* the onComplete message is shown when WtP is done 
* here you find again some basic information e.g. how long was your run, where are the results and a literature-file for citing us and the tools WtP uses