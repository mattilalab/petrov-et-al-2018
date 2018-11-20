# Computational analysis of the evolutionarily conserved Missing In Metastasis / Metastasis Suppressor 1 gene predicts novel interactions, regulatory regions and transcriptional control

Petrov _et al_ 2018 (MANUSCRIPT)

Home-brewed shell scripts.

These simple shell scripts were tested on Slackware GNU/Linux (http://www.slackware.com/). All prerequisites were installed from the scripts at SlackBuilds.org (http://slackbuilds.org).

## Prerequisites

You need the following:

1.  **RepeatMasker** (Screen DNA sequence for interspersed repeats)
    * Homepage: http://www.repeatmasker.org/
    * On SBo: http://slackbuilds.org/repository/14.2/academic/RepeatMasker/
2.  **BedTools** (A powerful toolset for genome arithmetic)
    * Homepage: http://bedtools.readthedocs.org/
    * On SBo: http://slackbuilds.org/repository/14.2/academic/bedtools/
3.  **MEME-suite** (Motif based sequence analysis tools)
    * Homepage: http://meme-suite.org/
    * On SBo: http://slackbuilds.org/repository/14.2/academic/meme-suite/
4.  **Motif databases** (Used by the MEME Suite)
    * Download: http://meme-suite.org/doc/download.html
    * Location: `/var/lib/meme-suite/motif_databases`

## TFBS: transcription factor binding sequences

Scripts are divided into two folders:

1.  **tfKnown**: This folder contains scripts that were used in our study to acquire data for transcription factor (TF) binding sequences. We used TFs reported for _H. sapiens_ to also screen the corresponding genomic regions of other species. 

Contents:
    * 00_batchFromNCBI/
        * `batchFromNCBI`: Download chromosomes from NCBI for a list of species
        * `batchGunzip`: Batch extract gzipped chromosomes
    * 01_memePrepKnown/
        * `memePrepKnown`: Extract and sort corresponding genomic regions from multiple species
    * 02_extractTFmatrix/
        * `extractTFmatrix`: Extract PFM from (4) databases for a list of transcription factors
    * 03_mastOnly/
        * `mastOnly`: Run MAST with selected PFM on genomic regions of interest
    * 04_mastBestSort/
        * `mastBestSort`: Create a CVS table of the best TF hits    
    
2.  **tfUnknown**: This folder contains scripts that were used in our study to predict for novel TF binding sequences. We used TFs predicted for _H. sapiens_ to also screen the corresponding genomic regions of other species.

Contents:
    * 01_memePrepUnknown/
        * `memePrepUnknown`: Extract and sort corresponding genomic regions from multiple species
        * `sequenceRepeatMasker`: Mask repeates on the sorted genomic regions
    * 02_searchUnknown/
        * `novelTF`: Search for novel transcription factor binding sites by MEME-suite
    * 03_mastOnlyUnknown/
        * `mastOnlyUnknown`: Run MAST with selected PFM on genomic regions of interest
    * 04_mastBestSortUnknown/
        * `mastBestSortUnknown`: Create a CVS table of the best TF hits


**Please note!**

This is work in progress. We are in the process of commenting our home-made scripts. We expect it to be ready till 23 November!
