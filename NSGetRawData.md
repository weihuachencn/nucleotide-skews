

## Introduction ##

create a folder with name "**_bacteria_**", and put everything into this folder.

## get genome sequences and annotation ##

  1. genome sequences
    * create a subfolder **_bacterial\_genomes\_seqs\_fasta_**
    * go to this subfolder (now working directory should be "_**bacteria/bacterial\_genomes\_seqs\_fasta**_") and download all complete prokaryotic genomes from NCBI: [ftp://ftp.ncbi.nlm.nih.gov/genomes/Bacteria/all.fna.tar.gz](ftp://ftp.ncbi.nlm.nih.gov/genomes/Bacteria/all.fna.tar.gz)
    * unzip downloaded file using command :
```
tar -zxvf all.fna.tar.gz
```
    * the downloaded file 'all.fna.tar.gz' can be then deleted

> 2. genome annotation
    * create a subfolder "**_bacterial\_gffs_**" in folder "_**bacteria**_" and go to this newly created folder; current working directory should be "**_bacteria/bacterial\_gffs_**"
    * download annotations in GFF format from NCBI: : [ftp://ftp.ncbi.nlm.nih.gov/genomes/Bacteria/all.gff.tar.gz](ftp://ftp.ncbi.nlm.nih.gov/genomes/Bacteria/all.gff.tar.gz)
    * unzip this file with command:
```
tar -zxvf all.gff.tar.gz
```

## replication origin sites ##

Replication origin sites can be obtained from [DoriC - a database of oriC regions in bacterial genomes](http://tubic.tju.edu.cn/doric/). Please always use the latest data from this database.

The replication origin sites we obtained can be downloaded from here: .

##  ##