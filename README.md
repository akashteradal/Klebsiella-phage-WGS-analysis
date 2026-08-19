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

```text
Paired-End FASTQ Reads
          │
          ▼
Quality Control & Read Preprocessing
          │
          ▼
      Trimmomatic
          │
          ▼
   SPAdes Phage Mode
          │
          ▼
        QUAST
          │
          ▼
       CheckV
          │
          ▼
      Pharokka
          │
          ▼
     NODE_100
       /     \
      ▼       ▼
   Proksee  ViPTree
      │       │
      ▼       ▼
Genome      Whole-Genome
Map         Phylogenetic Analysis

## Results

### Quality Control and Read Preprocessing

- Raw paired-end Illumina reads were assessed for sequencing quality using FastQC.
- Adapter and low-quality sequences were removed using Trimmomatic.
- The processed reads were used for downstream de novo genome assembly.

### Genome Assembly

- De novo genome assembly was performed using SPAdes in phage mode.
- The assembly generated multiple contigs, which were evaluated using QUAST.
- The assembly showed an N50 of approximately 5.7 kb and a GC content of approximately 47%.

### Viral Genome Quality Assessment

- CheckV was used to evaluate viral genome completeness and quality.
- Contig NODE_100 was identified as the complete viral genome and selected for downstream analysis.

### Genome Annotation

- Phage genome annotation was performed using Pharokka.
- The annotation identified predicted coding sequences and genomic features for the assembled phage genome.

### Genome Visualization and Phylogenetic Analysis

- Proksee was used for genome visualization and genomic feature representation.
- ViPTree was used for whole-genome phylogenetic analysis to investigate the relationship of the phage with other viral genomes.
