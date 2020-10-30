# WtP terminal execution:
In this section we want to explain what you see in the Terminal when you execute WtP:

## WIP
## Let's do a Testrun
Open your terminal(resize it to the whole screen), move to a directory where you want to execute WtP and type/copy the following command  

```bash
nextflow run phage.nf -profile smalltest,local,docker --work-dir --cores 16
```

Now you will see a lot of Processes popping up:  

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

 * 
 
```bash

[6b/79564a] process > identify_fasta_MSF:fasta_validation_wf:input_suffix_check (1)           [100%] 1 of 1 ✔
[c7/d34016] process > identify_fasta_MSF:fasta_validation_wf:seqkit (1)                       [100%] 1 of 1 ✔
[-        ] process > identify_fasta_MSF:virsorter_wf:virsorter                               [  0%] 0 of 1
[-        ] process > identify_fasta_MSF:virsorter_wf:filter_virsorter                        -
[-        ] process > identify_fasta_MSF:virsorter_wf:virsorter_collect_data                  -
[ff/f698ec] process > identify_fasta_MSF:virsorter2_wf:virsorter2 (1)                         [  0%] 0 of 1
[-        ] process > identify_fasta_MSF:virsorter2_wf:filter_virsorter2                      -
executor >  local (8)
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
[-        ] process > identify_fasta_MSF:virsorter_virome_wf:virsorter_virome                 [  0%] 0 of 1
[-        ] process > identify_fasta_MSF:virsorter_virome_wf:filter_virsorter_virome          -
[-        ] process > identify_fasta_MSF:virsorter_virome_wf:virsorter_virome_collect_data    -
[39/892692] process > identify_fasta_MSF:marvel_wf:split_multi_fasta (1)                      [100%] 1 of 1 ✔
[-        ] process > identify_fasta_MSF:marvel_wf:marvel                                     [  0%] 0 of 1
[-        ] process > identify_fasta_MSF:marvel_wf:filter_marvel                              -
[-        ] process > identify_fasta_MSF:marvel_wf:marvel_collect_data                        -
[3e/7c817b] process > identify_fasta_MSF:sourmash_wf:split_multi_fasta (1)                    [100%] 1 of 1 ✔
[-        ] process > identify_fasta_MSF:sourmash_wf:sourmash                                 [  0%] 0 of 1
[-        ] process > identify_fasta_MSF:sourmash_wf:filter_sourmash                          -
[-        ] process > identify_fasta_MSF:sourmash_wf:sourmash_collect_data                    -
[-        ] process > identify_fasta_MSF:metaphinder_wf:metaphinder                           [  0%] 0 of 1
[-        ] process > identify_fasta_MSF:metaphinder_wf:filter_metaphinder                    -
[-        ] process > identify_fasta_MSF:metaphinder_wf:metaphinder_collect_data              -
[-        ] process > identify_fasta_MSF:metaphinder_own_DB_wf:metaphinder_own_DB             [  0%] 0 of 1
[-        ] process > identify_fasta_MSF:metaphinder_own_DB_wf:filter_metaphinder_own_DB      -
[-        ] process > identify_fasta_MSF:metaphinder_own_DB_wf:metaphinder_collect_data_ownDB -
[a8/b8dadd] process > identify_fasta_MSF:deepvirfinder_wf:deepvirfinder (1)                   [  0%] 0 of 1
[-        ] process > identify_fasta_MSF:deepvirfinder_wf:filter_deepvirfinder                -
[-        ] process > identify_fasta_MSF:deepvirfinder_wf:deepvirfinder_collect_data          -
[-        ] process > identify_fasta_MSF:virfinder_wf:virfinder                               [  0%] 0 of 1
[-        ] process > identify_fasta_MSF:virfinder_wf:filter_virfinder                        -
[-        ] process > identify_fasta_MSF:virfinder_wf:virfinder_collect_data                  -
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

* after 30 min
```bash
[6b/79564a] process > identify_fasta_MSF:fasta_validation_wf:input_suffix_check (1)               [100%] 1 of 1 ✔
[c7/d34016] process > identify_fasta_MSF:fasta_validation_wf:seqkit (1)                           [100%] 1 of 1 ✔
[d4/25d5ec] process > identify_fasta_MSF:virsorter_wf:virsorter (1)                               [100%] 1 of 1 ✔
[d0/41eecd] process > identify_fasta_MSF:virsorter_wf:filter_virsorter (1)                        [100%] 1 of 1 ✔
[39/6ccdf3] process > identify_fasta_MSF:virsorter_wf:virsorter_collect_data (1)                  [100%] 1 of 1 ✔
[ff/f698ec] process > identify_fasta_MSF:virsorter2_wf:virsorter2 (1)                             [  0%] 0 of 1
[-        ] process > identify_fasta_MSF:virsorter2_wf:filter_virsorter2                          -
[-        ] process > identify_fasta_MSF:virsorter2_wf:virsorter2_collect_data                    -
[38/7a44b2] process > identify_fasta_MSF:virsorter_virome_wf:virsorter_virome (1)                 [100%] 1 of 1 ✔
[5e/0242a1] process > identify_fasta_MSF:virsorter_virome_wf:filter_virsorter_virome (1)          [100%] 1 of 1 ✔
[74/04b03f] process > identify_fasta_MSF:virsorter_virome_wf:virsorter_virome_collect_data (1)    [100%] 1 of 1 ✔
[39/892692] process > identify_fasta_MSF:marvel_wf:split_multi_fasta (1)                          [100%] 1 of 1 ✔
[cf/aac9b6] process > identify_fasta_MSF:marvel_wf:marvel (1)                                     [100%] 1 of 1 ✔
[d1/efd14f] process > identify_fasta_MSF:marvel_wf:filter_marvel (1)                              [100%] 1 of 1 ✔
[d2/54c214] process > identify_fasta_MSF:marvel_wf:marvel_collect_data (1)                        [100%] 1 of 1 ✔
[3e/7c817b] process > identify_fasta_MSF:sourmash_wf:split_multi_fasta (1)                        [100%] 1 of 1 ✔
[66/67563a] process > identify_fasta_MSF:sourmash_wf:sourmash (1)                                 [100%] 1 of 1 ✔
[e7/1e0fab] process > identify_fasta_MSF:sourmash_wf:filter_sourmash (1)                          [100%] 1 of 1 ✔
[1e/a2db47] process > identify_fasta_MSF:sourmash_wf:sourmash_collect_data (1)                    [100%] 1 of 1 ✔
[21/755a4e] process > identify_fasta_MSF:metaphinder_wf:metaphinder (1)                           [100%] 1 of 1 ✔
[ae/6efb67] process > identify_fasta_MSF:metaphinder_wf:filter_metaphinder (1)                    [100%] 1 of 1 ✔
[32/b28c92] process > identify_fasta_MSF:metaphinder_wf:metaphinder_collect_data (1)              [100%] 1 of 1 ✔
[9a/9f579e] process > identify_fasta_MSF:metaphinder_own_DB_wf:metaphinder_own_DB (1)             [100%] 1 of 1 ✔
[e9/94dab1] process > identify_fasta_MSF:metaphinder_own_DB_wf:filter_metaphinder_own_DB (1)      [100%] 1 of 1 ✔
[25/9f603c] process > identify_fasta_MSF:metaphinder_own_DB_wf:metaphinder_collect_data_ownDB (1) [100%] 1 of 1 ✔
[a8/b8dadd] process > identify_fasta_MSF:deepvirfinder_wf:deepvirfinder (1)                       [100%] 1 of 1 ✔
[0d/bd99d5] process > identify_fasta_MSF:deepvirfinder_wf:filter_deepvirfinder (1)                [100%] 1 of 1 ✔
[e7/01c318] process > identify_fasta_MSF:deepvirfinder_wf:deepvirfinder_collect_data (1)          [100%] 1 of 1 ✔
[40/46b0b6] process > identify_fasta_MSF:virfinder_wf:virfinder (1)                               [100%] 1 of 1 ✔
[ef/f0d3c7] process > identify_fasta_MSF:virfinder_wf:filter_virfinder (1)                        [100%] 1 of 1 ✔
[ad/bee7aa] process > identify_fasta_MSF:virfinder_wf:virfinder_collect_data (1)                  [100%] 1 of 1 ✔
[fc/e0fcc7] process > identify_fasta_MSF:pprmeta_wf:pprmeta (1)                                   [100%] 1 of 1 ✔
[51/aa554b] process > identify_fasta_MSF:pprmeta_wf:filter_PPRmeta (1)                            [100%] 1 of 1 ✔
[fb/39f826] process > identify_fasta_MSF:pprmeta_wf:pprmeta_collect_data (1)                      [100%] 1 of 1 ✔
[6b/2add4a] process > identify_fasta_MSF:vibrant_wf:vibrant (1)                                   [100%] 1 of 1 ✔
[53/9e38f2] process > identify_fasta_MSF:vibrant_wf:filter_vibrant (1)                            [100%] 1 of 1 ✔
[c9/44f88a] process > identify_fasta_MSF:vibrant_wf:vibrant_collect_data (1)                      [100%] 1 of 1 ✔
[db/897fb6] process > identify_fasta_MSF:vibrant_virome_wf:vibrant_virome (1)                     [100%] 1 of 1 ✔
[1b/03af21] process > identify_fasta_MSF:vibrant_virome_wf:filter_vibrant_virome (1)              [100%] 1 of 1 ✔
[6b/a1390d] process > identify_fasta_MSF:vibrant_virome_wf:vibrant_virome_collect_data (1)        [100%] 1 of 1 ✔
[08/50ce71] process > identify_fasta_MSF:virnet_wf:normalize_contig_size (1)                      [100%] 1 of 1 ✔
[a9/ea50cb] process > identify_fasta_MSF:virnet_wf:virnet (1)                                     [100%] 1 of 1 ✔
[13/a41f33] process > identify_fasta_MSF:virnet_wf:filter_virnet (1)                              [100%] 1 of 1 ✔
[0f/c89610] process > identify_fasta_MSF:virnet_wf:virnet_collect_data (1)                        [100%] 1 of 1 ✔
[4e/ca5a07] process > identify_fasta_MSF:phigaro_wf:phigaro (1)                                   [100%] 1 of 1 ✔
[69/9d3a8c] process > identify_fasta_MSF:phigaro_wf:phigaro_collect_data (1)                      [100%] 1 of 1 ✔
[e1/809e03] process > identify_fasta_MSF:seeker_wf:seeker (1)                                     [100%] 1 of 1 ✔
[0c/bc83b7] process > identify_fasta_MSF:seeker_wf:filter_seeker (1)                              [100%] 1 of 1 ✔
[46/6a91e7] process > identify_fasta_MSF:seeker_wf:seeker_collect_data (1)                        [100%] 1 of 1 ✔
[-        ] process > identify_fasta_MSF:filter_tool_names                                        -
[-        ] process > identify_fasta_MSF:r_plot                                                   -
[-        ] process > identify_fasta_MSF:upsetr_plot                                              -
[-        ] process > identify_fasta_MSF:samtools                                                 -
[-        ] process > phage_annotation_MSF:prodigal                                               -
[-        ] process > phage_annotation_MSF:hmmscan                                                -
[-        ] process > phage_annotation_MSF:chromomap_parser                                       -
[-        ] process > phage_annotation_MSF:chromomap                                              -
[-        ] process > checkV_wf:checkV                                                            -
[-        ] process > phage_tax_classification:split_multi_fasta                                  -
[-        ] process > phage_tax_classification:sourmash_for_tax                                   -


Done! Results are stored here --> results 
Thank you for using What the Phage
 
Please cite us: https://doi.org/10.1101/2020.07.24.219899                                       

Please also cite the other tools we use in our workflow --> results/literature
Completed at: 30-Oct-2020 10:15:27
Duration    : 49m 34s
CPU hours   : 5.2
Succeeded   : 61
```
