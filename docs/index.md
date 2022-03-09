![logo](figures/logo-wtp_small.png)
[![Twitter Follow](https://img.shields.io/twitter/follow/gcloudChris.svg?style=social)](https://twitter.com/gcloudChris) 
[![Twitter Follow](https://img.shields.io/twitter/follow/mult1fractal.svg?style=social)](https://twitter.com/mult1fractal)

![](https://img.shields.io/github/v/release/replikation/What_the_Phage)
![](https://img.shields.io/badge/licence-GPL--3.0-lightgrey.svg)
![](https://github.com/replikation/What_the_Phage/workflows/Syntax_check/badge.svg)

![](https://img.shields.io/badge/nextflow-20.07.1-brightgreen)
![](https://img.shields.io/badge/uses-docker-blue.svg)
![](https://img.shields.io/badge/uses-singularity-yellow.svg)

[![Generic badge](https://img.shields.io/badge/Preprint-bioRxiv-red.svg)](https://www.biorxiv.org/content/10.1101/2020.07.24.219899v1)

**[CaSe-Group](https://case-group.github.io/)**


> **What the Phage: A scalable workflow for the identification and analysis of phage sequences**
>
> M. Marquet, M. Hölzer, M. W. Pletz, A. Viehweger, O. Makarewicz, R. Ehricht, C. Brandt
>
> doi: https://doi.org/10.1101/2020.07.24.219899

-----------------------------------------
# System Requirements

| Components | minimum | recomended |
|-|-|-|
| OS | Linux like | Linux like |
| Cores | 4 | 8 |
| Memory | 4 GB RAM | 8 GB RAM |
| Storage | 50 GB available space | 128-256 GB available space | 

[Why so much space? -.-](troubleshooting.md)

-----------------------------------------

## What the Phage
Phages are among the most abundant and diverse biological entities on earth. Identification from sequence data is a crucial first step to understand their impact on the environment. A variety of bacteriophage identification tools have been developed over the years. They differ in algorithmic approach, results and ease of use. We, therefore, developed “What the Phage” (WtP), an easy-to-use and parallel multitool approach for phage identification combined with an annotation and classification downstream strategy, thus, supporting the user’s decision-making process when the phage identification tools are not in agreement to each other. WtP is reproducible and scales to thousands of datasets through the use of a workflow manager (Nextflow).

-----------------------------------------

## Under the hood

![plot](figures/wtp-flowchart-simple.png)

*Figure 3:* This plot shows a simplified dag-chart of WtP for better understanding of what's going on behind the curtain  

-----------------------------------------
## Included tools

### Identification

Toolname/Gitlink | Reference |
|-|-|
[VirFinder](https://github.com/jessieren/VirFinder)|[VirFinder: R package for identifying viral sequences from metagenomic data using sequence signatures](https://link.springer.com/epdf/10.1186/s40168-017-0283-5?)
[PPR-Meta](https://github.com/zhenchengfang/PPR-Meta)|[PPR-Meta: a tool for identifying phages and plasmids from metagenomic fragments using deep learning](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6586199/)
[VirSorter](https://github.com/simroux/VirSorter)|[VirSorter: mining viral signal from microbial genomic data](https://peerj.com/articles/985/)
[MetaPhinder](https://github.com/vanessajurtz/MetaPhinder)|[MetaPhinder—Identifying Bacteriophage Sequences in Metagenomic Data Sets](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0163111)
[DeepVirFinder](https://github.com/jessieren/DeepVirFinder)|[Identifying viruses from metagenomic data by deep learning](https://arxiv.org/abs/1806.07810)
[Sourmash](https://github.com/dib-lab/sourmash)|[sourmash: a library for MinHash sketching of DNA](https://joss.theoj.org/papers/10.21105/joss.00027)|
[VIBRANT](https://github.com/AnantharamanLab/VIBRANT)|[Automated recovery, annotation and curation of microbial viruses, and evaluation of virome function from genomic sequences](https://www.biorxiv.org/content/biorxiv/early/2019/11/26/855387.full.pdf)
[VirNet](https://github.com/alyosama/virnet)|[Deep attention model for viral reads identification](https://ieeexplore.ieee.org/document/8639400)
[Phigaro](https://github.com/bobeobibo/phigaro)| [Phigaro: high throughput prophage sequence annotation](https://www.biorxiv.org/content/10.1101/598243v1)
[Virsorter2](https://github.com/jiarong/VirSorter2)| [VirSorter2: a multi-classifier, expert-guided approach to detect diverse DNA and RNA viruses](https://escholarship.org/content/qt4d30q22s/qt4d30q22s.pdf?t=qok4nd)]|
[Seeker](https://github.com/gussow/seeker)|[Seeker: alignment-free identification of bacteriophage genomes by deep learning](https://doi.org/10.1093/nar/gkaa856)|

### Annotation & classification

|Toolname/Git | Reference|
|-|-|
[prodigal](https://github.com/hyattpd/Prodigal)|[Prodigal: prokaryotic gene recognition and translation initiation site identification](https://bmcbioinformatics.biomedcentral.com/articles/10.1186/1471-2105-11-119)|
[hmmer](http://hmmer.org/)|[nhmmer: DNA homology search with profile HMMs](https://academic.oup.com/bioinformatics/article/29/19/2487/186765)|
[chromomap](https://cran.r-project.org/web/packages/chromoMap/vignettes/chromoMap.html)||
[CheckV](https://bitbucket.org/berkeleylab/checkv/src/master/)|[CheckV: assessing the quality of metagenome-assembled viral genomes](https://www.biorxiv.org/content/10.1101/2020.05.06.081778v1)|


### Other tools

|Toolname/Git | Reference|
|-|-|
[samtools](https://github.com/samtools/samtools)|[The Sequence Alignment/Map format and SAMtools](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2723002/)|
[seqkit](https://github.com/shenwei356/seqkit)|[SeqKit: A Cross-Platform and Ultrafast Toolkit for FASTA/Q File Manipulation](https://ieeexplore.ieee.org/document/8639400)|
[UpSetR](https://github.com/hms-dbmi/UpSetR)|[UpSetR: an R package for the visualization of intersecting sets and their properties](https://doi.org/10.1093/bioinformatics/btx364)|



<!-- ### MARVEL  
### VirFinder  
[Citation](https://link.springer.com/epdf/10.1186/s40168-017-0283-5?) [github](https://github.com/jessieren/VirFinder)

### PPR-Meta  
[Citation](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6586199/) [github](https://github.com/zhenchengfang/PPR-Meta)

### VirSorter  
[Citation](https://peerj.com/articles/985/) [github](https://github.com/simroux/VirSorter)

### MetaPhinder  
[Citation](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0163111) [github](https://github.com/vanessajurtz/MetaPhinder)

### DeepVirFinder  
[Citation](https://arxiv.org/abs/1806.07810) [github](https://github.com/jessieren/DeepVirFinder)

### Sourmash  
[Citation](https://joss.theoj.org/papers/10.21105/joss.00027) [github](https://github.com/dib-lab/sourmash)

### VIBRANT  
[Citation](https://www.biorxiv.org/content/biorxiv/early/2019/11/26/855387.full.pdf) [github](https://github.com/AnantharamanLab/VIBRANT)

### VirNet  
[Citation](https://ieeexplore.ieee.org/document/8639400) [github](https://github.com/alyosama/virnet)

### Phigaro  
[Citation](https://www.biorxiv.org/content/10.1101/598243v1) [github](https://github.com/bobeobibo/phigaro)

### Virsorter2 beta  
[github](https://github.com/jiarong/VirSorter2)
 -->


-----------------------------------------

.