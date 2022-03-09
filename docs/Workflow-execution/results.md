## Example run
We executed the following commands do perform a WtP test-run from the Terminal-section:
 
```bash
nextflow run phage.nf -profile smalltest,local,docker --work-dir --cores 16
```
 
WtP will create a `results`-folder in your current working dir (where you executed WtP) and a subfolder with the name of your input-fasta - in our case `all_pos_phage`
 
## Results
 
`literature`  

* contains a Citations.bib file which you can import the in your citation program to have all the citations of the programs WtP uses for its analysis
 
`run info`
 
execution_report.html:
 
* this report gives an overview over: 
   * distribution of resource usage for each process (CPU, Memory, Job duration) 
   * information about each task in the workflow 
 
execution_timeline.html: 
 
* this report gives you an overview over the processes execution timeline 
 
--------------------------------------------------
## Test sample result
 
A testreport for a larger dataset can be found [here](https://replikation.github.io/What_the_Phage/)


--------------------------------------------------
 
`raw_data`
 
 * contains the raw output from the phage-identification-tools packed as toolname.tar.gz -file
 
--------------------------------------------------
 
`sample_overview-small.html, sample_overview-large.html`
 
![chromomap results](chromomap-small.png)   
![chromomap results](chromomap-large.png)
 
The graphical output of the annotation shows an overview of the individual loci of the predicted ORFs and the corresponding genes in the fasta sequences identified as phages. For a better visibility, we have chosen 4 categories: tail, capsid, baseplate, and other. This output can be used to verify the identified sequences (if the predicted sequences make sense or not). The annotation results are additionally plotted in an interactive HTML-file and are available as a file for further analysis.
 
--------------------------------------------------
 
 

