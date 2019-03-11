# Computational analysis of the evolutionarily conserved Missing In Metastasis / Metastasis Suppressor 1 gene predicts novel interactions, regulatory regions and transcriptional control

_Petar Petrov<sup>1*</sup>, Alexey V. Sarapulov<sup>1</sup>, Lel Eöry <sup>2</sup>, Cristina Scielzo<sup>3,4</sup>, Lydia Scarfò<sup>3,4,5</sup>, Jacqueline Smith<sup>2</sup>, David W. Burt<sup>6</sup> & Pieta K. Mattila<sup>1</sup>_

1. Institute of Biomedicine, and MediCity Research Laboratories, University of Turku, Tykistökatu 6A, 20520, Turku,
Finland. 
2. Division of Genetics and Genomics, The Roslin Institute and R(D)SVS, University of Edinburgh, Roslin,
Easter Bush campus, Midlothian, EH25 9RG, United Kingdom. 
3. Unit of B Cell Neoplasia, Division of Molecular
Oncology, IRCCS, San Raffaele Scientific Institute, Milano, Italy. 
4. Università Vita-Salute San Raffaele, Milan, Italy.
5. Strategic Research Program on CLL, Division of Experimental Oncology, IRCCS, San Raffaele Scientific Institute,
Milano, Italy. 
6. University of Queensland, St. Lucia, QLD, 4072, Australia.

**Scientific Reports** https://www.nature.com/articles/s41598-019-40697-1

* Correspondence and requests for the scripts should be addressed to Petar Petrov (firstname.lastname@utu.fi)

# Shell scripts used in the study.

These simple shell scripts were tested on Slackware GNU/Linux (http://www.slackware.com/). All prerequisites were installed from the scripts at SlackBuilds.org (http://slackbuilds.org).

## Prerequisites

You need the following:

1.  RepeatMasker (Screen DNA sequence for interspersed repeats)
    * Homepage: http://www.repeatmasker.org/
    * On SBo: http://slackbuilds.org/repository/14.2/academic/RepeatMasker/
2.  BedTools (A powerful toolset for genome arithmetic)
    * Homepage: http://bedtools.readthedocs.org/
    * On SBo: http://slackbuilds.org/repository/14.2/academic/bedtools/
3.  MEME-suite (Motif based sequence analysis tools)
    * Homepage: http://meme-suite.org/
    * On SBo: http://slackbuilds.org/repository/14.2/academic/meme-suite/
4.  Motif databases (Used by the MEME Suite)
    * Download: http://meme-suite.org/doc/download.html
    * Location: `/var/lib/meme-suite/motif_databases`

## TFBS: transcription factor binding sequences

Scripts are divided into two folders (check each sub-folder for detailed instructions):

### tfKnown

This folder contains scripts that were used in our study to acquire data for transcription factor (TF) binding sequences. We used TFs reported for _H. sapiens_ to also screen the corresponding genomic regions of other species. Contents:

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
    * `mastBestSort`: Create a CVS table of the best TF hits.
    
### tfUnknown

This folder contains scripts that were used in our study to predict for novel TF binding sequences. We used TFs predicted for _H. sapiens_ to also screen the corresponding genomic regions of other species. Contents:

* 01_memePrepUnknown/
    * `memePrepUnknown`: Extract and sort corresponding genomic regions from multiple species
    * `sequenceRepeatMasker`: Mask repeates on the sorted genomic regions
* 02_searchUnknown/
    * `novelTF`: Search for novel transcription factor binding sites by MEME-suite
* 03_mastOnlyUnknown/
    * `mastOnlyUnknown`: Run MAST with selected PFM on genomic regions of interest
* 04_mastBestSortUnknown/
    * `mastBestSortUnknown`: Create a CVS table of the best TF hits

## Scripts output

The scripts use `/tmp` for their working and output dirs. The only exception is the scripts found in 00_batchFromNCBI, which use `/var/tmp/chromosomes`.
