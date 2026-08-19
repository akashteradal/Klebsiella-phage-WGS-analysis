# Genomic Characterization of a *Klebsiella pneumoniae* Bacteriophage Using Whole Genome Sequencing

## Project Overview

This project involved the bioinformatics analysis of whole genome sequencing (WGS) data from a bacteriophage infecting *Klebsiella pneumoniae*.

The analysis was performed using paired-end Illumina sequencing data provided as part of the internship project. The workflow included read preprocessing, de novo genome assembly, assembly quality assessment, viral genome quality evaluation, phage genome annotation, genome visualization, and whole-genome phylogenetic analysis.

## Objectives

- Perform quality control and preprocessing of raw paired-end sequencing reads.
- Assemble the bacteriophage genome using de novo genome assembly.
- Evaluate assembly quality using standard assembly statistics.
- Assess viral genome completeness and quality.
- Annotate the bacteriophage genome using a phage-specific annotation tool.
- Visualize genome organization and genomic features.
- Determine the phylogenetic relationship of the bacteriophage using whole-genome comparison.

## Dataset

- **Sequencing technology:** Illumina
- **Data type:** Paired-end FASTQ reads
- **Approximate data size:** 3.9 GB
- **Data source:** Raw sequencing data provided for the internship project

The raw sequencing files are not included in this repository because of their large size and data-sharing considerations.

## Computational Environment

- Ubuntu Linux
- Windows Subsystem for Linux (WSL2)
- Conda environment for software installation and dependency management
- Galaxy web platform for selected analysis steps

## Bioinformatics Workflow

**Paired-End FASTQ Reads**  
           ↓  
**FastQC — Initial Quality Assessment**  
           ↓  
**Trimmomatic v0.39 — Read Trimming**  
           ↓  
**FastQC — Post-Trimming Quality Assessment**  
           ↓  
**SPAdes v3.15.5 — Phage Mode**  
           ↓  
**QUAST v5.2.0 — Assembly Quality Assessment**  
           ↓  
**CheckV v1.0.3 — Viral Genome Quality Assessment**  
           ↓  
**Pharokka — Phage Genome Annotation**  
           ↓  
**NODE_100 — Complete Viral Genome Selection**  
           ↓  
**Proksee — Genome Visualization**  
           ↓  
**ViPTree — Whole-Genome Phylogenetic Analysis**


## Results and Analysis

### 1. Quality Control and Read Preprocessing

The raw paired-end Illumina sequencing reads were assessed for quality before downstream analysis. Low-quality regions and sequencing artifacts were removed using **Trimmomatic v0.39**. A post-trimming quality assessment was then performed to confirm the quality of the processed reads.

A high proportion of reads were retained after preprocessing, indicating good initial sequencing quality. The resulting high-quality paired-end reads were used for de novo genome assembly.

### 2. De Novo Genome Assembly

The processed sequencing reads were assembled using **SPAdes v3.15.5 in phage mode**. This approach was used to reconstruct genomic regions of the bacteriophage from overlapping short sequencing reads.

The initial assembly produced:

- **13,238 contigs**
- **Approximately 16.6 Mb total assembled length**
- **Largest contig: approximately 8.7 kb**
- **Initial N50: 1,462 bp**

Because the initial assembly was highly fragmented, contigs of **≥5 kb** were selected for downstream analysis. After filtering, **103 contigs** remained and the N50 increased to **5,686 bp**, indicating improved assembly continuity.

### 3. Assembly Quality Assessment

**QUAST v5.2.0** was used to evaluate the quality of the assembled contigs. The analysis considered assembly statistics such as contig number, genome length, N50, L50, and GC content.

The filtered assembly showed an **N50 of 5,686 bp** and an approximate **GC content of 47%**. No ambiguous bases were detected in the assembly, supporting the reliability of the assembled sequences for downstream analysis.

### 4. Viral Genome Quality Assessment

**CheckV v1.0.3** was used to assess the viral nature, completeness, and potential host contamination of the assembled contigs.

Most contigs were classified as genome fragments with varying completeness estimates. CheckV confirmed the viral nature of key contigs, allowing suitable viral sequences to be taken forward for functional and comparative analysis.

### 5. Phage Genome Annotation

Phage genome annotation was performed using **Pharokka** through the **Galaxy** platform. Pharokka was used to identify coding sequences, tRNA genes, and phage-associated proteins.

The annotation identified:

- **542 coding sequences (CDSs)**
- **2 tRNA genes**

Several predicted proteins were associated with important viral processes, including replication and transcription. However, a substantial proportion of predicted proteins were annotated as **hypothetical proteins**, reflecting the limited functional characterization of many bacteriophage proteins in available databases.

Among the assembled contigs, **NODE_100 showed higher viral gene content** and was therefore selected for further genome visualization and phylogenetic analysis.

### 6. Genome Visualization

The Pharokka-annotated GenBank file of **NODE_100** was analyzed using **Proksee**.

A circular genome map was generated to visualize:

- Coding sequence distribution
- Gene orientation
- GC content
- GC skew

The visualization provided an overall view of the genome organization and compositional characteristics of the selected phage contig.

### 7. Whole-Genome Phylogenetic Analysis

The evolutionary relationship of NODE_100 with known bacteriophages was investigated using **ViPTree**.

ViPTree performs whole-genome proteomic comparisons to determine relationships between viral genomes. The resulting phylogenetic analysis placed **NODE_100 with related *Klebsiella*-infecting bacteriophages**, indicating an evolutionary relationship with known phage lineages.


## Key Findings

The integrated whole-genome sequencing workflow successfully enabled the characterization of the *Klebsiella pneumoniae* bacteriophage from raw paired-end Illumina sequencing data.

- Quality control and read preprocessing produced high-quality reads suitable for downstream genome assembly.
- De novo assembly generated multiple contigs, and filtering for contigs ≥5 kb improved assembly continuity.
- Viral genome assessment identified contigs suitable for further phage genomic analysis.
- Phage-specific annotation identified coding sequences, tRNA genes, and several predicted viral proteins, including replication-related proteins.
- A large proportion of predicted proteins were classified as hypothetical proteins, highlighting the limited functional characterization of bacteriophage genomes.
- NODE_100 was selected for further analysis based on its higher viral gene content.
- Genome visualization provided an overview of gene organization and genomic composition.
- Whole-genome phylogenetic analysis placed NODE_100 among related *Klebsiella*-infecting bacteriophages, supporting its evolutionary relationship with known phage lineages.


## Conclusion

This study demonstrated the application of a complete bioinformatics workflow for characterizing a *Klebsiella pneumoniae* bacteriophage using whole-genome sequencing data. The analysis progressed from raw read quality assessment and de novo genome assembly to viral genome evaluation, phage annotation, genome visualization, and whole-genome phylogenetic analysis. NODE_100 showed strong viral characteristics and was associated with known *Klebsiella*-infecting bacteriophage lineages, providing a basis for further genomic and functional characterization.


## Repository Structure

The repository will be organized to document the major stages of the bacteriophage whole-genome sequencing and bioinformatics analysis.

- `README.md` — Project overview, workflow, results, and conclusions.
- `results/` — Important analysis results and output files.
- `figures/` — Genome visualization and phylogenetic analysis figures.
- `scripts/` — Analysis commands or scripts used during the workflow.

Raw sequencing data are not included in this repository because of their large file size and data-sharing considerations.


## Acknowledgments

The raw paired-end Illumina sequencing data used in this project were provided by my mentor as part of the internship project.

The bioinformatics analysis and interpretation presented in this repository were performed as part of the internship work.


## References

1. Dion MB, Oechslin F, Moineau S. Phage diversity, genomics and phylogeny. *Nature Reviews Microbiology*. 2020;18(3):125–138.

2. Bolger AM, Lohse M, Usadel B. Trimmomatic: a flexible trimmer for Illumina sequence data. *Bioinformatics*. 2014;30(15):2114–2120.

3. Bankevich A, Nurk S, Antipov D, et al. SPAdes: a new genome assembly algorithm and its applications to single-cell sequencing. *Journal of Computational Biology*. 2012;19(5):455–477.

4. Gurevich A, Saveliev V, Vyahhi N, Tesler G. QUAST: quality assessment tool for genome assemblies. *Bioinformatics*. 2013;29(8):1072–1075.

5. Nayfach S, Camargo AP, Schulz F, et al. CheckV assesses the quality and completeness of metagenome-assembled viral genomes. *Nature Biotechnology*. 2021;39(5):578–585.

6. Bouras G, Nepal R, Houtak G, et al. Pharokka: a fast and flexible phage annotation pipeline. *Bioinformatics*. 2023;39(1):btac776.

7. Grant JR, Stothard P. Proksee: in-depth characterization and visualization of bacterial genomes. *Bioinformatics*. 2023;39(6):btad326.

8. Nishimura Y, Yoshida T, Kuronishi M, et al. ViPTree: the viral proteomic tree server. *Bioinformatics*. 2017;33(15):2379–2380.


## License

The code, documentation, and analysis workflow in this repository are provided for educational and research purposes.

The raw sequencing data used in this project were provided as part of the internship and are not included in this repository.
