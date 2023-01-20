# Genome Assembly
## Quality Control
On the Galaxy panel, click on the upload data button and drag and drop the FastQ file for analysis.
Select the FastQC program from the list of tools.
Select the uploaded data for the option 'short read data fom your current history',
Leave the other options as default and click the Execute button.
## Contig assembly
Open the velveth program in Galaxy
In the program options,click on insert input files and select the FASTQ file previously uploaded.
Leave the options as default and click on the execute button.
After the De Bruijn graphs has been built, open the program velvetg and select as its input the output of velveth.
In the 'set minimum contig 'length' select yes and set to 100.
leave the options as default and click on Execute.
five files will be generated from as the output but the file Contigs and Stats are of interest.
## Combining contigs into scaffolds
In a web browser open the genome database at the European Bioinformatics Institute (EBI).
Select the Bacteria genome page in the menu on the left and through the list of genomes to find entries for Campylobacter coli
In the Campylobacter coli 76339 isolate row,click on 'HG326877'in the sequence HTML (the 5th column).
Save the genome sequence file on the PC by right clicking on the Download:Fasta link
Open the BLASTN page at NCBI,and ensure that the blast tab is selected. Click on the 'Align two or more sequences'option.
In the first (Query)sequence use the 'Browse'button to upload the 'Contigs' file generated with 'Velvet'. 
In the subject sequence upload the genome sequence retrieved from EBI.
leave the 'megablast' option selected.
click on the 'BLAST' button.
Download the Hit Table after the BLAST has completed.
Column I and J have the start and end mapping positions in the reference genome.
#Functional annotation of genomes
##Automatic annotation of bacterial genomes
In the Galaxy platform,use the upload tool to upload the genome assembly file campylo.fas,in the Type menu,select 'fasta' format and click start
Find Augustus in the tools panel.
In tge 
