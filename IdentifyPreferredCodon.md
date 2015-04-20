# Introduction #

Here we provide a Java program to identify preferred codons in a genome using coding sequences as input.

This method we use here was previously described by Hershberg and Petrov in their PLoS Genetics (2009) paper [(PMID: 19593368)](http://www.ncbi.nlm.nih.gov/pubmed/19593368). Please acknowledge their work (and ours of course) if you find this tool useful.

This tool is written in Java so it will run on any OS with Java installed.

# What is a preferred codon and how to identify one? #

The design of the codon table is that 61 codons code for 20 amino acids, so an amino acid is often coded by multiple codons. Thus codons can be grouped into 20 groups (aka codon families), according to the coded amino acids. A preferred codon refers to a codon that is significantly more frequently used than expected within a codon family.

Methods to identify preferred codes:

  1. for each protein-coding gene in each genome a Nc value was calculated as the measure of the overall codon bias of the gene using the ENCprime program. Nc ranges from 20 (the most biased) to 61 (the least biased).
  1. For each gene the frequency of each valid codon was also calculated.
  1. for each codon a Spearman’s correlation was calculated between its frequencies across all coding genes in a specific genome and the Nc values of the corresponding coding genes.
  1. A preferred codon would be then selected for each codon family (a codon family contains all codons that code for the same amino acid) if it has the strongest and significant negative correlation value among all codons within this codon family, and a Spearman’s p-value less than 0.05/n, where n is the number of codons in this codon family.

# Downloads #

| **link** | **description** |
|:---------|:----------------|
| [Multithreading version](https://drive.google.com/open?id=0BwieX-ApVZM5bUtsQ2VBeWZCNTA&authuser=0) | Source codes and a precompiled jar are included; use this version if you wish to use multiple CPU-cores and have big memory |
| [Single thread version](https://drive.google.com/open?id=0BwieX-ApVZM5YWFXVXM3MlVKam8&authuser=0) | Source codes and a precompiled jar are included; use this version if you have slower machine and not so much memory |

**NOTES**
  1. It is a NetBeans 8 project. Unzip the archived file and open it with NetBeans, you can see the source codes.
  1. a precompile jar file can be found in the 'dist/' subfolder. to run it, JAVA 1.7 is required.
  1. this program uses a parallel library and it will be VERY memory-consuming, so please try not to run it on your laptop / desktop.

# Input file and prerequisites for running this tool #

  1. two executables, namely ENCprime and SeqCount are required; they are available for download from https://github.com/jnovembre/ENCprime
  1. a text file contains a list of input genomes is also needed; this file should contain two columns, separated by a single '\t' character. The 1st column is the accession number of a genome, and the 2nd is the full path to the coding sequence file of the genome. The sequences should be in fasta format. For example:
```
NC_012793       /path/to/NC_012793.fna
NC_012794       /path/to/NC_012794.fna
```

# A file contains pre-calculated preferred codons for 1550 prokaryotic genomes is available for download #

[here (Excel file)](https://drive.google.com/open?id=0BwieX-ApVZM5MnJ2T2hUZVF5SWM&authuser=0)