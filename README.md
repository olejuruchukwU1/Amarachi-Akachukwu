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
In the Genome sequence menu, select the uploaded genpme
In the model organism select 'E coli K12'.
Inthe GFF formatted output option select Yes.
click Execute
open the search in text files (grep) tools from the tools panel.
Select the GFF file from Augustus as the input.
Select the option NON matching.
In pattern write ^#
Execute
Copy the sequence of the first annotated gene from August output file Coding sequence.
BLAST this in the NCBI  Nucleotide BLAST page.
##Gene expression analysis:measuring transcripts levels with RNA-Seq.
Open the public repository Sequence Read Archive (SRA).
Find the dataset ERR036499.<
In the Galaxy webpage,find and open the tool Download and Extract Reads in FASTA/Q.
In the Accession field type ERR036499,and click Execute.
Open and find tool Bowtie2.
Select the FASTQ file extracted from SRA.
In the will you select a reference option select Use a genome from history and build index and choose the Campylobacter FASTA genome uploaded.
Open the program htseq-count and select the BAM file from Bowtie2.
Select the GFF annotation file generated from Augustus;in the feature write CDS and in the ID attribute write ID.
Execute.
##Gene expression analysis:differential gene expression
Download the file campylobacter expression.zip file.
open the DESEQ2 tool.
In option 1:Factor write lab. In option 1:Factor level select in the counts file(s)box samples 1 and 2
In option 2:Factor level select in the Counts file(s)box samples 3 and 4.
Change the name of the factor levels;Lab A and Lab B.
Leave all the options as default and Execute.
Open the Filter tool and runit on the output from DESeq2. The conditions to filter on are c3>2 and c7<0.01.
Use the cut tool to select column 1.
##Functional annotation of gene lists: Gene ontology enrichment
open the gene ontology browser using http://geneontology.org.
Paste in the gene ontology windows the gene obtained from 61
select Biological process and the species E.coli.
Launch.
#
